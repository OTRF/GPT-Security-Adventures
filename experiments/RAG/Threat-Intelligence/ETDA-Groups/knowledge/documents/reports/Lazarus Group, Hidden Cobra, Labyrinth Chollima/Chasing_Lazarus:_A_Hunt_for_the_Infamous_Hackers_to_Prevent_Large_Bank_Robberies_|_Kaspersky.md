# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: Chasing Lazarus: A Hunt for the Infamous Hackers to Prevent Large Bank Robberies | Kaspersky

**Source**: https://www.kaspersky.com/about/press-releases/2017_chasing-lazarus-a-hunt-for-the-infamous-hackers-to-prevent-large-bank-robberies

## Content
Chasing Lazarus: A Hunt for the Infamous Hackers to Prevent Large Bank Robberies | KasperskySkip to main contentSolutions for:Home ProductsSmall Business 1-50 employeesMedium Business 51-999 employeesEnterprise 1000+ employeesSolutions for:Home ProductsSmall Business 1-50 employeesMedium Business 51-999 employeesEnterprise 1000+ employeesKaspersky logoAbout UsAbout UsCompanyTeamTransparencyCorporate NewsPress CenterCareersSponsorshipsPolicy BlogPolicy BlogGeneral CybersecurityIndustrial CybersecurityPrivacyCyber InsuranceDigital SkillsHomeAboutCorporate NewsApril 04, 2017Chasing Lazarus: A Hunt for the Infamous Hackers to Prevent Large Bank RobberiesKaspersky Lab has published the results of its more-than-year-long investigation into the activity of Lazarus – a notorious hacking group allegedly responsible for the theft of 81 million dollars from the Central Bank of Bangladesh in 2016.Kaspersky Lab has published the results of its more-than-year-long investigation into the activity of Lazarus – a notorious hacking group allegedly responsible for the theft of 81 million dollars from the Central Bank of Bangladesh in 2016. During the forensic analysis of artefacts left by the group in South-East Asian and European banks, Kaspersky Lab has reached a deep understanding of what malicious tools the group uses and how it operates while attacking financial institutions, casinos, software developers for investment companies and crypto-currency businesses around the world. This knowledge has helped to interrupt at least two other operations which had one goal - to steal a large amount of money from financial institutions.In February 2016, a group of hackers (unidentified at that time) attempted to steal $851 million USD, and managed to transfer 81 million USD from the Central Bank of Bangladesh. This is considered to be one of the largest, most successful cyber heists ever. Further investigation conducted by researchers from different IT security companies including Kaspersky Lab revealed a high chance that the attacks were conducted by Lazarus – a notorious cyber espionage and sabotage group responsible for a series of regular and devastating attacks, and known for attacking manufacturing companies, media and financial institutions in at least 18 countries around the world since 2009.Although several months of silence followed the Bangladesh attack, the Lazarus group was still active. They had been preparing for a new operation to steal money from other banks and, by the time they were ready, they already had their foot in a financial institution in South East Asia. After being interrupted by Kaspersky Lab products and the following investigation, they were set back for another few months, and later decided to change their operation by moving to Europe. But here too, their attempts were interrupted by Kaspersky Lab’s security software detections, as well as the quick incident response, forensic analysis, and reverse engineering with support from company’s top researchers.Lazarus FormulaBased on the results of the forensic analysis of these attacks, Kaspersky Lab researchers were able to reconstruct the modus operandi of the group.Initial compromise: A single system inside a bank is breached either with remotely accessible vulnerable code (i.e. on a webserver) or through a watering hole attack through an exploit planted on a benign website. Once such a site is visited, the victim’s (bank employee) computer gets malware, which brings additional components.Foothold established: Then the group migrates to other bank hosts and deploys persistent backdoors – the malware allows them to come and go whenever they want.Internal reconnaissance: Subsequently the group spends days and weeks learning the network, and identifying valuable resources. One such resource may be a backup server, where authentication information is stored, a mail server or the whole domain controller with keys to every “door” in the company, as well as servers storing or processing records of financial transactions.Deliver and steal: Finally, they deploy special malware capable of bypassing the internal security features of financial software and issuing rogue transactions on behalf of the bank.Geography and AttributionThe attacks investigated by Kaspersky Lab researchers lasted for weeks. However, the attackers could operate under the radar for months. For example, during the analysis of the incident in South-East Asia, experts discovered that hackers were able to compromise the bank network no less than seven months prior to the day when the bank’s security team requested incident response. In fact, the group had access to the network of that bank even before the day of the Bangladesh incident.According to Kaspersky Lab records, from December 2015, malware samples relating to Lazarus group activity appeared in financial institutions, casinos software developers for investment companies and crypto-currency businesses in Korea, Bangladesh, India, Vietnam, Indonesia, Costa Rica, Malaysia, Poland, Iraq, Ethiopia, Kenya, Nigeria, Uruguay, Gabon, Thailand and several other countries. The latest samples known to Kaspersky Lab were detected in March 2017, showing that attackers have no intention of stopping.Even though attackers were careful enough to wipe their traces, at least one server they breached for another campaign contained a serious mistake with an important artefact being left behind. In preparation for operation, the server was configured as the command & control center for the malware. The first connections made on the day of configuration were coming from a few VPN/proxy servers indicating a testing period for the C&C server. However, there was one short connection on that day which was coming from a very rare IP address range in North Korea.According to researchers, that could mean several things:The attackers connected from that IP address in North KoreaIt was someone else’s carefully planned false flag operationSomeone in North Korea accidentally visited the command and control URLThe Lazarus group heavily invests in new variants of their malware. For months they were trying to create a malicious toolset which would be invisible to security solutions, but every time they did this, Kaspersky Lab’s specialists managed to identify unique features in how they create their code, allowing Kaspersky Lab to keep tracking the new samples. Now, the attackers have gone relatively quiet, which probably means that they have paused to rework their arsenal.“We’re sure they’ll come back soon. In all, attacks like the ones conducted by Lazarus group show that a minor misconfiguration may result in a major security breach, which can potentially cost a targeted business hundreds of millions of dollars in loss. We hope that chief executives from banks, casinos and investment companies around the world will become wary of the name Lazarus,” said Vitaly Kamluk, Head of Global Research and Analysis Team APAC at Kaspersky Lab.Kaspersky Lab products successfully detect and block the malware used by the Lazarus threat actor with the following specific detection names:HEUR:Trojan-Banker.Win32.Alreay*,Trojan-Banker.Win32.Agent*The company is also releasing crucial Indicators of Compromise (IOC) and other data to help organizations search for traces of these attack groups in their corporate networks. For more information go to Securelist.comWe urge all organizations to carefully scan their networks for the presence of Lazarus malware samples and, if detected, to disinfect their systems and report the intrusion to law enforcement and incident response teams.To learn more about financial attacks by Lazarus group, read the blog post available at Securelist.com or watch the video.Chasing Lazarus: A Hunt for the Infamous Hackers to Prevent Large Bank RobberiesKasperskyKaspersky Lab has published the results of its more-than-year-long investigation into the activity of Lazarus – a notorious hacking group allegedly responsible for the theft of 81 million dollars from the Central Bank of Bangladesh in 2016.Related Articles Virus News‘Coyote’ ugly: Kaspersky unveils banking trojan targeting over 60 institutionsA new sophisticated banking Trojan that steals sensitive financial information and introduces advanced tactics to avoid detection has been discovered by Kaspersky's Global Research and Analysis Team (GReAT). Dubbed 'Coyote,' this malware relies on the Squirrel installer for distribution, its name drawing inspiration from coyotes, the natural predators of squirrels.Read More > New cross-platform threats uncovered by Kaspersky Kaspersky's Global Research and Analysis Team (GReAT) has uncovered the emergence of three cross-platform threats, and reveals three new strategies being employed by cybercriminals using the FakeSG campaign, Akira ransomware, and AMOS macOS stealer in its latest report.Read More > Kaspersky reveals advanced tactics in cyber espionage campaigns using MATA toolsetKaspersky's Global Research and Analysis Team (GReAT) and Industrial Control Systems Cyber Emergency Response Team (ICS CERT) have unveiled significant developments in the cyber espionage activities targeting Eastern European industrial companies with the use of updated MATA toolset. The investigation, spanning months, exposed sophisticated attack techniques, updated malware capabilities, and a novel infection chain.Read More > Stay in Touch

