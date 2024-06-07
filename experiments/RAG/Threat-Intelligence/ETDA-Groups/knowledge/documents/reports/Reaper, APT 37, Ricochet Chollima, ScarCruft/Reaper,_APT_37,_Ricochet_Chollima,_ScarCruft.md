# Threat actor: Reaper, APT 37, Ricochet Chollima, ScarCruft

**UUID**: be6e7cee-7c2c-4298-941d-01b2106284e6

**First seen**: 2012

**Source last modified**: 2024-01-16

## Threat actor aliases

Reaper (FireEye), TEMP.Reaper (FireEye), APT 37 (Mandiant), Ricochet Chollima (CrowdStrike), ScarCruft (Kaspersky), Cerium (Microsoft), Group 123 (Talos), Red Eyes (AhnLab), Geumseong121 (ESRC), Venus 121 (ESRC), Hermit (Tencent), InkySquid (Volexity), ATK 4 (Thales), ITG10 (IBM), Ruby Sleet (Microsoft)

## Description

Some research organizations link this group to {{Lazarus Group, Hidden Cobra, Labyrinth Chollima}}.

(FireEye) Read our report, APT37 (Reaper): The Overlooked North Korean Actor, to learn more about our assessment that this threat actor is working on behalf of the North Korean government, as well as various other details about their operations:
• Targeting: Primarily South Korea – though also Japan, Vietnam and the Middle East – in various industry verticals, including chemicals, electronics, manufacturing, aerospace, automotive, and healthcare.
• Initial Infection Tactics: Social engineering tactics tailored specifically to desired targets, strategic web compromises typical of targeted cyberespionage operations, and the use of torrent file-sharing sites to distribute malware more indiscriminately.
• Exploited Vulnerabilities: Frequent exploitation of vulnerabilities in Hangul Word Processor (HWP), as well as Adobe Flash. The group has demonstrated access to zero-day vulnerabilities (CVE-2018-0802), and the ability to incorporate them into operations.
• Command and Control Infrastructure: Compromised servers, messaging platforms, and cloud service providers to avoid detection. The group has shown increasing sophistication by improving their operational security over time.
• Malware: A diverse suite of malware for initial intrusion and exfiltration. Along with custom malware used for espionage purposes, APT37 also has access to destructive malware.

## Sponsor type and motivation

**Sponsor**: State-sponsored

**Motivation**: Information theft and espionage


## Country of origin

North Korea

## Observed attacked sectors where victims operate in

Aerospace, Automotive, Chemical, Financial, Government, Healthcare, High-Tech, Manufacturing, Technology, Transportation

## Observed attacked countries where victims operate in

China, Czech, Hong Kong, India, Japan, Kuwait, Nepal, Poland, Romania, Russia, South Korea, UK, USA, Vietnam

## Observed usage of tools

BLUELIGHT, CARROTBALL, CARROTBAT, Cobalt Strike, CORALDECK, DOGCALL, Dolphin, Erebus, Final1stSpy, Freenki Loader, GELCAPSULE, GOLDBACKDOOR, GreezeBackdoor, HAPPYWORK, KARAE, KevDroid, Konni, MILKDROP, N1stAgent, NavRAT, Nokki, Oceansalt, PoohMilk Loader, POORAIM, RokRAT, RICECURRY, RUHAPPY, ScarCruft, SHUTTERSPEED, SLOWDRIFT, SOUNDWAVE, Syscon, WINERACK, ZUMKONG, several 0-day Flash and MS Office exploits

## Reported hacking operations

2012: Spying on South Korean users.

2016: Operation “Erebus”
https://www.trendmicro.com/vinfo/us/security/news/cyber-attacks/erebus-linux-ransomware-impact-to-servers-and-countermeasures

2016-03: Operation “Daybreak”
Target: High profile victims.
Method: Previously unknown (0-day) Adobe Flash Player exploit. It is also possible that the group deployed another zero day exploit, CVE-2016-0147, which was patched in April.
https://securelist.com/operation-daybreak/75100/
Note: not the same operation as {{DarkHotel}}’s Operation “Daybreak”.

2016-08: Operation “Golden Time”
Target: South Korean users.
Method: spear-phishing emails combined with malicious HWP documents created using Hancom Hangul Office Suite

2016-11: Operation “Evil New Year”
Target: South Korean users.
Method: spear-phishing emails combined with malicious HWP documents created using Hancom Hangul Office Suite.

