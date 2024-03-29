# Reference for threat actor for "Inception Framework, Cloud Atlas"

**Title**: Cloud Atlas: RedOctober APT is back in style | Securelist

**Source**: https://securelist.com/cloud-atlas-redoctober-apt-is-back-in-style/68083/

## Content















Cloud Atlas: RedOctober APT is back in style | Securelist



































































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

Cloud Atlas: RedOctober APT is back in style 

APT reports

10 Dec 2014

  minute read								
















Table of Contents





Meet Cloud AtlasC&C communicationVictim statistics: top 5 infected countriesSimilarities with RedOctoberConclusionParallel research: 






 

Authors




GReAT





Two years ago, we published our research into RedOctober, a complex cyber-espionage operation targeting diplomatic embassies worldwide. We named it RedOctober because we started this investigation in October 2012, an unusually hot month.
After our announcement in January 2013, the RedOctober operation was promptly shut down and the network of C&Cs was dismantled. As usually happens with these big operations, considering the huge investment and number of resources behind it, they don’t just “go away” forever. Normally, the group goes underground for a few months, redesigns the tools and the malware and resume operations.
See:

RedOctober Part 1
RedOctober Part 2

Since January 2013, we’ve been on the lookout for a possible RedOctober comeback. One possible hit was triggered when we observed Mevade, an unusual piece of malware that appeared late in 2013. The Mevade C&C name styles as well as some other technical similarities indicated a connection to RedOctober, but the link was weak. It wasn’t until August 2014 that we observed something which made us wonder if RedOctober is back for good.
Meet Cloud Atlas
In August 2014, some of our users observed targeted attacks with a variation of CVE-2012-0158 and an unusual set of malware. We did a quick analysis of the malware and it immediately stood out because of certain unusual things that are not very common in the APT world.
Some of the filenames used in the attacks included:

FT – Ukraine Russia’s new art of war.doc
Катастрофа малайзийского лайнера.doc
Diplomatic Car for Sale.doc
МВКСИ.doc
Organigrama Gobierno Rusia.doc
Фото.doc
Информационное письмо.doc
Форма заявки (25-26.09.14).doc
Информационное письмо.doc
Письмо_Руководителям.doc
Прилож.doc
Car for sale.doc
Af-Pak and Central Asia’s security issues.doc

At least one of them immediately reminded us of RedOctober, which used a very similarly named  spearphish: “Diplomatic Car for Sale.doc”. As we started digging into the operation, more details emerged which supported this theory.
Perhaps the most unusual fact was that the Microsoft Office exploit didn’t directly write a Windows PE backdoor on disk. Instead, it writes an encrypted Visual Basic Script and runs it.

Cloud Atlas exploit payload – VBScript
This VBScript drops a pair of files on disk – a loader and an encrypted payload. The loader appears to be different every time and internal strings indicate it is “polymorphically” generated. The payload is always encrypted with a unique key, making it impossible to decrypt unless the DLL is available.
We observed several different spear-phishing documents that drop uniquely named payloads. For instance, the “qPd0aKJu.vbs” file MD5:
E211C2BAD9A83A6A4247EC3959E2A730 drops the following files:
DECF56296C50BD3AE10A49747573A346 – bicorporate – encrypted payload
D171DB37EF28F42740644F4028BCF727 – ctfmonrn.dll – loader
The VBS also adds a registry key:
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run\ setting the key “bookstore” to the value “regsvr32 %path%\ctfmonrn.dll /s”, which ensures the malware runs every time at system boot.
Some of the DLL names we observed include:
f4e15c1c2c95c651423dbb4cbe6c8fd5 – bicorporate.dll
649ff144aea6796679f8f9a1e9f51479 – fundamentive.dll
40e70f7f5d9cb1a669f8d8f306113485 – papersaving.dll
58db8f33a9cdd321d9525d1e68c06456 – previliges.dll
f5476728deb53fe2fa98e6a33577a9da – steinheimman.dll
Some of the payload names include:
steinheimman
papersaving
previliges
fundamentive
bicorporate
miditiming
damnatorily
munnopsis
arzner
redtailed
roodgoose
acholias
salefians
wartworts
frequencyuse
nonmagyar
shebir
getgoing
The payload includes an encrypted configuration block which contains information about the C&C sever:

The information from the config includes a WebDAV URL which is used for connections, a username and password, two folders on the WebDAV server used to store plugins/modules for the malware and where data from the victim should be uploaded.
C&C communication
The Cloud Atlas implants utilize a rather unusual C&C mechanism. All the malware samples we’ve seen communicate via HTTPS and WebDav with the same server “cloudme.com”, a cloud services provider. According to their website, CloudMe is owned and operated by CloudMe AB, a company based in Linköping, Sweden.
(Important note: we do not believe that CloudMe is in any way related to the Cloud Atlas group – the attackers simply create free accounts on this provider and abuse them for command-and-control).

Each malware set we have observed so far communicates with a different CloudMe account though. The attackers upload data to the account, which is downloaded by the implant, decrypted and interpreted. In turn, the malware uploads the replies back to the server via the same mechanism. Of course, it should be possible to reconfigure the malware to use any Cloud-based storage service that supports WebDAV.
Here’s a look at one such account from CloudMe:

The data from the account:

The files stored in the randomly named folder were uploaded by the malware and contain various things, such as system information, running processes and current username. The data is compressed with LZMA and encrypted with AES, however, the keys are stored in the malware body which makes it possible to decrypt the information from the C&C.
We previously observed only one other group using a similar method – ItaDuke – that connected to accounts on the cloud provider mydrive.ch.
Victim statistics: top 5 infected countries





CloudAtlas
RedOctober


Russia
15
35


Kazakhstan
14
21


Belarus
4
5


India
2
14


Czech Republic
2
 5




Similarities with RedOctober
Just like with RedOctober, the top target of Cloud Atlas is Russia, followed closely by Kazakhstan, according to data from the Kaspersky Security Network (KSN). Actually, we see an obvious overlap of targets between the two, with subtle differences which closely account for the geopolitical changes in the region that happened during the last two years.
Interestingly, some of the spear-phishing documents between Cloud Atlas and RedOctober seem to exploit the same theme and were used to target the same entity at different times.




Cloud Atlas
RedOctober








Both Cloud Atlas and RedOctober malware implants rely on a similar construct, with a loader and the final payload that is stored encrypted and compressed in an external file. There are some important differences though, especially in the encryption algorithms used – RC4 in RedOctober vs AES in Cloud Atlas.
The usage of the compression algorithms in Cloud Altas and RedOctober is another interesting similarity. Both malicious programs share the code for LZMA compression algorithm. In CloudAtlas it is used to compress the logs and to decompress the decrypted payload from the C&C servers, while in Red October the “scheduler” plugin uses it to decompress executable payloads from the C&C.
It turns out that the implementation of the algorithm is identical in both malicious modules, however the way it is invoked is a bit different, with additional input integrity checks added to the CloudAtlas version.

Another interesting similarity between the malware families is the configuration of the build system used to compile the binaries. Every binary created using the Microsoft Visual Studio toolchain has a special header that contains information about the number of input object files and version information of the compilers used to create them, the “Rich” header called so by the magic string that is used to identify it in the file.
We have been able to identify several RedOctober binaries that have “Rich” headers describing exactly the same layout of VC 2010 + VC 2008 object files. Although this doesn’t necessarily mean that the binaries were created on the same development computer, they were definitely compiled using the same version of the Microsoft Visual Studio up to the build number version and using similar project configuration.




Number of object files, CloudAtlas loader
Number of object files, Red October Office plugin
Number of object files,Red October Fileputexec plugin
HEX compiler version
Decoded compiler version


01
01
01
009D766F
VC 2010 (build 30319)


01
01
01
009B766F
VC 2010 (build 30319)


22
2E
60
00AB766F
VC 2010 (build 30319)


5B
60
A3
00010000
–


05
07
11
00937809
VC 2008 (build 30729)


72
5C
AD
00AA766F
VC 2010 (build 30319)


20
10
18
009E766F
VC 2010 (build 30319)




To summarize the similarities between the two:





Cloud Atlas
RedOctober


Shellcode marker in spearphished documents
PT@T
PT@T


Top target country
Russia
Russia


Compression algorithm used for C&C communications
LZMA
LZMA


C&C servers claim to be / redirect to
BBC (mobile malware)
BBC


Compiler version
VC 2010 (build 30319)
VC 2010 (build 30319) (some modules)




