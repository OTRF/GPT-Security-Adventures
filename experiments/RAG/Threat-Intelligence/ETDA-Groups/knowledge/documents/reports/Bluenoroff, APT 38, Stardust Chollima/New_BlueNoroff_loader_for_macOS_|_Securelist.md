# Reference for threat actor for "Bluenoroff, APT 38, Stardust Chollima"

**Title**: New BlueNoroff loader for macOS | Securelist

**Source**: https://securelist.com/bluenoroff-new-macos-malware/111290/

## Content















New BlueNoroff loader for macOS | Securelist



































































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

BlueNoroff: new Trojan attacking macOS users 

Malware descriptions

05 Dec 2023

  minute read								








 

Authors




Sergey Puzan





We recently discovered a new variety of malicious loader that targets macOS, presumably linked to the BlueNoroff APT gang and its ongoing campaign known as RustBucket. The threat actor is known to attack financial organizations, particularly companies, whose activity is in any way related to cryptocurrency, as well as individuals who hold crypto assets or take an interest in the subject. Information about the new loader variant first appeared in an X (formerly Twitter) post.
Original X (formerly Twitter) post about the new loader
Earlier RustBucket versions spread its malicious payload via an app disguised as a PDF viewer. By contrast, this new variety was found inside a ZIP archive that contained a PDF file named, “Crypto-assets and their risks for financial stability”, with a thumbnail that showed a corresponding title page. The metadata preserved inside the ZIP archive suggests the app was created on October 21, 2023.
App structure
Document thumbnail
Exactly how the archive spread is unknown. The cybercriminals might have emailed it to targets as they did with past campaigns.
The app had a valid signature when it was discovered, but the certificate has since been revoked.





Signature #1: Valid
    Chain   #1:
      Verified:           True
      Serial:               6210670360873047962
      Issuer:              CN=Developer ID Certification Authority,OU=Apple Certification Authority,O=Apple Inc.,C=US
      Validity:            from = 20.10.2023 3:11:55
                                 to = 01.02.2027 22:12:15
      Subject:            UID=2C4CB2P247,CN=Developer ID Application: Northwest Tech-Con Systems Ltd (2C4CB2P247),OU=2C4CB2P247,O=Northwest Tech-Con Systems Ltd,C=CA
      SHA-1 Fingerprint:   da96876f9535e3946aff3875c5e5c05e48ecb49c

      Verified:          True
      Serial:              1763908746353189132
      Issuer:             C=US,O=Apple Inc.,OU=Apple Certification Authority,CN=Apple Root CA
      Validity:            from = 01.02.2012 22:12:15
                                 to = 01.02.2027 22:12:15
      Subject:             CN=Developer ID Certification Authority,OU=Apple Certification Authority,O=Apple Inc.,C=US
      SHA-1 Fingerprint:   3b166c3b7dc4b751c9fe2afab9135641e388e186

      Verified:            True (self-signed)
      Serial:                2
      Issuer:               C=US,O=Apple Inc.,OU=Apple Certification Authority,CN=Apple Root CA
      Validity:            from = 25.04.2006 21:40:36
                                 to = 09.02.2035 21:40:36
      Subject:             C=US,O=Apple Inc.,OU=Apple Certification Authority,CN=Apple Root CA
      SHA-1 Fingerprint:   611e5b662c593a08ff58d14ae22452d198df6c60




12345678910111213141516171819202122232425

Signature #1: Valid    Chain   #1:      Verified:           True      Serial:               6210670360873047962      Issuer:              CN=Developer ID Certification Authority,OU=Apple Certification Authority,O=Apple Inc.,C=US      Validity:            from = 20.10.2023 3:11:55                                 to = 01.02.2027 22:12:15      Subject:            UID=2C4CB2P247,CN=Developer ID Application: Northwest Tech-Con Systems Ltd (2C4CB2P247),OU=2C4CB2P247,O=Northwest Tech-Con Systems Ltd,C=CA      SHA-1 Fingerprint:   da96876f9535e3946aff3875c5e5c05e48ecb49c       Verified:          True      Serial:              1763908746353189132      Issuer:             C=US,O=Apple Inc.,OU=Apple Certification Authority,CN=Apple Root CA      Validity:            from = 01.02.2012 22:12:15                                 to = 01.02.2027 22:12:15      Subject:             CN=Developer ID Certification Authority,OU=Apple Certification Authority,O=Apple Inc.,C=US      SHA-1 Fingerprint:   3b166c3b7dc4b751c9fe2afab9135641e388e186       Verified:            True (self-signed)      Serial:                2      Issuer:               C=US,O=Apple Inc.,OU=Apple Certification Authority,CN=Apple Root CA      Validity:            from = 25.04.2006 21:40:36                                 to = 09.02.2035 21:40:36      Subject:             C=US,O=Apple Inc.,OU=Apple Certification Authority,CN=Apple Root CA      SHA-1 Fingerprint:   611e5b662c593a08ff58d14ae22452d198df6c60




