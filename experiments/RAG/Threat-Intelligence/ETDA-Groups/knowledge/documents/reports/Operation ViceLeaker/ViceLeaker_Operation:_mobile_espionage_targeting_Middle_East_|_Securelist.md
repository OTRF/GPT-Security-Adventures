# Reference for threat actor for "Operation ViceLeaker"

**Title**: ViceLeaker Operation: mobile espionage targeting Middle East | Securelist

**Source**: https://securelist.com/fanning-the-flames-viceleaker-operation/90877/

## Content















ViceLeaker Operation: mobile espionage targeting Middle East | Securelist




































































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

ViceLeaker Operation: mobile espionage targeting Middle East 

APT reports

26 Jun 2019

  minute read								








 

Authors




GReAT





In May 2018, we discovered a campaign targeting dozens of mobile Android devices belonging to Israeli citizens. Kaspersky spyware sensors caught the signal of an attack from the device of one of the victims; and a hash of the APK involved (Android application) was tagged in our sample feed for inspection. Once we looked into the file, we quickly found out that the inner-workings of the APK included a malicious payload, embedded in the original code of the application. This was an original spyware program, designed to exfiltrate almost all accessible information.
Spyware sensors samples feed contained the first sample
During the course of our research, we noticed that we were not the only ones to have found the operation. Researchers from Bitdefender also released an analysis of one of the samples in a blogpost. Although something had already been published, we decided to do something different with the data we acquired. The following month, we released a private report on our Threat Intelligence Portal to alert our clients about this newly discovered operation and began writing YARA rules in order to catch more samples. We decided to call the operation “ViceLeaker”, because of strings and variables in its code.
Mobile ViceLeaker
The following table shows meta information on the observed samples, including compiler timestamps:



MD5
Package
Compiler
C2


51df2597faa3fce38a4c5ae024f97b1c
com.xapps.SexGameForAdults
dexlib 2.x
188.165.28[.]251


2d108ff3a735dea1d1fdfa430f37fab2
com.psiphon3
dexlib 2.x
188.165.49[.]205


7ed754a802f0b6a1740a99683173db73
com.psiphon3
dexlib 2.x
188.165.49[.]205


3b89e5cd49c05ce6dc681589e6c368d9
ir.abed.dastan
dexlib 2.x
185.141.60[.]213



To backdoor legitimate applications, attackers used a Smali injection technique – a type of injection that allows attackers to disassemble the code of original app with the Baksmali tool, add their malicious code, and assemble it with Smali. As a result, due to such an unusual compilation process, there were signs in the dex file that point to dexlib, a library used by the Smali tool to assemble dex files.
Original code of the APK on the left, versus injected APK on the right
The analysis of the APK was rather interesting, because some of the actions were very common spyware features, such as the exfiltration of SMS messages, call logs and other data. However, in addition to the traditional functionality, there were also backdoor capabilities such as upload, download, delete files, camera takeover and record surrounding audio.
The malware uses HTTP for communication with the C2 server for command handling and data exfiltration. Here is a command and control protocol fragment:
Commands from C2 server parsing
In total, the malicious APK handles 16 different commands:



Command
Endpoint
Description


1
reqsmscal.php
Send specified SMS message


2
reqsmscal.php
Call specified number


3
reqsmscal.php
Exfiltrate device info, such as phone model and OS version


4
reqsmscal.php
Exfiltrate a list of all installed applications


5
reqsmscal.php
Exfiltrate default browser history (limited to a given date)


6
reqsmscal.php
Exfiltrate Chrome browser history (limited to a given date)


7
reqsmscal.php
Exfiltrate memory card file structure


8
reqsmscal.php
Record surrounding sound for 80 seconds


1
reqcalllog.php
Exfiltrate all call logs


2
reqcalllog.php
Exfiltrate all SMS messages


3
reqcalllog.php
Upload specified file from the device to the C2


4
reqcalllog.php
Download file from specified URL and save on device


5
reqcalllog.php
Delete specified file


6,7,8
reqcalllog.php
Commands not yet implemented


9
reqcalllog.php
Take photo (muted audio) with rear camera, send to C2


10
reqcalllog.php
Take photo (muted audio) with front camera, send to C2



