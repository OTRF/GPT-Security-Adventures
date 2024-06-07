# Reference for threat actor for "Evilnum"

**Title**: Buy, Sell, Steal, EvilNum Targets Cryptocurrency, Forex, Commodities | Proofpoint US

**Source**: https://www.proofpoint.com/us/blog/threat-insight/buy-sell-steal-evilnum-targets-cryptocurrency-forex-commodities

## Content































































Buy, Sell, Steal, EvilNum Targets Cryptocurrency, Forex, Commodities | Proofpoint US









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
                                    Buy, Sell, Steal, EvilNum Targets Cryptocurrency, Forex, Commodities
                              

 












Buy, Sell, Steal, EvilNum Targets Cryptocurrency, Forex, Commodities





Share with your network!








 July 21, 2022


                Bryan Campbell, Pim Trouerbach, Selena Larson and the Proofpoint Threat Research Team
  
        

 
Key Findings
TA4563 is a threat actor leveraging EvilNum malware to target European financial and investment entities, especially those with operations supporting foreign exchanges, cryptocurrency, and decentralized finance (DeFi).
EvilNum is a backdoor that can be used for data theft or to load additional payloads.
The malware includes multiple interesting components to evade detection and modify infection paths based on identified antivirus software.
Overview
Since late 2021 through the present, Proofpoint Threat Research observed the group Proofpoint calls TA4563 targeting various European financial and investment entities with the malware known as EvilNum. The actor exclusively targeted entities in the Decentralized Finance (DeFi) industry in recently observed campaigns. The activity Proofpoint associates with TA4563 has some overlap with activity publicly associated with a group referred to as DeathStalker and EvilNum. The activity described in this report has some overlap with EvilNum activity publicly reported by Zscaler in June 2022.  
The identified campaigns delivered an updated version of the EvilNum backdoor using a varied mix of ISO, Microsoft Word and Shortcut (LNK) files in late 2021 and early 2022, presumably as a method of testing the efficacy of the delivery methods. This malware can be used for reconnaissance, data theft, and to deploy additional payloads.
Campaign Details
2021 
Proofpoint observed the first campaign in December 2021. The messages purported to be related to financial trading platform registration or related documents. The initial campaign observed included the attempted delivery of Microsoft Word documents responsible for the attempted installation of the updated version of the EvilNum backdoor.
These messages used a remote template document that analysts observed attempting to communicate with domains to install several LNK loader components, leveraging wscript to load the EvilNum payload, and a JavaScript payload that was ultimately installed on the user's host. These lures contained a financial theme, suggesting on one occasion that the intended victim needed to submit “proof of ownership of missing documents”.
Proofpoint identified the following post-infection related domains:
mailgunltd[.]com
azuredllservices[.]com
officelivecloud[.]com

Early 2022 
The group continued to target financial entities with a variation on the original email campaign, attempting to deliver multiple OneDrive URLs that contained either an ISO or .LNK attachment. In identified campaigns, the actor used financial lures to get the recipient to launch the EvilNum payload. Messages purported to be, for example:
           From: “Viktoria Helle” <viktoria.helle79@zingamail[.]uk>
            Subject: Re: Reminder to submit your proof of identity and address
Campaigns continued to target specific European financial and investment entities.
Subsequent campaigns included the delivery of a compressed .LNK file directly as an additional attempt to install EvilNum.
Mid 2022
As the threat actor maintained consistent targeting and victimology, the methodology again changed. In mid-2022 campaigns, TA4563 delivered Microsoft Word documents to attempt to download a remote template.
Messages purported to be, for example:

From: "19steeven " <arfeuille19@gmail[.]com>
Subject: Fwd: KOT4X - Proof of ownership (urgent missing document)
Attachment: steve kot4x.docx
The attached document was responsible for generating traffic to http://outlookfnd[.]com, a likely actor-controlled domain responsible for the EvilNum payload.

Figure 1: Attached Word document delivering EvilNum.
EvilNum Details
Previous versions of EvilNum publicly reported by security organizations include both a JavaScript component and C# component of the backdoor. Proofpoint did not observe a JavaScript component in recent campaigns and analyzed the C# component observed in multiple recent campaigns.  
Each campaign is highly fenced; the malware only allows one download per IP address to ensure only the target host can retrieve the final payload. The initial stage LNK loader is responsible for executing PowerShell via cmd.exe, this then downloads two different payloads from the initial host (e.g. infntio[.]com).
The first payload is responsible for executing two PowerShell scripts.

