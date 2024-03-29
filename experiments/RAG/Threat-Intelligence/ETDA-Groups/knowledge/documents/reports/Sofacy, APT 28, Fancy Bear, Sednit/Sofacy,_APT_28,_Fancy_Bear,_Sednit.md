# Threat actor: Sofacy, APT 28, Fancy Bear, Sednit

**UUID**: e6037735-ed1b-4ae3-a45b-45d66e2c80f1

**First seen**: 2004

**Source last modified**: 2024-01-16

## Threat actor aliases

Sofacy (Kaspersky), APT 28 (Mandiant), Fancy Bear (CrowdStrike), Sednit (ESET), Group 74 (Talos), TG-4127 (SecureWorks), Pawn Storm (Trend Micro), Tsar Team (iSight), Strontium (Microsoft), Swallowtail (Symantec), SIG40 (NSA), Snakemackerel (iDefense), Iron Twilight (SecureWorks), ATK 5 (Thales), T-APT-12 (Tencent), ITG05 (IBM), TAG-0700 (Recorded Future), UAC-0028 (CERT-UA), FROZENLAKE (Google), Grey-Cloud (?), Grizzly Steppe (US Government), Forest Blizzard (Microsoft), BlueDelta (Recorded Future), TA422 (Proofpoint), Fighting Ursa (Palo Alto)

## Description

APT 28 is a threat group that has been attributed to Russia’s Main Intelligence Directorate of the Russian General Staff by a July 2018 U.S. Department of Justice indictment. This group reportedly compromised the Hillary Clinton campaign, the Democratic National Committee, and the Democratic Congressional Campaign Committee in 2016 in an attempt to interfere with the U.S. presidential election. APT 28 has been active since at least January 2007.

(FireEye) APT28 likely seeks to collect intelligence about Georgia’s security and political dynamics by targeting officials working for the Ministry of Internal Affairs and the Ministry of Defense.

APT28 has demonstrated interest in Eastern European governments and security organizations. These victims would provide the Russian government with an ability to predict policymaker intentions and gauge its ability to influence public opinion.

APT28 appeared to target individuals affiliated with European security organizations and global multilateral institutions. The Russian government has long cited European security organizations like NATO and the OSCE as existential threats, particularly during periods of increased tension in Europe.

Sofacy may be related to {{Hades}}, but it could be a false flag as well.

## Sponsor type and motivation

**Sponsor**: State-sponsored, two GRU units known as Unit 26165 and Unit 74455

**Motivation**: Information theft and espionage


## Country of origin

Russia

## Observed attacked sectors where victims operate in

Automotive, Aviation, Chemical, Construction, Defense, Education, Embassies, Energy, Engineering, Financial, Government, Healthcare, Industrial, IT, Media, NGOs, Oil and gas, Think Tanks, Intelligence organizations

## Observed attacked countries where victims operate in

Afghanistan, Armenia, Australia, Azerbaijan, Belarus, Belgium, Brazil, Bulgaria, Canada, Chile, China, Croatia, Cyprus, France, Georgia, Germany, Hungary, India, Iran, Iraq, Italy, Japan, Jordan, Kazakhstan, Latvia, Malaysia, Mexico, Mongolia, Montenegro, Netherlands, Norway, Pakistan, Poland, Romania, Saudi Arabia, Slovakia, South Africa, South Korea, Spain, Sweden, Switzerland, Tajikistan, Thailand, Turkey, Uganda, UAE, UK, Ukraine, USA, Uzbekistan, NATO, APEC and OSCE

## Observed usage of tools

Cannon, certutil, Computrace, CORESHELL, DealersChoice, Downdelph, Drovorub, Foozer, Graphite, Headlace, HIDEDRV, Impacket, JHUHUGIT, Koadic, Komplex, LoJax, MASEPIE, Mimikatz, Nimcy, OCEANMAP, OLDBAIT, PocoDown, ProcDump, PythocyDbg, Responder, Sedkit, Sedreco, SkinnyBoy, SMBExec, STEELHOOK, USBStealer, VPNFilter, Winexe, WinIDS, X-Agent, X-Tunnel, Zebrocy, Living off the Land

## Reported hacking operations

