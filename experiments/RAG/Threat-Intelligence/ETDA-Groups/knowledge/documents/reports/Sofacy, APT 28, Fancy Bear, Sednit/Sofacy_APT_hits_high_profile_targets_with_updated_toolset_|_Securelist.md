# Reference for threat actor for "Sofacy, APT 28, Fancy Bear, Sednit"

**Title**: Sofacy APT hits high profile targets with updated toolset | Securelist

**Source**: https://securelist.com/sofacy-apt-hits-high-profile-targets-with-updated-toolset/72924/

## Content















Sofacy APT hits high profile targets with updated toolset | Securelist


































































Solutions for:

Home Products
Small Business 1-50 employees
Medium Business 51-999 employees
Enterprise 1000+ employees
 



















by Kaspersky


CompanyAccount
Get In Touch
Dark mode off
EnglishRussianSpanish













Solutions



Hybrid Cloud SecurityLearn More
Internet of Things & Embedded SecurityLearn More
Threat Management and DefenseLearn More
Industrial CybersecurityLearn More
Fraud PreventionLearn More



Other solutions
Blockchain Security
Kaspersky for Security Operations Center


Industries



National CybersecurityLearn More
Industrial CybersecurityLearn More
Finance Services CybersecurityLearn More
Healthcare CybersecurityLearn More
Transportation CybersecurityLearn More
Retail CybersecurityLearn More



Other Industries
Telecom Cybersecurity
Blockchain Security
View all


Products



KasperskyEndpoint Security for BusinessLearn More
KasperskyEndpoint Detection and Response (EDR)Learn More
KasperskyEDR OptimumLearn More
KasperskyAnti Targeted Attack PlatformLearn More
KasperskyManaged Detection and ResponseLearn More
KasperskySandboxLearn More



Other Products
Kaspersky Security for Mail Server
Kaspersky Security for Internet Gateway
Kaspersky Embedded Systems Security
Kaspersky Hybrid Cloud Security for AWS
Kaspersky Hybrid Cloud Security for Azure
View All


Services



KasperskyCybersecurity ServicesLearn More
KasperskyAdaptive Online TrainingLearn More
KasperskyPremium SupportLearn More
KasperskyThreat IntelligenceLearn More
KasperskyAPT Intelligence ReportingLearn More
KasperskyTargeted Attack DiscoveryLearn More



Other Services
Kaspersky Professional Services
Kaspersky Incident Response
Kaspersky Cybersecurity Training
Kaspersky Incident Communications
Kaspersky Security Awareness
View All


Resource Center

Case Studies
White Papers
Datasheets
Technologies
MITRE ATT&CK

About Us

Transparency
Corporate News
Press Center
Careers
Innovation Hub
Sponsorship
Policy Blog
Contacts

GDPR
 





Subscribe
 Dark mode off
Login


Securelist menu

EnglishRussianSpanish
Existing Customers

Personal

My Kaspersky
Renew your product
Update your product
Customer support

Business

KSOS portal
Kaspersky Business Hub
Technical Support
Knowledge Base
Renew License


Home

Products
Trials&Update
Resource Center

Business

Small Business (1-50 employees)
Medium Business (51-999 employees)
Enterprise (1000+ employees)


Securelist
Threats

Financial threats
Mobile threats
Web threats
Secure environment (IoT)
Vulnerabilities and exploits
Spam and Phishing
Industrial threats

Categories

APT reports
Incidents
Research
Malware reports
Spam and phishing reports
Publications
Kaspersky Security Bulletin

Archive
All Tags
APT Logbook
Webinars
Statistics
Encyclopedia
Threats descriptions
KSB 2021

About Us

Company
Transparency
Corporate News
Press Center
Careers
Sponsorships
Policy Blog
Contacts

Partners

Find a Partner
Partner Program
















Content menu
Close













Subscribe













by Kaspersky

 Dark mode off




ThreatsThreats

APT (Targeted attacks)
Secure environment (IoT)
Mobile threats
Financial threats
Spam and phishing
Industrial threats
Web threats
Vulnerabilities and exploits


