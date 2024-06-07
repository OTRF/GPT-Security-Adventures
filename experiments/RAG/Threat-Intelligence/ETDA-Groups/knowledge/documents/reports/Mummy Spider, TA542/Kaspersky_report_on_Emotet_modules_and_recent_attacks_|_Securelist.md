# Reference for threat actor for "Mummy Spider, TA542"

**Title**: Kaspersky report on Emotet modules and recent attacks | Securelist

**Source**: https://securelist.com/emotet-modules-and-recent-attacks/106290/

## Content















Kaspersky report on Emotet modules and recent attacks | Securelist




































































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

Emotet modules and recent attacks 

Malware descriptions

13 Apr 2022

  minute read								
















Table of Contents





Emotet technical analysisInfection chainProcess List moduleMail PassView moduleWebBrowser PassView moduleOutlook Address Grabber moduleOutlook E-mails Grabber moduleThunderbird Address Grabber moduleThunderbird E-mails Grabber moduleSpam moduleUPnP moduleStatisticsVictimologyConclusionIndicators of Compromise 






 

Authors




AMR




GReAT



Anti-Malware Research


Emotet was first found in the wild in 2014. Back then its main functionality was stealing user banking credentials. Since then it has survived numerous transformations, started delivering other malware and finally became a powerful botnet. In January 2021 Emotet was disrupted by a joint effort of different countries’ authorities. It took the threat actors almost 10 months to rebuild the infrastructure, whereupon Emotet returned in November. At that time, Trickbot malware was used to deliver Emotet. Now, Emotet is spreading by itself in malicious spam campaigns.
Based on recent Emotet protocol analysis and C2 responses, we can say that now Emotet can download 16 additional modules. We were able to retrieve 10 of them (including two different copies of the Spam module), used by Emotet for Credential/Password/Account/E-mail stealing and spamming. In this post, we provide a brief analysis of these modules, as well as statistics on recent Emotet attacks.
Emotet technical analysis
Infection chain
A typical Emotet infection begins with spam e-mails delivered with Microsoft Office (Word, Excel) attachments. Malicious macros are used to start PowerShell, and download and execute an Emotet DLL. Depending on the available access, Emotet creates a subdirectory with a random name in the %Windows%\SysWOW64\ or %User%\AppData\Local\ directory, and copies itself there under a randomly generated name and extension. The exported Control_RunDLL function is used to run the main activity of the Emotet DLL.

Emotet infection execution chain
After being run, the Emotet malware creates a service by calling the CreateServiceW() function. A randomly generated name and extension, which were used to create a copy, act as service names.

CreateServiceW() function with arguments
If the attempt to create a new service fails, Emotet creates a new registry key in HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Run with the same names that were used when creating the service.

Autostart key in registry
As soon as the Emotet DLL is launched, it registers with one of the 20 C2 IPs that are hardcoded in encrypted form into the malware body. Downloaded modules can also include additional C2 IPs. The following data is used for bot registration:

Registration data
Together with the registration data, the victim’s public key that is generated in every run is also sent to the C2. Unlike previous versions that used RSA to encrypt the generated AES key, this newest Emotet sample uses the ECDH (Elliptic curve Diffie–Hellman) algorithm, using the victim’s generated key pair together with Emotet’s public key hardcoded into the code to derive the AES key for encrypting the communication. This is done with use of the Windows API BCryptSecretAgreement.
During our monitoring we have observed that after registration the C2 replies with the Process List module payload. The module comes in the form of a DLL that is parsed and loaded directly into the Rundll32 process. Its entry point is called by passing a specific structure to its DllMain function. It is also worth noting that Emotet uses the ECDSA (Elliptic Curve Digital Signature Algorithm) to verify the payload integrity before loading it.

Pseudo code to load Emotet’s second-stage DLL directly into memory
Aside from loading the DLL into memory, there are other ways to run the payload. For example:

write the DLL payload to disk and run it through regsvr32.exe -s “%s” or rundll32.exe “%s”,Control_RunDLL
write the payload to disk and attempt to call CreateProcess or duplicate the user token to call CreateProcessAsUser

