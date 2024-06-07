# Reference for threat actor for "APT 29, Cozy Bear, The Dukes"

**Title**: Cozy Bear - Wikipedia

**Source**: https://en.wikipedia.org/wiki/Cozy_Bear

## Content




Cozy Bear - Wikipedia



























Jump to content







Main menu





Main menu
move to sidebar
hide



		Navigation
	


Main pageContentsCurrent eventsRandom articleAbout WikipediaContact usDonate





		Contribute
	


HelpLearn to editCommunity portalRecent changesUpload file





Languages

Language links are at the top of the page.



















Search











Search





























Create account

Log in








Personal tools





 Create account Log in





		Pages for logged out editors learn more



ContributionsTalk




























Contents
move to sidebar
hide




(Top)





1Methods and technical capability







2Attacks



Toggle Attacks subsection





2.1Office Monkeys (2014)







2.2Pentagon (August 2015)







2.3Democratic National Committee (2016)







2.4US think tanks and NGOs (2016)







2.5Norwegian government (2017)







2.6Dutch ministries (2017)







2.7Operation Ghost







2.8COVID-19 vaccine data (2020)







2.9SUNBURST malware supply chain attack (2020)







2.10Republican National Committee (2021)







2.11Microsoft (2022-23)









3See also







4References







5External links

















Toggle the table of contents







Cozy Bear



10 languages




ČeštinaDeutschEspañolFrançais한국어ItalianoעבריתРусскийSuomiУкраїнська

Edit links











ArticleTalk





English

















ReadEditView history







Tools





Tools
move to sidebar
hide



		Actions
	


ReadEditView history





		General
	


What links hereRelated changesUpload fileSpecial pagesPermanent linkPage informationCite this pageGet shortened URLDownload QR codeWikidata item





		Print/export
	


Download as PDFPrintable version

























From Wikipedia, the free encyclopedia


Russian hacker group
"Office Monkeys" redirects here. For the 2003 British hidden camera television programme, see Office Monkey.
This article's lead section may be too short to adequately summarize the key points. Please consider expanding the lead to provide an accessible overview of all important aspects of the article. (December 2020)
Cozy BearFormationc. 2008[1]TypeAdvanced persistent threatPurposeCyberespionage, cyberwarfareRegion RussiaMethodsSpearphishing, malwareOfficial language RussianLeaderWriaseParent organizationeither FSB or SVR[2][3][4]AffiliationsFancy BearFormerly calledAPT29, CozyCar, CozyDuke, Dark Halo, The Dukes, Grizzly Steppe (when combined with Fancy Bear), NOBELIUM, Office Monkeys, StellarParticle, UNC2452, YTTRIUM
Cozy Bear, classified by the United States federal government as advanced persistent threat APT29, is a Russian hacker group believed to be associated with one or more intelligence agencies of Russia. The Dutch General Intelligence and Security Service (AIVD) deduced from security camera footage that it is led by the Russian Foreign Intelligence Service (SVR),[5] a view shared by the United States.[4] Cybersecurity firm CrowdStrike also previously suggested that it may be associated with either the Russian Federal Security Service (FSB) or SVR.[2] The group has been given various nicknames by other cybersecurity firms, including CozyCar,[6] CozyDuke[7][8] (by F-Secure), Dark Halo, The Dukes (by Volexity), Midnight Blizzard[9] (by Microsoft), NOBELIUM, Office Monkeys, StellarParticle, UNC2452, and YTTRIUM.
On 20 December 2020, it was reported that Cozy Bear was responsible for a cyber attack on U.S. sovereign national data, believed to be at the direction of the Russian government.[10]


