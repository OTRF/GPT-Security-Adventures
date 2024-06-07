# Reference for threat actor for "Silence, Contract Crew"

**Title**: Silence – a new Trojan attacking financial organizations | Securelist

**Source**: https://securelist.com/the-silence/83009/

## Content















Silence – a new Trojan attacking financial organizations | Securelist



































































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


 











 

Research

Silence – a new Trojan attacking financial organizations 

Research

01 Nov 2017

  minute read								








 

Authors




GReAT





More information about the Silence Trojan is available to customers of Kaspersky Intelligence Reporting Service. Contact: intelreports@kaspersky.com
In September 2017, we discovered a new targeted attack on financial institutions. Victims are mostly Russian banks but we also found infected organizations in Malaysia and Armenia. The attackers were using a known but still very effective technique for cybercriminals looking to make money: gaining persistent access to an internal banking network for a long period of time, making video recordings of the day to day activity on bank employees’ PCs, learning how things works in their target banks, what software is being used, and then using that knowledge to steal as much money as possible when ready.
We saw that technique before in Carbanak, and other similar cases worldwide. The infection vector is a spear-phishing email with a malicious attachment. An interesting point in the Silence attack is that the cybercriminals had already compromised banking infrastructure in order to send their spear-phishing emails from the addresses of real bank employees and look as unsuspicious as possible to future victims.
The attacks are currently still ongoing.
Technical details
The cybercriminals using Silence send spear-phishing emails as initial infection vectors, often using the addresses of employees of an already infected financial institution, with a request to open an account in the attacked bank. The message looks like a routine request. Using this social engineering trick, it looks unsuspicious to the receiver:
Spear-phishing email in Russian.
Malicious .chm attachment



md5
dde658eb388512ee9f4f31f0f027a7df


Type
Windows help .chm file



The attachment we detected in this new wave is a “Microsoft Compiled HTML Help” file. This is a Microsoft proprietary online help format that consists of a collection of HTML pages, indexing and other navigation tools. These files are compressed and deployed in a binary format with the .CHM (compiled HTML) extension. These files are highly interactive and can run a series of technologies including JavaScript, which can redirect a victim towards an external URL after simply opening the CHM. Attackers began exploiting CHM files to automatically run malicious payloads once the file is accessed. Once the attachment is opened by the victim, the embedded .htm content file (“start.htm”) is executed. This file contains JavaScript, and its goal is to download and execute another stage from a hardcoded URL:
Part of start.htm embedded file
The goal of the script is to download and execute an obfuscated .VBS script which again downloads and executes the final dropper
Obfuscated VBS script that downloads binary dropper
Dropper



md5
404D69C8B74D375522B9AFE90072A1F4


Compilation
Thu Oct 12 02:53:12 2017


Type
Win32 executable



The dropper is a win32 executable binary file, and its main goal is to communicate with the command and control (C&C) server, send the ID of the infected machine and download and execute malicious payloads.
After executing, the dropper connects to the C&C using a GET request, sends the generated victim ID, downloads the payloads and executes them using the CreateProcess function.
C&C connect request string with ID
C&C connect procedure
Payloads
The payloads are a number of modules executed on the infected system for various tasks like screen recording, data uploading etc.
All the payload modules we were able to identify are registered as Windows services.
Monitoring and control module



md5
242b471bae5ef9b4de8019781e553b85


Compilation
Tue Jul 19 15:35:17 2016


Type
Windows service executable



The main task for this module is to monitor the activity of the victim. In order to do so it takes multiple screenshots of the victim´s active screen, providing a real-time pseudo-video stream with all the victim´s activity. A very similar technique was used in the Carbanak case, where this monitoring was used to understand the victim´s day to day activity.
The module is registered and started by a Windows service named “Default monitor”.
Malicious service module name
After the initial startup, it creates a Windows named pipe with a hardcoded value – “\\.\pipe\{73F7975A-A4A2-4AB6-9121-AECAE68AABBB}”. This pipe is used for sharing data in malicious inter-process communications between modules.
Named pipe creation
The malware decrypts a block of data and saves it as a binary file with the hardcoded name “mss.exe” in a Windows temporary location, and later executes it using the CreateProcessAsUserA function. This dropped binary is the module responsible for the real-time screen activity recording.
Then, the monitoring module waits for a new dropped module to start in order to share the recorded data with other modules using the named pipe.
Screen activity gathering module



md5
242b471bae5ef9b4de8019781e553b85


Compilation
Tue Jul 19 15:35:17 2016


Type
Windows 32 executable



This module uses both the Windows Graphics Device Interface (GDI) and the Windows API to record victim screen activity. This is done using the CreateCompatibleBitmap and GdipCreateBitmapFromHBITMAP functions. Then the module connects to the named pipe created by the previously described module and writes the data in there. This technique allows for the creation of a pseudo-video stream of the victim’s activity by putting together all the collected bitmaps.
Writing bitmaps to pipe
C&C communication module with console backconnect



md5
6A246FA30BC8CD092DE3806AE3D7FC49


Compilation
Thu Jun 08 03:28:44 2017


Type
Windows service executable