Figure 2: PowerShell script examples.
The first is used to decrypt a PNG and follows logic to restart the infection chain. The second, larger PowerShell script loads C# code dynamically and sends screenshots to a command-and-control server (C2). This C# application then executes another PowerShell command:
/c start /min \”\” powershell -inputformat none -outputformat none -windowstyle hidden -c \”&hpfde.exe” –v=[Random]
Several applications are executed depending on what antivirus software – either Avast, AVG, or Windows Defender – is found on the host. The malware will try and call multiple executables likely already on the host machine (e.g. TechToolkit.exe and nvapiu.exe). The malware execution chain will change to best evade detection from the identified antivirus engine.

Figure 3: Executables called depending on the antivirus engine identified.
The second payload contains two encrypted blobs. The first is decrypted to an executable, (e.g. hpfde.exe) and the second to a TMP file (e.g. devXYXY5.tmp). The initial executable reads and decrypts the TMP file to load a 53KB shellcode file resulting in a final decrypted and decompressed PE file.
The EvilNum backdoor can be used for reconnaissance and data theft activity and to load follow-on payloads.
Conclusion
EvilNum malware and the TA4563 group poses a risk to financial organizations. Based on Proofpoint analysis, TA4563’s malware is under active development. Although Proofpoint did not observe follow-on payloads deployed in identified campaigns, third-party reporting indicates EvilNum malware may be leveraged to distribute additional malware including tools available via the Golden Chickens malware-as-a-service. TA4563 has adjusted their attempts to compromise the victims using various methods of delivery, whilst Proofpoint observed this activity and provided detection updates to thwart this activity, it should be noted that a persistent adversary will continue to adjust their posture in their compromise attempts.
Indicators Of Compromise
2851693 - ETPRO MALWARE EvilNum Related Domain in DNS Lookup (malware.rules)
2851694 - ETPRO MALWARE EvilNum Related Domain in DNS Lookup (malware.rules)
2851695 - ETPRO MALWARE EvilNum Related Domain in DNS Lookup (malware.rules)
2851696 - ETPRO MALWARE EvilNum Related Domain in DNS Lookup (malware.rules)
2851697 - ETPRO MALWARE EvilNum Related Domain in DNS Lookup (malware.rules)

Indicator


Description


hxxp://officelivecloud[.]com


Payload Domain December 2021 


hxxp://mailgunltd[.]com


Payload Domain December 2021 


hxxp://officelivecloud[.]com


Payload Domain December 2021 


hxxp://visitaustriaislands[.]com


Command and Control Domain May 2022


hxxp://outlookfnd[.]com


Command and Control Domain June 2022


hxxp://infntio[.]com/save/user.php 


Payload URL March 2022


hxxp://advflat[.]com/save/user.php 


Command and Control URL March 2022


hxxp://pngdoma[.]com/admin/index.php


Command and Control URL March 2022


hxxp://goalrom[.]com/admin/settings.php


Command and Control URL March 2022


hxxp://elitefocuc[.]com/save/user.php


Command and Control URL March 2022


hxxp://hubflash[.]co/configuration.php


Command and Control URL April 2022


bookingitnow[.]org


Command and Control Domain


bookaustriavisit[.]com


Command and Control Domain


moretraveladv[.]com


Command and Control Domain


estoniaforall[.]com
 


Command and Control Domain


ef1a660ee8b11bbcf681e8934c5f16e4a249ba214d743bbf8b1f8043296b6ffc


Word Doc SHA256 June 2022


da642cc233ea3595d8aaf8daf6129c59682b19462d5d5abb1f494042d4c044f4


Word Doc SHA256 Sample June 2022


53ade63ba9938fd97542a0a725d82045f362766f24f0b1f414f4693d9919f631


LNK SHA256 Sample March 2022


f0a002c7d2174f2a022d0dfdb0d83973c1dd96c4db86a2b687d14561ab564daa


LNK SHA256 Sample March 2022


53ade63ba9938fd97542a0a725d82045f362766f24f0b1f414f4693d9919f631


Word Doc SHA256 Sample December 2021


649183519d59ea332d687a01c37040b91da69232aadb0c1215c36a5b87ad2ec7


Word Doc SHA256 Sample December 2021


viktoria.helle79@zingamail[.]uk


Sender Email March 2022


paul@christiesrealestate[.]uk


Sender Email December 2021


sherry@schalapartners[.]com


Sender Email March 2022


arfeuille19@gmail[.]com


Sender Email June 2022


arole@delaware-north[.]com


Sender Email May 2022


hxxps://onedrive.live[.]com/download?resid=
			680BC877518B4D11%21388&authkey=!AMMjaIOZSltiS_Q


OneDrive URL March 2022


hxxps://onedrive.live[.]com/download?resid=
			680BC877518B4D11!531&authkey=!ADr0ziYEPBJJK9w


OneDrive URL March 2022


hxxps://onedrive.live[.]com/download?resid=
			680BC877518B4D11!426&authkey=!AB60IPFY2E-XMXs


OneDrive URL March 2022

 


 









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

 







 

















