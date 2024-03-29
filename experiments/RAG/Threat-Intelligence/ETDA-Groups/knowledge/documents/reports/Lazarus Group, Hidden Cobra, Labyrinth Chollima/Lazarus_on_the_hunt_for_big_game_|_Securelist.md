# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: Lazarus on the hunt for big game | Securelist

**Source**: https://securelist.com/lazarus-on-the-hunt-for-big-game/97757/

## Content















Lazarus on the hunt for big game | Securelist


































































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

Lazarus on the hunt for big game 

APT reports

28 Jul 2020

  minute read								








 

Authors



 Ivan Kwiatkowski



 Pierre Delcher




Félix Aime





We may only be six months in, but there’s little doubt that 2020 will go down in history as a rather unpleasant year. In the field of cybersecurity, the collective hurt mostly crystallized around the increasing prevalence of targeted ransomware attacks. By investigating a number of these incidents and through discussions with some of our trusted industry partners, we feel that we now have a good grasp on how the ransomware ecosystem is structured.

Structure of the ransomware ecosystem
Criminals piggyback on widespread botnet infections (for instance, the infamous Emotet and Trickbot malware families) to spread into the network of promising victims and license ransomware “products” from third-party developers. When the attackers have a good understanding of the target’s finances and IT processes, they deploy the ransomware on all the company’s assets and enter the negotiation phase.
This ecosystem operates in independent, highly specialized clusters, which in most cases have no links to each other beyond their business ties. This is why the concept of threat actors gets fuzzy: the group responsible for the initial breach is unlikely to be the party that compromised the victim’s Active Directory server, which in turn is not the one that wrote the actual ransomware code used during the incident. What’s more, over the course of two incidents, the same criminals may switch business partners and could be leveraging different botnet and/or ransomware families altogether.
But of course, no complex ecosystem could ever be described by a single, rigid set of rules and this one is no exception. In this blog post, we describe one of these outliers over two separate investigations that occurred between March and May 2020.
Case #1: The VHD ransomware
This first incident occurred in Europe and caught our attention for two reasons: it features a ransomware family we were unaware of, and involved a spreading technique reminiscent of APT groups (see the “spreading utility” details below). The ransomware itself is nothing special: it’s written in C++ and crawls all connected disks to encrypt files and delete any folder called “System Volume Information” (which are linked to Windows’ restore point feature). The program also stops processes that could be locking important files, such as Microsoft Exchange and SQL Server. Files are encrypted with a combination of AES-256 in ECB mode and RSA-2048. In our initial report published at the time we noted two peculiarities with this program’s implementation:

The ransomware uses Mersenne Twister as a source of randomness, but unfortunately for the victims the RNG is reseeded every time new data is consumed. Still, this is unorthodox cryptography, as is the decision to use the “electronic codebook” (ECB) mode for the AES algorithm. The combination of ECB and AES is not semantically secure, which means the patterns of the original clear data are preserved upon encryption. This was reiterated by cybersecurity researchers who analyzed Zoom security in April 2020.
VHD implements a mechanism to resume operations if the encryption process is interrupted. For files larger than 16MB, the ransomware stores the current cryptographic materials on the hard drive, in clear text. This information is not deleted securely afterwards, which implies there may be a chance to recover some of the files.


The Mersenne Twister RNG is reseeded every time it is called.
To the best of our knowledge, this malware family was first discussed publicly in this blog post.
A spreading utility, discovered along the ransomware, propagated the program inside the network. It contained a list of administrative credentials and IP addresses specific to the victim, and leveraged them to brute-force the SMB service on every discovered machine. Whenever a successful connection was made, a network share was mounted, and the VHD ransomware was copied and executed through WMI calls. This stood out to us as an uncharacteristic technique for cybercrime groups; instead, it reminded us of the APT campaigns Sony SPE, Shamoon and OlympicDestroyer, three previous wipers with worming capabilities.
We were left with more questions than answers. We felt that this attack did not fit the usual modus operandi of known big-game hunting groups. In addition, we were only able to find a very limited number of VHD ransomware samples in our telemetry, and a few public references. This indicated that this ransomware family might not be traded widely on dark market forums, as would usually be the case.
Case #2: Hakuna MATA
A second incident, two months later, was handled by Kaspersky’s Incident Response team (GERT). That meant we were able to get a complete picture of the infection chain leading to the installation of the VHD ransomware.