2011/2012: Back in 2011-2012, the group used a relatively tiny implant (known as “Sofacy” or SOURFACE) as its first stage malware. The implant shared certain similarities with the old Miniduke implants. This led us to believe the two groups were connected, at least to begin with, although it appears they parted ways in 2014, with the original Miniduke group switching to the CosmicDuke implant.

2013: At some point during 2013, the Sofacy group expanded its arsenal and added more backdoors and tools, including CORESHELL, SPLM (aka Xagent, aka CHOPSTICK), JHUHUGIT (which is built with code from the Carberp sources), AZZY (aka ADVSTORESHELL, NETUI, EVILTOSS, and spans across four to five generations) and a few others. We’ve seen quite a few versions of these implants and they were relatively widespread for a time.

2014-10: Operation “Pawn Storm”
Target: Several foreign affairs ministries from around the globe.
Method:  Spear-phishing e-mails with links leading to an Adobe Flash exploit.
https://blog.trendmicro.com/trendlabs-security-intelligence/new-adobe-flash-zero-day-used-in-pawn-storm-campaign/

2014-12: Six-month-long cyberattack on the German parliament
http://www.lse.co.uk/AllNews.asp?code=kwdwehme&headline=Russian_Hackers_Suspected_In_Cyberattack_On_German_Parliament

2015-02: U.S. military wives’ death threats
Five military wives received death threats from a hacker group calling itself “{{Cyber Caliphate Army (CCA), United Cyber Caliphate (UCC)}}”, claiming to be an Islamic State affiliate, on February 10, 2015. This was later discovered to have been a false flag attack by Fancy Bear, when the victims’ email addresses were found to have been in the Fancy Bear phishing target list.
https://www.apnews.com/4d174e45ef5843a0ba82e804f080988f

2015-04: Compromise of TV5Monde in France
“A group calling itself the {{Cyber Caliphate Army (CCA), United Cyber Caliphate (UCC)}}, linked to so-called Islamic State, first claimed responsibility. But an investigation now suggests the attack was in fact carried out by a group of Russian hackers.”
https://www.bbc.com/news/technology-37590375

2015-04: Operation “Russian Doll”
Method: Adobe Flash 0-day
https://www.fireeye.com/blog/threat-research/2015/04/probable_apt28_useo.html

2015-04: Compromise of the German Parliament (Bundestag) network
https://netzpolitik.org/2015/digital-attack-on-german-parliament-investigative-report-on-the-hack-of-the-left-party-infrastructure-in-bundestag/

2015-07: Pawn Storm Update: Trend Micro Discovers New Java Zero-Day Exploit
https://blog.trendmicro.com/trendlabs-security-intelligence/pawn-storm-update-trend-micro-discovers-new-java-zero-day-exploit/

2015-08: EFF spoof, White House and NATO attack
Method: zero-day exploit of Java, spoofing the Electronic Frontier Foundation and launching attacks on the White House and NATO. The hackers used a spear-phishing attack, directing emails to the false url electronicfrontierfoundation.org.
https://www.eff.org/deeplinks/2015/08/new-spear-phishing-campaign-pretends-be-eff

2015-09: Bootstrapped Firefox Add-on
https://labsblog.f-secure.com/2015/09/08/sofacy-recycles-carberp-and-metasploit-code/

2015-10: Attack on Bellingcat
Eliot Higgins and other journalists associated with Bellingcat, a group researching the shoot down of Malaysia Airlines Flight 17 over Ukraine, were targeted by numerous spear-phishing emails. The messages were fake Gmail security notices with Bit.ly and TinyCC shortened URLs.
https://blog.trendmicro.com/trendlabs-security-intelligence/pawn-storm-targets-mh17-investigation-team/

2015-10: Attack on Dutch Safety Board
The group targeted the Dutch Safety Board, the body conducting the official investigation into the crash, before and after the release of the board’s final report. They set up fake SFTP and VPN servers to mimic the board’s own servers, likely for the purpose of spear-phishing usernames and passwords.
https://www.msn.com/en-au/news/world/russia-tried-to-hack-mh17-inquiry-system/ar-BBmmuuT

