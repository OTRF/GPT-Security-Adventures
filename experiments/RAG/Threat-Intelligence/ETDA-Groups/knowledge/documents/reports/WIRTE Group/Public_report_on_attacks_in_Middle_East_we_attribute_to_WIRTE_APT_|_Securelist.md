# Reference for threat actor for "WIRTE Group"

**Title**: Public report on attacks in Middle East we attribute to WIRTE APT | Securelist

**Source**: https://securelist.com/wirtes-campaign-in-the-middle-east-living-off-the-land-since-at-least-2019/105044/

## Content















Public report on attacks in Middle East we attribute to WIRTE APT | Securelist


































































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

WIRTE’s campaign in the Middle East ‘living off the land’ since at least 2019 

APT reports

29 Nov 2021

  minute read								
















Table of Contents





OverviewGaining an initial footholdExploitation, installation and persistenceFerocious dropperLitePower stagerCommand and controlVictimologyThreat actor assessmentConclusion and outlookIndicators of compromiseMalicious documents and droppersClass IDs in registryFile pathPDB pathsDomains and IPs 






 

Authors



 Maher Yamout





Overview
This February, during our hunting efforts for threat actors using VBS/VBA implants, we came across MS Excel droppers that use hidden spreadsheets and VBA macros to drop their first stage implant. The implant itself is a VBS script with functionality to collect system information and execute arbitrary code sent by the attackers on the infected machine.
Although these intrusion sets may appear similar to the new MuddyWater first stage VBS implant used for reconnaissance and profiling activities, which we described recently in a private report, they have slightly different TTPs and wider targeting. To date, most of the known victims are located in the Middle East, but there are also targets in other regions. Various industries are affected by this campaign. The main focus is on government and diplomatic entities, though we also noticed an unusual targeting of law firms and financial institutions.
We attribute this campaign with high confidence to an actor named WIRTE, which is a lesser-known threat actor first publicly referenced by our colleagues at Lab52 in 2019. We further suspect, with low confidence, that the WIRTE group has relations with the Gaza Cybergang threat actor.
More information about WIRTE is available to customers of Kaspersky Intelligence Reporting. Contact: intelreports@kaspersky.com”
Gaining an initial foothold
In the instances we have observed, the threat actor sent spear-phishing emails, luring the victims to open a malicious Microsoft Excel/Word document. The Excel droppers observed in all instances were using Excel 4.0 macros – a technique that uses formulas in hidden spreadsheets or cells that execute macro 4.0 commands – to drop malware that in our particular case was named Ferocious dropper. The Word droppers were using standard VBA macros to download the payload. The actor tailored the decoy contents to the targeted victims, using logos and themes relevant to the targeted company or using trending topics from their region and, in one instance, even mimicking the Palestinian authority.
However, in some cases we saw a fake ‘Kaspersky Update Agent’ executable acting as a dropper for the VBS implant. We were unable to confirm if this PE file was also distributed through email or downloaded by the threat actor after some initial penetration, but our analysis shows it has the same execution flow as the Excel 4.0 macros.









Sample VBS dropper Excel and Word documents, and executable
Exploitation, installation and persistence
Ferocious dropper
This first stage implant is composed of VBS and PowerShell scripts. The actor used some interesting new techniques in the dropper’s execution flow. Below, we break it down into three parts:


Ferocious dropper: The Excel dropper, after the user opens it and disables the protected mode, will execute a series of formulas placed in a hidden column. Initially, they will hide the main spreadsheet that requested the user to “enable editing”, then unhide a secondary spreadsheet that contains the decoy, to avoid raising suspicion. The dropper will then run formulas from a third spreadsheet with hidden columns. The infection process will start by running three basic anti-sandbox checks using the Excel 4.0 function “GET.WORKSPACE”, with three integers:


1: Get the name of the environment in which Microsoft Excel is running, as text, followed by the environment’s version number. The result will then be compared to a predefined Windows version in a hidden cell, for example: Windows (64-bit) NT :.00, Windows (64-bit) NT 6.01, Windows (32-bit) NT 10.00, Windows (32-bit) NT 6.02.


