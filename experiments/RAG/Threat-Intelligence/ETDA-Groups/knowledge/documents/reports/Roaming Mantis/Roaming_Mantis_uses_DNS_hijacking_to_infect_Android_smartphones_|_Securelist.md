# Reference for threat actor for "Roaming Mantis"

**Title**: Roaming Mantis uses DNS hijacking to infect Android smartphones | Securelist

**Source**: https://securelist.com/roaming-mantis-uses-dns-hijacking-to-infect-android-smartphones/85178/

## Content















Roaming Mantis uses DNS hijacking to infect Android smartphones | Securelist


































































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


 











 

Research

Roaming Mantis uses DNS hijacking to infect Android smartphones 

Research

16 Apr 2018

  minute read								








 

Authors



 Suguru Ishimaru





In March 2018, Japanese media reported the hijacking of DNS settings on routers located in Japan, redirecting users to malicious IP addresses. The redirection led to the installation of Trojanized applications named facebook.apk and chrome.apk that contained Android Trojan-Banker. According to our telemetry data, this malware was detected more than 6,000 times, though the reports came from just 150 unique users (from February 9 to April 9, 2018). Of course, this is down to the nature of the malware distribution, but it also suggests a very painful experience for some users, who saw the same malware appear again and again in their network. More than half of the detections were observed targeting the Asian region.
During our research we received some invaluable information about the true scale of this attack. There were thousands of daily connections to the command and control (C2) infrastructure, with the device locale for the majority of victims set to Korean. Since we didn’t find a pre-existing name for this malware operation, we decided to assign a new one for future reference. Based on its propagation via smartphones roaming between Wi-Fi networks, potentially carrying and spreading the infection, we decided to call it ‘Roaming Mantis’.
Distribution
Roaming Mantis malware is designed for distribution through a simple, but very efficient trick based on a technique known as DNS hijacking. When a user attempts to access any website via a compromised router, they will be redirected to a malicious website. For example, if a user were to navigate to securelist.com using a web browser, the browser would be redirected to a rogue server which has nothing to do with the security research blog. As long as the browser displays the original URL, users are likely to believe the website is genuine. The web page from the rogue server displays the popup message (screenshot below): “To better experience the browsing, update to the latest chrome version.”

Looking at the HTML source of the malicious webpage, it seems to support five locales: Korean, Traditional Chinese, Simplified Chinese, Japanese and English.

However, after carefully studying the HTML source, we found that the actual number of target locales is only four: Korean, Simplified Chinese, Japanese and English, based on Android devices. As shown in the image above, the HTML code contains an identical message in Traditional Chinese and Simplified Chinese. Also, the HTML source contains several short code comments in Simplified Chinese.
Analyzing chrome.apk
One of the applications pushed to users impersonated a Chrome browser for Android. Kaspersky Lab got a copy of chrome.apk (md5:f3ca571b2d1f0ecff371fb82119d1afe) in April 2018. The Android application package structure is as follows:

The package contains classes.dex, which is a Dalvik VM executable file. Its main purpose is to read the file named /assets/db. It decodes the data inside with a Base64 decoder and produces another Dalvik VM executable named test.dex:

The extracted test.dex contains the main malicious payload, which is described in more detail below. The Base64 encoding technique is probably used to bypass trivial signature-based detection.
AndroidManifest.xml contains one of the key components of the package – the permissions requested by the application from the device owner during installation.

From the xml above, it seems that Roaming Mantis requests permission to be notified when the device is booted, using the internet, collecting account information, managing SMS/MMS and making calls, recording audio, controlling external storage, checking packages, working with file systems, drawing overlay windows and so on. All these requests are of course backed up by malicious functionality implemented in test.dex.
For instance, after installation, the malware overlays all other windows with one carrying a message in broken English: “Account No.exists risks, use after certification”. After that, the malware starts its own webserver on the device, and renders a page spoofing Google’s authentication on 127.0.0.1.

The page uses a Google account name obtained from the infected device and asks the owner to complete two input boxes with ‘Name:’ and ‘Date of birth:’, which would facilitate access to the user account. After the user enters their name and date of birth, the browser is redirected to a blank page at http://127.0.0.1:${random_port}/submit.
While analyzing the extracted test.dex, we found an interesting piece of code.

