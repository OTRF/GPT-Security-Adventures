# Threat actor: MuddyWater, Seedworm, TEMP.Zagros, Static Kitten

**UUID**: 0d5af1f9-fa2e-4ce9-a4ce-0c6fade938e9

**First seen**: 2017

**Source last modified**: 2024-01-16

## Threat actor aliases

MuddyWater (Palo Alto), Seedworm (Symantec), TEMP.Zagros (FireEye), Static Kitten (CrowdStrike), Mercury (Microsoft), TA450 (Proofpoint), Cobalt Ulster (SecureWorks), ATK 51 (Thales), T-APT-14 (Tencent), ITG17 (IBM), Mango Sandstorm (Microsoft)

## Description

(Reaqta) MuddyWater is an APT group that has been active throughout 2017, targeting victims in Middle East with in-memory vectors leveraging on Powershell, in a family of attacks now identified as “Living off the land”, as they don’t require the creation of new binaries on the victim’s machine, thus maintaining a low detection profile and a low forensic footprint.

The operators behind MuddyWater are likely espionage motivated, we derive this information from the analysis of data and backdoors behaviors. We also find that despite the strong preponderance of victims from Pakistan, the most active targets appear to be in: Saudi Arabia, UAE and Iraq. Amongst the victims we identify a variety of entities with a stronger focus at Governments, Telcos and Oil companies.

By tracking the operations we finally figure out that the originating country is likely to be Iran, while it remains harder to ascertain whether MuddyWater is state sponsored or a criminal organization incline to espionage.

## Sponsor type and motivation

**Sponsor**: State-sponsored, IRGC (Islamic Republic Guard Corps)

**Motivation**: Information theft and espionage


## Country of origin

Iran

## Observed attacked sectors where victims operate in

Defense, Education, Energy, Financial, Food and Agriculture, Gaming, Government, Healthcare, High-Tech, IT, Media, NGOs, Oil and gas, Telecommunications, Transportation

## Observed attacked countries where victims operate in

Afghanistan, Armenia, Austria, Azerbaijan, Bahrain, Belarus, Egypt, Georgia, India, Iran, Iraq, Israel, Jordan, Kuwait, Laos, Lebanon, Mali, Netherlands, Oman, Qatar, Pakistan, Russia, Saudi Arabia, Sudan, Tajikistan, Tanzania, Thailand, Tunisia, Turkey, UAE, Ukraine, USA

## Observed usage of tools

ChromeCookiesView, chrome-passwords, CLOUDSTATS, Cobalt Strike, CrackMapExec, DELPHSTATS, EmpireProject, FruityC2, Koadic, LaZagne, Meterpreter, Mimikatz, MuddyC2Go, Mudwater, MZCookiesView, PhonyC2, Powermud, PowerSploit, POWERSTATS, PowGoop, PRB-Backdoor, QUADAGENT, Secure Socket Funneling, SHARPSTATS, Shootback, Smbmap, Living off the Land

## Reported hacking operations

2017-02: The MuddyWater attacks are primarily against Middle Eastern nations. However, we have also observed attacks against surrounding nations and beyond, including targets in India and the USA.
https://unit42.paloaltonetworks.com/unit42-muddying-the-water-targeted-attacks-in-the-middle-east/

2018-01: Updated Tactics, Techniques and Procedures in Spear Phishing Campaign
We attribute this activity to TEMP.Zagros (reported by Palo Alto Networks and Trend Micro as MuddyWater), an Iran-nexus actor that has been active since at least May 2017. This actor has engaged in prolific spear phishing of government and defense entities in Central and Southwest Asia.
https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html

2018-03: Campaign Possibly Connected to “MuddyWater” Surfaces in the Middle East and Central Asia
We discovered a new campaign targeting organizations in Turkey, Pakistan and Tajikistan that has some similarities with an earlier campaign named MuddyWater, which hit various industries in several countries, primarily in the Middle East and Central Asia.
https://blog.trendmicro.com/trendlabs-security-intelligence/campaign-possibly-connected-muddywater-surfaces-middle-east-central-asia/

