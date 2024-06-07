# Reference for threat actor for "Roaming Mantis"

**Title**: Roaming Mantis part III: iOS crypto-mining and spreading via malicious content delivery system | Securelist

**Source**: https://securelist.com/roaming-mantis-part-3/88071/

## Content















Roaming Mantis part III: iOS crypto-mining and spreading via malicious content delivery system | Securelist


































































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


 











 

Malware descriptions

Roaming Mantis, part III 

Malware descriptions

01 Oct 2018

  minute read								








 

Authors




GReAT



iOS crypto-mining and spreading via malicious content delivery system


In Q2 2018, Kaspersky Lab published two blogposts about Roaming Mantis sharing details of this new cybercriminal campaign. In the beginning, the criminals used DNS hijacking in vulnerable routers to spread malicious Android applications of Roaming Mantis (aka MoqHao and XLoader), spoofing legitimate applications such as Facebook and Chrome. During our research, it became clear that Roaming Mantis has been rather active and has evolved quickly. The group’s malware now supports 27 languages, including multiple countries from Asia and beyond, Europe and the Middle East. In addition, they have started using web crypto-mining for PC, and an Apple phishing page for iOS devices.
You can check previous chapters of this research here:

Roaming Mantis uses DNS hijacking to infect Android smartphones (April 2018)
Roaming Mantis dabbles in mining and phishing multilingually (May 2018)

In addition we would like to thank and credit security researchers from LAC Co. Ltd. for a very insightful article describing how vulnerable routers were compromised by the Roaming Mantis group, which was disclosed in their Japanese blogpost in June 2018. According to this research, the threat actor logged in to their router using default ID and password, and changed legitimate DNS settings to rogue DNS settings, where the router’s control panel was accessible over the Internet.
The Roaming Mantis group did not stop its activities after publication of our reports. We have confirmed several new activities and changes to their illegal profit-gaining methods such as web crypto mining for iOS devices, spreading via malicious content delivery system and so on. This blogpost reveals some details of our new findings related to Roaming Mantis, based on our research.
Web crypto-mining for iOS devices
The criminals previously targeted iOS devices using an Apple phishing site to steal credentials. However, they changed the HTML source code of the malicious landing page as follows:
Part of HTML source code of the malicious landing page for iOS
The code above shows that they disabled redirection to the fake Apple portal (with a phishing page) and added code with a web mining script (previously used only for the PC platform) to run mining on iOS devices.
If the user visits this landing page from an iOS device, a blank page displays in the web browser. In the background, CPU usage increases to 90% immediately.
Screen capture of the landing page and CPU monitoring tool
Interestingly, the day after we confirmed this, the attacker switched back to Apple phishing again. We believe that the criminals, at that time, were testing the possible revenue from web mining on iOS devices, looking for an efficient way to monetize their activities.
Filtering Japanese devices
One thing we noticed is that the criminals responded to a number of articles and research activities coming from Japan. The new feature was added in the landing page to filter out Japanese environment:
Added confirmation of Japanese environment for filtering
It looks like they want to slow down infections of Japanese targets for the time being.
Spreading via another malware delivery system
In the middle of July 2018, the live landing page we had been monitoring unfortunately went dark. However, the malicious APK files of Roaming Mantis, detected as “Trojan-Banker.AndroidOS.Wroba.al”, were still being detected by our customers, according to our KSN data.
Number of detected users from KSN data (Jun 10, 2018 – Sep 10, 2018)
Our deeper investigation revealed that their new malware spreading method was the one used by other Android malware, the “sagawa.apk” delivery system. We published a Japanese blogpost of this Android malware in January 2018. Trend Micro named it FAKESPY and published a blogpost about it, “FakeSpy Android Information-Stealing Malware Targets Japanese and Korean-Speaking Users”. According to our previous blogpost, the infection vector involved users received a phishing SMS message spoofing a notification from a Japanese delivery company. The message contained a malicious URL. If the user clicked it, the server displayed a fake web site that downloaded and installed the malicious application “sagawa.apk”. We discovered two types of such “sagawa.apk” samples:




Type A
Type B


File name
sagawa.apk
sagawa.apk


