# Reference for threat actor for "Dungeon Spider"

**Title**: Locky: the encryptor taking the world by storm | Securelist

**Source**: https://securelist.com/locky-the-encryptor-taking-the-world-by-storm/74398/

## Content















Locky: the encryptor taking the world by storm | Securelist




































































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

Locky: the encryptor taking the world by storm 

Malware descriptions

06 Apr 2016

  minute read								
















Table of Contents





PropagationGeography of attacksHow it worksFile encryptionRansom demandsCommunication with C&CCountermeasuresPreventing infections 






 

Authors




Fedor Sinitsyn





In February 2016, the Internet was shaken by an epidemic caused by the new ransomware Trojan Locky (detected by Kaspersky Lab products as Trojan-Ransom.Win32.Locky). The Trojan has been actively propagating up to the present day. Kaspersky Lab products have reported attempts to infect users with the Trojan in 114 countries around the world.
Analysis of the samples has shown that this Trojan is a brand new ransomware threat, written from scratch. So, what is Locky, and how can we protect against it?
Propagation
In order to spread the Trojan, cybercriminals sent out mass mailings with malicious loaders attached to spam messages.
Initially, the malicious spam messages contained an attached DOC file with a macro that downloaded the Locky Trojan from a remote server and executed it.

An early-stage spam message with a malicious document attached

A fragment of the malicious macro
Kaspersky Lab products detect files with malicious macros as Trojan-Downloader.MSWord.Agent and HEUR:Trojan-Downloader.Script.Generic.
We should note that in modern versions of Microsoft Office, automatic execution of macros is disabled for security reasons. However, practice shows that users often enable macros manually, even in documents from unknown sources, which may lead to some damaging consequences.
At the time of writing, the malicious spam is still being sent, but instead of the DOC files being attached there are now ZIP archives containing one or more obfuscated scripts in JavaScript. The messages are mostly in English, though some bilingual variants have appeared.

Spam message in English with the archive attached 

Message in German and English with the archive attached 
The user is prompted to manually launch the scripts.

Contents of the archive attached to the message

Fragment of the archived script
When launched, the script downloads the Locky Trojan from a remote server and launches it.
Kaspersky Lab products detect these script loaders as Trojan-Downloader.JS.Agent and HEUR:Trojan-Downloader.Script.Generic.
Geography of attacks
Kaspersky Security Network has reported Locky attacks in 114 countries.
TOP 10 countries



Country
Number of users attacked


France
469


Germany
340


India
267


USA
224


Republic of South Africa
182


Italy
171


Mexico
159


Brazil
156


China
126


Vietnam
107



We should note that these statistics only include cases where the actual Trojan was detected, and does not include early-stage detections reported as malicious spam or malicious downloaders.

The geography of Trojan-Ransom.Win32.Locky attacks (number of attacked users)
As we can see, the Trojan carries out attacks in practically all regions of the world. We can assume which countries the cybercriminals see as their main targets based on the list of languages used on the ransom payment webpage (see details below).
How it works
The Locky Trojan is an executable file, about 100 kb in size. It is written in C++ using STL, and is compiled in Microsoft Visual Studio. When launching, it copies itself to %TEMP%\svchost.exe and deletes the NTFS data stream Zone.Identifier from its copy – this is done to ensure that when the file is launched, Windows does not display a notification saying that the file has been downloaded from the Internet and may be potentially dangerous. The Trojan then launches from %TEMP%.
Once launched, the Trojan checks for the presence and the contents of the below registry keys.



Path
Type
Value


HKEY_CURRENT_USER\Software\Locky\id
REG_SZ
Infection ID


HKEY_CURRENT_USER\Software\Locky\pubkey
REG_BINARY
Public RSA key in MSBLOB format


HKEY_CURRENT_USER\Software\Locky\paytext
REG_BINARY
Text shown to the victim


HKEY_CURRENT_USER\Software\Locky\completed
REG_DWORD
Status (whether encryption is completed)



If data already exists in the registry keys (this is the case if the Trojan has launched before, but its previous session aborted for some reason), Locky reads that data and continues with the infection process.
If launched for the first time, the Trojan performs the following actions:

Contacts C&C and reports infection;
Receives a public RSA-2048 key and infection ID from C&C, saves them in the registry;
Sends information about the language of the infected operating system, receives the cybercriminals’ ransom demand text that will be shown to the victim, saves the text in the registry;
Searches for files with specific extensions on local disk drives, encrypts them;
Deletes shadow copies of files;
Registers itself for autostart (HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run);
Searches for and encrypts files with specific extensions on network drives and on network file resources with no assigned drive letter;
Displays the cybercriminals’ ransom demands to the victim;
Terminates its process and removes itself.


Fragment of code that determines the language of the operating system
File encryption
The Trojan searches for files matching a given list of extensions. Then, these files are encrypted as described below.

List of file extensions that are subject to encryption
For each file that matches an extension on the list, the Trojan generates a new 128-bit key and encrypts the file’s contents with the algorithm AES-128 in CTR mode. The encrypted file is given the name <16 HEX characters as ID><16 random HEX characters>.locky. Then the following structure is added to the end of the file:

Structure appended by the Trojan to the end of an encrypted file
In C language syntax, this structure may be described as follows:


C


struct file_data
{
uint32_t start_marker;          //Structure start marker = 0x8956FE93
char id[16];                    //Infection ID 
uint8_t aes_key[256];           //AES key encrypted with RSA-2048
uint32_t name_marker;           //Name start marker encrypted with AES (= 0xD41BA12A after decryption)
uint8_t orig_name[520];         //Original file name encrypted with AES
WIN32_FILE_ATTRIBUTE_DATA attr; //Original file attributes encrypted with AES
};




123456789

struct file_data{uint32_t start_marker;          //Structure start marker = 0x8956FE93char id[16];                    //Infection ID uint8_t aes_key[256];           //AES key encrypted with RSA-2048uint32_t name_marker;           //Name start marker encrypted with AES (= 0xD41BA12A after decryption)uint8_t orig_name[520];         //Original file name encrypted with AESWIN32_FILE_ATTRIBUTE_DATA attr; //Original file attributes encrypted with AES};



 
Appended structure described in C language syntax
Ransom demands
After encrypting the user’s files, the Trojan displays the following message with the cybercriminals’ ransom demands.

Ransom demand in English

Ransom demand in German
The ransom message contains the address of the cybercriminals’ ‘secret server’ where they placed information about the ransom they demand for the decryption program. All four links in the message lead to the same website in the Tor network.
During the early spamming campaigns, the ransom payment page looked like this:

Early version of Locky’s ransom demand page
On this page, the cybercriminals suggested that the victims pay in bitcoins to decrypt the affected files on their computer. They also gave recommendations about where and how to get the cryptocurrency.
The contents and the design of the page changed with time. Today, the page is available in more than 20 languages (that can be selected from a dropdown list), and looks like this:

Latest version of Locky’s ransom payment page
If we look at the page’s source code, we will see a complete list of supported languages. The cybercriminals obviously see the corresponding countries as the main targets for this ransomware Trojan. Interestingly, Russian and other CIS languages are not on the list. For some reason the cybercriminals are not that keen on targeting users in countries where those languages are spoken – something that KSN statistics confirm.

List of languages supported on Locky ransom payment page
Communication with C&C
The Trojan’s code contains between one and three C&C IP addresses. On top of that, the code contains an algorithm generating new C&C addresses (DGA, domain generation algorithm) depending on the current day, month and year. With this algorithm, six C&C addresses are generated each day. The pseudo-code to illustrate the DGA Locky algorithm is highlighted in the screenshot below.

Pseudo-code of Locky C&C domain generation algorithm
Communication with a C&C is performed using the HTTP protocol. The Trojan sends a POST request to an address with the format http://<cnc_url>/main.php; the transmitted data is encrypted with a simple symmetric algorithm.
Let’s have a look at the possible types of transmitted parameters.


Notification about infection and request for key.id=<infection id>&act=getkey&affid=<partner id contained in the Trojan’s body>&lang=<language of the operating system>&corp=<whether the OS is a corporate OS>&serv=<whether the OS is a server OS>&os=<OS version>&sp=<version of OS service pack>&x64=<whether the OS is 32- or 64-bit>
Judging by the affid parameter, Locky is distributed via an affiliate, or partnership, program.


Sending list of encrypted paths.id=<infection id>&act=report&data=<list of paths>
For each disk drive it has handled, the Trojan sends the C&C a list of all paths to all encrypted files.


Sending statistics for each handled disk drive.id=<infection id>&act=stats&path=<path>&encrypted=<number of files encrypted>&failed=<number of errors>&length=<total size of encrypted files>


It should be noted that the cybercriminal collects very detailed statistics for each infection. Other ransomware families that we analyzed earlier were not this thorough at collecting statistics.
Countermeasures
Kaspersky Lab products protect against the Locky ransomware Trojan at all stages of the attack:

The anti-spam module detects emails sent by the Trojan’s distributors;
Script loaders are detected by static and heuristic signatures of email and file antivirus with the verdicts Trojan-Downloader.MSWord.Agent, Trojan-Downloader.JS.Agent, HEUR:Trojan-Downloader.Script.Generic;
The Trojan’s executable file is detected by file antivirus signatures as Trojan-Ransom.Win32.Locky;
Unknown samples of Locky are proactively detected by the System Watcher module with the verdict PDM:Trojan.Win32.Generic.

Preventing infections
Locky is a typical ransomware Trojan, and it exhibits no major differences from other ransomware families in its internal arrangement or its principles of operation. However, it caught the attention of researchers because it was so active and so widespread. According to KSN data, Kaspersky Lab products have blocked Locky attacks in over 100 countries around the world – no other ransomware Trojan to date has attacked so many countries at once.
To protect yourself from this ransomware Trojan, follow these preventive measures:

Do not open attachments in emails from senders you don’t know;
Back up your files on a regular basis and store the backup copies on removable storage media or in cloud storages – not on your computer;
Regularly run updates for your antivirus databases, operating system and other software installed on your computer;
Create a separate network folder for each user when managing access to shared network folders.

For more detailed information about protection from ransomware Trojans, please follow this link.







Encryption
Macros
Malware Descriptions
Malware Statistics
Malware Technologies
Ransomware
Trojan



Authors




Fedor Sinitsyn





Locky: the encryptor taking the world by storm 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Martin 


