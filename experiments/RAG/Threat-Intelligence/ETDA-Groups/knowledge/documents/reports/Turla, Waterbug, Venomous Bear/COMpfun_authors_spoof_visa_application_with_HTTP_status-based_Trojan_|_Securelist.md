# Reference for threat actor for "Turla, Waterbug, Venomous Bear"

**Title**: COMpfun authors spoof visa application with HTTP status-based Trojan | Securelist

**Source**: https://securelist.com/compfun-http-status-based-trojan/96874/

## Content















COMpfun authors spoof visa application with HTTP status-based Trojan | Securelist


































































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

COMpfun authors spoof visa application with HTTP status-based Trojan 

APT reports

14 May 2020

  minute read								








 

Authors




GReAT





You may remember that in autumn 2019 we published a story about how a COMpfun successor known as Reductor infected files on the fly to compromise TLS traffic. If you’re wondering whether the actor behind the malware is still developing new features, the answer is yes. Later in November 2019 our Attribution Engine revealed a new Trojan with strong code similarities. Further research showed that it was obviously using the same code base as COMPFun.
What’s of interest inside
The campaign operators retained their focus on diplomatic entities, this time in Europe, and spread the initial dropper as a spoofed visa application. It is not clear to us exactly how the malicious code is being delivered to a target. The legitimate application was kept encrypted inside the dropper, along with the 32- and 64-bit next stage malware.

Overall infection chain. Interestingly, C2 commands are rare HTTP status codes
We observed an interesting C2 communication protocol utilizing rare HTTP/HTTPS status codes (check IETF RFC 7231, 6585, 4918). Several HTTP status codes (422-429) from the Client Error class let the Trojan know what the operators want to do. After the control server sends the status “Payment Required” (402), all these previously received commands are executed.
The authors keep the RSA public key and unique HTTP ETag in encrypted configuration data. Created for web content caching reasons, this marker could also be used to filter unwanted requests to the C2, e.g., those that are from network scanners rather than targets. Besides the aforementioned RSA public key to communicate with the C2, the malware also uses a self-generated AES-128 key.
Who is the author?
We should mention here once again that the COMPfun malware was initially documented by G-DATA in 2014; and although the company did not identify which APT was using the malware. Based mostly on victimology, we were able to associate it with the Turla APT with medium-to-low level of confidence.
What the Trojan is able to do
Its functions include the ability to acquire the target’s geolocation, gathering host- and network-related data, keylogging and screenshots. In other words, it’s a normal full-fledged Trojan that is also capable of propagating itself to removable devices.
As in previous malware from the same authors, all the necessary function addresses resolve dynamically to complicate analysis. To exfiltrate the target’s data to the C2 over HTTP/HTTPS, the malware uses RSA encryption. To hide data locally, the Trojan implements LZNT1 compression and one-byte XOR encryption.



Encrypted data
Algorithm
Key source


Exfiltrated keystrokes, screenshots, etc.
RSA
Public key from configuration data


Configuration data in .rsrc section
XOR (plus LZNT1 compression)
Hardcoded one-byte key


Parameters inside the HTTP GET/POST requests
AES-128 (plus ETag from config)
Generated by Trojan and shared in beacon


Commands and arguments from C2 for HTTP status 427 (dir, upl, usb, net)
AES-128
Generated by Trojan and shared in beacon



Encryption and compression used by the Trojan for various tasks
Initial dropper
The first stage dropper was downloaded from the LAN shared directory. The file name related to the visa application process perfectly corresponds with the targeted diplomatic entities. As with all modules with a similar code base, the dropper begins by dynamically resolving all the required Windows API function addresses and puts them into structures. It then decrypts the next stage malware from its resource (.rsrc) section. The algorithm used to decrypt the next stage is a one-byte XOR using the key “0x55”, followed by LZNT1 decompression.
The following files are dropped to the disk in addition to the original application that the malware tries to mimic:



MD5 hash
File name
Features