Methods and technical capability[edit]
Diagram outlining Cozy Bear and Fancy Bear's  process of using of malware to penetrate targets
Kaspersky Lab determined that the earliest samples of the MiniDuke malware attributed to the group date from 2008.[1] The original code was written in assembly language.[11] Symantec believes that Cozy Bear had been compromising diplomatic organizations and governments since at least 2010.[12]
The CozyDuke malware utilises a backdoor and a dropper. The malware exfiltrates data to a command and control server. Attackers may tailor the malware to the environment.[1] The backdoor components of Cozy Bear's malware are updated over time with modifications to cryptography, trojan functionality, and anti-detection. The speed at which Cozy Bear develops and deploys its components is reminiscent of the toolset of Fancy Bear, which also uses the tools CHOPSTICK and CORESHELL.[13]
Cozy Bear's CozyDuke malware toolset is structurally and functionally similar to second stage components used in early Miniduke, Cosmicduke, and OnionDuke operations. A second stage module of the CozyDuke malware, Show.dll, appears to have been built onto the same platform as OnionDuke, suggesting that the authors are working together or are the same people.[13] The campaigns and the malware toolsets they use are referred to as the Dukes, including Cosmicduke, Cozyduke, and Miniduke.[12] CozyDuke is connected to the MiniDuke and CosmicDuke campaigns, as well as to the OnionDuke cyberespionage campaign. Each threat group tracks their targets and use toolsets that were likely created and updated by Russian speakers.[1] Following exposure of the MiniDuke in 2013, updates to the malware were written in C/C++ and it was packed with a new obfuscator.[11]
Cozy Bear is suspected of being behind the 'HAMMERTOSS' remote access tool which uses commonly visited websites like Twitter and GitHub to relay command data.[14]
Seaduke is a highly configurable, low-profile Trojan only used for a small set of high-value targets. Typically, Seaduke is installed on systems already infected with the much more widely distributed CozyDuke.[12]

Attacks[edit]
Cozy Bear appears to have different projects, with different user groups. The focus of its project "Nemesis Gemina" is military, government, energy, diplomatic and telecom sectors.[11] Evidence suggests that Cozy Bear's targets have included commercial entities and government organizations in Germany, Uzbekistan, South Korea and the US, including the US State Department and the White House in 2014.[13]

Office Monkeys (2014)[edit]
In March 2014, a Washington, D.C.-based private research institute was found to have CozyDuke (Trojan.Cozer) on their network. Cozy Bear then started an email campaign attempting to lure victims into clicking on a flash video of office monkeys that would also include malicious executables.[12][1] By July the group had compromised government networks and directed CozyDuke-infected systems to install Miniduke onto a compromised network.[12]
In the summer of 2014, digital agents of the Dutch General Intelligence and Security Service infiltrated Cozy Bear. They found that these Russian hackers were targeting the US Democratic Party, State Department and White House. Their evidence influenced the FBI's decision to open an investigation.[5][15]

Pentagon (August 2015)[edit]
In August 2015, Cozy Bear was linked to a spear-phishing cyber-attack against the Pentagon email system, causing the shut down of the entire Joint Staff unclassified email system and Internet access during the investigation.[16][17]

Democratic National Committee (2016)[edit]
Main article: Democratic National Committee cyber attacks
In June 2016, Cozy Bear was implicated alongside the hacker group Fancy Bear in the Democratic National Committee cyber attacks.[2] While the two groups were both present in the Democratic National Committee's servers at the same time, they appeared to be unaware of the other, each independently stealing the same passwords and otherwise duplicating their efforts.[18] A CrowdStrike forensic team determined that while Cozy Bear had been on the DNC's network for over a year, Fancy Bear had only been there a few weeks.[19] Cozy Bear's more sophisticated tradecraft and interest in traditional long-term espionage suggest that the group originates from a separate Russian intelligence agency.[18]

US think tanks and NGOs (2016)[edit]
After the 2016 United States presidential election, Cozy Bear was linked to a series of coordinated and well-planned spear phishing campaigns against U.S.-based think tanks and non-governmental organizations (NGOs).[20]

Norwegian government (2017)[edit]
On 3 February 2017, the Norwegian Police Security Service (PST) reported that attempts had been made to spearphish the email accounts of nine individuals in the Ministry of Defence, Ministry of Foreign Affairs, and the Labour Party. The acts were attributed to Cozy Bear, whose targets included the Norwegian Radiation Protection Authority, PST section chief Arne Christian Haugstøyl, and an unnamed colleague. Prime Minister Erna Solberg called the acts "a serious attack on our democratic institutions."[21] The attacks were reportedly conducted in January 2017.[22]

Dutch ministries (2017)[edit]
In February 2017, it was revealed that Cozy Bear and Fancy Bear had made several attempts to hack into Dutch ministries, including the Ministry of General Affairs, over the previous six months. Rob Bertholee, head of the AIVD, said on EenVandaag that the hackers were Russian and had tried to gain access to secret government documents.[23]
In a briefing to parliament, Dutch Minister of the Interior and Kingdom Relations Ronald Plasterk announced that votes for the Dutch general election in March 2017 would be counted by hand.[24]