The C&C communication module is a Windows service, as are all the other modules. Its main functionality is to provide backconnect access to the victim machine using console command execution. After the service initialization, it decrypts the needed Windows API function names, loads them with LoadLibrary and resolves with GetProcAddress functions.
WinAPI resolving
After successful loading of the WinAPI functions, the malware tries to connect to the C&C server using a hardcoded IP address (185.161.209[.]81).
C&C IP
The malware sends a special request to the command server with its ID and then waits for a response, which consists of a string providing the code of what operation to execute. The options are:

“htrjyytrn” which is the transliteration of “reconnect” (“реконнект” in russian layout).
“htcnfhn” which is the transliteration of “restart” (“рестарт” in russian layout).
“ytnpflfybq” which is the transliteration of “нет заданий” meaning “no tasks”

Finally the malware receives instructions on what console commands to execute, which it does using a new cmd.exe process with a parameter command.
Instruction check
The described procedure allows attackers to install any other malicious modules. That can be easily done using the “sc create” console command.
Winexecsvc tool



md5
0B67E662D2FD348B5360ECAC6943D69C


Compilation
Wed May 18 03:58:26


Type
Windows 64 executable



Also, on some infected computers we found a tool called the Winexesvc tool. This tool basically provides the same functionality as the well-known “psexec” tool. The main difference is that the Winexesvc tool enables the execution of remote commands from Linux-based operating system. When the Linux binary “winexe” is run against a Windows server, the winexesvc.exe executable is created and installed as a service.
Conclusion
Attacks on financial organization remain a very effective way for cybercriminals to make money. The analysis of this case provides us with a new Trojan, apparently being used in multiple international locations, which suggests it is an expanding activity of the group. The Trojan provides monitoring capabilities similar to the ones used by the Carbanak group.
The group uses legitimate administration tools to fly under the radar in their post-exploitation phase, which makes detection of malicious activity, as well as attribution more complicated. This kind of attack has become widespread in recent years, which is a very worrisome trend as it demonstrates that criminals are successful in their attacks. We will continue monitoring the activity for this new campaign.
The spear-phishing infection vector is still the most popular way to initiate targeted campaigns. When used with already compromised infrastructure, and combined with .chm attachments, it seems to be a really effective way of spreading, at least among financial organizations.
Recommendations
The effective way of protection from targeted attacks focused on financial organizations are preventive advanced detection capabilities such as a solution that can detect all types of anomalies and scrutinize suspicious files at a deeper level, be present on users’ systems. The Kaspersky Anti Targeted Attack solution (KATA) matches events coming from different infrastructure levels, discerns anomalies and aggregates them into incidents, while also studying related artifacts in a safe environment of a sandbox. As with most Kaspersky products, KATA is powered by HuMachine Intelligence, which is backed by on premise and in lab-running machine learning processes coupled with real-time analyst expertise and our understanding of threat intelligence big data.
The best way to prevent attackers from finding and leveraging security holes, is to eliminate the holes altogether, including those involving improper system configurations or errors in proprietary applications. For this, Kaspersky Penetration Testing and Application Security Assessment services can become a convenient and highly effective solution, providing not only data on found vulnerabilities, but also advising on how to fix it, further strengthening corporate security.
IOC’s
Kaspersky lab products detects the Silence trojan with the following verdicts:
Backdoor.Win32.Agent.dpke
Backdoor.Win32.Agent.dpiz
Trojan.Win32.Agentb.bwnk
Trojan.Win32.Agentb.bwni
Trojan-Downloader.JS.Agent.ocr
HEUR:Trojan.Win32.Generic
Full IOC’s and YARA rules delivered with private report subscription.
MD5
Dde658eb388512ee9f4f31f0f027a7df
404d69c8b74d375522b9afe90072a1f4
15e1f3ce379c620df129b572e76e273f
D2c7589d9f9ec7a01c10e79362dd400c
1b17531e00cfc7851d9d1400b9db7323
242b471bae5ef9b4de8019781e553b85
324D52A4175722A7850D8D44B559F98D
6a246fa30bc8cd092de3806ae3d7fc49
B43f65492f2f374c86998bd8ed39bfdd
cfffc5a0e5bdc87ab11b75ec8a6715a4







Backdoor
Dropper
Financial malware
Targeted attacks



Authors




GReAT





Silence – a new Trojan attacking financial organizations 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Jesse 


							Posted on							November 1, 2017. 9:24 pm 



Pretty sure the chm file cannot download/execute. It simply browses to a URL and downloads the file. It’s up to the user to actually run the file.
Reply 








Sal Rosenburg 


							Posted on							November 2, 2017. 1:03 pm 



Interesting report, thanks for sharing! May I ask what is the hash for the VBS file that is downloaded? I was not able to find this info in VT.
Reply 








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




 


A lightweight method to detect potential iOS malware 






 


Operation Triangulation: The last (hardware) mystery 






 


Windows CLFS and five exploits used by ransomware operators (Exploit #4 – CVE-2023-23376) 






 


Windows CLFS and five exploits used by ransomware operators (Exploit #3 – October 2022) 






 


Windows CLFS and five exploits used by ransomware operators (Exploit #2 – September 2022) 






 















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



























