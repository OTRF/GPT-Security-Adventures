# Reference for threat actor for "Operation Ghoul"

**Title**: Operation Ghoul: targeted attacks on industrial and engineering organizations | Securelist

**Source**: https://securelist.com/operation-ghoul-targeted-attacks-on-industrial-and-engineering-organizations/75718/

## Content















Operation Ghoul: targeted attacks on industrial and engineering organizations | Securelist


































































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

Operation Ghoul: targeted attacks on industrial and engineering organizations 

APT reports

17 Aug 2016

  minute read								
















Table of Contents





IntroductionMain infection vector: malicious emailsMalicious attachmentsTechnical detailsMalware functionalityMalware command centerVictim informationVictim industry informationThe last attack wavesOther attack informationConclusionIndicators of CompromiseFilenames and paths related to malwareList of malware related MD5 hashesList of malware related domainsObserved phishing URLsOther malware links 






 

Authors



 Mohamad Amin Hasbini





Introduction
Kaspersky Lab has observed new waves of attacks that started on the 8th and the 27th of June 2016. These have been highly active in the Middle East region and unveiled ongoing targeted attacks in multiple regions. The attackers try to lure targets through spear phishing emails that include compressed executables. The malware collects all data such as passwords, keystrokes and screenshots, then sends it to the attackers.
#OpGhoul targeting industrial, manufacturing and engineering organizations in 30+ countriesTweet
We found that the group behind this campaign targeted mainly industrial, engineering and manufacturing organizations in more than 30 countries. In total, over 130 organizations have been identified as victims of this campaign. Using the Kaspersky Security Network (KSN) and artifacts from malware files and attack sites, we were able to trace the attacks back to March 2015. Noteworthy is that since the beginning of their activities, the attackers’ motivations are apparently financial, whether through the victims’ banking accounts or through selling their intellectual property to interested parties, most infiltrated victim organizations are considered SMBs (Small to Medium size businesses, 30-300 employees), the utilization of commercial off-the-shelf malware makes the attribution of the attacks more difficult.
In total, over 130 organizations have been identified as victims of Operation Ghoul #OpGhoulTweet
In ancient Folklore, the Ghoul is an evil spirit associated with consuming human flesh and hunting kids, originally a Mesopotamian demon. Today, the term is sometimes used to describe a greedy or materialistic individual.
Main infection vector: malicious emails
The following picture represents emails that are being used to deliver malware to the victims, in what looks like a payment document. The e-mails sent by attackers appear to be coming from a bank in the UAE, the Emirates NBD, and include a 7z file with malware. In other cases, victims received phishing links. A quick analysis of the email headers reveals fake sources being utilised to deliver the emails to victims.

Malicious attachments
In the case of spear phishing emails with an attachment, the 7z does not contain payment instructions but a malware executable (EmiratesNBD_ADVICE.exe). We have observed executables with the following MD5s:
Malware MD5 hashes
fc8da575077ae3db4f9b5991ae67dab1b8f6e6a0cb1bcf1f100b8d8ee5cccc4c08c18d38809910667bbed747b274620155358155f96b67879938fe1a14a00dd6
Email file MD5 hashes
5f684750129e83b9b47dc53c96770e09460e18f5ae3e3eb38f8cae911d447590
The spear phishing emails are mostly sent to senior members and executives of targeted organizations, most likely because the attackers hope to get access to core intelligence, controlling accounts and other interesting information from people who have the following positions or similar:

Chief Executive Officer
Chief Operations Officer
General Manager
General Manager, Sales and Marketing
Deputy General Manager
Finance and Admin Manager
Business Development Manager
Manager
Export manager
Finance Manager
Purchase manager
Head of Logistics
Sales Executive
Supervisor
Engineer

Technical details
Malware functionality
The malware is based on the Hawkeye commercial spyware, which provides a variety of tools for the attackers, in addition to malware anonymity from attribution. It initiates by self-deploying and configuring persistence, while using anti-debugging and timeout techniques, then starts collecting interesting data from the victim’s device, including:

Keystrokes
Clipboard data
FileZilla ftp server credentials
Account data from local browsers
Account data from local messaging clients (Paltalk, Google talk, AIM…)
Account data from local email clients (Outlook, Windows Live mail…)
License information of some installed applications

