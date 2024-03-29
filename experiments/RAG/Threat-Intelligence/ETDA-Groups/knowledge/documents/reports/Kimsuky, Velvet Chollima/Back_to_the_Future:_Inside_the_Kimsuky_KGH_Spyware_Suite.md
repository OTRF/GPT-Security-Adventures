# Reference for threat actor for "Kimsuky, Velvet Chollima"

**Title**: Back to the Future: Inside the Kimsuky KGH Spyware Suite

**Source**: https://www.cybereason.com/blog/back-to-the-future-inside-the-kimsuky-kgh-spyware-suite

## Content






Back to the Future: Inside the Kimsuky KGH Spyware Suite









































































Back to Cybereason.com









All Posts
Research
Podcasts
Webinars
Resources
Videos
News


Subscribe






















Subscribe




All
Research
Podcasts
Webinars
Resources
Videos
News







Search


Subscribe






 
            X
        




Search



























Back to the Future: Inside the Kimsuky KGH Spyware Suite


Written By
Cybereason Nocturnus







Research by: Assaf Dahan, Lior Rochberger, Daniel Frank and Tom Fakterman

The Cybereason Nocturnus Team has been tracking various North Korean threat actors, among them the cyber espionage group known as Kimsuky, (aka: Velvet Chollima, Black Banshee and Thallium), which has been active since at least 2012 and is believed to be operating on behalf of the North Korean regime. The group has a rich and notorious history of offensive cyber operations around the world, including operations targeting South Korean think tanks, but over the past few years they have expanded their targeting to countries including the United States, Russia and various nations in Europe. Some of their observed targets include:
• Pharmaceutical/Research companies working on COVID-19 vaccines and therapies• UN Security Council• South Korean Ministry of Unification • Various Human Rights Groups• South Korean Institute for Defense Analysis• Various Education and Academic Organizations• Various Think Tanks• Government Research Institutes• Journalists covering Korean Peninsula relations• South Korean Military
On October 27th, the US-CERT published a report summarizing Kimusky’s recent activities and describing the group’s TTPs and infrastructure.
Combining the information in the report with the intelligence accumulated by Cybereason Nocturnus over time, the researchers discovered a previously undocumented modular spyware suite dubbed KGH_SPY that provides Kimsuky with stealth capabilities to carry out espionage operations. 
In addition, Cybereason Nocturnus uncovered another new malware strain dubbed CSPY Downloader that was observed to be a sophisticated tool with extensive anti-analysis and evasion capabilities, allowing the attackers to determine if  “the coast is clear” before downloading additional payloads. 
Lastly, the Cybereason Nocturnus team identified new server infrastructure used by Kimsuky that overlaps with previously identified Kimsuky infrastructure.

KGH backdoor caught by Cybereason Platform
Table of Contents
- Key Findings
- Kimsuky Infrastructure Overlap
- New Toolset Infrastructure
- Back to the Future: Suspected Anti-Forensics
- KGH Spyware Suite
- Infection Vector: Weaponized Word Documents
- KGH Spyware Payloads Overview
- Analysis of the KGH Installer (M1.dll)
- Analysis of the KGH Backdoor Loader (msic.exe)
- KGH Backdoor Commands 
- KGH Infostealer Module (m.dll)
- CSPY Downloader - A New Downloader in the Arsenal
- Anti-analysis Techniques
- Conclusion
- MITRE ATTACK Breakdown
- Indicators of Compromise

Key Findings
• Discovery of a New Modular Spyware Suite: “KGH_SPY” is a modular suite of tools that provides the threat actors with reconnaissance, keylogging, information stealing and backdoor capabilities
• Discovery of a Stealthy New Malware: “CSPY Downloader” is a tool designed to evade analysis and download additional payloads
• New toolset Infrastructure: Newly discovered toolset infrastructure registered between 2019-2020 that overlaps with another Kimsuky’s malware called BabyShark that was used in the past to target US-based Think tanks 
• Anti-Forensics: The creation/compilation timestamps of malware in the report appear to have been tampered with and backdated to 2016 in an attempt to thwart forensic investigation
• Behavioral and Code Similarities to Other Kimsuky Malware: The newly discovered malware shares various behavioral and code similarities to known Kimsuky malware, including: code signing with EGIS revoked certificate; shared strings; file naming convention; string decryption algorithms; PDB paths referencing authors / projects
• Undetected by Antivirus: At the time of writing this report, some of the mentioned payloads  are not detected by any antivirus vendors

