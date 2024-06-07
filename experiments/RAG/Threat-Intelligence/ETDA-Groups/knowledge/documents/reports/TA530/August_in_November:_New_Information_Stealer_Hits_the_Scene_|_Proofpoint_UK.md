# Reference for threat actor for "TA530"

**Title**: August in November: New Information Stealer Hits the Scene | Proofpoint UK

**Source**: https://www.proofpoint.com/uk/threat-insight/post/august-in-december-new-information-stealer-hits-the-scene

## Content


































































August in November: New Information Stealer Hits the Scene | Proofpoint UK









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
Premium ServicesGet deeper insight with on-call, personalised assistance from our expert team.





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
Change User BehaviourHelp your employees identify, resist and report attacks before the damage is done.
Combat Data Loss and Insider RiskPrevent data loss via negligent, compromised and malicious insiders by correlating content, behaviour and threats.
Modernise Compliance and ArchivingManage risk and data retention needs with a modern compliance and archiving solution.


Protect Cloud AppsKeep your people and their cloud apps secure by eliminating threats, avoiding data loss and mitigating compliance risk.
Secure Microsoft 365Implement the very best security and compliance solution for your Microsoft 365 collaboration suite.
Defend Your Remote Workforce with Cloud EdgeSecure access to corporate resources and ensure business continuity for your remote workers.
Authenticate Your EmailProtect your email deliverability with DMARC.
Why ProofpointToday’s cyber attacks target people. Learn about our unique people-centric approach to protection.




Solutions by Industry

Financial Services
Counties and Local Government
Higher Education
Healthcare
Mobile for ISPs
Email for ISPs
Small and Medium Businesses






Partner Programs


Channel PartnersBecome a channel partner. Deliver Proofpoint solutions to your customers and grow your business.
Archive Extraction PartnersLearn about the benefits of becoming a Proofpoint Extraction Partner.


Technology and Alliance PartnersLearn about our relationships with industry-leading firms to help protect your people, data and brand.
Social Media Protection PartnersLearn about the technology and alliance partners in our Social Media Protection Partner program.




Partner Tools

Become a Channel Partner
Channel Partner Portal








Resource LibraryFind the information you're looking for in our library of videos, data sheets, white papers and more.
BlogKeep up with the latest news and happenings in the ever-evolving cybersecurity landscape.
PodcastsLearn about the human side of cybersecurity. Episodes feature insights from experts and executives.
New Perimeters MagazineGet the latest cybersecurity insights in your hands – featuring valuable knowledge from our own industry experts.


Threat GlossaryLearn about the latest security threats and how to protect your people, data, and brand.
EventsConnect with us at events to learn how to protect your people and data from ever-evolving threats.
Customer StoriesRead how Proofpoint customers around the globe solve their most pressing cybersecurity challenges.
WebinarsBrowse our webinar library to learn about the latest threats, trends and issues in cybersecurity.




Security Hubs

Get free research and resources to help you protect against threats, build a security culture, and stop ransomware in its tracks.

CISO Hub
Cybersecurity Awareness Hub
Ransomware Hub
Compliance Hub
Insider Threat Management Hub









About ProofpointProofpoint is a leading cybersecurity company that protects organizations' greatest assets and biggest risks: their people.
Why ProofpointToday’s cyber attacks target people. Learn about our unique people-centric approach to protection.
News CenterRead the latest press releases, news stories and media highlights about Proofpoint.


Privacy and TrustLearn about how we handle data and make commitments to privacy and other regulations.
Environmental, Social, and GovernanceLearn about our people-centric principles and how we implement them to positively impact our global community.




Support

Access the full range of Proofpoint support services.
Learn More











 




BlogThreat Insight
                                    August in November: New Information Stealer Hits the Scene
                              

 












August in November: New Information Stealer Hits the Scene





Share with your network!





 December 07, 2016


                Proofpoint Staff
  
        

 Overview
During the month of November, Proofpoint observed multiple campaigns from TA530 - an actor we have noted for their highly personalized campaigns [6] - targeting customer service and managerial staff at retailers. These campaigns utilized “fileless” loading of a relatively new malware called August through the use of Word macros and PowerShell. August contains stealing functionality targeting credentials and sensitive documents from the infected computer.
Delivery and Targeting
During our analysis we found that many of the lures and subject lines of the emails used references to issues with supposed purchases on the company’s website and were targeted at individuals who may be able to provide support for those issues. The lures also suggested that the attached document contained detailed information about the issue. However, the documents contained macros that could download and install August Stealer.
The subject lines were personalized with the recipient's domain. Examples included:
Erroneous charges from [recipient’s domain]
[recipient’s domain] - Help: Items vanish from the cart before checkout
[recipient’s domain] Support: Products disappear from the cart during checkout
Need help with order on [recipient’s domain]
Duplicate charges on [recipient’s domain]