Operation Ghost[edit]
Suspicions that Cozy Bear had ceased operations were dispelled in 2019 by the discovery of three new malware families attributed to Cozy Bear: PolyglotDuke, RegDuke and FatDuke. This shows that Cozy Bear did not cease operations, but rather had developed new tools that were harder to detect. Target compromises using these newly uncovered packages are collectively referred to as Operation Ghost.[25]

COVID-19 vaccine data (2020)[edit]
In July 2020 Cozy Bear was accused by the NSA, NCSC and the CSE of trying to steal data on vaccines and treatments for COVID-19 being developed in the UK, US, and Canada.[26][27][28][29][4]

SUNBURST malware supply chain attack (2020)[edit]
Main article: 2020 United States federal government data breach
On 8 December 2020, U.S. cybersecurity firm FireEye disclosed that a collection of their proprietary cybersecurity research tools had been stolen, possibly by "a nation with top-tier offensive capabilities."[30][31]  On 13 December 2020, FireEye announced that investigations into the circumstances of that intellectual property theft revealed "a global intrusion campaign ... [utilizing a] supply chain attack trojanizing SolarWinds Orion business software updates in order to distribute malware we call SUNBURST.... This campaign may have begun as early as Spring 2020 and... is the work of a highly skilled actor [utilizing] significant operational security."[32][promotional source?]
Shortly thereafter, SolarWinds confirmed that multiple versions of their Orion platform products had been compromised, probably by a foreign nation state.[33] The impact of the attack prompted the U.S. Cybersecurity and Infrastructure Security Agency (CISA) to issue a rare emergency directive.[34][35] Approximately 18,000 SolarWinds clients were exposed to SUNBURST, including several U.S. federal agencies.[36] Washington Post sources identified Cozy Bear as the group responsible for the attack.[37][4]
According to Microsoft,[38] the hackers then stole signing certificates that allowed them to impersonate any of a target’s existing users and accounts through the Security Assertion Markup Language. Typically abbreviated as SAML, the XML-based language provides a way for identity providers to exchange authentication and authorization data with service providers.[39]

Republican National Committee (2021)[edit]
In July 2021, Cozy Bear breached systems of the Republican National Committee.[40][41] Officials said they believed the attack to have been conducted through Synnex.[40] The cyberattack came amid larger fallout over the ransomware attack spread through compromised Kaseya VSA software.[40]

Microsoft (2022-23)[edit]
On 24 August 2022, Microsoft revealed a customer was compromised by a Cozy Bear attack that had very high resilience on an Active Directory Federated Services server and dubbed this attack method "MagicWeb", an attack which "manipulates the user authentication certificates used for authentication".[42]
In January 2024, Microsoft reported having recently discovered and ended a breach beginning the previous November of the email accounts of their senior leadership and other employees in the legal and cybersecurity teams using a "password spray", a form of brute-force attack. This hack conducted by Midnight Blizzard appears to have aimed to find what the company knew about the hacking operation.[43]

See also[edit]
2016 United States election interference by Russia
The Plot to Hack America
Vulkan files leak
References[edit]


^ a b c d e "MiniDuke relation 'CozyDuke' Targets White House". Threat Intelligence Times. 27 April 2015. Archived from the original on 11 June 2018. Retrieved 15 December 2016.

^ a b c Alperovitch, Dmitri. "Bears in the Midst: Intrusion into the Democratic National Committee". CrowdStrike Blog. Retrieved 27 September 2016.

^ "INTERNATIONAL SECURITY AND ESTONIA" (PDF). www.valisluureamet.ee. 2018. Archived from the original (PDF) on 2020-10-26. Retrieved 2020-12-15.

^ a b c d Andrew S. Bowen (January 4, 2021). Russian Cyber Units (Report). Congressional Research Service. p. 1. Retrieved July 25, 2021.

^ a b Huib Modderkolk (25 January 2018). "Dutch agencies provide crucial intel about Russia's interference in US-elections". de Volkskrant.

^ "Who Is COZY BEAR?". CrowdStrike. 19 September 2016. Archived from the original on 15 December 2020. Retrieved 15 December 2016.

^ "F-Secure Study Links CozyDuke to High-Profile Espionage" (Press Release). 30 April 2015. Retrieved 6 January 2017.

^ "Cyberattacks Linked to Russian Intelligence Gathering" (Press Release). F-Secure. 17 September 2015. Retrieved 6 January 2017.

^ Weise, Karen (January 19, 2024). "Microsoft Executives' Emails Hacked by Group Tied to Russian Intelligence". The New York Times.

