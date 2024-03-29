# Reference for threat actor for "TA516"

**Title**: Threat Actors Using Legitimate PayPal Accounts To Distribute Chthonic Banking Trojan | Proofpoint US

**Source**: https://www.proofpoint.com/us/threat-insight/post/threat-actors-using-legitimate-paypal-accounts-to-distribute-chthonic-banking-trojan

## Content































































Threat Actors Using Legitimate PayPal Accounts To Distribute Chthonic Banking Trojan | Proofpoint US









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
                                    Threat Actors Using Legitimate PayPal Accounts To Distribute Chthonic Banking Trojan
                              

 












Threat Actors Using Legitimate PayPal Accounts To Distribute Chthonic Banking Trojan





Share with your network!








 July 26, 2016




 Updated August 2, 2016, to reflect new information a bout the malware referenced in this post; additional details added at the bottom.
While many email providers, clients, and anti-spam engines have become adept at detecting spam, malicious messages sent via high-profile, legitimate providers are much harder to catch. Threat actors continue to look for new ways to bypass these engines and, in the latest example of innovative approaches to malware distribution, have managed to co-opt PayPal services in a small campaign.
Proofpoint analysts recently noticed an interesting abuse of legitimate service in order to deliver malicious content. Specifically, we observed emails with the subject “You’ve got a money request” that came from PayPal. The sender does not appear to be faked: instead, the spam is generated by registering with PayPal (or using stolen accounts) and then using the portal to “request money.” We are not sure how much of this process was automated and how much manual, but the email volume was low. 
Figure 1: Email delivering malicious content
Although the actual email address is obscured in Figure 1, this message was sent to a Gmail inbox. Gmail failed to block the email since it appears legitimate. PayPal’s money request feature allows adding a note along with the request, where the attacker crafted a personalized message and included a malicious URL. In a double whammy, the recipient here can fall for the social engineering and lose $100, click on the link and be infected with malware, or both.
If the user does click on the Goo.gl link, they are redirected to katyaflash[.]com/pp.php, which downloads an obfuscated JavaScript file named paypalTransactionDetails.jpeg.js to the user’s system. If the user then opens the JavaScript file, it downloads an executable from wasingo[.]info/2/flash.exe. This executable is Chthonic, a variant of the Zeus banking Trojan. The command and control (C&C) for this instance is kingstonevikte[.]com. The following screenshot more clearly illustrates the sequence of events:
Figure 2: Network traffic generated starting with user clicking on the malicious URL and opening the downloaded JavaScript
It is also interesting that Chthonic downloads a second-stage payload, a previously undocumented malware “AZORult” which we are currently investigating:
Figure 3: Logo used internally by the AZORult module
Conclusion
Although the scale of this campaign appeared to be relatively small (this particular example was only detected through one of our spamtraps; as of the writing of this blog, the malicious link has only been clicked 27 times according to Google Analytics for the URL shortener), the technique is both interesting and troubling. For users without anti-malware services that can detect compromised links in emails and/or phone homes to a C&C, the potential impact is high. At the same time, the combined social engineering approach of requesting money via PayPal from what appears to be a legitimate source creates additional risk for untrained or inattentive recipients, even if they are not infected with the malicious payload.
PayPal has been notified of this particular abuse of service but this represents yet another technique threat actors can use to bypass traditional defenses, regardless of the specific provider.
Indicators of Compromise (IOC’s)

IOC


IOC Type


Description


