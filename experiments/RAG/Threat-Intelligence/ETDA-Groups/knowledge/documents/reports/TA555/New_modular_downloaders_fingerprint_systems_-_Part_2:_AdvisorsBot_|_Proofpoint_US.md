# Reference for threat actor for "TA555"

**Title**: New modular downloaders fingerprint systems - Part 2: AdvisorsBot | Proofpoint US

**Source**: https://www.proofpoint.com/us/threat-insight/post/new-modular-downloaders-fingerprint-systems-part-2-advisorsbot

## Content





























































New modular downloaders fingerprint systems - Part 2: AdvisorsBot | Proofpoint US









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
                                    New modular downloaders fingerprint systems - Part 2: AdvisorsBot
                              

 












New modular downloaders fingerprint systems - Part 2: AdvisorsBot





Share with your network!








 August 23, 2018


                Proofpoint Staff
  
        

 Overview
Beginning in May 2018, Proofpoint researchers observed a previously undocumented downloader dubbed AdvisorsBot appearing in malicious email campaigns. The campaigns appear to primarily target hotels, restaurants, and telecommunications, and are distributed by an actor we track as TA555. To date, we have observed AdvisorsBot used as a first-stage payload, loading a fingerprinting module that, as with Marap, is presumably used to identify targets of interest to further infect with additional modules or payloads. AdvisorsBot is under active development and we have also observed another version of the malware completely rewritten in PowerShell and .NET.
Campaign Analysis
We first observed campaigns delivering AdvisorsBot in May 2018. Since then, the campaigns have used several themes in the email lures. The first is a “double charge” lure that appears to target hotels (Figure 1). The second is a “food poisoning” lure for restaurant targeting (Figure 2). The third is a “catering order” lure also targeting restaurants (Figure 3). The fourth is a “resume” lure that targets telecommunications organizations (Figure 4). While we did observe targeting leaning towards hotels, restaurants, and telecommunications industries, we found that these campaigns were not as well-targeted as the lures might imply, with many messages going to targets unrelated to the contents of the lure.
In the May and June campaigns, the documents contained macros that executed a PowerShell command to download and execute AdvisorsBot. In the August 8 campaign, the actor shifted techniques, using a macro to execute a PowerShell command that in turn downloaded another PowerShell script. This script executed embedded shellcode that ran AdvisorsBot without writing it to disk. Finally, on August 15, the actor made another major change and the macro instead downloaded and executed a PowerShell version of AdvisorsBot that we called PoshAdvisor.

Figure 1: Message purporting to include information about a double charge delivering AdvisorsBot

Figure 2: Message purporting to include information about a food poisoning incident and delivering PoshAdvisor

Figure 3: Message purporting to include information about a catering order and delivering AdvisorsBot

Figure 4: Message purporting to include a resume/CV delivering AdvisorsBot

Figure 5: Example macro document lure  
Malware Analysis
The name “AdvisorsBot” is based on early command and control (C&C) domains that all contained the word “advisors”. The malware is written in C, but the threat actor has recently created an interesting fork of the code that we discuss in the “PoshAdvisor” section.
Anti-Analysis Features
Like most modern malware, AdvisorsBot employs a number of anti-analysis features. One of the most effective is the use of junk code--such as extra instructions, conditional statements, and loops--to considerably slow down reverse engineering. For example, comparing the beginning of a function (part of the URI generation discussed in the “Command and Control” section) from the x86 version of the malware (Figure 6) to the same function in the x64 version (Figure 7) which doesn’t seem to be as affected by the inclusion of the junk code as much.

Figure 6: The x86 version of the malware contains significantly more instances of junk code

