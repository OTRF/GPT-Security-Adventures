# Reference for threat actor for "Dungeon Spider"

**Title**: Locky Ransomware Virus Delivered by Actor Behind Dridex | Proofpoint US

**Source**: https://www.proofpoint.com/us/threat-insight/post/Dridex-Actors-Get-In-the-Ransomware-Game-With-Locky

## Content






























































Locky Ransomware Virus Delivered by Actor Behind Dridex | Proofpoint US









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
                                    Dridex Actors Get In the Ransomware Game With "Locky"
                              

 












Dridex Actors Get In the Ransomware Game With "Locky"





Share with your network!








 February 16, 2016


                Proofpoint Staff
  
        

 Locky Ransomware Overview
Proofpoint researchers have discovered a new ransomware named "Locky" being distributed via MS Word documents with malicious macros. While a variety of new ransomware has appeared since the end of 2015, Locky ransomware stands out because it is being delivered by the same actor behind many of the Dridex malware campaigns we have tracked over the last year.
 
Locky Spam Distribution
As with most malware campaigns this year, actors are distributing Locky ransomware through document attachments spam. In this campaign, messages from random senders with the subject "ATTN: Invoice J-12345678" deliver an attachment "invoice_J-12345678.doc". The attachments are MS Word documents containing macros which download and install the Locky ransomware, first observed by Proofpoint on February 16, 2016.
The botnet (a group of infected machines running a spam bot) delivering the spam is the same botnet that distributes the vast majority of messages bearing the Dridex banking Trojan. In the past, this botnet delivered Dridex botnet IDs 120, 122, 123, 220, 223, 301 (among others), as well as some other non-Dridex malware such as Ursnif (for example on 1-5-2016), Nymaim (12-15-2015), TeslaCrypt (12-14-2015), and Shifu (10-07-2015).

Figure 1 : Email lure associated with Locky
The actors behind the Locky ransomware attack are clearly taking a cue from the Dridex playbook in terms of distribution. Just as Dridex has been pushing the limits of campaign sizes, now we're seeing even higher volumes with Locky, rivaling the largest Dridex campaigns we have observed to date.
Coincidentally, the same day we tracked the large spam campaign, we also spotted Locky ransomware being distributed in a Neutrino thread usually spreading Necurs. When run on the same virtual machine, the document from both the Neutrino drop and the spam emails generate the same individual ID, point to the same Bitcoin wallet, and appear to use the same infrastructure. This can be explained either by a common actor or, more likely, by a distribution in affiliate mode.

Figure 2 : Locky being dropped by the Neutrino EK
When users open the attached document, they must enable macros to be infected.

Figure 3: Attachment showing macro enabling
 
Locky Ransomware
The ransomware encrypts files based on their extension and uses notepad to display the ransom message (Figure 5). Additionally, it replaces the Desktop background with the ransom message (Figure 4). If the user visits the .onion (or tor2web) links specified in the ransom message, s/he is instructed to buy Bitcoins, send them to a certain Bitcoin address, and then refresh the page to wait for the decryptor download. We have not confirmed if the decryptor will actually be provided if the user pays.

Figure 4: Desktop background after Locky is installed

Figure 5: Ransom message displayed in notepad

