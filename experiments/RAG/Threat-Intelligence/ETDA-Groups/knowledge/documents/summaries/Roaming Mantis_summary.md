
Report 1

Summary:
The threat actor known as Roaming Mantis, also referred to as Shaoye, has been identified as conducting a long-term cyberattack campaign targeting Android devices in the Asian region, particularly in Japan, South Korea, and Taiwan. The threat actor has implemented a DNS changer function in the Android malware Wroba.o/Agent.eq to target specific Wi-Fi routers, mainly in South Korea. This new capability allows the threat actor to compromise the DNS settings of the routers and redirect users to malicious landing pages. The threat actor has been observed using smishing as the main initial infection method, delivering malicious URLs to users' devices. The campaign has expanded to target regions beyond South Korea, including France, Japan, Germany, the United States, Taiwan, Turkey, and others. Kaspersky experts are concerned about the potential for the DNS changer to be used in other regions and cause significant security issues. The threat actor's activities have been detected and monitored through IoCs such as malicious domains, landing pages, and rogue DNS servers. The discovery of this new DNS changer implementation highlights the evolving tactics and techniques of the Roaming Mantis threat actor.





Report 2

The threat actor known as "Roaming Mantis" has been identified targeting Japanese and Korean users with a new type of Android spyware. The spyware pretends to be security applications on the Google Play store, with low download numbers. The spyware collects device information, steals SMS/MMS messages, and has command and control functions sent via Tencent Push Notification Service. Additionally, fake Korean police applications have been found targeting Korean users. The spyware hides and accesses control server addresses via Twitter accounts, with functions to disable anti-spam call applications. The spyware is believed to be connected to the ongoing MoqHao campaigns, with common spy commands and crash report keys. McAfee is collaborating with Japanese law enforcement to combat the attack campaign. The spyware aims to track device location and eavesdrop on call conversations, distributed through official application stores. McAfee Mobile Security detects this threat as Android/SpyAgent. The attack campaign is ongoing, and users are advised to avoid installing apps from unofficial sources and keep their devices updated with security software. (Report date: Aug 07, 2019)





Report 3

Summary:
- Threat actor: Roaming Mantis
- Region: France
- Operating sector: Mobile phone users
- Type of company: Not specified
- Date: July 4, 2022
- Evidence of capability: Roaming Mantis conducted an ongoing smishing campaign targeting French mobile phone users, deploying the MoqHao Android malware or redirecting to an Apple login credential harvesting page. The campaign impacted around 70,000 Android devices in France. The threat actor, Roaming Mantis, is a financially motivated Chinese group with a history of targeting developed countries.
- Novelty of tools and techniques: Roaming Mantis used geofencing and operating system checking capabilities to tailor attacks and hinder detection efforts. The MoqHao Android Remote Access Trojan (RAT) has information-stealing and backdoor capabilities, spreading via SMS. The threat actor's infrastructure included separate servers for Android payloads, Apple phishing, and MoqHao C2 servers. The campaign utilized sophisticated techniques such as DES-encrypted C2 server retrieval from social network profiles.
- Operation time window: Ongoing campaign targeting France.





Report 4

Summary:
- Threat actor: Roaming Mantis
- Region: Global
- Operating sector: Cybersecurity
- Type of company targeted: Android running machines
- Date: Since April 2018
- Capability: Utilized DNS hijacking attack vector, phishing SMS with malicious links, and crypto mining script on PCs
- Novelty: Used over 120 malicious domains with similar syntax patterns, targeting android devices with Sagawa APK
- Ongoing analysis to uncover more indicators related to Roaming Mantis and Sagawa APK.





Report 5

Malformed report.





Report 6

Malformed report.





Report 7