Kimsuky Infrastructure Overlap
Kimsuky is known for their complex infrastructure that uses free-registered domains, compromised domains, as well as private domains registered by the group. Tracking down the infrastructure, the Nocturnus team was able to detect overlaps with BabyShark malware and other connections to different malware such as AppleSeed backdoor:

Infrastructure graph for different Kimsuky’s domains and the overlaps between them
Throughout the years, Kimsuky has been using an array of malware in their operations. The infrastructure of some of the malware used by Kimsuky can be tracked using pattern analysis of the URI structures used by some of their tools. The following table maps commonly observed URI patterns to their respective malware: 




Malware name


Description


C2 URL Pattern




AppleSeed 


Backdoor


http://hao.aini.pe[.]hu/init/image?i=ping&u=8dc1078f1639d34c&p=wait..
http://mernberinfo[.]tech/wp-data/?m=dunan&p=de3f6e263724&v=win6.1.0-sp1-x64
http://eastsea.or[.]kr/?m=a&p1=00000009&p2=Win6.1.7601x64-Spy-v2370390




FlowerPower


Powershell based profiling tool


http://dongkuiri.atwebpages[.]com/venus02/venus03/venus03.ps1
http://attachchosun.atwebpages[.]com/leess1982/leess1982.ps1




Gold Dragon


Backdoor


http://portable.epizy[.]com/img/png/download.php?filename=images01
http://foxonline123.atwebpages[.]com/home/jpg/download.php?filename=flower03




BabyShark


VBS-based backdoor and reconnaissance tool


http://nhpurumy.mireene[.]com/theme/basic/skin/member/basic/ upload/download.php?param=res2.txt
http://jmable.mireene[.]com/shop/kcp/js/com/expres.php?op=2




New toolset Infrastructure
By tracking the previous infrastructure and correlating the data regarding the URI patterns used by different Kimsuky tools, the Cybereason Nocturnus Team was able to uncover a new infrastructure that was used by the new malware toolset: 




Malware name


Description


C2 URL Pattern




KGH malware suite


Different components in the KGH malware suite


http://csv.posadadesantiago[.]com/home?id=[Machine_name]&act=sbk&ver=x64
http://csv.posadadesantiago[.]com/home/up.php?id=[Machine_name]




CSPY Downloader


Downloader


http://wave.posadadesantiago[.]com/home/dwn.php?van=10860http://wave.posadadesantiago[.]com/home/dwn.php?van=101http://wave.posadadesantiago[.]com/home/dwn.php?van=102




KGH_Backdoor
winload.x


Backdoor and Keylogger component, VBS downloader


http://csv.posadadesantiago[.]com/home?act=news&id=[Machine_name]
http://csv.posadadesantiago[.]com/home?id=ֿ[Machine_name]&act=upf&ver=x64
http://csv.posadadesantiago[.]com/home?id=[Machine_name]&act=tre&ver=x64
http://csv.posadadesantiago[.]com/home?id=[Machine_name]&act=wbi&ver=x64
http://csv.posadadesantiago[.]com/home?id=[Machine_name]&act=cmd&ver=x64
http://csv.posadadesantiago[.]com/home?id=[Machine_name]&act=pws&ver=x64




PM_Abe_draft_letter _on_UN_NK_20200130.doc


Phishing document


http://myaccounts.posadadesantiago[.]com/test/Update. php?wShell=201




 
The new domains are all registered to the same IP address that was reported in previous Kimsuky-related attacks involving the Baby Shark malware: 




IP Address


Domain Name


Kimsuky Activity




173.205.125.124


csv.posadadesantiago[.]com


KGH Backdoor




