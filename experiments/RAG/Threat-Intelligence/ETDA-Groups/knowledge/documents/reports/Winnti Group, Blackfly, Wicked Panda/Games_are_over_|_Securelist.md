# Reference for threat actor for "Winnti Group, Blackfly, Wicked Panda"

**Title**: Games are over | Securelist

**Source**: https://securelist.com/games-are-over/70991/

## Content















Games are over | Securelist




































































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

Games are over: Winnti is now targeting pharmaceutical companies 

APT reports

22 Jun 2015

  minute read								








 

Authors



 Dmitry Tarakanov





For a long time the Winnti group had been considered as a Chinese threat actor targeting gaming companies specifically. Recently, we’ve seen information indicating that the scope of targets can be wider and is no longer limited to the entertainment business. We actually track samples of Winnti malware all the time, but so far we haven’t been able to catch one with solid clues indicating other targeted industries. Also our visibility as a vendor does not cover every company in the world (at least so far ;)) and the Kaspersky Security Network (KSN) did not reveal other attacks except those against gaming companies. Well, sometimes targeted entities have included telecommunication companies, or better, large holdings, but it seems that at least one of their businesses was in some way related to the production or distribution of computer games.
In April Novetta released its excellent report on the Winnti malware spotted in the operations of Axiom group. The Axiom group has been presented as an advanced Chinese threat actor carrying out cyber-espionage attacks against a whole range of different industries. For us, the Novetta report was another source of intelligence that Winnti was already expanding beyond online games. One of the recent Winnti samples we found appears to confirm this as well.
The new sample belongs to one of the Winnti versions described in Novetta’s report – Winnti 3.0. This is one of the Dynamic Link Libraries composing this RAT (Remote Access Trojan) platform – the worker library (which in essence is the RAT DLL) with the internal name w64.dll and the exported functions work_end and work_start. Since, as usual, this component is stored on the disk with the strings and much of other data in the PE header removed/zeroed, it is impossible to restore the compilation date of this DLL. But this library includes two drivers compiled on August 22 and September 4, 2014. The sample has an encrypted configuration block placed in overlay. This block may include a tag for the sample – usually it is a campaign ID or victim ID/name. This time the operators put such tag in the configuration and it turned out to be the name of the well-known global pharmaceutical company headquartered in Europe:
Pic.1 Configuration block
Besides the sample tag, the configuration block includes the names of other files involved in the working of the RAT platform and the service name (Adobe Service), after which malware is installed. The presence of the following files could indicate that the system has been compromised:
C:\Windows\TEMP\tmpCCD.tmp
ServiceAdobe.dll
ksadobe.dat
One of the mentioned drivers (a known, malicious Winnti network rootkit) was signed with a stolen certificate of a division of a huge Japanese conglomerate. Although this division is involved in microelectronics manufacturing, other business directions of the conglomerate include development and production of drugs as well as medical equipment.
Although the nature of the involvement of Winnti operators, who were earlier perceived to be a threat only to the online gaming industry, in the activities of other cyber-espionage teams still remains rather obscure, the evidence is there. From now on, when you see Winnti mentioned, don’t think just about gaming companies; consider also at least targeted telecoms and big pharma companies.
Here are the samples in question:
8e61219b18d36748ce956099277cc29b – Backdoor.Win64.Winnti.gy
5979cf5018c03be2524b87b7dda64a1a – Backdoor.Win64.Winnti.gf
ac9b247691b1036a1cdb4aaf37bea97f – Rootkit.Win64.Winnti.ai
 






APT
Cyber espionage
Digital Certificates
Malware
Winnti



Authors



 Dmitry Tarakanov





Games are over: Winnti is now targeting pharmaceutical companies 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Jose Ramon Palanco 


							Posted on							June 23, 2015. 4:21 am 



We have discovered another file related: b8ffea5aa357e8bac5efc03f8e202292
You can use this Yara signature to track related files:
rule WinntiPharma
{
meta:
	author = “Jose Ramon Palanco”
	copyright = “Drainware, Inc.”
	date = “2015-06-23”
	description = “Winnti targeting pharmaceutical organizations”
	ref = “htm://securelist.com/blog/research/70991/games-are-over/”
strings:
	$s0 = “Cookie: SN=”
	$s1 = “{3ec05b4a-ea88-1378-3389-66706ba27600}”
	$s2 = “{4D36E972-E325-11CE-BFC1-08002BE10318}”
	$s3 = “master secret”
	$s4 = “MyEngineNetEvent”
condition:
	all of ($s*)
}
Reply 








Jose Ramon Palanco 


							Posted on							June 23, 2015. 4:38 am 



We have discovered another related files:
b8ffea5aa357e8bac5efc03f8e202292
80f37df0d062fa4ddaace213c2883da5
You can use this Yara signature to track related files:
rule WinntiPharma
{
meta:
	author = “Jose Ramon Palanco”
	copyright = “Drainware, Inc.”
	date = “2015-06-23”
	description = “Winnti targeting pharmaceutical organizations”
	ref = “htm://securelist.com/blog/research/70991/games-are-over/”
strings:
	$s0 = “Cookie: SN=”
	$s1 = “{3ec05b4a-ea88-1378-3389-66706ba27600}”
	$s2 = “{4D36E972-E325-11CE-BFC1-08002BE10318}”
	$s3 = “master secret”
	$s4 = “MyEngineNetEvent”
condition:
	all of ($s*)
}
Reply 








Lucie Ellis 


							Posted on							July 7, 2015. 12:11 pm 



Hi Dmitry, 
Interesting blog post. Would you be able to tell me a bit more about what this risk is/ means to big pharma?
And how concerning it is/ should be from a business POV?
Best, 
Lucie
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




 


PlugX malware: A good hacker is an apologetic hacker 






 


I am HDRoot! Part 2 






 


I am HDRoot! Part 1 






 


The Inevitable Move – 64-bit ZeuS Enhanced With Tor 






 


The rush for CVE-2013-3906 – a Hot Commodity 









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



























