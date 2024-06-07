# Threat actor: TA505, Graceful Spider, Gold Evergreen

**UUID**: 0ac7cc26-cb85-42f7-a2c1-41762b2e2541

**First seen**: 2006

**Source last modified**: 2023-04-26

## Threat actor aliases

TA505 (Proofpoint), Graceful Spider (CrowdStrike), Gold Evergreen (SecureWorks), Gold Tahoe (SecureWorks), TEMP.Warlock (FireEye), ATK 103 (Thales), SectorJ04 (ThreatRecon), Hive0065 (IBM), Chimborazo (Microsoft), Spandex Tempest (Microsoft)

## Description

(Proofpoint) Proofpoint researchers track a wide range of threat actors involved in both financially motivated cybercrime and state-sponsored actions. One of the more prolific actors that we track – referred to as TA505 – is responsible for the largest malicious spam campaigns we have ever observed, distributing instances of the Dridex banking Trojan, Locky ransomware, Jaff ransomware, The Trick banking Trojan, and several others in very high volumes.

Because TA505 is such a significant part of the email threat landscape, this blog provides a retrospective on the shifting malware, payloads, and campaigns associated with this actor. We examine their use malware such as Jaff, Bart, and Rockloader that appear to be exclusive to this group as well as more widely distributed malware like Dridex and Pony. Where possible, we detail the affiliate models with which they are involved and outline the current state of TA505 campaigns.

TA505 is arguably one of the most significant financially motivated threat actors because of the extraordinary volumes of messages they send. The variety of malware delivered by the group also demonstrates their deep connections to the underground malware scene. At the time of writing, Locky ransomware remains their malware of choice, even as the group continues to experiment with a variety of additional malware.

Much of the malware from TA505 has been observed to be distributed using {{Avalanche}}, Cutwail (operated by {{Narwhal Spider}}), Necurs (operated by {{Monty Spider}}) and Emotet (operated by {{Mummy Spider, TA542}}).

TA505 also has some infrastructure overlap with {{Buhtrap, Ratopak Spider}} and Group-IB found several relationships with {{Silence, Contract Crew}}.

The Dridex development appears to have been done by a subgroup named {{Indrik Spider}} and, by extension, {{Doppel Spider}}.

See also: {{Dungeon Spider}} and {{FIN11}}.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Financial crime, Financial gain


## Country of origin

Russia

## Observed attacked sectors where victims operate in

Education, Financial, Healthcare, Hospitality, Retail

## Observed attacked countries where victims operate in

Worldwide

## Observed usage of tools

Amadey, AndroMut, Bart, CryptoLocker, CryptoMix, Dridex, Dudear, EmailStealer, FlawedAmmyy, FlawedGrace, FlowerPippi, GameOver Zeus, Gelup, Get2, GlobeImposter, Jaff, Kegotip, Locky, MINEBRIDGE, MirrorBlast, Neutrino, Philadelphia, Pony, ReflectiveGnome, RockLoader, RMS, SDBbot, ServHelper, Shifu, Snatch, TeslaGun, TinyMet, Zeus, Living off the Land

## Reported hacking operations

2017-10: On October 10, TA505 introduced their first geo-targeted campaign dropping either Locky or The Trick banking Trojan. In this campaign, HTML files were attached to emails inquiring about the status of an invoice.
https://www.proofpoint.com/us/threat-insight/post/ta505-shifts-times

2018-06: We first observed an actor embedding SettingContent-ms inside a PDF on June 18. However, on July 16 we observed a particularly large campaign with hundreds of thousands of messages attempting to deliver PDF attachments with an embedded SettingContent-ms file.
https://www.proofpoint.com/us/threat-insight/post/ta505-abusing-settingcontent-ms-within-pdf-files-distribute-flawedammyy-rat

2018-11: Since November 15, 2018, Proofpoint began observing email campaigns from a specific actor targeting large retail chains, restaurant chains and grocery chains, as well as other organizations in the food and beverage industries.
https://www.proofpoint.com/us/threat-insight/post/ta505-targets-us-retail-industry-personalized-attachments

