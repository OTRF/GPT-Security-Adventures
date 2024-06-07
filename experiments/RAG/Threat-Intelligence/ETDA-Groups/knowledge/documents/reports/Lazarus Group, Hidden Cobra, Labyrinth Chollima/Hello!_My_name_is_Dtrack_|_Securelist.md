# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: Hello! My name is Dtrack | Securelist

**Source**: https://securelist.com/my-name-is-dtrack/93338/

## Content















Hello! My name is Dtrack | Securelist




































































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

Hello! My name is Dtrack 

Malware descriptions

23 Sep 2019

  minute read								








 

Authors



 Konstantin Zykov





Our investigation into the Dtrack RAT actually began with a different activity. In the late summer of 2018, we discovered ATMDtrack, a piece of banking malware targeting Indian banks. Further analysis showed that the malware was designed to be planted on the victim’s ATMs, where it could read and store the data of cards that were inserted into the machines. Naturally, we wanted to know more about that ATM malware, so we used YARA and Kaspersky Attribution Engine to uncover more interesting material: over 180 new malware samples of a spy tool that we now call Dtrack.
All the Dtrack samples we initially found were dropped samples, as the real payload was encrypted with various droppers — we were able to find them because of the unique sequences shared by ATMDtrack and the Dtrack memory dumps. After that, it got very interesting, because once we decrypted the final payload and used Kaspersky Attribution Engine again, we saw similarities with the DarkSeoul campaign, dating back to 2013 and attributed to the Lazarus group. It seems that they reused part of their old code to attack the financial sector and research centers in India. According to our telemetry, the last activity of DTrack was detected in the beginning of September 2019.
Technical details
The dropper has its encrypted payload embedded as an overlay of a PE file as extra data that will never be used in normal execution steps. Its decryption routine, part of an executable physical patch, begins somewhere between the start() and WinMain() functions. A fun fact is that the malware authors embedded their malicious code into a binary that was a harmless executable. In some cases, it was the default Visual Studio MFC project, but it could be any other program.
The decrypted overlay data contains the following artifacts:

an extra executable;
process hollowing shellcode;
a list of predefined executable names, which the malware uses as a future process name.

After decryption of the data, the process hollowing code is started, taking the name of the process to be hollowed as an argument. The name comes from the predefined list found within the decrypted overlay. All the names come from the %SYSTEM32% folder, as you can see in the decrypted file list below.

fontview.exe
dwwin.exe
wextract.exe
runonce.exe
grpconv.exe
msiexec.exe
rasautou.exe
rasphone.exe
extrac32.exe
mobsync.exe
verclsid.exe
ctfmon.exe
charmap.exe
write.exe
sethc.exe
control.exe
presentationhost.exe
napstat.exe
systray.exe
mstsc.exe
cleanmgr.exe

What is inside the dropper?
After execution, the target of the process hollowing is suspended until its memory is overwritten with the decrypted executable payload from the dropper overlay. After this, the target process resumes.
The droppers contain a variety of executables, all of these intended for spying on the victim. Below is an incomplete functionality list for the various Dtrack payload executables found:

keylogging,
retrieving browser history,
gathering host IP addresses, information about available networks and active connections,
listing all running processes,
listing all files on all available disk volumes.

At this point, the design philosophy of the framework becomes a bit unclear. Some of the executables pack the collected data into a password protected archive and save it to the disk, while others send the data to the C&C server directly.
Aside from the aforementioned executables, the droppers also contained a remote access Trojan (RAT). The RAT executable allows criminals to perform various operations on a host, such as uploading/downloading, executing files, etc. For a full list of operations, see the table below.



command id
description


1003
upload a file to the victim’s computer


1005
make target file persistent with auto execution on the victim’s host start


1006
download a file from the victim’s computer


1007
dump all disk volume data and upload it to a host controlled by criminals


1008
dump a chosen disk volume and upload it to a host controlled by criminals


1011
dump a chosen folder and upload it to a host controlled by criminals


1018
set a new interval timeout value between new command checks


1023
exit and remove the persistence and the binary itself


default
execute a process on the victim’s host



Dtrack and ATMDTrack malware similarities
ATMDTrack is a subset of the DTrack family. They naturally look different despite their similarities. For example, Dtrack’s payload is encrypted within a dropper—unlike the ATMDTrack samples, which were not encrypted at all. But after decrypting the Dtrack payload, it becomes clear that the developers are the same group of people: both projects have the same style and use the same implemented functions. The most obvious function they have in common is the string manipulation function. It checks if there is a CCS_ substring at the beginning of the parameter string, cuts it out and returns a modified one. Otherwise, it uses the first byte as an XOR argument and returns a decrypted string.
Functions common to the two families (the functions/arguments were named by the researchers)
Conclusions
When we first discovered ATMDtrack, we thought we were just looking at another ATM malware family, because we see new ATM malware families appearing on a regular base. However, this case proved once again that it is important to write proper YARA rules and have a solid working attribution engine, because this way you can uncover connections with malware families that have appeared in the past. One of the most memorable examples of this was the WannaCry attribution case. Now we can add another family to the Lazarus group’s arsenal: ATMDtrack and Dtrack.
The vast amount of Dtrack samples that we were able to find shows that the Lazarus group is one of the most active APT groups in terms of malware development. They continue to develop malware at a fast pace and expand their operations. We first saw early samples of this malware family in 2013, when it hit Seoul. Now, six years later, we see them in India, attacking financial institutions and research centers. And once again, we see that this group uses similar tools to perform both financially-motivated and pure espionage attacks.

To succeed in spying, the criminals should be able to gain at least partial control over the internal network. This means that the target organizations may have a number of security issues, such as:

weak network security policies,
weak password policies,
lack of traffic monitoring.

We therefore advise the companies to:

tighten their network and password policies,
use traffic monitoring software, such as Kaspersky Anti Targeted Attack Platform (KATA),
use antivirus solutions.

IoCs

8f360227e7ee415ff509c2e443370e56
3a3bad366916aa3198fd1f76f3c29f24
F84de0a584ae7e02fb0ffe679f96db8d







ATM
Dropper
Financial malware
Lazarus
Malware Descriptions
RAT Trojan



Authors



 Konstantin Zykov





Hello! My name is Dtrack 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







saassdd 


							Posted on							October 24, 2019. 9:41 am 



I want to know which is Dtrack?  When I debuged 3a3ba…c29f24, then I get the Rat, but where is the Dtrack?  The  Rat  is Dtrack?
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




 


CactusPete APT group’s updated Bisonal backdoor 






 


How we developed our simple Harbour decompiler 






 


Criminals, ATMs and a cup of coffee 






 


ATM robber WinPot: a slot machine instead of cutlets 






 


ATM malware is being sold on Darknet market 









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



