Figure 7: The x64 version contains far fewer instances of junk code
We can also see two more anti-analysis features in the same screenshots:
Most strings are stored as “stack strings” in which the characters of the string are manually pushed onto stack memory with individual instructions. This makes it more difficult to quickly see the strings the malware uses.
Windows API function hashing, which hinders identification of the malware’s functionality. A Python implementation of the hashing algorithm is available on Github [1].
To detect various malware analysis tools, AdvisorsBot takes a CRC32 hash of the system’s volume serial number and each running process name and compares them to a list of hardcoded hash values. If it finds a match, the malware exits. To detect whether it is running on a virtual machine, the malware inspects the system’s firmware table (via a call to GetSystemFirmwareTable) for strings associated with virtual machine vendors. Again, if it finds a match, the malware exits.
In the August 8 campaign, it became clear that the threat actor was paying close attention to the characteristics of victims connecting back to their C&C servers. The updated version of AdvisorsBot in this campaign included an additional anti-analysis check that compared the system’s machine SID to a list of 13 hardcoded values (Figure 8). We assume that they have profiled sandbox or malware researcher systems in prior campaigns and blacklisted them.

Figure 8: Snippet of code showing AdvisorsBot comparing the victim machine’s SID to a blacklist
Command and Control
The malware uses HTTPS to communicate with the C&C server. In the requests from the bot to the C&C, URIs contain encoded data that are used to identify a victim, for example:
       /aa/rek5h/lnl5/s4zakljmo/4f/xbdju4a02tnxywx/etl2dni405a1khwxyg0r2.jpg
More specifically, the data that is encoded in the URI contains the machine SID, CRC32 hash of the computer name, some unknown hardcoded values, and the Windows version:

Figure 9: Snippet of code showing the data structure used during formatting of the URI
This data is encoded via the following steps:
Random 4-byte XOR key is generated
Data structure is XOR-encoded with the key and the key is prepended to the encrypted data
The key and encrypted data are converted from binary to lowercase letters and digits with a binary encoding similar to base32
Random slashes are added to make it look like a URI path
A “.jpg” extension is added for GET requests and an “.asp” extension is added for POST requests
Commands from the C&C server are polled via GET requests. A response that contains a command is structured as shown below:
Offset 0: Command
Offset 4: Unknown, possibly module ID or command ID
Offset 8: Length of encrypted data
Offset 12: CRC32 hash of plaintext data
Offset 16: XTEA IV
Offset 24: XTEA key
Offset 40: XTEA encrypted data using CBC mode
AdvisorsBot currently can receive and act on only two commands:
Load a module (command ID 1)
Load shellcode in a thread (any other command ID)
Modules are DLLs that are manually loaded (allocate a buffer, copy the PE header and sections, relocate, resolve the import table, and execute the entry point). A “communications” function is passed from the downloader to the module so that it can send back data to the C&C server. These requests have the same style of URIs, but use POST data structured as shown below:
Offset 0: Length of encrypted data
Offset 4: CRC32 hash of plaintext data
Offset 8: XTEA IV
Offset 16: XTEA key
Offset 32: XTEA encrypted data using CBC mode
Modules
At the time of publication we have only observed a system fingerprinting module being sent from a C&C server. It performs the following activities and sends their output back to the C&C:
Takes a screenshot and base64 encodes it
Extracts Microsoft Outlook account details
Runs the following system commands:
	systeminfo
ipconfig /all
netstat -f
net view
tasklist
whoami
net group "domain admins" /domain
dir %USERPROFILE%\Desktop
wmic /namespace:\\root\securitycenter2 path antivirusproduct GET displayName,pathToSignedProductExe

PoshAdvisor
On August 15, we saw what initially looked like a second AdvisorsBot campaign for the month. However, after closer analysis of the payload we were surprised to find that the threat actor had essentially rewritten AdvisorsBot using PowerShell and a .NET DLL embedded inside the PowerShell script. We track this variant as “PoshAdvisor” and, while it is not an exact duplicate of AdvisorsBot, it does contain the same:
URI generation and format (Figure 10)
C&C response format and encryption
Module download and execute functionality
System fingerprinting functionality (Figure 11)

