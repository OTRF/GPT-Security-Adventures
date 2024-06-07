# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: Cryptocurrency businesses still being targeted by Lazarus | Securelist

**Source**: https://securelist.com/cryptocurrency-businesses-still-being-targeted-by-lazarus/90019/

## Content















Cryptocurrency businesses still being targeted by Lazarus | Securelist




































































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

Cryptocurrency businesses still being targeted by Lazarus 

APT reports

26 Mar 2019

  minute read								








 

Authors




GReAT





It’s hardly news to anyone who follows cyberthreat intelligence that the Lazarus APT group targets financial entities, especially cryptocurrency exchanges. Financial gain remains one of the main goals for Lazarus, with its tactics, techniques, and procedures constantly evolving to avoid detection.
In the middle of 2018, we published our Operation Applejeus research, which highlighted Lazarus’s focus on cryptocurrency exchanges utilizing a fake company with a backdoored product aimed at cryptocurrency businesses. One of the key findings was the group’s new ability to target macOS. Since then Lazarus has been busy expanding its operations for the platform.
Further tracking of their activities targeting the financial sector enabled us to discover a new operation, active since at least November 2018, which utilizes PowerShell to control Windows systems and macOS malware for Apple users.

Infection procedure
Lazarus is a well-organized group, something that can be seen from their malware population: not only have we seen them build redundancy to reserve some malware in case of in-operation hot spare replacement of ‘burnt’ (detected) samples but they also conform to specific internal standards and protocols when developing backdoors. This case is no different. They have developed custom PowerShell scripts that communicate with malicious C2 servers and execute commands from the operator. The C2 server script names are disguised as WordPress (popular blog engine) files as well as those of other popular open source projects. After establishing the malware control session with the server, the functionality provided by the malware includes:

Set sleep time (delay between C2 interactions)
Exit malware
Collect basic host information
Check malware status
Show current malware configuration
Update malware configuration
Execute system shell command
Download & Upload files

Lazarus uses different tactics to run its C2 servers: from purchasing servers to using hacked ones. We have seen some legitimate-looking servers that are most likely compromised and used in malicious campaigns. According to server response headers, they are most likely running an old vulnerable instance of Internet Information Services (IIS) 6.0 on Microsoft Windows Server 2003. Another C2 server was probably purchased by Lazarus from a hosting company and used to host macOS and Windows payloads. The geography of the servers varies, from China to the European Union. But why use two different types of servers? The group seems to have a rule (at least in this campaign) to only host malware on rented servers, while hosting C2 scripts for malware communication on compromised servers.

Infrastructure segregation by purpose
The malware was distributed via documents carefully prepared to attract the attention of cryptocurrency professionals. Seeing as how some of the documents were prepared in Korean, we believe that South Korean businesses are a high priority for Lazarus. One document entitled ‘Sample document for business plan evaluation of venture company’ (translated from Korean) looks like this:

Content of weaponized document from Lazarus (4cbd45fe6d65f513447beb4509a9ae3d)
Another macro-weaponized document (e9a6a945803722be1556fd120ee81199) contains a business overview of what seems to be a Chinese technology consulting group named LAFIZ. We couldn’t confirm if it’s a legitimate business or another fake company made up by Lazarus. Their website lafiz[.]link has been parked since 2017.

Contents of another weaponized document (e9a6a945803722be1556fd120ee81199)
Based on our telemetry, we found a cryptocurrency exchange company attacked with a malicious document containing the same macro. The document’s content provided information for coin listings with a translation in Korean:

Content of another weaponized document (6a0f3abd05bc75edbfb862739865a4cc)
The payloads show that Lazarus keeps exploring more ways to evade detection to stay under the radar longer. The group builds malware for 32-bit and 64-bit Windows separately to support both platforms and have more variety in terms of compiled code. The Windows payloads distributed from the server (nzssdm[.]com) hosting the Mac malware have a CheckSelf export function, and one of them (668d5b5761755c9d061da74cb21a8b75) has the internal name ‘battle64.dll’. From that point we managed to find additional Windows malware samples containing the CheckSelf export function and an internal name containing the word ‘battle’.
These Windows malware samples were delivered using malicious HWP (Korean Hangul Word Processor format) documents exploiting a known PostScript vulnerability. It should be noted that HWP documents are only popular among Korean users (Hangul Word Processor was developed in South Korea) and we have witnessed several attacks using the same method.