wave.posadadesantiago[.]com


CSPY Downloader




myaccounts.posadadesantiago[.]com


Malicious Phishing Document




www.eventosatitlan[.]com


Baby Shark / Autumn Aperture Campaign





Phishing Themes related to the New Infrastructure
When analyzing the weaponized phishing documents that were connected to the new tools infrastructure, one can notice the topic of human rights in the North Korea repeated in at least two documents: 

PM_Abe_draft_letter_on_UN_NK_20200130.doc - This document contains what appears to be a letter in English and Japanese that was addressed to the (now former) Prime minister of Japan, Shinzo Abe, regarding the subject of human rights in North Korea. The document’s malicious macro code communicates with the domain myaccounts.posadadesantiago[.]com 
Interview with a north korean defector.doc - This document contains an interview with a North Korean defector who escaped to Japan and discusses problems with life in North Korea. This document drops a malware that communicates with the domain wave.posadadesantiago[.]com


The topic of human rights violations in North Korea previously appeared in multiple phishing documents attributed to Kimsuky. 

Phishing Documents containing DPRK-related human rights issues

Back to the Future: Suspected Anti-Forensics 
Backdating, or timestomping, is a technique used by many threat actors which involves the manipulation of the creation timestamps or compilation date of a file in order to thwart analysis attempts (anti-forensics). It is suspected that the creation date of most of the files mentioned in this report were tampered with by the threat actors and backdated to 2016:




Name


SHA-256


Creation Date (likely fake)


VT Upload Date




m1.dll 
cur_install_x64.dll


af13b16416760782ec81d587736cb4c9b2e7099afc10cb764eeb4c 922ee8802f


2016-10-02 07:35:25


2020-10-07 13:03:45




msic.exe


E4d28fd7e0fc63429fc199c1b683340f725f0bf9834345174ff0b6a 3c0b1f60e


2016-09-28 02:08:00


2020-10-07 13:03:530




msfltr32.dll


66fc8b03bc0ab95928673e0ae7f06f34f17537caf159e178a452c2 c56ba6dda7


2016-10-02 07:23:16


2020-10-07 13:03:56




m.dll


f989d13f7d0801b32735fee018e816f3a2783a47cff0b13d70ce2f  1cbc754fb9


2016-09-28 08:41:36


2020-10-07 13:03:56




0807.dotm


97d4898c4e70335f0adbbace34593236cb84e849592e5971a797 554d3605d323


2016-08-07 11:31:00


2020-08-19 09:46:33




0928.dotm


d88c5695ccd83dce6729b84c8c43e8a804938a7ab7cfeccaa0699 d6b1f81c95c


2016-09-28 02:08:00


2020-10-06 07:53:38




winload.exe


7158099406d99db82b7dc9f6418c1189ee472ce3c25a3612a5ec 5672ee282dc0


2016-07-30 01:20:23


2020-06-12 01:48:02




 
The assumption is backed by the registration dates of the domains that were hardcoded in all the above mentioned malware samples. According to the domain registration information in RiskIQ PassiveTotal, these domains were first registered between January 2019 to August 2020, years after the seemingly manipulated creation dates: 




Domain


IP Resolution


First Observed


Earliest Observed Certificate Issue Date




csv.posadadesantiago[.]com


173.205.125.124


2020-08-09


SHA-1: 87b35e1998bf00a8b7e32ed391c217deaec408ad 
Date: 2020-08-19




wave.posadadesantiago[.]com


173.205.125.124


2020-02-27


SHA-1: F846981567760d40b5a90c8923ca8c2e7c881c5f 
Date: 2020-03-24




myaccounts.posadadesantiago[.]com


173.205.125.124


2019-01-25


SHA-1: 90d00ecb1e903959a3853e8ee1c8af89fb82a179 
Date: 2019-01-25





KGH Spyware Suite

The connection between different components of the KGH malware suite
During our analysis, Cybereason Nocturnus discovered a new malware suite dubbed “KGH” which contains several modules used as spyware. The name “KGH” is derived from the PDB path and internal names found in the malware samples: 