Figure 10: Snippet of code showing similarity of PoshAdvisor’s URI generation

Figure 11: Snippet of code showing similarity of PoshAdvisor’s system fingerprinting
This is noteworthy since it is fairly rare to see  malware be rewritten in a completely different programming language.
Conclusion
While it remains to be seen whether this threat actor will continue to distribute AdvisorsBot, PoshAdvisor, or both in future campaigns, this pair of downloaders, with extensive anti-analysis features and increasingly sophisticated distribution techniques, warrant further investigation. AdvisorsBot, along with another similar but unrelated malware that we detailed last week, point to a growing trend of small, versatile malware that give actors flexibility to launch future attacks and identify systems of interest that may lend themselves to more significant compromise.
References
[1] https://github.com/EmergingThreats/threatresearch/blob/master/advisorsbot/func_hashes.py
Indicators of Compromise (IOCs)
 

IOC


IOC Type


Description


6d73bea291bf6114af8333031187ac05fdfc8afe05025b272f510a6977b2153e


SHA256


Example Document Attachment (May)


hxxp://chklink[.]us/upd.bin


URL


AdvisorsBot download URL (May)


9dd12d3a32d2ba133bac8747f872f649b389a9cf3f4baaa9fad69a43d2e4f982


SHA256


AdvisorsBot (May)


investments-advisors[.]bid


Domain


AdvisorsBot C&C (May)


interactive-investments[.]bid


Domain


AdvisorsBot C&C (May)


 


 


 


1eb1ef64a9b41267e362597e071e181acb86b50e708ede4a9448689da7fb2425


SHA256


Example Document Attachment (June)


hxxp://finance-advisors-ca[.]bid/ldr.bin


URL


AdvisorsBot download URL (June)


ee32c4e0a4b345029d8b0f5c6534fa9fc41e795cc937d3f3fd743dcb0a1cea35


SHA256


AdvisorsBot (June)


real-estate-advisors[.]win


Domain


AdvisorsBot C&C (June)


secur-real-estate[.]bid


Domain


AdvisorsBot C&C (June)


34a2fc4eb718a8b13a44cfb851ccac6cf63e54fe7e7ab145a5bdeb6def2d4620


SHA256


AdvisorsBot system fingerprinting module (June and August)


 


 


 


956eae6395ed5e1b2d49ffa08ff85b42d1fc210531ab9c48c2d76e6ee38c9781


SHA256


Example Document Attachment (August)


hxxp://204.155.31[.]167/bootstrap.css


URL


AdvisorsBot download URL (August)


c659b00a65a574a08fff64662581a8ecae7eafa38850a6c7c19b88c2085a1c03


SHA256


AdvisorsBot (August)


185.180.198[.]56


IP


AdvisorsBot C&C (August)


 


 


 


fdf5072b904ba9148d8b98e4ba01987e644449e2b10f033ca4d2f967dc502a58


SHA256


Example Document Attachment (August)


hxxp://162.244.32[.]185/jquery.js


URL


PoshAdvisor download URL (August)


2a27d7ad1f16c90767e1cf98c92905aa5a3030a268c8206462c5215a87d0e132


SHA256


PoshAdvisor PowerShell script (August)


335229e528c6348a3dc5941c434dc67acb031f297d9ac25e53a2a56d3df3e255


SHA256


PoshAdvisor .NET library (August)


162.244.32[.]148


IP


PoshAdvisor C&C (August)

ET and ETPRO Suricata/Snort Signatures
2832183 | ETPRO TROJAN PoshAdvisor SSL/TLS Certificate Observed
2830733 || ETPRO TROJAN Observed AdvisorsBot CnC Domain Domain (investments-advisors .bid in TLS SNI)
2830732 || ETPRO TROJAN Observed Malicious SSL Cert (AdvisorsBot CnC Domain)






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

 







 

















