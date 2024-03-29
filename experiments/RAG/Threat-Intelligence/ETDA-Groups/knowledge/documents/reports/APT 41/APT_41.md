# Threat actor: APT 41

**UUID**: 2fe6ac14-796b-4d63-b136-2c20b88bdd9e

**First seen**: 2012

**Source last modified**: 2023-10-12

## Threat actor aliases

APT 41 (FireEye), Double Dragon (FireEye), TG-2633 (SecureWorks), Bronze Atlas (SecureWorks), Red Kelpie (PWC), Blackfly (Symantec), Earth Baku (Trend Micro), SparklingGoblin (ESET), Grayfly (Symantec), Redfly (Symantec)

## Description

(FireEye) FireEye Threat Intelligence assesses with high confidence that APT41 is a prolific cyber threat group that carries out Chinese state-sponsored espionage activity in addition to financially motivated activity potentially outside of state control. Activity traces back to 2012 when individual members of APT41 conducted primarily financially motivated operations focused on the video game industry before expanding into likely state-sponsored activity. This is remarkable because explicit financially motivated targeting is unusual among Chinese state-sponsored threat groups, and evidence suggests these two motivations were balanced concurrently from 2014 onward.

• APT41 overlaps at least partically with public reporting on group including {{Barium}} and {{Winnti Group, Blackfly, Wicked Panda}}. In some cases the primary observed similarity in the publicly reported Winnti activity was the use of the same malware – including HIGHNOON – across otherwise separate clusters of activity.
• Previous FireEye Threat Intelligence reporting on the use of HIGHNOON and related activity was grouped together under both {{Ke3chang, Vixen Panda, APT 15, GREF, Playful Dragon}} and Mana, although we now understand this to be the work of several Chinese cyber espionage groups that share tools and digital certificates.
• APT41 reflects our current understanding of what was previously reported as GREF, as well as additional indicators and activity gathered during our extensive review of our intelligence holdings.

APT 41 has 1 subgroup:
1. {{Subgroup: Earth Longzhi}}

Also see {{Earth Lusca}} and {{RedGolf}}.

## Sponsor type and motivation

**Sponsor**: State-sponsored

**Motivation**: Financial crime, Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in

Construction, Defense, Education, Energy, Financial, Government, Healthcare, High-Tech, Hospitality, Manufacturing, Media, Oil and gas, Petrochemical, Pharmaceutical, Retail, Telecommunications, Transportation, Online video game companies

## Observed attacked countries where victims operate in

Australia, Bahrain, Brazil, Canada, Chile, Denmark, Finland, France, Georgia, Hong Kong, India, Indonesia, Italy, Japan, Malaysia, Mexico, Myanmar, Netherlands, Pakistan, Philippines, Poland, Qatar, Saudi Arabia, Singapore, South Korea, South Africa, Sri Lanka, Sweden, Switzerland, Taiwan, Thailand, Turkey, UAE, UK, USA, Vietnam

## Observed usage of tools

9002 RAT, AceHash, ADORE.XSEC, ASPXSpy, Barlaiy, BIOPASS RAT, BlackCoffee, certutil, China Chopper, Cobalt Strike, COLDJAVA, Crackshot, CrossWalk, DBoxAgent, DEADEYE, DEPLOYLOG, Derusbi, DIRTCLEANER, DragonEgg, EasyNight, FunnySwitch, GearShift, Gh0st RAT, HDRoot, HighNoon, HighNote, HKDOOR, HUI Loader, Jumpall, KEYPLUG, LATELUNCH, LIFEBOAT, Lowkey, MessageTap, Meterpreter, Mimikatz, MoonBounce, njRAT, NTDSDump, PACMAN, PipeMon, PlugX, POTROAST, PRIVATELOG, pwdump, RedXOR, ROCKBOOT, SAGEHIRE, SerialVlogger, ShadowHammer, ShadowPad Winnti, SideWalk, Skip-2.0, SPARKLOG, Speculoos, Spyder, STASHLOG, SWEETCANDLE, TERA, TIDYELF, WIDETONE, WINNKIT, Winnti, WINTERLOVE, WyrmSpy, xDll, XDOOR, XMRig, ZXShell, Living off the Land

## Reported hacking operations

2016 Autumn: Breach of TeamViewer
https://www.bleepingcomputer.com/news/security/teamviewer-confirms-undisclosed-breach-from-2016/

2017-07: ShadowPad is one of the largest known supply-chain attacks. Had it not been detected and patched so quickly, it could potentially have targeted hundreds of organizations worldwide.
https://www.kaspersky.com/about/press-releases/2017_shadowpad-how-attackers-hide-backdoor-in-software-used-by-hundreds-of-large-companies-around-the-world

2018-06: Operation “ShadowHammer”
A supply-chain attack dubbed “Operation ShadowHammer” has been uncovered, targeting users of the ASUS Live Update Utility with a backdoor injection. The China-backed BARIUM APT is suspected to be at the helm of the project.
According to Kaspersky Lab, the campaign ran from June to at least November 2018 and may have impacted more than a million users worldwide – though the adversaries appear to have been after specific victims in Asia.
https://threatpost.com/asus-pc-backdoors-shadowhammer/143129/

2019: Operation “CuckooBees”
Cybereason Uncovers Massive Chinese Intellectual Property Theft Operation
https://www.cybereason.com/blog/operation-cuckoobees-cybereason-uncovers-massive-chinese-intellectual-property-theft-operation
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/spyder-loader-cuckoobees-hong-kong

2019-03: Although the malware uses different configurations in each case, the three affected software products included the same backdoor code and were launched using the same mechanism. While two of the compromised products no longer include the backdoor, one of the affected developers is still distributing the trojanized version: ironically, the game is named Infestation, and is produced by Thai developer Electronics Extreme.
https://www.welivesecurity.com/2019/03/11/gaming-industry-scope-attackers-asia/

