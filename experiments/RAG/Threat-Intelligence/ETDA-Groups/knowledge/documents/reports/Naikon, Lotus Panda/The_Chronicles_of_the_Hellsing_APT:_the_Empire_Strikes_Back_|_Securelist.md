# Reference for threat actor for "Naikon, Lotus Panda"

**Title**: The Chronicles of the Hellsing APT: the Empire Strikes Back | Securelist

**Source**: https://securelist.com/the-chronicles-of-the-hellsing-apt-the-empire-strikes-back/69567/

## Content















The Chronicles of the Hellsing APT: the Empire Strikes Back | Securelist




































































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

The Chronicles of the Hellsing APT: the Empire Strikes Back 

APT reports

15 Apr 2015

  minute read								
















Table of Contents





IntroductionThe empire strikes backArtifacts and overlap with other APTsOther toolsAttributionConclusionsDeny the Hellsing APT by defaultAppendix: 






 

Authors



 Costin Raiu




Maxim Golovkin





https://www.youtube.com/watch?v=gvAUfp4iDw4
Introduction
One of the most active APT groups in Asia, and especially around the South China Sea area is “Naikon”.   Naikon plays a key part in our story, but the focus of this report is on another threat actor entirely; one who came to our attention when they hit back at a Naikon attack. 
Naikon is known for its custom backdoor, called RARSTONE, which our colleagues at Trend Micro have described in detail. The name Naikon comes from a custom user agent string, “NOKIAN95/WEB”, located within the backdoor: 

NOKIAN string in Naikon backdoor
The Naikon group is mostly active in countries such as the Philippines, Malaysia, Cambodia, Indonesia, Vietnam, Myanmar, Singapore, and Nepal, hitting a variety of targets in a very opportunistic way. What was perhaps one of the biggest operations of the Naikon group was launched in March 2014, in the wake of the MH370 tragedy that took place on March 8th.  By  March 11th, the Naikon group was actively hitting most of the nations involved in the search for MH370. The targets were extremely wide-ranging but included institutions with access to information related to the disappearance of MH370, such as:

Office of the President
Armed Forces
Office of the Cabinet Secretary
National Security Council(s)
Office of the Solicitor General
National Intelligence Coordinating Agency
Civil Aviation Authority
Department of Justice
National Police
Presidential Management Staff

The Naikon group used mostly spear-phished documents for the attacks, with CVE-2012-0158 exploits that dropped the group’s signature backdoor. 
While many of these attacks were successful, at least one of the targets didn’t seem to like being hit, and instead of opening the documents, decided on a very different course of action.
The empire strikes back
Here’s a question – what should you do when you receiving a suspicious document from somebody you don’t know, or know very little? Choose one:

Open the document
Don’t open the document
Open the document on a Mac (everybody knows Mac’s don’t get viruses)
Open the document in a virtual machine with Linux

Based on our experience, most people would say 2, 3 or 4. Very few would open the document and even fewer would actually decide to test the attacker and verify its story.
But this is exactly what happened when one of the Naikon spear-phishing targets received a suspicious email. Instead of opening the document or choosing to open it on an exotic platform, they decided to check the story with the sender:

Naikon target asks for confirmation of the email
In the email above, we can see the target questioning the authenticity of the Naikon spear-phishing. They ask the sender if it was their intention to email this document.
The attacker was, of course, not confused in the slightest, and being very familiar with the internal structure of the target’s government agency, replied claiming that they work for the secretariat division and were instructed to send it by the organization’s management:

Naikon attacker replies to the target
The reply is written in poor English and indicates that the attacker is probably not as proficient in the language as the intended victim. Seeing the reply, the target obviously decided not to open the document. Moreover, they decided to go a bit further and try to learn more about the attacker.
Not long after the first exchange, the following email was sent to the attacker by the target:

The attachment is a RAR archive with password, which allows it to safely bypass malware scanners associated with the free email account used by the attackers. Inside the archive we find two decode PDF files and one SCR file:

Much to our surprise, the “SCR” file turned out to be a backdoor prepared especially for the Naikon fraudsters. 
The file “Directory of … Mar 31, 2014.scr” (md5: 198fc1af5cd278091f36645a77c18ffa) drops a blank document containing the error message and a backdoor module (md5: 588f41b1f34b29529bc117346355113f). The backdoor connects to the command server located at philippinenews[.]mooo[.]com.
The backdoor can perform the following actions:

download files
upload files
update itself
uninstall itself

We were amazed to see this course of action and decided to investigate the “Empire Strikes Back”-door further; naming the actor “Hellsing” (explained later).
The malware used by the intended victim appears to have the following geographical distribution, according to KSN data:

Malaysia – government networks
Philippines – government networks
Indonesia – government networks
USA – diplomatic agencies
India (old versions of malware)

In addition, we’ve observed the targeting of ASEAN-related entities.

Victims of Hellsing attacks
The actor  targets its intended victims using  spear-phishing emails with archives containing malware, similar to the one it used against the Naikon group. Some of the attachment names we observed include:

2013 Mid-Year IAG Meeting Admin Circular FINAL.7z
HSG FOLG ITEMS FOR USE OF NEWLY PROMOTED YNC FEDERICO P AMORADA 798085 PN CLN.zip
Home Office Directory as of May 2012.Please find attached here the latest DFA directory and key position officials for your referenece.scr
LOI Nr 135-12 re 2nd Quarter.Scr
Letter from Paquito Ochoa to Albert Del Rosario,the Current Secretary of Foreign Affairs of the Philippines.7z
Letter to SND_Office Call and Visit to Commander, United States Pacific Command (USPACOM) VER 4.0.zip
PAF-ACES Fellowship Program.scr
RAND Analytic Architecture for Capabilities Based Planning, Mission System Analysis, and Transformation.scr
Update Attachments_Interaction of Military Personnel with the President _2012_06_28.rar
Update SND Meeting with the President re Hasahasa Shoal Incident.scr
Washington DC Directory November 2012-EMBASSY OF THE PHILIPPINES.zip
ZPE-791-2012&ZPE-792-2012.rar
zpe-791-2012.PDF.scr

We’ve observed RAR, ZIP and 7ZIP archives in the attacks – the 7ZIP archives with passwords were probably introduced as a way to bypass the recent security features on Gmail, which block password-protected archives with executables inside.
Each backdoor has a command and control server inside as well as a version number and a campaign or victim identifier. Some examples include:




MD5
Date
C&C
Campaign identifier


2682a1246199a18967c98cb32191230c
Mar 31 2014
freebsd.extrimtur[.]com
1.6.1_MOTAC


31b3cc60dbecb653ae972db9e57e14ec
Mar 31 2014
freebsd.extrimtur[.]com
1.6.1_MOTAC


4dbfd37fd851daebdae7f009adec3cbd
Nov 08 2013
articles.whynotad[.]com
1.5_articles.whynotad.com-nsc


015915bbfcda1b2b884db87262970a11
Feb 19 2014
guaranteed9.strangled[.]net
1.5_guaranteed9-nsc


3a40e0deb14f821516eadaed24301335
Mar 31 2014
hosts.mysaol[.]com
1.6.1_imi;simple


73396bacd33cde4c8cb699bcf11d9f56
Nov 08 2013
web01.crabdance[.]com
1.5_op_laptop


7c0be4e6aee5bc5960baa57c6a93f420
Nov 08 2013
hosts.mysaol[.]com
1.5_MMEA


bff9c356e20a49bbcb12547c8d483352
Apr 02 2014
imgs09.homenet[.]org
1.6.1_It


c0e85b34697c8561452a149a0b123435
Apr 02 2014
imgs09.homenet[.]org
1.6.1_It


f13deac7d2c1a971f98c9365b071db92
Nov 08 2013
hosts.mysaol[.]com
1.5_MMEA


f74ccb013edd82b25fd1726b17b670e5
May 12 2014
second.photo-frame[.]com
1.6.2s_Ab




