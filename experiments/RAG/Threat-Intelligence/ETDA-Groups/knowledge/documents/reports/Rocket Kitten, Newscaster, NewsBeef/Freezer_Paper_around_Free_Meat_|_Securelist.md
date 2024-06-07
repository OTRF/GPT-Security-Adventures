# Reference for threat actor for "Rocket Kitten, Newscaster, NewsBeef"

**Title**: Freezer Paper around Free Meat | Securelist

**Source**: https://securelist.com/freezer-paper-around-free-meat/74503/

## Content















Freezer Paper around Free Meat | Securelist


































































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

Freezer Paper around Free Meat 

APT reports

27 Apr 2016

  minute read								








 

Authors




GReAT



Repackaging Open Source BeEF for Tracking and More


BeEF Wrapped Up and Delivered in 2016
In late February 2016, a University website in Iran stood out for thoroughly vetting its current and potential students and staff. The University’s web site served repackaged content from the Browser Exploitation Framework (BeEF) with embedded JavaScript content maintaining the potential to hook visitors’ web browsers, identify visited websites and domains, explore for vulnerabilities (we did not observe any auto-pwning), and provide tracking through evercookies. Even a partial listing of visited sites can be sensitive and valuable information, and this sort of “sites visited” data gathering via other techniques, like screengrabbing and keylogging, were observed in past APT incidents like the Madi campaigns. Currently, it’s advisable to avoid the site.

The embedded BeEF content appears not to be fully configured, and only partially implemented. Perhaps a limited data set was of interest for this attacker, or this was an early attempt at deploying BeEF.
This incident is interesting because at the same time and a bit earlier, another group was heavily relying on repackaging open source offensive security product in their toolset by deploying both BeEF and Metasploit-produced components across a select set of strategic web compromises. This particular APT has years of low-tech elaborate social engineering schemes and re-purposed open source efforts under its belt.

While we call them the NewsBeef APT, they have been reported in the past as Charming Kitten or Newscaster in 2014, social engineering their way into sensitive circles of trust with spoofed LinkedIn profiles and phony news media organizations.
They continue to be highly active, but this time, they are using a slightly more technical toolset. On one hand, they have developed skills or discovered tools to compromise select web applications and sites, supporting their watering hole campaigns. On the other hand, they have repackaged leaked bot source code and repackaged open source Metasploit and PowerSploit components to produce and administer backdoors and downloaders.
Newsbeef/Newscaster will find a way to compromise a web site, usually the vulnerability appears to be CMS related, in an outdated WordPress plugin, Joomla version, or Drupal version. Attackers usually perform one of two things, Newsbeef has been performing the first of the two:

inject a src or iframe link into web pages or css sheets
inject the content of an entire BeEF web page into one of the internally linked javascript helpers

The injected link will redirect visitors’ browsers to a BeEF server. Usually, the attackers deliver some of the tracking and system/browser identification and evercookie capabilities. Sometimes, it appears that they deliver the metasploit integration to exploit and deliver backdoors (we haven’t identified that exploitation activity in our ksn data related to this group just yet). Sometimes, it is used to pop up spoofed login input fields to steal social networking site credentials. We also haven’t detected that in ksn, but some partners have privately reported it about various incidents. But we have identified that attackers will redirect specific targets to laced Adobe Flash and other installers from websites that they operate.
So, the watering hole activity isn’t always and usually isn’t delivering backdoors. Most of the time, the watering hole injections are used to identify and track visitors or steal their browser history. Then, they deliver the backdoors to the right targets.
In addition to the University site and the NewsBeef APT, in the past couple of months, we identified a variety of compromised sites around the world serving the BeEF. Most are cleaned up. Deployments to interesting and strategic web sites and their true reach on a global scale appears to be on the increase:

Middle eastern embassy in the Russian Federation
Indian military technology school
High conflict regional presidency
Ukrainian ICS Scanner mirror
European Union education diversification support agency
Russian foreign trade management organization
Progressive Kazakh news and politics media
Turkish news organization
Specialized German music school
Japanese textile manufacturing inspection corporate division
Middle Eastern social responsibility and philanthropy
surprisingly popular British “lifestyle” blog
Algerian University’s online course platform
Chinese construction group
Russian overseas business development and holding company
Russian gaming developer forum
Romanian Steam gaming developer
Chinese online gaming virtual gold seller
Brazilian music instrument retailer

 
BeEF Capabilities
Key to these incidents are the development, distribution, and ease of use of toolkits like BeEF.

BeEF itself is an open source collection of tools and tricks, some years old, that combined together can effectively hook a visiting web browser for evaluation and full exploitation. Because of its capabilities, we have seen increased adoption of the framework for the past year or so.

Browser enumeration and reporting
Plugin enumeration and reporting
Retrieve visited domains (based on an old browser cache fetch timing trick)
Social engineering via live sessions and phishing within the browser
Network exploration, discovery, and exfiltration tunneling
Metasploit exploit integration and autopwning
Evercookie deployment for persistent tracking – multiple platforms
XSS evaluation and exploitation

At the same time, many of the techniques implemented are very old and public. The kit is extensible, customizable, and integrates with metasploit for autopwnage. Some of the techniques were discussed during Jeremiah Grossman’s 2006 Black Hat conference presentation. The delay in deployment for techniques of this type indicates that some teams are dependent on open source tool packaging and ease of use. We have seen this sort of reliance on both open source offensive toolkits and legitimate software in the past from APT like Crouching Yeti, TeamSpy, and now the Newsbeef.
Fighting against the use of browser hooking frameworks for identification, tracking, live session social engineering, and precision and auto-exploitation effectively requires a mix of technologies. When these JavaScript-based frameworks are used in a malicious manner, the combination of network and host based detection is required to fully handle more serious incidents.
Unfortunately, these incidents are on the increase. You can disable JavaScript in your own browser with NoScript, but that’s much like just moving to Lynx or a text-based browser – people don’t want that because it kills functionality in the browser they do want. A Chrome plugin that detects the BeEF cookie is easily evaded by serious players. And preventing the tracking methods altogether is another whole ball of wax, because much of the functionality is tied into legitimate web pages by third party marketers and retailers.
Preventing the social engineering sessions for credential theft and Metasploit exploit integration makes immediate sense and can be incorporated at the network and more effectively at the host level. AntiAPT can help wipe out most of an operation on the network at scale, but these measures can be evaded as well. In other words, dealing with a determined attacker using tools like this one is difficult.
References
NEWSCASTER – An Iranian Threat Inside Social Media
The Browser Exploitation Framework Project
Metasploit: Penetration Testing Software







APT
Cyber espionage
Cybercrime
Targeted attacks
Vulnerabilities and exploits
Website Hacks



Authors




GReAT





Freezer Paper around Free Meat 
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



























