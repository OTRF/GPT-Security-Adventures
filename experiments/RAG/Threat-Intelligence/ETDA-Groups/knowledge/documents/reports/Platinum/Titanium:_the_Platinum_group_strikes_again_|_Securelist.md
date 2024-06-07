# Reference for threat actor for "Platinum"

**Title**: Titanium: the Platinum group strikes again | Securelist

**Source**: https://securelist.com/titanium-the-platinum-group-strikes-again/94961/

## Content















Titanium: the Platinum group strikes again | Securelist



































































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

Titanium: the Platinum group strikes again 

APT reports

08 Nov 2019

  minute read								
















Table of Contents





VictimologyIntroductionInfection vector1 – Shellcode2 – Wrapper DLLs3 – Windows task installer (SFX archive)4 – Trojan-Backdoor installer (SFX archive)5 – BITS DownloaderShellcode descriptionBITS Downloader descriptionExecution sequenceArgument parserConfirmation URL request and file downloadingPayload decryption and launchFile launchingFile downloading using BITSWindows task installation (SFX archive with cURL)p.batRequest 1Request 2Task installationTrojan-backdoor installerpsinstrc.ps1DvDupdate.dllDllGetClassObjectnav_downarrow.pngnav_downarrow.png – Ordinal 1 (Trojan-backdoor main function)Execution threadInitializing C&C communicationReceiving commandsC&C command processor (command descriptions)Conclusions 






 

Authors




AMR




GReAT





Platinum is one of the most technologically advanced APT actors with a traditional focus on the APAC region. During recent analysis we discovered Platinum using a new backdoor that we call Titanium (named after a password to one of the self-executable archives). Titanium is the final result of a sequence of dropping, downloading and installing stages. The malware hides at every step by mimicking common software (protection related, sound drivers software, DVD video creation tools).
Victimology
During our research we found that the main targets of this campaign were located in South and Southeast Asia.
 
Introduction
The Titanium APT includes a complex sequence of dropping, downloading and installing stages, with deployment of a Trojan-backdoor as the final step. Almost every level of the system mimics known software, such as security software, software for making DVD videos, sound drivers’ software etc. 
In every case the default distribution is:

an exploit capable of executing code as a SYSTEM user
a shellcode to download the next downloader
a downloader to download an SFX archive that contains a Windows task installation script
a password-protected SFX archive with a Trojan-backdoor installer
an installer script (ps1)
a COM object DLL (a loader)
the Trojan-backdoor itself

Infection vector
We believe the Titanium APT uses local intranet websites with a malicious code to start spreading.
1 – Shellcode
Another known way of spreading is the use of a shellcode that needs to be injected into a process. In this case it was winlogon.exe. Unfortunately, we don’t know how the shellcode was injected. See the shellcode description below.
2 – Wrapper DLLs
Attackers make active use of various kinds of ‘wrappers’. Each wrapper is usually a COM DLL, with the corresponding exported functions. The main purpose of these libraries is to decrypt and load an encrypted file (previously dropped somewhere) into the system memory (a payload) and then redirect calls to the wrapper itself to the payload’s exported functions.
Another type of wrapper DLL is designed to obtain a command line from its exported function argument passed by a caller and create a new process.
3 – Windows task installer (SFX archive)
This is a password-encrypted SFX archive that can be downloaded via BITS Downloader. The password is hardcoded into the downloader that is used to decrypt the SFX archive using the -p command line argument.
The main feature of this archive is that it contains the cURL executable code, compiled into a DLL. Its purpose is to install the Windows task to establish persistence in the infected system.
4 – Trojan-Backdoor installer (SFX archive)
The backdoor itself uses an SFX archive which must be launched from the command line using a password to unpack it. All paths examples here and there will be for the DVD making software. However, these notes can be also applied to any other known software paths. 
5 – BITS Downloader
This component is used to download encrypted files from the C&C server then decrypt and launch them.
Shellcode description
The shellcode itself contains position-independent code and doesn’t require previously loaded libraries (except Kernel32.dll). Its sole purpose is to connect to the hardcoded C&C address, download an encrypted payload (the password-protected SFX archive), then decrypt and launch it using the hardcoded unpacking password. The usual command line is:





"rundll32 "$temp\IOZwXLeM023.tmp",GetVersionInfo -t 06xwsrdrub2i84n6map3li3vz3h9bh4vfgcw"




1

"rundll32 "$temp\IOZwXLeM023.tmp",GetVersionInfo -t 06xwsrdrub2i84n6map3li3vz3h9bh4vfgcw"




BITS Downloader description
The BITS Downloader is a DLL file which has only one exported function: GetVersionInfoA. The main purpose of this library is to download files in encrypted form from the C&C and launch them.
Execution sequence
The first thing the downloader does is to check whether it was started using the SYSTEM user. If it was, it launches command line arguments (that were passed to the binary loaded by the downloader DLL) using WMI.
If it wasn’t started using the SYSTEM user, the downloader passes command line arguments into the argument parser.
Argument parser



Key
Parameter description


-c URL
Specifies a URL address where system information will be sent


-t STRING
An additional string that will be appended to a request string to the C&C