The campaign identifiers could be related to the organizations targeted by the specific builds of this APT. Some possible descriptions for these initials could be:

MOTAC – Ministry of Tourism and Culture, Malaysia – http://www.motac.gov.my/en/
NSC – http://www.nsc.gov.my/
MMEA – Malaysian Maritime Enforcement Agency – http://www.mmea.gov.my

Artifacts and overlap with other APTs
Interestingly, some of the infrastructure used by the attackers appears to overlap (although around a year apart) with a group tracked internally at Kaspersky Lab as PlayfullDragon (also known as “GREF”); while other aspects of the infrastructure overlap with a group known as Mirage or Vixen Panda.
For instance, one of the PlayfullDragon’s Xslcmd backdoors described by our colleagues from FireEye (md5: 6c3be96b65a7db4662ccaae34d6e72cc) beams to cdi.indiadigest[.]in:53. One of the Hellsing samples we analysed (md5: 0cbefd8cd4b9a36c791d926f84f10b7b) connects to the C&C server at webmm[.]indiadigest[.]in. Although the hostname is not the same, the top level domain suggests some kind of connection between the groups. Several other C&C subdomains on “indiadigest[.]in” include:

aac.indiadigest[.]in
ld.indiadigest[.]in
longc.indiadigest[.]in

Another overlap we observed is with an APT known as Cycldek or Goblin Panda. Some of the Hellsing samples we analysed in this operation (e.g. md5: a91c9a2b1bc4020514c6c49c5ff84298) communicate with the server webb[.]huntingtomingalls[.]com, using a protocol specific to the Cycldek backdoors (binup.asp/textup.asp/online.asp).
It appears that the Hellsing developer started with the Cycldek sources and worked together with the operators from other APT groups. Nevertheless, it is sufficiently different to warrant classification as a stand-alone operation. 
So, where does the Hellsing name come from? One of the samples we analysed (md5: 036e021e1b7f61cddfd294f791de7ea2) appears to have been compiled in a rush and the attacker forgot to remove the debug information. One can see the project name is Hellsing and the malware is called “msger”:

Of course, Hellsing can have many different meanings, including the famous doctor from Bram Stoker’s Dracula. However, according to Wikipedia, “Hellsing (ヘルシング Herushingu) is also a Japanese manga series written and illustrated by Kouta Hirano. It first premiered in Young King Ours in 1997 and ended in September 2008″.

The Hellsing series chronicles the efforts of the mysterious and secret Hellsing Organization, as it combats vampires, ghouls, and other supernatural foes; which makes it perhaps an appropriate name for our group.
In addition to the Hellsing/msger malware, we’ve identified a second generation of Trojan samples which appear to be called “xweber” by the attackers:

“Xweber” seems to be the more recent Trojan, taking into account compilation timestamps. All the “msger” samples we have seen appear to have been compiled in 2012.  The “Xweber” samples are from 2013 and from 2014, indicating that at some point during 2013 the “msger” malware project was renamed and/or integrated into “Xweber”.
During our investigation we’ve observed the Hellsing APT using both the “Xweber” and “msger” backdoors in their attacks, as well as other tools named “xrat”, “clare”, “irene” and “xKat”.
Other tools
Once the Hellsing attackers compromise a computer, they deploy other tools which can be used for gathering further information about the victim or doing lateral movement. One such tool is “test.exe”:




Name
test.exe


Size
45,568 bytes


MD5
14309b52f5a3df8cb0eb5b6dae9ce4da


Type
Win32 PE i386 executable




This tool is used to gather information and test available proxies. Interestingly, it also contains the Hellsing debug path:

Another attack tool deployed in a victim’s environment was a file system driver, named “diskfilter.sys”, although internally it claims to be named “xrat.sys”. The driver is unsigned and compiled for 32-bit Windows. It was used briefly in 2013, before being abandoned by the attackers, possibly due to Windows 7 driver signing requirements:

Another tool used by the attackers is called “xKat”:




Name
xkat.exe


Size
78,848 bytes