19: Check if a mouse is present.


42: Check if the host computer is capable of playing sounds.
If any of the above checks fail, or if the Windows environment matches any of the aforementioned versions predefined in the document (different documents have different predefined versions), the process will halt. Otherwise, the macro will open a temporary %ProgramData%\winrm.txt file and save a VBS stager to %ProgramData%\winrm.vbs and set up registry keys for persistence.




Ferocious run-1: After the macro finishes writing to disk, it runs winrm.vbs using explorer.exe. In turn, the VBS script will write an embedded PowerShell snippet to a predefined filename that varies between samples, for instance, %ProgramData%\regionh.txt. The VBS script will also add two important registry keys for persistence.
The persistence technique observed in all intrusions uses COM hijacking. In this technique, the threat actor is able to add a Class ID in the current user registry hive (HKCU) referencing the malicious VBS script written previously to %ProgramData%\winrm.vbs. This registry modification will effectively invoke the malicious VBS script any time a program or script references “Scripting.Dictionary” COM programs during their execution.
In our analysis and testing, the WinRM Scripting API that is called by the legitimate Windows VBS scripts “C:\Windows\System32\winrm.vbs” or “C:\Windows\SysWOW64\winrm.vbs”, are able to trigger the persistence mechanism smoothly. Microsoft’s command line licensing tool slmgr.vbs is also able to provide similar results. Both winrm.vbs and slmgr.vbs were leveraged across different intrusions. The mechanism through which these scripts are invoked during the boot process is described in a later section.

Registry keys used for COM hijacking
After the above execution chain, the Excel 4.0 macro will clean up and delete the winrm.vbs and winrm.txt files.

Ferocious run-2: The macro will continue after the cleanup by recreating and opening the same files, winrm.vbs and winrm.txt. However, this time it writes a PowerShell one-liner wrapped with VB code temporarily into %ProgramData%\winrm.txt and then saved into %ProgramData%\winrm.vbs. This one-liner acts as a stager for the PowerShell snippet written in regionh.txt mentioned above. Once successful, the macro invokes %ProgramData%\winrm.vbs again using explorer.exe, which in turn will execute the PowerShell snippet that connects to the C2 server and which we named LitePower Stager.

LitePower stager
The implant is a small PowerShell script that acts as a downloader and secondary stager used to execute commands provided by its C2, and possibly download and deploy further malware.

LitePower PowerShell implant
This script is able to connect with the embedded C2 domain using predefined HTTP settings such as a unique User-Agent:





Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:FTS_06) Gecko/22.36.35.06 Firefox/2.0




1

Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:FTS_06) Gecko/22.36.35.06 Firefox/2.0




Interestingly, and across the different incidents we observed, the “rv” field of the user agent has changed. In the example above, it is FTS_06. However, we have seen more than 10 variations. We suspect these are used to track intrusions.
If the connection to the C2 server is successful, the script parses the output and invokes it using IEX. The script sleeps for a random number of seconds between 60 and 100 after each attempt to reach the C2. If the threat actor succeeds in establishing C2 communications using LitePower, further payloads containing system commands are sent back to the victim in the form of PowerShell functions through HTTP GET requests, and the command results are sent back as HTTP POST requests to the C2 server. The GET requests will be parsed by LitePower and invoked using PowerShell’s IEX function.
The threat actor initially conducts system reconnaissance to assess the AV software installed and the user privilege. This is followed by the creation of a legitimate scheduled task to trigger “Scripting.Dictionary” COM programs; this will become the cornerstone that allows the persistence to work using the COM hijacking technique and the registry keys added during the installation phase described above.

Sample scheduled task settings referencing SLMGR.VBS to trigger WINRM.VBS through COM hijacking
The commands observed during the different intrusions are summarized below:



Command
Description


Get-WmiObject Win32_logicaldisk -Filter ‘DeviceID=”C:”’ |
select volumeserialnumber
List local disk drives