md5
956f32a28d0057805c7234d6a13aa99b
a19f4cb93274c949e66efe13173c95e6


File size
427KB (437,556)
2.3MB (2,381,665)


Loader module
\classes.dex
\classes.dex +
\lib\arm64-v8a\libkao.so
\lib\armeabi-v7a\libkao.so
\lib\x86\libkao.so
\lib\x86_64\libkao.so


Encrypted payload (enc_data)
\assets\a
\assets\code.so


Decrypt algorithm
payload =  base64_dec(zlib_dec(enc_data));
aes_key = base64_dec(hardcoded data);
payload = AES_dec(enc_data, aes_key);


Alias
MoqHao (McAfee)
XLoader (TrendMicro)
FAKESPY (TrendMicro)


Old file name
facebook.apk
chrome.apk
${random}.apk
sagawa.apk



Based on detailed static analysis, they belong to different Android malware families. Both Type A and Type B have common features, such as monitoring SMS messages and stealing data from infected devices. However, there are differences in their code structure, communication protocol and other features. One significant difference is that Type B targets Japan only, unlike Type A which is multilingual. Type B contains hardcoded strings that are displayed to infected users. These strings are in Japanese only.
Japanese messages displayed to infected users
In addition, this malware confirms whether a domestic Japanese prepaid card application is installed on the infected device.
Check for the domestic Japanese prepaid card application “Au Wallet”
If the application is installed on the device, the malware downloads and installs a fake application as its update.
Unfortunately, the relationship between the Roaming Mantis group and the service owner of the “sagawa.apk” delivery mechanism isn’t very clear at the moment. They might just use the same service as customers, or might not. However, it is clear that these criminal groups use the same malware-spreading eco-system for spreading their Android malware.
Researchers may use the following simplified python scripts to extract the payload from “sagawa.apk”:

sagawa.apk_typeA_payload_extractor.py






#!/usr/bin/env python

import sys
import zlib
import base64 

data = open(sys.argv[1],"rb").read()
dec_z = zlib.decompress(data)
dec_b = base64.b64decode(dec_z)

with open(sys.argv[1]+".dec","wb") as fp:
    fp.write(dec_b)




123456789101112

#!/usr/bin/env python import sysimport zlibimport base64  data = open(sys.argv[1],"rb").read()dec_z = zlib.decompress(data)dec_b = base64.b64decode(dec_z) with open(sys.argv[1]+".dec","wb") as fp:    fp.write(dec_b)



 

sagawa.apk_typeB_payload_extractor.py






#!/usr/bin/env python

import sys
from Crypto.Cipher import AES, ARC4
import base64 

data = open(sys.argv[1],"rb").read()
key = sys.argv[2]
aes_key = base64.b64decode(key) // key is H8chGVmHxKRdjVSO14Mvgg== in libkao.so
aes = AES.new(aes_key) 
dec = aes.decrypt(data)

with open(sys.argv[1]+".dec","wb") as fp:
    fp.write(dec)




1234567891011121314

