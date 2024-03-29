# Reference for threat actor for "LookBack, TA410"

**Title**: LookBack Forges Ahead: Continued Targeting of the United States’ Utilities Sector Reveals Additional Adversary TTPs | Proofpoint US

**Source**: https://www.proofpoint.com/us/threat-insight/post/lookback-forges-ahead-continued-targeting-united-states-utilities-sector-reveals

## Content































































LookBack Forges Ahead: Continued Targeting of the United States’ Utilities Sector Reveals Additional Adversary TTPs | Proofpoint US









      Skip to main content
    







Products
Solutions
Partners
Resources
Company











English (Americas)
English (Europe, Middle East, Africa)
English (Asia-Pacific)
Español
Deutsch
Français
Italiano
Português
日本語
한국어



Login

Support Log-in
Digital Risk Portal
Email Fraud Defense
ET Intelligence
Proofpoint Essentials
Sendmail Support Log-in


Contact






Aegis Threat Protection PlatformDisarm BEC, phishing, ransomware, supply chain threats and more.
Sigma Information Protection PlatformDefend your data from careless, compromised and malicious users.
Identity Threat Defense PlatformPrevent identity risks, detect lateral movement and remediate identity threats in real time.
Intelligent Compliance PlatformReduce risk, control costs and improve data visibility to ensure compliance.
Premium ServicesLeverage proactive expertise, operational continuity and deeper insights from our skilled experts.





Email Security and Protection
Email Protection
Email Fraud Defense
Secure Email Relay
Threat Response Auto-Pull
Sendmail Open Source
Essentials for Small Business

Advanced Threat Protection
Targeted Attack Protection in Email
Threat Response
Emerging Threats Intelligence

Security Awareness Training
Assess
Change Behavior
Evaluate


Information Protection
Enterprise Data Loss Prevention (DLP)
Insider Threat Management
Intelligent Classification and Protection
Endpoint Data Loss Prevention (DLP)
Email Data Loss Prevention (DLP)
Email Encryption
Data Discover

Cloud Security
Isolation
Cloud App Security Broker
Web Security


Identity Threat Detection and Response
Spotlight
Shadow


Compliance and Archiving
Automate
Capture
Patrol
Track
Archive
Discover
Supervision


Premium Services
Managed Email Threat Protection
Managed Information Protection
Managed Security Awareness
Managed Abuse Mailbox
Recurring Consultative Services
Technical Account Managers
Threat Intelligence Services
People-Centric Security Program






  New threat protection solution bundles with flexible deployment options 
  AI-powered protection against BEC, ransomware, phishing, supplier risk and more with inline+API or MX-based deployment
Learn More






Solutions by Topic


Combat Email and Cloud ThreatsProtect your people from email and cloud threats with an intelligent and holistic approach.
Change User BehaviorHelp your employees identify, resist and report attacks before the damage is done.
Combat Data Loss and Insider RiskPrevent data loss via negligent, compromised and malicious insiders by correlating content, behavior and threats.
Modernize Compliance and ArchivingManage risk and data retention needs with a modern compliance and archiving solution.
Protect Cloud AppsKeep your people and their cloud apps secure by eliminating threats, avoiding data loss and mitigating compliance risk.


Prevent Loss from RansomwareLearn about this growing threat and stop attacks by securing today’s top ransomware vector: email.
Secure Microsoft 365Implement the very best security and compliance solution for your Microsoft 365 collaboration suite.
Defend Your Remote Workforce with Cloud EdgeSecure access to corporate resources and ensure business continuity for your remote workers.
Authenticate Your EmailProtect your email deliverability with DMARC.
Why ProofpointToday’s cyber attacks target people. Learn about our unique people-centric approach to protection.




Solutions by Industry

Federal Government
State and Local Government
Higher Education
Financial Services
Healthcare
Mobile Operators
Internet Service Providers
Small and Medium Businesses






Partner Programs


Channel PartnersBecome a channel partner. Deliver Proofpoint solutions to your customers and grow your business.
Archive Extraction PartnersLearn about Proofpoint Extraction Partners.
Global System Integrator (GSI) and Managed Service Provider (MSP) PartnersLearn about our global consulting and services partners that deliver fully managed and integrated solutions.


Technology and Alliance PartnersLearn about our relationships with industry-leading firms to help protect your people, data and brand.
Social Media Protection PartnersLearn about the technology and alliance partners in our Social Media Protection Partner program.
Proofpoint Essentials Partner ProgramsSmall Business Solutions for channel partners and MSPs.




