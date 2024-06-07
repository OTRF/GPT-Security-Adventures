# Reference for threat actor for "Turla, Waterbug, Venomous Bear"

**Title**: The Epic Turla Operation | Securelist

**Source**: https://securelist.com/the-epic-turla-operation/65545/

## Content















The Epic Turla Operation | Securelist




































































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

The Epic Turla Operation 

APT reports

07 Aug 2014

  minute read								
















Table of Contents





Executive SummaryThe Epic Turla attacksThe watering hole attacksThe Epic command-and-control infrastructureThe Epic / Tavdig / Wipbot  backdoorLateral movement and upgrade to  more sophisticated backdoorsLanguage artifactsVictim statisticsSummary 






 

Authors




GReAT



Solving some of the mysteries of Snake/Uroburos



 Technical Appendix with IOCs
Executive Summary
Over the last 10 months, Kaspersky Lab  researchers have analyzed a massive cyber-espionage operation which we call  “Epic Turla”. The attackers behind Epic Turla have infected several hundred  computers in more than 45 countries, including government institutions,  embassies, military, education, research and pharmaceutical companies.
The attacks are known to have used at least  two zero-day exploits:

CVE-2013-5065 – Privilege escalation vulnerability in Windows XP and Windows 2003
CVE-2013-3346 – Arbitrary  code-execution vulnerability in Adobe Reader

We also observed exploits against older  (patched) vulnerabilities, social engineering techniques and watering hole  strategies in these attacks. The primary backdoor used in the Epic attacks is  also known as “WorldCupSec”, “TadjMakhal”, “Wipbot” or “Tavdig”.
When G-Data published on Turla/Uroburos  back in February,  several questions remained unanswered. One big unknown was the infection vector for Turla (aka Snake or  Uroburos). Our analysis indicates that victims are infected via a sophisticated  multi-stage attack, which begins with the Epic Turla. In time, as the attackers  gain confidence, this is upgraded to more sophisticated backdoors, such as the  Carbon/Cobra system. Sometimes, both backdoors are run in tandem, and used to  “rescue” each other if communications are lost with one of the backdoors.
Once the attackers obtain the necessary  credentials without the victim noticing, they deploy the rootkit and other  extreme persistence mechanisms.
The attacks are still ongoing as of July  2014, actively targeting users in Europe and the Middle East.
Note: A full analysis of the Epic attacks is available  to the Kaspersky Intelligent Services subscribers. Contact:  intelreports@kaspersky.com
The Epic Turla attacks
The attacks in this campaign fall into  several different categories depending on the vector used in the initial compromise:

Spearphishing e-mails with Adobe PDF exploits (CVE-2013-3346 +  CVE-2013-5065)
Social engineering to trick the user into running malware installers  with “.SCR” extension, sometimes packed with RAR
Watering hole attacks using Java exploits (CVE-2012-1723), Flash  exploits (unknown) or Internet Explorer 6,7,8 exploits (unknown)
Watering hole attacks that rely on social engineering to trick the  user into running fake “Flash Player” malware installers

The attackers use both direct spearphishing  and watering hole attacks to infect their victims. Watering holes (waterholes)  are websites of interest to the victims that have been compromised by the  attackers and injected to serve malicious code.
So far we haven’t been able to locate any  e-mail used against the victims, only the attachments. The PDF attachments do  not show any “lure” to the victim when opened, however, the SCR packages  sometime show a clean PDF upon successful installation.

Some of known attachment names used in the  spearphishing attacks are:

ؤتمر جنيف.rar (translation from Arabic:  “Geneva conference.rar”)
NATO position on Syria.scr
Note_№107-41D.pdf
Talking Points.scr
border_security_protocol.rar
Security protocol.scr
Program.scr

In some cases, these filenames can provide  clues about the type of victims the attackers are targeting.
The watering hole attacks
Currently, the Epic attackers run a vast  network of watering holes that target visitors with surgical precision.
Some of the injected websites include:

The  website of the City Hall of Pinor, Spain

A  site promoting entrepreneurship in the border area of Romania