CategoriesCategories

APT reports
Malware descriptions
Security Bulletin
Malware reports
Spam and phishing reports
Security technologies
Research
Publications


Other sections

Archive
All tags
Webinars
APT Logbook
Statistics
Encyclopedia
Threats descriptions
KSB 2023


 











 

APT reports

Sofacy APT hits high profile targets with updated toolset 

APT reports

04 Dec 2015

  minute read								
















Table of Contents





Sofacy’s August 2015 attack waveConclusionsTechnical analysisSofacy AZZY 4.3 dropper analysisDropper payload – downloader DLLFile collection module (“USB Stealer”)Indicators of compromise:AZZY 4.3 installer:New generation (4.3) AZZY implants:Dropped C&C helper DLL for AZZY 4.3:File collectors / USB stealers:Stand-alone AZZY backdoors:C&C hostnames:Kaspersky Lab products detect the malware mentioned here with the following names: 






 

Authors




GReAT





Sofacy (also known as “Fancy Bear”, “Sednit”, “STRONTIUM” and “APT28”) is an advanced threat group that has been active since around 2008, targeting mostly military and government entities worldwide, with a focus on NATO countries.  More recently, we have also seen an increase in activity targeting Ukraine.
Back in 2011-2012, the group used a relatively tiny implant (known as “Sofacy” or SOURFACE) as its first stage malware. The implant shared certain similarities with the old Miniduke implants. This led us to believe the two groups were connected, at least to begin with, although it appears they parted ways in 2014, with the original Miniduke group switching to the CosmicDuke implant.
At some point during 2013, the Sofacy group expanded its arsenal and added more backdoors and tools, including CORESHELL, SPLM (aka Xagent, aka CHOPSTICK), JHUHUGIT (which is built with code from the Carberp sources), AZZY (aka ADVSTORESHELL, NETUI, EVILTOSS, and spans across four to five generations) and a few others. We’ve seen quite a few versions of these implants and they were relatively widespread for a time.
#Sofacy group has been active since 2008, targeting mostly military and government entities in NATO countriesTweet
Earlier this year, we noticed a new release of the AZZY implant which, at the time, was largely undetected by anti-malware products. We observed several waves of attacks using this version, most recently in October. The new waves of attacks also included a new generation of USB stealers deployed by the Sofacy actor, with the first versions dating back to February 2015, and which appear to be geared exclusively towards high profile targets.
Sofacy’s August 2015 attack wave
In the months leading up to August, the Sofacy group launched several waves of attacks relying on zero-day exploits in Microsoft Office, Oracle Sun Java, Adobe Flash Player and Windows itself. For instance, its JHUHUGIT implant was delivered through a Flash zero-day and used a Windows EoP exploit to break out of the sandbox. The JHUHUGIT implant became a relatively popular first stage for the Sofacy attacks and was used again with a Java zero-day (CVE-2015-2590) in July 2015.
While the JHUHUGIT (and more recently, “JKEYSKW”) implant used in most of the Sofacy attacks, high profile victims are being targeted with another first level implant, representing the latest evolution of their AZZYTrojan.
Two recurring characteristics of the #Sofacy group are speed and the use of multi-backdoor packagesTweet
The first versions of the new AZZY implant appeared in August of this year. During a high profile incident we investigated, our products successfully detected and blocked a “standard” Sofacy “AZZY” sample that was used to target a range of defense contractors. The sample used in this attack (md5 A96F4B8AC7AA9DBF4624424B7602D4F7, compiled July 29th, 2015) was a pretty standard Sofacy x64 AZZY implant, which has the internal name “advshellstore.dll”.
Interestingly, the fact that the attack was blocked didn’t appear to stop the Sofacy team. Just an hour and a half later they had compiled and delivered another AZZY x64 backdoor (md5: 9D2F9E19DB8C20DC0D20D50869C7A373, compiled August 4th, 2015). This was no longer detectable with static signatures by our product. However, it was detected dynamically by the host intrusion prevention subsystem when it appeared in the system and was executed.