In this instance, we believe initial access was achieved through opportunistic exploitation of a vulnerable VPN gateway. After that, the attackers obtained administrative privileges, deployed a backdoor on the compromised system and were able to take over the Active Directory server. They then deployed the VHD ransomware to all the machines in the network. In this instance, there was no spreading utility, but the ransomware was staged through a downloader written in Python that we still believe to be in development. The whole infection took place over the course of 10 hours.
A more relevant piece of information is that the backdoor used during this incident is an instance of a multiplatform framework we call MATA (some vendors also call it Dacls). On July 22, we published a blog article dedicated to this framework. In it, we provide an in-depth description of its capabilities and provide evidence of its links to the Lazarus group. Other members of the industry independently reached similar conclusions.
The forensics evidence gathered during the incident response process is strong enough that we feel comfortable stating with a high degree of confidence that there was only a single threat actor in the victim’s network during the time of the incident.
Conclusion
The data we have at our disposal tends to indicate that the VHD ransomware is not a commercial off-the-shelf product; and as far as we know, the Lazarus group is the sole owner of the MATA framework. Hence, we conclude that the VHD ransomware is also owned and operated by Lazarus.
Circling back to our introduction, this observation is at odds with what we know about the cybercrime ecosystem. Lazarus has always existed at a special crossroads between APT and financial crime, and there have long been rumors in the threat intelligence community that the group was a client of various botnet services. We can only speculate about the reason why they are now running solo ops: maybe they find it difficult to interact with the cybercrime underworld, or maybe they felt they could no longer afford to share their profits with third parties.
It’s obvious the group cannot match the efficiency of other cybercrime gangs with their hit-and-run approach to targeted ransomware. Could they really set an adequate ransom price for their victim during the 10 hours it took to deploy the ransomware? Were they even able to figure out where the backups were located? In the end, the only thing that matters is whether these operations turned a profit for Lazarus.
Only time will tell whether they jump into hunting big game full time, or scrap it as a failed experiment.
Indicators of compromise
The spreader utility contains a list of administrative credentials and IP addresses specific to the victim, which is why it’s not listed in the IoC section.
As the instance of the MATA framework was extracted from memory, no relevant hashes can be provided for it in the IoC section.
VHD ransomware
6D12547772B57A6DA2B25D2188451983
D0806C9D8BCEA0BD47D80FA004744D7D
DD00A8610BB84B54E99AE8099DB1FC20
CCC6026ACF7EADADA9ADACCAB70CA4D6
EFD4A87E7C5DCBB64B7313A13B4B1012
Domains and IPs
172.93.184[.]62                  MATA C2
23.227.199[.]69                  MATA C2
104.232.71[.]7                     MATA C2
mnmski.cafe24[.]com       Staging endpoint for the ransomware (personal web space hosted at a legit web service and used                                                as a redirection to another compromised legit website).






Botnets
Cybercrime
Lazarus
Malware Descriptions
Malware Technologies
Ransomware
Targeted attacks



Authors



 Ivan Kwiatkowski



 Pierre Delcher




Félix Aime





Lazarus on the hunt for big game 
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




 


Tomiris called, they want their Turla malware back 






 


VileRAT: DeathStalker’s continuous strike at foreign and cryptocurrency exchanges 






 


The SessionManager IIS backdoor 






 


‘Unpacking’ technical attribution and challenges for ensuring stability in cyberspace 






 


Extracting type information from Go binaries 









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



