^ Sanger, David E. (2020-12-13). "Russian Hackers Broke Into Federal Agencies, U.S. Officials Suspect". The New York Times. ISSN 0362-4331. Retrieved 2021-10-03.

^ a b c Kaspersky Lab's Global Research & Analysis Team (3 July 2014). "Miniduke is back: Nemesis Gemina and the Botgen Studio". Securelist.

^ a b c d e ""Forkmeiamfamous": Seaduke, latest weapon in the Duke armory". Symantec Security Response. 13 July 2015.

^ a b c Baumgartner, Kurt; Raiu, Costin (21 April 2015). "The CozyDuke APT". Securelist.

^ "HAMMERTOSS: Stealthy Tactics Define a Russian Cyber Threat Group". FireEye. 9 July 2015. Archived from the original on 23 March 2019. Retrieved 7 August 2015.

^ Noack, Rick (January 26, 2018). "The Dutch were a secret U.S. ally in war against Russian hackers, local media reveal". The Washington Post. Retrieved February 15, 2023.

^ Kube, Courtney (7 August 2015). "Russia hacks Pentagon computers: NBC, citing sources". Retrieved 7 August 2015.

^ Starr, Barbara (7 August 2015). "Official: Russia suspected in Joint Chiefs email server intrusion". Retrieved 7 August 2015.

^ a b "Bear on bear". The Economist. 22 September 2016. Retrieved 14 December 2016.

^ Ward, Vicky (October 24, 2016). "The Man Leading America's Fight Against Russian Hackers Is Putin's Worst Nightmare". Esquire.

^ "PowerDuke: Widespread Post-Election Spear Phishing Campaigns Targeting Think Tanks and NGOs". Volexity. November 9, 2016.

^ Stanglin, Doug (February 3, 2017). "Norway: Russian hackers hit spy agency, defense, Labour party". USA Today.

^ "Norge utsatt for et omfattende hackerangrep". NRK. February 3, 2017.

^ Modderkolk, Huib (February 4, 2017). "Russen faalden bij hackpogingen ambtenaren op Nederlandse ministeries". De Volkskrant (in Dutch).

^ Cluskey, Peter (February 3, 2017). "Dutch opt for manual count after reports of Russian hacking". The Irish Times.

^ "Operation Ghost: The Dukes aren't back – they never left". ESET Research. October 17, 2019.

^ "NSA Teams with NCSC, CSE, DHS CISA to Expose Russian Intelligence Services Targeting COVID". National Security Agency Central Security Service. Archived from the original on 11 December 2020. Retrieved 25 July 2020.

^ "CSE Statement on Threat Activity Targeting COVID-19 Vaccine Development – Thursday, July 16, 2020". cse-cst.gc.ca. Communications Security Establishment. 14 July 2020. Retrieved 16 July 2020.

^ James, William (16 July 2020). "Russia trying to hack and steal COVID-19 vaccine data, says Britain". Reuters UK. Retrieved 16 July 2020.

^ "UK and allies expose Russian attacks on coronavirus vaccine development". National Cyber Security Centre. 16 July 2020. Retrieved 16 July 2020.

^ Sanger, David E.; Perlroth, Nicole (December 8, 2020). "FireEye, a Top Cybersecurity Firm, Says It Was Hacked by a Nation-State". The New York Times.

^ agencies, Guardian staff and (December 9, 2020). "US cybersecurity firm FireEye says it was hacked by foreign government". the Guardian.

^ "Highly Evasive Attacker Leverages SolarWinds Supply Chain to Compromise Multiple Global Victims With SUNBURST Backdoor". FireEye.

^ "Security Advisory | SolarWinds". www.solarwinds.com.

^ "cyber.dhs.gov - Emergency Directive 21-01". cyber.dhs.gov. 13 December 2020.

^ "cyber.dhs.gov - Cybersecurity Directives". cyber.dhs.gov. 18 May 2022.

^ Cimpanu, Catalin. "SEC filings: SolarWinds says 18,000 customers were impacted by recent hack". ZDNet.

^ Nakashima, Ellen; Timberg, Craig. "Russian government hackers are behind a broad espionage campaign that has compromised U.S. agencies, including Treasury and Commerce". Washington Post. ISSN 0190-8286. Retrieved 2020-12-14.

^ "Important steps for customers to protect themselves from recent nation-state cyberattacks". 14 December 2020.

^ Goodin, Dan; Timberg. "~18,000 organizations downloaded backdoor planted by Cozy Bear hackers". Ars Technica. Retrieved 2020-12-15.