This recurring, blindingly-fast Sofacy attack attracted our attention as neither sample was delivered through a zero-day vulnerability — instead, they appeared to be downloaded and installed by another malware. This separate malware was installed by an unknown attack as “AppData\Local\Microsoft\Windows\msdeltemp.dll” (md5: CE8B99DF8642C065B6AF43FDE1F786A3).
The top level malware, CE8B99DF8642C065B6AF43FDE1F786A3 (named by its authors “msdeltemp.dll” according to internal strings, and compiled July 28th, 2015) is a rare type of the Sofacy AZZY implant.  It has been modified to drop a separate C&C helper, (md5: 8C4D896957C36EC4ABEB07B2802268B9) as “tf394kv.dll“.
The dropped “tf394kv.dll” file is an external C&C communications library, compiled on July 24th, 2015 and used by the main backdoor for all Internet-based communications.

Decrypted configuration block of the C&C helper library “tf394kv.dll“
This code modification marks an unusual departure from the typical AZZY backdoors, with its C&C communication functions moved to an external DLL file. In the past, the Sofacy developers modified earlier AZZY backdoors to use a C&C server encoded in the registry, instead of storing it in the malware itself, so this code modularisation follows the same line of thinking.
In addition to the new AZZY backdoors with side-DLL for C&C, we observed a new set of data-theft modules deployed against victims by the Sofacy group. Among the most popular modern defense mechanisms against APTs are air-gaps — isolated network segments without Internet access, where sensitive data is stored. In the past, we’ve seen groups such as Equation and Flame use malware to steal data from air-gapped networks. The Sofacy group uses such tools as well.
The first versions of these new USB stealer modules appeared around February 2015 and the latest appear to have been compiled in May 2015. Older versions of these USBSTEALER modules were previously described by our colleagues from ESET.
One example of the new Sofacy USBSTEALER modules is 8b238931a7f64fddcad3057a96855f6c, which is named internally as msdetltemp.dll.

This data theft module appears to have been compiled in May 2015 and is designed to watch removable drives and collect files from them, depending on a set of rules defined by the attackers. The stolen data is copied into a hidden directory as “%MYPICTURES%\%volume serial number%“, from where it can be exfiltrated by the attackers using one of the AZZY implants. More details on the new USB stealers are available in the section on technical analysis.
Conclusions
Over the last year, the Sofacy group has increased its activity almost tenfold when compared to previous years, becoming one of the most prolific, agile and dynamic threat actors in the arena. This activity spiked in July 2015, when the group dropped two completely new exploits, an Office and Java zero-day.
At the beginning of August, Sofacy began a new wave of attacks, focusing on  defense-related targets. As of November 2015, this wave of attacks is ongoing. The attackers deploy a rare modification of the AZZY backdoor, which is used for the initial reconnaissance. Once a foothold is established, they try to upload more backdoors, USB stealers as well as other hacking tools such as “Mimikatz” for lateral movement.
Over the last year, the #Sofacy group has increased its activity almost tenfold, that spiked in July 2015Tweet
Two recurring characteristics of the Sofacy group that we keep seeing in its attacks are speed and the use of multi-backdoor packages for extreme resilience. In the past, the group used droppers that installed both the SPLM and AZZY backdoors on the same machine. If one of them was detected, the other one provided the attacker with continued access.
As usual, the best defense against targeted attacks is a multi-layered approach. Combine traditional anti-malware technologies with patch management, host intrusion detection and, ideally, allowlisting and default-deny strategies. According to a study by the Australian DSD, 85% of the targeted attacks analysed could have been stopped by four simple defense strategies. While it’s impossible to achieve 100% protection, in practice and most cases all you have to do is increase your defenses to the point where it becomes too expensive for the attacker – who will just give up and move on to other targets.
More information about the Sofacy group is available to customers of Kaspersky Intelligent Services.
Is there a ‘silver bullet’ to protect yourself against Sofacy? Learn more on Kaspersky Business blog.
Technical analysis
Internal name: DWN_DLL_MAIN.dllFile format: PE32 DLLMD5: ce8b99df8642c065b6af43fde1f786a3Linker version: 11.0, Microsoft Visual StudioLinker timestamp: 2015.07.28 13:05:20 (GMT)Exported functions:

10003F30: ?Applicate@@YGHXZ
10004270: ?SendDataToServer_2@@YGHPAEKEPAPAEPAK@Z
10003F60: ?k@@YGPAUHINSTANCE__@@PBD@Z

The library starts its main worker thread from the DllMain function.
Most of the strings inside the module are encrypted with a homebrew XOR-based algorithm. In addition to that, API function names are reversed, presumably to avoid detection in memory.
Once started, the code in the main thread resolves the basic API functions it needs and loads an additional library from the following location: “%TEMP%\tf394kv.dll”. If this file is not present, it is recreated from a hardcoded encrypted array inside the body of the DLL.
Next, the module enters an infinite loop. Every five minutes it collects basic system information and sends it to the C2 server:

Windows version number
Hardcoded string “4.3” (the backdoor’s internal version number)
List of running processes

The main thread also spawns a separate thread for receiving new commands from the C2 servers. Every 10 minutes, it sends a new request to the server. The server is expected to send back executable code and one of the following commands:

Write a new file “%LOCAL_APPDATA%\dllhost.exe” or “%TEMP%\dllhost.exe” and execute it, then delete the file
Write a new file “%LOCAL_APPDATA%\sechost.dll” or “%TEMP%\sechost.dll” and call its first exported function using  “rundll32.exe” or Windows API, then delete the file
Run shellcode provided by the server in a new thread

While processing the commands, the backdoor logs all errors and execution results. The module also reads the contents of the file “%APPDATA%\chkdbg.log” and appends it to the results. It then sends the aggregated log back to the C2 server.
The module aborts the thread receiving C2 command after it fails to correctly execute commands more than six times in a row, i.e. if file or process creation fails.
The export called “k” is a wrapper for the “LoadLibraryA” API function.
The export called “SendDataToServer_2” does exactly what the name means: it encrypts all collected data, encodes it using Base64 encoding and calls its additional library to send the data to the C2 server. The names of the C2 servers are hardcoded.

Hardcoded C&C servers in the main module
The two C&C’s hardcoded in the configuration block of the main binary are:

intelnetservice[.]com
intelsupport[.]net

The export called “Applicate” runs a standard Windows application message loop until a “WM_ENDSESSION” message is received. It then terminates the main thread.
Internal name: snd.dllFile format: PE32 DLLMD5: 8c4d896957c36ec4abeb07b2802268b9Linker version: 11.0, Microsoft Visual StudioLinker timestamp: 2015.07.24 12:07:27 (GMT)Exported functions:

10001580: Init
10001620: InternetExchange
10001650: SendData

This external library implements a simple Wininet-based transport for the main module.
The strings inside the binary are encrypted using 3DES and XOR and reversed.
The DllMain function initializes the library and resolves all required Windows API functions.
The “Init” export establishes connection to port 80 of a C2 server using Wininet API. The user agent string employed is “MSIE 8.0”.
The “SendData” export sends a HTTP POST request using a hardcoded URI “/store/“. The reply, if its length is not equal to six and its contents do not contain “OK” is returned back to the caller.
The “InternetExchange” export closes the established connection and frees associated handles.
Sofacy AZZY 4.3 dropper analysis
File format: PE32 EXEFile size: 142,336 bytesMD5: c3ae4a37094ecfe95c2badecf40bf5bbLinker version: 11.0, Microsoft Visual StudioLinker timestamp: 2015.02.10 10:01:59 (GMT)
Most of the strings and data in the file are encrypted using 3DES and XOR.
The code makes use of the Windows Crypto API for 3DES and the decryption key is stored as a standard Windows PUBLICKEYSTRUC structure:

Part of the decryption algorithm

