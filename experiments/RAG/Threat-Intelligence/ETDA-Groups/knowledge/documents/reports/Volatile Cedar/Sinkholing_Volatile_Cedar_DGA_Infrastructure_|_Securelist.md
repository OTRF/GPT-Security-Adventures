# Reference for threat actor for "Volatile Cedar"

**Title**: Sinkholing Volatile Cedar DGA Infrastructure | Securelist

**Source**: https://securelist.com/sinkholing-volatile-cedar-dga-infrastructure/69421/

## Content















Sinkholing Volatile Cedar DGA Infrastructure | Securelist



































































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

Sinkholing Volatile Cedar DGA Infrastructure 

APT reports

31 Mar 2015

  minute read								








 

Authors



 Kurt Baumgartner



 Costin Raiu



Victim spread contained within Lebanon


There is currently some buzz about the Volatile Cedar APT activity in the Middle East, a group that deploys not only custom built RATs, but USB propagation components, as reported by Check Point [pdf]. If you are interested in learning more about this APT, we recommend checking their paper first.
One interesting feature of the backdoors used by this group is their ability to first connect to a set of static updater command and control (C2) servers, which then redirect to other C2. When they cannot connect to their hardcoded static C2, they fall back to a DGA algorithm, and cycle through other domains to connect with.
Statistics:
This particular actor’s true impact seemed interesting, so we sinkholed some of their dynamically generated command and control infrastructure. These victim statistics present a somewhat surprising profile. Almost all of these victims are geolocated in Lebanon.
Victims checking in to DGA c2
Clearly, the bulk of the victims we observe are all communicating from ip ranges maintained by ISPs in Lebanon. And most of the other checkins appear to be research related. Almost all of the backdoors communicating with sinkholed domains are the main “explosion” backdoor. But, some of the victim systems in Lebanon communicating with our sinkhole are running the very rare “micro” backdoor written up by our colleagues from Checkpoint in their paper: “Micro is a rare Explosive version. It can best be described as a completely different version of the Trojan, with similarities to the rest of Explosive “family” (such as configuration and code base). We believe that Micro is actually an old ancestor of Explosive, from which all other versions were developed. As in other versions, this version is also dependent on a self-developed DLL named “wnhelp.dll.” They check in to edortntexplore[.]info with the URI “/micro/data/index.php?micro=4” over port 443.

While Volatile Cedar certainly does not have a high level of technological prowess, it appears that they have been effective at spreading their malware, much like the Madi APT we reported on mid-2012. Because the group is not known for spearphishing, IT administrators should be aware of their own publicly exposed attack surface like web applications, ftp servers, ssh servers, etc, and ensure they are not vulnerable to SQLi, SSI attacks, and other server side offensive activity.
Kaspersky Verdicts and MD5s:
Trojan.Win32.Explosion.a
981234d969a4c5e6edea50df009efedd
Trojan.Win32.Explosion.b
7031426fb851e93965a72902842b7c2c
Trojan.Win32.Explosion.c
6f11a67803e1299a22c77c8e24072b82
Trojan.Win32.Explosion.d
eb7042ad32f41c0e577b5b504c7558ea
Trojan.Win32.Explosion.e
61b11b9e6baae4f764722a808119ed0c
Trojan.Win32.Explosion.f
c7ac6193245b76cc8cebc2835ee13532
184320a057e455555e3be22e67663722
Trojan.Win32.Explosion.g
5d437eb2a22ec8f37139788f2087d45d
Trojan.Win32.Explosion.i
7dbc46559efafe8ec8446b836129598c
Trojan.Win32.Explosion.j
c898aed0ab4173cc3ac7d4849d06e7fa
Trojan.Win32.Explosion.k
9a5a99def615966ea05e3067057d6b37
Trojan.Win32.Explosion.l
1dcac3178a1b85d5179ce75eace04d10
Trojan.Win32.Explosion.m
22872f40f5aad3354bbf641fe90f2fd6
Trojan.Win32.Explosion.n
2b9106e8df3aa98c3654a4e0733d83e7
Trojan.Win32.Explosion.o
08c988d6cebdd55f3b123f2d9d5507a6
Trojan.Win32.Explosion.p
1d4b0fc476b7d20f1ef590bcaa78dc5d
Trojan.Win32.Explosion.q
c9a4317f1002fefcc7a250c3d76d4b01
Trojan.Win32.Explosion.r
4f8b989bc424a39649805b5b93318295
Trojan.Win32.Explosion.s
3f35c97e9e87472030b84ae1bc932ffc
Trojan.Win32.Explosion.t
7cd87c4976f1b34a0b060a23faddbd19
Trojan.Win32.Explosion.u
ea53e618432ca0c823fafc06dc60b726
Trojan.Win32.Explosion.v
034e4c62965f8d5dd5d5a2ce34a53ba9
Trojan.Win32.Explosion.w
5ca3ac2949022e5c77335f7e228db1d8
Trojan.Win32.Explosion.x
ab3d0c748ced69557f78b7071879e50a
Trojan.Win32.Explosion.y
5b505d0286378efcca4df38ed4a26c90
Trojan.Win32.Explosion.z
e6f874b7629b11a2f5ed3cc2c123f8b6
Trojan.Win32.Explosion.aa
306d243745ba53d09353b3b722d471b8
Trojan.Win32.Explosion.ab
740c47c663f5205365ae9fb08adfb127
Trojan.Win32.Explosion.ac
c19e91a91a2fa55e869c42a70da9a506
Trojan.Win32.Explosion.ad
edaca6fb1896a120237b2ce13f6bc3e6
Trojan.Win32.Explosion.ae
d2074d6273f41c34e8ba370aa9af46ad
Trojan.Win32.Explosion.af
66e2adf710261e925db588b5fac98ad8
29eca6286a01c0b684f7d5f0bfe0c0e6
2783cee3aac144175fef308fc768ea63
f58f03121eed899290ed70f4d19af307
Trojan.Win32.Agent.adsct
826b772c81f41505f96fc18e666b1acd
Trojan-Dropper.Win32.Dycler.vhp
44b5a3af895f31e22f6bc4eb66bd3eb7
??
96b1221ba725f1aaeaaa63f63cf04092
 
References:

Volatile Cedar – Analysis of a Global Cyber Espionage Campaign (Checkpoint)







APT
Cyber espionage
Malware Statistics
Targeted attacks



Authors



 Kurt Baumgartner



 Costin Raiu





Sinkholing Volatile Cedar DGA Infrastructure 
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




 


PuzzleMaker attacks with Chrome zero-day exploit chain 






 


Looking at Big Threats Using Code Similarity. Part 1 






 


Verizon’s 2020 DBIR 






 


YARA webinar follow up 






 


Hunting APTs with YARA 









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



























