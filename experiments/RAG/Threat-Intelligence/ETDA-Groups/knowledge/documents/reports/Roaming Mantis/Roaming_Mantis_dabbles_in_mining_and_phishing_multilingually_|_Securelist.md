# Reference for threat actor for "Roaming Mantis"

**Title**: Roaming Mantis dabbles in mining and phishing multilingually | Securelist

**Source**: https://securelist.com/roaming-mantis-dabbles-in-mining-and-phishing-multilingually/85607/

## Content















Roaming Mantis dabbles in mining and phishing multilingually | Securelist


































































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


 











 

Incidents

Roaming Mantis dabbles in mining and phishing multilingually 

Incidents

18 May 2018

  minute read								
















Table of Contents





27 languages: targeting the worldApple phishing site for iOS deviceWeb crypto mining for PCReal C2 destination is hidden in email subjectBackdoor command “ping”Auto-generating apk file and filenameRapidly improving malicious apk and landing pagesGeographical expansionConclusionsIoCs 






 

Authors



 Suguru Ishimaru





In April 2018, Kaspersky Lab published a blogpost titled ‘Roaming Mantis uses DNS hijacking to infect Android smartphones’. Roaming Mantis uses Android malware which is designed to spread via DNS hijacking and targets Android devices. This activity is located mostly in Asia (South Korea, Bangladesh and Japan) based on our telemetry data. Potential victims were redirected by DNS hijacking to a malicious web page that distributed a Trojanized application spoofed Facebook or Chrome that is then installed manually by users. The application actually contained an Android Trojan-Banker. 
Soon after our publication it was brought to our attention that other researchers were also focused on this malware family. There was also another publication after we released our own blog. We’d like to acknowledge the good work of our colleagues from other security companies McAfee and TrendMicro covering this threat independently. If you are interested in this topic, you may find the following articles useful:

Android Banking Trojan MoqHao Spreading via SMS Phishing in South Korea
XLoader Android Spyware and Banking Trojan Distributed via DNS Spoofing

In May, while monitoring Roaming Mantis, aka MoqHao and XLoader, we observed significant changes in their M.O.  The group’s activity expanded geographically and they broadened their attack/evasion methods. Their landing pages and malicious apk files now support 27 languages covering Europe and the Middle East. In addition, the criminals added a phishing option for iOS devices, and crypto-mining capabilities for the PC.
27 languages: targeting the world
In our previous blogpost we mentioned that a user attempting to connect to any websites while using a hijacked DNS, will be redirected to malicious landing pages on the rogue server. The landing page displays a popup message that corresponds to the language settings of the device and which urges the user to download a malicious apk file named ‘facebook.apk’ or ‘chrome.apk’.
Kaspersky Lab confirmed several languages hardcoded in the HTML source of the landing page to display the popup message.

The attackers  substantially extended their target languages from four to 27, including European and Middle Eastern languages. And yet, they keep adding comments in Simplified Chinese.
But, of course, this multilingualism is not limited to the landing page. The most recent malicious apk (MD5:”fbe10ce5631305ca8bf8cd17ba1a0a35″) also was expanded to supports 27 languages.

The landing page and malicious apk now support the following languages:

Arabic
Bulgarian
Bengali
Czech
German
English
Spanish
Hebrew
Hindi
Armenian
Indonesian
Italian
Japanese
Georgian
Korean
Malay
Polish
Portuguese
Russian
Serbo-Croatian
Thai
Tagalog
Turkish
Ukrainian
Vietnamese
Traditional Chinese
Simplified Chinese

We believe the attacker made use of an easy method to potentially infect more users, by translating their initial set of languages with an automatic translator.
Apple phishing site for iOS device
Previously, this criminal group focused on Android devices only. They have apparently changed their monetizing strategy since then. The attackers now target iOS devices as well, using a phishing site to steal user credentials. When a user connects to the landing page via iOS devices, the user is redirected to ‘http://security.apple.com/’:

A legitimate DNS server wouldn’t be able to resolve a domain name like that, because it simply doesn’t exist. However, a user connecting via a compromised router can access the landing page because the rogue DNS service resolves this domain to the IP address 172.247.116[.]155. The final page is a phishing page mimicking the Apple website with the very reassuring domain name ‘security.apple.com’ in the address bar of the browser. 

The phishing site steals user ID, password, card number, card expiration date and CVV. The HTML source of the phishing site also supports 25 languages.

The supported languages are almost the same as on the landing pages and malicious apk files – only Bengali and Georgian are missing from the phishing site.
Web crypto mining for PC
Looking at the HTML source code of the landing page, we also discovered a new feature: web mining via a special script executed in the browser. More details about web miners can be found in our blogpost ‘Mining is the new black‘.

Coinhive is the most popular web miner used by cybercriminals around the world. When a user connects to the landing page from a PC, the CPU usage will drastically increase because of the crypto mining activity in the browser. 

Real C2 destination is hidden in email subject
Older malicious apk samples include a legitimate website, accounts and a regular expression for retrieving the real C2 address, which the malware connects to by using a web socket. This process for obtaining its C2 changes in more recent samples, further described below:



MD5
f3ca571b2d1f0ecff371fb82119d1afe
4d9a7e425f8c8b02d598ef0a0a776a58
fbe10ce5631305ca8bf8cd17ba1a0a35


Date
March 29 2018
April 7 2018
May 14 2018


File name
chrome.apk
facebook.apk
$random_num{8}.apk


Legitimate web
http://my.tv.sohu[.]com/user/%s
https://www.baidu[.]com/p/%s/detail
n/a


Email
n/a
n/a
@outlook.com


Accounts
329505231329505325329505338
haoxingfu88haoxingfu12389wokaixin158998
haoxingfu11haoxingfu22haoxingfu33


RegExp

"<p>([\u4e00-\u9fa5]+?)</p>\s+</div>" 

"公司</span>([\\u4e00-\\u9fa5]+?)<" 
“abcd”


Encrypted dex
\assets\db
\assets\data.sql
\assets\data.sql


Encoding
Base64
Base64 + zlib compression
Base64 + zlib compression



Older samples retrieved the next C2 by accessing the legitimate website, extracting a Chinese string from a specific part of the HTML code, and decoding it. This scheme has been changed in the recent sample. Instead of using HTML protocol, it now uses email protocol to retrieve the C2.

The malware connects to an email inbox using hardcoded outlook.com credentials via POP3. It then obtains the email subject (in Chinese) and extracts the real C2 address using the string “abcd” as an anchor.
The old and new decoding functions are exactly the same.

We decoded the following next stage C2 servers:

220.136.78[.]40
220.136.73[.]107

Backdoor command “ping”
Kaspersky Lab observed that the previous malicious apk (MD5:f3ca571b2d1f0ecff371fb82119d1afe) had 18 backdoor commands to confirm victims’ environments and to control devices.
According to our analysis, the recent malicious apk (MD5:fbe10ce5631305ca8bf8cd17ba1a0a35) now implements 19 backdoor commands: “ping” was added.  

The backdoor commands in the recent sample are as follows:

sendSms
setWifi
gcont
lock
bc
setForward
getForward
hasPkg
setRingerMode
setRecEnable
reqState
showHome
getnpki
http
onRecordAction
call
get_apps
show_fs_float_window
ping   NEW

This additional command calls the OS ping command with the IP address of the C2 server. By running this, the attackers validate the availability of the server, packet travel time or detect network filtering in the target network. This feature can also be used to detect semi-isolated research environments.
Auto-generating apk file and filename
Roaming Mantis uses a very simple detection evasion trick on the malicious server. It entails the landing page generating a filename for the malicious apk file using eight random numbers. 

