# Reference for threat actor for "Emissary Panda, APT 27, LuckyMouse, Bronze Union"

**Title**: LuckyMouse hits national data center to organize country-level waterholing campaign | Securelist

**Source**: https://securelist.com/luckymouse-hits-national-data-center/86083/

## Content















LuckyMouse hits national data center to organize country-level waterholing campaign | Securelist



































































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

LuckyMouse hits national data center to organize country-level waterholing campaign 

APT reports

13 Jun 2018

  minute read								
















Table of Contents





What happened?Who’s behind it?How did the malware spread?What did the malware do in the data center?What does the resulting watering hole look like?ConclusionsSome indicators of compromise 






 

Authors



 Denis Legezo





What happened?
In March 2018 we detected an ongoing campaign targeting a national data center in the Central Asia that we believe has been active since autumn 2017. The choice of target made this campaign especially significant – it meant the attackers gained access to a wide range of government resources at one fell swoop. We believe this access was abused, for example, by inserting malicious scripts in the country’s official websites in order to conduct watering hole attacks.
The operators used the HyperBro Trojan as their last-stage in-memory remote administration tool (RAT). The timestamps for these modules are from December 2017 until January 2018. The anti-detection launcher and decompressor make extensive use of Metasploit’s shikata_ga_nai encoder as well as LZNT1 compression.
Kaspersky Lab products detect the different artifacts used in this campaign with the following verdicts: Trojan.Win32.Generic, Trojan-Downloader.Win32.Upatre and Backdoor.Win32.HyperBro. A full technical report, IoCs and YARA rules are available from our intelligence reporting service (contact us intelligence@kaspersky.com).
Who’s behind it?
Due to tools and tactics in use we attribute the campaign to LuckyMouse Chinese-speaking actor (also known as EmissaryPanda and APT27). Also the C2 domain update.iaacstudio[.]com was previously used in their campaigns. The tools found in this campaign, such as the HyperBro Trojan, are regularly used by a variety of Chinese-speaking actors. Regarding Metasploit’s shikata_ga_nai encoder – although it’s available for everyone and couldn’t be the basis for attribution, we know this encoder has been used by LuckyMouse previously.
Government entities, including the Central Asian ones also were a target for this actor before. Due to LuckyMouse’s ongoing waterholing of government websites and the corresponding dates, we suspect that one of the aims of this campaign is to access web pages via the data center and inject JavaScripts into them.

How did the malware spread?

The initial infection vector used in the attack against the data center is unclear. Even when we observed LuckyMouse using weaponized documents with CVE-2017-11882 (Microsoft Office Equation Editor, widely used by Chinese-speaking actors since December 2017), we can´t prove they were related to this particular attack. It’s possible the actor used a waterhole to infect data center employees.
The main C2 used in this campaign is bbs.sonypsps[.]com, which resolved to IP-address, that belongs to the Ukrainian ISP network, held by a Mikrotik router using firmware version 6.34.4 (from March 2016) with SMBv1 on board. We suspect this router was hacked as part of the campaign in order to process the malware’s HTTP requests. The Sonypsps[.]com domain was last updated using GoDaddy on 2017-05-05 until 2019-03-13.
FMikrotik router with two-year-old firmware and SMBv1 on board used in this campaign
In March 2017, Wikileaks published details about an exploit affecting Mikrotik called ChimayRed. According to the documentation, however, it doesn’t work for firmware versions higher than 6.30. This router uses version 6.34.
There were traces of HyperBro in the infected data center from mid-November 2017. Shortly after that different users in the country started being redirected to the malicious domain update.iaacstudio[.]com as a result of the waterholing of government websites. These events suggest that the data center infected with HyperBro and the waterholing campaign are connected.
What did the malware do in the data center?
Anti-detection stages. Different colors show the three dropped modules: legit app (blue), launcher (green), and decompressor with the Trojan embedded (red)
The initial module drops three files that are typical for Chinese-speaking actors: a legit Symantec pcAnywhere (IntgStat.exe) for DLL side loading, a .dll launcher (pcalocalresloader.dll) and the last-stage decompressor (thumb.db). As a result of all these steps, the last-stage Trojan is injected into svchost.exe’s process memory.
The launcher module, obfuscated with the notorious Metasploit’s shikata_ga_nai encoder, is the same for all the droppers. The resulting deobfuscated code performs typical side loading: it patches pcAnywhere’s image in memory at its entry point. The patched code jumps back to the decryptor’s second shikata_ga_nai iteration, but this time as part of the allowlisted application.
This Metasploit’s encoder obfuscates the last part of the launcher’s code, which in turn resolves the necessary API and maps thumb.db into the same process’s (pcAnywhere) memory. The first instructions in the mapped thumb.db are for a new shikata_ga_nai iteration. The decrypted code resolves the necessary API functions, decompresses the embedded PE file with RtlCompressBuffer() using LZNT1 and maps it into memory.
What does the resulting watering hole look like?
The websites were compromised to redirect visitors to instances of both ScanBox and BEeF. These redirects were implemented by adding two malicious scripts obfuscated by a tool similar to the Dean Edwards packer.
Resulting script on the compromised government websites
Users were redirected to https://google-updata[.]tk:443/hook.js, a BEeF instance, and https://windows-updata[.]tk:443/scanv1.8/i/?1, an empty ScanBox instance that answered a small piece of JavaScript code.
Conclusions
LuckyMouse appears to have been very active recently. The TTPs for this campaign are quite common for Chinese-speaking actors, where they typically provide new solid wrappers (launcher and decompressor protected with shikata_ga_nai in this case) around their RATs (HyperBro).
The most unusual and interesting point here is the target. A national data center is a valuable source of data that can also be abused to compromise official websites. Another interesting point is the Mikrotik router, which we believe was hacked specifically for the campaign. The reasons for this are not very clear: typically, Chinese-speaking actors don’t bother disguising their campaigns. Maybe these are the first steps in a new stealthier approach.
Some indicators of compromise
Droppers
22CBE2B0F1EF3F2B18B4C5AED6D7BB79
0D0320878946A73749111E6C94BF1525
Launcher
ac337bd5f6f18b8fe009e45d65a2b09b
HyperBro in-memory Trojan
04dece2662f648f619d9c0377a7ba7c0
Domains and IPs
bbs.sonypsps[.]com
update.iaacstudio[.]com
wh0am1.itbaydns[.]com
google-updata[.]tk
windows-updata[.]tk






JavaScript
Targeted attacks
Trojan
Vulnerabilities and exploits
Watering hole attacks



Authors



 Denis Legezo





LuckyMouse hits national data center to organize country-level waterholing campaign 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





What happened?Who’s behind it?How did the malware spread?What did the malware do in the data center?What does the resulting watering hole look like?ConclusionsSome indicators of compromise 





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




 


A new secret stash for “fileless” malware 






 


WildPressure targets the macOS platform 






 


MontysThree: Industrial espionage with steganography and a Russian accent on both sides 






 


Microcin is here 






 


WildPressure targets industrial-related entities in the Middle East 









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



























