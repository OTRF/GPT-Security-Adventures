# Reference for threat actor for "Tonto Team, HartBeat, Karma Panda"

**Title**: CactusPete APT group’s updated Bisonal backdoor | Securelist

**Source**: https://securelist.com/cactuspete-apt-groups-updated-bisonal-backdoor/97962/

## Content















CactusPete APT group’s updated Bisonal backdoor | Securelist



































































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

CactusPete APT group’s updated Bisonal backdoor 

APT reports

13 Aug 2020

  minute read								
















Table of Contents





What are they looking for?CactusPete activityIn the end…IoCs 






 

Authors



 Konstantin Zykov



The backdoor was used to target financial and military organizations in Eastern Europe


CactusPete (also known as Karma Panda or Tonto Team) is an APT group that has been publicly known since at least 2013. Some of the group’s activities have been previously described in public by multiple sources. We have been investigating and privately reporting on this group’s activity for years as well. Historically, their activity has been focused on military, diplomatic and infrastructure targets in Asia and Eastern Europe.
This is also true of the group’s latest activities.
A new CactusPete campaign, spotted at the end of February 2020 by Kaspersky, shows that the group’s favored types of target remain the same. The victims of the new variant of the Bisonal backdoor, according to our telemetry, were from financial and military sectors located in Eastern Europe. Our research started from only one sample, but by using the Kaspersky Threat Attribution Engine (KTAE) we found 300+ almost identical samples. All of them appeared between March 2019 and April 2020. This underlines the speed of CactusPete’s development – more than 20 samples per month. The target location forced the group to use a hardcoded Cyrillic codepage during string manipulations. This is important, for example, during remote shell functionality, to correctly handle the Cyrillic output from executed commands.
The method of malware distribution for the new campaign remains unknown, but previous campaigns indicate that it’s their usual way of distributing malware. The attackers’ preferred way to deliver malware is spear-phishing messages with “magic” attachments. The attachments never contain zero-day exploits, but they do include recently discovered and patched vulnerabilities, or any other crafty approaches that might help them deliver the payload. Running these attachments leads to infection.
Once the malware starts it tries to reach a hardcoded C2. The communication takes place using the unmodified HTTP-based protocol, the request and response body are RC4-encrypted, and the encryption key is also hardcoded into the sample. As the result of the RC4 encryption may contain binary data, the malware additionally encodes it in BASE64, to match the HTTP specification.





http://C2_DOMAIN_IP/chapter1/user.html/BASE64_RC4_ENCRYPTED_BODY




1

http://C2_DOMAIN_IP/chapter1/user.html/BASE64_RC4_ENCRYPTED_BODY




The handshake consists of several steps: initial request, victim network details and a more detailed victim information request. This is the complete list of victim specific information that is sent to the C2 during the handshake steps:

Hostname, IP and MAC address;
Windows version;
Time set on infected host;
Flags that indicates if the malware was executed on VMware environment;
Proxy usage flag;
System default CodePage Identifier;

After the handshake has been completed, the backdoor waits for a command, periodically pinging the C2 server. The response body from the C2 ping might hold the command and parameters (optionally). The updated Bisonal backdoor version maintains functionality similar to past backdoors built from the same codebase:

Execute a remote shell;
Silently start a program on a victim host;
Retrieve a list of processes from the victim host;
Terminate any process;
Upload/Download/Delete files to/from victim host;
Retrieve a list of available drives from the victim host;
Retrieve a filelist of a specified folder from the victim host;

This is what it looks like in code.

 Screenshot of the C2 command handling subroutine
This set of remote commands helps the attackers study the victim environment for lateral movement and deeper access to the target organization. The group continues to push various custom Mimikatz variants and keyloggers for credential harvesting purposes, along with privilege escalation malware.
What are they looking for?
Since the malware contains mostly information gathering functionality, most likely they hack into organizations to gain access to the victims’ sensitive data. If we recall that CactusPete targets military, diplomatic and infrastructure organizations, the information could be very sensitive indeed.
We would suggest the following countermeasures to prevent such threats:

Network monitoring, including unusual behavior detection;
Up-to-date software to prevent exploitation of vulnerabilities;
Up-to-date antivirus solutions;
Training employees to recognize email-based (social engineering) attacks;