^ a b c Turton, William; Jacobs, Jennifer (6 July 2021). "Russia 'Cozy Bear' Breached GOP as Ransomware Attack Hit". Bloomberg News. Retrieved 7 July 2021.

^ Campbell, Ian Carlos (6 July 2021). "Russian hackers reportedly attacked GOP computer systems". The Verge. Retrieved 7 July 2021.

^ "MagicWeb: NOBELIUM's post-compromise trick to authenticate as anyone". Microsoft Security Blog. Microsoft. 24 August 2022. Retrieved 26 August 2022.

^ Franceschi-Bicchierai, Lorenzo (19 January 2024). "Hackers breached Microsoft to find out what Microsoft knows about them". Techcrunch. Retrieved 22 January 2024.


External links[edit]
Russian government employees charged in hacking campaigns
vteHacking in the 2010s
← 2000s
Timeline
2020s →
Major incidents2010
Operation Aurora (publication of 2009 events)
Australian cyberattacks
Operation Olympic Games
Operation ShadowNet
Operation Payback
2011
Canadian government
DigiNotar
DNSChanger
HBGary Federal
Operation AntiSec
PlayStation network outage
RSA SecurID compromise
2012
LinkedIn hack
Stratfor email leak
Operation High Roller
2013
South Korea cyberattack
Snapchat hack
Cyberterrorism Attack of June 25
2013 Yahoo! data breach
Singapore cyberattacks
2014
Anthem medical data breach
Operation Tovar
2014 celebrity nude photo leak
2014 JPMorgan Chase data breach
2014 Sony Pictures hack
Russian hacker password theft
2014 Yahoo! data breach
2015
Office of Personnel Management data breach
Hacking Team
Ashley Madison data breach
VTech data breach
Ukrainian Power Grid Cyberattack
SWIFT banking hack
2016
Bangladesh Bank robbery
Hollywood Presbyterian Medical Center ransomware incident
Commission on Elections data breach
Democratic National Committee cyber attacks
Vietnam Airport Hacks
DCCC cyber attacks
Indian Bank data breaches
Surkov leaks
Dyn cyberattack
Russian interference in the 2016 U.S. elections
2016 Bitfinex hack
2017
SHAttered
2017 Macron e-mail leaks
WannaCry ransomware attack
Westminster data breach
Petya and NotPetya
2017 Ukraine ransomware attacks
Vault7 data breach
Equifax data breach
Deloitte breach
Disqus breach
2018
Trustico
Atlanta cyberattack
SingHealth data breach
2019
Sri Lanka cyberattack
Baltimore ransomware attack
Bulgarian revenue agency hack
WhatsApp snooping scandal
Jeff Bezos phone hacking incident
Hacktivism
Anonymous
associated events
CyberBerkut
GNAA
Goatse Security
Lizard Squad
LulzRaft
LulzSec
New World Hackers
NullCrew
OurMine
PayPal 14
RedHack
Teamp0ison
 TDO 
UGNazi
Ukrainian Cyber Alliance
Advancedpersistent threats
Bureau 121
Charming Kitten
Cozy Bear
Dark Basin
DarkMatter
Elfin Team
Equation Group
Fancy Bear
GOSSIPGIRL (confederation)
Guccifer 2.0
Hacking Team
Helix Kitten
Iranian Cyber Army
Lazarus Group (BlueNorOff) (AndAriel)
NSO Group
Numbered Panda
PLA Unit 61398
PLA Unit 61486
PLATINUM
Pranknet
Red Apollo
Rocket Kitten
Stealth Falcon
Syrian Electronic Army
Tailored Access Operations
The Shadow Brokers
Yemen Cyber Army
Individuals
George Hotz
Guccifer
Jeremy Hammond
Junaid Hussain
Kristoffer von Hassel
Mustafa Al-Bassam
MLT
Ryan Ackroyd
Sabu
Topiary
Track2
The Jester
Major vulnerabilitiespublicly disclosed
Evercookie (2010)
iSeeYou (2013)
 Heartbleed (2014)
Shellshock (2014)
POODLE (2014)
Rootpipe (2014)
Row hammer (2014)
SS7 vulnerabilities (2014)
JASBUG (2015)
Stagefright (2015)
DROWN (2016)
Badlock (2016)
Dirty COW (2016)
Cloudbleed (2017)
Broadcom Wi-Fi (2017)
EternalBlue (2017)
DoublePulsar (2017)
Silent Bob is Silent (2017)
KRACK (2017)
ROCA vulnerability (2017)
BlueBorne (2017)
Meltdown (2018)
Spectre (2018)
EFAIL (2018)
Exactis (2018)
Speculative Store Bypass (2018)
Lazy FP state restore (2018)
TLBleed (2018)
SigSpoof (2018)
Foreshadow (2018)
Dragonblood (2019)
Microarchitectural Data Sampling (2019)
BlueKeep (2019)
Kr00k (2019)
Malware2010
Bad Rabbit
 Black Energy 2