2018-05: Another Potential MuddyWater Campaign uses Powershell-based PRB-Backdoor
In May 2018, we found a new sample (Detected as W2KM_DLOADR.UHAOEEN) that may be related to this campaign. Like the previous campaigns, these samples again involve a Microsoft Word document embedded with a malicious macro that is capable of executing PowerShell (PS) scripts leading to a backdoor payload. One notable difference in the analyzed samples is that they do not directly download the Visual Basic Script(VBS) and PowerShell component files, and instead encode all the scripts on the document itself. The scripts will then be decoded and dropped to execute the payload without needing to download the component files.
https://blog.trendmicro.com/trendlabs-security-intelligence/another-potential-muddywater-campaign-uses-powershell-based-prb-backdoor/

2018-05: We recently noticed a large amount of spear phishing documents that appear to be targeting government bodies, military entities, telcos and educational institutions in Jordan, Turkey, Azerbaijan and Pakistan, in addition to the continuous targeting of Iraq and Saudi Arabia, other victims were also detected in Mali, Austria, Russia, Iran and Bahrain.. These new documents have appeared throughout 2018 and escalated from May onwards. The attacks are still ongoing.
https://securelist.com/muddywater/88059/

2018-09: Group remains highly active with more than 130 victims in 30 organizations hit since September 2018.
Seedworm’s motivations are much like many cyber espionage groups that we observe—they seek to acquire actionable information about the targeted organizations and individuals. They accomplish this with a preference for speed and agility over operational security, which ultimately led to our identification of their key operational infrastructure.
https://www.symantec.com/blogs/threat-intelligence/seedworm-espionage-group

2018-11: Operations in Lebanon and Oman
MuddyWater has recently been targeting victims likely from Lebanon and Oman, while leveraging compromised domains, one of which is owned by an Israeli web developer. The investigation aimed to uncover additional details regarding the compromise vector. Further, we wished to determine the infection vector, which is currently unknown. With that in mind, past experience implies that this might be a two-stage spear-phishing campaign.
https://www.clearskysec.com/wp-content/uploads/2018/11/MuddyWater-Operations-in-Lebanon-and-Oman.pdf

2019-04: Targeting Kurdish Political Groups and Organizations in Turkey
However, unlike the previous vector, we did not identify this time any compromised servers used to host the malware’s code. Instead, the lure document already contains the malicious code. We also detected five additional files that operate in a similar file to the aforementioned document; but unlike that file, these do not have any content.
https://www.clearskysec.com/muddywater-targets-kurdish-groups-turkish-orgs/

2019-04: The Iranian APT, MuddyWater, has been active since at least 2017. Most recently though, a new campaign, targeting Belarus, Turkey and Ukraine, has emerged that caught the attention of Check Point researchers.
https://research.checkpoint.com/the-muddy-waters-of-apt-attacks/

2019-04: Operation “BlackWater”
Newly associated samples from April 2019 indicate attackers have added three distinct steps to their operations, allowing them to bypass certain security controls and suggesting that MuddyWater’s tactics, techniques and procedures (TTPs) have evolved to evade detection.
https://blog.talosintelligence.com/2019/05/recent-muddywater-associated-blackwater.html

2019-06: Clearsky has detected new and advanced attack vector used by MuddyWater to target governmental entities and the telecommunication sector. Notably, the TTP includes decoy documents exploiting CVE-2017-0199 as the first stage of the attack. This is followed by the second stage of the attack – communication with the hacked C2 servers and downloading a file infected with the macros.
https://www.clearskysec.com/muddywater2/

2019-06: We came across new campaignsthat seem to bear the markings of MuddyWater –a threat actor group with a history of targeting organizations in Middle Eastern and Asian countries. The group used new tools and payloads in campaigns over the first half of 2019, pointing to the continued work the group has put in since our last report on MuddyWaterin November 2018.
https://documents.trendmicro.com/assets/white_papers/wp_new_muddywater_findings_uncovered.pdf