2018-11: ServHelper and FlawedGrace – New malware introduced by TA505
https://www.proofpoint.com/us/threat-insight/post/servhelper-and-flawedgrace-new-malware-introduced-ta505

2018-12: In mid-December 2018 a spear-phishing campaign was detected as targeting large US-based retailers along with organizations in the food and beverage industry. Masquerading as a legitimate communication sent from a Ricoh printer, the initial email lured victims into opening an attached malicious Microsoft Word document.

2018-12: Last month, 360 Threat Intelligence Center captured multiple phishing emails sent by TA505 Group to target financial institutions. These phishing emails contain Excel attachments with Excel 4.0 Macro embedded and download Backdoor at last.
https://ti.360.net/blog/articles/excel-4.0-macro-utilized-by-ta505-to-target-financial-institutions-recently-en/

2019-04: LOLBins and a New Backdoor Malware
https://www.cybereason.com/blog/threat-actor-ta505-targets-financial-enterprises-using-lolbins-and-a-new-backdoor-malware

2019-04: While monitoring their activities, we found that the group is still updating their tactics, techniques, and procedures (TTPs). In April, TA505 targeted Latin American countries Chile and Mexico, and even Italy using either FlawedAmmyy RAT or RMS RAT as payload. By the end of April, we learned that the group started to go after targets in East Asian countries such as China, South Korea, and Taiwan using FlawedAmmyy RAT as its payload.
https://blog.trendmicro.com/trendlabs-security-intelligence/shifting-tactics-breaking-down-ta505-groups-use-of-html-rats-and-other-techniques-in-latest-campaigns/

2019-05: During the last month our Threat Intelligence surveillance team spotted increasing evidence of an operation intensification against the Banking sector.
https://blog.yoroi.company/research/the-stealthy-email-stealer-in-the-ta505-arsenal/

2019-05: In the last few days, during monitoring activities, Yoroi CERT noticed a suspicious attack against an Italian organization. The malicious email contains a highly suspicious sample which triggered the ZLAB team to investigate its capabilities and its possible attribution, discovering a potential expansion of the TA505 operation.
https://blog.yoroi.company/research/ta505-is-expanding-its-operations/

2019-06: In June 2019, TA505 appears to have introduced yet another new downloader malware, AndroMut, which has some similarities in code and behavior to Andromeda, a long-established malware family.
https://www.proofpoint.com/us/threat-insight/post/ta505-begins-summer-campaigns-new-pet-malware-downloader-andromut-uae-south

2019-06: Latest Spam Campaigns from TA505 Now Using New Malware Tools Gelup and FlowerPippi
https://blog.trendmicro.com/trendlabs-security-intelligence/latest-spam-campaigns-from-ta505-now-using-new-malware-tools-gelup-and-flowerpippi/

2019-08: Given the group’s active campaigns since our updates in June and July, we continued following their latest campaigns. Just like in previous operations, they continue to make small changes, such as targeting other countries, entities, or the combination of techniques used for deployment, for each campaign.
https://blog.trendmicro.com/trendlabs-security-intelligence/ta505-at-it-again-variety-is-the-spice-of-servhelper-and-flawedammyy/

2019-09: In September 2019, Proofpoint researchers observed a prolific threat actor, TA505, sending email campaigns that attempt to deliver and install Get2, a new downloader. Get2 was, in turn, observed downloading FlawedGrace, FlawedAmmyy, Snatch, and SDBbot (a new RAT) as secondary payloads.
https://www.proofpoint.com/us/threat-insight/post/ta505-distributes-new-sdbbot-remote-access-trojan-get2-downloader

2019-12: Throughout January 2020, FireEye has continued to observe multiple targeted phishing campaigns designed to download and deploy a backdoor we track as MINEBRIDGE.
https://www.fireeye.com/blog/threat-research/2020/01/stomp-2-dis-brilliance-in-the-visual-basics.html