#OpGhoul malware collects all data such as #passwords, keystrokes and screenshotsTweet
Data exfiltration
Data is collected by the attackers using primarily:
Http GET posts

Sent to hxxp://192.169.82.86

Email messages

mail.ozlercelikkapi[.]com (37.230.110.53), mail to info@ozlercelikkapi[.]com
mail.eminenture[.]com (192.185.140.232), mail to eminfo@eminenture[.]com

Both ozlercelikkapi[.]com and eminenture[.]com seem to belong to compromised organisations operating in manufacturing and technology services.
Malware command center
The malware connects to 192.169.82.86 to deliver collected information from the victim’s PC. This information includes passwords, clipboard data, screenshots…
hxxp://192.169.82.86/~loftyco/skool/login.phphxxp://192.169.82.86/~loftyco/okilo/login.php

The IP address 192.169.82.86 seems to belong to a compromised device running multiple malware campaigns.
Victim information
Victim organizations are distributed in different countries worldwide with attackers focused on certain countries more than others:

Number of Victim Organisations by Country
Countries marked as “others” have less than three victim organizations each, they are: Switzerland, Gibraltar, USA, Sweden, China, France, Azerbaijan, Iraq, Turkey, Romania, Iran, Iraq and Italy.
Victim industry information
Victim industry types were also indicators of targeted attacks as attackers were looking to infiltrate organizations that belong to the product life cycle of multiple goods, especially industrial equipment.
#Manufacturing #transportation #travel targets of #OpGhoulTweet

Number of Victim Organizations by Industry Type
Victim industry description



Industrial
Petrochemical, naval, military, aerospace, heavy machinery, solar energy, steel, pumps, plastics


Engineering
Construction, architecture, automation, chemical, transport, water


Shipping
International freight shipping


Pharmaceutical
Production/research of pharmaceutical and beauty products


Manufacturing
Furniture, decor, textiles


Trading
Industrial, electronics and food trading


Education
Training centers, universities, academic publishing


Tourism
Travel agencies


Technology/IT
Providers of IT technologies and consulting services


Unknown
Unidentified victims



The last attack waves
Kaspersky Lab user statistics indicate the new waves of attacks that started in June 2016 are focused on certain countries more than others.
#opghoul highly active in #MiddleEastTweet
Hundreds of detections have been reported by Kaspersky Lab users; 70% of the attacked users were found in the United Arab Emirates alone, the other 30% were distributed in Russia, Malaysia, India, Jordan, Lebanon, Turkey, Algeria, Germany, Iran, Egypt, Japan, Switzerland, Bahrain and Tunisia.

Other attack information
Phishing pages have also been spotted through 192.169.82.86, and although they are taken down quickly, more than 150 user accounts were identified as victims of the phishing links sent by the attackers. Victims were connecting from the following devices and inserting their credentials, a reminder that phishing attacks do work on all platforms: 

Windows
Mac OS X
Ubuntu
iPhone
Android