“KGH” in an internal name of the backdoor

“m.dll” pdb path
A possible link to North Korean attacks referencing the name “KGH” was mentioned in 2017 in a research by Ahnlab, however it is unclear whether it is related to the same malware authors. 

Infection Vector: Weaponized Word Documents
The infection vector seems to originate from a Word documents containing malicious macros: 




Name


SHA-256


Domain


Creation Date (likely fake)


VT Upload Date




0807.dotm


97d4898c4e70335f0adbbace34593236cb 84e849592e5971a797554d3605d323


csv.posadadesantiago.com


2016-08-07 11:31:00


2020-08-19 09:46:33




0928.dotm


d88c5695ccd83dce6729b84c8c43e8a804 938a7ab7cfeccaa0699d6b1f81c95c


csv.posadadesantiago.com


2016-09-28 02:08:00


2020-10-06 07:53:38




We observed two Word documents that communicate with the domains above which contain code similarities to each other and to the previously mentioned “Interview with a north korean defector.doc”. The macros of the malicious documents do the following: 
0807.dotm:

1. Drops a script named “winload.x” and a wscript.exe binary renamed as “cs.exe” to “%appdata%\Micorosoft\Templates”.



2. Sets the reg key “HKCU\Environment\UserInitMprLogonScript” to run a cmd command that copies “winload.x” as “a.vbs”, executes it and deletes “a.vbs”.  The mentioned registry key is used to execute Logon Scripts, and will execute what is written to it at startup. The document is using this key to achieve persistence for the file “winload.x”:


Persistence using UserInitMprLogonScript Registry keys

3. Collects system, network and drive information and installed applications, saves it to a file named “info” and sends it to the C2 using iexplorer.exe
4. When “winload.x” (“a.vbs”) is executed, it tries to download and execute code from “csv.posadadesantiago[.]com/home?act=news&id=[Machine_name]”:


Winload.x (a.vbs) contents deobfuscated
0928.dotm:

1. Collects information about the infected system, network, drives, and installed applications.
2. Saves the collected information to a file named “info” in “%appdata%\Micorosoft\Templates” and sends it to the C2.
3. Downloads m1.dll (KGH Installer) from “csv.posadadesantiago[.]com/home?id=[Machine_name]&act=sbk&ver=x64”
4. Downloads m.dll (KGH-Browser Stealer) from “csv.posadadesantiago[.]com/home?id=[Machine_name]&act=wbi&ver=x64”
5. Executes the KGH installer:


URLs creation from 0928.dotm macro code
Both documents use similar function names and variable names:

0928.dotm VB code (left) & 0807.dotm VB code (right)
Once the macro collected all the information, it sends the data to the C2 server over an HTTP POST request: 

Exfiltration of the collected system information stored in “info”

KGH Spyware Payloads Overview
The following payloads were observed to be downloaded and dropped by the previously mentioned malicious documents:




File Name(s)


Purpose


Creation Date (likely fake)


VT Upload Date




m1.dll 


Drops KGH backdoor and creates persistence to msic.exe and drops: 
 - C:\Users\user\AppData\Local\AreSoft\msic.exe
 - C:\Users\user\AppData\Local\AreSoft\msfltr32.dll
 


2016-10-02 07:35:25


2020-10-07 13:03:45




msic.exe


Loads and executes msfltr32.dll
C:\Users\user\AppData\Local\AreSoft\msfltr32.dll


2016-09-28 02:08:00


2020-10-07 13:03:53




msfltr32.dll


KGH backdoor capabilities: 

 - Persistence
 - Keylogger
 - Downloads additional payloads
- Executes arbitrary commands (cmd.exe / powershell)



2016-10-02 07:23:16


2020-10-07 13:03:56




m.dll


KGH-Browser Stealer 
Steals stored data from Chrome, Edge, Firefox, Thunderbird, Opera, Winscp. 


2016-09-28 08:41:36


2020-10-07 13:03:56




 
The following files were downloaded / dropped by the macro as caught by the Cybereason platform: 

Cybereason defense platform presenting the creation of the files