Connection with previous HWP attacks
It’s no secret that Apple products are now very popular among successful internet startups and fintech companies, and this is why the malicious actor built and used macOS malware. While investigating earlier Lazarus incidents, we anticipated this actor would eventually expand its attacks to macOS.
It appears that Lazarus is using the same developers to expand to other platforms, because some of the features have remained consistent as its malware evolves.

Overlap of current campaign and previous hwp-based attack cases
We’d therefore like to ask Windows and macOS users to be more cautious and not fall victim to Lazarus. If you’re part of the booming cryptocurrency or technological startup industry, exercise extra caution when dealing with new third parties or installing software on your systems. It’s best to check new software with an antivirus or at least use popular free virus-scanning services such as VirusTotal. And never ‘Enable Content’ (macro scripting) in Microsoft Office documents received from new or untrusted sources. Avoid being infected by fake or backdoored software from Lazarus – if you need to try out new applications, it’s better do so offline or on an isolated network virtual machine which you can erase with a few clicks. We’ll continue posting on Lazarus’s latest tactics and tricks in our blog. In the meantime, stay safe!
For more details on this and other research, please contact intelreports@kaspersky.com.
File Hashes:
Malicious office document used in real attack
4cbd45fe6d65f513447beb4509a9ae3d 샘플_기술사업계획서(벤처기업평가용).doc
6a0f3abd05bc75edbfb862739865a4cc 문의_Evaluation Table.xls
Testing office document
29a37c6d9fae5664946c6607f351a8dc list.doc
e9a6a945803722be1556fd120ee81199 list.doc
a18bc8bc82bca8245838274907e64631 list.doc
macOS malware
4345798b2a09fc782901e176bd0c69b6
PowerShell script
cb713385655e9af0a2fc10da5c0256f5 test.ps1
e6d5363091e63e35490ad2d76b72e851 test.ps1 – It does not contain URLs.
Da4981df65cc8b5263594bb71a0720a1
Windows executable payload
171b9135540f89bf727b690b9e587a4e wwtm.dat
668d5b5761755c9d061da74cb21a8b75 wwtm.dat
ad3f966d48f18b5e7b23a579a926c7e8
Manuscrypt payload
35e38d023b253c0cd9bd3e16afc362a7
72fe869aa394ef0a62bb8324857770dd
86d3c1b354ce696e454c42d8dc6df1b7
5182e7a2037717f2f9bbf6ba298c48fb
Malicious hwp file
F392492ef5ea1b399b4c0af38810b0d6 일일동향보고_180913.hwp
0316f6067bc02c23c1975d83c659da21 국가핵심인력등록관리제등검토요청(10.16)(김경환변호사).hwp
Domains and IPs
Compromised first stage C2 server
http://bluecreekrobotics[.]com/wp-includes/common.php
http://dev.microcravate[.]com/wp-includes/common.php
http://dev.whatsyourcrunch[.]com/wp-includes/common.php
http://enterpriseheroes.com[.]ng/wp-includes/common.php
http://hrgp.asselsolutions[.]com/wp-includes/common.php
https://baseballcharlemagnelegardeur[.]com/wp-content/languages/common.php
https://bogorcenter[.]com/wp-content/themes/index2.php
https://eventum.cwsdev3.bi[.]com/wp-includes/common.php
https://streamf[.]ru/wp-content/index2.php
https://towingoperations[.]com/chat/chat.php
https://vinhsake[.]com//wp-content/uploads/index2.php
https://www.tangowithcolette[.]com/pages/common.php
Second stage C2 server
http://115.28.160[.]20:443 – Compromised server
Malware hosting server
http://nzssdm[.]com/assets/wwtm.dat – Windows payload distribution URL
http://nzssdm[.]com/assets/mt.dat – Mac payload distribution URL






Apple MacOS
Cryptocurrencies
Lazarus
Malware Descriptions
PowerShell
Spear phishing
Targeted attacks



Authors




GReAT





Cryptocurrency businesses still being targeted by Lazarus 
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



