Figure 1: Example email used to deliver the macro-laden document

Figure 2: Example email used to deliver the macro-laden document

Figure 3: Example macro-laden document attachment used to deliver August
The macro used is very similar to the one we discussed in our previous post detailing sandbox evasion techniques used to deliver the Ursnif banking Trojan [1]. It filters out security researchers and sandboxes using checks including Maxmind, task counts, task names, and recent file counts. Notably, the macro used in this campaign launches a Powershell command to “filelessly” load the payload from a byte array hosted on a remote site. This actor previously used this technique to load POS payloads [2][3][4].

Figure 4: Example PowerShell command used to download and execute the byte array

Figure 5: Snippet of the network traffic returning the byte array used to load August
The screenshot above shows the payload downloaded from the remote site as a PowerShell byte array. In addition to the byte array itself, there are few lines of code that deobfuscate the array through an XOR operation, and execute the “Main” function of the payload.
Analysis
August is written in .NET, with samples obfuscated with Confuser [5]. We determined from the source code of a particular sample that August can
Steal and upload files with specified extensions to a command and control (C&C) server
Steal .rdp files
Steal wallet.dat files
Steal crypto currency wallets including Electrum and Bither
Grab FTP credentials from applications including SmartFTP, FileZilla, TotalCommander, WinSCP, and CoreFTP
Grab messenger credentials for Pidgin, PSI, LiveMessenger, and others
Collect cookies and passwords from Firefox, Chrome, Thunderbird, and Outlook
Determine the presence of common security tools including Wireshark and Fiddler
Communicate the hardware ID, OS name, and victim's username to the C&C server
Use simple encryption of network data via base64 encoding, character replacement, adding a random key (passed to server encoded in the User-Agent field), and reversing the strings

Figure 6: The “Main” function executed from the PowerShell command

Figure 7: Determines the presence of security tools, and does not communicate with the C&C if they are found

Figure 8: Network data encryption

Figure 9: Example encrypted traffic generated by August

Figure 10: August configured to search and upload .txt and .doc files to the server

Figure 11: August control panel with stolen credentials for FTP, messenger, mail, RDP, and other programs
Conclusion
August is a new information stealer currently being distributed by threat actor TA530 through socially engineered emails with attached malicious documents. While this actor is largely targeting retailers and manufacturers with large B2C sales operations, August could be used to steal credentials and files in a wide range of scenarios. The malware itself is obfuscated while the macro used in these distribution campaigns employs a number of evasion techniques and a fileless approach to load the malware via PowerShell. All of these factors increase the difficulty of detection, both at the gateway and the endpoint. As email lures become increasingly sophisticated and personalized, organizations need to rely more heavily on email gateways capable of detecting macros with sandbox evasion built in as well as user education that addresses emails that do not initially look suspicious.
References
[1] https://www.proofpoint.com/uk/threat-insight/post/ursnif-banking-trojan-campaign-sandbox-evasion-techniques
[2] https://www.proofpoint.com/us/threat-insight/post/phish-scales-malicious-actor-target-execs
[3] http://researchcenter.paloaltonetworks.com/2016/03/powersniff-malware-used-in-macro-based-attacks/
[4] https://www.fireeye.com/blog/threat-research/2016/05/windows-zero-day-payment-cards.html
[5] https://confuser.codeplex.com/
[6] https://www.proofpoint.com/us/threat-insight/post/phish-scales-malicious-actor-target-execs
Indicators of Compromise (IOCs)

IOC


IOC Type


Description


c432cc99b390b5edbab400dcc322f7872d3176c08869c8e587918753c00e5d4e


SHA256


Example Document


hxxp://thedragon318[.]com/exchange/owalogon.asp
 


URL


Payload URL


hxxps://paste[.]ee/r/eY3Ui
 


URL


Payload URL


hxxp://muralegdanskzaspa[.]eu/network/outlook.asp
 


URL


Payload URL


hxxp://krusingtheworld[.]de/port/login.asp
 


URL


Payload URL


hxxp://pg4pszczyna[.]edu[.]pl/config/config.asp
 


URL


Payload URL


hxxp://www[.]overstockage[.]com/image/image.asp
 


URL


Payload URL


hxxp://thedragon318[.]com/exchange/port10/gate/
 


URL


August C2


hxxp://himalayard[.]de/exchange/port10/gate/
 


URL


August C2


hxxp://muralegdanskzaspa[.]eu/network/port10/gate/
 


URL


August C2


hxxp://krusingtheworld[.]de/port/jp/gate/
 