[hxxp://goo[.]gl/G7z1aS?paypal-nonauthtransaction.jpg]


URL


URL in the email message


[hxxp://katyaflash[.]com/pp.php]


URL


URL after the goo.gl redirect (hosting the js)


865d2e9cbf5d88ae8b483f0f5e2397449298651381f66c55b7afd4b750eb4da4


SHA256


paypalTransactionDetails.jpeg.js


[hxxp://wasingo[.]info/2/flash.exe]


URL


JavaScript payload


0d2def167ecf39a69a7e949c88bb2096cfd76f7d4bf72f1b0fe27a9da686c141


SHA256


flash.exe


kingstonevikte[.]com


Domain


Chthonic C&C


[hxxp://www.viscot[.]com/system/helper/bzr.exe]


URL


Chthonic 2nd Stage hosting


10d159b0ddb92e9f4b395e90f9cfaa554622c4e77f66f7da176783777db5526a


SHA256


Chthonic 2nd Stage (AZORult)


[91.215.154[.]202/AZORult/gate.php]


URL


AZORult C&C

Select ET Signatures that would fire on such traffic:
2810099 || ETPRO TROJAN Chthonic CnC Beacon
2811901 || ETPRO TROJAN Chthonic CnC Beacon 
2821358 || ETPRO TROJAN Win32/Zbot Variant Checkin
 
The information below was added based on additional background research conducted by Proofpoint analysts.
On July 31, Proofpoint researchers discovered an advertisement in an underground forum for the AZORult information stealer. This was the second-stage payload that Chthonic delivered to infected machines. The original ad in mixed Russian and English appears on top with our translation below:
Original Ad
[AZORult - Passwords, cookies, bitcoin, desktop files, etc stealer]
Многофункциональный стиллер.
Функционал:
• Stealer сохраненных паролей из следующих программ(browsers, email, ftp, im):
Спойлер
Google Chrome
Google Chrome x64
YandexBrowser
Opera
Mozilla Firefox
InternetMailRu
ComodoDragon
Amigo
Bromium
Chromium
Outlook
Thunderbird
Filezilla
Pidgin
PSI
PSI Plus
• Stealer cookies(Стиллер куков) из браузеров + данные автозаполнения форм(formhistory, autofill)
Поддерживаемые браузеры:
Спойлер
Google Chrome
Google Chrome x64
YandexBrowser
Opera
Mozilla Firefox
InternetMailRu
ComodoDragon
Amigo
Bromium
Chromium
Куки в следующем формате, для удобного экспорта(Netscape cookie file format):
Спойлер
Instagram[.]com    FALSE     /    FALSE     11129062731157896     csrftoken ebc08a134952abc6a5c36fb54c1aaaa
.microsoft[.]com   TRUE /    FALSE     13140111158000000  TocPosition     1
www.searchengines[.]ru  FALSE     /    FALSE     11138811175911879     OAИCAP    640.1
vsokovikov.narod[.]ru   FALSE     /    FALSE     11168272384aaa000     __utma    1.211136481.14511109932.14658111726.1496725111.1
vsokovikov.narod[.]ru   FALSE     /    FALSE     13111168384000111     __utmz     1.1250111526.1.1.utmcsr=(direct)|utmccn=(direct)|utmcmd=(none)
• Bitcoin clients files
Собирает файлы wallet.dat популярных биткоин клиентов (bitcoin, litecoin, etc)
• Skype message history.
Грабит файл с базой данных переписки. Файл читается специальными утилитами.
• Desktop files grabber.
Собирает файлы указанных расширений с рабочего стола. Фильтр по размеру файла. Также рекурсивно ищет файлы во вложенных папках.
• Список установленных программ.
• Список запущенных процессов.
• Username, compname, OS, RAM
Необходимый функционал можно включать/выключать в админке.
В админке просматривается список поступивших отчетов, список сохраненных паролей из этих отчетов. Фильтры по дате, по типу паролей, поиск по базе.
Остальные данные сохраняются в zip архив(отдельный для каждого отчета). Данные в архиве разложны по папкам. В архиве хранятся все данные, в админке только список отчетов и пароли.
Спойлер
[]Browsers
-[]Autocomplete
--Google_Chrome_Default.txt
-[]Cookies
--Google_Chrome_Default.txt
--MozillaFirefox_tpsasn.default-111340945411.txt
[]Coins
-[]Bitcoin
--wallet.dat
-[]Litecoin
--wallet.dat
...
Info.txt
Passwords.txt
Process.txt
Programms.txt
Софт поставляется в виде:
.EXE - при запуске собирается необходимая инфа и отправляется на сервер
.DLL - при подгрузке dll (DLL_PROCESS_ATTACH) собирается необходимая инфа и отправляется на сервер
.DLL(thread) - при подгрузке dll (DLL_PROCESS_ATTACH) создается отдельный поток, в котором производится необходимая работа(собирается необходимая инфа и отправляется на сервер). Например для использования как плагина для популярных лоадеров.
Скриншоты:
Спойлер
[Screenshots linked in the original ad – displayed here]




Цена: $100
Ребилд: $30
Связь(jabber): [Redacted]@exploit[.]im
**************************************
Translation:
[AZORult - Passwords, cookies, bitcoin, desktop files, etc stealer]
Multifunctional Stealer.
Functions:
• Stealer of saved passwords from following programs (browsers, email, ftp, im):
Google Chrome
Google Chrome x64
YandexBrowser
Opera
Mozilla Firefox
InternetMailRu
ComodoDragon
Amigo
Bromium
Chromium
Outlook
Thunderbird
Filezilla
Pidgin
PSI
PSI Plus
• Stealer of cookies from browsers and forms (form history, autofill)
Supported Browsers:
Google Chrome
Google Chrome x64
YandexBrowser
Opera
Mozilla Firefox
InternetMailRu
ComodoDragon
Amigo
Bromium
Chromium
Cookies are in following format, for easy export (Netscape cookie file format):
instagram[.]com  FALSE /
FALSE 11129062731157111
csrftoken yyyc08a1349526c46a5c36fb54c1ayyy
.microsoft[.]com  TRUE /
FALSE 11140260158000111
TocPosition 1
www.searchengines[.]ru  FALSE /
FALSE 11138826175965111
OAИCAP 111.1
vsokovikov.narod[.]ru  FALSE /
FALSE 11168272384000111
__utma 1.111136481.1458509111.1465826111.1496725111.1
vsokovikov.narod[.]ru  FALSE /
FALSE 13120968384000111
__utmz 1.1110722526.1.1.utmcsr=(direct)|utmccn=(direct)|utmcmd=(none)
• Bitcoin clients files
Collects wallet.dat files from popular bitcoin clients (bitcoin, litecoin, etc)
• Skype message history.
Grabs files from chat history. Files are read with special utilities.
• Desktop files grabber.
Collects files with specified extensions from Desktop. Filter by file size. Recursively searches files in folders.
• List of installed programs
• List of running processes
• Username, compname, OS, RAM
Necessary functions that can be turned on and of in admin panel
The admin panel has a list of received reports, list of saved passwords from those reports. Has filters by date, type of password, search in the base.
The rest of data from reports is save as a zip aarchive, different one for each report. The data is sorted into folders. The archive contains all data, while the admin panel only list of reports and passwords.
[]Browsers
-[]Autocomplete
--Google_Chrome_Default.txt
-[]Cookies
--Google_Chrome_Default.txt
--MozillaFirefox_tpasdn.default-111140945111.txt
[]Coins
-[]Bitcoin
--wallet.dat
-[]Litecoin
--wallet.dat
...
Info.txt
Passwords.txt
Process.txt
Programms.txt
Software is delivered as:
.EXE - when started, collects necessary info and sends to server
.DLL - when started the dll (DLL_PROCESS_ATTACH) collects necessary info and sends to server
.DLL(thread) - when started dll (DLL_PROCESS_ATTACH) creates a new thread which does the work (collects necessary info and sends to server)
Price: $100
Rebuild: $30
Contact(jabber): [Redacted]@exploit[.]im






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

 







 

