Header of one encrypted data buffer containing the hardcoded 3DES key
First, it creates a new directory: “%LOCAL_APPDATA%\Microsoft\Windows”. If the directory creation fails it tries to install into “%TEMP%” directory instead.
Next it writes a hardcoded binary from its body to “msdeltemp.dll” into the target directory. If the file exists it then moves it to “__tmpdt.tmp” in the same directory and continues the installation. Sets file creation timestamp to that of “%SYSTEM%\sfc.dll”
To ensure the dropped payload starts automatically on user log-in it creates the following registry key:
[HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Run]
StartUpChekTemp=RUNDLL32.EXE “%path to msdeltemp.dll%”,#1
Next, it starts the dropped dll using the same command line:
RUNDLL32.EXE “%path to msdeltemp.dll%“,#1
Finally, the program removes itself by starting the following command: “cmd /c DEL %path to self%“
The MD5 of the dropped file is f6f88caf49a3e32174387cacfa144a89
Dropper payload – downloader DLL
Internal name: msdetltemp.dllFile format: PE32 DLLFile size: 73 728 bytesMD5:  f6f88caf49a3e32174387cacfa144a89Linker version: 11.0, Microsoft Visual StudioLinker timestamp: 2015.02.10 07:20:02 (GMT)Exported functions:10002B55: Applicate
Most of the strings inside the binary are encrypted using a homebrew XOR-based algorithm and reversed.
The library is an older version of the “DWN_DLL_MAIN.dll” (md5: ce8b99df8642c065b6af43fde1f786a3).
The DllMain function is identical and starts the main thread; the “Applicate” function is identical to the one in the newer library. This version of the module does not rely on an external transport DLL for communicating with its C2 servers; instead it directly uses Wininet API functions.
The module contains the following hardcoded C2 server names:

drivres-update[.]info
softupdates[.]info

The module uses a hardcoded URL (“/check/“) for sending HTTP POST requests to its C2 servers.
The server is expected to send back executable code and one of the following commands:

Write a new file “%LOCAL_APPDATA%\svchost.exe” or “%TEMP%\svchost.exe” and execute it, then delete the file
Write a new file “%LOCAL_APPDATA%\conhost.dll” or “%TEMP%\conhost.dll” and call its first exported function using  “rundll32.exe” or Windows API, then delete the file
Run shellcode provided by the server in a new thread

File collection module (“USB Stealer”)
Internal name: msdetltemp.dll (from resources)File size: 50,176 bytesFile format: PE32 EXEMD5: 0369620eb139c3875a62e36bb7abdae8Linker version: 10.0, Microsoft Visual StudioLinker timestamp: 2015.02.09 11:48:01 (GMT)
Most of the strings inside the binary are encrypted using 3DES and XOR and reversed.
The program creates the mutex “mtx” and an event named “WerTyQ34C”.
Upon start, it creates a window with the class name “Hello” and title “Program”, subscribes for device arrival notifications for that window and enters a standard Windows message processing loop. The message processing function waits for the WM_DEVICECHANGE event and starts a new thread on its arrival.
The module inspects every new disk volume attached to the system. For every disk it creates a “stash” directory in “%root stash directory location%\%volume serial number in hex%” with attributes FILE_ATTRIBUTE_HIDDEN and FILE_ATTRIBUTE_SYSTEM. The root stash directory location may be read from the configuration file or set to the default location which is “%MYPICTURES%”.
Then, it traverses the filesystem of the volume looking for files. Depending on the settings read from the configuration file, the scope may be narrowed to files with particular extensions and/or files created after a specified date.
It is worth noting that if the source file location contains the string “System Volume Information\S-1-5-21-1315235578-283289242\”, then the file is deleted after copying to the “stash” directory. There are known related samples that are able to create such directories on removable drives, i.e. the sample with md5: 8cb08140ddb00ac373d29d37657a03cc.
The configuration file is loaded from the same directory as the module and is expected to have a name “NvCpld.dat“. It is a text file that may contain the following configuration parameters:

Path – location of the root “stash” directory
Ext – search for files with one of these extensions only
Date – search for files not earlier than this date

