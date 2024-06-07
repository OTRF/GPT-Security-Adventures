# Reference for threat actor for "TA516"

**Title**: AZORult spreads as a fake ProtonVPN installer | Securelist

**Source**: https://securelist.com/azorult-spreads-as-a-fake-protonvpn-installer/96261/

## Content















AZORult spreads as a fake ProtonVPN installer | Securelist



































































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


 











 

Incidents

AZORult spreads as a fake ProtonVPN installer 

Incidents

18 Feb 2020

  minute read								








 

Authors



 Dmitry Bestuzhev





AZORult has its history. However, a few days ago, we discovered what appears to be one of its most unusual campaigns: abusing the ProtonVPN service and dropping malware via fake ProtonVPN installers for Windows. 
Screenshot of a fake ProtonVPN website
The campaign started at the end of November 2019 when the threat actor behind it registered a new domain under the name protonvpn[.]store. The Registrar used for this campaign is from Russia. 
We have found that at least one of the infection vectors is through affiliation banners networks (Malvertising).
When the victim visits a counterfeit website and downloads a fake ProtonVPN installer for Windows, they receive a copy of the Azorult botnet implant.

The Website is an HTTrack copy of the original ProtonVPN website as shown below.

Once the victim runs the implant, it collects the infected machine’s environment information and reports it to the C2, located on  the same accounts[.]protonvpn[.]store  server.





{
  "config: ": [
    "MachineID :",
    "EXE_PATH  :",
    "Windows    :",
    "Computer(Username) :",
    "Screen:",
    "Layouts:",
    "LocalTime:",
    "Zone:",
    "[Soft]",
    "Host: User-Agent: Accept: ; charset=Content-Type:  HTTP/1.0POST text/*utf-8text/htmlHTTP/Proxy-AuthenticateAcceptContent-TypeContent-Lengthrealmhttp::Connection::connect: using proxy %1%http::Connection::connect: testing %1% for proxy routing"
  ]
}




1234567891011121314

{  "config: ": [    "MachineID :",    "EXE_PATH  :",    "Windows    :",    "Computer(Username) :",    "Screen:",    "Layouts:",    "LocalTime:",    "Zone:",    "[Soft]",    "Host: User-Agent: Accept: ; charset=Content-Type:  HTTP/1.0POST text/*utf-8text/htmlHTTP/Proxy-AuthenticateAcceptContent-TypeContent-Lengthrealmhttp::Connection::connect: using proxy %1%http::Connection::connect: testing %1% for proxy routing"  ]}




In their greed, the threat actors have designed the malware to steal cryptocurrency from locally available wallets (Electrum, Bitcoin, Etherium, etc.), FTP logins and passwords from FileZilla, email credentials, information from locally installed browsers (including cookies), credentials for WinSCP, Pidgin messenger and others.

We have been able to identify a few samples associated with the campaign:



Filename
MD5 hash


ProtonVPN_win_v1.10.0.exe
cc2477cf4d596a88b349257cba3ef356


ProtonVPN_win_v1.11.0.exe
573ff02981a5c70ae6b2594b45aa7caa


ProtonVPN_win_v1.11.0.exe
c961a3e3bd646ed0732e867310333978


ProtonVPN_win_v1.11.0.exe
2a98e06c3310309c58fb149a8dc7392c


ProtonVPN_win_v1.11.0.exe
f21c21c2fceac5118ebf088653275b4f


ProtonVPN_win_v1.11.0.exe
0ae37532a7bbce03e7686eee49441c41 


Unknown
974b6559a6b45067b465050e5002214b 



Kaspersky products detect this threat as HEUR:Trojan-PSW.Win32.Azorult.gen







Botnets
Cryptocurrencies
Data theft
Malvertizing
Trojan-stealer



Authors



 Dmitry Bestuzhev





AZORult spreads as a fake ProtonVPN installer 
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




 


Cyberthreats to financial organizations in 2022 






 


Targeted ransomware: it’s not just about encrypting your data! 






 


The world’s southernmost security conference 






 


Cybercriminals target early IRS 2018 refunds now 






 


IT threats during the 2016 Olympic Games in Brazil 









Subscribe to our weekly e-mails
The hottest research right in your inbox




Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ








In the same category




 


A hack in hand is worth two in the bush 






 


QBot banker delivered through business correspondence 






 


Not just an infostealer: Gopuram backdoor deployed through 3CX supply chain attack 






 


CVE-2022-41040 and CVE-2022-41082 – zero-days in MS Exchange 






 


Ongoing exploitation of CVE-2022-41352 (Zimbra 0-day) 






 















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



