Just like the distribution page, the malware supports four locales: Korean, Traditional Chinese, Japanese and English. The code above was taken from an original Google authentication page intended for an English environment, though we aren’t sure why the three Korean strings appear here. The English translations are as follows:

I have an anomaly on my Google account. For voice verification, enter your verification number to verify your Google account. //구글 계정이 이상이 있습니다.음성검증을 들어 인증번호를 입력하여 구글 계정을 검증하도록합니다.
Verification Number. //인증번호
Please enter your verification number. //인증번호를 입력하세요

Judging by these strings, it’s clear that the criminals behind the malware are trying to get a verification code for two-factor authentication. There may be a bug or design fault that causes Korean strings to be displayed not just for Korean users but also for those using Japanese and English. Traditional Chinese users will see strings in Traditional Chinese. The authors could have overlooked this in the rush to launch the campaign, but it reveals a certain bias by the authors towards Korean and Traditional Chinese.
Permission to receive/read/write/send SMS/MMS and record audio could also allow the malware operators to steal a verification code for the two-factor authentication function.
Secondly, this malware contains references to Android application IDs popular in South Korea and mostly linked to mobile banking and games.

The following hardcoded strings were extracted from the malware:

wooribank.pib.smart
kbstar.kbbank
ibk.neobanking
sc.danb.scbankapp
shinhan.sbanking
hanabank.ebk.channel.android.hananbank
smart
epost.psf.sdsi
kftc.kjbsmb
smg.spbs
webzen.muorigin.google
ncsoft.lineagem19
ncsoft.lineagem
co.neople.neopleotp
co.happymoney.android.happymoney
nexon.axe
nexon.nxplay
atsolution.android.uotp2

Another piece of code verifies the presence of the su binary in /system/bin/, /system/xbin/, /system/sbin/, sbin/ or /vendor/bin/ on a device.

