# Threat actor: Stone Panda, APT 10, menuPass

**UUID**: 2aa9ca75-fa1b-422e-9677-02983934f983

**First seen**: 2006

**Source last modified**: 2022-12-27

## Threat actor aliases

Stone Panda (CrowdStrike), APT 10 (Mandiant), menuPass Team (Symantec), menuPass (Palo Alto), Red Apollo (PWC), CVNX (BAE Systems), Potassium (Microsoft), Hogfish (iDefense), Happyyongzi (FireEye), Cicada (Symantec), Bronze Riverside (SecureWorks), CTG-5938 (SecureWorks), ATK 41 (Thales), TA429 (Proofpoint), ITG01 (IBM)

## Description

menuPass is a threat group that appears to originate from China and has been active since approximately 2009. The group has targeted healthcare, defense, aerospace, and government sectors, and has targeted Japanese victims since at least 2014. In 2016 and 2017, the group targeted managed IT service providers, manufacturing and mining companies, and a university.

Also see {{Operation LiberalFace, MirrorFace}} and {{Twisted Panda}}.

## Sponsor type and motivation

**Sponsor**: State-sponsored, Tianjin bureau of the Chinese Ministry of State Security, Huaying Haitai

**Motivation**: Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in

Aerospace, Defense, Energy, Financial, Government, Healthcare, High-Tech, IT, Media, NGOs, Pharmaceutical, Telecommunications, MSPs

## Observed attacked countries where victims operate in

Australia, Belgium, Brazil, Canada, China, Finland, France, Germany, Hong Kong, India, Israel, Italy, Japan, Montenegro, Netherlands, Norway, Philippines, Singapore, South Africa, South Korea, Sweden, Switzerland, Taiwan, Thailand, Turkey, UAE, UK, USA, Vietnam

## Observed usage of tools

Anel, BloodHound, certutil, ChChes, China Chopper, Cobalt Strike, Derusbi, DILLJUICE, DILLWEED, Ecipekac, Emdivi, EvilGrab RAT, Gh0st RAT, HTran, Impacket, Invoke the Hash, LODEINFO, Mimikatz, MiS-Type, nbtscan, P8RAT, PlugX, Poison Ivy, Poldat, PowerSploit, PowerView, PsExec, PsList, pwdump, Quarks PwDump, QuasarRAT, RedLeaves, Rubeus, SharpSploit, SodaMaster, SNUGRIDE, Trochilus RAT, WinRAR, WmiExec, Living off the Land

## Reported hacking operations

2016-09: Spear-phishing attack
Method: The attackers spoofed several sender email addresses to send spear-phishing emails, most notably public addresses associated with the Sasakawa Peace Foundation and The White House.
Target: Japanese academics working in several areas of science, along with Japanese pharmaceutical and a US-based subsidiary of a Japanese manufacturing organizations.
https://unit42.paloaltonetworks.com/unit42-menupass-returns-new-malware-new-attacks-japanese-academics-organizations/

2016: Operation “Cloud Hopper”
The campaign, which we refer to as Operation Cloud Hopper, has targeted managed IT service providers (MSPs), allowing APT10 unprecedented potential access to the intellectual property and sensitive data of those MSPs and their clients globally. A number of Japanese organizations have also been directly targeted in a separate, simultaneous campaign by the same actor
https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-report-final-v4.pdf
https://www.reuters.com/investigates/special-report/china-cyber-cloudhopper/
https://www.wsj.com/articles/ghosts-in-the-clouds-inside-chinas-major-corporate-hack-11577729061

2016/2017: Leveraging its global footprint, FireEye has detected APT10 activity across six continents in 2016 and 2017. APT10 has targeted or compromised manufacturing companies in India, Japan and Northern Europe; a mining company in South America; and multiple IT service providers worldwide. We believe these companies are a mix of final targets and organizations that could provide a foothold in a final target.
https://www.fireeye.com/blog/threat-research/2017/04/apt10_menupass_grou.html

2017-02: Operation “TradeSecret”
The National Foreign Trade Council (NFTC) website was allegedly infiltrated by Chinese nation-state threat actors, according to a new report from Fidelis Cybersecurity. The attack against the NFTC site has been dubbed ‘Operation TradeSecret’ by Fidelis and is seen as an attempt to gain insight into individuals closely associated with U.S trade policy activities.
https://www.eweek.com/security/chinese-nation-state-hackers-target-u.s-in-operation-tradesecret

