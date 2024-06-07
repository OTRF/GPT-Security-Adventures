# Reference for threat actor for "Roaming Mantis"

**Title**: Roaming Mantis, part IV | Securelist

**Source**: https://securelist.com/roaming-mantis-part-iv/90332/

## Content















Roaming Mantis, part IV | Securelist


































































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

Roaming Mantis, part IV 

Malware descriptions

03 Apr 2019

  minute read								








 

Authors




GReAT



Mobile config for Apple phishing, and re-spreading an updated malicious APK (MoqHao/XLoader)


One year has passed since we published the first blogpost about the Roaming Mantis campaign on securelist.com, and this February we detected new activities by the group. This blogpost is follow up on our earlier reporting about the group with updates on their tools and tactics.
Mobile config for Apple phishing
Our key finding is that the actor continues to seek ways to compromise iOS devices and has even built a new landing page for iOS users. When an iPhone user visits this landing page, they sees pop-up messages guiding them to the malicious iOS mobile config installation:
Pop-up messages and mobile config installation
After installation of this mobile config, the phishing site automatically opens in a web browser and collected information from the device is sent to the attacker’s server. This information includes DEVICE_PRODUCT, DEVICE_VERSION, UDID, ICCID, IMEI and MEID.
XML and CA in mobile config
The CA contains the suspected developer’s email address, “zeeyf79797@yahoo.co[.]jp”, which could be malicious.
We created a test account for this research and used the account credentials at the phishing site. As soon as the threat actor received the ID and password, the criminals attempted to log in to the account from Hong Kong. After entering the credentials, we were directed to the next page, which tried to steal the two-factor authentication code (PIN) sent to the device.
Phishing page for stealing apple ID and two-factor authentication
Re-spreading the updated sagawa.apk Type A (MoqHao/XLoader)
On the Android front, our telemetry data shows a new wave of malicious APK files which we detect as “Trojan-Dropper.AndroidOS.Wroba.g”.
sagawa.apk Type A has spread since Feb 26
We have analyzed the malicious APK file and confirmed that it is definitely a variant of sagawa.apk Type A malware, also known as MoqHao (Mcafee) and XLoader (TrendMicro). Type A malware was earlier distributed via SMS in Japan.
We also found out that the threat actors had compromised routers to overwrite DNS settings and discovered that the following two features were updated as well:

Decryption algorithm for encrypted payload in Trojan-Dropper module
Stored destination and accounts for getting real C2

Decryption algorithm for encrypted payload in Trojan-Dropper module
Compared to the previous version, the Trojan-Dropper’s decryption function has been altered slightly (change highlighted in purple):
Added 4-byte skip from encrypted data in decompiled code
Why did the attackers change it? Well, the simplified Python script for extracting encrypted payload was disclosed in our previous blog posts. We are suspecting that the actor considered this and introduced some minor changes to their decryption algorithm to evade detection by security products and researchers.
However, we have updated the simplified Python script according to this change:
sagawa.apk_typeA_payload_extractor_1.01.py





#!/usr/bin/env python

import sys
import zlib
import base64 

data = open(sys.argv[1],"rb").read()
dec_z = zlib.decompress(data[4:])            # open.skip(4);
dec_b = base64.b64decode(dec_z)

with open(sys.argv[1]+".dec","wb") as fp:
    fp.write(dec_b)




123456789101112

#!/usr/bin/env python import sysimport zlibimport base64  data = open(sys.argv[1],"rb").read()dec_z = zlib.decompress(data[4:])            # open.skip(4);dec_b = base64.b64decode(dec_z) with open(sys.argv[1]+".dec","wb") as fp:    fp.write(dec_b)




Stored destination and accounts for getting real C2
In the previous campaign, the three accounts “haoxingfu11”, “haoxingfu22” and “haoxingfu33” on @outlook.com were stored inside the samples for the purpose of retrieving the C2 server address. In order to fetch the C2 server address, the email service was used the real C2 destination was delivered to the victims in an encrypted form from the email subject. In the new version the actor has switched their tactics for retrieving the C2 address from email service to fetching it from Twitter.
“https://twitter.com/%s” is stored in the malware
The three suspected Twitter accounts were easily found as well, because the sample had the account IDs stored together, separated by the “|” character just like the old samples:
Three account IDs separated by the “|” character
The decryption algorithm for the real C2 address remained untouched – the malware connects to the extracted real C2 via web socket. In addition to the three accounts mentioned earlier, we found several other accounts:

lucky88755
lucky98745
lucky876543
gyugyu87418490
luckyone1232
sadwqewqeqw

The decryption algorithm for extracting the real C2 from Chinese characters is the same as in the previous sample, so our scripts from the old blogpost will still work. All the accounts are related to the same IP, although the port numbers are different. The table below shows these changes as derived from the account “@luckyone1232”.



Datetime (UTC)
Encrypted data
Decrypted real C2


February 25 2019 11:30
傘傠傘偠傈傠偠傠傐傸偘储傀傐僨傀僨僸傸傀
114.43.155[.]227:28855


February 26 2019 08:00
傀傸傸偠傠傠傠偘傘储偘傰傠僠僨傀僨僸傸傀
220.136.47[.]169:28855


March 02 2019 01:00
傀傸傸偠傠傠傠偘傘僘偘傰傈傐僨傀僨僸傸傀
220.136.49[.]137:28855


March 05 2019 06:00
傀傸傸偠傠傠傠偘傠僘偘傰僀傸僸僐傀傐
220.136.39[.]1:28855


March 07 2019 03:00
傘傠僸偠傠傈僐偘傰傈储偈傀傰傈僀傸僸僐傀傐
118.168.130[.]236:28855


March 09 2019 10:00
傠傠偈傀傰傸偠傸傰傐偘储傀僨僨傀僨僸傸傀
61.230.210[.]228:28855


March 13 2019 01:00
傘傸傐偠傸储储偘傰储傈偈傈傀僨傀僨僸傸傀
125.227.174[.]35:28855


March 21 2019 01:00
傘偘傰傠僠偈傀储傠偠傈僸僀傸僸僐傀傐
1.169.203[.]48:28855



We also noticed that the threat actor has introduced a new backdoor command “getPhoneState”. The following table shows the comparison of the older and newer versions of the malware:



Date
August 08 2018
March 03 2019


MD5
956f32a28d0057805c7234d6a13aa99b
651b6888b3f419fc1aac535921535324


File size
427.3 KB (437556 bytes)
396.0 KB (405504 bytes)


Malware type
sagawa.apk Type A
MoqHao (McAfee)
XLoader (TrendMicro)
sagawa.apk Type A
MoqHao (McAfee)
XLoader (TrendMicro)


Encrypted payload (enc_data)
\assets\a
\assets\bin


Decryption algorithm for payload
payload = base64.b64decode(zlib.decompress(enc_data));
payload = base64.b64decode(zlib.decompress(enc_data[4:]));


Backdoor commands
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
ping
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
ping
getPhoneState


Stored destination
@outlook.com (email)
https://twitter.com/%s (SNS)


Accounts
haoxingfu11
haoxingfu22
haoxingfu33
luckyone1232
sadwqewqeqw
gyugyu87418490


RegExp
abcd
<title>abcd([\\u4e00-\\u9fa5]+?) “;