The malware files are detected using the following heuristic signatures:
Trojan.MSIL.ShopBot.wwTrojan.Win32.Fsysna.dfahTrojan.Win32.Generic
Conclusion
Operation Ghoul is one of the many attacks in the wild targeting industrial, manufacturing and engineering organizations, Kaspersky Lab recommends users to be extra cautious while checking and opening emails and attachments. In addition, privileged users need to be well trained and ready to deal with cyber threats; failure in this is, in most cases, the cause behind private or corporate data leakage, reputation and financial loss.
Indicators of Compromise
The following are common among the different malware infections; the presence of these is an indication of a possible infection.
Filenames and paths related to malware
C:\Users\%UserName%\AppData\Local\Microsoft\Windows\bthserv.exeC:\Users\%UserName%\AppData\Local\Microsoft\Windows\BsBhvScan.exeC:\Users\%UserName%\AppData\Local\Client\WinHttpAutoProxySync.exeC:\Users\%UserName%\AppData\Local\Client\WdiServiceHost.exeC:\Users\%UserName%\AppData\Local\Temp\AF7B1841C6A70C858E3201422E2D0BEA.datC:\Users\%UserName%\AppData\Roaming\Helper\Browser.txtC:\Users\%UserName%\AppData\Roaming\Helper\Mail.txtC:\Users\%UserName%\AppData\Roaming\Helper\Mess.txtC:\Users\%UserName%\AppData\Roaming\Helper\OS.txtC:\ProgramData\Mails.txtC:\ProgramData\Browsers.txt
List of malware related MD5 hashes
55358155f96b67879938fe1a14a00dd6f9ef50c53a10db09fc78c123a95e8eecb8f6e6a0cb1bcf1f100b8d8ee5cccc4c 07b105f15010b8c99d7d727ff3a9e70fae2a78473d4544ed2acd46af2e09633d 21ea64157c84ef6b0451513d0d11d02e08c18d38809910667bbed747b2746201fc8da575077ae3db4f9b5991ae67dab18d46ee2d141176e9543dea9bf1c079c836a9ae8c6d32599f21c9d1725485f1a3cc6926cde42c6e29e96474f740d12a786e959ccb692668e70780ff92757d23353664d7150ac98571e7b5652fd7e44085d87d26309ef01b162882ee5069dc0bde5a97d62dc84ede64846ea4f3ad4d2f935a68f149c193715d13a361732f5adaa1dabc47df7ae7d921f18faf685c367889aaee8ba81bee3deb1c95bd3aaa6b13d7460e18f5ae3e3eb38f8cae911d447590c3cf7b29426b9749ece1465a4ab4259e
List of malware related domains
Indyproject[.]orgStudiousb[.]comcopylines[.]bizGlazeautocaree[.]comBrokelimiteds[.]inmeedlifespeed[.]com468213579[.]com468213579[.]com357912468[.]comaboranian[.]comapple-recovery[.]ussecurity-block[.]comcom-wn[.]inf444c4f547116bfd052461b0b3ab1bc2b445a[.]comdeluxepharmacy[.]netkatynew[.]pw Mercadojs[.]com
Observed phishing URLs
hxxp://free.meedlifespeed[.]com/ComCast/hxxp://emailreferentie.appleid.apple.nl.468213579[.]com/hxxp://468213579[.]com/emailreferentie.appleid.apple.nl/emailverificatie-40985443/home/login.phphxxp://verificatie.appleid.apple.nl.referentie.357912468[.]com/emailverificatie-40985443/home/lo…hxxp://192.169.82.86/~gurgenle/verify/webmail/hxxp://customer.comcast.com.aboranian[.]com/loginhxxp://apple-recovery[.]us/hxxp://apple.security-block[.]com/Apple%20-%20My%20Apple%20ID.htmlhxxp://cgi.ebay.com-wn[.]in/itm/2000-Jeep-Wrangler-Sport-4×4-/?ViewItem&item=17475607809hxxp://https.portal.apple.com.idmswebauth.login.html.appidkey.05c7e09b5896b0334b3af1139274f266b2hxxp://2b68.f444c4f547116bfd052461b0b3ab1bc2b445a[.]com/login.htmlhxxp://www.deluxepharmacy[.]net 
Other malware links
Malware links observed on 192.169.82.86 dating back to March and April 2016:
hxxp://glazeautocaree[.]com/proforma-invoice.exehxxp://brokelimiteds[.]in/cdn/images/bro.exehxxp://brokelimiteds[.]in/cdn/images/onowu.exehxxp://brokelimiteds[.]in/cdn/images/obe.exehxxp://brokelimiteds[.]in/wp-admin/css/upload/order.exehxxp://brokelimiteds[.]in/wp-admin/css/upload/orders.exehxxp://papercuts[.]info/SocialMedia/java.exehxxp://studiousb[.]com/mercadolivrestudio/f.ziphxxp://copylines[.]biz/lasagna/gate.php?request=true
For more information on how you can protect your business from similar attacks, please visit this post from Kaspersky Business.






APT
Malware
Phishing
Social engineering
Spyware



Authors



 Mohamad Amin Hasbini





Operation Ghoul: targeted attacks on industrial and engineering organizations 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





IntroductionMain infection vector: malicious emailsMalicious attachmentsTechnical detailsMalware functionalityMalware command centerVictim informationVictim industry informationThe last attack wavesOther attack informationConclusionIndicators of CompromiseFilenames and paths related to malwareList of malware related MD5 hashesList of malware related domainsObserved phishing URLsOther malware links 





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




 


5G technology predictions 2020 






 


5G security and privacy for smart cities 






 


Gaza Cybergang – updated activity in 2017: 






 


Gaza cybergang, where’s your IR team? 






 


The Syrian malware part 2: Who is The Joe? 









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



