Analysis of the KGH Installer (M1.dll)
The KGH installer was uploaded to VirusTotal in October 2020 and at the time of writing this report is not detected by any Antivirus engines: 

 KGH installer detections in VT
The file is a DLL that executes the installation / dropper code located in the “outinfo” export:

 KGH installer exports
The DLL contains two encrypted blobs in its resource section. It can be noticed that there are traces of Korean language in those resources: 

 KGH installer resources
These encrypted blobs are dropped to C:\Users\user\AppData\Local\Temp\3f34a.tmp one after the other. Once they are dropped, the dropper also decrypts them and writes them to a newly created folder and creates persistence:

C:\Users\user\AppData\Local\AreSoft\msic.exe
C:\Users\user\AppData\Local\AreSoft\msfltr32.dll


Dropped files location on an infected machine
The backdoor achieves persistence by creating the following registry autoruns keys: 

Key: HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows\Load
Value: C:\Users\user\AppData\Local\AreSoft\msic.exe


Analysis of the KGH Backdoor Loader (msic.exe)
The KGH loader (msic.exe) is responsible for loading and executing the KGH backdoor DLL (msfltr32.dll) in memory: 

Msic.exe loads msfltr32.dll to memory
The file itself is unsigned and masquerades as a legitimate Microsoft Windows tool:

Msfltr32.dll Signature Info
KGH Backdoor - Main Module (msfltr32.dll)
The msfltr32.dll module is the core module of the KGH backdoor. The backdoor contains the following functionality: 

• Persistence using autorun keys
• Keylogger
• Directory and file listing
• Downloading secondary payloads from the C2 server
• Exfiltrating collected information from the host to the C2 server
• Executing arbitrary commands via cmd.exe or PowerShell

KGH Backdoor: Keylogger Functionality
The KGH backdoor has a keylogger functionality built into its code, which is achieved by a common technique of polling the GetAsyncKeyState() function:

Excerpt from KGH’s Keylogger function
The recorded keystrokes are stored in the “lg” folder in %appdata% with the file extension “.x”
KGH Backdoor Secondary Payloads
The KGH backdoor contacts the C2 with URL “csv.posadadesantiago[.]com/home?act=news&id=[Machine_name]” and saves the response to “C:\Users\user\AppData\Local\Temp\n.x”:

URL string in KGH Backdoor
The KGH backdoor will then parse the contents of “n.x”. The “n.x” file may contain an “SHL”, “DLL” or “EXE” file.
In case it is a “DLL” or an “EXE” the KGH backdoor will execute the file. In case the downloaded file contains an “SHL” file, the KGH backdoor will parse the file to retrieve commands sent by the C2:

Check “n.x” file type code from KGH backdoor 

KGH Backdoor Commands
The KGH backdoor has a predefined set of commands that it receives from the server: 

KGH’s backdoor commands




Command


Purpose




upf


Uploads files to the C2




tre


Create a list of all files in the system using the “tree” command, save to a file named “c.txt” and upload the file to the C2




wbi


Download “m.dll” browser stealer module and exfiltrates stolen data




cmd


Execute a cmd shell command




pws


Execute a powershell command 




 
List of files generated by or downloaded by the KGH backdoor: 




File


Purpose




C:\Users\user\AppData\Roaming\lg\[year_month_day].x


Keylogger stolen data storage




C:\Users\user\AppData\Local\Temp\n.x


Payload downloaded from the server




C:\Users\user\AppData\Local\Temp\C.txt


Output of tree command (directory and files listing)
C:\Windows\System32\cmd.exe /c tree /f C:\ >> C:\Users\user\AppData\Local\Temp\C.txt




C:\Users\user\Documents\w.x


Stolen browser data (from m.dll module)




sig.x


Likely checks write permission to the disk




C:\test1.txt


N/A





KGH Infostealer Module (m.dll)
Another component of the KGH suite is the m.dll module, which is an information stealer that harvest data from browsers, Windows Credential Manager, WINSCP and mail clients. The infostealer module is not detected by any AV vendor at the time of writing this report: 