Summary:
The threat actor known as Roaming Mantis has been active since 2017, with a focus on financial crime. They have targeted victims primarily in the Asian region, with thousands of daily connections to their command and control infrastructure, mostly from Korean devices. The group has used novel techniques such as DNS hijacking to distribute malware, with a significant evolution in their tactics over time. They have expanded geographically, added phishing options for iOS devices, and incorporated crypto-mining capabilities. The group's attack methods have continuously improved, with a shift towards techniques that evade detection and tracking. Roaming Mantis has also targeted European countries and implemented new tools like a DNS changer in their malicious mobile apps. The threat actor remains active, with ongoing smishing campaigns targeting countries like France.





Report 8

Summary:
The threat actor known as Roaming Mantis targeted a Japanese MNO in a phishing campaign using Android malware and phishing scams. The campaign involved hijacking DNS settings on routers in Japan to redirect users to malicious IP addresses, leading to the installation of Trojanized applications containing Android Trojan-Banker. The threat actor reappeared in 2019 with new techniques, including a phishing website targeting a Japanese MNO, NTT DoCoMo. The landing page of Roaming Mantis showed similarities with a phishing campaign called GaoHao, suggesting a possible connection between the two. The threat actor used rogue DNS to control victims and employed novel techniques to spread malware and conduct phishing attacks. The campaign's IoCs included various landing page IP addresses and phishing websites. The report provides insights into the evolving tactics and targets of the Roaming Mantis threat actor.





Report 9

Summary:
The threat actor known as Roaming Mantis has been conducting a smishing campaign targeting Asian Android users since 2018, impersonating a logistics company to steal SMS messages and contact lists. In the second half of 2020, they enhanced their campaign by using dynamic DNS services and spreading phishing URLs that infected victims with the fake Chrome application MoqHao. Since January 2021, they have been targeting Japanese users with a new malware called SmsSpy, capable of infecting Android devices based on their OS version. The threat actor's ability to download malicious payloads based on OS versions allows them to infect a wider range of devices. The malware's main purpose is to steal phone numbers and SMS messages, masquerading as security services like Google Play or Chrome. The threat actor uses different C2 servers and phishing domains to hide their activities. McAfee Mobile Security detects this threat as Android/SmsSpy and provides protection against data loss. The threat actor's evolving tactics and infrastructure suggest multiple groups or individuals behind the attacks. The report provides IoC details for further investigation and mitigation efforts. (Date: May 05, 2021)





Report 10

Summary:
The threat actor known as Roaming Mantis has been observed engaging in mining and phishing activities across multiple languages, targeting victims primarily in Asia, including South Korea, Bangladesh, and Japan. The threat actor has expanded its operations geographically to cover Europe and the Middle East, supporting 27 languages on their landing pages and malicious apk files. Additionally, Roaming Mantis has added a phishing option for iOS devices and crypto-mining capabilities for PCs. The threat actor has evolved rapidly, implementing new techniques such as using the email POP protocol to retrieve C2 addresses, dynamically generating apk file names, and including a backdoor command for network validation. The campaign has shown significant growth, targeting countries beyond Asia and indicating strong financial motivation. Kaspersky products detect this threat as HEUR:Trojan-Banker.AndroidOS.Wroba.





Report 11

Summary:
The threat actor known as Roaming Mantis has been infecting smartphones through hacked Wi-Fi routers, initially targeting users from Japan, Korea, and China. The malware has since spread worldwide, adding two dozen languages to its capabilities. Roaming Mantis uses compromised routers to infect Android devices, redirects iOS devices to phishing sites, and runs CoinHive cryptomining scripts on desktops and laptops through DNS hijacking. The threat actor has expanded its reach to iOS devices and added cryptocurrency mining capabilities to its arsenal. The report was published on May 18, 2018, and provides details on the novel techniques used by Roaming Mantis to target a wide range of devices and users globally.





Report 12

Summary:
The threat actor known as Roaming Mantis has evolved rapidly, targeting victims in multiple regions including Asia, Europe, and the Middle East. They have expanded their operations to include web crypto-mining for PC and an Apple phishing page for iOS devices. The threat actor has demonstrated the capability to support 27 languages and has used DNS hijacking to spread malicious Android applications. They have also utilized a malicious content delivery system to spread malware, including a new method involving prezi.com. The threat actor has stolen a significant amount of data from victims worldwide, including sensitive information such as credit card details and passwords. The Roaming Mantis group continues to develop new attack methods and expand their targets, posing a significant threat to Android and iOS users. The malware is detected by Kaspersky Lab products as HEUR:Trojan-Banker.AndroidOS.Wroba.