Internal name: NvCpld.dll (from export table), msdetltemp.dll (from resources), IGFSRVC.dll (from resources)File format: PE32 DLLFile size: 76,288 bytesMD5s:  8b238931a7f64fddcad3057a96855f6c, ce151285e8f0e7b2b90162ba171a4b90Linker version: 11.0, Microsoft Visual StudioLinker timestamps:   2015.05.29 11:20:32 (GMT),  2006.11.25 04:39:15 (GMT)Exported functions:10002500: NvMswt10002860: NvReg10002880: NvStart10002A80: NvStop
This library is a newer version of the file collection module (md5: 0369620eb139c3875a62e36bb7abdae8) wrapped in a DLL file.
There are two known variants of this module; they only differ in timestamp values and version information in the resource section.
The DllMain function only decrypts the data structures and initializes Windows API pointers.
The function “NvMswt” is a wrapper for the API function MsgWaitForMultipleObjects.
The function “NvReg” is a wrapper for the API function RegisterClassW.
The function “NvStart” is similar to the main function of the older module; it creates a window and enters the message loop waiting for device arrival notifications. The only difference introduced is that an event named “WerTyQ34C” can be signalled by the function “NvStop” to terminate the message loop and stop processing.
Indicators of compromise:
AZZY 4.3 installer:
c3ae4a37094ecfe95c2badecf40bf5bb
New generation (4.3) AZZY implants:
ce8b99df8642c065b6af43fde1f786a3f6f88caf49a3e32174387cacfa144a89
Dropped C&C helper DLL for AZZY 4.3:
8c4d896957c36ec4abeb07b2802268b9
File collectors / USB stealers:
0369620eb139c3875a62e36bb7abdae88b238931a7f64fddcad3057a96855f6cce151285e8f0e7b2b90162ba171a4b90f6f88caf49a3e32174387cacfa144a89
Stand-alone AZZY backdoors:
a96f4b8ac7aa9dbf4624424b7602d4f79d2f9e19db8c20dc0d20d50869c7a373
C&C hostnames:

drivres-update[.]info
intelnetservice[.]com
intelsupport[.]net
softupdates[.]info

Kaspersky Lab products detect the malware mentioned here with the following names:

Trojan.Win32.Sofacy.al
Trojan.Win32.Sofacy.be
Trojan.Win32.Sofacy.bf
Trojan.Win32.Sofacy.bg
Trojan.Win32.Sofacy.bi
Trojan.Win32.Sofacy.bj
Trojan.Win64.Sofacy.q
Trojan.Win64.Sofacy.s
HEUR:Trojan.Win32.Generic








APT
Backdoor
Cyber espionage
Nation State Sponsored Espionage
Sofacy



Authors




GReAT





Sofacy APT hits high profile targets with updated toolset 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





Sofacy’s August 2015 attack waveConclusionsTechnical analysisSofacy AZZY 4.3 dropper analysisDropper payload – downloader DLLFile collection module (“USB Stealer”)Indicators of compromise:AZZY 4.3 installer:New generation (4.3) AZZY implants:Dropped C&C helper DLL for AZZY 4.3:File collectors / USB stealers:Stand-alone AZZY backdoors:C&C hostnames:Kaspersky Lab products detect the malware mentioned here with the following names: 





GReAT webinars






																		13 May 2021, 1:00pm								
GReAT Ideas. Balalaika Edition 





Boris Larin



Denis Legezo










																		26 Feb 2021, 12:00pm								
GReAT Ideas. Green Tea Edition 





John Hultquist



Brian Bartholomew



Suguru Ishimaru



Vitaly Kamluk



Seongsu Park



Yusuke Niwa



Motohiko Sato










																		17 Jun 2020, 1:00pm								
GReAT Ideas. Powered by SAS: malware attribution and next-gen IoT honeypots 





Marco Preuss



Denis Legezo



Costin Raiu



Kurt Baumgartner



Dan Demeter



Yaroslav Shmelev










																		26 Aug 2020, 2:00pm								
GReAT Ideas. Powered by SAS: threat actors advance on new fronts 





Ivan Kwiatkowski



Maher Yamout



Noushin Shabab



Pierre Delcher



Félix Aime



Giampaolo Dedola