1BB03CBAD293CA9EE3DDCE6F054FC325
ieframe.dll.mui
64-bit Trojan version


A6AFA05CBD04E9AF256D278E5B5AD050
ExplorerFrame.dll.mui
32-bit Trojan version



The dropper urges users to run the file as administrator (using messages such as “need to run as admin”), then drops a version corresponding to the host’s architecture and sets the file system timestamp to 2013.12.20 22:31.
Interestingly, the dropper’s abilities aren’t limited to PE lures; as an alternative, this stage is also able to use .doc and .pdf files. In such cases, the dropper will open the files using the “open” shell command instead of running the legitimate spoofed executable application.
Main module – HTTP status-based Trojan





SHA256
710b0fafe5fd7b3d817cf5c22002e46e2a22470cf3894eb619f805d43759b5a3


MD5
a6afa05cbd04e9af256d278e5b5ad050


Compiled
2015.06.26 09:42:27 (GMT)


Type
I386 Windows GUI DLL


Size
593408


Internal name 
ExplorerFrame.dll.mui



The analysis below is based on the 32-bit sample from the table above. The legitimate ExplorerFrame.dll.mui is a language resource for the ExplorerFrame.dll file used by Windows Explorer.

Multi-threaded Trojan features such as monitoring USB devices to spread further and receiving commands as HTTP status codes
Initialization
As usual in this malware family’s code, a huge number of short standalone functions return all the readable strings. This is done to complicate analysis by not allowing the strings to be visible at a glance for researchers. The module’s preparation stage dynamically resolves all required Windows API function addresses into corresponding custom structures. Afterwards the malware uses indirect function calls only.
The module obtains the processor architecture (32- or 64-bit) and Windows OS version. It includes a number of anti-analysis checks for virtual machine-related devices (VEN_VMWARE, VBOX_HARDDISK, Virtual_DVD_ROM, etc.) to avoid controlled execution. It also notes which security products are running on the host (Symantec, Kaspersky, Dr.Web, Avast).
Before every communication with the C2, the malware checks if software such as debuggers (WinDbg, OllyDbg, Visual Studio) and host (Process Explorer or Monitor, etc.) or network monitoring (Wireshark, TCPView, etc.) programs are running. It also checks for internet connectivity and does not attempt to communicate if the checks fail.
The DLL also checks for potentially available launch processes that it can inject itself into. In the case of PaymentRequired, this could be system, security product or browser processes. Then the malware forms the corresponding code to drop files, delete files, etc.
The last step in the initialization procedure is to decrypt and decompress the configuration file. Decryption is done via a one-byte XOR using the 0xAA key, followed by decompression using the LZNT1 algorithm. From the configuration, the malware parses the RSA public key, ETag and IP addresses to communicate with its control servers.

Decrypted configuration data contains an RSA public key to encrypt exfiltrated data, C2 IPs and unique ETag to communicate with them
HTTP status-based communication module
Firstly, the module generates the following:

AES-128 encryption key used in HTTP GET/POST parameters and HTTP status code 427 (request new command);
4-byte unique hardware ID (HWID) based on the host network adapters, CPU and first fixed logical drive serial number.

The module then chooses a process to inject the code into, in order of decreasing priority, starting from Windows (cmd.exe, smss.exe), security-related applications (Symantec’s nis.exe, Dr.Web’s spideragent.exe) and browsers (IE, Opera, Firefox, Yandex browser, Chrome).
The main thread checks if the C2 supports TLS in its configuration. If it does, communication will be over HTTPS and port 443; otherwise, the HTTP protocol and port 80 are used.



Config Parameter
Value


Encryption key
RSA public key on the image above


ETag
C8E9CEAD2E084F58A94AEDC14D423E1A


C2 IPs
95.183.49[.]10
95.183.49[.]29
200.63.45[.]35



Decrypted configuration content inside the analyzed sample
The first GET request sent contains an ETag “If-Match” header that is built using data from its decrypted configuration. ETags are normally used by web servers for caching purposes in order to be more efficient and save bandwidth by not resending redundant information if an ETag value matches. The implementation of ETags means the C2 may ignore all requests that are not sent from its intended targets if they don’t have the required ETag value.