Home Solutions

Kaspersky Standard
Kaspersky Plus
Kaspersky Premium
Kaspersky Safe Kids
Kaspersky VPN Secure Connection
Kaspersky Password Manager
All Solutions



Small Business Products
(1-50 employees)

Kaspersky Small Office Security
Kaspersky Endpoint Security Cloud
All Products



Medium Business Products
(51-999 employees)

Kaspersky Endpoint Security Cloud
Kaspersky Endpoint Security for Business Select
Kaspersky Endpoint Security for Business Advanced
All Products



Enterprise Solutions
(1000+ employees)

Cybersecurity Services
Threat Management and Defense
Endpoint Security
Hybrid Cloud Security
All Solutions


© 2024 AO Kaspersky LabPrivacy Policy • Online Tracking Opt-Out Guide • Anti-Corruption Policy • License Agreement B2C • License Agreement B2BContact UsAbout UsPartnersBlogResource CenterPress ReleasesSitemapCareersSelect your countryGlobal
Americas

América Latina
Brasil
United States
Canada

Africa

Afrique Francophone
Algérie
Maroc
South Africa
Tunisie

Middle East

Middle East
الشرق الأوسط



Western Europe

Belgique & Luxembourg
Danmark
Deutschland & Schweiz
España
France
Italia & Svizzera
Nederland & België
Norge
Österreich
Portugal
Sverige
Suomi
United Kingdom



Eastern Europe

Česká republika
Magyarország
Polska
România
Srbija
Türkiye
Ελλάδα (Greece)
България (Bulgaria)
Россия и Белару́сь (Russia & Belarus)
Україна (Ukraine)



Asia & Pacific

Australia
India
New Zealand
Việt Nam
ไทย (Thailand)
한국 (Korea)
中国 (China)
香港特別行政區 (Hong Kong SAR)
台灣 (Taiwan)
日本語 (Japan)

For all other countries

Global Website

We use cookies to make your experience of our websites better. By using and further navigating this website you accept this. Detailed information about the use of cookies on this website is available by clicking on more information.Accept and Close