2019: TA505 hacking crew spent much of 2019 trying to breach South Korea's financial sector
https://www.cyberscoop.com/ta505-south-korea-bank-phishing/

2019: In this newly discovered campaign from TA505, threat actors targeted German companies with trojanized emails disguised as job applicants. While this activity appeared to be geographically based in Germany, these same techniques could easily be applied to any organization.
Once the email attachment was activated, a company's secure credentials and credit card data could be transmitted covertly to the threat actors. In the 2019 iterations of this attack, TA505 used commercial tools to encrypt all the users files, which suggests this recent activity could also lay the groundwork for an infection vector into the company's network to encrypt files.
https://blog.prevailion.com/2020/03/the-curious-case-of-criminal-curriculum.html

2020-01: Microsoft says that an ongoing TA505 phishing campaign is using attachments featuring HTML redirectors for delivering malicious Excel documents, this being the first time the threat actors have been seen adopting this technique.
https://www.bleepingcomputer.com/news/security/microsoft-detects-new-ta505-malware-attacks-after-short-break/

2020-04: TA505 Continues to Infect Networks With SDBbot RAT
https://securityintelligence.com/posts/ta505-continues-to-infect-networks-with-sdbbot-rat/

2020-06: To evade detection, hackers are requiring targets to complete CAPTCHAs
https://arstechnica.com/information-technology/2020/06/to-evade-detection-hackers-are-requiring-targets-to-complete-captchas/

2020-10: Microsoft is warning that cybercriminals have started to incorporate exploit code for the ZeroLogon vulnerability in their attacks.
https://www.bleepingcomputer.com/news/security/ransomware-gang-now-using-critical-windows-flaw-in-attacks/

2021-06: Signed MSI files, Raccoon and Amadey are used for installing ServHelper RAT
https://blog.talosintelligence.com/2021/08/raccoon-and-amadey-install-servhelper.html

2021-09: Explosive New MirrorBlast Campaign Targets Financial Companies
https://blog.morphisec.com/explosive-new-mirrorblast-campaign-targets-financial-companies

2021-09: Whatta TA: TA505 Ramps Up Activity, Delivers New FlawedGrace Variant
https://www.proofpoint.com/us/blog/threat-insight/whatta-ta-ta505-ramps-activity-delivers-new-flawedgrace-variant

2021-10: TA505 exploits SolarWinds Serv-U vulnerability (CVE-2021-35211) for initial access
https://research.nccgroup.com/2021/11/08/ta505-exploits-solarwinds-serv-u-vulnerability-cve-2021-35211-for-initial-access/

## Reported counter operations against threat actor

2010-03: Zeus botnet dealt a blow as ISP Troyak knocked out
https://www.itworld.com/article/2762789/zeus-botnet-dealt-a-blow-as-isp-troyak-knocked-out.html

2010-10: Operation “Trident Breach”
FBI announces arrests in $70 million cyber-theft
http://edition.cnn.com/2010/CRIME/10/01/cyber.theft/

2012-03: John Doe lawsuit against the Zeus operator
http://www.zeuslegalnotice.com/images/Debenham_Decl_Part_1.pdf

2014-06: Operation “Tovar”
Dell SecureWorks Contributes to Efforts Targeting Gameover Zeus and CryptoLocker
https://www.secureworks.com/blog/operation-tovar-dell-secureworks-contributes-to-efforts-targeting-gameover-zeus-and-cryptolocker
https://www.justice.gov/opa/pr/us-leads-multi-national-action-against-gameover-zeus-botnet-and-cryptolocker-ransomware

2016-12: FACT SHEET: Actions in Response to Russian Malicious Cyber Activity and Harassment
https://obamawhitehouse.archives.gov/the-press-office/2016/12/29/fact-sheet-actions-response-russian-malicious-cyber-activity-and

2022-11: Suspected Zeus cybercrime ring leader ‘Tank’ arrested by Swiss police
https://www.bleepingcomputer.com/news/security/suspected-zeus-cybercrime-ring-leader-tank-arrested-by-swiss-police/



