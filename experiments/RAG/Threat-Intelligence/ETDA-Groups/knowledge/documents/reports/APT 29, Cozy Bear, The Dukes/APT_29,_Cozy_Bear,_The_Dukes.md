# Threat actor: APT 29, Cozy Bear, The Dukes

**UUID**: 93ba9804-335e-4782-855d-40af22b93201

**First seen**: 2008

**Source last modified**: 2024-01-16

## Threat actor aliases

APT 29 (Mandiant), Cozy Bear (CrowdStrike), The Dukes (F-Secure), Group 100 (Talos), Yttrium (Microsoft), Iron Hemlock (SecureWorks), Minidionis (Palo Alto), CloudLook (Kaspersky), ATK 7 (Thales), ITG11 (IBM), Grizzly Steppe (US Government), UNC2452 (FireEye), Dark Halo (Volexity), SolarStorm (Palo Alto), StellarParticle (CrowdStrike), SilverFish (Prodaft), Nobelium (Microsoft), Iron Ritual (SecureWorks), Cloaked Ursa (Palo Alto), BlueBravo (Recorded Future), Midnight Blizzard (Microsoft)

## Description

(F-Secure) The Dukes are a well-resourced, highly dedicated and organized cyberespionage group that we believe has been working for the Russian Federation since at least 2008 to collect intelligence in support of foreign and security policy decision-making.

The Dukes primarily target Western governments and related organizations, such as government ministries and agencies, political think tanks, and governmental subcontractors. Their targets have also included the governments of members of the Commonwealth of Independent States; Asian, African, and Middle Eastern governments; organizations associated with Chechen extremism; and Russian speakers engaged in the illicit trade of controlled substances and drugs.

The Dukes are known to employ a vast arsenal of malware toolsets, which we identify as MiniDuke, CosmicDuke, OnionDuke, CozyDuke, CloudDuke, SeaDuke, HammerDuke, PinchDuke, and GeminiDuke. In recent years, the Dukes have engaged in apparently biannual large-scale spear-phishing campaigns against hundreds or even thousands of recipients associated with governmental institutions and affiliated organizations.

These campaigns utilize a smash-and-grab approach involving a fast but noisy break-in followed by the rapid collection and exfiltration of as much data as possible. If the compromised target is discovered to be of value, the Dukes will quickly switch the toolset used and move to using stealthier tactics focused on persistent compromise and long-term intelligence gathering.

In addition to these large-scale campaigns, the Dukes continuously and concurrently engage in smaller, much more targeted campaigns, utilizing different toolsets. These targeted campaigns have been going on for at least 7 years. The targets and timing of these campaigns appear to align with the known foreign and security policy interests of the Russian Federation at those times.

## Sponsor type and motivation

**Sponsor**: State-sponsored

**Motivation**: Information theft and espionage


## Country of origin

Russia

## Observed attacked sectors where victims operate in

Aerospace, Defense, Education, Embassies, Energy, Financial, Government, Healthcare, Law enforcement, Media, NGOs, Pharmaceutical, Telecommunications, Transportation, Think Tanks, Imagery

## Observed attacked countries where victims operate in

Australia, Azerbaijan, Belarus, Belgium, Brazil, Bulgaria, Canada, Chechnya, Chile, China, Cyprus, Czech, Denmark, France, Georgia, Germany, Hungary, India, Ireland, Israel, Italy, Japan, Kazakhstan, Kyrgyzstan, Latvia, Lebanon, Lithuania, Luxembourg, Mexico, Montenegro, Netherlands, New Zealand, Poland, Portugal, Romania, Russia, Singapore, Slovakia, Slovenia, Spain, South Korea, Switzerland, Thailand, Turkey, Uganda, UAE, UK, Ukraine, USA, Uzbekistan, NATO

## Observed usage of tools

7-Zip, AdFind, ATI-Agent, AtNow, BEATDROP, BloodHound, CEELOADER, CloudDuke, Cobalt Strike, CosmicDuke, CozyDuke, EnvyScout, FatDuke, FoggyWeb, GeminiDuke, GoldFinder, GoldMax, GraphicalNeutrino, GraphicalProton, HammerDuke, LiteDuke, MagicWeb, meek, Mimikatz, MiniDuke, OnionDuke, PinchDuke, PolyglotDuke, POSHSPY, PowerDuke, RAINDROP, RegDuke, Rubeus, SeaDuke, Sharp-SMBExec, SharpView, Sibot, SoreFang, SUNBURST, SUNSPOT, SUPERNOVA, TEARDROP, TrailBlazer, WellMail, WellMess, Living off the Land

