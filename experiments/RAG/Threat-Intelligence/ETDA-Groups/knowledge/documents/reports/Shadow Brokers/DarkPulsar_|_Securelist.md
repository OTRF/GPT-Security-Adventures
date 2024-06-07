# Reference for threat actor for "Shadow Brokers"

**Title**: DarkPulsar | Securelist

**Source**: https://securelist.com/darkpulsar/88199/

## Content















DarkPulsar | Securelist



































































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

DarkPulsar 

APT reports

19 Oct 2018

  minute read								








 

Authors




Andrey Dolgushev



 Dmitry Tarakanov




Vasily Berdnikov





In March 2017, the ShadowBrokers published a chunk of stolen data that included two frameworks: DanderSpritz and FuzzBunch.
DanderSpritz consists entirely of plugins to gather intelligence, use exploits and examine already controlled machines. It is written in Java and provides a graphical windows interface similar to botnets administrative panels as well as a Metasploit-like console interface. It also includes its own backdoors and plugins for not-FuzzBunch-controlled victims.
DanderSprit interface
Fuzzbunch on the other hand provides a framework for different utilities to interact and work together. It contains various types of plugins designed to analyze victims, exploit vulnerabilities, schedule tasks, etc. There are three files in the plugin set from the FuzzBunch framework:

%pluginName%-version.fb

This is the utility file of the framework. It duplicates the header from XML and includes the plugin’s ID.

%pluginName%-version.exe

This executable file is launched when FuZZbuNch receives the command to do so.

%pluginName%-version.xml

This configuration file describes the plugin’s input and output parameters – the parameter name, its type and description of what it’s responsible for; all of these can be shown in FuzzBunch as a prompt. This file also contributes a lot to the framework’s usability, as it supports the specification of default parameters.
One of the most interesting Fuzzbunch’s categories is called ImplantConfig and includes plugins designed to control the infected machines via an implant at the post-exploitation stage. DarkPulsar is a very interesting administrative module for controlling a passive backdoor named ‘sipauth32.tsp’ that provides remote control, belonging to this category.
It supports the following commands:

Burn
RawShellcode
EDFStagedUpload
DisableSecurity
EnableSecurity
UpgradeImplant
PingPong

Burn, RawShellcode, UpgradeImplant, and PingPong remove the implant, run arbitrary code, upgrade the implant and check if the backdoor is installed on a remote machine, respectively. The purpose of the other commands is not that obvious and, to make it worse, the leaked framework contained only the administrative module to work with DarkPulsar’s backdoor, but not the backdoor itself.
While analyzing the administrative module, we noticed several constants that are used to encrypt the traffic between the C&C and the implant:

We thought that probably these constants should also appear in the backdoor, so we created a detection for them. Several months later we found our mysterious DarkPulsar backdoor. We later were able to find both 32- and 64-bit versions.
We found around 50 victims located in Russia, Iran and Egypt, typically infecting Windows 2003/2008 Server. Targets were related to nuclear energy, telecommunications, IT, aerospace and R&D.
DarkPulsar technical highlights
The DarkPulsar implant is a dynamic library whose payload is implemented in exported functions. These functions can be grouped as follows:

Two nameless functions used to install the backdoor in the system.
Functions with names related to TSPI (Telephony Service Provider Interface) operations that ensure the backdoor is in the autorun list and launched automatically.
A function with a name related to SSPI (Security Support Provider Interface) operations. It implements the main malicious payload.

The implementations of the SSPI and TSPI interfaces are minimalistic: the functions that are exported by DarkPulsar have the same names as the interface functions; however, they include malicious code instead of the phone service.
The implant is installed in the system by the nameless exported function. The backdoor is launched by calling Secur32.AddSecurityPackage with administrator privileges with the path to its own library in the parameter, causing lsass.exe to load DarkPulsar as SSP/AP and to call its exported function SpLsaModeInitialize used by DarkPulsar to initialize the backdoor. In this way AddSecurityPackage is used to inject code into lsass.exe. It also adds its library name at HKLM\Software\Microsoft\Windows\CurrentVersion\Telephony\Providers
This is loaded at start by the Telephony API (TapiSrv) launched alongside the Remote Access Connection Manager (RasMan) service, setting startup type as “Automatic”. When loading the telephony service provider’s library, TapiSrv calls TSPI_lineNegotiateTSPIVersion which contains the AddSecurityPackage call to make the inject into lsass.exe.
DarkPulsar implements its payload by installing hooks for the SpAcceptLsaModeContext – function responsible for authentication. Such injects are made in several system authentication packets within the process lsass.exe and allow Darkpulsar to control authentication process based on the following protocols:

Msv1_0.dll – for the NTLM protocol,
Kerberos.dll – for the Kerberos protocol,
Schannel.dll – for the TLS/SSL protocols,
Wdigest.dll – for the Digest protocol, and
Lsasrv.dll –for the Negotiate protocol.

