# Reference for threat actor for "Slingshot"

**Title**: The Slingshot APT FAQ | Securelist

**Source**: https://securelist.com/apt-slingshot/84312/

## Content















The Slingshot APT FAQ | Securelist



































































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

The Slingshot APT FAQ 

APT reports

09 Mar 2018

  minute read								








 

Authors



 Alexey Shulmin




Sergey Yunakovsky




Vasily Berdnikov




Andrey Dolgushev





While analysing an incident which involved a suspected keylogger, we identified a malicious library able to interact with a virtual file system, which is usually the sign of an advanced APT actor. This turned out to be a malicious loader internally named ‘Slingshot’, part of a new, and highly sophisticated attack platform that rivals Project Sauron and Regin in complexity.
The initial loader replaces the victim´s legitimate Windows library ‘scesrv.dll’ with a malicious one of exactly the same size. Not only that, it interacts with several other modules including a ring-0 loader, kernel-mode network sniffer, own base-independent packer, and virtual filesystem, among others.

While for most victims the infection vector for Slingshot remains unknown, we were able to find several cases where the attackers got access to Mikrotik routers and placed a component downloaded by Winbox Loader, a management suite for Mikrotik routers. In turn, this infected the administrator of the router.
We believe this cluster of activity started in at least 2012 and was still active at the time of this analysis (February 2018).
Why did you call the intruder Slingshot?
The name appears unencrypted in some of the malicious samples – it is the name of one of the threat actor’s components, so we decided to extend it to the APT as a whole.
When was Slingshot active?
The earliest sample we found was compiled in 2012 and the threat was still active in February 2018.
How did the threat attack and infect its victims?
Slingshot is very complex and the developers behind it have clearly spent a great deal of time and money on its creation. Its infection vector is remarkable – and, to the best of our knowledge, unique.
We believe that most of the victims we observed appeared to have been initially infected through a Windows exploit or compromised Mikrotik routers.

How exactly does infection happen?
The exact method used by Slingshot to exploit the routers in the first instance is not yet clear. When the target user runs Winbox Loader software (a utility used for Mikrotik router configuration), this connects to the router and downloads some DLLs (dynamic link libraries) from the router’s file system.
One of them – ipv4.dll – has been placed by the APT with what is, in fact, a downloader for other malicious components. Winbox Loader downloads this ipv4.dll library to the target’s computer, loads it in memory and runs it.
This DLL then connects to a hardcoded IP and port (in every cases we saw it was the router’s IP address), downloads the other malicious components and runs them.
To run its code in kernel mode in the most recent versions of operating systems, that have Driver Signature Enforcement, Slingshot loads signed vulnerable drivers and runs its own code through their vulnerabilities. .
Following infection, Slingshot would load a number of modules onto the victim device, including two huge and powerful ones: Cahnadr, the kernel mode module, and GollumApp, a user mode module. The two modules are connected and able to support each other in information gathering, persistence and data exfiltration.
The most sophisticated module is GollumApp. This contains nearly 1,500 user-code functions and provides most of the above described routines for persistence, file system control and C&C communications.
Canhadr, also known as NDriver, contains low-level routines for network, IO operations and so on. Its kernel-mode program is able to execute malicious code without crashing the whole file system or causing Blue Screen – a remarkable achievement. Written in pure C language, Canhadr/Ndriver provides full access to the hard drive and operating memory despite device security restrictions, and carries out integrity control of various system components to avoid debugging and security detection.
Are Mikrotik the only affected routers?
Some victims may have been infected through other routes. During our research we also found a component called KPWS that turned out to be another downloader for Slingshot components.
Did you inform the affected vendor?
Although the available intelligence is limited and we are not sure what kind of exploit was used to infect routers, we provided Mikrotik with all information available.
What can users of Mikrotik routers do to protect themselves?
Users of Mikrotik routers should upgrade to the latest software version as soon as possible to ensure protection against known vulnerabilities. Further, Mikrotik Winbox no longer downloads anything from the router to the user’s computer.
What are the advantages of achieving kernel mode?
It gives intruders complete control over the victim computer. In kernel mode malware can do everything. There are no restrictions, no limitations, and no protection for the user (or none that the malware can’t easily bypass).