Palestinian  Authority Ministry of Foreign Affairs
In total, we observed more than 100  injected websites. Currently, the largest number of injected sites is in  Romania.
Here’s a statistic on the injected  websites:

The distribution is obviously not random,  and it reflects some of the interests of the attackers. For instance, in  Romania many of the infected sites are in the Mures region, while many of the  Spanish infected sites belong to local governments (City Hall).
Most of the infected sites use the TYPO3  CMS (see: https://typo3.org/),  which could indicate the attackers are abusing a specific vulnerability in this  publishing platform.
Injected websites load a remote JavaScript  into the victim’s browser:

The script “sitenavigatoin.js” is a  Pinlady-style browser and plugin detection script, which in turn, redirects to a  PHP script sometimes called main.php or wreq.php. Sometimes, the attackers  register the .JPG extension with the PHP handler on the server, using “JPG”  files to run PHP scripts:

Profiling  script
The main exploitation script “wreq.php”,  “main.php” or “main.jpg” performs a numbers of tasks. We have located several  versions of this script which attempt various exploitation mechanisms.
One version of this script attempts to  exploit Internet Explorer versions 6, 7 and 8:

Internet  Explorer exploitation script
Unfortunately, the Internet Explorer  exploits have not yet been retrieved.
Another more recent version attempts to  exploit Oracle Sun Java and Adobe Flash Player:

Java  and Flash Player exploitation scripts
Although the Flash Player exploits couldn’t  be retrieved, we did manage to obtain the Java exploits:




Name
MD5


allj.html
536eca0defc14eff0a38b64c74e03c79 


allj.jar
f41077c4734ef27dec41c89223136cf8 


allj64.html
15060a4b998d8e288589d31ccd230f86 


allj64.jar
e481f5ea90d684e5986e70e6338539b4 


lstj.jar
21cbc17b28126b88b954b3b123958b46 


lstj.html
acae4a875cd160c015adfdea57bd62c4 




The Java files exploit a popular  vulnerability, CVE-2012-1723,  in various configurations.
The payload dropped by these Java exploits  is the following:




MD5: d7ca9cf72753df7392bfeea834bcf992




The Java exploit use a special loader that  attempts to inject the final Epic backdoor payload into explorer.exe. The  backdoor extracted from the Java exploits has the following C&C hardcoded  inside:




www.arshinmalalan[.]com/themes/v6/templates/css/in.php




This C&C is still online at the moment  although it redirects to a currently suspended page at “hxxp://busandcoachdirectory.com[.]au“. For a full list of C&C  servers, please see the Appendix.
The Epic Turla attackers are extremely  dynamic in using exploits or different methods depending on what is available  at the moment. Most recently, we observed them using yet another technique  coupled with watering hole attacks.  This  takes advantage of social engineering to trick the user into running a fake  Flash Player (MD5: 030f5fdb78bfc1ce7b459d3cc2cf1877):

In at least one case, they tried to trick  the user into downloading and running a fake Microsoft Security Essentials app  (MD5: 89b0f1a3a667e5cd43f5670e12dba411):

The fake application is signed by a valid  digital certificate from Sysprint AG:
Serial number:  ‎00 c0 a3 9e 33 ec 8b ea 47 72 de 4b dc b7 49 bb 95
Thumbprint: ‎24  21 58 64 f1 28 97 2b 26 22 17 2d ee 62 82 46 07 99 ca 46

Valid  signature from Sysprint AG on Epic dropper
This file was distributed from the Ministry  of Foreign Affairs of Tajikistan’s website, at “hxxp://mfa[.]tj/upload/security.php“.
The file is a .NET application that  contains an encrypted resource. This drops the malicious file with the MD5 7731d42b043865559258464fe1c98513.
This is an Epic backdoor which connects to  the following C&Cs, with a generic internal ID of 1156fd22-3443-4344-c4ffff:




hxxp://homaxcompany[.]com/components/com_sitemap/ 
hxxp://www.hadilotfi[.]com/wp-content/themes/profile/




A full list with all the C&C server  URLs that we recovered from the samples can be found in the technical Appendix.
The Epic command-and-control infrastructure
The Epic backdoors are commanded by a huge  network of hacked servers that deliver    command and control functionality.
The huge  network commanded by the Epic Turla attackers serves multiple purposes. For  instance, the motherships function as both exploitation sites and command and  control panels for the malware. 
Here’s how the big picture looks  like:

Epic Turla lifecycle
The first level of command and control  proxies generally talk to a second level of proxies, which in turn, talk to the  “mothership” server. The mothership server is generally a VPS, which runs the  Control panel software used to interact with the victims. The attackers operate  the mothership using a network of proxies and VPN servers for anonymity  reasons. The mothership also work as the exploitation servers used in the  watering hole attacks, delivering Java, IE or fake applications to the victim.
We were able to get a copy of one of the  motherships, which provided some insight into the operation. 
It runs a control panel which is password  protected:

Epic mothership control panel login
Once logged into the Control panel, the  attackers can see a general overview of the system including the number of  interesting potential targets:

Epic control panel status overview
A very interesting file on the servers is task.css, where the attackers define  the IP ranges they are interested in. To change the file, they are using the  “Task editor” from the menu. Depending on the “tasks”, they will decide whether  to infect the visitors or not. In this case, we found they targeted two ranges  belonging to:

“Country A” – Federal Government Network
“Country B” – Government Telecommunications and Informatics Services Network

It should be noted though, the fact that  the attackers were targeting these ranges doesn’t necessarily mean they also  got infected. Some other unknown IPs were also observed in the targeting  schedules.
There is also an “except.css” file where attackers log the reasons they didn’t try to  exploit certain visitors. There are three possible values:

TRY
DON’T TRY -> Version of the  browser and OS does not meet the conditions
DON’T TRY -> (2012-09-19  10:02:04) – checktime < 60

These are the “don’t meet the conditions”  reasons observed in the logs:

Windows 7 or 2008 R2
MSIE 8.0
Mozilla/4.0 (compatible; MSIE  8.0; Windows NT 6.1; WOW64; Trident/4.0; SLCC2; .NET CLR 2.0.50727; .NET CLR  3.5.30729; .NET CLR 3.0.30729; .NET CLR 1.1.4322; .NET4.0C; .NET4.0E)
Adobe Shockwave 11.5.1.601
Adobe Flash 10.3.181.14
Adobe Reader 10.1.0.0
Win Media Player  12.0.7601.17514
Quick Time null
MS Word null
Java null

The Epic / Tavdig / Wipbot  backdoor
For this first stage of the attack, the  threat actor uses a custom backdoor. In some cases, the backdoor is packaged  together with the CVE-2013-5065 EoP exploit and heavily obfuscated. This makes  the analysis more difficult.
The CVE-2013-5065 exploit allows the  backdoor to achieve administrator privileges on the system and run  unrestricted. This exploit only works on unpatched Microsoft Windows XP  systems.
Other known detection names for the  backdoor is Trojan.Wipbot (Symantec) or Tavdig.
The main backdoor is about 60KB in size and  implements a C&C protocol on top of normal HTTP requests. The communication  protocol uses  requests in the C&C replies, which the malware decrypts and processes. The  replies are sent back to the C&C through the same channel.
The malware behavior is defined by a  configuration block. The configuration block usually contains two hard-coded  C&C URLs. He have also seen one case where the configuration block contains  just one URL. The configuration can also be updated on the fly by the  attackers, via the C&C. 
The backdoor attempts to identify the  following processes and, if found, it will terminate itself:

tcpdump.exe
windump.exe
ethereal.exe
wireshark.exe
ettercap.exe
snoop.exe
dsniff.exe

It contains an internal unique ID, which is  used to identify the victim to the C&C. Most samples, especially old ones,  have the ID 1156fd22-3443-4344-c4ffff.  Once a victim is confirmed as “interesting”, the attackers upload another Epic  backdoor which has a unique ID used to control this specific victim.
During the first C&C call, the backdoor  sends a pack with the victim’s system information. All further information sent  to the C&C is encrypted with a public key framework, making decryption  impossible. The commands from the C&C are encrypted in a simpler manner and  can be decrypted if intercepted because the secret key is hardcoded in the  malware.
Through monitoring, we were able to capture  a large amount of commands sent to the victims by the attackers, providing an  unique view into this operation. Here’s a look at one of the encrypted server  replies:

Once a victim is infected and “checks in”  with the server, the attackers send a template of commands:

Next, the attackers try to move through the  victim’s network using pre-defined or collected passwords:

Listing all .doc files recursively is also  a common “theme”:

In total, we have decoded several hundreds  of these command packages delivered to the victims, providing an unique insight  into the inner workings of the attackers.
In addition to generic searches, some very  specific lookups have been observed as well.   These include searches for:

*NATO*.msg
eu energy dialogue*.*
EU*.msg
Budapest*.msg

In this case, the attackers were interested  to find e-mails related to “NATO”, “Energy Dialogue within European Union”  and so on.
For some of the C&C servers, the  attackers implemented RSA encryption for the C&C logs, which makes it  impossible to decrypt them. This scheme was implemented in April 2014.

Lateral movement and upgrade to  more sophisticated backdoors
Once a victim is compromised, the attackers  upload several tools that are used for lateral movement.
One such tool observed in the attacks and  saved as “C:Documents and SettingsAll  usersStart MenuProgramsStartupwinsvclg.exe” is:




Name: winsvclg.exe 
MD5: a3cbf6179d437909eb532b7319b3dafe 
Compiled: Tue Oct 02 13:51:50 2012




This is a keylogger tool that creates %temp%~DFD3O8.tmp. Note: the filename  can change across victims. On one Central Asian government’s Ministry of  Foreign Affairs victim system, the filename used was “adobe32updt.exe“.
In addition to these custom tools, we  observed the usage of standard administration utilities. For instance, another  tool often uploaded by the attackers to the victim’s machine is “winrs.exe”:




Name: winrs.exe 
MD5: 1369fee289fe7798a02cde100a5e91d8 




This is an UPX packed binary, which  contains the genuine “dnsquery.exe” tool from Microsoft, unpacked MD5:  c0c03b71684eb0545ef9182f5f9928ca.
In several cases, an interesting update has  been observed —  a malware from a  different, yet related family.




Size: 275,968 bytes 
MD5: e9580b6b13822090db018c320e80865f 
Compiled: Thu Nov 08 11:05:35 2012




another example:




Size: 218,112 bytes 
MD5: 071d3b60ebec2095165b6879e41211f2 
Compiled: Thu Nov 08 11:04:39 2012




This backdoor is more sophisticated and  belongs to the next level of cyber-espionage tools called the “Carbon system”  or Cobra by the Turla attackers. Several plugins for the “Carbon system” are  known to exist.

Decoded  configuration for e9580b6b13822090db018c320e80865f
Note: the command and control servers www.losguayaberos[.]com and thebesttothbrushes[.]com have been  sinkholed by Kaspersky Lab.
Other packages delivered to the victims  include:




MD5: c7617251d523f3bc4189d53df1985ca9 
MD5: 0f76ef2e6572befdc2ca1ca2ab15e5a1




These top level packages deploy both  updated Epic backdoors and Turla Carbon system backdoors to confirmed victims,  effectively linking the Epic and Turla Carbon operations together.
The Turla Carbon dropper from these  packages has the following properties:




MD5: cb1b68d9971c2353c2d6a8119c49b51f 




This is called internally by the authors  “Carbon System”, part of the “Cobra” project, as it can be seen from the debug  path inside:

This acts as a dropper for the following  modules, both 32 and 64 bit:




MD5
Resource number


4c1017de62ea4788c7c8058a8f825a2d 
101


43e896ede6fe025ee90f7f27c6d376a4 
102


e6d1dcc6c2601e592f2b03f35b06fa8f 
104


554450c1ecb925693fedbb9e56702646 
105


df230db9bddf200b24d8744ad84d80e8 
161


91a5594343b47462ebd6266a9c40abbe 
162


244505129d96be57134cb00f27d4359c 
164


4ae7e6011b550372d2a73ab3b4d67096 
165




The Carbon system is in essence an  extensible platform, very similar to other attack platforms such as the Tilded  platform  or the Flame platform.  The plugins for the Carbon system can be easily recognized as they always  feature at least two exports named:

ModuleStart
ModuleStop


Carbon  system plugin with characteristic exports
Several Epic backdoors appear to have been  designed to work as Carbon system plugins as well – they require a specialized  loader to start in victim systems that do not have the Carbon system deployed.
Some modules have artifacts which indicate  the Carbon system is already at version 3.x, although the exact Carbon system  version is very rarely seen in samples:

The author of the Carbon module above can  be also seen in the code, as “gilg”, which also authored several other Turla  modules.
We are planning to cover the Turla Carbon  system with more details in a future report.

Language artifacts
The payload recovered from one of the  mothership servers (at newsforum.servehttp[.]com/wordpress/wp-includes/css/img/upload.php,  MD5: 4dc22c1695d1f275c3b6e503a1b171f5,  Compiled: Thu Sep 06 14:09:55 2012) contains two modules, a loader/injector and  a backdoor. Internally, the backdoor is named “Zagruzchik.dll”:

The word “Zagruzchik” means “boot loader”  in Russian.
The Control panel for the Epic motherships  also sets the language to codepage “1251”: 

Codepage 1251 is commonly used to render  Cyrillic characters.
There are other indications that the  attackers are not native English language speakers:

Password it´s wrong!
Count successful more MAX
File is not exists
File is exists for edit

The sample e9580b6b13822090db018c320e80865f that was delivered to several Epic  victims as an upgraded backdoor, has the compilation code page language set to  “LANG_RUSSIAN”.

The threat actor behind the “Epic”  operation uses mainly hacked servers to host their proxies. The hacked servers  are controlled through the use of a PHP webshell. This shell is password  protected; the password is checked against an MD5 hash:

The MD5 “af3e8be26c63c4dd066935629cf9bac8” has been solved by Kaspersky Lab  as the password “kenpachi”. In February 2014 we observed the Miniduke threat actor using the same backdoor on their  hacked servers, although using a much stronger password.
Once again, it is also interesting to point  out the usage of Codepage 1251 in the webshell, which is used to render  Cyrillic characters.
There appears to be several links between  Turla and Miniduke, but we will leave that for a future blogpost.
Victim statistics
On some of the C&C servers used in the  Epic attacks, we were able to identify detailed victim statistics, which were  saved for debugging purposes by the attackers.
This is the country distribution for the  top 20 affected countries by victim’s IP:

According to the public information  available for the victims’ IPs, targets of “Epic” belong to the following  categories:

Government

 Ministry of interior  (EU country)
 Ministry of trade and  commerce (EU country)
 Ministry of  foreign/external affairs (Asian country, EU country)
 Intelligence (Middle  East, EU Country)

Embassies
Military (EU country)
Education
Research (Middle East)
Pharmaceutical companies
Unknown (impossible to  determine based on IP/existing data)

Summary
When G-Data published their Turla paper,  there were few details publicly available on how victims get infected with this  malware campaign. Our analysis indicates this is a sophisticated multi-stage  infection; which begins with Epic Turla. This is used to gain a foothold and  validate the high profile victim. If the victim is interesting, they get  upgraded to the Turla Carbon system.
Most recently, we observed this attack  against a Kaspersky Lab user on August 5, 2014, indicating the operation  remains fresh and ongoing.
Note:  A full analysis of the Epic attacks is available to the Kaspersky Intelligent  Services customers. Contact:  intelreports@kaspersky.com
We would like to add the following at the end of the blogpost, right before the detection names:
Further reading
If you’d like to read more about Turla/Uroburos, here’s a few recommendations:

G-Data’s paper “Uroburos Highly complex espionage  software with Russian roots”
BAE Systems analysis of “The Snake campaign”
“Uroburos: the snake rootkit”, technical analysis by deresz and tecamac
“TR-25 Analysis – Turla / Pfinet / Snake/ Uroburos” by CIRCL.LU

Kaspersky products’ detection names for all the malware samples described in this post: 

Backdoor.Win32.Turla.an
Backdoor.Win32.Turla.ao
Exploit.JS.CVE-2013-2729.a
Exploit.JS.Pdfka.gkx
Exploit.Java.CVE-2012-1723.eh
Exploit.Java.CVE-2012-1723.ou
Exploit.Java.CVE-2012-1723.ov
Exploit.Java.CVE-2012-1723.ow
Exploit.Java.CVE-2012-4681.at
Exploit.Java.CVE-2012-4681.au
Exploit.MSExcel.CVE-2009-3129.u
HEUR:Exploit.Java.CVE-2012-1723.gen
HEUR:Exploit.Java.CVE-2012-4681.gen
HEUR:Exploit.Java.Generic
HEUR:Exploit.Script.Generic
HEUR:Trojan.Script.Generic
HEUR:Trojan.Win32.Epiccosplay.gen
HEUR:Trojan.Win32.Generic
HackTool.Win32.Agent.vhs
HackTool.Win64.Agent.b
Rootkit.Win32.Turla.d
Trojan-Dropper.Win32.Dapato.dwua
Trojan-Dropper.Win32.Demp.rib
Trojan-Dropper.Win32.Injector.jtxs
Trojan-Dropper.Win32.Injector.jtxt
Trojan-Dropper.Win32.Injector.jznj
Trojan-Dropper.Win32.Injector.jznk
Trojan-Dropper.Win32.Injector.khqw
Trojan-Dropper.Win32.Injector.kkkc
Trojan-Dropper.Win32.Turla.b
Trojan-Dropper.Win32.Turla.d
Trojan.HTML.Epiccosplay.a
Trojan.Win32.Agent.iber
Trojan.Win32.Agent.ibgm
Trojan.Win32.Agentb.adzu
Trojan.Win32.Inject.iujx
Trojan.Win32.Nus.g
Trojan.Win32.Nus.h

 Technical Appendix with IOCs






APT
Cyber espionage
Social engineering
Turla
Vulnerabilities and exploits
Watering hole attacks



Authors




GReAT





The Epic Turla Operation 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







true dia 


							Posted on							August 9, 2014. 5:53 am 



“word “Zagruzchik” means “boot loader” in Russian”
” attackers are not native English language speakers”
“File is not exists”  ” Codepage 1251″
LOL, are you shure?
Russians only can set language to russian…. ?
And my english it’s not sogood?
THATS sound really dumbish.
Reply 








Săndel 


							Posted on							December 9, 2014. 8:46 am 



Well… If you ask me, your English is rather shaggy.
But you’re right. One doesn’t have to be Russian or Ukrainian or Moldovan to set CP1251. 
салют
/Алексеи.
Reply 










André Spindler 


							Posted on							August 16, 2014. 10:51 am 



Hello.
You tell abaout more than 100 websites being infected. And say that most of them use TYPO3 CMS.
So I expect You have checked all websites to verify this. But obviously you have missed something:
You only name some few websites in detail, the first one is the website for City Hall in Pinor. I have checked this. It uses TYPO3, that’s right. But it uses TYPO3 version 4.1. Support for 4.1 was dropped years ago. Now we have 6.2.
Obviously you don’t know that. So You can’t tell about a specific vulnerability in this publishing platform.
You have mentioned three affected websites. I was only able to find one online. And this outdated version could not be used as an example that TYPO3 has a specific vulnerability. Unto now this version has MANY. Addionally this also means that there is a PHP version 5.2 or earlier is in use (PHP4). Seems like the complete server has been set up years ago and is not up to date. So it also can be a vulnerability in Apache, PHP, TYPO3, FTP and a lot more services and software.
I checked I site. And it didn’t prove the fact it is a TYPO3 vulnerability. Will I get this also on the more of 100 other sites, too?
Reply 



















Table of Contents





Executive SummaryThe Epic Turla attacksThe watering hole attacksThe Epic command-and-control infrastructureThe Epic / Tavdig / Wipbot  backdoorLateral movement and upgrade to  more sophisticated backdoorsLanguage artifactsVictim statisticsSummary 





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



























