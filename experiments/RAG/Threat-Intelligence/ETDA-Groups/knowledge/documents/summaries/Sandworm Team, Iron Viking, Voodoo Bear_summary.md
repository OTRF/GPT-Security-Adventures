
Report 1

Sandworm Team, also known as Iron Viking and Voodoo Bear, has been actively exploiting a critical vulnerability in the Windows operating system (CVE-2014-4114) to deliver Backdoor.Lancafdo.A malware to targeted organizations in the US and Europe. The vulnerability allows attackers to embed OLE files from external locations, enabling the download and installation of malware on the target's computer. The attacks have targeted NATO, Ukrainian government organizations, Western European governmental organizations, energy sector companies, European telecoms firms, and a US academic organization. The exploitation has been ongoing since August, with spear-phishing emails containing malicious PowerPoint file attachments being used to deliver the malware. Symantec detects the malware payload as Backdoor.Lancafdo.A and advises affected Windows users to apply security patches from Microsoft, keep security software up-to-date, and exercise caution when opening email attachments. The vulnerability is considered critical as it allows remote code execution on the target's computer, and Microsoft has issued a security patch to address it. The threat actor's capability to exploit this vulnerability and use novel techniques like embedding URLs in OLE documents highlights their advanced persistent threat (APT) capabilities. (Report date: October 15, 2014)





Report 2

Malformed report.





Report 3

Malformed report.





Report 4

Summary:
The threat actor known as Sandworm Team, Iron Viking, or Voodoo Bear has been identified as using the BlackEnergy malware for significant geopolitical operations. The threat actor has demonstrated the capability to develop custom plugins for attacking ARM and MIPS platforms, scripts for Cisco network devices, and destructive plugins. The threat actor has targeted victims in various sectors, including power generation, government, technology, and finance, across multiple countries. The threat actor has shown a high level of sophistication in hiding their presence within compromised environments and has used unique tools and techniques, such as router abuse and custom plugins for different architectures. The threat actor has been active since at least 2010 and continues to pose a significant threat to organizations globally. The report provides detailed insights into the threat actor's tactics, techniques, and targets, highlighting the need for enhanced cybersecurity measures to mitigate the risks posed by this threat actor.





Report 5

Malformed report.





Report 6

The Sandworm threat actor, attributed to the Russian GRU, has replaced the VPNFilter malware with a new framework called Cyclops Blink. The actor has been involved in various malicious cyber activities, including disrupting Ukrainian electricity, deploying Industroyer, NotPetya, and attacking the Winter Olympics. Cyclops Blink, active since 2019, is a modular malware framework targeting network devices, primarily WatchGuard devices. The malware is sophisticated, with the capability to beacon device information, download and execute files, and add new modules while running. Sandworm manages Cyclops Blink through a Tor network, using TLS for communication. Mitigations include removing the malware, updating devices, and using multi-factor authentication. The report was last revised on February 23, 2022, and was a collaborative effort by the NCSC, NSA, FBI, and CISA.





Report 7

Malformed report





Report 8

Summary: The Russian state-sponsored hacking group known as Sandworm breached 11 Ukrainian telecommunication service providers between May and September 2023, as reported by Ukraine's CERT-UA. The group utilized phishing lures, Android malware, and data-wipers to target telcos, focusing on reconnaissance using tools like 'masscan' to scan networks for vulnerabilities. Sandworm employed backdoors like 'Poemgate' and 'Poseidon' to gain access to admin credentials and control systems remotely. They used tools like 'Whitecat' to cover their tracks and deployed scripts to disrupt services, particularly targeting Mikrotik equipment. The attacks were sophisticated and aimed at causing service interruptions and data breaches in the Ukrainian telco sector. Date: October 16, 2023.





Report 9

Summary: Russian hackers, specifically the Sandworm Team, have been targeting Ukraine with Follina exploits, a remote code execution vulnerability in Microsoft Windows Support Diagnostic Tool (MSDT) tracked as CVE-2022-30190. The attacks have been ongoing since at least April 2022, with evidence pointing to the Sandworm hacker group as the perpetrators. The threat actors targeted media organizations in Ukraine, including radio stations and newspapers, through a malicious email campaign. The malware named "CrescentImp" was used in the attacks, with indicators of compromise provided by CERT-UA. Sandworm's activities in Ukraine have increased following the Russian invasion, with previous attacks targeting energy providers and operating the Cyclops Blink botnet. The U.S. has offered a reward for information on members of the Sandworm group. The threat actor's capability is demonstrated through the use of novel tools and techniques, highlighting the evolving nature of cyber threats. 

Date: June 13, 2022

Region: Ukraine

Operating Sector: Media organizations

Type of Company: Radio stations and newspapers

Evidence of Capability: Exploitation of Follina vulnerability, use of malicious email campaigns, targeting critical infrastructure, creation of persistent malware, and involvement in high-profile cyber incidents.





Report 10

Summary: The Russian threat actor group known as Sandworm utilized WinRAR to wipe data from Ukrainian state agency devices. The attack involved compromised VPN accounts without multi-factor authentication to access critical systems. The threat actors used a BAT script named RoarBat on Windows machines to search for specific file types and delete them using WinRAR with the "-df" command-line option. On Linux systems, a Bash script was used with the "dd" utility to overwrite target file types. The attack, similar to a previous incident in January 2023, aimed to destroy data effectively. The threat actors' use of legitimate programs like WinRAR and dd likely helped evade detection by security software. The incident highlights the need for organizations to enhance security measures, patch vulnerabilities, and monitor network activity. Date: May 3, 2023. Region: Ukraine. Operating Sector: State agency. Company Type: Government.