2017: Operation “ChessMaster”
Take for instance the self-named ChessMaster, a campaign targeting Japanese academe, technology enterprises, media outfits, managed service providers, and government agencies. It employs various poisoned pawns in the form of malware-laden spear-phishing emails containing decoy documents.
https://blog.trendmicro.com/trendlabs-security-intelligence/chessmaster-cyber-espionage-campaign/

2017: Operation “Soft Cell”
Earlier this year, Cybereason identified an advanced, persistent attack targeting telecommunications providers that has been underway for years, soon after deploying into the environment.
The threat actor was attempting to steal all data stored in the active directory, compromising every single username and password in the organization, along with other personally identifiable information, billing data, call detail records, credentials, email servers, geo-location of users, and more.
https://www.cybereason.com/blog/operation-soft-cell-a-worldwide-campaign-against-telecommunications-providers

2017-11: Targeted Norwegian MSP and US Companies in Sustained Campaign
A sustained cyberespionage campaign targeting at least three companies in the United States and Europe was uncovered by Recorded Future and Rapid7 between November 2017 and September 2018.
https://go.recordedfuture.com/hubfs/reports/cta-2019-0206.pdf

2018: Operation “New Battle”
This report provides a technical overview of the bespoke RedLeaves implants leveraged by the actor in their “new battle” campaign.
https://www.accenture.com/t20180423T055005Z_w_/se-en/_acnmedia/PDF-76/Accenture-Hogfish-Threat-Analysis.pdf
https://www.us-cert.gov/sites/default/files/publications/IR-ALERT-MED-17-093-01C-Intrusions_Affecting_Multiple_Victims_Across_Multiple_Sectors.pdf

2018-07: Attack on the Japanese media sector
In July 2018, FireEye devices detected and blocked what appears to be APT10 (menuPass) activity targeting the Japanese media sector.
https://www.fireeye.com/blog/threat-research/2018/09/apt10-targeting-japanese-corporations-using-updated-ttps.html

2019-01: Breach of Airbus
https://www.mirror.co.uk/travel/news/breaking-airbus-cyber-attack-believed-13955680

2019-03: Operation “A41APT”
https://securelist.com/apt10-sophisticated-multi-layered-loader-ecipekac-discovered-in-a41apt-campaign/101519/
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/cicada-apt10-japan-espionage

2019-04: In April 2019, enSilo detected what it believes to be new activity by Chinese cyber espionage group APT10. The variants discovered by enSilo are previously unknown and deploy malware that is unique to the threat actor.
https://blog.ensilo.com/uncovering-new-activity-by-apt10

2019-10: Japan-Linked Organizations Targeted in Long-Running and Sophisticated Attack Campaign
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/cicada-apt10-japan-espionage

2021-02: Chinese hackers target Indian vaccine makers SII, Bharat Biotech, says security firm
https://www.cnbctv18.com/healthcare/chinese-hackers-target-indian-vaccine-makers-sii-bharat-biotech-says-security-firm-8461981.htm

2021-11: Operation “Cache Panda”
A hacking group affiliated with the Chinese government is believed to have carried out a months-long attack against Taiwan’s financial sector by leveraging a vulnerability in a security software solution used by roughly 80% of all local financial organizations.
https://therecord.media/chinese-hackers-linked-to-months-long-attack-on-taiwanese-financial-sector/

2022-02: Cicada: Chinese APT Group Widens Targeting in Recent Espionage Activity
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/cicada-apt10-china-ngo-government-attacks

## Reported counter operations against threat actor

2018-12: Chinese Hackers Indicted
https://www.fbi.gov/news/stories/chinese-hackers-indicted-122018
https://www.justice.gov/opa/speech/deputy-attorney-general-rod-j-rosenstein-announces-charges-against-chinese-hackers

2020-07: EU imposes the first ever sanctions against cyber-attacks
https://www.consilium.europa.eu/en/press/press-releases/2020/07/30/eu-imposes-the-first-ever-sanctions-against-cyber-attacks/



