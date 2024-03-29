# Reference for threat actor for "Operation Parliament"

**Title**: Operation Parliament, who is doing what? | Securelist

**Source**: https://securelist.com/operation-parliament-who-is-doing-what/85237/

## Content















Operation Parliament, who is doing what? | Securelist


































































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

Operation Parliament, who is doing what? 

APT reports

12 Apr 2018

  minute read								








 

Authors




GReAT





Summary
Kaspersky Lab has been tracking a series of attacks utilizing unknown malware since early 2017. The attacks appear to be geopolitically motivated and target high profile organizations. The objective of the attacks is clearly espionage – they involve gaining access to top legislative, executive and judicial bodies around the world.

The attackers have targeted a large number of organizations globally since early 2017, with the main focus on the Middle East and North Africa (MENA), especially Palestine. High-profile organizations have also been targeted in other regions. The number of attacks has decreased since the beginning of 2018.
The attacks were initially discovered while investigating a phishing attack that targeted political figures in the MENA region. At first the attacks looked to be the work of the low-sophistication Gaza Cybergang (decoys, file names), but further analysis painted a very different picture.
Targets include high-profile entities such as parliaments, senates, top state offices and officials, political science scholars, military and intelligence agencies, ministries, media outlets, research centers, election commissions, Olympic organizations, large trading companies, and other unknown entities.
The malware basically provides a remote CMD/PowerShell terminal for the attackers, enabling them to execute any scripts/commands and receive the result via HTTP requests.
Kaspersky Lab users and Threat Management and Defense clients are protected from the attacks.

Cisco Talos recently published a blogpost describing targeted attacks in the Middle East region which we believe may be connected.
Victimology and Statistics
Based on our findings, we believe the attackers represent a previously unknown geopolitically motivated threat actor. The campaign started in 2017, with the attackers doing just enough to achieve their goals. They most likely have access to additional tools when needed and appear to have access to an elaborate database of contacts in sensitive organizations and personnel worldwide, especially of vulnerable and non-trained staff. The victim systems range from personal desktop or laptop systems to large servers with domain controller roles or similar. The nature of the targeted ministries varied, including those responsible for telecommunications, health, energy, justice, finance and so on.
Victims have been spotted in the Palestinian Territories, Egypt, Jordan, the UAE, Saudi Arabia, Djibouti, Qatar, Lebanon, Chile, Somalia, Iraq, Morocco, Syria, India, Iran, Canada, the USA, the UK, Germany, Israel, Afghanistan, Serbia, Russia, Oman, Kuwait, South Korea and Denmark.



Victim organization type
Number of victim organizations


Unknown
91


Senates/Parliaments
7


Prime Ministerial Offices
3


Military/Intelligence Agencies
5


Other Gov./Ministerial/Diplomatic Offices
20


Financial/Banking Institutions
5


Media Outlets
2


Olympic/Sports Bodies
2


Research Centers/Scholars
2


Election Commissions
1


Distribution/Logistics
1




The number of victims/victim organizations probably doesn’t represent the full scope of the attacks – only a portion.
Attack description and attribution
Operation Parliament appears to be another symptom of escalating tensions in the Middle East region. The attackers have taken great care to stay under the radar, imitating another attack group in the region. They have been particularly careful to verify victim devices before proceeding with the infection, safeguarding their command and control servers. The targeting seems to have slowed down since the beginning of 2018, probably winding down when the desired data or access was obtained. The targeting of specific victims is unlike previously seen behavior in regional campaigns by Gaza Cybergang or Desert Falcons and points to an elaborate information-gathering exercise that was carried out before the attacks (physical and/or digital).
With deception and false flags increasingly being employed by threat actors, attribution is a hard and complicated task that requires solid evidence, especially in complex regions such as the Middle East.
See the following for more information and examples of false flags being used in cyberattacks:
Wave your false flags! …or the Nightmares and Nuances of a Self-Aware Attribution Space
OlympicDestroyer is here to trick the industry
Malware description
The malware was first seen packed with VMProtect; when unpacked the sample didn’t show any similarities with previously known malware. All the strings and settings were encrypted and obfuscated. Functionality was identified that enables HTTP communication with the C&C server and invokes “processcreate” based on parameters received as a response.
The configuration and strings are encrypted using 3DES and Base64 encoding. Data sent to the C&C server is also encrypted using 3DES and Base64. Different keys are used for local and network encryption.
The malware starts communicating with the C&C server by sending basic information about the infected machine. The C&C server then replies with the encrypted serialized configuration.
The malware basically provides a remote CMD/PowerShell terminal for the attackers, enabling them to execute scripts/commands and receive the results via HTTP requests.
Sample of the C&C response with encrypted commands and configurations
Examples of attack decoys
Translation: Contacts list of media personnel
Translation: Relations between UAE and Jordan, and the impact caused by the non-boycott of Qatar
Translation: Military retirement statement 2017 June
Translation: The new Hamas structure for Gaza strip 2017
Translation: Clarification report (on Gaza employee salaries)
What should high-profile organizations do?
High-profile organizations should have elevated levels of cybersecurity. Attacks against them are inevitable and are unlikely to ever cease. These organizations need to pay particular attention to their security, implementing additional measures to ensure they are well protected. Anti-targeted attack solutions, threat intelligence capabilities and data flows, default-deny application lockdown, endpoint detection and response, data leak and insider threat prevention, and even isolated/air-gapped networks should form the basis of any strategy for protecting organizations in the current threat landscape.
The victims of Operation Parliament need to re-evaluate their approach to cybersecurity.
Additional information
For more information about the attacks and the indicators of compromise, please contact: intelreports@kaspersky.com
Alternatively, please visit: https://www.kaspersky.com/enterprise-security/apt-intelligence-reporting
To find more information about cybersecurity awareness training for enterprise or government staff, go to Kaspersky Security Awareness.







APT
Cyber espionage
Malware Descriptions
Malware Statistics
Targeted attacks



Authors




GReAT





Operation Parliament, who is doing what? 
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



