Report 11

Summary:
- Threat actor: Sandworm Team, Iron Viking, Voodoo Bear
- Date: December attack on Kyivstar, Ukraine's largest telecommunications service provider
- Russian hackers wiped thousands of systems on Kyivstar's core network, impacting 25 million subscribers
- Evidence of capability: Attack involved wiping virtual servers and computers, destroying the core of the telecoms operator
- Novelty of tools and techniques: Malware samples used by threat actor under research, attack carefully prepared for months
- Region: Ukraine
- Operating sector: Telecommunications
- Type of company: Telecommunications service provider
- Sandworm military hackers identified as responsible for the attack
- Sandworm previously breached networks of 11 Ukrainian telecom service providers since May 2023.





Report 12

Sandworm Team, also known as Iron Viking and Voodoo Bear, disrupted power in Ukraine through a novel attack against operational technology in late 2022. The threat actor targeted a critical infrastructure organization in Ukraine, leveraging living off the land (LotL) techniques to trip substation circuit breakers, causing a power outage coinciding with missile strikes. Sandworm later deployed a new variant of CADDYWIPER in the victim's IT environment. This attack showcased Russia's evolving cyber physical attack capability, indicating a growing maturity in offensive operational technology (OT) arsenal. Sandworm's ability to quickly develop OT capabilities, potentially within two months, suggests a significant threat to OT systems globally. The attack, tracked as UNC3810 before merging with Sandworm, highlights the group's focus on Ukraine and its disruptive and destructive campaigns. Sandworm's use of LotL techniques and streamlined OT attack capabilities reveal insights into Russia's offensive cyber capabilities. The attack coincided with Russian kinetic operations, indicating strategic timing. Sandworm's global threat activity and novel OT capabilities pose an immediate threat to critical infrastructure worldwide, urging asset owners to take mitigation actions. The report provides detailed technical analysis, including attack lifecycle, IOCs, hardening guidance, and MITRE ATT&CK mappings. Date: November 9, 2023. Source: Mandiant.





Report 13

Sandworm Team, also known as Iron Viking and Voodoo Bear, is a Russian cyberespionage group that has been active since around 2009. The group is believed to be Russian pro-hacktivists and is closely associated with state-sponsored GRU Unit 74455. Sandworm Team primarily targets Ukrainian entities in sectors such as energy, industrial control systems, SCADA, government, and media. They have been linked to the 2015 Ukrainian energy sector attack. The threat actor has used a variety of tools and techniques, including novel malware like Cyclops Blink, ArguePatch, and SwiftSlicer. Sandworm Team has been involved in multiple high-profile operations, such as the 2015 power outages in Ukraine and the 2022 disruption of power in Ukraine using a novel attack against operational technology. The group has also targeted countries like France, Denmark, and Iran. Counter operations against Sandworm Team have been reported, including the charging of six Russian GRU officers in 2020 and the disruption of a botnet controlled by the GRU in 2022.





Report 14

Summary:
The threat actor known as FROZENBARENTS, attributed to the Russian Armed Forces’ Main Directorate of the General Staff (GRU) Unit 74455, remains highly active in targeting Ukraine, particularly focusing on the energy sector, defense industry, and information operations. They utilize a variety of offensive capabilities, including credential phishing, mobile activity, malware, and exploitation of services. The group has been observed targeting organizations like the Caspian Pipeline Consortium (CPC) and Ukroboronprom, a Ukrainian defense company, through phishing campaigns and hack-and-leak operations. FROZENBARENTS also engages in information operations through online personas like 'CyberArmyofRussia' to promote pro-Russia narratives. Additionally, another threat actor, FROZENLAKE, has been using reflected cross-site scripting (XSS) in phishing attacks against Ukrainian users, a new technique for the group. The report covers activities from the first quarter of 2023 and highlights the ongoing cyber threats posed by these Russian threat actors. The report also mentions the targeting of regional webmail providers by the Belarusian threat actor PUSHCHA. The threat actor's activities demonstrate a high level of sophistication and a focus on targeting specific sectors and regions, showcasing their advanced capabilities and novel techniques. The report was published on April 19, 2023, by Google’s Threat Analysis Group.





Report 15

Summary:
The threat actor known as VOODOO BEAR, also identified as Sandworm Team and BlackEnergy APT Group, is a highly advanced adversary with ties to the Russian Federation. They have been active since at least 2011, targeting entities associated with energy, industrial control systems, SCADA, government, and media for espionage and destructive purposes. VOODOO BEAR utilizes custom-developed plugins for Black Energy malware, including a wiper called PassKillDisk. They have a particular focus on targeting entities in Ukraine and are believed to be behind the 2015 power outages in the country. The threat actor is aligned with Russian state interests and operates in support of Russian economic and national objectives through targeted espionage and sabotage operations. The tools and techniques used by VOODOO BEAR, such as zero-day exploits and custom-developed plugins, highlight their advanced capabilities. The threat actor's operations are consistent with an organization that also tasks multiple pro-Russian hacktivist entities. The report was published on January 29, 2018, by CrowdStrike.