2015-10: New Adobe Flash Zero-Day Used in Pawn Storm Campaign Targeting Foreign Affairs Ministries
https://blog.trendmicro.com/trendlabs-security-intelligence/new-adobe-flash-zero-day-used-in-pawn-storm-campaign/

2016-01: Pawn Storm Campaign Adds Turkey To Its List of Targets
https://blog.trendmicro.com/trendlabs-security-intelligence/pawn-storm-adds-turkey-list-targets/

2016-05: Pawn Storm Targets German Christian Democratic Union
https://blog.trendmicro.com/trendlabs-security-intelligence/pawn-storm-targets-german-christian-democratic-union/

2016-05: Russian cyber-espionage group hits Sanoma
https://yle.fi/uutiset/osasto/news/russian_cyber-espionage_group_hits_sanoma/8919118

2016-06: Breach of Democratic National Committee
Fancy Bear carried out spear-phishing attacks on email addresses associated with the Democratic National Committee in the first quarter of 2016. On March 10, phishing emails that were mainly directed at old email addresses of 2008 Democratic campaign staffers began to arrive. One of these accounts may have yielded up to date contact lists. The next day, phishing attacks expanded to the non-public email addresses of high level Democratic Party officials. Hillaryclinton.com addresses were attacked, but required two factor authentication for access. The attack redirected towards Gmail accounts on March 19th. Podesta’s Gmail account was breached the same day, with 50,000 emails stolen.
Another sophisticated hacking group attributed to the Russian Federation, nicknamed {{APT 29, Cozy Bear, The Dukes}} appears to be a different agency, one more interested in traditional long-term espionage.
https://www.crowdstrike.com/blog/bears-midst-intrusion-democratic-national-committee/
https://www.secureworks.com/research/threat-group-4127-targets-google-accounts

2016-06: “Exercise Noble Partner 2016” spear-phishing e-mail
Method: Spear-phishing e-mail
Target: USA government
https://unit42.paloaltonetworks.com/unit42-new-sofacy-attacks-against-us-government-agency/

2016-08: Spear-phishing attack members of the Bundestag and multiple political parties such as Linken-faction leader Sahra Wagenknecht, Junge Union and the CDU of Saarland. Authorities feared that sensitive information could be gathered by hackers to later manipulate the public ahead of elections such as Germany’s next federal election which was due in September 2017.
http://www.dw.com/en/hackers-lurking-parliamentarians-told/a-19564630

2016-08: World Anti-Doping Agency
Method: Phishing emails sent to users of its database claiming to be official WADA communications requesting their login details.
http://www.ibtimes.co.uk/russian-hackers-fancy-bear-likely-breached-olympic-drug-testing-agency-dnc-experts-say-1577508

2016-09: Operation “Komplex”
https://unit42.paloaltonetworks.com/unit42-sofacys-komplex-os-x-trojan/

2016-10: Operation “DealersChoice”
https://unit42.paloaltonetworks.com/unit42-dealerschoice-sofacys-flash-player-exploit-platform/
https://unit42.paloaltonetworks.com/unit42-let-ride-sofacy-groups-dealerschoice-attacks-continue/
The global reach that coincided with this focus on NATO and the Ukraine couldn’t be overstated. Our KSN data showed spear-phishing targets geo-located across the globe into 2017.
AM, AZ, FR, DE, IQ, IT, KG, MA, CH, UA, US, VN
DealersChoice emails, like the one above, that we were able to recover from third party sources provided additional targeting insight, and confirmed some of the targeting within our KSN data:
TR, PL, BA, AZ, KR, LV, GE, LV, AU, SE, BE

2017 Early: GAMEFISH backdoor
Target: Europe.
Method: They took advantage of the Syrian military conflict for thematic content and file naming “Trump’s_Attack_on_Syria_English.docx”. Again, this deployment was likely a part of their focus on NATO targets.

2017 Early: LoJax: First UEFI rootkit found in the wild
https://www.welivesecurity.com/2018/09/27/lojax-first-uefi-rootkit-found-wild-courtesy-sednit-group/

