# Reference for threat actor for "Hades"

**Title**: Olympic Destroyer is still alive | Securelist

**Source**: https://securelist.com/olympic-destroyer-is-still-alive/86169/

## Content















Olympic Destroyer is still alive | Securelist


































































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

Hades, the actor behind Olympic Destroyer is still alive 

APT reports

19 Jun 2018

  minute read								








 

Authors




GReAT





In March 2018 we published our research on Olympic Destroyer, an advanced attack that hit organizers, suppliers and partners of the Winter Olympic Games 2018 held in Pyeongchang, South Korea. Olympic Destroyer was a cyber-sabotage attack based on the spread of a destructive network worm. The sabotage stage was preceded by reconnaissance and infiltration into target networks to select the best launchpad for the self-replicating and self-modifying destructive malware.
We are calling the actor behind the Olympic Destroyer attack – “Hades”. We have previously emphasized that Hades is different from other threat actors because the whole attack was a masterful operation in deception. Despite that, the attackers made serious mistakes, which helped us to spot and prove the forgery of rare attribution artefacts. The attackers behind Olympic Destroyer forged automatically generated signatures, known as Rich Header, to make it look like the malware was produced by Lazarus APT, an actor widely believed to be associated with North Korea. If this is new to the reader, we recommend a separate blog dedicated to the analysis of this forgery.
The deceptive behavior of Hades and its excessive use of various false flags, which tricked many researchers in the infosecurity industry, got our attention. Based on malware similarity, the Olympic Destroyer malware was linked by other researchers to three Chinese speaking APT actors and the allegedly North Korean Lazarus APT; some code had hints of the EternalRomance exploit, while other code was similar to the Netya (Expetr/NotPetya) and BadRabbit targeted ransomware. Kaspersky Lab managed to find lateral movement tools and initial infection backdoors, and has followed the infrastructure used to control Olympic Destroyer in one of its South Korean victims.
Some of the TTPs and operational security used by Hades during the Olympic Destroyer attack bear a certain resemblance to Sofacy APT group activity. When it comes to false flags, mimicking TTPs is much harder than tampering with technical artefacts. It implies a deep knowledge of how the actor being mimicked operates as well as operational adaptation to these new TTPs. However, it is important to remember that Hades can be considered a master in the use of false flags: for now we assess that connection with low to moderate confidence.
We decided to keep tracking the Hades group and set our virtual ‘nets’ to catch them again if it showed up with a similar arsenal. To our surprise it has recently resurfaced with new activity.
In May-June 2018 we discovered new spear-phishing documents that closely resembled weaponized documents used by Hades in the past. This and other TTPs led us to believe that we were looking at the same actor again. However, this time the attacker has new targets. According to our telemetry and the characteristics of the analyzed spear-phishing documents, we believe the attackers are now targeting financial organizations in Russia, and biological and chemical threat prevention laboratories in Europe and Ukraine. They continue to use a non-binary executable infection vector and obfuscated scripts to evade detection.
Simplified infection procedure
Infection Analysis
In reality the infection procedure is a bit more complex and relies on multiple different technologies, mixing VBA code, Powershell, MS HTA, with JScript inside and more Powershell. Let’s take a look at this more closely to let incident responders and security researchers recognize such an attack at any time in the future.
One of the recent documents that we discovered had the following properties:
MD5: 0e7b32d23fbd6d62a593c234bafa2311
SHA1: ff59cb2b4a198d1e6438e020bb11602bd7d2510d
File Type: Microsoft Office Word
Last saved date: 2018-05-14 15:32:17 (GMT)
Known file name: Spiez CONVERGENCE.doc
The embedded macro is heavily obfuscated. It has a randomly-generated variable and function name.
Obfuscated VBA macro
Its purpose is to execute a Powershell command. This VBA code was obfuscated with the same technique used in the original Olympic Destroyer spear-phishing campaign.
It starts a new obfuscated Powershell scriptlet via the command line. The obfuscator is using array-based rearranging to mutate original code, and protects all commands and strings such as the command and control (C2) server address.
There is one known obfuscation tool used to produce such an effect: Invoke-Obfuscation.
Obfuscated commandline Powershell scriptlet
This script disables Powershell script logging to avoid leaving traces:

It has an inline implementation of the RC4 routine in Powershell, which is used to decrypt additional payload downloaded from Microsoft OneDrive. The decryption relies on a hardcoded 32-byte ASCII hexadecimal alphabet key. This is a familiar technique used in other Olympic Destroyer spear-phishing documents in the past and in Powershell backdoors found in the infrastructure of Olympic Destroyer’s victims located in Pyeongchang.
[/caption]
The second stage payload downloaded is an HTA file that also executes a Powershell script.
Downloaded access.log.txt
This file has a similar structure to the Powershell script executed by the macro in spear-phishing attachments. After deobfuscating it, we can see that this script also disables Powershell logging and downloads the next stage payload from the same server address. It also uses RC4 with a pre-defined key:

The final payload is the Powershell Empire agent. Below we partially provide the http stager scriptlet for the downloaded Empire agent.

Powershell Empire is a post-exploitation free and open-source framework written in Python and Powershell that allows fileless control of the compromised hosts, has modular architecture and relies on encrypted communication. This framework is widely used by penetration-testing companies in legitimate security tests for lateral movement and information gathering.
Infrastructure
We believe that the attackers used compromised legitimate web servers for hosting and controlling malware. Based on our analysis, the URI path of discovered C2 servers included the following paths:

/components/com_tags/views
/components/com_tags/views/admin
/components/com_tags/controllers
/components/com_finder/helpers
/components/com_finder/views/
/components/com_j2xml/
/components/com_contact/controllers/

These are known directory structures used by a popular open source content management system, Joomla:
Joomla components path on Github
Unfortunately we don’t know what exact vulnerability was exploited in the Joomla CMS. What is known is that one of the payload hosting servers used Joomla v1.7.3, which is an extremely old version of this software, released in November 2011.
A compromised server using Joomla
Victims and Targets
Based on several target profiles and limited victim reports, we believe that the recent operations by Hades target Russia, Ukraine and several other European countries. According to our telemetry, several victims are entities from the financial sector in Russia. In addition, almost all the samples we found were uploaded to a multi-scanner service from European countries such as the Netherlands, Germany and France, as well as from Ukraine and Russia.
Location of targets in recent Hades attacks
Since our visibility is limited, we can only speculate about the potential targets based on the profiles suggested by the content of selected decoy documents, email subjects or even file names picked by the attackers.
One such decoy document grabbed our attention. It referred to ‘Spiez Convergence’, a bio-chemical threat research conference held in Switzerland, organized by SPIEZ LABORATORY, which not long ago was involved in the Salisbury attack investigation.
Decoy document using Spiez Convergence topic
Another decoy document observed in the attacks (‘Investigation_file.doc’) references the nerve agent used to poison Sergey Skripal and his daughter in Salisbury:

Some other spear-phishing documents include words in the Russian and German language in their names:

9bc365a16c63f25dfddcbe11da042974 Korporativ.doc
da93e6651c5ba3e3e96f4ae2dd763d94 Korporativ_2018.doc
e2e102291d259f054625cc85318b7ef5 E-Mail-Adressliste_2018.doc

