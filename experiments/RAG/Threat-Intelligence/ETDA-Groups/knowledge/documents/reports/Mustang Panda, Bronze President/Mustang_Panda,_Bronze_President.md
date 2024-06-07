# Threat actor: Mustang Panda, Bronze President

**UUID**: d8fa62d2-de5c-4c13-8cdf-6428d02bc4d6

**First seen**: 2012

**Source last modified**: 2023-11-30

## Threat actor aliases

Mustang Panda (CrowdStrike), Bronze President (SecureWorks), TEMP.Hex (FireEye), HoneyMyte (Kaspersky), Red Lich (PWC), Earth Preta (Trend Micro), Camaro Dragon (Check Point), Stately Taurus (Palo Alto)

## Description

(CrowdStrike) In April 2017, CrowdStrike Falcon Intelligence observed a previously unattributed actor group with a Chinese nexus targeting a U.S.-based think tank. Further analysis revealed a wider campaign with unique tactics, techniques, and procedures (TTPs). This adversary targets non-governmental organizations (NGOs) in general, but uses Mongolian language decoys and themes, suggesting this actor has a specific focus on gathering intelligence on Mongolia. These campaigns involve the use of shared malware like Poison Ivy or PlugX.

Recently, Falcon Intelligence observed new activity from Mustang Panda, using a unique infection chain to target likely Mongolia-based victims. This newly observed activity uses a series of redirections and fileless, malicious implementations of legitimate tools to gain access to the targeted systems. Additionally, Mustang Panda actors reused previously-observed legitimate domains to host files.

Also see {{RedDelta}}.

## Sponsor type and motivation

**Sponsor**: State-sponsored

**Motivation**: Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in

Aviation, Education, Government, NGOs, Think Tanks, Telecommunications

## Observed attacked countries where victims operate in

Australia, Bangladesh, Belgium, Bulgaria, China, Cyprus, Czech, Ethiopia, France, Germany, Greece, Hong Kong, Hungary, India, Indonesia, Japan, Mongolia, Myanmar, Nepal, Pakistan, Philippines, Russia, Singapore, Slovakia, South Africa, South Korea, South Sudan, Sweden, Taiwan, Thailand, UK, USA, Vietnam, UN

## Observed usage of tools

AdFind, China Chopper, Cobalt Strike, DCSync, Hdump, Hodur, HopperTick, Impacket, LadonGo, nbtscan, Mimikatz, MQsTTang, NetSess, Netview, nmap, Orat, Poison Ivy, PlugX, PowerView, PUBLOAD, PVE Find AD Users, RCSession, ShadowPad Winnti, TeamViewer, TinyNote, TONEINS, TONESHELL, WmiExec, WispRider

## Reported hacking operations

2014: Secureworks Counter Threat Unit (CTU) researchers have observed BRONZE PRESIDENT activity since mid-2018 but identified artifacts suggesting that the threat actors may have been conducting network intrusions as far back as 2014.
https://www.secureworks.com/research/bronze-president-targets-ngos

2019-08: In mid-August 2019, the Anomali Threat Research Team discovered suspicious “.lnk” files during routine intelligence collection. While the distribution method of these documents cannot be confirmed at this time, it is likely that spearphishing is being utilized because it aligns with Mustang Panda’s TTPs, and it is a common tactic used amongst APT actors.
https://www.anomali.com/blog/china-based-apt-mustang-panda-targets-minority-groups-public-and-private-sector-organizations#When:17:14:00Z

2020-01: Avira’s Advanced Threat Research team discovered a new version of PlugX from the Mustang Panda APT that is used to spy on some targets in Hong Kong and Vietnam. The way that the APT actor infects the target, and launches the malicious payload is similar to previous versions—but with some differences.
https://insights.oem.avira.com/new-wave-of-plugx-targets-hong-kong/

2020-03: Vietnamese cyber-security firm VinCSS detected a Chinese state-sponsored hacking group (codenamed Mustang Panda) spreading emails with a RAR file attachment purporting to carry a message about the coronavirus outbreak from the Vietnamese Prime Minister.
https://blog.vincss.net/2020/03/re012-phan-tich-ma-doc-loi-dung-dich-COVID-19-de-phat-tan-gia-mao-chi-thi-cua-thu-tuong-Nguyen-Xuan-Phuc.html