SpyEye
Stuxnet
2011
Coreflood
Alureon
Duqu
Kelihos
Metulji botnet
Stars
2012
Carna
Dexter
FBI
Flame
Mahdi
Red October
Shamoon
2013
CryptoLocker
DarkSeoul
2014
Brambul
 Black Energy 3
Carbanak
Careto
DarkHotel
Duqu 2.0
FinFisher
Gameover ZeuS
Regin
2015
Dridex
Hidden Tear
Rombertik
TeslaCrypt
2016
Hitler
Jigsaw
KeRanger
MEMZ
Mirai
Pegasus
Petya and NotPetya
X-Agent
2017
BrickerBot
Kirk
LogicLocker
Rensenware
Triton
WannaCry
XafeCopy
2018
VPNFilter
2019
Grum
Joanap
NetTraveler
R2D2
Tinba
Titanium
ZeroAccess botnet

vteRussian interference in the 2016 United States electionsEvents
DNC cyber attacks
GRU
Fancy Bear
Guccifer 2.0
SVR RF
Cozy Bear
DCCC cyber attacks
Leaks
DNC email leak
Podesta emails
WikiLeaks
DCLeaks
Pizzagate conspiracy theory
Social media
IRA
Cambridge Analytica
Fake news websites
Russia and BLM
Timelines
Topical
before July 2016
July 2016 – election day
Transition
Jan–Jun 2017
Jul–Dec 2017
Jan–Jun 2018
Jul–Dec 2018
Jan–Jun 2019
Jul–Dec 2019
2020–2022
Timelines related to Donald Trump and Russian interference in United States elections
Post-electionevents
Steele dossier
Assessing Russian Activities and Intentions in Recent US Elections
Dismissal of James Comey
Crossfire Hurricane
Russia investigation origins counter-narrative
Durham special counsel investigation
Mueller special counsel investigation
Legal teams
list of charges
United States v. Flynn
Trials of Paul Manafort
Mueller report
Barr letter
Links between Trump associates and Russia
Trump business projects in Russia
Trump Tower Moscow
Trump Tower meeting
Reactions
Countering America's Adversaries Through Sanctions Act
Nunes memo
Facebook–Cambridge Analytica data scandal
DNC lawsuit
2018 interference
Senate Intelligence Committee report
2020 interference
Vulkan files leak
Kremlin papers
Related
Active measures
Russian disinformation
Cyberwarfare by Russia
Russian web brigades
Propaganda in Russia
Russian espionage in the United States
The Plot to Hack America (2016)
Trump: The Kremlin Candidate? (2017)
Cyberwar: How Russian Hackers and Trolls Helped Elect a President (2018)
Russian Roulette (2018)
Intelligence and Security Committee report
Russian interference in British politics
2016 Brexit referendum
2017 Macron e-mail leaks





Retrieved from "https://en.wikipedia.org/w/index.php?title=Cozy_Bear&oldid=1198107500"
Categories: Russian advanced persistent threat groupsCybercrimeCyberwarfareHacker groupsHacking in the 2000sHacking in the 2010sInformation technology in RussiaMilitary units and formations established in the 2000sOrganizations associated with Russian interference in the 2016 United States electionsHidden categories: CS1 Dutch-language sources (nl)Articles with short descriptionShort description matches WikidataWikipedia introduction cleanup from December 2020All pages needing cleanupArticles covered by WikiProject Wikify from December 2020All articles covered by WikiProject WikifyAll articles lacking reliable referencesArticles lacking reliable references from December 2020






 This page was last edited on 23 January 2024, at 00:53 (UTC).
Text is available under the Creative Commons Attribution-ShareAlike License 4.0;
additional terms may apply.  By using this site, you agree to the Terms of Use and Privacy Policy. Wikipedia® is a registered trademark of the Wikimedia Foundation, Inc., a non-profit organization.


Privacy policy
About Wikipedia
Disclaimers
Contact Wikipedia
Code of Conduct
Developers
Statistics
Cookie statement
Mobile view













Toggle limited content width