2019-04: In April 2019, FireEye’s Managed Defense team identified suspicious activity on a publicly-accessible web server at a U.S.-based research university. This activity, indicated that the attackers were exploiting CVE-2019-3396, a vulnerability in Atlassian Confluence Server that allowed for path traversal and remote code execution.
https://www.fireeye.com/blog/threat-research/2019/08/game-over-detecting-and-stopping-an-apt41-operation.html

2019-08: APT41’s newest espionage tool, MESSAGETAP, was discovered during a 2019 investigation at a telecommunications network provider within a cluster of Linux servers. Specifically, these Linux servers operated as Short Message Service Center (SMSC) servers.
https://www.fireeye.com/blog/threat-research/2019/10/messagetap-who-is-reading-your-text-messages.html

2019-10: Winnti Group’s skip‑2.0: A Microsoft SQL Server backdoor
https://www.welivesecurity.com/2019/10/21/winnti-group-skip2-0-microsoft-sql-server-backdoor/

2019-11: In November 2019, we discovered a new campaign run by the Winnti Group against two Hong Kong universities. We found a new variant of the ShadowPad backdoor, the group’s flagship backdoor, deployed using a new launcher and embedding numerous modules. The Winnti malware was also found at these universities a few weeks prior to ShadowPad.
https://www.welivesecurity.com/2020/01/31/winnti-group-targeting-universities-hong-kong/

2020-01: Between January 20 and March 11, FireEye observed APT41 attempt to exploit vulnerabilities in Citrix NetScaler/ADC, Cisco routers, and Zoho ManageEngine Desktop Central at over 75 FireEye customers.
https://www.fireeye.com/blog/threat-research/2020/03/apt41-initiates-global-intrusion-campaign-using-multiple-exploits.html
https://unit42.paloaltonetworks.com/apt41-using-new-speculoos-backdoor-to-target-organizations-globally/

2020-02: In February 2020, we discovered a new, modular backdoor, which we named PipeMon. Persisting as a Print Processor, it was used by the Winnti Group against several video gaming companies that are based in South Korea and Taiwan and develop MMO (Massively Multiplayer Online) games. Video games developed by these companies are available on popular gaming platforms and have thousands of simultaneous players.
https://www.welivesecurity.com/2020/05/21/no-game-over-winnti-group/

2020: New Linux Backdoor RedXOR Likely Operated by Chinese Nation-State Actor
https://www.intezer.com/blog/malware-analysis/new-linux-backdoor-redxor-likely-operated-by-chinese-nation-state-actor/

2020-03: During threat research in March 2020, PT Expert Security Center specialists found a previously unknown backdoor and named it xDll, based on the original name found in the code. As a result of a configuration flaw of the malware's command and control (C2) server, some server directories were externally accessible.
https://www.ptsecurity.com/ww-en/analytics/pt-esc-threat-intelligence/shadowpad-new-activity-from-the-winnti-group/

2020-04: Hackers linked to Chinese government stole millions in Covid benefits, Secret Service says
https://www.nbcnews.com/tech/security/chinese-hackers-covid-fraud-millions-rcna59636

2020-07: APT41 Resurfaces as Earth Baku With New Cyberespionage Campaign
https://www.trendmicro.com/en_us/research/21/h/apt41-resurfaces-as-earth-baku-with-new-cyberespionage-campaign.html

2020-10: Lookout Attributes Advanced Android Surveillanceware to Chinese Espionage Group APT41
https://www.lookout.com/threat-intelligence/article/wyrmspy-dragonegg-surveillanceware-apt41

2021: APT41 World Tour 2021 on a tight schedule
https://blog.group-ib.com/apt41-world-tour-2021

2021-02: You never walk alone: The SideWalk backdoor gets a Linux variant
https://www.welivesecurity.com/2022/09/14/you-never-walk-alone-sidewalk-backdoor-linux-variant/

2021 Early: New Wave of Espionage Activity Targets Asian Governments
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/espionage-asia-governments

2021-03: Operation “ColunmTK”
Big airline heist
https://blog.group-ib.com/colunmtk_apt41

2021 Spring: MoonBounce: the dark side of UEFI firmware
https://securelist.com/moonbounce-the-dark-side-of-uefi-firmware/105468/

2021-05: Does This Look Infected? A Summary of APT41 Targeting U.S. State Governments
https://www.mandiant.com/resources/apt41-us-state-governments

2021-07: BIOPASS RAT: New Malware Sniffs Victims via Live Streaming
https://www.trendmicro.com/en_us/research/21/g/biopass-rat-new-malware-sniffs-victims-via-live-streaming.html

2021-08: The SideWalk may be as dangerous as the CROSSWALK
https://www.welivesecurity.com/2021/08/24/sidewalk-may-be-as-dangerous-as-crosswalk/

2022-08: Winnti APT group docks in Sri Lanka for new campaign
https://www.malwarebytes.com/blog/threat-intelligence/2022/winnti-apt-group-docks-in-sri-lanka-for-new-campaign-final.pdf

2022 Late: Blackfly: Espionage Group Targets Materials Technology
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/blackfly-espionage-materials

2023-02: Redfly: Espionage Actors Continue to Target Critical Infrastructure
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/critical-infrastructure-attacks

## Reported counter operations against threat actor

2020-08: Seven International Cyber Defendants, Including “Apt41” Actors, Charged In Connection With Computer Intrusion Campaigns Against More Than 100 Victims Globally
https://www.justice.gov/opa/pr/seven-international-cyber-defendants-including-apt41-actors-charged-connection-computer