2017-02: Attack on Dutch ministries
In February 2017, the General Intelligence and Security Service (AIVD) of the Netherlands revealed that Fancy Bear and Cozy Bear had made several attempts to hack into Dutch ministries, including the Ministry of General Affairs, over the previous six months. Rob Bertholee, head of the AIVD, said on EenVandaag that the hackers were Russian and had tried to gain access to secret government documents.
https://www.volkskrant.nl/cultuur-media/russen-faalden-bij-hackpogingen-ambtenaren-op-nederlandse-ministeries~b77ff391/

2017-02: Russian Hackers ‘Fancy Bear’ Targeted French Presidential Candidate Macron
https://www.vice.com/en_us/article/ez35p7/russian-hackers-fancy-bear-targeted-french-presidential-candidate-macron

2017-02: IAAF Hack
The officials of International Association of Athletics Federations (IAAF) stated in April 2017 that its servers had been hacked by the “Fancy Bear” group. The attack was detected by cybersecurity firm Context Information Security which identified that an unauthorized remote access to IAAF’s servers had taken place on February 21. IAAF stated that the hackers had accessed the Therapeutic Use Exemption applications, needed to use medications prohibited by WADA.
https://www.voanews.com/a/iaaf-hack-fancy-bears/3793874.html

2017-04: German elections
They targeted the German Konrad Adenauer Foundation and Friedrich Ebert Foundation, groups that are associated with Angela Merkel’s Christian Democratic Union and opposition Social Democratic Party, respectively. Fancy Bear set up fake email servers in late 2016 to send phishing emails with links to malware.
https://www.handelsblatt.com/today/politics/election-risks-russia-linked-hackers-target-german-political-foundations/23569188.html?ticket=ST-2696734-GRHgtQukDIEXeSOwksXO-ap1

2017 Early: SPLM backdoor
Target: included defense related commercial and military organizations, and telecommunications.
Targeting included TR, KZ, AM, KG, JO, UK, UZ
Method: SPLM/CHOPSTICK/Xagent

2017-06: Heavy Zebrocy deployments
Targeting profiles, spear-phish filenames, and lures carry thematic content related to visa applications and scanned images, border control administration, and various administrative notes. Targeting appears to be widely spread across the Middle East, Europe, and Asia:
- Business accounting practices and standards
- Science and engineering centers
- Industrial and hydro chemical engineering and standards/certification
- Ministry of foreign affairs
- Embassies and consulates
- National security and intelligence agencies
- Press services
- Translation services
- NGO – family and social service
- Ministry of energy and industry
Method: the Zebrocy chain follows a pattern: spear-phish attachment -> compiled Autoit script (downloader) -> Zebrocy payload. In some deployments, we observed Sofacy actively developing and deploying a new package to a much smaller, specific subset of targets within the broader set.

2017-07: APT28 Targets Hospitality Sector, Presents Threat to Travelers
https://www.fireeye.com/blog/threat-research/2017/08/apt28-targets-hospitality-sector.html

2017-10: In this case it capitalized on the recent terrorist attack in New York City. The document itself is blank. Once opened, the document contacts a control server to drop the first stage of the malware, Seduploader, onto a victim’s system.
https://securingtomorrow.mcafee.com/mcafee-labs/apt28-threat-group-adopts-dde-technique-nyc-attack-theme-in-latest-campaign/#sf151634298

2017-10: Russische hackers vallen vredesbeweging Pax aan
https://www.human.nl/schimmenspel/russische-hackers-vallen-Nederlandse-vredesbeweging-aan.html

2018-01: Breach of the International Olympic Committee
On January 10, 2018, the “Fancy Bears Hack Team” online persona leaked what appeared to be stolen International Olympic Committee (IOC) and U.S. Olympic Committee emails, dated from late 2016 to early 2017, were leaked in apparent retaliation for the IOC’s banning of Russian athletes from the 2018 Winter Olympics as a sanction for Russia’s systematic doping program. The attack resembles the earlier World Anti-Doping Agency (WADA) leaks. It is not known whether the emails are fully authentic, because of Fancy Bear’s history of salting stolen emails with disinformation. The mode of attack was also not known, but was probably phishing.
https://www.wired.com/story/russian-fancy-bears-hackers-release-apparent-ioc-emails/