During communication, C2 returns the module bodies and configuration. Based on the configuration, the malware selects the way to run the payload module. During our research, all the modules we retrieved were launched in the parent process, but a separate thread is started for each new module. Each module has its own numeric ID, and contains its own C2 list. However, all the modules we retrieved contained the same list of C2, except the Spam module. Emotet modules are delivered on demand, and there are always a few junk bytes that vary in different samples of the same module. This is likely to avoid cloud scanning or file hash detection.

Random bytes changed between “Process List” module binaries
Process List module
This module sends the list of running processes back to C2. Usually C2 does not send any other modules until it gets a response from this one.

Emotet Process List module request
Mail PassView module
The module contains an embedded executable called Nir Sofer’s Mail PassView, a password recovery tool that reveals passwords and account details for various e-mail clients. In order to execute the password recovery tool, the Emotet module copies certutil.exe into a %Temp% directory under a random name with the .exe extension, starts the copied executable and uses the process hollowing technique to inject the password recovery tool executable into the newly created process. The CertUtil process is started with command line arguments to force the recovery tool to save the results to file.

CertUtil with command line for password recovery tool
According to the official website, the utility is capable of revealing passwords and other account details for various e-mail clients, including Outlook and Thunderbird.
WebBrowser PassView module
This module is mostly the same as the previous one, except it uses  the Nir Sofer’s WebBrowser PassView password recovery tool for revealing passwords and account details in browsers.
According to the official website, the utility is capable of revealing passwords and other account details in various web browsers, including Internet Explorer, Mozilla Firefox, Google Chrome, Safari and Opera.

Pseudocode of function from WebBrowser PassView module
Emotet has used code obfuscation for years, and this module is no exception. In the figure above, we can see that the control flow obfuscation technique is used with the variable ‘state’ (yellow-colored). Also, all API calls are resolved during runtime. This is why this API resolution layer can use junk arguments (red-framed). Code listings can be larger and more obfuscated, which is why it makes no sense to show them for all modules.
Outlook Address Grabber module
A data exfiltration module for Outlook. The module uses the Outlook Messaging API interface, iterates through Outlook profiles and extracts all displayed names and mail addresses from each found mail. It then sends the collected e-mail addresses to C2.
Outlook E-mails Grabber module
A data exfiltration module for Outlook. The module uses the Outlook Messaging API interface, iterates through all personal folders (Inbox, Sent items, Deleted Items, etc), extracts all displayed names and mail addresses of sender and recipient, and extracts the e-mail subject and body. It then sends the collected e-mails to C2.
Thunderbird Address Grabber module
A data exfiltration module for Thunderbird. The module iterates through Thunderbird profiles located in %AppData%\Roaming\Thunderbird\Profiles\, parses Thunderbird data files and extracts displayed names and mail addresses. It then sends the collected e-mail addresses to C2.
Thunderbird E-mails Grabber module
A data exfiltration module for Thunderbird. The module iterates through Thunderbird profiles located in %AppData%\Roaming\Thunderbird\Profiles\, parses Thunderbird data files and extracts displayed names and mail addresses of sender and recipient, and extracts the e-mail subject and body. It then sends the collected e-mails to C2.
Spam module
The module is responsible for sending spam. It queries C2 until it receives a response with a spam task that usually consist of three parts:

A list of e-mail servers and compromised accounts to be used to send spam; dozens of compromised accounts are stored in a single task.
A list of targeted e-mails, recipient e-mail and name, sender e-mail and name.
A spam template with subject, body and attachments.