2017-03: Operation “Are You Happy?”
Target: South Korean users.
Method: Not only to gain access to the remote infected systems but to also wipe the first sectors of the device.

2017-05: Operation “FreeMilk”
Target: Several non-Korean financial institutions.
Method: A malicious Microsoft Office document, a deviation from their normal use of Hancom documents.
https://unit42.paloaltonetworks.com/unit42-freemilk-highly-targeted-spear-phishing-campaign/

2017-11: Operation “North Korean Human Right”
Target: South Korean users.
Method: Spear-phishing emails combined with malicious HWP documents created using Hancom Hangul Office Suite.

2017-12: Operation “Fractured Block”
https://unit42.paloaltonetworks.com/unit42-the-fractured-block-campaign-carrotbat-malware-used-to-deliver-malware-targeting-southeast-asia/

2018-01: Operation “Evil New Year 2018”
Target: South Korean users.
Method: Spear-phishing emails combined with malicious HWP documents created using Hancom Hangul Office Suite.

2018-03: Operation “Battle Cruiser”
https://blog.alyac.co.kr/1625

2018-04: Operation “Star Cruiser”
http://blog.alyac.co.kr/1653

2018-05: Operation “Onezero”
https://brica.de/alerts/alert/public/1215993/analysis-of-apt-attack-on-operation-onezero-conducted-as-a-document-on-panmunjom-declaration/

2018-08: Operation “Rocket Man”
https://brica.de/alerts/alert/public/1226363/the-latest-apt-campaign-of-venus-121-group-operation-rocket-man/

2018-11: Operation “Korean Sword”
https://brica.de/alerts/alert/public/1252896/venus-121-apt-organization-operation-high-expert/

2019-01: Operation “Holiday Wiper”
https://brica.de/alerts/alert/public/1252896/venus-121-apt-organization-operation-high-expert/

2019-03: Operation “Golden Bird”
https://brica.de/alerts/alert/public/1252896/venus-121-apt-organization-operation-high-expert/

2019-03: Operation “High Expert”
https://brica.de/alerts/alert/public/1252896/venus-121-apt-organization-operation-high-expert/

2019-04: Operation “Black Banner”
https://brica.de/alerts/alert/public/1257351/venus-121-rocketman-campaign-operation-black-banner-apt-attack/

2019-05: We recently discovered some interesting telemetry on this actor, and decided to dig deeper into ScarCruft’s recent activity. This shows that the actor is still very active and constantly trying to elaborate its attack tools. Based on our telemetry, we can reassemble ScarCruft’s binary infection procedure. It used a multi-stage binary infection to update each module effectively and evade detection.
https://securelist.com/scarcruft-continues-to-evolve-introduces-bluetooth-harvester/90729/

2019-07: Operation “Fractured Statue”
https://unit42.paloaltonetworks.com/the-fractured-statue-campaign-u-s-government-targeted-in-spear-phishing-attacks/

2019-09: Operation “Dragon messenger”
https://blog.alyac.co.kr/attachment/cfile1.uf@99A46A405DC8E3031C9E2A.pdf

2020-01: North Korean APT used VBA self decode technique to inject RokRat
https://blog.malwarebytes.com/threat-analysis/2021/01/retrohunting-apt37-north-korean-apt-used-vba-self-decode-technique-to-inject-rokrat/

2020-03: Operation “Spy Cloud”
https://blog.alyac.co.kr/attachment/cfile8.uf@9977CF405E81A09B1C4CE2.pdf

2020-12: North Korean software supply chain attack targets stock investors
https://www.bleepingcomputer.com/news/security/north-korean-software-supply-chain-attack-targets-stock-investors/
https://blog.alyac.co.kr/3489

2021-03: ScarCruft surveilling North Korean defectors and human rights activists
https://securelist.com/scarcruft-surveilling-north-korean-defectors-and-human-rights-activists/105074/

2021-04: North Korean APT InkySquid Infects Victims Using Browser Exploits
https://www.volexity.com/blog/2021/08/17/north-korean-apt-inkysquid-infects-victims-using-browser-exploits/
https://www.volexity.com/blog/2021/08/24/north-korean-bluelight-special-inkysquid-deploys-rokrat/

2021-04: Who’s swimming in South Korean waters? Meet ScarCruft’s Dolphin
https://www.welivesecurity.com/2022/11/30/whos-swimming-south-korean-waters-meet-scarcrufts-dolphin/

