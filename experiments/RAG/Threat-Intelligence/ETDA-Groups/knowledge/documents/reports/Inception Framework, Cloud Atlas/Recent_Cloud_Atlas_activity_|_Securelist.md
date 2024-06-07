# Reference for threat actor for "Inception Framework, Cloud Atlas"

**Title**: Recent Cloud Atlas activity | Securelist

**Source**: https://securelist.com/recent-cloud-atlas-activity/92016/

## Content















Recent Cloud Atlas activity | Securelist


































































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

Recent Cloud Atlas activity 

APT reports

12 Aug 2019

  minute read								








 

Authors




GReAT





Also known as Inception, Cloud Atlas is an actor that has a long history of cyber-espionage operations targeting industries and governmental entities. We first reported Cloud Atlas in 2014 and we’ve been following its activities ever since.
From the beginning of 2019 until July, we have been able to identify different spear-phishing campaigns related to this threat actor mostly focused on Russia, Central Asia and regions of Ukraine with ongoing military conflicts.
Countries targeted by Cloud Atlas recently
Cloud Atlas hasn’t changed its TTPs (Tactic Tools and Procedures) since 2018 and is still relying on its effective existing tactics and malware in order to compromise high value targets.
The Windows branch of the Cloud Atlas intrusion set still uses spear-phishing emails to target high profile victims. These emails are crafted with Office documents that use malicious remote templates – allowlisted per victims – hosted on remote servers. We described one of the techniques used by Cloud Atlas in 2017 and our colleagues at Palo Alto Networks also wrote about it in November 2018.
Previously, Cloud Atlas dropped its “validator” implant named “PowerShower” directly, after exploiting the Microsoft Equation vulnerability (CVE-2017-11882) mixed with CVE-2018-0802.  During recent  months, we have seen a new infection chain, involving a polymorphic HTA, a new and polymorphic VBS implant aimed at  executing PowerShower, and the Cloud Atlas second stage modular backdoor that we disclosed five years ago in our first blogpost about them and which remains unchanged.
Let’s meet PowerShower
PowerShower, named and previously disclosed by Palo Alto Networks in their blogspot (see above), is a malicious piece of PowerShell designed to receive PowerShell and VBS modules to execute on the local computer. This malware has been used since October 2018 by Cloud Atlas as a validator and now as a second stage. The differences in the two versions reside mostly in anti-forensics features for the validator version of PowerShower.

The PowerShower backdoor – even in its later developments – takes three commands:



Command
Description


0x80 (Ascii “P”)
It is the first byte of the magic PK. The implant will save the received content as a ZIP archive under %TEMP%\PG.zip.


0x79 (Ascii “O”)
It is the first byte of “On resume error”. The implant saves the received content as a VBS script under “%APPDATA%\Microsoft\Word\[A-Za-z]{4}.vbs” and executes it by using Wscript.exe


Default
If the first byte doesn’t match 0x80 or 0x79, the content is saved as an XML file under  “%TEMP%\temp.xml”. After that, the script loads the content of the file, parses the XML to get the PowerShell commands to execute, decodes them from Base64 and invokes IEX.
After executing the commands, the script deletes “%TEMP%\temp.xml” and sends the content of “%TEMP%\pass.txt” to the C2 via an HTTP POST request.



A few modules deployed by PowerShower have been seen in the wild, such as:

A PowerShell document stealer module which uses 7zip (present in the received PG.zip) to pack and exfiltrate *.txt, *.pdf, *.xls or *.doc documents smaller than 5MB modified during the last two days;
A reconnaissance module which retrieves a list of the active processes, the current user and the current Windows domain. Interestingly, this feature is present in PowerShower but the condition leading to the execution of that feature is never met in the recent versions of PowerShower;
A password stealer module which uses the opensource tool LaZagne to retrieve passwords from the infected system.

We haven’t yet seen a VBS module dropped by this implant, but we think that one of the VBS scripts dropped by PowerShower is a dropper of the group’s second stage backdoor documented in our article back in 2014.
And his new friend, VBShower
During its recent campaigns, Cloud Atlas used a new “polymorphic” infection chain relying no more on PowerShower directly after infection, but executing a polymorphic HTA hosted on a remote server, which is used to drop three different files on the local system.

A backdoor that we name VBShower which is polymorphic and replaces PowerShower as a validator;
A tiny launcher for VBShower ;
A file computed by the HTA which contains contextual data such as the current user, domain, computer name and a list of active processes.

This “polymorphic” infection chain allows the attacker to try to prevent IoC-based defence, as each code is unique by victim so it can’t be searched via file hash on the host.

The VBShower backdoor has the same philosophy of the validator version of PowerShower. Its aim is to complicate forensic analysis by trying to delete all the files contained in “%APPDATA%\..\Local\Temporary Internet Files\Content.Word” and “%APPDATA%\..\Local Settings\Temporary Internet Files\Content.Word\”.
Once these files have been deleted and its persistence is achieved in the registry, VBShower sends the context file computed by the HTA to the remote server and tries to get via HTTP a VBS script to execute from the remote server every hour.
At the time of writing, two VBS files have been seen pushed to the target computer by VBShower. The first one is an installer for PowerShower and the second one is an installer for the Cloud Atlas second stage modular backdoor which communicates to a cloud storage service via Webdav.
Final words
Cloud Atlas remains very prolific in Eastern Europe and Central Asia. The actor’s massive spear-phishing campaigns continue to use its simple but effective methods in order to compromise its targets.
Unlike many other intrusion sets, Cloud Atlas hasn’t chosen to use open source implants during its recent campaigns, in order to be less discriminating. More interestingly, this intrusion set hasn’t changed its modular backdoor, even five years after its discovery.
IoCs
Some emails used by the attackers

infocentre.gov@mail.ru
middleeasteye@asia.com
simbf2019@mail.ru
world_overview@politician.com
infocentre.gov@bk.ru

VBShower registry persistence

Key : HKCU\Software\Microsoft\Windows\CurrentVersion\Run\[a-f0-9A-F]{8}
Value : wscript //B “%APPDATA%\[A-Za-z]{5}.vbs”

VBShower paths

%APPDATA%\[A-Za-z]{5}.vbs.dat
%APPDATA%\[A-Za-z]{5}.vbs
%APPDATA%\[A-Za-z]{5}.mds

VBShower C2s

176.31.59.232
144.217.174.57







Backdoor
Cyber espionage
Microsoft Word
PowerShell
Spear phishing
Targeted attacks
Vulnerabilities and exploits



Authors




GReAT





Recent Cloud Atlas activity 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 





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




 


APT annual review: What the world’s threat actors got up to in 2020 






 


Cyberthreats to financial organizations in 2021 






 


Advanced Threat predictions for 2021 






 


Ghimob: a Tétrade threat actor moves to infect mobile devices 






 


APT trends report Q3 2020 









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



