Report 13

Summary:
The threat actor known as Roaming Mantis has expanded its operations to Europe, specifically targeting France and Germany in addition to Japan, Taiwan, and Korea. The campaign primarily focuses on infecting Android devices through smishing messages that lead to phishing pages or the download of the Wroba malware. The actor has employed anti-researcher tricks in the landing page to evade detection and has made modifications to the loader module and payload of Wroba.g/Wroba.o, including changing the programming language to Kotlin and adding new backdoor commands. The group has shown a strong financial motivation and is expected to continue its attacks in 2022. The report provides technical analysis and MD5 hashes of the Wroba.o malware. The activities of Roaming Mantis were observed between July 2021 and January 2022.





Report 14

Summary:
The threat actor known as Roaming Mantis utilized DNS hijacking to infect Android smartphones in March 2018, targeting users in the Asian region. The malware, named Trojan-Banker, was distributed through compromised routers, redirecting users to malicious websites to install Trojanized applications. The malware aimed to steal user information, including two-factor authentication credentials, and gain control over compromised devices. The malware communicated with a command and control (C2) infrastructure, with most victims having their device locale set to Korean. The threat actor displayed a bias towards Korean and Traditional Chinese languages. The malware was regularly updated, indicating an active threat actor. Kaspersky Lab products detected the malware as Trojan-Banker.AndroidOS.Wroba. The campaign was primarily focused on Asian countries, with South Korea, Bangladesh, and Japan being the most affected. Kaspersky Lab recommended changing default router login credentials and updating firmware to prevent similar attacks. The threat actor behind Roaming Mantis remains active, and further tracking of the campaign is ongoing.





Report 15

The RoamingMantis cybercrime group, known for infecting Android devices with malware such as FakeCop, FakeSpy, MoqHao, and FunkyBot, has expanded its operations to target European Apple accounts and Android devices. The group has been active since 2017, primarily focusing on Asian countries but has recently targeted European countries such as Denmark, France, Germany, Italy, Netherlands, Sweden, and Finland, as well as the UK, Switzerland, Brazil, and Japan. The group uses SMS spam and phishing websites impersonating local postal/delivery services to lure victims into downloading malicious components. They have also incorporated phishing attacks on Apple ID accounts, successfully stealing credentials at an alarming rate. The group's monetization schemes include bitcoin mining, money laundering, and banking fraud. The control panels used by RoamingMantis are in Chinese, indicating an unusual targeting of European financial organizations. The group's novel techniques and wide regional coverage pose a significant threat to mobile users in Europe. Date: June 25, 2020.





Report 16

Summary:
The threat actor "Roaming Mantis" has been identified deploying a new version of XLoader that disguises as Android apps and an iOS profile, with links to FakeSpy. The threat actor targets users in Japan through fake websites mimicking a Japanese mobile phone operator. The XLoader variant poses as a security app for Android devices and uses a malicious iOS profile to target iPhone and iPad devices. The threat actor has evolved its deployment techniques and code, with the latest variant labeled XLoader version 6.0. The threat actor uses social media platforms like Twitter to hide the real C&C addresses and collects unique identifiers of mobile devices. The threat actor has also been linked to FakeSpy, showing similarities in deployment techniques and C&C server hiding methods. The threat actor has been active since 2018 and continues to evolve its tactics, with newer variants posing as pornography apps targeting South Korean users. The threat actor has also used Instagram and Tumblr to hide C&C addresses in a newer variant labeled XLoader version 7.0. Users are advised to remove malicious profiles using official tools and practice caution when downloading apps or files from untrusted sources. Trend Micro offers solutions like Mobile Security for Android to protect against such threats.