URL


August C2


hxxp://pg4pszczyna[.]edu[.]pl/config/install/gate/
 


URL


August C2


hxxp://www[.]overstockage[.]com/catalog/core/gate/
 


URL


August C2

ET and ETPRO Suricata/Snort Coverage
2823166          ETPRO TROJAN August Stealer CnC Checkin
2823171          ETPRO CURRENT_EVENTS MalDoc Payload Inbound Nov 08
Appendix A: Forum Advertisement
August Stealer - Passwords/Documents/Cookies/Wallets/Rdp/Ftp/IM Clients
Описание функционала:
- Стиллинг данных браузеров (сохранённые пароли/куки файлы) из:
Mozilla FireFox
Google Chrome
Yandex Browser
Opera Browser
Comodo IceDragon
Vivaldi Browser
Mail.Ru Browser
Amigo Browser
Bromium
Chromium
SRWare Iron
CoolNovo Browser
RockMelt Browser
Torch Browser
Dooble Browser
U Browser
Coowon
- Стиллинг данных учётных записей из некоторых фтп клиентов:
FileZilla
SmartFTP
- Стиллинг данных из мессенджеров:
Psi+
Psi
- Стиллинг файлов из указанных директорий по указанным маскам (возможность ограничивать вес входящих файлов)
- Стиллинг файлов wallet.dat (кошельки криптвалюты)
- Стиллинг файлов удалённого подключения (.rdp)
Описание билда:
- Зависимость от .NET Framework (2.0, возможность компиляции для более поздних версий по желанию)
- Самоудаление после работы
- Отправка данных на гейт (PHP 5.4+)
- Шифрование входящего/исходящего трафика
- Вес чистого, необфусцированного билда ~ 45кб
- Не таскает за собой нативные библиотеки
- Не требуются админ. права для выполнения поставленных задач
- Не использовались чужие исходники
Описание панели управления:
- Версия PHP 5.4+
- Не требуется MySQL
- Интуитивно-понятный интерфейс
- Опенсорс, нет обфускации, нет привязок
- Английский язык
Первым трем покупателям - скидка 30% за отзыв
Тем, кто приобретал у меня ранее продукт, предоставляется скидка 50%
Принимаю предложения по совершенстованию софта/пополнению функционала
Знатоки английского для исправления косяков в панели тоже бы пригодились
Софт в будущем будет обновляться и пополняться новыми фичами, не глобальные обновления для клиентов будут бесплатны
Цена: 100$
Ребилд: 10$
Метод оплаты: BTC
Appendix B: Forum Advertisement - English Translation
August Stealer - Passwords/Documents/Cookies/Wallets/Rdp/Ftp/IM Clients
Stealing data browser (saved passwords / cookie files) from:
Mozilla FireFox
Google Chrome
Yandex Browser
Opera Browser
Comodo IceDragon
Vivaldi Browser
Mail.Ru Browser
Amigo Browser
Bromium
Chromium
SRWare Iron
CoolNovo Browser
RockMelt Browser
Torch Browser
Dooble Browser
U Browser
Coowon
- Stealing data accounts of some FTP clients:
FileZilla
SmartFTP
- Stealing data from the messengers:
Psi +
Psi
- Stealing files from the specified directory on the specified masks (the ability to restrict the size of incoming files)
- Stealing wallet.dat files (cryptocurrency purses)
- Stealing file remote connection (.rdp)
Description of the build:
- Dependence on the .NET Framework (2.0, able to compile for later versions on request)
- Self-removal after execution
- Sending data to the gate (PHP 5.4+)
- Encryption of incoming / outgoing traffic\
- Size of clean build before obfuscation ~45KB
- Does not bring with it native libraries
- Do not require admin
- Do not borrow sources from other malware
Description of the control panel:
- Version PHP 5.4+
- You do not need MySQL
- Intuitive interface
- Open source, no obfuscation, no bindings
- English
The first three customers - 30% discount for a review
Those who acquired my earlier product, 50% discount
I accept suggestions for making the software better / additional functionality
Experts of the English language to correct the bugs in the panel are welcome
Software in the future will be updated with new features done, small updates will be free for customers
Price: $ 100
Rebild: $ 10
Payment method: BTC






Previous Blog Post


Next Blog Post


















About


Overview
Careers
Events
Leadership Team
News Center
Nexus Platform
Privacy and Trust




Threat Center


Human Factor Report
Threat Glossary
Threat Blog








Products


Email Protection
Advanced Threat Protection
Archive & Compliance
Information Protection




Resources


White Papers
Webinars
Data Sheets
Customer Stories
Blog
Free Trial








Connect


+44 (0)118 402 5900
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

 







 
















