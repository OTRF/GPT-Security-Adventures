# Reference for threat actor for "Desert Falcons"

**Title**: Breaking The Weakest Link Of The Strongest Chain | Securelist

**Source**: https://securelist.com/breaking-the-weakest-link-of-the-strongest-chain/77562/

## Content















Breaking The Weakest Link Of The Strongest Chain | Securelist


































































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

Breaking The Weakest Link Of The Strongest Chain 

APT reports

16 Feb 2017

  minute read								
















Table of Contents





Attack FlowSocial EngineeringDropperKey featuresNetwork ProtocolsPayloadC&C CommandsScheduled ProcessConclusionsIOCsDomain names & APK hashesCertificates – SHA1 fingerprints 






 

Authors




IDF C4I




Ido Naor





Around July last year, more than a 100 Israeli servicemen were hit by a cunning threat actor. The attack compromised their devices and exfiltrated data to the attackers’ command and control server. In addition, the compromised devices were pushed Trojan updates, which allowed the attackers to extend their capabilities. The operation remains active at the time of writing this post, with attacks reported as recently as February 2017.
The campaign, which experts believe is still in its early stages, targets Android OS devices. Once the device is compromised, a process of sophisticated intelligence gathering starts, exploiting the ability to access the phone’s video and audio capabilities, SMS functions and location.
The campaign relies heavily on social engineering techniques, leveraging social networks to lure targeted soldiers into both sharing confidential information and downloading the malicious applications.
Characterized by relatively unsophisticated technical merit, and extensive use of social engineering, the threat actor targets only IDF soldiers.
IDF C4I & the IDF Information Security Department unit, with Kaspersky Lab researchers, have obtained a list of the victims; among them IDF servicemen of different ranks, most of them serving around the Gaza strip.
Attack Flow
The operation follows the same infection flow across the different victims:

Figure 1: Campaign’s attack flow
Social Engineering
The threat actor uses social engineering to lure targets into installing a malicious application, while continuously attempting to acquire confidential information using social networks. We’ve seen a lot of the group’s activity on Facebook Messenger. Most of the avatars (virtual participants in the social engineering stage) lure the victims using sexual innuendo, e.g. asking the victim to send explicit photos, and in return sending fake photos of teenage girls. The avatars pretend to be from different countries such as Canada, Germany, Switzerland and more.
Dropper
After the victim downloads the APK file from the malicious URL, the attacker expects the victim to install the package manually. The dropper requires common user permissions as shown in the following screenshot.

Figure 2: Dropper permissions once installed on a victim mobile device
Key features
The dropper relies on the configuration server which uses queries in order to download the best fitting payload for the specified device.

Downloader & Watchdog of the main payload
Payload update mechanism
Customized payload – the dropper sends a list of installed apps, and receives a payload package based on it
Obfuscation – The dropper package is obfuscated using ProGuard, which is an open source code obfuscator and Java optimizer, observed in the LoveSongs dropper.

Network Protocols
The network protocol between the dropper and the configuration server is based on HTTP POST requests. The following servers implement a RESTful API:
LoveSongs – http://endpointup[.]com/update/upfolder/updatefun.php
YeeCall, WowoMessanger – http://droidback[.]com/pockemon/squirtle/functions.php

Figure 3: Communication with C&C server over HTTP
Most of the communication with the server is in clear-text, except for specific commands which are encrypted using an AES-128 hard coded-key.

Figure 4: WowoMessanger REST-API POST packet capture

Figure 5: Fake WowoMessanger app – logic flow
Along with an ID existence check, the dropper sends a list of the device’s installed apps – if it hasn’t done so already.
The flow between different variants of the dropper is similar, with minor changes. One variant pretends to be a YouTube player, while others are chat apps:
LoveSongs has YouTube player functionality, whereas WowoMessanger does not have any legitimate functionality whatsoever; it erases its icon after the first run.
Payload
The payload is installed after one of the droppers mentioned above has been downloaded and executed on the victim device. The only payload we have seen so far is “WhatsApp_Update”.
The payload is capable of two collection mechanisms:

Execute “On demand” commands – manual commands that are triggered by the operator
Scheduled process – scheduled tasks that collect information periodically from various sources.

Most of the collected data will be sent only when a WI-FI network is available.
C&C Commands
The payload uses the WebSocket protocol, which gives the attacker a real-time interface to send commands to the payload in a way that resembles ‘reverse shell’. Some of the commands are not yet implemented (as shown in the table below). The commands gives the operator basic yet dangerous RAT capabilities:

Collect general information about the device e.g. Network operator, GPS location, IMEI etc.
Open a browser and browse to a chosen URL
Read & send SMS messages, and access contacts
Eavesdrop at a specific time and period
Take pictures (using the camera) or screenshots
Record video and audio.