2018-02: Attacks on Multiple Government Entities
Target: Ministries of Foreign Affairs of the USA and Romania.
Method: Spear-phishing using the subject line of Upcoming Defense events February 2018 and a sender address claiming to be from Jane’s 360 defense events.
https://unit42.paloaltonetworks.com/unit42-sofacy-attacks-multiple-government-entities/

2018-03: On March 12 and March 14, we observed the Sofacy group carrying out an attack on a European government agency involving an updated variant of DealersChoice. The updated DealersChoice documents used a similar process to obtain a malicious Flash object from a C2 server, but the inner mechanics of the Flash object contained significant differences in comparison to the original samples we analyzed.
https://unit42.paloaltonetworks.com/unit42-sofacy-uses-dealerschoice-target-european-government-agency/

2018-05: Breach of the Swedish Sports Confederation
The Swedish Sports Confederation reported Fancy Bear was responsible for an attack on its computers, targeting records of athletes’ doping tests.
https://www.reuters.com/article/us-sweden-doping/swedish-sports-body-says-anti-doping-unit-hit-by-hacking-attack-idUSKCN1IG2GN

2018-05: VPNFilter IoT botnet
ThaiCERT's whitepaper:
https://www.dropbox.com/s/9lkeenhveb3xbkq/Whitepaper VPNFilter IoT botnet seized by the FBI.pdf?dl=0

2018-06: This third campaign is consistent with two previously reported attack campaigns in terms of targeting: the targets were government organizations dealing with foreign affairs. In this case however the targets were in different geopolitical regions.
https://unit42.paloaltonetworks.com/unit42-sofacy-groups-parallel-attacks/

2018-08: Attacks on United States Conservative Groups
The software company Microsoft reported in August 2018 that the group had attempted to steal data from political organizations such as the International Republican Institute and the Hudson Institute think tanks. The attacks were thwarted when Microsoft security staff won control of six net domains. In its announcement Microsoft advised that “we currently have no evidence these domains were used in any successful attacks before the DCU transferred control of them, nor do we have evidence to indicate the identity of the ultimate targets of any planned attack involving these domains”.
https://www.bbc.co.uk/news/technology-45257081

2018-10: Operation “Dear Joohn”
Target: The weaponized documents targeted several government entities around the globe, including North America, Europe, and a former USSR state.
Method: new ‘Cannon’ Trojan
https://unit42.paloaltonetworks.com/dear-joohn-sofacy-groups-global-campaign/
https://unit42.paloaltonetworks.com/unit42-sofacy-continues-global-attacks-wheels-new-cannon-trojan/

2018: BREXIT-themed lure document
Brexit-themed bait documents to deliver the Zekapab (also known as Zebrocy) first-stage malware, sent on the same day the UK Prime Minister Theresa May announced the initial BREXIT draft agreement with the European Union (EU). “As the United Kingdom (UK) Prime Minister Theresa May announced the initial BREXIT draft agreement with the European Union (EU).
https://www.accenture.com/t20181129T203820Z__w__/us-en/_acnmedia/PDF-90/Accenture-snakemackerel-delivers-zekapab-malware.pdf

2019-02: 2019 Think Tank Attacks
In February 2019, Microsoft announced that it had detected spear-phishing attacks from APT28, aimed at employees of the German Marshall Fund, Aspen Institute Germany, and the German Council on Foreign Relations. Hackers from the group purportedly sent phishing e-mails to 104 email addresses across Europe in an attempt to gain access to employer credentials and infect sites with malware.
https://www.washingtonpost.com/technology/2019/02/20/microsoft-says-it-has-found-another-russian-operation-targeting-prominent-think-tanks/?utm_term=.870ff11468ae

2019-02: Threat Campaign Likely Targeting NATO Members, Defense and Military Outlets
iDefense assesses with moderate confidence that the actors may be targeting attendees and sponsors of the upcoming Underwater Defense & Security 2019 event occurring March 5-7, 2019, in Southampton, United Kingdom. This event draws attendees from government, military and private sector entities across the globe.
https://www.accenture.com/t20190213T141124Z__w__/us-en/_acnmedia/PDF-94/Accenture-SNAKEMACKEREL-Threat-Campaign-Likely-Targeting-NATO-Members-Defense-and-Military-Outlets.pdf