CactusPete activity
CactusPete is a Chinese-speaking cyber-espionage APT group that uses medium-level technical capabilities, and the people behind it have upped their game. They appear to have received support and have access to more complex code like ShadowPad, which CactusPete deployed in 2020. The group’s activity has been recorded since at least 2013, although Korean public resources mark an even earlier date – 2009. Historically, CactusPete targets organizations within a limited range of countries – South Korea, Japan, the US and Taiwan. Last year’s campaigns show that the group has shifted towards other Asian and Eastern European organizations.
Here’s an overview of CactusPete activity in recent years, based on Kaspersky research results:

May 2018: a new wave of targeted attacks abusing CVE-2018-8174 (this exploit has been associated with the DarkHotel APT group, as described on Securelist), with diplomatic, defense, manufacturing, military and government targets in Asia and Eastern Europe;
December 2018 and early 2019: Bisonal backdoor modification with a set of spying payloads in a campaign targeting organizations within mining, defense, government and technology research targets in Eastern Europe and Asia;
September and October 2019: a DoubleT backdoor campaign, targeting military-related and unknown victims;
March 2019 to April 2020: Bisonal backdoor modification in a campaign targeting organizations in financial and military institutions in Eastern Europe;
December 2019 to April 2020: a modified DoubleT backdoor campaign, targeting telecom and governmental organizations and other victims in Asia and Eastern Europe;
Late 2019 and 2020: CactusPete started to deploy ShadowPad malware with victims including government organizations, energy, mining, and defense bodies and telcoms located in Asia and Eastern Europe;

Known alternative names for this APT group:
CactusPete, Karma Panda, Tonto Team
Known alternative names for the different payloads used:
Bisonal, Curious Korlia, DoubleT, DOUBLEPIPE, CALMTHORNE
In the end…
We call CatusPete an Advanced Persistent Threat (APT) group, but the Bisonal code we analyzed is not that advanced. Yet, interestingly, the CactusPete APT group has had success without advanced techniques, using plain code without complicated obfuscation and spear-phishing messages with “magic” attachments as the preferred method of distribution. Of course, the group does continuously modify the payload code, studies the suggested victim in order to craft a trustworthy phishing email, sends it to an existing email address in the targeted company and makes use of new vulnerabilities and other methods to inconspicuously deliver the payload once an attachment has been opened. The infection occurs, not because of advanced technologies used during the attack, but because of those who view the phishing emails and open the attachments. Companies need to conduct spear-phishing awareness training for employees in order to improve their computer security knowledge.
IoCs
PDB path:
E:\vs2010\new big!\MyServe\Debug\MyServe.pdb
MD5:
A3F6818CE791A836F54708F5FB9935F3
3E431E5CF4DA9CAE83C467BC1AE818A0
11B8016045A861BE0518C9C398A79573
Related material:

January 29, 2020
https://nao-sec.org/2020/01/an-overhead-view-of-the-royal-road.html
March 5, 2020
https://blog.talosintelligence.com/2020/03/bisonal-10-years-of-play.html
2019
https://www.fireeye.com/content/dam/fireeye-www/summit/cds-2019/presentations/cds19-executive-s08-achievement-unlocked.pdf
July 31, 2018
https://unit42.paloaltonetworks.com/unit42-bisonal-malware-used-attacks-russia-south-korea/
2017
https://image.ahnlab.com/file_upload/asecissue_files/ASEC_REPORT_vol.88.pdf (Korean language)
2014
https://securitykitten.github.io/2014/11/25/curious-korlia.html
2013
https://web.archive.org/web/20130920120931/https://www.rsaconference.com/writable/presentations/file_upload/cle-t04_final_v1.pdf







Backdoor
Data theft
Malware Descriptions
Malware Technologies
Spear phishing
Targeted attacks



Authors



 Konstantin Zykov





CactusPete APT group’s updated Bisonal backdoor 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Source Link 


							Posted on							April 2, 2021. 2:38 am 



 thanks this really is good blog site. 
Reply 



















Table of Contents





What are they looking for?CactusPete activityIn the end…IoCs 





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




 


DTrack activity targeting Europe and Latin America 






 


How we developed our simple Harbour decompiler 






 


Hello! My name is Dtrack 






 


Criminals, ATMs and a cup of coffee 






 


ATM robber WinPot: a slot machine instead of cutlets 









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



