HTTP status
RFC status meaning
Corresponding command functionality


200
OK
Send collected target data to C2 with current tickcount


402
Payment Required
This status is the signal to process received (and stored in binary flag) HTTP statuses as commands


422
Unprocessable Entity (WebDAV)
Uninstall. Delete COM-hijacking persistence and corresponding files on disk


423
Locked (WebDAV)
Install. Create COM-hijacking persistence and drop corresponding files to disk


424
Failed Dependency (WebDAV)
Fingerprint target. Send host, network and geolocation data


427
Undefined HTTP status
Get new command into IEA94E3.tmp file in %TEMP%, decrypt and execute appended command


428
Precondition Required
Propagate self to USB devices on target


429
Too Many Requests
Enumerate network resources on target



C2 HTTP status code descriptions, including installation, USB propagation, fingerprinting, etc.
HTTP 427 can receive any of the following appended commands:



Command
Command functionality


dir
Send directory content to C2 encrypted with RSA public key from config


upl
Send file to C2 encrypted with RSA public key from config


usb
Not implemented yet. Possibly same function planned as for HTTP status 428


net
Not implemented yet. Possibly same function planned as for HTTP status 429



Removable device propagation module
If initialization is successful, the malware starts one more thread for dispatching Windows messages, looking for removable devices related to a WM_DEVICECHANGE event. The module runs its own handlers in the event of a USB device being plugged into or unplugged from the host.
Other spying modules: keylogger, screenshot tool and more
The user’s activity is monitored using several hooks. All of them gather the target’s data independently of any C2 command. Keystrokes are encrypted using the RSA public key stored in the configuration data and sent once every two seconds, or when moreа than 512 bytes are recorded. These 512 characters also include left mouse button clicks (written as the “MSLBTN” string) and Windows title bar texts. For clipboard content, the module calculates an MD5 hash and if it changes, encrypts the clipboard content with the same RSA public key and then sends it.
In a separate thread, the Trojan takes a bitmap screenshot using the GDIPlus library, compresses it with the LZNT1 algorithm, encrypts it using the key from the configuration data and sends it to the control server. A screenshot will be taken of the target and sent anyway, independently of any C2 command.
Last but not least
There are several choices – albeit not major additional technical ones – that the malware author made which we consider to be noteworthy.
The COM-hijacking-based persistence method injects its corresponding code and structure as a parameter into a legitimate process’s memory. The malware geolocates victims using legitimate web services: geoplugin.net/json.gp, ip-api.com/json and telize.com/geoip.
The unusual thread synchronization timeout calculation in the HTTP status thread is peculiar. Mathematically, the partial sum of the series is precisely:

This series, in the case of a full sum, is just a representation of the exponent. The developers probably used the exponent to make timeouts in the communication thread more unpredictable and grow at a fast rate, and the compiler calculated it this way.
So what did the COMPFun authors achieve?
We saw innovative approaches from the COMpfun developers twice in 2019. First, they bypassed TLS encrypted traffic via PRNG system function patching, and then we observed a unique implementation of C2 communications using uncommon HTTP status codes.
The malware operators retained their focus on diplomatic entities and the choice of a visa-related application – stored on a directory shared within the local network – as the initial infection vector worked in their favor. The combination of a tailored approach to their targets and the ability to generate and execute their ideas certainly makes the developers behind COMPFun a strong offensive team.
Indicators of compromise
File MD5 Hashes
Trojan 32-bit: A6AFA05CBD04E9AF256D278E5B5AD050
Trojan 64-bit: 1BB03CBAD293CA9EE3DDCE6F054FC325
IPs
95.183.49.10
95.183.49.29
200.63.45.35






APT
Keyloggers
Trojan-Dropper
Trojan-Spy
Turla



Authors




GReAT





COMpfun authors spoof visa application with HTTP status-based Trojan 
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



























