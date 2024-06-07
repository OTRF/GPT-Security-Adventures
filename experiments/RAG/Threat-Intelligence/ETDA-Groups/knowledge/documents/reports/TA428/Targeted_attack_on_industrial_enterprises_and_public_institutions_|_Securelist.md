# Reference for threat actor for "TA428"

**Title**: Targeted attack on industrial enterprises and public institutions | Securelist

**Source**: https://securelist.com/targeted-attack-on-industrial-enterprises-and-public-institutions/107054/

## Content















Targeted attack on industrial enterprises and public institutions | Securelist


































































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

Targeted attack on industrial enterprises and public institutions 

APT reports

08 Aug 2022

  minute read								
















Table of Contents





Initial infectionAdditional malwareLateral movementData theftWho is behind the attack?Conclusion 






 

Authors




Kaspersky ICS CERT





In January 2022, Kaspersky ICS CERT experts detected a wave of targeted attacks on military industrial complex enterprises and public institutions in several countries. In the course of our research, we were able to identify over a dozen of attacked organizations. The attack targeted industrial plants, design bureaus and research institutes, government agencies, ministries and departments in several East European countries (Belarus, Russia, and Ukraine), as well as Afghanistan.
The attackers were able to penetrate dozens of enterprises and even hijack the IT infrastructure of some, taking control of systems used to manage security solutions.
An analysis of information obtained while investigating the incidents indicates that cyberespionage was the goal of this series of attacks.
Initial infection
The attackers penetrated the enterprise network using carefully crafted phishing emails, some of which use information that is specific to the organization under attack and is not publicly available. This could indicate that the attackers did preparatory work in advance (they may have obtained the information in earlier attacks on the same organization or its employees, or on other organizations or individuals associated with the victim organization).
Microsoft Word documents attached to the phishing emails contained malicious code that exploits the CVE-2017-11882 vulnerability. The vulnerability enables an attacker to execute arbitrary code (in the attacks analyzed, the main module of the PortDoor malware) without any additional user activity.
An earlier series of attacks in which the PortDoor malware was also used was described by Cybereason experts. A new version of PortDoor was identified in the course of our research.

Initial infection of a system
After being launched, PortDoor collects general information on the infected system and sends it to the malware command-and-control (CnC) server. In cases where an infected system is of interest to the attackers, they use the PortDoor functionality to control the system remotely and install additional malware.
Additional malware
The attackers used five different backdoors at the same time – probably to set up redundant communication channels with infected systems in case one of the malicious programs was detected and removed by a security solution. The backdoors used provide extensive functionality for controlling infected systems and collecting confidential data.
Of the six backdoors identified on infected systems, five (PortDoor, nccTrojan, Logtu, Cotx, and DNSep) have been used earlier in attacks attributed by other researchers to APT TA428. The sixth backdoor is new and has not been observed in other attacks.
Lateral movement
After gaining a foothold on the initial system, the attackers attempt to spread the malware to other computers on the enterprise network. To gain access to those computers, the attackers use network scanning results, as well as user credentials stolen earlier.
The Ladon hacking utility (which is popular in China) is used as the main lateral movement tool. It combines network scanning, vulnerability search and exploitation, password attack, and other functionality. The attackers also extensively use standard utilities that are part of the Microsoft Windows operating system.
The attack’s final stage involves hijacking the domain controller and gaining full control of all of the organization’s workstations and servers.
The attackers used DLL hijacking and process hollowing techniques extensively in the attack to prevent security software from detecting the malware.
Data theft
After gaining domain administrator privileges, the attackers searched for and exfiltrated documents and other files that contained the attacked organization’s sensitive data to their servers hosted in different countries. These servers were also used as stage one CnC servers.
The attackers compressed stolen files into encrypted and password-protected ZIP archives. After receiving the data collected, the stage one CnC servers forwarded the archives received to a stage two server located in China.

Transfer of stolen data from infected systems
Who is behind the attack?
Significant overlaps in tactics, techniques, and procedures (TTPs) have been observed with APT TA428 activity.
The research identified malware and CnC servers previously used in attacks attributed by other researchers to TA428 APT group.
Some indirect evidence also supports our conclusion.
We believe that the series of attacks that we have identified is highly likely to be an extension of a known campaign that has been described in Cybereason, DrWeb, and NTTSecurity research and has been attributed with a high degree of confidence to APT TA428 activity.
Conclusion
The findings of our research show that spear phishing remains one of the most relevant threats to industrial enterprises and public institutions. In the course of the attack, the attackers used mostly known backdoor malware, as well as standard lateral movement techniques and methods designed to evade detection by security solutions.
The attack series that we have identified is not the first in the campaign. Given that the attackers have had some success, we believe it is highly likely that similar attacks will occur again in the future. Industrial enterprises and public institutions should do a great deal of work to successfully thwart such attacks.
Technical details of the attacks, as well as recommendations and indicators of compromise, can be found in the full public version of the article on the Kaspersky ICS CERT website.
A private version of the article has been published on Kaspersky Threat Intelligence.
We are not wrapping up our investigation as yet and will release information on new findings as they appear. For more information, you can contact ics-cert@kaspersky.com.






APT
Backdoor
Cyber espionage
Data theft
Malware
Spear phishing
Targeted attacks
Vulnerabilities and exploits



Authors




Kaspersky ICS CERT





Targeted attack on industrial enterprises and public institutions 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





Initial infectionAdditional malwareLateral movementData theftWho is behind the attack?Conclusion 





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




 


Threat landscape for industrial automation systems. Statistics for H1 2023 






 


Threat landscape for industrial automation systems for H2 2022 






 


The secrets of Schneider Electric’s UMAS protocol 






 


Threat landscape for industrial automation systems for H1 2022 






 


Threat landscape for industrial automation systems, H2 2021 









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



