2019-04: In April, security researchers in the Microsoft Threat Intelligence Center discovered infrastructure of a known adversary communicating to several external devices. Further research uncovered attempts by the actor to compromise popular IoT devices (a VOIP phone, an office printer, and a video decoder) across multiple customer locations.
https://msrc-blog.microsoft.com/2019/08/05/corporate-iot-a-path-to-intrusion/

2019-05: Since May 2019, Pawn Storm has been abusing compromised email addresses to send credential phishing spam. The majority of the compromised systems were from defense companies in the Middle East. Other targets included organizations in the transportation, utilities, and government sectors.
https://www.trendmicro.com/vinfo/us/security/news/cyber-attacks/probing-pawn-storm-cyberespionage-campaign-through-scanning-credential-phishing-and-more

2019-08: On August 20th, 2019, a new campaign was launched by the group targeting their usual victims – embassies of, and Ministries of Foreign Affairs in, Eastern European and Central Asian countries.
https://www.welivesecurity.com/2019/09/24/no-summer-vacations-zebrocy/

2019-08: APT28, one of Russia's military hacking units, was most likely responsible for hacking the email accounts of the Norwegian Parliament, the Norwegian police secret service (PST) said today.
https://www.zdnet.com/article/norway-says-russian-hacking-group-apt28-is-behind-august-2020-parliament-hack/

2019-09: At least 16 national and international sporting and anti-doping organizations across three continents were targeted in these attacks which began September 16th, just before news reports about new potential action being taken by the World Anti-Doping Agency. Some of these attacks were successful, but the majority were not.
https://blogs.microsoft.com/on-the-issues/2019/10/28/cyberattacks-sporting-anti-doping/

2019-11: Beginning in early November of 2019, the Main Intelligence Directorate of the General Staff of the Russian Army (GRU) launched a phishing campaign targeting Burisma Holdings, a holding company of energy exploration and production companies based in Kiev, Ukraine.
https://cdn.area1security.com/reports/Area-1-Security-PhishingBarismaHoldings.pdf

2020-04: Microsoft has tied STRONTIUM to a newly uncovered pattern of Office365 credential harvesting activity aimed at US and UK organizations directly involved in political elections.
https://www.microsoft.com/security/blog/2020/09/10/strontium-detecting-new-patters-credential-harvesting/

2020-05: Pawn Storm scanned IP addresses worldwide, including IP addresses from the defense industry in Europe, on TCP port 445 and 1433, likely in an attempt to find vulnerable SMB and SQL servers or brute force credentials.
https://www.trendmicro.com/en_us/research/20/l/pawn-storm-lack-of-sophistication-as-a-strategy.html

2020-08: New cyberattacks targeting U.S. elections
https://blogs.microsoft.com/on-the-issues/2020/09/10/cyberattacks-us-elections-trump-biden/

2020-08: APT28 Delivers Zebrocy Malware Campaign using NATO Theme as Lure
https://quointelligence.eu/2020/09/apt28-zebrocy-malware-campaign-nato-theme/

2020-11: A Zebra in Gopher's Clothing: Russian APT Uses COVID-19 Lures to Deliver Zebrocy
https://www.intezer.com/blog/research/russian-apt-uses-covid-19-lures-to-deliver-zebrocy/

2021: France says Russian state hackers breached numerous critical networks
https://www.bleepingcomputer.com/news/security/france-says-russian-state-hackers-breached-numerous-critical-networks/

2021-06: A not so Fancy game. Exploring the new “SkinnyBoy” Bear’s backdoor
https://cluster25.io/wp-content/uploads/2021/05/2021-05_FancyBear.pdf

2021-06: Hackers Exploited MSHTML Flaw to Spy on Government and Defense Targets
https://thehackernews.com/2022/01/hackers-exploited-mshtml-flaw-to-spy-on.html

2021-09: Google notifies 14,000 Gmail users of targeted APT28 attacks
https://therecord.media/google-notifies-14000-gmail-users-of-targeted-apt28-attacks/

2022-02: FancyBear/APT28, a threat actor attributed to Russia GRU, has conducted several large credential phishing campaigns targeting ukr.net users, UkrNet is a Ukrainian media company.
https://blog.google/threat-analysis-group/update-threat-landscape-ukraine/