All observed samples with Smali injections were signed by the same debug certificate (0x936eacbe07f201df).
As we know from our investigation, traces of the first development activities were found at the end of 2016, but the main distribution campaign began in 2018 (end of 2017).
Based on our detection statistics, the main infection vector is the spread  of Trojanized applications directly to victims via Telegram and WhatsApp messengers. There are the following relevant detection paths (the last one is an alternative Telegram client – “Telegram X“):



Name
Detection path


Sex Game For Adults 18.apk
/storage/emulated/0/WhatsApp/Media/WhatsApp Documents/


4_6032967490689041387.apk
/storage/emulated/0/Telegram/Telegram Documents/


Psiphon-v91.apk
/storage/emulated/0/Android/data/org.thunderdog.challegram/files/documents/



Backdoored Open Source
During the course of our analysis, we also found samples sharing code with the ViceLeaker malware, in particular they shared a delimiter that was used in both cases to parse commands from the C2 server.
Modified Conversations (on the right) code overlap with the Smali injections (left)
This would be a very unusual coincidence. Even when a false flag might also be a possibility, we consider this to be unlikely.
The samples sharing this overlap are modified versions of an open source Jabber/XMPP client called “Conversations” with some code additions. The legitimate version of this app is also available on Google Play.
Screenshot of Conversations app on Google Play
The Conversations modified samples differ from the original one in the getKnownHosts method that was modified to replace the main XMPP host with the attackers’ C2 server:
Comparison of the original “getKnownHosts” method (from Github) and the modified one
It appears that the attackers were using a specific C2 for the use of that app. Another important modification is in the message transfer process:
Comparison of the original Conversations method with the modified once
With this modification, an application sends device location coordinates with every message.
There are also many other modifications, fully described in our private report. In addition, we did not see traces of the Smali injection. In this case we found traces of dx/dexmerge compilers, which means that, this time, the attackers just imported the original source code into an Android IDE (such as Android Studio, for instance) and compiled it with their own modifications.
dx/dexmerge compiler of the modified Conversations samples
In addition to adding the code, the attackers also changed the icon and package name. We do not know why, but we suspect that it was an attempt to hide the origin of the application.
Conversations-based app mimics Telegram messenger
Even when we originally thought this was a backdoored version of the Conversations app, used to infect victims, we didn´t discovered anything malicious in it. This brought to us the hypothesis that this might be a version used by the group behind ViceLeaker for internal communication or for other, unclear purposes. All the detections of this backdoored app were geolocated in Iran.
Backdoored Conversations C2 server analysis
During the analysis of the Smali injected apps and their C2 server infrastructure we hadn’t found any interesting clues, but things changed when we looked at the C2 server of the linked Conversations messenger. It uses “185.51.201[.]133” as a main C2 address, and there is only one domain that is hosted on this dedicated server – iliageram[.]ir. Note that we later found versions that used the domain as a C2 directly instead of the IP address. The record contains a personal email address:
WHOIS records of C2 server exposing the attacker’s email address
We were aware of the possibility that the attackers might be using a compromised email account, so we dug deeper to find more information related to this email address. A quick search produced results about a personal page and, what is more interesting, a GitHub account that contains a forked Conversation repository.
Related Github account contains forked Conversations repository
Summarizing all the found clues, we have the following attribution flow:
 
Conclusion
The operation of ViceLeaker is still ongoing, as is our research. The attackers have taken down their communication channels and are probably looking for ways to assemble their tools in a different manner. Kaspersky detects and blocks samples of the ViceLeaker operation using the following verdict: Trojan-Spy.AndroidOS.ViceLeaker.*
Actually, we are currently investigating whether this group might also be behind a large-scale web-oriented attack at the end of 2018 using code injection and exploiting SQL vulnerabilities. Even when this would not be directly related to the Android malware described in this blogpost, it would be an indicator of wider capabilities and objectives of this actor.
For more information about the ViceLeaker operation, contact us at: intelreports@kaspersky.com






Backdoor
Code injection
Instant Messengers
Mobile Malware
Targeted attacks
Trojan
Vulnerabilities and exploits



Authors




GReAT





ViceLeaker Operation: mobile espionage targeting Middle East 
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



