Regular Android devices do not have the su binary. Its presence means the device is probably rooted. For attackers this may indicate that a device is owned by an advanced Android user (a signal to stop messing with the device) or, alternatively, a chance to leverage root access to gain access to the whole system.
C2 communication
Kaspersky Lab discovered a hardcoded URL template (http://my.tv.sohu.com/user/%s) in the malicious application used for malware control. The site my.tv.sohu.com is legitimate; however, some content on the user profile pages is controlled by the owners of the profiles.

A list of account IDs separated by the “|” character were included in the malware: “329505231|329505325|329505338”.

After getting the content from the sohu.com webpage, the malware extracts a Chinese string from a specific part of the HTML code.
For example, the malicious application receives the page at http://my.tv.sohu.com/user/329505338.

After that, it uses the hardcoded regular expression “<p>([\u4e00-\u9fa5]+?)</p>\s+</div>” to extract a Chinese string located in a very distinct place on the web page. Next, each character is decoded by subtracting 0x4E00, doing a right bitwise shift operation for 3 bits and xoring using the word “beg” as the key.

The result is the real C2 address, which the malware connects to by using a web socket. We traced this activity in the debug log of an infected device.

In another recent sample (MD5:4d9a7e425f8c8b02d598ef0a0a776a58), the connection protocol, including a hardcoded legitimate website, accounts and the regular expression for retrieving next level C2, had been changed:



MD5
f3ca571b2d1f0ecff371fb82119d1afe
4d9a7e425f8c8b02d598ef0a0a776a58


Date
March 29 2018
April 7 2018


Legitimate web
http://my.tv.sohu[.]com/user/%s
https://www.baidu[.]com/p/%s/detail


account_IDs
● 329505231
● 329505325
● 329505338
● haoxingfu88
● haoxingfu12389
● wokaixin158998


pattern
“<p>([\u4e00-\u9fa5]+?)</p>\s+</div>”
“公司</span>([\\u4e00-\\u9fa5]+?)<“


Encrypted dex
\assets\db
\assets\data.sql


Encoding
Base64
Base64 + zlib compression



In addition, the \assets\db file name was changed to \assets\data.sql and it’s encoding algorithm have also been changed from Base64 to Base64+zlib. The malware author seems to be updating the code quite regularly.
Researchers wishing to track Roaming Mantis campaign can use the following simplified python script to decode the real C2 server.


#!/usr/bin/env python
# -*- coding: utf-8 -*-
import sys
import re
page = open(sys.argv[1],"rb").read()
#pattern = u'&lt;p&gt;([\u4e00-\u9fa5]+?)&lt;/p&gt;\s+&lt;/div&gt;' # my.tv.sohu.com
pattern = u'公司&lt;/span&gt;([\u4e00-\u9fa5]+?)&lt;' # baidu.com
match = re.search(pattern, page.decode("utf-8"))
ext = match.group(1)
dec = ''
j = 0
for i in range(len(ext)):
dec = dec + chr((ord(ext[i]) - 0x4e00) &gt;&gt; 3 ^ ord('beg'[j]))
j = (j+1) %3
print(dec)




123456789101112131415

#!/usr/bin/env python# -*- coding: utf-8 -*-import sysimport repage = open(sys.argv[1],"rb").read()#pattern = u'&lt;p&gt;([\u4e00-\u9fa5]+?)&lt;/p&gt;\s+&lt;/div&gt;' # my.tv.sohu.compattern = u'公司&lt;/span&gt;([\u4e00-\u9fa5]+?)&lt;' # baidu.commatch = re.search(pattern, page.decode("utf-8"))ext = match.group(1)dec = ''j = 0for i in range(len(ext)):dec = dec + chr((ord(ext[i]) - 0x4e00) &gt;&gt; 3 ^ ord('beg'[j]))j = (j+1) %3print(dec)




An example of script input and output:


$ python dec_facebook_apk.py my.tv.sohu.com_329505338.html
220.136.76[.]200:8844
$ python dec_facebook_apk.py www.baidu.com_p_wokaixin158998_detail.html
220.136.179[.]5:28833




1234

$ python dec_facebook_apk.py my.tv.sohu.com_329505338.html220.136.76[.]200:8844$ python dec_facebook_apk.py www.baidu.com_p_wokaixin158998_detail.html220.136.179[.]5:28833




Most interestingly, the malware is embedded with a new feature that communicates with the C2 via email protocols. The data sent contains language, phone number, access information, and the result of a PING test to the C2.
Malware detection statistics
Kaspersky Lab products detect Roaming Mantis’s malicious apk file as Trojan-Banker.AndroidOS.Wroba. Based on the verdict, we checked the statistics from Kaspersky Security Network (KSN) for the two months from February 9 to April 9, 2018.

There were more than 6,000 detections coming from just over 150 unique users. The most affected countries were South Korea, Bangladesh and Japan. Based on the design of the malware and our detection statistics, this malware was designed to be spread mainly in Asian countries. While Kaspersky Lab products may only see a limited number of infections, based on further analysis of the C2 infrastructure we saw roughly 3,000 connections to C2 infrastructure per day, which suggests a much larger scale for this Android malware campaign. Upon every connection the malware sends information about compromised devices to the C2, including system locale, which indicates the possible origins of the victims. 98% of affected devices appear to have the Korean locale set.
We have done some calculations and built the following chart based on observed locales:

The breakdown of the remaining 2% reveals a few more system locales: en_GB, en_US, zh_CN, ja_JP and others.
As usual in such cases, Kaspersky Lab has got in touch with local CERTs (South Korea being the first) to provide information about the victims to help unsuspecting users remove the malware and prevent further reinfections.
Conclusions
Kaspersky Lab observed Roaming Mantis’ Android application being distributed via a DNS hijacking technique with the help of compromised routers. The malware aims to steal user information, including credentials for two-factor authentication, and give the attackers full control over compromised Android devices.
At the moment, clues appear to suggest a financial motive and low OPSEC for this attack, which is why we think it is likely to be the work of cybercriminal hackers.
Our research revealed that the malware contains Android application IDs for popular mobile banking and game applications in South Korea. The malware is most prevalent in South Korea, and Korean is the first language targeted in HTML and test.dex. Based on our findings, it appears the malicious app was originally distributed to South Korean targets. Support was then added for Traditional Chinese, English and Japanese, broadening its target base in the Asian region.
However, it’s still unclear how the attackers hijacked the router DNS settings. If you have any concerns about the DNS settings on your router, please check the user manual and verify that your DNS settings haven’t been tampered with, or contact your ISP for support. Kaspersky Lab also strongly recommends changing the default login and password for the admin web interface of their router, never install firmware from third-party sources and regularly update router firmware to prevent similar attacks in the future.
Based on our investigation, the Roaming Mantis attackers left some additional clues. For example, some comments in the HTML source, malware strings and a hardcoded legitimate website point to Simplified Chinese. Therefore, we believe the cybercriminals are familiar with both Simplified Chinese and Korean.
The malicious threat actor behind this campaign remains very active and the malware is updated every day. We will keep tracking this campaign to protect our customers and update our readers with new information.
Kaspersky Lab products detect this malware with the following verdict(s):
HEUR:Trojan-Banker.AndroidOS.Wroba
IOC
Malicious hosts:
114.44.37[.]112
118.166.1[.]124
118.168.193[.]123
128.14.50[.]146
128.14.50[.]147
220.136.111[.]66
220.136.179[.]5
220.136.76[.]200
43.240.14[.]44
haoxingfu01.ddns[.]net
shaoye11.hopto[.]org
Malicious apks:
03108e7f426416b0eaca9132f082d568
1cc88a79424091121a83d58b6886ea7a
2a1da7e17edaefc0468dbf25a0f60390
31e61e52d38f19cf3958df2239fba1a7
34efc3ebf51a6511c0d12cce7592db73
4d9a7e425f8c8b02d598ef0a0a776a58
808b186ddfa5e62ee882d5bdb94cc6e2
904b4d615c05952bcf58f35acadee5c1
a21322b2416fce17a1877542d16929d5
b84b0d5f128a8e0621733a6f3b412e19
bd90279ad5c5a813bc34c06093665e55
ff163a92f2622f2b8330a5730d3d636c
class.dex:
19e3daf40460aea22962d98de4bc32d2
36b2609a98aa39c730c2f5b49097d0ad
3ba4882dbf2dd6bd4fc0f54ec1373f4c
6cac4c9eda750a69e435c801a7ca7b8d
8a4ed9c4a66d7ccb3d155f85383ea3b3
b43335b043212355619fd827b01be9a0
b7afa4b2dafb57886fc47a1355824199
f89214bfa4b4ac9000087e4253e7f754
test.dex:
1bd7815bece1b54b7728b8dd16f1d3a9
307d2780185ba2b8c5ad4c9256407504
3e4bff0e8ed962f3c420692a35d2e503
57abbe642b85fa00b1f76f62acad4d3b
6e1926d548ffac0f6cedfb4a4f49196e
7714321baf6a54b09baa6a777b9742ef
7aa46b4d67c3ab07caa53e8d8df3005c
a0f88c77b183da227b9902968862c2b9






Botnets
Cybercrime
Google Android
Malware Descriptions
Malware Statistics
Malware Technologies
Mobile Malware
Trojan Banker



Authors



 Suguru Ishimaru





Roaming Mantis uses DNS hijacking to infect Android smartphones 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Isogeek 


							Posted on							April 18, 2018. 3:27 am 



Can you also create an info graphic showing evolution of ransomware attack complexity evolution from nuisance to extortion to cyber weapon
Reply 








Toni 


							Posted on							December 29, 2021. 7:35 am 



Hello and thank you to whoever wrote the article and to Kaspersky for having this on their website. This  sounds lot like what Ive been monitoring in my neighborhood, which is at least a year. There are these blue tooth devices that have been bouncing from house the and their names and Mac addresses don’tchange. About a year ago one connected to a new laptop and it destroyed it eventually. No idea til it was too late. I ve been trcking these “devices” since and I see the localizted to one section of the neighbood. They find away into the router. Is there any one I can report this too? Any researcher or team? I want help! I have plenty of evidence and the local cyber security that ive sopken too knows nothing and the authorities are no help! I just to give this to the right people and I am brand new to kaspersky and dont see anywhere to submit a report. thank you
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




 


APT10: Tracking down LODEINFO 2022, part II 






 


APT10: Tracking down LODEINFO 2022, part I 






 


Roaming Mantis reaches Europe 






 


Roaming Mantis, part V 






 


Roaming Mantis dabbles in mining and phishing multilingually 









Subscribe to our weekly e-mails
The hottest research right in your inbox




Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ








In the same category




 


A lightweight method to detect potential iOS malware 






 


Operation Triangulation: The last (hardware) mystery 






 


Windows CLFS and five exploits used by ransomware operators (Exploit #4 – CVE-2023-23376) 






 


Windows CLFS and five exploits used by ransomware operators (Exploit #3 – October 2022) 






 


Windows CLFS and five exploits used by ransomware operators (Exploit #2 – September 2022) 






 















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



