KGH infostealer module is undetected by any Antivirus vendors
The PDB path embedded in the m.dll module further shows a clear connection to the KGH backdoor, as it is named “KGH_Browser-Master”:

E:\SPY\WebBrowser\KGH_Browser-Master\x64\Release\KGH_Browser-Master.pdb
The “SPY” user was also observed in PDB of the “CSPY Downloader”, which is also mentioned in this report: 

PDB Path of the CSPY Downloader
The infostealer module steals information stored (cookies, credentials) in the following applications: 


• Browsers: Chrome, IE / Edge, Firefox, Opera



• WinSCP Client


• Windows Credential Manager


• Mozilla Thunderbird Mail Client


Main Infostealing routine
The stolen information is written to a file called “w.x”: 

Creation of the “w.x” file that stores the stolen data

CSPY Downloader - A New Downloader in the Arsenal
When hunting for some of the URI patterns mentioned in the US-CERT report (“/home/dwn.php?van=101”), another malicious executable was found communicating with the C2 wave.posadadesantiago[.]com, named winload.exe.
This sample was delivered by a malicious document named “Interview with a north Korean defector”. The macro embedded inside unpacks and executes winload.exe.
Upon analysis, the Nocturnus determined that winload.exe is a new type of a downloader, dubbed “CSPY” by Cybereason, that is packed with robust evasion techniques meant to ensure that the “coast is clear” and that the malware does not run in a context of a virtual machine or analysis tools before it continues to download secondary payloads: 

VirusTotal uploads of winload.exe communicating with the above mentioned C2
This file is mentioned in the report by ESTSecurity. In alignment with the findings there, it is packed with UPX, has resources in Korean, Anti-VM functionality and a timestamp that is tempered to July 30, 2016:

The PDB Path of the CSPY Downloader

PDB Path and resources of the malware
The file is also signed with the following revoked certificate. As can be seen, the signing date may be fake as well. EGIS Co., Ltd certificate issuer was previously reported to be used by Kimsuky:

Kimsuky’s typical revoked certificate
When further examining the file, some interesting functionality can be found. Indicative strings and API calls can be decrypted by deducting 1 from each character, similar to the KGH backdoor whose strings can be decrypted by deducting 5 from each character. When decrypting the strings, the malware’s full logs are revealed. The log file is stored in %appdata%\microsoft\NTUSERS.log:

Decrypted logging strings of CSPY Downloader
It is interesting to note that some of the abovementioned log strings are grammatically incorrect, which can suggest that the malware author is not a native English speaker.
The above logs imply that this sample might be a debug version of the malware. In many cases, debug versions are used by the malware authors for testing new malware or new features. This can also suggest that the malware is newly developed and has not been fully operationalized yet. Another clue that points to this assumption is that some parts of the malware code seem to be buggy or incomplete.

Anti-analysis Techniques
Prior to downloading secondary payloads, CSPY Downloader initiates an extensive series of checks to determine if it is being debugged or running in a virtual environment, by searching for specific virtualization-related loaded modules, the process PEB structure, various file paths, registry keys, and memory:

A list of methods performing anti-analysis checks by the malware
It is worth mentioning that the document which unpacks CSPY Downlader, runs an almost identical series of Anti-VM techniques prior to dropping the downloader, which highlights the attackers’ efforts to avoid detection and remain under-the-radar.
After the anti-analysis checks are complete, the loader starts preparing the infected environment for the downloading of additional payloads. There are 3 download attempts (and thus 3 GET requests trailing by a different numeric ID), the payloads are downloaded subsequently to the user’s %temp% folder.

Payloads download method
After downloading the payloads, they are moved and renamed. The whole process can be summarized as follows:




Download URI


Filename


Copied To


Purpose




dwn.php?van=10860


dwn.dat0


%temp%\Appx.exe


Main executable




dwn.php?van=101


dwn.dat1


C:\Users\Public\Documents\AppxUp\BSup.hf


Possible module




dwn.php?van=102


dwn.dat2


C:\Users\Public\Documents\AppxUp\BCup.hf


