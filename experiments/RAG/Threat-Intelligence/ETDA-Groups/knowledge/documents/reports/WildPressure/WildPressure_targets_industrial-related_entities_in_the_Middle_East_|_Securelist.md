# Reference for threat actor for "WildPressure"

**Title**: WildPressure targets industrial-related entities in the Middle East | Securelist

**Source**: https://securelist.com/wildpressure-targets-industrial-in-the-middle-east/96360/

## Content















WildPressure targets industrial-related entities in the Middle East | Securelist


































































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

WildPressure targets industrial-related entities in the Middle East 

APT reports

24 Mar 2020

  minute read								








 

Authors



 Denis Legezo





In August 2019, Kaspersky discovered a malicious campaign distributing a fully fledged C++ Trojan that we call Milum. All the victims we registered were organizations from the Middle East. At least some of them are related to industrial sector. Our Kaspersky Threat Attribution Engine (KTAE) doesn’t show any code similarities with known campaigns. Nor have we seen any target intersections. In fact, we found just three almost unique samples, all in one country. So we consider the attacks to be targeted and have currently named this operation WildPressure.
The compilation timestamps for all these files is the same – March 2019. This is consistent with the fact that we registered no infections before May 31, 2019, so the compilation dates don’t seem to be spoofed. For their campaign infrastructure, the operators used rented OVH and Netzbetrieb virtual private servers (VPS) and a domain registered with the Domains by Proxy anonymization service.
The malware uses the JSON format for configuration data and as a C2 communication protocol over HTTP as well. Inside the encrypted communications within the HTTP POST requests, we found several interesting fields. One of them shows the malware version – 1.0.1. A version number like this indicates an early stage of development. Other fields suggest the existence of, at the very least, plans for non-C++ versions.
The only encryption implemented is the RC4 algorithm with different 64-byte keys for different victims. Also, the developers were kind enough to leave RTTI data inside the files. Kaspersky products detect this malware as Backdoor.Win32.Agent. For more information, please contact: intelreports@kaspersky.com

Why we call it Milum and why it’s of interest
All the aforementioned C++ Trojans are compiled as standalone PE files, originally named Milum46_Win32.exe. The word ‘milum’ is used in the C++ class names inside the malware, so we named the Trojan after it.
Another distinctive characteristic is that the malware exports lots of zlib compression functions, such as zlibVersion(), inflate() or deflate(). This compression is needed for C2 communication, but in reality there is no need to export them in the case of a standalone application.
The JSON configuration fields are not limited to just the version and programming language; the campaign operators also use target IDs that are found in the samples. Among them, we found HatLandM30 and HatLandid3 – neither of which we are familiar with. The following table provides Milum samples that have similar PE header compilation timestamps but different target IDs:



Milum46_Win32.exe sample MD5 hash
Timestamp (GMT)
clientid


0C5B15D89FDA9BAF446B286C6F97F535
2019.03.09 06:17:19
839ttttttt


17B1A05FC367E52AADA7BDE07714666B
2019.03.09 06:17:19
HatLandid3


A76991F15D6B4F43FBA419ECA1A8E741
2019.03.09 06:17:19
HatLandM30



Rather than describing all the configuration fields one by one, we have gathered them together in the following table, with all the main characteristics for this malware family:




Programming language
C++ with STL functions used mostly to parse JSON data and exception handling.


Configuration data
Base64-encoded JSON data in PE resources. Includes timeouts, C2 URLs and keys for communication, including RC4 64-byte key.


Network protocol
Trojan transmits compressed JSON data in HTTP POST requests with gzip, base64-encoded and RC4 encrypted.


Beacon data
Encrypted JSON contains the malware version “1.0.1”, Epoch timestamp and client id. It also has specific fields such as “vt” and “ext” that correspond to programming language “c++” and file extension “exe”. If our hypothesis is correct, this suggests that non-C++ Trojan versions may be planned, if not already implemented.


Persistence
HKCU autorun system registry keys Run and RunOnce.


Encryption
The communication encryption used is RC4 with the 64-byte key stored in the configuration data.


Compression
For compression the Trojan uses an embedded gzip code. For some reason gzip functions are exported from PE, although the samples are standalone executables, not DLLs.




Let’s dig a little deeper inside
The most popular sample in our telemetry was:




MD5
0c5b15d89fda9baf446b286c6f97f535


Compiled
2019.03.09 06:17:19 (GMT)


Size
520704


Internal name
Milum46_Win32.exe


This application exists as an invisible toolbar window. The main malicious functions are implemented in a separate thread. Milum decodes its configuration data and, besides timeouts, it gets the parameters “clientid” and “encrypt_key” to use in RC4 encryption.

Example of the decoded and beautified configuration data. The “clientid” field differs in every sample observed
The following table describes the different configuration parameters:



Config parameter
Parameter features


shortwait
Pause in milliseconds between C2 communication working cycles


clientid
Unique ASCII target name


encrypt_key
RC4 encryption key for JSON-based C2 communications


relays – url
Full URL to send HTTP POST beacon and GET commands


relays – key
Unique ASCII key for each C2 to communicate with it



The operators can run the Trojan using the key (“b” or “B”) as the first argument and the file name as the second. In this case, Milum will delete the file sent as a parameter. Then the Trojan will create the C:\ProgramData\Micapp\Windows\ directory and parse its configuration data to form the beacon to send to its C2.
To send the beacon, Milum uses the HTTP POST request with three parameters as enumerated in the table below.



Beacon parameter
Parameter values


md
Clientid from config, with prefix 01011 and random five-character ASCII suffix


nk
Key from config to communicate with C2, differs for each server


val
Compressed, encrypted and encoded command JSON data



The first two parameters are taken from the configuration data. The third one is encrypted and after decryption, decompression, decoding and beautifying, it looks like this:

Decoded and beautified JSON beacon to C2. In this case, the connection to the first server was unsuccessful
There are several fields worth mentioning here. We referred above to different programming languages besides C++: “vt” seems to reference a programming language and “ext” a file extension. The only reason that we could think of for keeping these is if the attackers have several Trojans, written in different languages, to work with the same control server.
Regarding the “command” field, the control servers were inaccessible at the time of the analysis, so we don’t have commands from them. However, we analyzed the command handlers in Milum’s code as described below:



Code
Meaning
Features


1
Execution
Silently execute received interpreter command and return result through pipe


2
Server to client
Decode received content in “data” JSON field and drop to file mentioned in “path” field


3
Client to server
Encode file mentioned in received command “path” field to send it


4
File info
Get file attributes: hidden, read only, archive, system or executable


5
Cleanup
Generate and run batch script to delete itself


6
Command result
Get command execution status


7
System information
Validate target with Windows version, architecture (32- or 64-bit), host and user name, installed security products (with WQL request “Select From AntiVirusProduct WHERE displayName <>’Windows Defender'”)


8
Directory list
Get info about files in directory: hidden, read only, archive, system or executable


9
Update
Get the new version and remove the old one




Who was attacked?
According to our telemetry, the Milum Trojan was exclusively used to attack targets in the Middle East from at least the end of May 2019.

Number of detections for one of the samples from September 2019
We were able to sinkhole one of the WildPressure C2 domains (upiserversys1212[.]com) in September 2019. The vast majority of visitor IPs were also from the Middle East, and we believe the rest were network scanners, TOR exit nodes or VPN connections.

C2 domain sinkholing also shows active infections mostly from the Middle East

And who’s behind it?
To date we haven’t observed any strong code- or victim-based similarities with any known actor or set of activity. Their C++ code is quite common, regarding configuration data and communication protocol malware uses base64-encoded JSON-formatted configuration data stored in the binary’s resource section and parses it with Standard Template Library (STL) functions. However, these commonalities are not conclusive enough for attribution and our hypothesis is that they are merely coincidence. We will continue to monitor this activity
To sum up
To date, we don’t have any data regarding Milum’s spreading mechanism. A campaign that is, apparently, exclusively targeting entities in the Middle East (at least some of them are industrial-related) is something that automatically attracts the attention of any analyst. Any similarities should be considered weak in terms of attribution, and may simply be techniques copied from previous well-known cases. Indeed, this “learning from more experienced attackers” cycle has been adopted by some interesting new actors in recent years.
We should also be cautious regarding the true targeting of this new set of activities, as it is probably too soon to jump to conclusions. The targeted nature seems to be clear, but the targeting itself might be limited by our own visibility. The malware is not exclusively designed against any kind of victim in particular and might be reused in other operations.
Indicators of compromise
Files MD5
0C5B15D89FDA9BAF446B286C6F97F535
17B1A05FC367E52AADA7BDE07714666B
A76991F15D6B4F43FBA419ECA1A8E741
Original file names are Milum46_Win32.exe; on the target side they exist as system32.exe
URLs
upiserversys1212[.]com/rl.php
37.59.87[.]172/page/view.php
80.255.3[.]86/page/view.php






Encryption
Industrial threats
Malware Descriptions
Sinkholing
Targeted attacks
Trojan



Authors



 Denis Legezo





WildPressure targets industrial-related entities in the Middle East 
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




 


A new secret stash for “fileless” malware 






 


WildPressure targets the macOS platform 






 


MontysThree: Industrial espionage with steganography and a Russian accent on both sides 






 


Microcin is here 






 


Chafer used Remexi malware to spy on Iran-based foreign diplomatic entities 









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



