‘SELECT * FROM AntiVirusProduct’
$antivirusProduct = Get-WmiObject -Namespace
‘root\SecurityCenter2’ -Query $wmiQuery
if($antivirusProduct.displayName -eq ”){$ret= ‘N/A’}
else{$ret= $antivirusProduct.displayName}
Get list of antivirus software installed


New-Object Security.Principal.WindowsPrincipal([Security.Principal.WindowsId
entity]::GetCurrent())).IsInRole([Security.Principal.WindowsBuilt
inRole]::Administrator
Check if current user has admin privileges


Get-WmiObject win32_operatingsystem).caption) + ‘ x’+ ((Get-
WmiObject Win32_OperatingSystem).OSArchitecture).substring(0,2)
Get operating system architecture



Additional long functions that we observed can be summarized as follows:

Function Get-ServiceStatus: checks for possible backdoors installed as services (MsDataSvc and NgcCtrlSvc), if the computer is part of a domain, and if the current user is a member of “Domain admins”.
Function Get-PersistenceStatus: checks for the registry keys added for COM hijacking.
Function Get-HotFixes: lists all hotfixes installed.
Screenshot: takes system screenshots and saves them to %AppData% before sending them to the C2 via a POST request.

Command and control
In our initial sample analysis, the C2 domain we observed was stgeorgebankers[.]com. After conducting pivots through malware samples, we were able to identify multiple C2 domains that date back to at least December 2019. These C2 domains were occasionally behind CloudFlare to obscure the real C2 IP address. Thanks to collaboration with our partners, we were able to gather some of the original C2 IP addresses, which allowed us to discover that the servers are hosted in Ukraine and Estonia.

Infrastructure overview
By looking for more machines presenting identical TLS certificates, we were able to identify additional domain names and IP addresses. Interestingly, the server mapped to kneeexercises[.]net listens for incoming HTTPS connections on several ports and uses common names seen on other C2 domains. For example, ports 2083 and 8443 had CN firstohiobank[.]com, and TCP port 2087 had a TLS certificate with the common name dentalmatrix[.]net. We observed use of these non-standard ports during some of the older intrusions, while the newer ones mostly use port 443.
Victimology
Our telemetry indicates that the threat actor has targeted a variety of verticals including diplomatic and financial institutions, government, law firms, military organizations, and technology companies. The affected entities are located in Armenia, Cyprus, Egypt, Jordan, Lebanon, Palestine, Syria and Turkey.
Threat actor assessment
We assess with high confidence that the intrusions discussed here are associated with the WIRTE threat actor group.
WIRTE used documents deploying Visual Basic Script (VBS), potentially delivered through spear phishing, decoys with Arabic content, occasionally associated with Palestinian matters.
We see the same theme being followed in the intrusions discussed in this report. Both old and new intrusions leveraged VBS and PowerShell in similar ways to stage additional tools and communicate with the C2.
Even though the latest intrusions are using TCP/443 over HTTPS in C2 communications, the oldest intrusions explored in this report used similar ports to those mentioned in the public post by Lab52, such as TCP 2096 and 2087. In addition, the C2 requests explored here and in the public post have similar PowerShell IEX command execution and sleep functions.

Old C2 request highlighting the status condition, IEX invocation and 60-100 sleep function 