2021-07: New variant of Konni malware used in campaign targetting Russia
https://blog.malwarebytes.com/threat-intelligence/2021/08/new-variant-of-konni-malware-used-in-campaign-targetting-russia/

2021-12: North Korean hackers target Russian diplomats using New Year greetings
https://therecord.media/north-korean-hackers-attack-russian-diplomats-using-new-year-greetings/
https://blog.lumen.com/new-konni-campaign-targeting-russian-ministry-of-foreign-affairs/

2022-01: KONNI evolves into stealthier RAT
https://blog.malwarebytes.com/threat-intelligence/2022/01/konni-evolves-into-stealthier-rat/

2022-03: The ink-stained trail of GOLDBACKDOOR
https://stairwell.com/news/threat-research-the-ink-stained-trail-of-goldbackdoor/

2022-05: Comrades in Arms? | North Korea Compromises Sanctioned Russian Missile Engineering Company
https://www.sentinelone.com/labs/comrades-in-arms-north-korea-compromises-sanctioned-russian-missile-engineering-company/

2022-07: Operation “STIFF#BIZON”
The Securonix Threat Research (STR) team has been observing and investigating a new attack campaign exploiting high-value targets, including Czech Republic, Poland, and other countries.
https://www.securonix.com/blog/stiffbizon-detection-new-attack-campaign-observed/

2022-09: Meeting the “Ministrer”
https://www.fortinet.com/blog/threat-research/konni-rat-phishing-email-deploying-malware

2022-10: Internet Explorer 0-day exploited by North Korean actor APT37
https://blog.google/threat-analysis-group/internet-explorer-0-day-exploited-by-north-korean-actor-apt37/

2023-01: RedEyes hackers use new malware to steal data from Windows, phones
https://www.bleepingcomputer.com/news/security/redeyes-hackers-use-new-malware-to-steal-data-from-windows-phones/

2023-02: HWP Malware Using the Steganography Technique: RedEyes (ScarCruft)
https://asec.ahnlab.com/en/48063/

2023-03: CHM Malware Disguised as Security Email from a Korean Financial Company: Redeyes (Scarcruft)
https://asec.ahnlab.com/en/49089/

2023-04: RokRAT Malware Distributed Through LNK Files (*.lnk): RedEyes (ScarCruft)
https://asec.ahnlab.com/en/51751/

2023-04: ITG10 Likely Targeting South Korean Entities of Interest to the Democratic People’s Republic of Korea (DPRK)
https://securityintelligence.com/posts/itg10-targeting-south-korean-entities/

2023-05: Tracking Traces of Malware Disguised as Hancom Office Document File and Being Distributed (RedEyes)
https://asec.ahnlab.com/en/53377/

2023-05: RedEyes Group Wiretapping Individuals (APT37)
https://asec.ahnlab.com/en/54349/

2023-07: Operation “STARK#MULE”
Detecting Ongoing STARK#MULE Attack Campaign Targeting Victims Using US Military Document Lures
https://www.securonix.com/blog/detecting-ongoing-starkmule-attack-campaign-targeting-victims-using-us-military-document-lures/

2023-09: Distribution of Backdoor via Malicious LNK: RedEyes (ScarCruft)
https://asec.ahnlab.com/en/56756/

2023-09: RedEyes (ScarCruft)’s CHM Malware Using the Topic of Fukushima Wastewater Release
https://asec.ahnlab.com/en/56857/

2023-12: Distribution of Phishing Email Under the Guise of Personal Data Leak (Konni)
https://asec.ahnlab.com/en/59763/

## Reported counter operations against threat actor

2019-12: On December 27, a U.S. district court unsealed documents detailing work Microsoft has performed to disrupt cyberattacks from a threat group we call Thallium, which is believed to operate from North Korea. Our court case against Thallium, filed in the U.S. District Court for the Eastern District of Virginia, resulted in a court order enabling Microsoft to take control of 50 domains that the group uses to conduct its operations.
https://blogs.microsoft.com/on-the-issues/2019/12/30/microsoft-court-action-against-nation-state-cybercrime/

2023-03: The Unintentional Leak: A glimpse into the attack vectors of APT37
https://www.zscaler.com/blogs/security-research/unintentional-leak-glimpse-attack-vectors-apt37