Possible module




 
To execute the main downloaded payload, the loader tries to masquerade as a legitimate Windows service, claiming in its fake description, that it is used to support packed applications:

Registering the freshly downloaded malware as a service
In order to avoid raising suspicions from the victim, CSPY Downloader exploits a known UAC bypass technique that uses the SilentCleanup task to execute the binary with elevated privileges.

Using schtasks utility to disable UAC
As part of the exploitation process, the above value will be written to the registry under the %windir% variable, and deleted after execution. Appx.exe is moved once again, this time to %programdata%\Microsoft\Windows and registered as a service.
Finally, CSpy will initiate its self-deletion method.

Conclusion
In this report we uncovered a new toolset infrastructure that is used by the Kimsuky group, a notorious activity group that has been operating on behalf of the North Korean regime since 2012. A close examination of the new infrastructure combined with pattern-analysis led Cybereason’s Nocturnus team to the discovery of the “KGH Spyware Suite”, a modular malware likely involved in recent espionage operations, and the “CSPY Downloader” - both were previously undocumented. 
In addition, our report shows certain interesting overlaps between older Kimsuky malware and servers and the newly discovered malware and infrastructure. Moreover, the report highlights several behavior-based and code similarities between the new malware samples and older known Kimsuky malware and TTPs. 
Throughout the report it is noticeable that the threat actors invested efforts in order to remain under the radar, by employing various anti-forensics and anti-analysis techniques which included backdating the creation/compilation time of the malware samples to 2016, code obfuscation, anti-VM and anti-debugging techniques. At the time of writing this report, some of the samples mentioned in the report are still not detected by any AV vendor. 
While the identity of the victims of this campaign remains unclear, there are clues that can suggest that the infrastructure targeted organizations dealing with human rights violations. At the time of writing this report, there is not enough information available to Cybereason to determine this with a high certainty, and in any case, there could be a wide range of industries, organizations and individuals that were targeted by Kimsuky using this infrastructure.

MITRE ATT&CK BREAKDOWN




Reconnaissance


Initial Access


Execution


Persistence


Defense Evasion


Credential Access


Discovery


Collection


Exfiltration




Gather Victim Host Information


Phishing


Command and Scripting Interpreter


Registry Run Keys 


Masquerading


Credentials from Web Browsers


File and Directory Discovery


Keylogging


Exfiltration Over C2 Channel




Gather Victim Network Information

 

User Execution


Logon Script (Windows)


Bypass User Account Control


Keylogging


System Information Discovery

 
 


 
 
 

Windows  Service


Timestomp


Steal Web Session Cookie


System Network Configuration Discovery

 
 


 
 
 
 

Software Packing

 

Virtualization/Sandbox Evasion

 
 



 