-u URL
Confirmation URL where the downloader will send various confirmations or request data. Possible to build in two additional confirmation URLs


-br GUID
Stop a payload downloading. The GUID parameter must provide a download task GUID



If one of these parameters exists, the downloader will collect information about installed antivirus products and send it to the C&C.
After that, it sends the download request to the confirmation URL. In response, the C&C sends a file that will be downloaded in the %USERPROFILE% directory.
To decrypt the downloaded file, the downloader uses an MD5 hash of the strings’ encryption key.
Confirmation URL request and file downloading
Default (hardcoded) URL: http://70.39.115.196/payment/confirm.gif
The request is a string such as:

http://70.39.115.196/payment/confirm.gif?f=1 (x86)
http://70.39.115.196/payment/confirm.gif?f=2 (x64)

Payload decryption and launch
This is the structure of the encrypted file:





typedef struct {

    byte hash[16]; // md5 hash of the following data

    dword data_size;

    byte data[data_size];

} enc_data;




123456789

typedef struct {     byte hash[16]; // md5 hash of the following data     dword data_size;     byte data[data_size]; } enc_data;




The downloader checks the hash field against a calculated MD5 of the data field hash, and if the hash is correct, performs the following actions:

Appends an extension (DLL or EXE, depending on data type)
Stores the downloaded file in the %TMP% folder using the name %(SystemTimeAsFileTime.dwLowDateTime).%TMP

Then the downloader specifies a command line to launch the downloaded file. If the file is a DLL, the final command line will be:





"%systemroot%\system32\rundll32.exe %(SystemTimeAsFileTime.dwLowDateTime)%.TMP,-peuwewh383eg -t 06xwsrdrub2i84n6map3li3vz3h9bh4vfgcw"




1

"%systemroot%\system32\rundll32.exe %(SystemTimeAsFileTime.dwLowDateTime)%.TMP,-peuwewh383eg -t 06xwsrdrub2i84n6map3li3vz3h9bh4vfgcw"




If the file is an EXE file:





%(SystemTimeAsFileTime.dwLowDateTime)%.TMP -peuwewh383eg -t 06xwsrdrub2i84n6map3li3vz3h9bh4vfgcw




1

%(SystemTimeAsFileTime.dwLowDateTime)%.TMP -peuwewh383eg -t 06xwsrdrub2i84n6map3li3vz3h9bh4vfgcw




After that, the downloader deletes itself using the following command line:





/c for /L %i in (1,1,100) do ( for /L %k in (1,1,100) do (del /f /q module_path > NUL & if not exist module_path exit /b 0))




1

/c for /L %i in (1,1,100) do ( for /L %k in (1,1,100) do (del /f /q module_path > NUL & if not exist module_path exit /b 0))




File launching
To launch the downloaded file, the downloader uses the WMI classes Win32_ProcessStartup, Win32_Process and their methods and fields.
File downloading using BITS
To download a file, the downloader uses the BITS service and its COM interface, called IBackgroundCopyManager.
It creates a task with the name Microsoft Download, then specifies remote and local file paths and timeouts.
Windows task installation (SFX archive with cURL)
It contains:



Name
Description


p.bat
Launches cURL and obfuscated ps1 scripts


c.dll
cURL executable compiled as a DLL (7.50.3)


f1.ps1
Will be executed after the first request to the C&C; decrypts x.dat


f2.ps1
Will be executed after the second request to the C&C; decrypts b.dat


e.ps1
Contains code that calculates a string for the Authorization field of the HTTP header


h.ps1
Gets information about the system proxy settings


e.dll
A DLL file with a single exported function; calls CreateProcessA



It downloads:



Source file
Downloaded and decrypted file
Description


x.dat
u.xml
AES-encrypted file (see f1.ps1 for decryption algorithm)


b.dat
i.bat
AES-encrypted file (the same decryption algorithm)



The result:



Name
Description


i.bat
Performs Windows task installation



When a caller (previous step) executes this archive, it must specify two arguments:



Argument
Description


-pKEY
Argument with a key to unpack the SFX archive


-t ACCEPTANCE_ID_STRING
Argument with a long string – AcceptanceID (used in requests to the C&C)



p.bat
It launches the h.ps1 script to get information about system-wide proxy settings. After that it launches the e.ps1 script to calculate the SystemID that will be used in requests to the C&C.
To send a request, it uses c.dll (which is cURL and has an exported function called DllGetClassObject).
Request 1
Command line arguments:
 
Where:



Parameter
Description


%pp%
System-wide proxy


%output%
SystemID


%p3%
AcceptanceID



This request downloads the x.dat file, and the f1.ps1 script decrypts it into u.xml. After that it launches the next request.
Request 2
Command line arguments:
 
It downloads the b.dat file, and the f2.ps1 script decrypts it into i.bat (using the same decryption algorithm).
Task installation
After that, it launches the following command line to install the persistence task:
 
The i.bat file uses the previously decrypted u.xml file as the task description.
Trojan-backdoor installer
The archive unpacks its files into the following folder (in the case of DVD making software):
 
The archive itself contains:



Name
Description


BabyBoyStyleBackground.wmv
Configuration data


DvDupdate.dll
Trojan-backdoor loader


nav_downarrow.png
Trojan-backdoor


psinstrc.ps1
Loader installation script



In the case of the audio drivers software mimic, it differs only in its installation method compared to DVD making software: the ps1 script uses two known CLSIDs to replace their COM DLL paths with malicious ones.
psinstrc.ps1
This is the installer script that registers DvDupdate.dll as the ‘DVDMaker Help’ service, and sets its entry point as the DllGetClassObject name. It requires admin privileges to be executed correctly.
The script contains configurable parameters, so it’s easy to change any of the required parameters for different systems.
There are two ways the loader can be installed:

System service, with the DllGetClassObject exported function as the ServiceMain function
COM object, by replacing an existing CLSID registry path with its own

DvDupdate.dll
This is a service DLL, but with all the same exports you would expect from a COM object. Basically, it’s a payload loader.
The whole code is obfuscated with different Windows API calls and loops. It wasn’t designed to confuse a reverse engineer or to make reverse engineering harder, but to bypass some simple AV emulation engines.
The first exported function for every COM object is DllGetClassObject.
DllGetClassObject
The loader creates a thread that decrypts the payload, restores its PE and MZ headers, and then loads it into memory and launches it. The payload is encrypted with AES 256 CBC. The decryption key is hardcoded along with other encrypted strings. It doesn’t contain ‘MZ‘ and ‘PE‘ tags that allow it to bypass simple AV engines. After initializing the payload, the loader calls its function with ordinal 1.
nav_downarrow.png
The payload, with backdoor functionality, is a DLL file. The malware functionality is in the first exported entry only.
nav_downarrow.png – Ordinal 1 (Trojan-backdoor main function)
The first thing that it does is decrypt the other encrypted binary (containing configuration data) from the SFX content:
 
The configuration itself is divided into blocks, and every block has its own index. The payload uses these indices to get a specific item. The configuration contains:

the C&C address
traffic encryption key
the UserAgent string
other less important parameters

Execution thread
The execution thread is responsible for receiving commands from the C&C server and sending responses. It contains an execution loop that starts by reading configuration item #00 to get the C&C address.
Initializing C&C communication
To initialize the connection to the C&C, the payload sends a base64-encoded request that contains a unique SystemID, computer name, and hard disk serial number. After that, the malware starts receiving commands.
Receiving commands
To receive commands from the C&C, the payload sends an empty request to the C&C. It uses the UserAgent string from the configuration and a special cookie generation algorithm to prepare a request. The malware can also get proxy settings from Internet Explorer.
In response to this request, the C&C answers with a PNG file that contains steganographically hidden data. This data is encrypted with the same key as the C&C requests. The decrypted data contains backdoor commands and arguments for them.
Examples of PNG files:
 
C&C command processor (command descriptions)
The backdoor can accept many different commands, with the following among the most interesting:

Read any file from a file system and send it to the C&C
Drop or delete a file in the file system
Drop a file and run it
Run a command line and send execution results to the C&C
Update configuration parameters (except the AES encryption key)
Interactive mode – allows to the attacker to receive input from console programs and send their output at the C&C

Conclusions
The Titanium APT has a very complicated infiltration scheme. It involves numerous steps and requires good coordination between all of them. In addition, none of the files in the file system can be detected as malicious due to the use of encryption and fileless technologies. One other feature that makes detection harder is the mimicking of well-known software.
Regarding campaign activity, we have not detected any current activity related to the Titanium APT.






Backdoor
Fileless malware
Malware Descriptions
Malware Technologies
Targeted attacks
Trojan



Authors




AMR




GReAT





Titanium: the Platinum group strikes again 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Rico Pico Train 


							Posted on							November 8, 2019. 2:07 pm 



Any hashes, yara signatures you can share?
Reply 








Alexey Shulmin 


							Posted on							November 11, 2019. 12:16 pm 



All hashes and yara rules are avaliable via our threat intelligence portal. For more information please contact: intelreports@kaspersky.com.
Reply 










evandrix 


							Posted on							November 9, 2019. 6:39 pm 



malware sample hash(es)?
Reply 








SBO 


							Posted on							November 12, 2019. 12:21 pm 



Any indicators or detection mechanism available?
Reply 








song 


							Posted on							December 16, 2019. 11:29 am 



Any indicators or detection mechanism available?
Reply 



















Table of Contents





VictimologyIntroductionInfection vector1 – Shellcode2 – Wrapper DLLs3 – Windows task installer (SFX archive)4 – Trojan-Backdoor installer (SFX archive)5 – BITS DownloaderShellcode descriptionBITS Downloader descriptionExecution sequenceArgument parserConfirmation URL request and file downloadingPayload decryption and launchFile launchingFile downloading using BITSWindows task installation (SFX archive with cURL)p.batRequest 1Request 2Task installationTrojan-backdoor installerpsinstrc.ps1DvDupdate.dllDllGetClassObjectnav_downarrow.pngnav_downarrow.png – Ordinal 1 (Trojan-backdoor main function)Execution threadInitializing C&C communicationReceiving commandsC&C command processor (command descriptions)Conclusions 





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



