2020-03: ATR identified that the Higaisa and Mustang Panda Advanced Persistent Threat (APT) groups have been utilizing Coronavirus-themed lures in their campaigns.
https://www.anomali.com/blog/covid-19-themes-are-being-utilized-by-threat-actors-of-varying-sophistication#When:14:00:00Z

2021-03: Indonesian intelligence agency compromised in suspected Chinese hack
https://therecord.media/indonesian-intelligence-agency-compromised-in-suspected-chinese-hack/

2021 Mid: Cyberespionage Attacks Against Southeast Asian Government Linked to Stately Taurus, Aka Mustang Panda
https://unit42.paloaltonetworks.com/stately-taurus-attacks-se-asian-government/

2021-08: Mustang Panda’s Hodur: Old tricks, new Korplug variant
https://www.welivesecurity.com/2022/03/23/mustang-panda-hodur-old-tricks-new-korplug-variant/

2022-02: Mustang Panda or Temp.Hex, a China-based threat actor, targeted European entities with lures related to the Ukrainian invasion.
https://blog.google/threat-analysis-group/update-threat-landscape-ukraine/

2022-02: Mustang Panda deploys a new wave of malware targeting Europe
https://blog.talosintelligence.com/2022/05/mustang-panda-targets-europe.html

2022-02: Mustang Panda Uses the Russian-Ukrainian War to Attack Europe and Asia Pacific Targets
https://blogs.blackberry.com/en/2022/12/mustang-panda-uses-the-russian-ukrainian-war-to-attack-europe-and-asia-pacific-targets

2022-03: BRONZE PRESIDENT Targets Russian Speakers with Updated PlugX
https://www.secureworks.com/blog/bronze-president-targets-russian-speakers-with-updated-plugx

2022-03: Earth Preta Spear-Phishing Governments Worldwide
https://www.trendmicro.com/en_us/research/22/k/earth-preta-spear-phishing-governments-worldwide.html

2022-06: BRONZE PRESIDENT Targets Government Officials
https://www.secureworks.com/blog/bronze-president-targets-government-officials

2022: Earth Preta’s Cyberespionage Campaign Hits Over 200
https://www.trendmicro.com/en_us/research/23/c/earth-preta-cyberespionage-campaign-hits-over-200.html

2022-10: Pack it Secretly: Earth Preta’s Updated Stealthy Strategies
https://www.trendmicro.com/en_us/research/23/c/earth-preta-updated-stealthy-strategies.html

2022-12: Operation “SmugX”
SmugX: Unveiling a Chinese-Based APT Operation Targeting European Governmental Entities: Check Point Research Exposes a Shifting Trend
https://blog.checkpoint.com/securing-user-and-access/smugx-unveiling-a-chinese-based-apt-operation-targeting-european-governmental-entities-check-point-research-exposes-a-shifting-trend/

2023-01: MQsTTang: Mustang Panda’s latest backdoor treads new ground with Qt and MQTT
https://www.welivesecurity.com/2023/03/02/mqsttang-mustang-panda-latest-backdoor-treads-new-ground-qt-mqtt/

2023-01: Malware Spotlight: Camaro Dragon’s TinyNote Backdoor
https://research.checkpoint.com/2023/malware-spotlight-camaro-dragons-tinynote-backdoor/

2023 Early: Beyond the Horizon: Traveling the World on Camaro Dragon’s USB Flash Drives
https://research.checkpoint.com/2023/beyond-the-horizon-traveling-the-world-on-camaro-dragons-usb-flash-drives/

2023-04: New Mustang Panda’s campaing against Australia
https://lab52.io/blog/new-mustang-pandas-campaing-against-australia/

2023-05: Check Point Research reveals a malicious firmware implant for TP-Link routers, linked to Chinese APT group
https://blog.checkpoint.com/security/check-point-research-reveals-a-malicious-firmware-implant-for-tp-link-routers-linked-to-chinese-apt-group/

2023-08: In August, ESET researchers identified a campaign by Mustang Panda targeting a governmental organization in Slovakia.
https://web-assets.esetstatic.com/wls/en/papers/threat-reports/eset-apt-activity-report-q2-2023-q3-2023.pdf

2023-08: Stately Taurus Targets the Philippines As Tensions Flare in the South Pacific
https://unit42.paloaltonetworks.com/stately-taurus-targets-philippines-government-cyberespionage/

## Reported counter operations against threat actor