Partner Tools

Become a Channel Partner
Channel Partner Portal








Resource LibraryFind the information you're looking for in our library of videos, data sheets, white papers and more.
BlogKeep up with the latest news and happenings in the ever‑evolving cybersecurity landscape.
PodcastsLearn about the human side of cybersecurity. Episodes feature insights from experts and executives.
New Perimeters MagazineGet the latest cybersecurity insights in your hands – featuring valuable knowledge from our own industry experts.


Threat GlossaryLearn about the latest security threats and how to protect your people, data, and brand.
EventsConnect with us at events to learn how to protect your people and data from ever‑evolving threats.
Customer StoriesRead how Proofpoint customers around the globe solve their most pressing cybersecurity challenges.
WebinarsBrowse our webinar library to learn about the latest threats, trends and issues in cybersecurity.




Security Hubs

Get free research and resources to help you protect against threats, build a security culture, and stop ransomware in its tracks.

Threat Hub
CISO Hub
Cybersecurity Awareness Hub
Ransomware Hub
Insider Threat Management Hub









About ProofpointProofpoint is a leading cybersecurity company that protects organizations' greatest assets and biggest risks: their people.
Why ProofpointToday’s cyber attacks target people. Learn about our unique people-centric approach to protection.
CareersStand out and make a difference at one of the world's leading cybersecurity companies.


News CenterRead the latest press releases, news stories and media highlights about Proofpoint.
Privacy and TrustLearn about how we handle data and make commitments to privacy and other regulations.
Environmental, Social, and GovernanceLearn about our people-centric principles and how we implement them to positively impact our global community.




Support

Access the full range of Proofpoint support services.
Learn More











 




BlogThreat Insight
                                    LookBack Forges Ahead: Continued Targeting of the United States’ Utilities Sector Reveals Additional Adversary TTPs
                              

 












LookBack Forges Ahead: Continued Targeting of the United States’ Utilities Sector Reveals Additional Adversary TTPs





Share with your network!








 September 23, 2019


                Michael Raggi and the Proofpoint Threat Insight Team
  
        

 Overview
Early in August, Proofpoint described what appeared to be state-sponsored activity targeting the US utilities sector with malware that we dubbed “Lookback” [1]. Between August 21 and August 29, 2019, several spear phishing emails were identified targeting additional US companies in the utilities sector. The phishing emails originated from what appears to be an actor-controlled domain: globalenergycertification[.]net. This domain, like those used in previous campaigns, impersonated a licensing body related to the utilities sector. In this case, it masqueraded as the legitimate domain for Global Energy Certification (“GEC”). The emails include a GEC examination-themed body and a malicious Microsoft Word attachment that uses macros to install and run LookBack.
Phishing tactics, techniques, and procedures (TTPs) observed in these campaigns are consistent with previously reported activity. Persistent targeting of entities in the utilities sector demonstrates the continuing risk to US organizations from the actors responsible for LookBack. Proofpoint has identified at least 17 entities in the US utilities sector targeted by these actors from April 5 through August 29, 2019.
Reconnaissance
Proofpoint analysts have determined that, prior to the initiation of the phishing campaigns described here, threat actors conducted reconnaissance scanning against future targets utilizing a staging IP. This is a newly identified TTP not disclosed in our initial publication regarding LookBack. Scanning activity targets SMB over IP via port 445 up to two weeks prior to the arrival of phishing emails. Observed scanning IPs in some instances have also hosted phishing domains prior to their use in phishing campaigns.
Delivery
Emails delivered between August 21 and August 29, 2019, purported to be an invitation to take the Global Energy Certification (“GEC”) exam administered by the Energy Research and Intelligence Institution. The email utilized the GEC logo and originated from an email address at the domain globalenergycertification[.]net which spoofs the legitimate domain globalenergycertification[.]org. The emails included the subject line “Take the exam now” and a malicious Microsoft Word document attachment named “take the exam now.doc”. This file, like that used in the initial LookBack campaigns, contained VBA macros which led to the installation of LookBack. Unlike earlier campaigns, actors attached a legitimate and benign PDF file for exam preparation which was also hosted on the legitimate GEC site. It is likely that this represents social engineering efforts by the actors to legitimize the email to recipients.