Aside from the filename, we also observed that all the downloaded malicious apk files are unique due to package generation in real time as of May 16, 2018. It seems the actor added automatic generation of apk per download to avoid denylisting by file hashes. This is a new feature. According to our monitoring, the apk samples downloaded on May 8, 2018 were all the same.
However, the malicious apk still contains a loader inside ‘classes.dex’ and an encrypted payload inside ‘\assets\data.sql’ that are identical to those in the previous variants. For security researchers, we have added MD5 hashes of the decrypted payloads without hashes of the whole apk files in the IoC of this report, as well as a few full apk hashes that were uploaded to VirusTotal.
Rapidly improving malicious apk and landing pages
Since our first report, Roaming Mantis has evolved quickly. The update history shows how rapidly the threat has been growing: 

The actors behind it have been quite active in improving their tools. As seen in the graph below, which shows the unique detected user counts per day according to KSN data, the count increased on May 5. That date is very close to the update date of the new features on the landing pages. 

Geographical expansion
Kaspersky Lab products detect Roaming Mantis’s malicious apk files as ‘Trojan-Banker.AndroidOS.Wroba’. Below is the data from Kaspersky Security Network (KSN) based on the verdict ‘Trojan-Banker.AndroidOS.Wroba.al’ from May 1 to May 10, 2018. 

It’s clear from this that South Korea, Bangladesh and Japan are no longer the worst affected countries; instead, Russia, Ukraine and India bore the brunt. According to data gathered between February 9 and April 9, the unique user count was 150. It’s worth mentioning that the most recent data shows more than 120 users of Kaspersky Lab products were affected in just 10 days.
Also, it’s important to note that what we see in the KSN data is probably a tiny fraction of the overall picture. There are two reasons for that:

Some users may be using other AV products or no products at all.
Roaming Mantis, after all, uses DNS hijacking, which prevents even our customers from reporting a detection. However, some devices made it through – probably due to switching to cellular data or connecting to another Wi-Fi network.

Conclusions
The Roaming Mantis campaign evolved significantly in a short period of time. The earliest report of this attack was made public by researchers from McAfee in August 2017. At that time, the Roaming Mantis distribution method was SMS and there was one target: South Korea. When we first reported this attack in April 2018, it had already implemented DNS hijacking and expanded its targets to the wider Asian region.
In our report of April this year, we called it an active and rapidly changing threat. New evidence shows a dramatic expansion in the target geography to include countries from Europe, the Middle East and beyond by supporting 27 languages in total. The attackers have also gone beyond Android devices by adding iOS as a new target, and recently started targeting PC platforms – the landing page PC users are redirected to is now equipped with the Coinhive web miner.
The evasion techniques used by Roaming Mantis have also become more sophisticated. Several examples of recent additions described in this post include a new method of retrieving the C2 by using the email POP protocol, server side dynamic auto-generation of changing apk file/filenames, and the inclusion of an additional command to potentially assist in identifying research environments, have all been added.
The rapid growth of the campaign implies that those behind it have a strong financial motivation and are probably well-funded. 
For our previous findings, please refer to the Securelist post Roaming Mantis uses DNS hijacking to infect Android smartphones.
Kaspersky products detect this malware as:

HEUR:Trojan-Banker.AndroidOS.Wroba

Kaspersky Lab products block the Coinhive web miner for PC.
IoCs
Malicious hosts:

43.240.14[.]44
118.168.201[.]70 	NEW
118.168.202[.]125 	NEW
128.14.50[.]147
172.247.116[.]155 	NEW
220.136.73[.]107 	NEW
220.136.76[.]200
220.136.78[.]40 	NEW
220.136.111[.]66
220.136.179[.]5
220.136.182[.]72 	NEW
shaoye11.hopto[.]org
haoxingfu01.ddns[.]net

Malicious apks:

03108e7f426416b0eaca9132f082d568
07eab01094567c6d62a73f7098634eb8	NEW
1cc88a79424091121a83d58b6886ea7a
2a1da7e17edaefc0468dbf25a0f60390
31e61e52d38f19cf3958df2239fba1a7
34efc3ebf51a6511c0d12cce7592db73
4d9a7e425f8c8b02d598ef0a0a776a58
531714703557a58584a102ecc34162ff	NEW
904b4d615c05952bcf58f35acadee5c1
9f94c34aae5c7d50bc0997d043df032b	NEW
a21322b2416fce17a1877542d16929d5
b84b0d5f128a8e0621733a6f3b412e19
bd90279ad5c5a813bc34c06093665e55
cc1e4d3af5698feb36878df0233ab14a	NEW
ff163a92f2622f2b8330a5730d3d636c
808b186ddfa5e62ee882d5bdb94cc6e2
ee0718c18b2e9f941b5d0327a27fbda1 	NEW

classes.dex:

13c8dda30b866e84163f82b95008790a 	NEW
19e3daf40460aea22962d98de4bc32d2
1b984d8cb76297efa911a3c49805432e 	NEW
36b2609a98aa39c730c2f5b49097d0ad
3ba4882dbf2dd6bd4fc0f54ec1373f4c
46c34be9b3ff01e73153937ef35b0766 	NEW
5145c98d809bc014c3af39415be8c9ac 	NEW
6116dc0a59e4859a32caddaefda4dbf4 	NEW
8a4ed9c4a66d7ccb3d155f85383ea3b3
a5d2403b98cddcd80b79a4658df4d147 	NEW
b43335b043212355619fd827b01be9a0
b4152bee9eca9eb247353e0ecab37aa5	NEW
b7afa4b2dafb57886fc47a1355824199
bf5538df0688961ef6fccb5854883a20 	NEW
f89214bfa4b4ac9000087e4253e7f754
6cac4c9eda750a69e435c801a7ca7b8d
e56cccd689a9e354cb539bb069733a43 	NEW
fe0198f4b3d9dc501c2b7db2750a228b 	NEW

Decrypted payload (dex file) from \assets\data.sql:

1bd7815bece1b54b7728b8dd16f1d3a9
28ef823d10a3b78f8840310484e3cc69 	NEW
307d2780185ba2b8c5ad4c9256407504
3e01b64fb9fe9605fee7c07e42907a3b 	NEW
3e4bff0e8ed962f3c420692a35d2e503
3ed3b8ecce178c2e977a269524f43576 	NEW
57abbe642b85fa00b1f76f62acad4d3b
6e1926d548ffac0f6cedfb4a4f49196e
6d5f6065ec4112f1581732206539e72e 	NEW
7714321baf6a54b09baa6a777b9742ef
7aa46b4d67c3ab07caa53e8d8df3005c
a0f88c77b183da227b9902968862c2b9
b964645e76689d7e0d09234fb7854ede







Botnets
Google Android
Malware Descriptions
Miner
Mobile Malware
Phishing



Authors



 Suguru Ishimaru





Roaming Mantis dabbles in mining and phishing multilingually 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





27 languages: targeting the worldApple phishing site for iOS deviceWeb crypto mining for PCReal C2 destination is hidden in email subjectBackdoor command “ping”Auto-generating apk file and filenameRapidly improving malicious apk and landing pagesGeographical expansionConclusionsIoCs 





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




 


APT10: Tracking down LODEINFO 2022, part II 






 


APT10: Tracking down LODEINFO 2022, part I 






 


Roaming Mantis reaches Europe 






 


Roaming Mantis, part V 






 


Roaming Mantis uses DNS hijacking to infect Android smartphones 









Subscribe to our weekly e-mails
The hottest research right in your inbox




Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ








In the same category




 


A hack in hand is worth two in the bush 






 


QBot banker delivered through business correspondence 






 


Not just an infostealer: Gopuram backdoor deployed through 3CX supply chain attack 






 


CVE-2022-41040 and CVE-2022-41082 – zero-days in MS Exchange 






 


Ongoing exploitation of CVE-2022-41352 (Zimbra 0-day) 






 















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



