What kind of information does Slingshot appear to be looking for?
Slingshot’s main purpose seems to be cyber-espionage. Analysis suggests it collects screenshots, keyboard data, network data, passwords, USB connections, other desktop activity, clipboard and more. But with full access to the kernel part of the system, it can steal whatever it wants – credit card numbers, password hashes, social security account numbers – any type of data.
How did Slingshot avoid detection?
The threat actor combined a number of known approaches to protect it very effectively from detection: including encrypting all strings in its modules, calling system services directly in order to bypass security-product hooks, using a number of Anti-bug techniques, and more.
Further, it can shut down its components, but ensure they complete their tasks before closing. This process is triggered when there are signs of an imminent in-system event, such as a system shutdown, and is probably implemented to allow user-mode components of the malware to complete their tasks properly to avoid detection during any forensic research.
You said that it disables disk defragmentation module in Windows OS. Why?
This APT uses its own encrypted file system and this can be located among others in an unused part of a hard drive. During defragmentation, the defrag tool relocates data on disk and this tool can write something to sectors where Slingshot keeps its file systems (because the operating system thinks these sectors are free). This will damage the encrypted file system. We suspect that Slingshot tries to disable defragmentation of these specific areas of the hard drive in order to prevent this from happening.
How does it exfiltrate data?
The malware exfiltrates data through standard networks channels, hiding the traffic being extracted by hooking legitimate call-backs, checking for Slingshot data packages and showing the user (and users’ programs like sniffers and so on) clear traffic without exfiltrated data.
Does it use exploits to zero-day vulnerabilities? Any other exploits?
We haven’t seen Slingshot exploit any zero-days, but that doesn’t mean that it doesn’t – that part of a story is still unclear for us. But it does exploit known vulnerabilities in drivers to pass executable code into kernel mode. These vulnerabilities include CVE-2007-5633; CVE-2010-1592, CVE-2009-0824.
What is the victim profile and target geography?
So far, researchers have seen around 100 victims of Slingshot and its related modules, located in Kenya, Yemen, Afghanistan, Libya, Congo, Jordan, Turkey, Iraq, Sudan, Somalia and Tanzania. Most of the victims appear to be targeted individuals rather than organizations, but there are some government organizations and institutions. Kenya and the Yemen account for most of the victims observed to date.

What do we know about the group behind Slingshot?
The malicious samples investigated by the researchers were marked as ‘version 6.x’, which suggests the threat has existed for a considerable length of time. The development time, skill and cost involved in creating Slingshot’s complex toolset is likely to have been extremely high. Taken together, these clues suggest that the group behind Slingshot is likely to be highly organized and professional and probably state-sponsored.
Text clues in the code suggest it is English-speaking. Some of the techniques used by Slingshot, such as the exploitation of legitimate, yet vulnerable drivers has been seen before in other malware, such as White and Grey Lambert. However, accurate attribution is always hard, if not impossible to determine, and increasingly prone to manipulation and error.
Read more in our technical paper.






APT
Malware Descriptions
Vulnerabilities and exploits



Authors



 Alexey Shulmin




Sergey Yunakovsky




Vasily Berdnikov




Andrey Dolgushev





The Slingshot APT FAQ 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Michael Jordan 


							Posted on							March 12, 2018. 12:11 pm 



I know the Technicolor TC8717T Wireless Telephony DOCSIS 3.0 Modem, 4 Port Router which comes with ISP Xfinity, has been harnessed this attack. The malicious code has infected my personal network. I have logs and other detailed in-depth information gathered from my personal analysis. The ISP Xfinity (Comcast) would eventually confirm that my network had been compromised, but would not go as far as to agree to the nature of the attack and/or anything that would show incompetence on their end.
Reply 








FkucTard5000 


							Posted on							March 13, 2018. 3:41 pm 



You expect your ISP to admit they have a large scale problem on their hands?
I think not.
Reply 








Alexey Shulmin 


							Posted on							March 16, 2018. 11:09 am 



Hi, Michael!
Interesing! Do you think you could share all collected information with us? We need it to continue our research. If yes, please contact me via Alexey[dot]Shulmin[at]kaspersky[dot[com
Thank you!
Reply 








Albert Stein 


							Posted on							March 19, 2018. 10:13 am 



That strange: The infection goes router->management app in computer and since the TC8717T has NO management app (is managed via WEB interface) I can’t see how your network has been infected. 
The vulnerability analysis clearly states that “When the target user runs Winbox Loader software (a utility used for Mikrotik router configuration), this connects to the router and downloads some DLLs (dynamic link libraries) from the router’s file system.”
Theres NO Winbox-equivalent app for the TC8717T, so this exploit DOES NOT applies to you. Maybe your network is compromised, but by other means. Please, be precise with your sayings.
Please note: I’m not affiliated in any way to  Xfinity and/or Comcast. Feel free to answer since I’ve leaved my email in case of reply.
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




 


DarkUniverse – the mysterious APT framework #27 






 


Platinum is back 






 


New zero-day vulnerability CVE-2019-0859 in win32k.sys 






 


The fourth horseman: CVE-2019-0797 vulnerability 






 


DarkPulsar FAQ 









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



