One of the documents included a lure image with perfect Russian language in it.
A message in Russian encouraging the user to enable macro (54b06b05b6b92a8f2ff02fdf47baad0e)
One of the most recent weaponized documents was uploaded to a malware scanning service from Ukraine in a file named ‘nakaz.zip’, containing ‘nakaz.doc’ (translated as ‘order.doc’ from Ukrainian).
Another lure message to encourage the user to enable macro
According to metadata, the document was edited on June 14th. The Cyrillic messages inside this and previous documents are in perfect Russian, suggesting that it was probably prepared with the help of a native speaker and not automated translation software.
Once the user enables macro, a decoy document is displayed, taken very recently from a Ukrainian state organization (the date inside indicates 11 June 2018). The text of the document is identical to the one on the official website of the Ukrainian Ministry of Health.
Decoy document inside nakaz.doc
Further analysis of other related files suggest that the target of this document is working in the biological and epizootic threat prevention field.
Attribution
Although not comprehensive, the following findings can serve as a hint to those looking for a better connection between this campaign and previous Hades activity. More information on overlaps and reliable tracking of Hades’ attacks is available to subscribers of Kaspersky Intelligence Reporting Services (see below).
Similar obfuscated macro structure
The documents above show apparent structural similarity as if they were produced by the same tool and obfuscator. The highlighted function name in the new wave of attacks isn’t in fact new. While being uncommon, a function named “MultiPage1_Layout” was also found in the Olympic Destroyer spear phishing document (MD5: 5ba7ec869c7157efc1e52f5157705867).
Same MultiPage1_Layout function name used in older campaign
Conclusions
Despite initial expectations for it to stay low or even disappear, Hades, the actor behind the Olympic Destroyer attack, has resurfaced with new attacks in Europe, Russia and Ukraine. In late 2017, a similar reconnaissance stage preceded a larger cyber-sabotage stage meant to destroy and paralyze infrastructure of the Winter Olympic Games as well as related supply chains, partners and even venues at the event location. It’s possible that in this case we have observed a reconnaissance stage that will be followed by a wave of destructive attacks with new motives. That is why it is important for all bio-chemical threat prevention and research companies and organizations in Europe to strengthen their security and run unscheduled security audits.
The variety of financial and non-financial targets could indicate that the same malware was used by several groups with different interests – i.e. a group primarily interested in financial gain through cybertheft and another group or groups looking for espionage targets. This could also be a result of cyberattack outsourcing, which is not uncommon among nation state actors. On the other hand, the financial targets might be another false flag operation by an actor who has already excelled at this during the Pyeongchang Olympics to redirect researchers’ attention.
Certain conclusions could be made based on motives and the selection of targets in this campaign. However, it is easy to make a mistake when trying to answer the question of who is behind this campaign with only the fragments of the picture that are visible to researchers. Hades’ Olympic Destroyer-related activities at the beginning of this year, with their sophisticated deception efforts, changed the attribution game forever. We believe that it is no longer possible to draw conclusions based on few attribution vectors discovered during regular investigation. The resistance to and deterrence of threats such as Olympic Destroyer should be based on cooperation between the private sector and governments across national borders. Unfortunately, the current geopolitical situation in the world only boosts the global segmentation of the internet and introduces many obstacles for researchers and investigators. This will encourage APT attackers to continue marching into the protected networks of foreign governments and commercial companies.
The best thing we can do as researchers is to keep tracking threats like this. We will keep monitoring Hades and report on new discovered activities of this group.
More details about Hades, Olympic Destroyer and related activity are available to subscribers of Kaspersky Intelligence Reporting services. Contact: intelreports@kaspersky.com
Indicators Of Compromise
File Hashes
9bc365a16c63f25dfddcbe11da042974 Korporativ .doc
da93e6651c5ba3e3e96f4ae2dd763d94 Korporativ_2018.doc
6ccd8133f250d4babefbd66b898739b9 corporativ_2018.doc
abe771f280cdea6e7eaf19a26b1a9488 Scan-2018-03-13.doc.bin
b60da65b8d3627a89481efb23d59713a Corporativ_2018.doc
b94bdb63f0703d32c20f4b2e5500dbbe
bb5e8733a940fedfb1ef6b0e0ec3635c recommandation.doc
97ddc336d7d92b7db17d098ec2ee6092 recommandation.doc
1d0cf431e623b21aeae8f2b8414d2a73 Investigation_file.doc
0e7b32d23fbd6d62a593c234bafa2311 Spiez CONVERGENCE.doc
e2e102291d259f054625cc85318b7ef5 E-Mail-Adressliste_2018.doc
0c6ddc3a722b865cc2d1185e27cef9b8
54b06b05b6b92a8f2ff02fdf47baad0e
4247901eca6d87f5f3af7df8249ea825 nakaz.doc
Domains and IPs
79.142.76[.]40:80/news.php
79.142.76[.]40:8989/login/process.php
79.142.76[.]40:8989/admin/get.php
159.148.186[.]116:80/admin/get.php
159.148.186[.]116:80/login/process.php
159.148.186[.]116:80/news.php
****.****.edu[.]br/components/com_finder/helpers/access.log
****.****.edu[.]br/components/com_finder/views/default.php
narpaninew.linuxuatwebspiders[.]com/components/com_j2xml/error.log
narpaninew.linuxuatwebspiders[.]com/components/com_contact/controllers/main.php
mysent[.]org/access.log.txt
mysent[.]org/modules/admin.php
5.133.12[.]224:333/admin/get.php
 
Note: this blogpost was updated July 25, 2019, to include Hades as the name of the actor behind the Olympic Destroyer attack.






APT
Malware Descriptions
Olympic Destroyer
PowerShell
Vulnerabilities and exploits



Authors




GReAT





Hades, the actor behind Olympic Destroyer is still alive 
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



