Figure 1: GEC-themed phishing email
The emails originated from the IP address 79.141.169[.]3, which appears to be actor-controlled. An examination of passive DNS and domain registration history for globalenergycertification[.]net indicated that it was previously hosted by the IP 103.253.41[.]75. This staging IP previously hosted the domain NCEESS[.]com observed in historic LookBack phishing campaigns.

IP


Domain


Dates Registered


Impersonated Entity


79.141.169[.]3


globalenergycertification[.]net


August 1 – September 19, 2019


Global Energy Certification (“GEC”)


103.253.41[.]75


globalenergycertification[.]net


June 12 – July 30, 2019


Global Energy Certification (“GEC”)


79.141.168[.]137


nceess[.]com


June 24 – September 19, 2019


National Council of Examiners for Engineering and Surveying


103.253.41[.]75


nceess[.]com


May 29 – June 19, 2019


National Council of Examiners for Engineering and Surveying

Exploitation
The attachments titled “take the exam now.doc” contained VBA macros to install LookBack. The macros were mostly the same as those first observed in July and were similarly obfuscated with concatenation commands that made the macros difficult to detect with static signatures. When a user opens the malicious attachment and enables macros, the VBA macro within the Microsoft Word attachment installs several privacy-enhanced mail (PEM) files on the host.  When decoded, we found these to be both malware modules and macro variables. Tempgup.txt, tempgup2.txt, and tempsodom.txt are LookBack modules. Additionally, the file Temptcm.tmp, which is a version of certutil.exe, is dropped concurrently and will be used to decode the initial files. The macro then decodes the PEM files using Temptcm.tmp. The macro next creates a copy of the decoded PEM files restoring their proper file extensions with the Windows essentuti.exe:
Tempgup.txt becomes GUP.exe, the GUP Proxy tool.
Tempgup2.txt becomes libcurl.dll, a malicious loader.
Tempsodom.txt becomes sodom.txt, which contains command and control configuration data utilized by the SodomNormal module.
These TTPs are consistent with the initial LookBack phishing campaigns observed in July.
We observed an update in the macros used in the August campaigns which differed from earlier versions. The July version of the macro creates macro variables by saving PEM .txt files to the host after they are compiled from text blobs contained within the Microsoft Word attachment macro. These files (pense1.txt, pense2.txt, and pense3.txt) contain macro variables that are referred to when the Word document is opened and macros are enabled:
Pense1.txt contains variables specific to the creation of the GUP proxy tool
Pense2.txt pertains to the libcurl.dll downloader
Pense3.txt appears to be run alongside pense2.txt.
In the newly observed macros identified in August 2019 campaigns, the three pense[*].txt macro variables are replaced with 9 variable files in total. Pense1.txt and pense2.txt appear to remain constant. However, pense3.txt is replaced with seven additional PEM files that are each run alongside Pense2.txt individually. The ultimate result of this macro execution appears to be the installation of LookBack malware modules described above and first observed in July campaigns. However, the method by which this is achieved has been altered in more recent macros. Analysts have not determined the reason for altering this macro but speculate that by increasing the number of variable files and maintaining the core functionality of the macro, actors are attempting to further obfuscate this installation method to avoid detection.
It is notable that additional macro variables were utilized in the installation of the libcurl.dll loader while both the GUP proxy tool and sodom configuration file remained the same. The libcurl.dll module contains the subsequent LookBack modules SodomNormal and SodomMain, which are responsible for configuring the local host proxy and performing remote access Trojan functions. This update may represent an attempt by actors to obscure the installation of second stage payloads. A more thorough description of LookBack module functionality was included in the initial Proofpoint blog on the malware.
The images below offer a comparison of the different macro versions after the majority of concatenation characters have been removed for legibility.
 July 2019 Macro 

Figure 2: July 2019 LookBack Phishing Macro (without concatenation)
August 2019 Macro 

Figure 3: August 2019 LookBack Phishing Macro (without concatenation)
Command and Control Server
Analysts have determined that the LookBack samples from recent campaigns utilize the same command and control (C&C) server, 103.253.41[.]45, observed in July campaigns. The LookBack beacon is identifiable via the URL format below:
C&C host: 103.253.41[.]45 
C&C URL format: http://%s/status[.]gif?r=%d 
Conclusion
Newly discovered LookBack campaigns observed within the US utilities sector provides insight into an ongoing APT campaign with custom malware and a very specific targeting profile. The threat actors demonstrate persistence when intrusion attempts have been foiled and appear to have been undeterred by publications describing their toolset. In addition to the technical commonalities observed, distinct commonalities among the organizations targeted have begun to emerge. The evolution of TTPs including updated macros demonstrates a further departure from tactics previously employed by known APT groups. However, at the current moment, the creators of LookBack malware are yet to depart from their persistent focus on critical infrastructure providers in the United States.    
References
[1]https://www.proofpoint.com/us/threat-insight/post/lookback-malware-targets-united-states-utilities-sector-phishing-attacks
 