COLL_AUDIO_RECORDS
COLL_CALL_RECORDS
GET_LOCATION
CHECK_AVAILABILITY


OPEN_WEBPAGE
GET_IMAGE
GET_DEVICE_INFO
COLL_CAPTURED_PHOTOS


GET_TELEPHONY_INFO
GET_CELLS_INFO
TAKE_SCREENSHOT
CALL_PHONE


GET_SEC_GALL_CACHE
GET_SMS
SEND_SMS
GET_CONTACTS


GET_BOOKMARKS
TAKE_BACK_PIC
CHANGE_AUDIO_SOURCE
RECORD_AUDIO


GET_SEARCHES
CLOSE_APP
GET_HISTORY
OPEN_APP


GET_CALENDER_EVENTS
RESTART
GET_USER_DICTIONARY
SHUTDOWN


UNINSTALL_APP
GET_ACCOUNTS
INSTALL_APK
GET_INSTALLED_APPS


GET_WHATSAPP_KEY
RECORD_FRONT_VIDEO
GET_WHATSAPP_BACKUP
GET_FILE


GET_CALLS
GET_ROOT_STATUS
TAKE_FRONT_PIC
RECORD_BACK_VIDEO




INVALID_COMMAND
REMOVE_FILE




*Commands which were implemented are in bold.
Scheduled Process
Besides the C&C commands, the payload periodically collects data using various Android APIs. The default time interval is 30 seconds. The process collects the following data:

General data about the device (as mentioned in the C&C command)
SMS messages, WhatsApp database along with the encryption key (requires root permissions which is not yet fully implemented)
Browsing & search history along with bookmarks
Documents and archives ( < 2MB ) found in storage (doc, docx, ppt, rar, etc)
Pictures taken, auto captures while on an active call
List of contacts and call logs
Records calls and eavesdrops
Updates itself

The attackers implemented all of the malicious logic without any native or third-party sources. The logic behind the automatic call-recording feature is implemented entirely using Android’s API.

Figure 6: Call-Recording implementation in WhatsApp_update
Conclusions
The IDF, which led the research along with Kaspersky Lab researchers, has concluded that this is only the opening shot of this operation. Further, that it is by definition a targeted attack against the Israeli Defense Force, aiming to exfiltrate data on how ground forces are spread, which tactics and equipment the IDF is using and real-time intelligence gathering.
Kaspersky Lab GReAT researchers will disclose more behind-the-scenes details of the operation at the upcoming Security Analyst Summit.
IOCs
Domain names & APK hashes
androidbak[.]com
droidback[.]com
endpointup[.]com
siteanalysto[.]com
goodydaddy[.]com
10f27d243adb082ce0f842c7a4a3784b01f7248e
b8237782486a26d5397b75eeea7354a777bff63a
09c3af7b0a6957d5c7c80f67ab3b9cd8bef88813
9b923303f580c999f0fdc25cad600dd3550fe4e0
0b58c883efe44ff010f1703db00c9ff4645b59df
0a5dc47b06de545d8236d70efee801ca573115e7
782a0e5208c3d9e8942b928857a24183655e7470
5f71a8a50964dae688404ce8b3fbd83d6e36e5cd
03b404c8f4ead4aa3970b26eeeb268c594b1bb47
Certificates – SHA1 fingerprints
10:EB:7D:03:2A:B9:15:32:8F:BF:68:37:C6:07:45:FB:DF:F1:87:A6
9E:52:71:F3:D2:1D:C3:22:28:CB:50:C7:33:05:E3:DE:01:EB:CB:03
44:52:E6:4C:97:4B:6D:6A:7C:40:AD:1E:E0:17:08:33:87:AA:09:09
67:43:9B:EE:39:81:F3:5E:10:33:C9:7A:D9:4F:3A:73:3B:B0:CF:0A
89:C8:E2:E3:4A:23:3C:A0:54:A0:4A:53:D6:56:C8:2D:4A:8D:80:56
B4:D5:0C:8B:73:CB:A9:06:8A:B3:F2:49:35:F8:58:FE:A2:3E:2E:3A






Mobile security
Obfuscation
Social engineering
Targeted attacks
Trojan



Authors




IDF C4I




Ido Naor





Breaking The Weakest Link Of The Strongest Chain 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





Attack FlowSocial EngineeringDropperKey featuresNetwork ProtocolsPayloadC&C CommandsScheduled ProcessConclusionsIOCsDomain names & APK hashesCertificates – SHA1 fingerprints 





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




 


Gas is too expensive? Let’s make it cheap! 






 


One-stop-shop: Server steals data then offers it for sale 






 


CryPy: ransomware behind Israeli lines 






 


Facebook malware – the missing piece 






 


Facebook malware: tag me if you can 









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



























