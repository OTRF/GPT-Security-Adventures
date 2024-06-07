# Threat actor: Transparent Tribe, APT 36

**UUID**: be967aec-2b55-45f2-86e8-7f22cc66db85

**First seen**: 2013

**Source last modified**: 2023-10-12

## Threat actor aliases

Transparent Tribe (Proofpoint), APT 36 (Mandiant), ProjectM (Palo Alto), Mythic Leopard (CrowdStrike), TEMP.Lapis (FireEye), Copper Fieldstone (SecureWorks), Earth Karkaddan (Trend Micro), STEPPY-KAVACH (Securonix)

## Description

(Proofpoint) Proofpoint researchers recently uncovered evidence of an advanced persistent threat (APT) against Indian diplomatic and military resources. Our investigation began with malicious emails sent to Indian embassies in Saudi Arabia and Kazakstan but turned up connections to watering hole sites focused on Indian military personnel and designed to drop a remote access Trojan (RAT) with a variety of data exfiltration functions. Our analysis shows that many of the campaigns and attacks appear related by common IOCs, vectors, payloads, and language, but the exact nature and attribution associated with this APT remain under investigation.
At this time, the background and analysis in this paper provide useful forensics and detail our current thinking on the malware that we have dubbed “MSIL/Crimson”.

Transparent Tribe may be related to {{Gorgon Group}} and {{SideCopy}}.

Transparant Tribe has been observed to use the Andromeda botnet (operated by {{Andromeda Spider}}).

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

Pakistan

## Observed attacked sectors where victims operate in

Defense, Education, Embassies, Government

## Observed attacked countries where victims operate in

Afghanistan, Australia, Austria, Azerbaijan, Belgium, Botswana, Bulgaria, Canada, China, Czech, Germany, India, Iran, Japan, Kazakhstan, Kenya, Malaysia, Mongolia, Nepal, Netherlands, Oman, Pakistan, Romania, Saudi Arabia, Spain, Sweden, Thailand, Turkey, UAE, UK, USA

## Observed usage of tools

Amphibeon, Android RAT, beendoor, Bezigate, Bozok, BreachRAT, CapraRAT, Crimson RAT, DarkComet, Limepad, Luminosity RAT, Mobzsar, MumbaiDown, njRAT, ObliqueRAT, Peppy RAT, QuasarRAT, SilentCMD, Stealth Mango, UPDATESEE, USBWorm, Waizsar RAT

## Reported hacking operations

2012: Operation “Transparent Tribe”
On February 11, 2016, we discovered two attacks minutes apart directed towards officials at Indian embassies in both Saudi Arabia and Kazakhstan. Both e-mails (Fig. 1, 2) were sent from the same originating IP address (5.189.145[.]248) belonging to Contabo GmbH, a hosting provider that seems to be currently favored by these threat actors. The e-mails also likely utilized Rackspace’s MailGun service and both of them were carrying the same exact attachment.
https://www.proofpoint.com/sites/default/files/proofpoint-operation-transparent-tribe-threat-insight-en.pdf

2016-03: Indian TV station CNN-IBN has discovered that Pakistani officials were collecting data about Indian troop movements using an Android app called SmeshApp.
https://news.softpedia.com/news/smeshapp-removed-from-play-store-because-pakistan-used-it-to-spy-on-indian-army-501936.shtml

2016-03: Operation “C-Major”
Trend Micro is reporting on a third campaign, which they’ve named Operation C-Major. According to the security firm, this campaign targeted Indian military officials via spear-phishing emails, distributing spyware to its victims via an Adobe Reader vulnerability.
https://news.softpedia.com/news/another-case-of-a-pakistani-apt-spying-on-indian-military-personnel-502093.shtml
https://blog.trendmicro.com/trendlabs-security-intelligence/operation-c-major-actors-also-used-android-blackberry-mobile-spyware-targets/

2017-02: This blog post describes another attack campaign where attackers impersonated identity of Indian think tank IDSA (Institute for Defence Studies and Analyses) and sent out spear-phishing emails to target officials of the Central Bureau of Investigation (CBI) and possibly the officials of Indian Army.
https://cysinfo.com/cyber-attack-targeting-cbi-and-possibly-indian-army-officials/

2019-06: Over the past year, we have seen this group undergo an evolution, stepping up its activities, starting massive infection campaigns, developing new tools and strengthening their focus on Afghanistan.
https://securelist.com/transparent-tribe-part-1/98127/
https://securelist.com/transparent-tribe-part-2/98233/

2020-01: Investigating APT36 or Earth Karkaddan’s Attack Chain and Malware Arsenal
https://www.trendmicro.com/en_us/research/22/a/investigating-apt36-or-earth-karkaddans-attack-chain-and-malware.html

2020-01: Transparent tribe is back with a new campaign after several years of (apparently) inactivity. We can confirm that this campaign is completely new, relying on the registration record of the C2 that dates back to 29 January 2020.
https://blog.yoroi.company/research/transparent-tribe-four-years-later/

2020 Early: TransparentTribe started using a new module named USBWorm at the beginning of 2020, as well as improving its custom .NET tool named CrimsonRAT.
https://securelist.com/apt-trends-report-q1-2020/96826/

2020-03: APT36 spreads fake coronavirus health advisory
https://blog.malwarebytes.com/threat-analysis/2020/03/apt36-jumps-on-the-coronavirus-bandwagon-delivers-crimson-rat/

2020-04: Operation “Honey Trap”
APT36 Targets Defense Organizations in India
https://www.seqrite.com/blog/operation-honey-trap-apt36-targets-defense-organizations-in-india/

2021-02: ObliqueRAT returns with new campaign using hijacked websites
https://blog.talosintelligence.com/2021/02/obliquerat-new-campaign.html

2021-06: Transparent Tribe campaign uses new bespoke malware to target Indian government officials
https://blog.talosintelligence.com/2022/03/transparent-tribe-new-campaign.html

2021-12: Transparent Tribe begins targeting education sector in latest campaign
https://blog.talosintelligence.com/2022/07/transparent-tribe-targets-education.html

2022: APT-36 Uses New TTPs and New Tools to Target Indian Governmental Organizations
https://www.zscaler.com/blogs/security-research/apt-36-uses-new-ttps-and-new-tools-target-indian-governmental-organizations

2022-07: Love scam or espionage? Transparent Tribe lures Indian and Pakistani officials
https://www.welivesecurity.com/2023/03/07/love-scam-espionage-transparent-tribe-lures-indian-pakistani-officials/

2022-07: Pakistan-Aligned Threat Actor Expands Interest in Indian Education Sector
https://www.sentinelone.com/labs/transparent-tribe-apt36-pakistan-aligned-threat-actor-expands-interest-in-indian-education-sector/

2022-11: New STEPPY#KAVACH Attack Campaign Likely Targeting Indian Government: Technical Insights and Detection Using Securonix
https://www.securonix.com/blog/new-steppykavach-attack-campaign/

2023-04: Cyber Espionage in India: Decoding APT-36's New Linux Malware Campaign
https://www.uptycs.com/blog/cyber_espionage_in_india_decoding_apt_36_new_linux_malware

2023-04: CapraTube | Transparent Tribe’s CapraRAT Mimics YouTube to Hijack Android Phones
https://www.sentinelone.com/labs/capratube-transparent-tribes-caprarat-mimics-youtube-to-hijack-android-phones/

## Reported counter operations against threat actor