Indicators of Compromise (IOCs)

IOC


IOC Type


Description


b5436fcb8243a14f683b5074084bb3d9ff56cad35d2db2fda53a57fa6c42a22b


SHA256


Microsoft Word Attachment - take the exam now.doc
 


0a79e053e1ca809aa4b0393a12ccd547462bd076dbfcd8f6228d08ce0f486afa


SHA256


Benign PDF - GEC-Handbook-Study-Guide-web.pdf


589229e2bd93100049909edf9825dce24ff963a0c465d969027db34e2eb878b4


SHA256


Certutil Tool - Temptcm.tmp


449e1ead309934ac2276a5256cd105dd71d5dd14e49c65bdafc203a0d0eac894


SHA256


Sodom Module Congif - sodom.txt


7e5d2994ac1668178db0ee995cf3b6e4b60d437a09fc10f7afe19b0231615ae2


SHA256


Sodom Modules C2 Config - tempsodom.txt


0f951b7a68e9c0984a0bee3c44e2d64aeac6320bbc2ba2a0f1420893550cf441


SHA256


Gup Proxy – GUP.exe


c87fa8aed595df1dea39a07abdd640842b1c24343841bd72e43668bcfba7eaf1 


SHA256


Libcurl.dll loader – Libcurl.dll


248ff1a9fc2e2c465354f64172224a7c7c0c503cc03ce4524de1a2379692b017


SHA256


Macro Variable - pense1.txt


68ce133d4b18ddbf04da3462891dc04e945e499e8720183448ddf87e408b98a3


SHA256


Macro Variable – pense2.txt


4909d7092a45bc28fa54bb2ef82d426e30a6815fa33a7c00b38b4c3c42960d91


SHA256


Macro Variable – pense31.txt


05f434598b47a63f9f75ae54118fdf5747c02086ff91c1fdc9ac176cd54f102f


SHA256


Macro Variable – pense32.txt


a1bc6922c73726b0ff4e807ea8869ce0dae1b34bd32752f6708750c3f1fc7382


SHA256


Macro Variable – pense33.txt


06c8eb45345684a8d3ce35be695074d371fa9f79e549e39881298f547c9ffd18


SHA256


Macro Variable – pense34.txt


 6e73fd19e883d295c602f1ea349e14a03f8ff47f3dd588683c1f996853a56d98


SHA256


Macro Variable – pense35.txt


bcefb608cc66c93ea42bc5c50903432e6a37466229a534dfeefedfc7c07df1f9


SHA256


Macro Variable – pense36.txt


ff98aea1046dd9f8eda0aa1496660742a4295545d061f811ffa2b45c29fdf4c5


SHA256


Macro Variable – pense37.txt


103.253.41[.]45


IP


C&C IP


79.141.169[.]3


IP


Sender IP


103.253.41[.]75


IP


Staging IP


nceess[.]com


Domain


Phishing Domain


globalenergycertification[.]net


Domain


Phishing Domain

 
ET and ETPRO Suricata/Snort Signatures
2837783 ETPRO TROJAN Win32/LookBack C&C Activity






Previous Blog Post


Next Blog Post







Subscribe to the Proofpoint Blog

























About


Overview
Why Proofpoint
Careers
Leadership Team
News Center
Nexus Platform
Privacy and Trust




Threat Center


Threat Hub
Cybersecurity Awareness Hub
Ransomware Hub
Threat Glossary
Threat Blog








Products


Email Security & Protection
Advanced Threat Protection
Security Awareness Training
Cloud Security
Archive & Compliance
Information Protection
Product Bundles




Resources


White Papers
Webinars
Data Sheets
Events
Customer Stories
Blog
Free Trial








Connect


+1-408-517-4710
Contact Us
Office Locations
Request a Demo




Support


Support Login
Support Services
IP Address Blocked?
















Facebook
Twitter
linkedin
Youtube





English (US)
English (UK)
English (AU)
Español
Deutsch
Français
Italiano
Português
日本語
한국어





© 2024. All rights reserved.
            Terms and conditions
Privacy Policy
Sitemap

 







 

