							Posted on							April 6, 2016. 3:50 pm 



This is always interesting articles.
I’m really curious on the registry keys, if I create a rule that delete thoses key on creation, what will be the reaction of locky ?
Thanks,
Reply 








Brad 


							Posted on							April 8, 2016. 6:17 pm 



There has been information floating around about a possible vaccine to Locky (https://www.lexsi.com/securityhub/abusing-bugs-in-the-locky-ransomware-to-create-a-vaccine/?lang=en). 
Have you tested to see if these types of fixes are effective?  If so, how difficult will it be for the developers of Locky to get around these preventative measures?
Thanks!
Reply 








Roopi 


							Posted on							June 9, 2016. 6:14 am 



these measures are not really practical in any sense. they are ‘cool’ as they would put our RE skills to test. but that’s really as far as it goes. If you are worried you or your users might be the future target of such ransomwares, you should invest in a proper solution.
Reply 










Andrew 


							Posted on							April 10, 2016. 3:16 pm 



In total, how many infection attempts has the KSN reported todate from this ransonware ?
Reply 








Ido 


							Posted on							April 12, 2016. 12:20 pm 



About a 150 daily infections.
Reply 








Andrew 


							Posted on							April 13, 2016. 11:23 pm 



Are you part of the Kaspersky team ?  
I’ve been seeing all sorts of figures (some very high)  with regards to infection rate. Just wanted to get some hard figures from what KSN has logged so far.
Reply 












Linh 


							Posted on							May 23, 2016. 3:32 am 



I’m an victim of the Locky virus. All of word files and excel files are encrypted to locky file…however, i have forgottent backup, so can you help me decrypt those locky files to word and excel files… Thank you so much.
Reply 








akhil 


							Posted on							May 25, 2016. 7:35 am 



thank you!!!
Reply 








Cihan 


							Posted on							May 28, 2016. 8:57 pm 



good day, is there any solution for .locky files ?
Reply 








Andrew 


							Posted on							June 11, 2016. 3:14 am 



Decryption available yet?
Reply 








Cihan 


							Posted on							June 14, 2016. 9:15 am 



unfo not yet.
Reply 










M. Avis 


							Posted on							August 19, 2016. 7:52 am 



i was told that the the encryption on all my files (ending in ZEPTO) is a version of Locky encryption. is this the case?
Reply 








M.Cihan Erdem 


							Posted on							August 19, 2016. 11:13 am 



yes zepto is latest version of locky ransomware and there is currently no solution.
Reply 










EB 


							Posted on							September 15, 2016. 12:31 pm 



I need a solution to decrypt files attacked by zepto locky ransomware.
Reply 








Barry Reid 


							Posted on							September 15, 2016. 11:22 pm 



I also need a solution to decrypt files attacked by zepto locky ransomware.
Reply 








Mazhar 


							Posted on							September 20, 2016. 9:00 am 



I also need a solution to decrypt files attacked by zepto locky ransomware.
Reply 








Oll 


							Posted on							September 23, 2016. 7:51 pm 



Hello,
I would like to know if there are any news to decrypt zepto files?
I´d rally appreciate feedback!!!
Reply 








Amy 


							Posted on							September 27, 2016. 11:24 pm 



Unfortunately, my parents’ computer has been attacked by zepto.  Luckily, I have an old backup from 2014 which is almost identical to an external drive that was encrypted by Zepto, which is from the penultimate time my parents’ computer died of mysterious reasons (there are more!).  Are there any tools where key-guessing could be employed using a comparison of files in the two drives?  I’m looking to recover their files from late 2014-2016.
Thanks for the article.  I’m trying to get a handle on this.
Reply 








Joanne Zhao 


							Posted on							October 6, 2016. 6:04 am 



I need a solution to decrypt files attacked by odin locky ransomware.
Reply 








dexter23 


							Posted on							October 7, 2016. 10:54 am 



I’m an victim of the Locky virus. All of word files and excel files are encrypted to .odin file.
Reply 








Angelia 


							Posted on							October 15, 2016. 1:29 pm 



Hi,
My PC’s all the excel file was encrypted with *.odin extension.
Please let me know anyway I can restore the file?
Reply 








jason martin 


							Posted on							November 1, 2016. 9:29 pm 



got hit with the .thor extension. any solutions to that
Reply 








Tony Graziano 


							Posted on							November 10, 2016. 4:43 pm 



Jason Martin, Our company’s server got infected with .thor as well.  A careless employee clicked on an email attachment and the trojan was on his computer, but infected the srever as well.  I hope there is a decryption method soon.  All of our companys historical data has been encrypted.
Reply 










Mario 


							Posted on							November 23, 2016. 1:28 am 



Someone who knows that they can already be deciphered .locky, I’m waiting for a tool for my files.
Thank yoy
Reply 








M.Cihan Erdem 


							Posted on							November 24, 2016. 1:00 pm 



As known recently most of users have been infected ransomware virus which changes all important documents like (pdf,doc,docx, xls,xlsx,dwg,mp3,mp4,mpeg,avi,vb) to “.vvv, .ecc, .ezz, .exx, .xyz, .zzz, .aaa, .abc, .ccc, .xxx, .ttt, .micro, .mp3, .xtbl, .cerber, .enc, .encrypted” and no extension on last version” are encrypted and not usable/readable unfortunately. I can help infected users to decrypt their files, you can contact with me with below email address if you or one of your friend had been infected this kind of virus. 
Email: mcerdem82@yahoo.com
Reply 








E.K. 


							Posted on							November 25, 2016. 9:14 am 



Check momoreramsom project for tools
https://www.nomoreransom.org/
Reply 



















Table of Contents





PropagationGeography of attacksHow it worksFile encryptionRansom demandsCommunication with C&CCountermeasuresPreventing infections 





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




 


Ransomware in the CIS 






 


Evolution of JSWorm ransomware 






 


RansomEXX Trojan attacks Linux systems 






 


Life of Maze ransomware 






 


WastedLocker: technical analysis 









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



