Decryption algorithm for real C2
for i in range(len(ext)):
dec = dec + chr((ord(ext[i]) – 0x4e00) >> 3 ^ ord(‘beg'[j]))
j = (j+1) %3
for i in range(len(ext)):
dec = dec + chr((ord(ext[i]) – 0x4e00) >> 3 ^ ord(‘beg'[j]))
j = (j+1) %3



Rogue DNS settings in compromised routers again
In late February 2019, we detected a URL query of a malicious DNS changer. Here is an example:
URL query of malicious DNS changer
The router’s DNS setting is potentially compromised if the device reads the URL query of the DNS changer from localnet under a router with the following conditions:

No authentication for router panel from localnet
The device has an admin session for the router panel
Simple ID and password (or default) for route panel like admin:admin

As we have observed, several hundred routers have been compromised and all pointed to the rogue DNS IPs.
This code overwrites the rogue DNS IPs below into the DNS settings of routers:

171.244.33[.]114
171.244.33[.]116

Geographical expansion
According to our detection data, new variants of sagawa.apk Type A (Trojan-Dropper.AndroidOS.Wroba.g) have been detected in the wild, based on our KSN data from February 25, 2019 to March 20, 2019.
Geographical expansion from KSN data
The worst affected countries are Russia, Japan, India, Bangladesh, Kazakhstan, Azerbaijan, Iran and Vietnam. Our products detected this malware over 6,800 times for over 950 unique users during this period. We believe this attack wave has a much bigger scale and these numbers reflect only a small part of this campaign.
Conclusion
We have seen increased distribution of sagawa.apk Type A since late February 2019. This wave is characterized by a new attack method of phishing with malicious mobile config, although the previously observed DNS manipulation is also still actively used. We find the use of malicious mobile config especially alarming as this may cause serious problems for the users. As explained in an earlier blog post, “the profile could configure the device to use a malicious proxy or VPN, effectively allowing the attacker to monitor everything.”
We recommend users take the following steps:

Change the default ID and password, and apply the relevant security patches to counter these threats;
For Android users: do not download APKs from third-party sources;
For iOS users: do not install a non-trusted third-party mobile config.

For further information about this threat actor, please refer to our previous blog posts about Roaming mantis:

Roaming Mantis uses DNS hijacking to infect Android smartphones
Roaming Mantis dabbles in mining and phishing multilingually
Roaming Mantis, part III: iOS crypto-mining and spreading via malicious content delivery system

Kaspersky Lab products detect this malware for Android as:

HEUR:Trojan-Banker.AndroidOS.Wroba
HEUR:Trojan-Dropper.AndroidOS.Wroba

Finally, we would like to show our appreciation to the Japanese researchers @ninoseki and @papa_anniekey, who have shared and discussed with us their results of Roaming Mantis campaign research. The criminals are still rapidly improving their methods: we discovered some updated sagawa.apk Type A this April, the fresh sample has embedded DES algorithm instead of some decryption feature. We’re going to track Roaming Mantis activity and publish any new activities in the future.
Indicators of compromise (IoCs) examples
Malicious hosts:



114.43.155[.]227
real C2


220.136.47[.]169
real C2


220.136.49[.]137
real C2


220.136.39[.]1
real C2


118.168.130[.]236
real C2


171.244.33[.]114
RogueDNS


171.244.33[.]116
RogueDNS


61.230.153[.]211
Landing page


154.223.62[.]130
Landing page


ffakecg[.]com
Landing page


sagawa-mwm[.]com
Landing page


sagawa-mqd[.]com
Landing page


sagawa-bz[.]com
Landing page


nttdocomo-qae[.]com
Landing page


nttdocomo-qat[.]com
Landing page


Suspicious Twitter accounts:

luckyone1232
sadwqewqeqw
gyugyu87418490
lucky88755
lucky98745
lucky876543

sagawa.apk Type A and its modules:



417a6af1172042986f602cc0e2e681dc
APK file


651b6888b3f419fc1aac535921535324
APK file


0a4e8d3fe5ee383ba3a22d0f00670ce3
APK file


870697ddb36a8f205478c2338d7e6bc7
APK file


7e247800b95c643a3c9d4a320b12726b
\classes.dex


7cfb9ed812e0250bfcb4022c567771ec
\classes.dex


8358d2a39d412edbd1cf662e0d8a9f19
\classes.dex


7cfb9ed812e0250bfcb4022c567771ec
\classes.dex


af2890a472b85d473faee501337564a9
Decrypted dex file


c8d7475a27fb7d669ec3787fe3e9c031
Decrypted dex file


d0848d71a14e0f07c6e64bf84c30ee39
Decrypted dex file


e2b557721902bc97382d268f1785e085
Decrypted dex file








Apple iOS
Botnets
Google Android
Malware Descriptions
Mobile Malware
Phishing



Authors




GReAT





Roaming Mantis, part IV 
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



