Finally, perhaps the strongest connection comes from targeting. Based on observations from KSN, some of the victims of RedOctober are also being targeted by CloudAtlas. In at least one case, the victim’s computer was attacked only twice in the last two years, with only two malicious programs – RedOctober and Cloud Atlas.
These and other details make us believe that CloudAtlas represents a rebirth of the RedOctober attacks.
Conclusion
Following big announcements and public exposures of targeted attack operations, APT groups behave in a predictable manner. Most Chinese-speaking attackers simply relocate C&C servers to a different place, recompile the malware and carry on as if nothing happened.
Other groups that are more nervous about exposure go in a hibernation mode for months or years. Some may never return using the same tools and techniques.
However, when a major cyber-espionage operation is exposed, the attackers are unlikely to completely shut down everything. They simply go offline for some time, completely reshuffle their tools and return with rejuvenated forces.
We believe this is also the case of RedOctober, which makes a classy return with Cloud Atlas.
Kaspersky products detect the malware from the Cloud Atlas toolset with the following verdicts:
Exploit.Win32.CVE-2012-0158.j
Exploit.Win32.CVE-2012-0158.eu
Exploit.Win32.CVE-2012-0158.aw
Exploit.MSWord.CVE-2012-0158.ea
HEUR:Trojan.Win32.CloudAtlas.gen
HEUR:Trojan.Win32.Generic
HEUR:Trojan.Script.Generic
Trojan-Spy.Win32.Agent.ctda
Trojan-Spy.Win32.Agent.cteq
Trojan-Spy.Win32.Agent.ctgm
Trojan-Spy.Win32.Agent.ctfh
Trojan-Spy.Win32.Agent.cter
Trojan-Spy.Win32.Agent.ctfk
Trojan-Spy.Win32.Agent.ctfj
Trojan-Spy.Win32.Agent.crtk
Trojan-Spy.Win32.Agent.ctcz
Trojan-Spy.Win32.Agent.cqyc
Trojan-Spy.Win32.Agent.ctfg
Trojan-Spy.Win32.Agent.ctfi
Trojan-Spy.Win32.Agent.cquy
Trojan-Spy.Win32.Agent.ctew
Trojan-Spy.Win32.Agent.ctdg
Trojan-Spy.Win32.Agent.ctlf
Trojan-Spy.Win32.Agent.ctpz
Trojan-Spy.Win32.Agent.ctdq
Trojan-Spy.Win32.Agent.ctgm
Trojan-Spy.Win32.Agent.ctin
Trojan-Spy.Win32.Agent.ctlg
Trojan-Spy.Win32.Agent.ctpd
Trojan-Spy.Win32.Agent.ctps
Trojan-Spy.Win32.Agent.ctpq
Trojan-Spy.Win32.Agent.ctpy
Trojan-Spy.Win32.Agent.ctie
Trojan-Spy.Win32.Agent.ctcz
Trojan-Spy.Win32.Agent.ctgz
Trojan-Spy.Win32.Agent.ctpr
Trojan-Spy.Win32.Agent.ctdp
Trojan-Spy.Win32.Agent.ctdr
Trojan.Win32.Agent.idso
Trojan.Win32.Agent.idrx
HEUR:Trojan.Linux.Cloudatlas.a
Trojan.AndroidOS.Cloudatlas.a
Trojan.IphoneOS.Cloudatlas.a
 
Parallel research:

Blue Coat Exposes Inception Framework








APT
Cyber espionage
Malware Descriptions
Targeted attacks
Trojan-Spy



Authors




GReAT





Cloud Atlas: RedOctober APT is back in style 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







kathy-tom thuma 


							Posted on							December 12, 2014. 1:31 am 



how about using a previous windows set point?
Reply 








Costin Raiu 


							Posted on							December 22, 2014. 12:13 pm 



Hi Kathy,
Could you please explain what you mean by that in the context of the article? TIA
Reply 





















Table of Contents





Meet Cloud AtlasC&C communicationVictim statistics: top 5 infected countriesSimilarities with RedOctoberConclusionParallel research: 





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




 


APT trends report Q2 2021 






 


Arrests of members of Tetrade seed groups Grandoreiro and Melcoz 






 


Ferocious Kitten: 6 years of covert surveillance in Iran 






 


Bizarro banking Trojan expands its attacks to Europe 






 


APT trends report Q1 2021 









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



