MD5
621e4c293313e8638fb8f725c0ae9d0f


Type
Win32 PE i386 executable




This is a powerful file deletion and process killer which uses a driver (Dbgv.sys) to perform the operations. We’ve seen it being used by the attackers to kill and delete malware belonging to their competitors. 
Some of the debug paths found in the binaries include:

e:\Hellsing\release\clare.pdb
e:\Hellsing\release\irene\irene.pdb
d:\hellsing\sys\irene\objchk_win7_x86\i386\irene.pdb
d:\hellsing\sys\xkat\objchk_win7_x86\i386\xKat.pdb
d:\Hellsing\release\msger\msger_install.pdb
d:\Hellsing\release\msger\msger_server.pdb
d:\hellsing\sys\xrat\objchk_win7_x86\i386\xrat.pdb
D:\Hellsing\release\exe\exe\test.pdb

Attribution
In general, the attribution of APTs is a very tricky task which is why we prefer to publish technical details and allow others to draw their own conclusions.
The Hellsing-related samples appear to have been compiled around the following times:

Assuming normal work starts at around 9 am, the attacker seems to be most active in a time-zone of GMT+8 or +9, considering a work program of 9/10 am to 6/7pm.
Conclusions
The Hellsing APT group is currently active in the APAC region, hitting targets mainly in the South China Sea area, with a focus on Malaysia, the Philippines and Indonesia. The group has a relatively small footprint compared to massive operations such as “Equation“. Smaller groups can have the advantage of being able to stay under the radar for longer periods of time, which is what happened here.
The targeting of the Naikon group by the Hellsing APT is perhaps the most interesting part. In the past, we’ve seen APT groups accidentally hitting each other while stealing address books from victims and then mass-mailing everyone on each of these lists. But, considering the timing and origin of the attack, the current case seems more likely to be an APT-on-APT attack.
To protect against a Hellsing attack, we recommend that organisations follow basic security best practices:

Don’t open attachments from people you don’t know
Beware of password-protected archives which contain SCR or other executable files inside
If you are unsure about the attachment, try to open it in a sandbox
Make sure you have a modern operating system with all patches installed
Update all third party applications such as Microsoft Office, Java, Adobe Flash Player and Adobe Reader

Kaspersky Lab products detect the backdoors used by the Hellsing attacker as: HEUR:Trojan.Win32.Generic, Trojan-Dropper.Win32.Agent.kbuj, Trojan-Dropper.Win32.Agent.kzqq.
Deny the Hellsing APT by default
Appendix:
Hellsing Indicators of Compromise






APT
Social engineering
Targeted attacks
Vulnerabilities and exploits



Authors



 Costin Raiu




Maxim Golovkin





The Chronicles of the Hellsing APT: the Empire Strikes Back 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Lawrence Munro 


							Posted on							April 15, 2015. 7:16 am 



Maybe a slight tangey, but how did they get named ‘Naikon’ from ‘Nokian’. Especially as I think it’s referencing the Nokia N95 which is an old smart phone that is commonly weaponised by pen testers / hackers.
Reply 








assp1r1n3 


							Posted on							July 6, 2016. 7:34 pm 



I’m not aware of any custom firmware for N95, as well as any other Symbian phone, which could have value for pentester/hacker. Perhaps, those phones are _really_ old.
Reply 










Ghost 


							Posted on							April 15, 2015. 6:21 pm 



@Lawrence, reverse the string 🙂
Reply 








Donny 


							Posted on							May 14, 2015. 9:15 am 



NAIKON comes from the HTTP user-agent, which was NOKIAN95.
Reply 



















Table of Contents





IntroductionThe empire strikes backArtifacts and overlap with other APTsOther toolsAttributionConclusionsDeny the Hellsing APT by defaultAppendix: 





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




 


TOP 10 unattributed APT mysteries 






 


Applied YARA training Q&A 






 


PuzzleMaker attacks with Chrome zero-day exploit chain 






 


Looking at Big Threats Using Code Similarity. Part 1 






 


YARA webinar follow up 









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



