New C2 request highlighting the status condition, IEX invocation and 60-100 sleep function
The snippets above also show the custom user-agents. Although the old intrusions had them encoded, the intrusions explored in this report had them in plain text. In both cases the adversaries identified separate intrusions by changing the “rv” field.
The C2s in both cases were protected by Cloudflare, and the real VPSs were under ASNs primarily in Ukraine (e.g., ASN 201094).
In the Lab52 post, the author described the use of a defense evasion and living-off-the-land (LotL) technique using regsvr32.exe, whereas in the intrusions explored in this report, the threat actor used another LotL technique such as COM hijacking. In both cases, the working directory is %ProgramData%.
All in all, we believe that all these similarities are a strong indication that the attacks described in this report were conducted by the WIRTE threat actor.
We assess with low confidence that WIRTE is a subgroup under the Gaza Cybergang umbrella. Although the three subgroups we are tracking use entirely different TTPs, they all occasionally use decoys associated with Palestinian matters, which we haven’t seen commonly used by other threat actors, especially those operating in the Middle East region such as MuddyWater and Oilrig.
Conclusion and outlook
WIRTE operators use simple and rather common TTPs that have allowed them to remain undetected for a long period of time. If our assessment of associating WIRTE with Gaza Cybergang proves to be correct in the future, it may signal a change in the group’s motivation. Gaza Cybergang is politically motivated and therefore primarily targets governmental and political entities; it is unusual for such groups to target law firms and financial institutions. Despite the targeting of these latter spheres, the majority of victims still fall within the government and diplomatic categories.
WIRTE modified their toolset and how they operate to remain stealthy for a longer period of time. Living-off-the-land (LotL) techniques are an interesting new addition to their TTPs. This suspected subgroup of Gaza Cybergang used simple yet effective methods to compromise its victims with better OpSec than its suspected counterparts. Using interpreted language malware such as VBS and PowerShell scripts, unlike the other Gaza Cybergang subgroups, adds flexibility to update their toolset and avoid static detection controls.
Whether WIRTE is a new subgroup or an evolution of existing Gaza Cybergang subgroups, we see them expanding their presence further in cyberspace by using updated and stealthier TTPs. In the near future we expect them to continue compromising their victims using the TTPs discussed in this report.
Indicators of compromise
Malicious documents and droppers



ecaaab9e2fc089eefb6accae9750ac60
xls.اللائحة الجنیسیة


a7802c9a4046edbcbe3f5a503de61867
doc.1803202155-تعمیم رقم


3a7425539f8853e7b89624890a5de25b
saint george bankers & trust business offer.docx


5AE4505A5CA7235C842680C557D05383
slmgr.vbs


B2F8CCE7B03E7AA70DAB4A5D377375B5
exhaustedq.txt


8ade05c4b4e98cc89fa09bd513ea1a99
kaspersky update agent.exe



Class IDs in registry
HKCU:\Software\Classes\CLSID\{50236F14-2C02-4291-93AB-B5A80F9666B0}\LocalServer32
HKCU:\Software\Classes\CLSID\{14C34482-E07F-44CF-B261-385B616C54EC}\LocalServer32
File path
%AppData%\Temp\9127.tmp\9128.tmp\
%ProgramData%\
PDB paths
K:\Hacking\NgcCtrlSvc\NgcCtrlSvc\obj\Release\NgcCtrlSvc.pdb
K:\Hacking\Tools\MsDataSvc-v3\MsDataSvc\obj\Release\MsDataSvc.pdb
Domains and IPs
nutrition-information[.]org
Stgeorgebankers[.]com
Firstohiobank[.]com
allaccounting[.]ca
est-clinic[.]com
unitedfamilyhealth[.]net
pocket-property[.]com
kneeexercises[.]net
doctoressolis[.]com
omegaeyehospital[.]com
Healthyhabitsusa[.]com
niftybuysellchart[.]com
Dentalmatrix[.]net
91.211.89[.]33
91.203.6[.]27
45.129.96[.]174
45.129.97[.]207






APT
Cybercrime
Macros
Malicious spam
Microsoft Excel
Microsoft Word
Spear phishing
Targeted attacks



Authors



 Maher Yamout





WIRTE’s campaign in the Middle East ‘living off the land’ since at least 2019 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





OverviewGaining an initial footholdExploitation, installation and persistenceFerocious dropperLitePower stagerCommand and controlVictimologyThreat actor assessmentConclusion and outlookIndicators of compromiseMalicious documents and droppersClass IDs in registryFile pathPDB pathsDomains and IPs 





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




 


A lightweight method to detect potential iOS malware 









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



