## Reported hacking operations

2013-02: Since the original announcement, we have observed several new attacks using the same exploit (CVE-2013-0640) which drop other malware. Between these, we’ve observed a couple of incidents which are so unusual in many ways that we-ve decided to analyse them in depth.
https://securelist.com/the-miniduke-mystery-pdf-0-day-government-spy-assembler-0x29a-micro-backdoor/31112/

2013: While the old style Miniduke implants were used to target mostly government victims, the new style CosmicDuke implants have a somehow different typology of victims. The most unusual is the targeting of individuals that appear to be involved in the traffic and reselling of controlled and illegal substances, such as steroids and hormones. These victims in the NITRO project have been observed only in Russia.
https://securelist.com/miniduke-is-back-nemesis-gemina-and-the-botgen-studio/64107/

2013: Operation “Ghost”
We call these newly uncovered Dukes campaigns, collectively, Operation Ghost, and describe how the group  has been busy compromising government targets, including three European Ministries of Foreign Affairs and the Washington DC embassy of a European Union country, all without drawing attention to their activities.
https://www.welivesecurity.com/wp-content/uploads/2019/10/ESET_Operation_Ghost_Dukes.pdf

2014-03: Operation “Office monkeys”
In March 2014, a Washington, D.C.-based private research institute was found to have CozyDuke (Trojan.Cozer) on their network. Cozy Bear then started an email campaign attempting to lure victims into clicking on a flash video of office monkeys that would also include malicious executables. By July the group had compromised government networks and directed CozyDuke-infected systems to install MiniDuke onto a compromised network.
https://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory

2015-08: Attack on the Pentagon in the USA
In August 2015 Cozy Bear was linked to a spear-phishing cyberattack against the Pentagon email system causing the shutdown of the entire Joint Staff unclassified email system and Internet access during the investigation.
https://www.cnbc.com/2015/08/06/russia-hacks-pentagon-computers-nbc-citing-sources.html

2016-06: Breach of Democratic National Committee
In June 2016, Cozy Bear was implicated alongside the hacker group {{Sofacy, APT 28, Fancy Bear, Sednit}} had only been there a few weeks. Cozy Bear’s more sophisticated tradecraft and interest in traditional long-term espionage suggest that the group originates from a separate Russian intelligence agency.
https://www.crowdstrike.com/blog/bears-midst-intrusion-democratic-national-committee/

2016-08: Attacks on US think tanks and NGOs
After the United States presidential election, 2016, Cozy Bear was linked to a series of coordinated and well-planned spear-phishing campaigns against U.S.-based think tanks and non-governmental organizations (NGOs).
https://www.volexity.com/blog/2016/11/09/powerduke-post-election-spear-phishing-campaigns-targeting-think-tanks-and-ngos/

2017-01: Attacks on the Norwegian Government
On February 3, 2017, the Norwegian Police Security Service (PST) reported that attempts had been made to spear-phish the email accounts of nine individuals in the Ministry of Defense, Ministry of Foreign Affairs, and the Labour Party. The acts were attributed to Cozy Bear, whose targets included the Norwegian Radiation Protection Authority, PST section chief Arne Christian Haugstøyl, and an unnamed college.
https://www.usatoday.com/story/news/2017/02/03/norway-russian-hackers-hit-spy-agency-defense-labour-party/97441782/

2017-02: Attack on Dutch ministries
In February 2017, the General Intelligence and Security Service (AIVD) of the Netherlands revealed that Fancy Bear and Cozy Bear had made several attempts to hack into Dutch ministries, including the Ministry of General Affairs, over the previous six months. Rob Bertholee, head of the AIVD, said on EenVandaag that the hackers were Russian and had tried to gain access to secret government documents.
https://www.volkskrant.nl/cultuur-media/russen-faalden-bij-hackpogingen-ambtenaren-op-nederlandse-ministeries~b77ff391/