#!/usr/bin/env python import sysfrom Crypto.Cipher import AES, ARC4import base64  data = open(sys.argv[1],"rb").read()key = sys.argv[2]aes_key = base64.b64decode(key) // key is H8chGVmHxKRdjVSO14Mvgg== in libkao.soaes = AES.new(aes_key) dec = aes.decrypt(data) with open(sys.argv[1]+".dec","wb") as fp:    fp.write(dec)



 
Spreading via prezi.com like a scam
We also observed another malware distribution method of Roaming Mantis which is linked to prezi.com. Prezi is a popular computer application and online service to create dynamic presentations. The criminals used this service to spread their scam. When a user visits a page crafted by the attackers, a link is shown offering free content such as adult video, a game, a comic, music and so on, like pirate editions.
Redirection to a scam page
Based on our research, there were multiple messages leveraging different social engineering tricks to invite users to a scam website. On the other hand, the Roaming Mantis’ landing page was found to be linked to several such accounts carrying out redirections.
Corrupted landing page code from Roaming Mantis posted on prezi.com
However, fortunately this code does not work because of mistakes made during the code preparation stage.
Records of stolen data
Kaspersky Lab discovered fragments of data stolen from victims’ Android devices via Type A of the malware, which suggests thousands of compromised victims:
Suspected stolen data from victims’ Android devices
This data contained phone number, date, IP, language, email/id, password, name, date of birth, address, credit card information including cvv, bank information, and secret question and answer in Simplified Chinese. Data headers in Chinese suggest that the attackers are fluent in Chinese – unless this is a false flag, of course. The first column seems to contain the record number, which in July was already over 4,800. The user device language setting may indicate victims’ geography. Below is a pie chart created from the language data:
Victims’ language settings 
The top language is “en-us” (39%), the second is “ko-kr”, the third is “ru”. Judging from this data, victims’ geographical distribution has changed significantly since our first report. This might be due to the update adding support for 27 languages and the new distribution strategies. The reason why the “en-us” is the most popular could be because English is used as second language in several countries.
Conclusions
In previous reports, we claimed that the Roaming Mantis campaign had evolved significantly in a short period of time, applying new attack methods and expanding its targets. It seems that the attack doesn’t stop developing. In our recent research, we found that they probed using a web miner for iOS, instead of redirecting to a fake Apple website.
Another new method they applied is the use of a malware delivery eco-system that is probably operated by a third party and was used to spread other (maybe even unrelated) malware in the past. The infection vector in that case was an SMS message with a malicious link that led a user to a fake web site that offered a download of the malicious apk file “sagawa.apk”.  It is not clear how Roaming Mantis and the distributor of “sagawa.apk” are related, but it’s worth mentioning the fact that they are now using the same eco-system.
Roaming Mantis is also trying to spread its malware via prezi.com, with a scam that offers a visitor free content such as videos and more.
Judging from the list of stolen credentials, the attackers seems to have stolen a large amount of data from victims worldwide. This gives us a glimpse of the real scale of the attack, but we believe that this is just a tip of the iceberg.
We strongly recommend that Android users turn off the option that allows installation of applications from third-party repositories, to keep their device safe. They should also be suspicious if their phones become unusually hot, which may be a side-effect of the hidden crypto-mining application in action.
Kaspersky Lab products detect this malware with the following verdict:

HEUR:Trojan-Banker.AndroidOS.Wroba

IoCs
Malicious hosts:

59.105.6[.]230
sagawa-otqwt[.]com
sagawa-polsw[.]com

Hashes of Type A:

956f32a28d0057805c7234d6a13aa99b sagawa.apk
3562f9de6dbe70c2e19a20d8683330ce \classes.dex
01fa0039b62c5db8d91dfc6b75b246f8 decrypted payload (dex file) from \assets\a

Hashes of Type B:

a19f4cb93274c949e66efe13173c95e6
5e913208ecc69427efb6bbf9e6505624 \classes.dex
67bc2e8beb14b259a5c60fe7a31e6795  \arm64-v8a/libkao.so
f120f5f78c7ef762996314cf10f343af  \armeabi-v7a/libkao.so
efe54c22e2b28a44f723d3479487620c   \x86_64/libkao.so
e723c6aec4433f3c6e5d3d24fe810e05   \x86/libkao.so
daeccda295de93cf767fd39a86a44355 decrypted payload (jar file) from \assets\code.so
581b08b277a8504ed222a71c19cea5f9 classes.dex from decrypted payload







Apple iOS
Botnets
Google Android
Malware Descriptions
Miner
Mobile Malware
Phishing



Authors




GReAT





Roaming Mantis, part III 
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




 


Coyote: A multi-stage banking Trojan abusing the Squirrel installer 






 


FakeSG campaign, Akira ransomware and AMOS macOS stealer 






 


Advanced threat predictions for 2024 






 


Stealer for PIX payment system, new Lumar stealer and Rhysida ransomware 






 


Updated MATA attacks industrial companies in Eastern Europe 









Subscribe to our weekly e-mails
The hottest research right in your inbox




Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ








In the same category




 


Coyote: A multi-stage banking Trojan abusing the Squirrel installer 






 


Cracked software beats gold: new macOS backdoor stealing cryptowallets 






 


New macOS Trojan-Proxy piggybacking on cracked software 






 


BlueNoroff: new Trojan attacking macOS users 






 


Ducktail fashion week 






 















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



























