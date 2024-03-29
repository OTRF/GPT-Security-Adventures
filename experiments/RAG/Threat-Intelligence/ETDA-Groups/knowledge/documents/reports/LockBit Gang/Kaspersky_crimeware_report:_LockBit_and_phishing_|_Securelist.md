# Reference for threat actor for "LockBit Gang"

**Title**: Kaspersky crimeware report: LockBit and phishing | Securelist

**Source**: https://securelist.com/crimeware-report-lockbit-switchsymb/110068/

## Content















Kaspersky crimeware report: LockBit and phishing | Securelist


































































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


 











 

Malware reports

LockBit Green and phishing that targets organizations 

Malware reports

22 Jun 2023

  minute read								
















Table of Contents





IntroductionPhishing and a kitLockBit GreenMulti-platform LockBitConclusion 






 

Authors




GReAT





Introduction
In recent months, we published private reports on a broad range of subjects. We wrote about malware targeting Brazil, about CEO fraud attempts, Andariel, LockBit and others. For this post, we selected three private reports, namely those related to LockBit and phishing campaigns targeting businesses, and prepared excerpts from these. If you have questions or need more information about our crimeware reporting service, contact crimewareintel@kaspersky.com.
Phishing and a kit
Recently we stumbled upon a Business Email Compromise (BEC) case, active since at least Q3 2022. The attackers target German-speaking companies in the DACH region. As in many other BEC cases, they register a domain name that is similar to that used by the attacked organization and typically differs in one or two letters. For reasons unknown, the Reply-to field contains a different email address from the From field. The Reply-to email address does not mimic the target-organization’s domain.
In contrast to BEC campaigns that are targeted and require significant effort from the criminals, ordinary phishing campaigns are relatively simple. This creates opportunities for automation, of which the SwitchSymb phishing kit is one example.
At the end of this past January, we observed a spike in phishing email from a campaign targeting business users, which we have closely monitored. We noticed that the message contained a link to an “email confirmation form”. If one clicked on the link, they found themselves on a page looking very similar to that of the recipient’s domain. The phishing kit was designed to serve multiple campaigns at a time while running one instance on the web server. This was easily demonstrated by modifying the page URL, specifically the reference to the targeted user in it^ the layout of the phishing page would change.
An example of a SwitchSymb-generated phishing page
LockBit Green
LockBit is one of the most prolific ransomware groups currently active, targeting businesses all over the world. Over time, they have adopted code from other ransomware gangs, such as BlackMatter and DarkSide, making it easier for potential affiliates to operate the ransomware.
Starting in this past February, we have detected a new variant, named “LockBit Green”, which borrows code from the now-defunct Conti gang. According to the Kaspersky Threat Attribution Engine (KTAE), LockBit incorporates 25% of Conti code.
KTAE shows similarities between LockBit Green and Conti
Three pieces of adopted code really stand out: the ransomware note, the command line options and the encryption scheme. Adopting the ransom note makes the least sense. We could not think of a good reason for doing so, but nevertheless, LockBit did it. In terms of command line options, the group added those from Conti to make them available in Lockbit. All the command line options available in Lockbit Green are: 



Flag
Functionality


-p folder
Encrypt the selected folder using a single thread


-m local
Encrypt all available drives within multiple threads, each of them


-m net
Encrypt all network shares within multiple threads, each of them


-m all
Encrypt all available drives and Network shares within multiple threads, each of them


-m backups
Flag not available to use on the detected versions but coded inside the ransomware


-size chunk
Functionality to encrypt only part of the files


-log file.log
Possibility to log every action performed by the ransomware


-nomutex
Skip mutex creation



Finally, LockBit adopted the encryption scheme from Conti. The group now usesa custom ChaCha8 implementation to encrypt files with a randomly generated key and nonce that are saved/encrypted with a hard-coded public RSA key.
Binary diffing across the two families
Multi-platform LockBit
We recently stumbled on a ZIP file, uploaded to a multiscanner, that contained LockBit samples for multiple architectures, such as Apple M1, ARM v6, ARM v7, FreeBSD and many others. The next question would obviously be, “What about codebase similarity?”.
For this, we used the KTAE: simply throwing in the downloaded ZIP file was enough to see that all the samples were derived from the LockBit Linux/ESXi version, which we wrote about in an earlier private report.
Source code shared with LockBit Linux
Further analysis of the samples led us to believe that LockBit were in the process of testing their ransomware on various architectures, instead of deploying it in the wild. For instance, the macOS sample was unsigned, so it could not be executed as is. Also, the string encryption method was simple: one byte XOR.
Nevertheless, our findings suggest that LockBit will target more platforms in the wild in the (near) future.
Conclusion
The world of cybercrime is huge, consisting of many players and gangs that are fluid in terms of composition. Groups adopt other groups’ code, and affiliates — which can be considered cybercrime groups in their own right — switch between different types of malware. Groups work on upgrades to their malware, adding features and providing support for multiple, previously unsupported, platforms, a trend that existed for some time now.
When an incident occurs, it is important to find out who has targeted you. This helps to limit the scope of incident response and could help to prevent further damage. The KTAE attributes code to cybercrime groups and highlights features shared by different malware families. This information can also help in taking proactive countermeasures to prevent incidents from happening in the future.
Finally, criminals often resort to old tricks, such as phishing, which, nevertheless, remain highly effective. Being aware of the latest trends can prevent threats like BEC from materializing.
Intelligence reports can help you to stay protected against these threats. If you want to keep up to date on the latest TTPs used by criminals or have questions about our private reports, contact crimewareintel@kaspersky.com.






Apple MacOS
crimeware
Cybercrime
LockBit
Malware
Malware Descriptions
Phishing
Phishing kits
Ransomware
Spear phishing



Authors




GReAT





LockBit Green and phishing that targets organizations 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





IntroductionPhishing and a kitLockBit GreenMulti-platform LockBitConclusion 





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




 


FakeSG campaign, Akira ransomware and AMOS macOS stealer 






 


IT threat evolution in Q3 2023. Mobile statistics 






 


IT threat evolution Q3 2023 






 


IT threat evolution in Q3 2023. Non-mobile statistics 






 


Stealer for PIX payment system, new Lumar stealer and Rhysida ransomware 






 















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



