Figure 6: Decryption website
Locky ransomware encrypts most of the useful file formats on the user's local disk drives; some reports are emerging that Locky also encrypts files on mapped shared drives. The affected file formats are listed below:
.m4u | .m3u | .mid | .wma | .flv | .3g2 | .mkv | .3gp | .mp4 | .mov | .avi | .asf | .mpeg | .vob | .mpg | .wmv | .fla | .swf | .wav | .mp3 | .qcow2 | .vdi | .vmdk | .vmx | .gpg | .aes | .ARC | .PAQ | .tar.bz2 | .tbk | .bak | .tar | .tgz | .gz | .7z | .rar | .zip | .djv | .djvu | .svg | .bmp | .png | .gif | .raw | .cgm | .jpeg | .jpg | .tif | .tiff | .NEF | .psd | .cmd | .bat | .sh | .class | .jar | .java | .rb | .asp | .cs | .brd | .sch | .dch | .dip | .pl | .vbs | .vb | .js | .asm | .pas | .cpp | .php | .ldf | .mdf | .ibd | .MYI | .MYD | .frm | .odb | .dbf | .db | .mdb | .sql | .SQLITEDB | .SQLITE3 | .asc | .lay6 | .lay | .ms11 (Security copy) | .ms11 | .sldm | .sldx | .ppsm | .ppsx | .ppam | .docb | .mml | .sxm | .otg | .odg | .uop | .potx | .potm | .pptx | .pptm | .std | .sxd | .pot | .pps | .sti | .sxi | .otp | .odp | .wb2 | .123 | .wks | .wk1 | .xltx | .xltm | .xlsx | .xlsm | .xlsb | .slk | .xlw | .xlt | .xlm | .xlc | .dif | .stc | .sxc | .ots | .ods | .hwp | .602 | .dotm | .dotx | .docm | .docx | .DOT | .3dm | .max | .3ds | .xml | .txt | .CSV | .uot | .RTF | .pdf | .XLS | .PPT | .stw | .sxw | .ott | .odt | .DOC | .pem | .p12 | .csr | .crt | .key
Locky also appears to generate DGA traffic for command and control (the list of domains below were unregistered at the time of investigation):
vkrdbsrqpi[.]de                               
jaomjlyvwxgdt[.]fr                         
wpogw[.]it                         
ofhhoowfmnuihyd[.]ru
We detected several filesystem IOCs (files, registry keys used for persistence, etc):
Registry: HKCU\Software\Microsoft\Windows\CurrentVersion\Run\Locky
Registry: HKCU\Software\Locky\id
Registry: HKCU\Software\Locky\pubkey
Registry: HKCU\Software\Locky\paytext
File: C:\Users\(username)\AppData\Local\Temp\ladybi.exe
File: C:\Users\(username)\Documents\_Locky_recover_instructions.txt
Command: vssadmin.exe Delete Shadows /All /Quiet
Command: "C:\Windows\system32\NOTEPAD.EXE" C:\Users\Admin\Desktop\_Locky_recover_instructions.txt
As both endpoint and network protection measures become increasingly capable of handling the ransomware that made headlines in the last couple of years (CryptoLocker, CryptoWall, etc.), new variants and strains will continue to emerge. Check back later this week for a complete rundown of several new ransomwares that are making the rounds in the wild.
 
Locky Malware IOCs
Sample hashes
e95cde1e6fa2ce300bf778f3e9f17dfc6a3e499cb0081070ef5d3d15507f367b (Neutrino EK)
5466fb6309bfe0bbbb109af3ccfa0c67305c3464b0fdffcec6eda7fcb774757e (attachment)
Filesystem IOCs (files, registry keys used for persistence, etc):
Registry: HKCU\Software\Microsoft\Windows\CurrentVersion\Run\Locky
Registry: HKCU\Software\Locky\id
Registry: HKCU\Software\Locky\pubkey
Registry: HKCU\Software\Locky\paytext
File: C:\Users\(username)\AppData\Local\Temp\ladybi.exe
File: C:\Users\(username)\Documents\_Locky_recover_instructions.txt
Command: vssadmin.exe Delete Shadows /All /Quiet
Command: "C:\Windows\system32\NOTEPAD.EXE" C:\Users\Admin\Desktop\_Locky_recover_instructions.txt
Payloads downloaded by macro:
[hxxp://www.iglobali[.]com/34gf5y/r34f3345g.exe]
[hxxp://www.southlife[.]church/34gf5y/r34f3345g.exe]
[hxxp://www.villaggio.airwave[.]at/34gf5y/r34f3345g.exe]
[hxxp://www.jesusdenazaret[.]com.ve/34gf5y/r34f3345g.exe]
[hxxp://66.133.129[.]5/~chuckgilbert/09u8h76f/65fg67n]
[hxxp://173.214.183[.]81/~tomorrowhope/09u8h76f/65fg67n]
[hxxp://iynus[.]net/~test/09u8h76f/65fg67n]
Locky C2:
[hxxp://109.234.38[.]35/main.php]
[hxxp://lneqqkvxxogomu[.]eu/main.php]
[hxxp://qpdar[.]pw/main.php]
[hxxp://ydbayd[.]de/main.php]
[hxxp://ssojravpf[.]be/main.php]
[hxxp://gioaqjklhoxf[.]eu/main.php]     
[hxxp://txlmnqnunppnpuq[.]ru/main.php]
Payment URIs (Locky asks user to click these links):
[hxxp://6dtxgqam4crv6rr6.tor2web[.]org]
[hxxp://6dtxgqam4crv6rr6.onion[.]to]
[hxxp://6dtxgqam4crv6rr6.onion[.]cab]
[hxxp://6dtxgqam4crv6rr6.onion[.]link]
[hxxps://6dtxgqam4crv6rr6[.]onion]
 






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

 







 

















