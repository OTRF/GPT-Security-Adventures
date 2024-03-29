# Reference for threat actor for "IronHusky"

**Title**: MysterySnail attacks with Windows zero-day | Securelist

**Source**: https://securelist.com/mysterysnail-attacks-with-windows-zero-day/104509/

## Content















MysterySnail attacks with Windows zero-day | Securelist


































































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

MysterySnail attacks with Windows zero-day 

Research

12 Oct 2021

  minute read								
















Table of Contents





Executive SummaryElevation of privilege exploitMysterySnail RATIoCs 






 

Authors



 Boris Larin



 Costin Raiu





Executive Summary
In late August and early September 2021, Kaspersky technologies detected attacks with the use of an elevation of privilege exploit on multiple Microsoft Windows servers. The exploit had numerous debug strings from an older, publicly known exploit for vulnerability CVE-2016-3309, but closer analysis revealed that it was a zero-day. We discovered that it was using a previously unknown vulnerability in the Win32k driver and exploitation relies heavily on a technique to leak the base addresses of kernel modules. We promptly reported these findings to Microsoft. The information disclosure portion of the exploit chain was identified as not bypassing a security boundary, and was therefore not fixed. Microsoft assigned CVE-2021-40449 to the use-after-free vulnerability in the Win32k kernel driver and it was patched on October 12, 2021, as a part of the October Patch Tuesday.
Besides finding the zero-day in the wild, we analyzed the malware payload used along with the zero-day exploit, and found that variants of the malware were detected in widespread espionage campaigns against IT companies, military/defense contractors, and diplomatic entities.
We are calling this cluster of activity MysterySnail. Code similarity and re-use of C2 infrastructure we discovered allowed us to connect these attacks with the actor known as IronHusky and Chinese-speaking APT activity dating back to 2012.
Elevation of privilege exploit
The discovered exploit is written to support the following Windows products:

Microsoft Windows Vista
Microsoft Windows 7
Microsoft Windows 8
Microsoft Windows 8.1
Microsoft Windows Server 2008
Microsoft Windows Server 2008 R2
Microsoft Windows Server 2012
Microsoft Windows Server 2012 R2
Microsoft Windows 10 (build 14393)
Microsoft Windows Server 2016 (build 14393)
Microsoft Windows 10 (build 17763)
Microsoft Windows Server 2019 (build 17763)

The list of supported products and supported Windows 10 build numbers, explicit declaration of server OSs and the fact that exploits were only discovered in attacks on servers, all lead us to believe the exploit was developed and advertised as a solution to elevate privileges on servers.
CVE-2021-40449 is a use-after-free vulnerability in Win32k’s NtGdiResetDC function. As with many other Win32k vulnerabilities, the root cause of this vulnerability lies in the ability to set user-mode callbacks and execute unexpected API functions during execution of those callbacks. The CVE-2021-40449 is triggered when the function ResetDC is executed a second time for the same handle during execution of its own callback. The exploitation process for this vulnerability is as follows:

A user-mode call to ResetDC executes syscall NtGdiResetDC and its inner function GreResetDCInternal. This function gets a pointer to a PDC object, and then performs a call to function hdcOpenDCW.
Function hdcOpenDCW performs a user-mode callback and it can be used to execute ResetDC for the same handle a second time.
If an exploit executes ResetDC during a callback, NtGdiResetDC and GreResetDCInternal are executed again for the same DC.
If an exploit ignores all the callbacks during the second call to GreResetDCInternal, this function will be executed as intended. It will create a new DC and get rid of the old one (the PDC object is destroyed).
In the callback, after the second ResetDC call has completed, the exploit can reclaim the freed memory of the PDC object and finish the execution of the callback.
After execution of the callback, function hdcOpenDCW returns to GreResetDCInternal, but the pointer retrieved in step (1) is now a dangling pointer – it points to the memory of the previously destroyed PDC object.
In the late stage of GreResetDCInternal execution, a malformed PDC object can be used to perform a call to an arbitrary kernel function with controlled parameters.

In the discovered exploit attackers are able to achieve the desired state of memory with the use of GDI palette objects and use a single call to a kernel function to build a primitive for reading and writing kernel memory. This step is easily accomplished, because the exploit process is running with Medium IL and therefore it’s possible to use publicly known techniques to leak kernel addresses of currently loaded drivers/kernel modules. In our opinion, it would be preferable if the Medium IL processes had limited access to such functions as NtQuerySystemInformation or EnumDeviceDrivers.
MysterySnail RAT
Our deep dive into the MysterySnail RAT family started with an analysis of a previously unknown remote shell-type Trojan that was intended to be executed by an elevation of privilege exploit. The sample which we analyzed was also uploaded to VT on August 10, 2021. The sample is very big – 8.29MB. One of the reasons for the file size is that it’s statically compiled with the OpenSSL library and contains unused code and data belonging to that library. But the main reason for its size is the presence of two very large functions that do nothing but waste processor clock cycles. These functions also “use” randomly generated strings that are also present in a binary.

Random strings used by anti-analysis functions
We assume these two functions are used as an AV-evasion technique for the purpose of anti-emulation. This theory is supported by the presence of other redundant logics and the presence of a relatively large number of exported functions while the real work is performed by only one of them.