Santiago Pontiroli










																		22 Jul 2020, 2:00pm								
GReAT Ideas. Powered by SAS: threat hunting and new techniques 





Dmitry Bestuzhev



Costin Raiu



Pierre Delcher



Brian Bartholomew



Boris Larin



Ariel Jungheit



Fabio Assolini












From the same authors




 


Coyote: A multi-stage banking Trojan abusing the Squirrel installer 






 


FakeSG campaign, Akira ransomware and AMOS macOS stealer 






 


Advanced threat predictions for 2024 






 


Stealer for PIX payment system, new Lumar stealer and Rhysida ransomware 






 


Updated MATA attacks industrial companies in Eastern Europe 









Subscribe to our weekly e-mails
The hottest research right in your inbox




Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ








In the same category




 


HrServ – Previously unknown web shell used in APT attack 






 


Modern Asian APT groups’ tactics, techniques and procedures (TTPs) 






 


A cascade of compromise: unveiling Lazarus’ new campaign 






 


How to catch a wild triangle 






 


StripedFly: Perennially flying under the radar 






 















Latest Posts




 



Malware descriptions

Cracked software beats gold: new macOS backdoor stealing cryptowallets 





Sergey Puzan










 



Kaspersky Security Bulletin

Dark web threats and dark market predictions for 2024 





Sergey Lozhkin



Anna Pavlovskaya



Kaspersky Security Services










 



Research

A lightweight method to detect potential iOS malware 





Maher Yamout










 



Research

Operation Triangulation: The last (hardware) mystery 





Boris Larin












Latest Webinars





 




Technologies and services



												11 Dec 2023, 4:00pm					
60 min

The Future of AI in cybersecurity: what to expect in 2024






Vladimir Dashchenko



Victor Sergeev



Vladislav Tushkanov



Dennis Kipker











 




Threat intelligence and IR



												30 Nov 2023, 4:00pm					
70 min

Responding to a data breach: a step-by-step guide






Anna Pavlovskaya











 




Cyberthreat talks



												14 Nov 2023, 4:00pm					
60 min

2024 Advanced persistent threat predictions






Igor Kuznetsov



David Emm



Marc Rivero



Dan Demeter



Sherif Magdy











 




Cyberthreat talks



												09 Nov 2023, 5:00pm					
60 min

Overview of modern car compromise techniques and methods of protection






Alexander Kozlov



Sergey Anufrienko












Reports







HrServ – Previously unknown web shell used in APT attack 

In this report Kaspersky researchers provide an analysis of the previously unknown HrServ web shell, which exhibits both APT and crimeware features and has likely been active since 2021.








Modern Asian APT groups’ tactics, techniques and procedures (TTPs) 

Asian APT groups target various organizations from a multitude of regions and industries. We created this report to provide the cybersecurity community with the best-prepared intelligence data to effectively counteract Asian APT groups.








A cascade of compromise: unveiling Lazarus’ new campaign 

We unveil a Lazarus campaign exploiting security company products and examine its intricate connections with other campaigns








How to catch a wild triangle 

How Kaspersky researchers obtained all stages of the Operation Triangulation campaign targeting iPhones and iPads, including zero-day exploits, validators, TriangleDB implant and additional modules.








 









Subscribe to our weekly e-mails
The hottest research right in your inbox





Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe











Δ








 











ThreatsThreats

APT (Targeted attacks)
Secure environment (IoT)
Mobile threats
Financial threats
Spam and phishing
Industrial threats
Web threats
Vulnerabilities and exploits


CategoriesCategories

APT reports
Malware descriptions
Security Bulletin
Malware reports
Spam and phishing reports
Security technologies
Research
Publications


Other sections

Archive
All tags
Webinars
APT Logbook
Statistics
Encyclopedia
Threats descriptions
KSB 2023


 









© 2024 AO Kaspersky Lab. All Rights Reserved.
Registered trademarks and service marks are the property of their respective owners.



Privacy Policy
License Agreement
Cookies












Subscribe to our weekly e-mails
The hottest research right in your inbox



Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ



