Indicators of Compromise
URLs:
http://csv.posadadesantiago[.]com/home?act=news&id=[Machine_name]
http://csv.posadadesantiago[.]com/home?id=[Machine_name]&act=upf&ver=x64
http://csv.posadadesantiago[.]com/home?id=[Machine_name]&act=tre&ver=x64
http://csv.posadadesantiago[.]com/home?id=[Machine_name]&act=wbi&ver=x64
http://csv.posadadesantiago[.]com/home?id=[Machine_name]&act=cmd&ver=x64
http://csv.posadadesantiago[.]com/home?id=[Machine_name]&act=pws&ver=x64
http://csv.posadadesantiago[.]com/home?id=[Machine_name]&act=sbk&ver=x64
http://csv.posadadesantiago[.]com/home/up.php?id=[Machine_name]
http://myaccounts.posadadesantiago[.]com/test/Update.php?wShell=201
http://wave.posadadesantiago[.]com/home/dwn.php?van=10860
http://wave.posadadesantiago[.]com/home/dwn.php?van=101
http://wave.posadadesantiago[.]com/home/dwn.php?van=102
Domains
csv.posadadesantiago[.]com
wave.posadadesantiago[.]com
myaccounts.posadadesantiago[.]com
www.eventosatitlan[.]com
IPs
173.205.125.124
Malicious Documents
97d4898c4e70335f0adbbace34593236cb84e849592e5971a797554d3605d323
d88c5695ccd83dce6729b84c8c43e8a804938a7ab7cfeccaa0699d6b1f81c95c
7af3930958f84e0b64f8297d1a556aab359bb65691208dc88ea4fc9698250c43
252d1b7a379f97fddd691880c1cf93eaeb2a5e5572e92a25240b75953c88736c
KGH SPYWARE SUITE
Bcf4113ec8e888163f1197a1dd9430a0df46b07bc21aba9c9a1494d2d07a2ba9
af13b16416760782ec81d587736cb4c9b2e7099afc10cb764eeb4c922ee8802f
E4d28fd7e0fc63429fc199c1b683340f725f0bf9834345174ff0b6a3c0b1f60e
66fc8b03bc0ab95928673e0ae7f06f34f17537caf159e178a452c2c56ba6dda7
f989d13f7d0801b32735fee018e816f3a2783a47cff0b13d70ce2f1cbc754fb9
Fa282932f1e65235dc6b7dba2b397a155a6abed9f7bd54afbc9b636d2f698b4b
65fe4cd6deed85c3e39b9c1bb7c403d0e69565c85f7cd2b612ade6968db3a85c
CSPY Downloader
7158099406d99db82b7dc9f6418c1189ee472ce3c25a3612a5ec5672ee282dc0
e9ea5d4e96211a28fe97ecb21b7372311a6fa87ce23db4dd118dc204820e011c




Share



















About the Author
Cybereason Nocturnus






The Cybereason Nocturnus Team has brought the world’s brightest minds from the military, government intelligence, and enterprise security to uncover emerging threats across the globe. They specialize in analyzing new attack methodologies, reverse-engineering malware, and exposing unknown system vulnerabilities. The Cybereason Nocturnus Team was the first to release a vaccination for the 2017 NotPetya and Bad Rabbit cyberattacks.
All Posts by Cybereason Nocturnus











Related Posts




PowerLess Trojan: Iranian APT Phosphorus Adds New PowerShell Backdoor for Espionage
Cybereason discovered a new toolset developed by Iranian APT Phosphorus which revealed a connection to Memento ransomware and includes the newly discovered PowerLess Backdoor that evades detection by running PowerShell in a .NET context...





Operation CuckooBees: Deep-Dive into Stealthy Winnti Techniques
Cybereason investigated multiple intrusions targeting technology and manufacturing companies located in Asia, Europe and North America. Based on the findings of our investigation, it appears that the goal behind these intrusions was to steal sensitive intellectual property for cyber espionage purposes...




















Subscribe
Never miss a blog.



Recent Posts


From Cracked to Hacked: Malware Spread via YouTube Videos




THREAT ALERT: Ivanti Connect Secure VPN Zero-Day Exploitation




Malicious Life Podcast: SIM Registration: Security, or Surveillance?




Categories

Research
Podcasts
Webinars
Resources
Videos
News

All Posts














Related Posts




PowerLess Trojan: Iranian APT Phosphorus Adds New PowerShell Backdoor for Espionage
Cybereason discovered a new toolset developed by Iranian APT Phosphorus which revealed a connection to Memento ransomware and includes the newly discovered PowerLess Backdoor that evades detection by running PowerShell in a .NET context...





Operation CuckooBees: Deep-Dive into Stealthy Winnti Techniques
Cybereason investigated multiple intrusions targeting technology and manufacturing companies located in Asia, Europe and North America. Based on the findings of our investigation, it appears that the goal behind these intrusions was to steal sensitive intellectual property for cyber espionage purposes...














NEWSLETTER
Never miss a blog
Get the latest research, expert insights, and security industry news.
Subscribe












Want to see the Cybereason Defense Platform in action?
Schedule a Demo

X
























About

Who We Are
Careers

Contact



Resources

Blog
Case Studies
Webinars
White Papers



Platform

Overview
Endpoint Protection
EDR
MDR








©Cybereason 2024. All Rights Reserved.



Terms of Use
Privacy Notice
Do Not Sell
Security









































