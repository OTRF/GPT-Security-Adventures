# Reference for threat actor for "Roaming Mantis"

**Title**: Roaming Mantis, part V | Securelist

**Source**: https://securelist.com/roaming-mantis-part-v/96250/

## Content















Roaming Mantis, part V | Securelist


































































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


 











 

Malware descriptions

Roaming Mantis, part V 

Malware descriptions

27 Feb 2020

  minute read								
















Table of Contents





Distribution of Wroba.g via SMiShing with impersonated brandsAllowlist feature of Wroba.g landing page for Korea onlyMultidex obfuscation trick in a loader module of Wroba.gWroba.g is targeting carrier billing and online banks in JapanWroba.j and Fakecop discovered in 2019ConclusionFurther readingExample of md5 hashes for each APK 






 

Authors



 Suguru Ishimaru



Distributed in 2019 using SMiShing and enhanced anti-researcher techniques


Kaspersky has continued to track the Roaming Mantis campaign. The group’s attack methods have improved and new targets continuously added in order to steal more funds. The attackers’ focus has also shifted to techniques that avoid tracking and research: allowlist for distribution, analysis environment detection and so on. We’ve also observed new malware families: Fakecop (also known as SpyAgent by McAfee) and Wroba.j (also known as Funkybot by Fortinet). 
Distribution of Wroba.g via SMiShing with impersonated brands
In 2018, the group added a distribution method for Wroba.g (aliases: Moqhao and XLoader), in addition to the original method of DNS hijacking. It was SMiShing using a spoofed delivery notice from a logistics company. In 2019, we confirmed another new method where a downloaded malicious APK file has an icon that impersonates a major courier company brand. The spoofed brand icon is customized for the country it targets, for example, Sagawa Express for Japan; Yamato Transport and FedEx for Taiwan; CJ Logistics for South Korea and Econt Express for Russia.
Examples of SMiShing with Android malware icons impersonating brands 
In February 2020, the attacker modified a SMiShing message from a spoofed absence notification to “delivering free masks for the coronavirus issue” in Japan, according to a warning by Japan Cybercrime Control Center (JC3). This once again shows that criminals always make use of hot topics in their activities. 
Allowlist feature of Wroba.g landing page for Korea only
The Roaming Mantis actor also employed a new feature in their Wroba.g landing page – currently only on the Korean page. It’s a allowlist feature to evade security researchers. When a user visits the landing page, they have to enter their phone number for confirmation. If the phone number is on the allowlist, the landing page distributes a malicious app.apk:
The fake CJ Logistics landing page includes an allowlist
The actor has a habit of trying out their new methods in Korean first. It means the method described above may be applied later on landing pages in other languages as well. If that happens, it would make it almost impossible for researchers to obtain a sample, because it would require a specific phone number in the actor’s allowlist database.
Multidex obfuscation trick in a loader module of Wroba.g
A single Dalvik Executable (DEX) has a 64K reference limit. As a workaround, a configuration of Mutidex allows the application to build and read multiple DEX files. In 2019, the actor used Multidex in an APK file to hide a malicious loader module as an obfuscation trick. Our analysis shows that it has been modified little by little:  
Transition of obfuscation using Multidex
The classes${num}.dex marked with a red square is the actual malicious loader module. All the other DEX files are simply junk code. However, the encrypted payload of Wroba.g is still under the assets directory and can be decrypted by the simple python script described in our previous blogpost.
Wroba.g is targeting carrier billing and online banks in Japan
The actor has a strong financial motivation. They are targeting carrier billing and online bank accounts. They have implemented redirection to phishing sites to steal credentials in the decrypted payload of Wroba.g:
Hardcoded pkg name, URL of pinterest.com and pop-up message
When the malware detects a specific package of a Japanese online bank or specific mobile carriers on the infected device, it connects in the background to a hardcoded malicious account of pinterest.com to fetch a phishing site with an alert message. The message claims that it has blocked unauthorized access from a third party and asks the user to click on a button to confirm they want to proceed. If the user clicks the button, they will be redirected to a phishing site:
Redirecting to a phishing site via malicious account on pinterest.com
The targeted packages for online banks and mobile carriers correspond to the relevant accounts on pinterest.com that lead to phishing sites:


Pkgs or mobile carrier
Accounts on pinterest.com
Phishing site in Dec 2019
Phishing site in Jan 2020


jp.co.japannetbank.smtapp.balance
nor**********
jnb.jp-bankq[.]com
N/A


jp.co.jibunbank.jibunmain
abi********
jibun.jp-bankq[.]com
N/A


jp.co.netbk.smartkey.SSNBSmartkey
sin*************
sbi.jp-bankq[.]com
N/A