App signature details
Written in Swift and named “EdoneViewer”, the executable is a universal format file that contains versions for both Intel and Apple Silicon chips. Decryption of the XOR-encrypted payload is handled by the main function, CalculateExtameGCD. While the decryption process is running, the app puts out unrelated messages to the terminal to try and lull the analyst’s vigilance.
The decrypted payload has the AppleScript format:
AppleScript code executed after the payload is deciphered
The script assembles and runs the following shell command:
Shell command
Once assembled, the shell command goes through the following steps:

Downloads a PDF file, save it at /Users/Shared/Crypto-assets and their risks for financial stability.pdf, and opens it. This is a benign file launched as a diversion.
Title page of the PDF decoy
Sends a POST request to the server and saves the response to a hidden file named “.pw” and located at /Users/Shared/.
Grants permissions to the file and executes it with the C&C address as an argument.

The C&C server is hosted at hxxp://on-global[.]xyz, a domain name registered fairly recently, on October 20, 2023. We were unable to find any links between the domain and any other files or threats.
The .pw file is a Trojan we detected back in August. Like the loader, this is a universal format file:
Details of the .pw file
The file collects and sends the following system information to the C&C:

Computer name
OS version
Time zone
Device startup date
OS installation date
Current time
List of running processes

The data is collected and forwarded in cycles every minute. The Trojan expects one of the following three commands in response:



Command #
Description


0x0
Save response to file and run


0x1
Delete local copy and shut down


Any other number
Keep waiting for command



After receiving a 0x0 command, the program saves data sent with the command to the shared file named “.pld” and located at /Users/Shared/, gives it the read/write/run permissions and executes it:
Code snippet that writes and runs the downloaded file
Unfortunately, we did not receive a single command from the server during our analysis, so we were unable to find out the content of the following attack stage. The Trojan can now be detected by most anti-malware solutions:
Details of the second download as posted on VirusTotal
Indicators of compromise
Files



MD5 hash
File format
File name


1fddf14984c6b57358401a4587e7b950
Mach-O Fat
EdoneViewer


d8011dcca570689d72064b156647fa82
Mach-O Fat
.pw


90385d612877e9d360196770d73d22d6
Zip
Crypto-assets and their risks for financial stability.zip


3b3b3b9f7c71fcd7239abe90c97751c0
Zip
Crypto-assets and their risks for financial stability.zip


b1e01ae0006f449781a05f4704546b34
Zip
Crypto-assets and their risks for financial stability.zip


80c1256f8bb2a9572e20dd480ac68759
PDF
Crypto-assets and their risks for financial stability.pdf



Links



URL
Description


hxxp://on-global[.]xyz/Ov56cYsfVV8/OJITWH2WFx/Jy5S7hSx0K/fP7saoiPBc/A==
PDF file URL


hxxp://on-global[.]xyz/Of56cYsfVV8/OJITWH2WFx/Jy5S7hSx0K/fP7saoiPBc/A==
Trojan URL









Apple MacOS
BlueNoroff
Malware
Malware Descriptions
Malware Technologies
Trojan



Authors




Sergey Puzan





BlueNoroff: new Trojan attacking macOS users 
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




 


Cracked software beats gold: new macOS backdoor stealing cryptowallets 






 


New macOS Trojan-Proxy piggybacking on cracked software 









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






 


Ducktail fashion week 






 


WhatsApp spy mod spreads through Telegram, attacks Arabic-speaking users 






 















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



