2019-12: Group continues to be highly active in 2020, while tentative links to recently discovered PowGoop tool suggest possible retooling.
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/seedworm-apt-iran-middle-east

2019: State-sponsored hackers abuse Slack API to steal airline data
https://www.bleepingcomputer.com/news/security/state-sponsored-hackers-abuse-slack-api-to-steal-airline-data/

2020-09: Operation “Quicksand”
During September 2020, weidentified a new campaign targeting many prominent Israeli organizations.
https://www.clearskysec.com/wp-content/uploads/2020/10/Operation-Quicksand.pdf

2020-10: MSTIC has observed activity by the nation-state actor MERCURY using the CVE-2020-1472 exploit (ZeroLogon) in active campaigns over the last 2 weeks.
https://www.zdnet.com/article/microsoft-says-iranian-hackers-are-exploiting-the-zerologon-vulnerability/

2020-12: GitHub-hosted malware calculates Cobalt Strike payload from Imgur pic
https://www.bleepingcomputer.com/news/security/github-hosted-malware-calculates-cobalt-strike-payload-from-imgur-pic/

2021-02: Probable Iranian Cyber Actors, Static Kitten, Conducting Cyberespionage Campaign Targeting UAE and Kuwait Government Agencies
https://www.anomali.com/blog/probable-iranian-cyber-actors-static-kitten-conducting-cyberespionage-campaign-targeting-uae-and-kuwait-government-agencies

2021-02: Operation “Earth Vetala”
Earth Vetala used spearphishing emails with embedded links to a legitimate file-sharing service to distribute their malicious package. The links were embedded within lure documents as well as emails.
https://www.trendmicro.com/en_us/research/21/c/earth-vetala---muddywater-continues-to-target-organizations-in-t.html

2021-06: Espionage Campaign Targets Telecoms Organizations across Middle East and Asia
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/espionage-campaign-telecoms-asia-middle-east

2021-11: Iranian APT MuddyWater targets Turkish users via malicious PDFs, executables
https://blog.talosintelligence.com/2022/01/iranian-apt-muddywater-targets-turkey.html

2021 Late: New MuddyWater Threat: Old Kitten; New Tricks
https://www.deepinstinct.com/blog/new-muddywater-threat-old-kitten-new-tricks

2022 Late: APT groups muddying the waters for MSPs
https://www.welivesecurity.com/2023/05/02/apt-groups-muddying-waters-msps/

2023-04: MERCURY and DEV-1084: Destructive attack on hybrid environment
https://www.microsoft.com/en-us/security/blog/2023/04/07/mercury-and-dev-1084-destructive-attack-on-hybrid-environment/

2023-04: PhonyC2: Revealing a New Malicious Command & Control Framework by MuddyWater
https://www.deepinstinct.com/blog/phonyc2-revealing-a-new-malicious-command-control-framework-by-muddywater

2023-05: Microsoft: Iranian hacking groups join Papercut attack spree
https://www.bleepingcomputer.com/news/security/microsoft-iranian-hacking-groups-join-papercut-attack-spree/

2023-07: MuddyC2Go – Latest C2 Framework Used by Iranian APT MuddyWater Spotted in Israel
https://www.deepinstinct.com/blog/muddyc2go-latest-c2-framework-used-by-iranian-apt-muddywater-spotted-in-israel

2023-10: MuddyWater eN-Able spear-phishing with new TTPs
https://www.deepinstinct.com/blog/muddywater-en-able-spear-phishing-with-new-ttps

2023-11: Seedworm: Iranian Hackers Target Telecoms Orgs in North and East Africa
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/iran-apt-seedworm-africa-telecoms

## Reported counter operations against threat actor

2019-05: New leaks of Iranian cyber-espionage operations hit Telegram and the Dark Web
https://www.zdnet.com/article/new-leaks-of-iranian-cyber-espionage-operations-hit-telegram-and-the-dark-web/
Update: this leak may have been the work of the {{CIA}}.