Names of exported functions; the actual business logic is executed from function “GetInfo”
The sample has two hardcoded URLs present in plain text – “www[.]disktest[.]com” and “www[.]runblerx[.]com”. They are put into class variables for intended use, but remain unused; the real C2 address is decoded by a single byte xor – “http[.]ddspadus[.]com”.
The malware enumerates the values under the “Software\Microsoft\Windows\CurrentVersion\Internet Settings\ProxyServer” registry key and uses them to request tunneling through a proxy server in case it fails to connect to the C2 directly.
The malware itself is not very sophisticated and has functionality similar to many other remote shells. But it still somehow stands out, with a relatively large number of implemented commands and extra capabilities like monitoring for inserted disk drives and the ability to act as a proxy.
Inbound and outbound commands have the same binary-based format that is provided below. All communication is encrypted with SSL.



Offset
Description


0
Size of additional data


4
Session ID


8
Command ID


0xC
Additional data



Format of communication commands
Before receiving any commands, the malware gathers and sends general information about the victim machine. This information includes:

Computer name
Current OEM code-page/default identifier
Windows product name
Local IP address
Logged-in user name
Campaign name

One interesting fact is that “Campaign name” by default is set to “windows”. This name gets overwritten, but it might indicate there are versions of the same RAT compiled for other platforms.
In total, the RAT implements 20 commands. Their description and command IDs are provided in the table below.



Command ID
Description


1F4h
Launch interactive cmd.exe shell. Before launch cmd.exe is copied to the temp folder with a different name


1F5h
Spawn new process


1F6h
Spawn new process (console)


1F7h
Get existing disk drives and their type. This function also works in the background, checking for new drives


1F8h
Create (upload) new file. If a file exists, append data to it


1FAh
Get directory list


1FBh
Kill arbitrary process


1FFh
Delete file


202h
Read file. If the file is too big, async read operation can be stopped with cmd 20Ch.


205h
Re-connect


208h
Set sleep time (in ms)


209h
Shutdown network and exit


20Ah
Exit


20Bh
Kill interactive shell (created with cmd 1F4h)


20Ch
Terminate file reading operation (started with cmd 202h)


217h
No operation


21Bh
Open proxy’ed connection to provided host. Up to 50 simultaneous connections are supported.


21Ch
Send data to proxy’ed connection


21Eh
Close all proxy connections


21Fh
Close requested proxy connection



List of commands supported by the RAT
The analysis of the MysterySnail RAT helped us discover campaigns using other variants of the analyzed malware as well as study and document the code changes made to this tool over a six-month period. We provide more info about these variants and campaigns in our private report.
With the help of Kaspersky Threat Attribution Engine (KTAE) and the discovery of early variants of MysterySnail RAT we were able to find direct code and functionality overlap with the malware attributed to the IronHusky actor. We were also able to discover the re-use of C2 addresses used in attacks by the Chinese-speaking APT as far back as 2012. This discovery links IronHusky to some of the older known activities.
Kaspersky products detect the CVE-2021-40449 exploit and related malware with the verdicts:

PDM:Exploit.Win32.Generic
PDM:Trojan.Win32.Generic
Trojan.Win64.Agent*

Kaspersky products detected these attacks with the help of the Behavioral Detection Engine and the Exploit Prevention component. CVE-2021-40449 is the latest addition to the long list of zero-days discovered in the wild with the help of our technologies. We will continue to improve defenses for our users by enhancing technologies and working with third-party vendors to patch vulnerabilities, making the internet more secure for everyone.
More information about these attacks and the actor behind them is available to customers of the Kaspersky Intelligence Reporting service. Contact: intelreports@kaspersky.com.
Kaspersky would like to thank Microsoft for their prompt analysis of the report and patches.
IoCs
www[.]disktest[.]com
www[.]runblerx[.]com
http[.]ddspadus[.]com
MD5 e2f2d2832da0facbd716d6ad298073ca
SHA1 ecdec44d3ce31532d9831b139ea04bf48cde9090
SHA256 b7fb3623e31fb36fc3d3a4d99829e42910cad4da4fa7429a2d99a838e004366e






APT
Malware Descriptions
Microsoft Windows
RAT Trojan
Targeted attacks
Vulnerabilities and exploits
Zero-day vulnerabilities



Authors



 Boris Larin



 Costin Raiu





MysterySnail attacks with Windows zero-day 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Greg 


							Posted on							October 14, 2021. 12:55 pm 



Just wanted to say thank you for the great information. I appreciate securelist and want you to know it.
Reply 



















Table of Contents





Executive SummaryElevation of privilege exploitMysterySnail RATIoCs 





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




 


Operation Triangulation: The last (hardware) mystery 






 


Windows CLFS and five exploits used by ransomware operators (Exploit #4 – CVE-2023-23376) 






 


Windows CLFS and five exploits used by ransomware operators (Exploit #3 – October 2022) 






 


Windows CLFS and five exploits used by ransomware operators (Exploit #2 – September 2022) 






 


Windows CLFS and five exploits used by ransomware operators 









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



