jp.co.rakuten_bank.rakutenbank
kel***************
rakuten.jp-bankq[.]com
N/A


jp.co.sevenbank.AppPassbook
gh6******
seven.jp-bankq[.]com
N/A


jp.co.smbc.direct
eme*************
smbc.jp-bankq[.]com
smbc.bk-securityo[.]com


jp.japanpost.jp_bank.FIDOapp
fel***************
jppost.jp-bankq[.]com
N/A


jp.mufg.bk.applisp.app
sho*************
mufg.jp-bankq[.]com
N/A


Docomo
ami***********
nttdocomo-uh[.]com
nttdocomo-xm[.]com


au
pos***********
au-ul[.]com
au-xm[.]com


Softbank
ash************
epos-ua[.]com
N/A


As can be seen in the table above, all the accounts have corresponding phishing sites as of December 2019 (data provided by @ninoseki on Twitter). These destination URLs are continuously changed by the attackers. In January 2020, only three of these accounts were enabled for some reason. However, as it’s easy for the criminals to modify the phishing page address, apps without corresponding phishing sites are also likely to be attacked again in the near future. 
Wroba.j and Fakecop discovered in 2019
Roaming Mantis has been using Wroba.g and Wroba.f as its main Android malware. In April 2019, we observed two more malware families, Wroba.j and Fakecop. These two malware families have some similarities with the other families in terms of infrastructure, distribution channel, etc. We have created some slides, Roaming Mantis: A melting pot of Android bots in Botconf2019, showing the timeline, impersonated brands, malware features and money laundering method.
Based on our telemetry data, detection rates of both malicious programs were very low. We believe that this was a test by the attacker. However, the most alarming thing we discovered was the following SMS spamming function in Wroba.j:
Generating feedback for SMS spamming results
The function automatically creates a sophisticated list of phone numbers from the feedback for SMS spamming results. This malware also has another function that checks the International Mobile Subscriber Identifier (IMSI) to identify mobile carriers in Japan and add the phone number to a relevant spamming list.
Checking the IMSI of mobile carrier Docomo
According to the hardcoded IMSIs and strings shown below, the attacker seems to be targeting Docomo and Softbank mobile carriers.
IMSI of Docomo:




44001
4401
44058


44002
4402
4406


44003
4403
44087


44009
44049
44099 


IMSI of Softbank:




44020
44021


44005
44101


Conclusion
The Roaming Mantis actor is strongly motivated by financial gain and is eager to evade tracking by researchers. It is now employing yet another method – allowlisting – to achieve this. This new method is currently only being applied for Korean pages, but it’s only a matter of time before it’s implemented for other languages. 
The actor is still very active in using SMiShing for Android malware distribution. This is particularly alarming, because it means all infected mobile devices could form a botnet for malware delivery, SMiShing, and so on. ISPs, together with security companies, need to keep a close eye on the Roaming Mantis campaign to understand how to combat it.
Further reading
Further information about the Fakecop and Wroba.j families has also appeared in the following blogs published by McAfee and Fortinet respectively:

MoqHao Related Android Spyware Targeting Japan and Korea Found on Google Play
FunkyBot: A New Android Malware Family Targeting Japan

These blogposts provide some interesting updates on Roaming Mantis activities during 2019. 
Example of md5 hashes for each APK
e6ae4277418323810505c28d2b6b3647	Wroba.g
939770e5a14129740dc57c440afbf558	Wroba.f
521312a8b5a76519f9237ec500afd534	Wroba.j
6d29caaa8b30cc8b454e74a75d33c902	Fakecop







Botnets
Google Android
Malware Descriptions
Mobile Malware
Phishing



Authors



 Suguru Ishimaru





Roaming Mantis, part V 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





Distribution of Wroba.g via SMiShing with impersonated brandsAllowlist feature of Wroba.g landing page for Korea onlyMultidex obfuscation trick in a loader module of Wroba.gWroba.g is targeting carrier billing and online banks in JapanWroba.j and Fakecop discovered in 2019ConclusionFurther readingExample of md5 hashes for each APK 





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




 


APT10: Tracking down LODEINFO 2022, part II 






 


APT10: Tracking down LODEINFO 2022, part I 






 


Roaming Mantis reaches Europe 






 


Roaming Mantis dabbles in mining and phishing multilingually 






 


Roaming Mantis uses DNS hijacking to infect Android smartphones 









Subscribe to our weekly e-mails
The hottest research right in your inbox




Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ








In the same category




 


Coyote: A multi-stage banking Trojan abusing the Squirrel installer 






 


Cracked software beats gold: new macOS backdoor stealing cryptowallets 






 


New macOS Trojan-Proxy piggybacking on cracked software 






 


BlueNoroff: new Trojan attacking macOS users 






 


Ducktail fashion week 






 















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



