After this, Darkpulsar gets ability to embed malware traffic into system protocols. Since this network activity takes place according to standard system charts, it will only be reflected in the System process – it uses the system ports reserved for the above protocols without hindering their normal operation.
Network traffic during successful connection to DarkPulsar implant
The second advantage of controlling authentication processes is ability to bypass entering a valid username and password for obtaining access to objects that require authentication such as processes list, remote registry, file system through SMB. After Darkpulsar’s DisableSecurity command is sent, backdoor’s hooks on the victim side will always returns in the SpAcceptLsaModeContext function that passed credentials are valid. Getting that, system will provide access to protected objects to client.
Working with DarkPulsar
Darkpulsar-1.1.0.exe is the administrative interface working under the principle of “one command – one launch”. The command to be executed must be specified either in the configuration file Darkpulsar-1.1.0.9.xml or as command line arguments, detailing at least:

whether the target machine uses a 32-bit or 64-bit system;
protocol (SMB, NBT, SSL, RDP protocols are supported) to deliver the command and port number
private RSA key to decrypt the session AES key

Darkpulsar-1.1.0 was not designed as a standalone program for managing infected machines. This utility is a plugin of the Fuzzbunch framework that can manage parameters and coordinate different components.  Here is how DisableSecurity command in Fuzzbunch looks like:

Below is an example of Processlist after DisableSecurity, allowing to execute any plugin without valid credentials and operating via regular system functions (remote registry service):

DanderSpritz
DanderSpritz is the framework for controlling infected machines, different from FuZZbuNch as the latter provides a limited toolkit for the post-exploitation stage with specific functions such as DisableSecurity and EnableSecurity for DarkPulsar.
For DanderSpritz works for a larger range of backdoors, using PeedleCheap in the victim to enable operators launching plugins. PeddleCheap is a plugin of DanderSpritz which can be used to configure implants and connect to infected machines. Once a connection is established all DanderSpritz post-exploitation features become available.
This is how DarkPulsar in EDFStagedUpload mode provides the opportunity to infect the victim with a more functional implant: PCDllLauncher (Fuzzbunch’s plugin) deploys the PeddleCheap implant on the victim side, and DanderSpritz provides a user-friendly post-exploitation interface. Hence, the full name of PCDllLauncher is ‘PeddleCheap DLL Launcher’.
The complete DanderSpritz usage scheme with the plugin PeddleCheap via FuZZbuNch with the plugins DarkPulsar and PCDllLauncher consists of four steps:

Via FuZZbuNch, run command EDFStagedUpload to launch DarkPulsar.
In DanderSpritz, run command pc_prep (PeedelCheap Preparation) to prepare the payload and the library to be launched on the implant side.
In DanderSpritz, run command pc_old (which is the alias of command pc_listen -reuse -nolisten -key Default) – this sets it to wait for a socket from Pcdlllauncher.
Launch Pcdlllauncher via FuZZbuNch and specify the path to the payload that has been prepared with the command pc_prep in the ImplantFilename parameter.


DanderSpritz
File System plugin
Conclusions
The FuzzBunch and DanderSpritz frameworks are designed to be flexible and to extend functionality and compatibility with other tools. Each of them consists of a set of plugins designed for different tasks: while FuzzBunch plugins are responsible for reconnaissance and attacking a victim, plugins in the DanderSpritz framework are developed for managing already infected victims.
The discovery of the DarkPulsar backdoor helped in understanding its role as a bridge between the two leaked frameworks, and how they are part of the same attacking platform designed for long-term compromise, based on DarkPulsar’s advanced abilities for persistence and stealthiness. The implementation of these capabilities, such as encapsulating its traffic into legitimate protocols and bypassing entering credentials to pass authentication, are highly professional.
Our product can completely remove the related to this attack malware.
Detecting malicious network activity 
When EDFStagedUpload is executed in an infected machine, a permanent connection is established, which is why traffic via port 445 appears. A pair of bound sockets also appears in lsass.exe:

When DanderSpritz deploys PeddleCheap’s payload via the PcDllLauncher plugin, network activity increases dramatically:

When a connection to the infected machine is terminated, network activity ceases, and only traces of the two bound sockets in lsass.exe remain:

IOCs
implant – 96f10cfa6ba24c9ecd08aa6d37993fe4
File path – %SystemRoot%\System32\sipauth32.tsp
Registry – HKLM\Software\Microsoft\Windows\CurrentVersion\Telephony\Providers






APT
Backdoor
Shadow Brokers
Targeted attacks



Authors




Andrey Dolgushev



 Dmitry Tarakanov




Vasily Berdnikov





DarkPulsar 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Marissa Jennings 


							Posted on							October 26, 2018. 10:42 am 



Please upload it to Hybrid-Analysis already.
m(
Reply 








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




 


DarkUniverse – the mysterious APT framework #27 






 


Platinum is back 






 


New zero-day vulnerability CVE-2019-0859 in win32k.sys 






 


The fourth horseman: CVE-2019-0797 vulnerability 






 


DarkPulsar FAQ 









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



























