# Reference for threat actor for "El Machete"

**Title**: "El Machete" | Securelist

**Source**: https://securelist.com/el-machete/66108/

## Content















"El Machete" | Securelist



































































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

“El Machete” 

APT reports

20 Aug 2014

  minute read								
















Table of Contents





IntroductionWhat is “Machete”?Targets of “Machete”How does “Machete” operate?Indicators of CompromiseWeb infectionsDomainsInfection artifactsTraces on infected machinesHuman part of “Machete”LanguageConclusion 






 

Authors




GReAT





Introduction
Some time ago, a Kaspersky Lab customer in Latin America contacted us to say he had visited China and suspected his machine was infected with an unknown, undetected malware. While assisting the customer, we found a very interesting file in the system that is completely unrelated to China and contained no Chinese coding traces. At first look, it pretends to be a Java related application but after a quick analysis, it was obvious this was something more than just a simple Java file.  It was a targeted attack we are calling “Machete”.
What is “Machete”?
“Machete” is a targeted attack campaign with Spanish speaking roots. We believe this campaign started in 2010 and was renewed with an improved infrastructure in 2012. The operation may be still “active”.
The malware is capable of the following cyber-espionage operations:

Logging keystrokes
Capturing audio from the computer’s microphone
Capturing screenshots
Capturing geolocation data
Taking photos from the computer’s web camera
Copying files to a remote server
Copying files to a special USB device if inserted
Hijjacking the clipboard and capturing information from the target machine

Targets of “Machete”

Most of the victims are located in, Venezuela, Ecuador, Colombia, Peru, Russia, Cuba, and Spain, among others. In some cases, such as Russia, the target appears to be an embassy from one of the countries of this list.
Targets include high-level profiles, including intelligence services, military, embassies and government institutions.
How does “Machete” operate?
The malware is distributed via social engineering techniques, which includes spear-phishing emails and infections via Web by a fake Blog website. We have found no evidence of of exploits targeting zero-day vulnerabilities. Both the attackers and the victims appear to be Spanish-speaking.
During this investigation, we also discovered many other the files installing this cyber-espionage tool in what appears to be a dedicated a spear phishing campaign. These files display a PowerPoint presentation that installs the malware on the target system once the file is opened.  These are the names of the PowerPoint attachments:

Hermosa XXX.pps.rar
Suntzu.rar
El arte de la guerra.rar
Hot brazilian XXX.rar

These files are in reality Nullsoft Installer self-extracting archives and have compilation dates going back to 2008.
A consequence of the embedded  Python code inside the executables is that these installers include all the necessary Python libraries as well as the PowerPoint file shown to the victim during the installation. The result is extremely large files, over 3MB.
Here are some screnshots of the mentioned files:



A technical relevant fact about this campaign is the use of Python embedded into Windows executables of the malware. This is very unusual and does not have any advantage for the attackers except ease of coding. There is no multi-platform support as the code is heavily Windows-oriented (use of libraries). However, we discovered several clues that the attackers prepared the infrastructure for Mac OS X and Unix victims as well. In addition to Windows components, we also found a mobile (Android) component.
Both attackers and victims speak Spanish natively, as we see it consistently in the source code of the client side and in the Python code.
Indicators of Compromise
Web infections
The following code snippets were found into the HTML of websites used to infect victims:

Note: Thanks to Tyler Hudak from Korelogic who noticed that the above HTML is copy pasted from SET, The Social Engineering Toolkit (https://www.trustedsec.com/downloads/social-engineer-toolkit/).
Also the following link to one known infection artifact:
hxxp://name.domain.org/nickname/set/Signed_Update.jar
Domains
The following are domains found during the infection campaign. Any communication with them must be considered extremely suspicious
java.serveblog.net 
agaliarept.com
frejabe.com
grannegral.com
plushbr.com
xmailliwx.com
blogwhereyou.com (sinkholed by Kaspersky Lab)
grannegral.com (sinkholed by Kaspersky Lab)
Infection artifacts




MD5
Filename


61d33dc5b257a18eb6514e473c1495fe
AwgXuBV31pGV.eXe


b5ada760476ba9a815ca56f12a11d557
EL ARTE DE LA GUERRA.exe


d6c112d951cb48cab37e5d7ebed2420b
Hermosa XXX.rar


df2889df7ac209e7b696733aa6b52af5
Hermosa XXX.pps.rar


e486eddffd13bed33e68d6d8d4052270
Hermosa XXX.pps.rar


e9b2499b92279669a09fef798af7f45b
Suntzu.rar


f7e23b876fc887052ac8e2558f0d6c38
Hot Brazilian XXX.rar


b26d1aec219ce45b2e80769368310471
Signed_Update.jar




Traces on infected machines
Creates the file Java Update.lnk pointing to appdata/Jre6/java.exe
Malware is installed in appdata/ MicroDes/
Running processes Creates Task Microsoft_up
Human part of “Machete”
Language
The first evidence is the language used, both for the victims and attackers, is Spanish.
The victims are all Spanish speaking according to the filenames of the stolen documents.
The language is also Spanish for the operators of the campaign, we can find all the server side code written in this language: reportes, ingresar, peso, etc.
Conclusion
The “Machete” discovery shows there are many regional  players in the world of targeted attacks. Unfortunately, such attacks became a part of the cyber arsenal of many nations located over the world. We can be sure there are other parallel targeted attacks running now in Latin America and other regions.
Kaspersky Lab products detect malicious samples related to this targeted attack as Trojan-Spy.Python.Ragua.
Note: A full analysis of the Machete attacks is available to the Kaspersky Intelligent Services customers. Contact: intelreports@kaspersky.com







APT
Cyber espionage
Machete
Spear phishing



Authors




GReAT





“El Machete” 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





IntroductionWhat is “Machete”?Targets of “Machete”How does “Machete” operate?Indicators of CompromiseWeb infectionsDomainsInfection artifactsTraces on infected machinesHuman part of “Machete”LanguageConclusion 





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



