Redacted list of email servers, compromised accounts used for spamming
Two of the 10 modules we were able to obtain were spam modules. Their functionality is one and the same, but the module IDs differ.
UPnP module
An auxiliary module for testing the possibility of connecting to the infected system from the outside. In the settings of this module, which are sent by C2, together with the module itself, the external IP address of the infected system is transmitted. The first thing this module does is enumerate the network interfaces and compare their addresses with the IP address obtained from the module’s configuration settings. If a suitable network interface is found, the module opens ports for listening and waits for an incoming connection. The module can open the following ports: 80, 443, 8080, 8090, 7080, 8443, 20, 21, 22, 53, 143, 465, 990, 993, 995. If a suitable network interface is not found, it uses the SSDP protocol to find devices (modem, router, etc.) with Internet access. If suitable devices are found, the module tries to reconfigure them using AddPortMapping to allow port forwarding.

Example of AddPortMapping for 443 port forwarding
Statistics
Since Emotet’s return in November 2021, we have observed its activity gradually increase. In March 2022, however, based on our telemetry, the number of attacked users shot up from 2,847 in February to 9,086 — more than threefold growth.

Dynamics of the number of attacked users in recent Emotet attacks, November 2021–March 2022 (download)
A similar upsurge we observed in March in the number of Emotet detections.

Dynamics of the number of Emotet detections, November 2021–March 2022 (download)
Victimology
Emotet infects computers of companies and individual users all over the world. In Q1 2022, according to our telemetry, users of the following countries were most often targeted by Emotet: Italy (10.04%), Russia (9.87%), Japan (8.55%), Mexico (8.36%), Brazil (6.88%), Indonesia (4.92%), India (3.21%), Vietnam (2.70%), China (2.62), Germany (2.19%) and Malaysia (2.13%).

Geographical distribution of Emotet targets, Q1 2022 (download)
Conclusion
The current set of modules is capable of performing a large set of malicious actions: stealing e-mails, passwords and login data from various sources; sending spam. All these modules, except those for Thunderbird, in one form or another, have been used before by Emotet. However, there are still modules that we have not been able to obtain yet. In addition, our telemetry shows significant growth in the number of attacked users in March. We continue to actively monitor the Emotet family. More information about the malware we provide in our private reports on Kaspersky Threat Intelligence Portal.
Indicators of Compromise
Note: Because Emotet is polymorphic malware, there are no IOC hashes.
C2 IP addresses
70[.]36.102.35:443
197[.]242.150.244:8080
188[.]44.20.25:443
45[.]118.135.203:7080
92[.]240.254.110:8080
103[.]43.46.182:443
1[.]234.2.232:8080
50[.]116.54.215:443
51[.]91.76.89:8080
206[.]188.212.92:8080
153[.]126.146.25:7080
178[.]79.147.66:8080
217[.]182.25.250:8080
196[.]218.30.83:443
51[.]91.7.5:8080
72[.]15.201.15:8080
119[.]193.124.41:7080
5[.]9.116.246:8080
151[.]106.112.196:8080
101[.]50.0.91:8080
45[.]142.114.231:8080
185[.]157.82.211:8080
46[.]55.222.11:443
103[.]75.201.2:443
176[.]56.128.118:443
176[.]104.106.96:8080
107[.]182.225.142:8080
31[.]24.158.56:8080
51[.]254.140.238:7080
159[.]65.88.10:8080
82[.]165.152.127:8080
146[.]59.226.45:443
173[.]212.193.249:8080
212[.]24.98.99:8080
212[.]237.17.99:8080
110[.]232.117.186:8080
131[.]100.24.231:80
209[.]250.246.206:443
195[.]201.151.129:8080
138[.]185.72.26:8080






Botnets
Emotet
Malware
Malware Descriptions
Malware Statistics
Malware Technologies
Trojan Banker



Authors




AMR




GReAT





Emotet modules and recent attacks 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





Emotet technical analysisInfection chainProcess List moduleMail PassView moduleWebBrowser PassView moduleOutlook Address Grabber moduleOutlook E-mails Grabber moduleThunderbird Address Grabber moduleThunderbird E-mails Grabber moduleSpam moduleUPnP moduleStatisticsVictimologyConclusionIndicators of Compromise 





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






 


Kaspersky Security Bulletin 2023. Statistics 






 


IT threat evolution in Q3 2023. Non-mobile statistics 






 


Advanced threat predictions for 2024 









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



