2017-09: Russian hackers breached Dutch police systems in 2017
https://therecord.media/russian-hackers-breached-dutch-police-systems-in-2017/

2018-11: Phishing campaign in the USA
Target: Multiple industries, including think tank, law enforcement, media, U.S. military, imagery, transportation, pharmaceutical, national government, and defense contracting.
Method: Phishing email appearing to be from the U.S. Department of State with links to zip files containing malicious Windows shortcuts that delivered Cobalt Strike Beacon.
https://www.fireeye.com/blog/threat-research/2018/11/not-so-cozy-an-uncomfortable-examination-of-a-suspected-apt29-phishing-campaign.html

2019-08: SolarWinds Orion Supply-chain Attack
https://www.dropbox.com/s/yu5uwsfyo9q4oj2/Whitepaper%20SolarWinds%20Orion%20Supply-chain%20Attack.pdf?dl=0

2020: Throughout 2020, APT29 has targeted various organisations involved in COVID-19 vaccine development in Canada, the United States and the United Kingdom, highly likely with the intention of stealing information and intellectual property relating to the development and testing of COVID-19 vaccines.
https://www.ncsc.gov.uk/files/Advisory-APT29-targets-COVID-19-vaccine-development.pdf

2020: Suspected Russian Activity Targeting Government and Business Entities Around the Globe
https://www.mandiant.com/resources/russian-targeting-gov-business

2021: Operation “StellarParticle”
Early Bird Catches the Wormhole: Observations from the StellarParticle Campaign
https://www.crowdstrike.com/blog/observations-from-the-stellarparticle-campaign/

2021-02: Russian cyberspies targeted the Slovak government for months
https://therecord.media/russian-cyberspies-targeted-slovak-government-for-months/

2021-02: France warns of Nobelium cyberspies attacking French orgs
https://www.bleepingcomputer.com/news/security/france-warns-of-nobelium-cyberspies-attacking-french-orgs/

2021 Early: Trello From the Other Side: Tracking APT29 Phishing Campaigns
https://www.mandiant.com/resources/blog/tracking-apt29-phishing-campaigns

2021-04: FoggyWeb: Targeted NOBELIUM malware leads to persistent backdoor
https://www.microsoft.com/security/blog/2021/09/27/foggyweb-targeted-nobelium-malware-leads-to-persistent-backdoor/

2021-05: Suspected APT29 Operation Launches Election Fraud Themed Phishing Campaigns
https://www.volexity.com/blog/2021/05/27/suspected-apt29-operation-launches-election-fraud-themed-phishing-campaigns/

2021-06: New Nobelium activity
https://msrc-blog.microsoft.com/2021/06/25/new-nobelium-activity/

2021 Mid: SOLARDEFLECTION C2 Infrastructure Used by NOBELIUM in Company Brand Misuse
https://www.recordedfuture.com/solardeflection-c2-infrastructure-used-by-nobelium-in-company-brand-misuse/

2021-06: Bear Tracks: Infrastructure Patterns Lead to More Than 30 Active APT29 C2 Servers
https://www.riskiq.com/blog/external-threat-management/apt29-bear-tracks/

2021-07: Russia ‘Cozy Bear’ Breached GOP as Ransomware Attack Hit
https://www.bloomberg.com/news/articles/2021-07-06/russian-state-hackers-breached-republican-national-committee

2021-07: New activity from Russian actor Nobelium
https://blogs.microsoft.com/on-the-issues/2021/10/24/new-activity-from-russian-actor-nobelium/

2021-07: Solarwind Attackers at It Again in Back-to-Back Campaigns
https://cybersecurityworks.com/blog/vulnerabilities/solarwind-attackers-at-it-again-in-back-to-back-campaigns.html>

2021-07: In recent months, the Dukes launched several spearphishing campaigns targeting European diplomats, think tanks and international organizations. ESET researchers identified victims in more than 12 different European countries.
https://www.welivesecurity.com/wp-content/uploads/2021/09/eset_threat_report_t22021.pdf

2021-10: In October and November 2021, ESET detected additional spearphishing campaigns, again targeting European diplomatic missions and Ministries of Foreign Affairs.
https://www.welivesecurity.com/wp-content/uploads/2022/02/eset_threat_report_t32021.pdf

