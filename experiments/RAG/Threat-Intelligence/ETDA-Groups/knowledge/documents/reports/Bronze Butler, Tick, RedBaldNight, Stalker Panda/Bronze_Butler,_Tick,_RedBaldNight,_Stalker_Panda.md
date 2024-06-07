# Threat actor: Bronze Butler, Tick, RedBaldNight, Stalker Panda

**UUID**: 334d9e0e-dab2-4bc5-8db2-5ab016f36947

**First seen**: 2006

**Source last modified**: 2023-04-26

## Threat actor aliases

Bronze Butler (SecureWorks), CTG-2006 (SecureWorks), Tick (Symantec), TEMP.Tick (FireEye), RedBaldNight (Trend Micro), Stalker Panda (Crowdstrike)

## Description

(SecureWorks) CTU analysis indicates that Bronze Butler primarily targets organizations located in Japan. The threat group has sought unauthorized access to networks of organizations associated with critical infrastructure, heavy industry, manufacturing, and international relations. Secureworks analysts have observed Bronze Bulter exfiltrating the following categories of data:

• Intellectual property related to technology and development
• Product specification
• Sensitive business and sales-related information
• Network and system configuration files
• Email messages and meeting minutes

The focus on intellectual property, product details, and corporate information suggests that the group seeks information that they believe might be of value to competing organizations. The diverse targeting suggests that Bronze Bulter may be tasked by multiple teams or organizations with varying priorities.

## Sponsor type and motivation

**Sponsor**: State-sponsored, National University of Defense and Technology

**Motivation**: Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in

Critical infrastructure, Defense, Engineering, Government, High-Tech, Industrial, Manufacturing, Media, Technology, International relations

## Observed attacked countries where victims operate in

China, Hong Kong, Japan, Russia, Singapore, South Korea, Taiwan, USA

## Observed usage of tools

9002 RAT, 8.t Dropper, Blogspot, Daserf, Datper, Elirks, Gh0st RAT, gsecdump, HomamDownloader, Lilith RAT, Mimikatz, Minzen, rarstar, ShadowPad Winnti, SymonLoader, Windows Credentials Editor

## Reported hacking operations

2015-07: Symantec discovered the most recent wave of Tick attacks in July 2015, when the group compromised three different Japanese websites with a Flash (.swf) exploit to mount watering hole attacks. Visitors to these websites were infected with a downloader known as Gofarer (Downloader.Gofarer). Gofarer collects information about the compromised computer and then downloads and installs Daserf.
https://www.symantec.com/connect/blogs/tick-cyberespionage-group-zeros-japan

2017-04: Wali is a backdoor used for targeted attacks. It gathers information about the compromised machines and their networks, in addition to stealing sensitive information and credentials. Wali’s operators use this information to move laterally in an organization and compromise more machines.
https://www.cybereason.com/blog/labs-shadowwali-new-variant-of-the-xxmm-family-of-backdoors

2017-11: Daserf’s infection chain accordingly evolved, as shown below. It has several methods for infecting its targets of interest: spear phishing emails, watering hole attacks, and exploiting a remote code execution vulnerability (CVE-2016-7836, patched last March 2017) in SKYSEA Client View, an IT asset management software widely used in Japan.
https://blog.trendmicro.com/trendlabs-security-intelligence/redbaldknight-bronze-butler-daserf-backdoor-now-using-steganography/

2018-06: Tick Group Weaponized Secure USB Drives to Target Air-Gapped Critical Systems
https://unit42.paloaltonetworks.com/unit42-tick-group-weaponized-secure-usb-drives-target-air-gapped-critical-systems/

2019: Operation “ENDTRADE”
By the first half of 2019, we found that the group was able to zero in on specific industries in Japan from which it could steal proprietary information and classified data. We named this campaign “Operation ENDTRADE,” based on its targets.
https://documents.trendmicro.com/assets/pdf/Operation-ENDTRADE-TICK-s-Multi-Stage-Backdoors-for-Attacking-Industries-and-Stealing-Classified-Data.pdf

2019-06: Breach of Mitsubishi Electric
https://www.zdnet.com/article/mitsubishi-electric-discloses-security-breach-china-is-main-suspect/

2021-02: Exchange servers under siege from at least 10 APT groups
https://www.welivesecurity.com/2021/03/10/exchange-servers-under-siege-10-apt-groups/

2021-03: The slow Tick‑ing time bomb: Tick APT group compromise of a DLP software developer in East Asia
https://www.welivesecurity.com/2023/03/14/slow-ticking-time-bomb-tick-apt-group-dlp-software-developer-east-asia/
https://asec.ahnlab.com/en/51340/

## Reported counter operations against threat actor

2021-04: Tokyo police referred a Chinese man, who is a member of the Chinese Communist Party, to prosecutors Tuesday over his alleged involvement in the cyberattacks, they said.
https://www.japantimes.co.jp/news/2021/04/20/national/chinese-military-japan-cyberattacks/