2022-02: BlueDelta Exploits Ukrainian Government Roundcube Mail Servers to Support Espionage Activities
https://go.recordedfuture.com/hubfs/reports/cta-2023-0620.pdf

2022-04: APT28 or Fancy Bear, a threat actor attributed to Russia GRU, was observed targeting users in Ukraine with a new variant of malware.
https://blog.google/threat-analysis-group/update-on-cyber-activity-in-eastern-europe/

2022-06: The Ukrainian Computer Emergency Response Team (CERT) is warning that Russian hacking groups are exploiting the Follina code execution vulnerability in new phishing campaigns to install the CredoMap malware and Cobalt Strike beacons.
https://www.bleepingcomputer.com/news/security/russian-govt-hackers-hit-ukraine-with-cobalt-strike-credomap-malware/

2022-09: In the footsteps of the Fancy Bear: PowerPoint mouse-over event abused to deliver Graphite implants
https://blog.cluster25.duskrise.com/2022/09/23/in-the-footsteps-of-the-fancy-bear-powerpoint-graphite/

2023-03: TA422’s Dedicated Exploitation Loop—the Same Week After Week
https://www.proofpoint.com/us/blog/threat-insight/ta422s-dedicated-exploitation-loop-same-week-after-week

2023-04: Hackers use fake ‘Windows Update’ guides to target Ukrainian govt
https://www.bleepingcomputer.com/news/security/hackers-use-fake-windows-update-guides-to-target-ukrainian-govt/

2023-08: ITG05 operations leverage Israel-Hamas conflict lures to deliver Headlace malware
https://securityintelligence.com/x-force/itg05-ops-leverage-israel-hamas-conflict-lures-to-deliver-headlace-malware/

2023-09: Ukraine says an energy facility disrupted a Fancy Bear intrusion
https://therecord.media/ukraine-energy-facility-cyberattack-fancy-bear-email

2023-09: Fighting Ursa Aka APT28: Illuminating a Covert Campaign
https://unit42.paloaltonetworks.com/russian-apt-fighting-ursa-exploits-cve-2023-233397/

2023-09: Operation “Steal-It”
https://www.zscaler.com/blogs/security-research/steal-it-campaign

2023-12: Russian hackers exploiting Outlook bug to hijack Exchange accounts
https://www.bleepingcomputer.com/news/microsoft/russian-hackers-exploiting-outlook-bug-to-hijack-exchange-accounts/

2023-12: Russian military hackers target Ukraine with new MASEPIE malware
https://www.bleepingcomputer.com/news/security/russian-military-hackers-target-ukraine-with-new-masepie-malware/

## Reported counter operations against threat actor

2018-05: Justice Department Announces Actions to Disrupt Advanced Persistent Threat 28 Botnet of Infected Routers and Network Storage Devices
https://www.justice.gov/opa/pr/justice-department-announces-actions-disrupt-advanced-persistent-threat-28-botnet-infected

2018-07: Mueller indicts 12 Russians for DNC hacking as Trump-Putin summit looms
https://www.politico.com/story/2018/07/13/mueller-indicts-12-russians-for-hacking-into-dnc-718805

2018-08: Microsoft’s Digital Crimes Unit (DCU) successfully executed a court order to disrupt and transfer control of six internet domains
https://blogs.microsoft.com/on-the-issues/2018/08/20/we-are-taking-new-steps-against-broadening-threats-to-democracy/

2018-10: US charges Russian military officers over international hacking and disinformation campaigns
https://www.zdnet.com/article/us-charges-russian-military-officers-over-international-hacking-and-disinformation-campaigns/

2020-05: German authorities charge Russian hacker for 2015 Bundestag hack
https://www.zdnet.com/article/german-authorities-charge-russian-hacker-for-2015-bundestag-hack/

2022-04: Disrupting cyberattacks targeting Ukraine
https://blogs.microsoft.com/on-the-issues/2022/04/07/cyberattacks-ukraine-strontium-russia/

2023-04: Hacked: Russian GRU officer wanted by the FBI, leader of the hacker group APT 28
https://informnapalm.org/en/hacked-russian-gru-officer/