2022-02: Nobelium Returns to the Political World Stage
https://www.fortinet.com/blog/threat-research/nobelium-returns-to-the-political-world-stage

2022-05: Russian APT29 Hackers Use Online Storage Services, DropBox and Google Drive
https://unit42.paloaltonetworks.com/cloaked-ursa-online-storage-services-campaigns/

2022-08: You Can’t Audit Me: APT29 Continues Targeting Microsoft 365
https://www.mandiant.com/resources/blog/apt29-continues-targeting-microsoft

2022-08: MagicWeb: NOBELIUM’s post-compromise trick to authenticate as anyone
https://www.microsoft.com/security/blog/2022/08/24/magicweb-nobeliums-post-compromise-trick-to-authenticate-as-anyone/

2023-01: BlueBravo Adapts to Target Diplomatic Entities with GraphicalProton Malware
https://go.recordedfuture.com/hubfs/reports/cta-2023-0727-1.pdf

2023-02: Diplomats Beware: Cloaked Ursa Phishing With a Twist
https://unit42.paloaltonetworks.com/cloaked-ursa-phishing/

2022-10: BlueBravo Uses Ambassador Lure to Deploy GraphicalNeutrino Malware
https://go.recordedfuture.com/hubfs/reports/cta-2023-0127.pdf

2023-03: NOBELIUM Uses Poland's Ambassador’s Visit to the U.S. to Target EU Governments Assisting Ukraine
https://blogs.blackberry.com/en/2023/03/nobelium-targets-eu-governments-assisting-ukraine

2023-05: Midnight Blizzard conducts targeted social engineering over Microsoft Teams
https://www.microsoft.com/en-us/security/blog/2023/08/02/midnight-blizzard-conducts-targeted-social-engineering-over-microsoft-teams/

2023-06: Kremlin-backed hacking group puts fresh emphasis on stealing credentials
https://therecord.media/nobelium-hacking-group-stealing-credentials

2023-08: German Embassy Lure: Likely Part of Campaign Against NATO Aligned Ministries of Foreign Affairs
https://blog.eclecticiq.com/german-embassy-lure-likely-part-of-campaign-against-nato-aligned-ministries-of-foreign-affairs

2023-09: APT29 Attacks Embassies Using CVE-2023-38831
https://www.rnbo.gov.ua/files/2023_YEAR/CYBERCENTER/november/APT29%20attacks%20Embassies%20using%20CVE-2023-38831%20-%20report%20en.pdf

2023-09: Russian Foreign Intelligence Service (SVR) Exploiting JetBrains TeamCity CVE Globally
https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-347a

## Reported counter operations against threat actor

2014-08: Dutch agencies provide crucial intel about Russia’s interference in US-elections
https://www.volkskrant.nl/wetenschap/dutch-agencies-provide-crucial-intel-about-russia-s-interference-in-us-elections~b4f8111b/

2018-07: Mueller indicts 12 Russians for DNC hacking as Trump-Putin summit looms
https://www.politico.com/story/2018/07/13/mueller-indicts-12-russians-for-hacking-into-dnc-718805

2021-04: Executive Order on Blocking Property with Respect to Specified Harmful Foreign Activities of the Government of the Russian Federation
https://www.whitehouse.gov/briefing-room/statements-releases/2021/04/15/fact-sheet-imposing-costs-for-harmful-foreign-activities-by-the-russian-government/
https://www.whitehouse.gov/briefing-room/presidential-actions/2021/04/15/executive-order-on-blocking-property-with-respect-to-specified-harmful-foreign-activities-of-the-government-of-the-russian-federation/
https://www.whitehouse.gov/briefing-room/statements-releases/2021/04/15/a-letter-on-blocking-property-with-respect-to-specified-harmful-foreign-activities-of-the-government-of-the-russian-federation/

2021-06: Justice Department Announces Court-Authorized Seizure of Domain Names Used in Furtherance of Spear-Phishing Campaign Posing as U.S. Agency for International Development
https://www.justice.gov/opa/pr/justice-department-announces-court-authorized-seizure-domain-names-used-furtherance-spear



