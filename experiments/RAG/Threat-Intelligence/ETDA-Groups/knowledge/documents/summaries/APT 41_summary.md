
Report 1

APT41, known for cyberespionage activities, has resurfaced as Earth Baku with a new campaign targeting public and private entities in the Indo-Pacific region. The group utilizes advanced malware tools like StealthVector and StealthMutant, along with a backdoor named ScrambleCross, to carry out targeted attacks. The campaign, traced back to July 2020, involves multiple attack vectors such as SQL injection, scheduled task installment, and exploitation of vulnerabilities like ProxyLogon. Earth Baku's recruitment of members with low-level programming skills indicates a focus on developing novel tools for cyber operations. The group's activities have been linked to previous campaigns, showcasing a continuous evolution in their tactics and techniques. The victims targeted include specific industries in countries like India, Indonesia, Malaysia, and Taiwan. The report provides detailed insights into Earth Baku's new cyberespionage campaign, highlighting the group's capabilities and the sophistication of their tools.





Report 2

Malformed report.





Report 3

APT41, a threat actor, conducted a global attack campaign between January 20 and March 11, 2020, targeting Citrix, Cisco, and Zoho network appliances by exploiting CVE-2019-19781. The attack affected industries such as healthcare, higher education, manufacturing, government, and technology services in North America, South America, and Europe. A backdoor named Speculoos was used, specifically designed to execute on FreeBSD operating systems. The backdoor communicated with command and control (C2) servers over TCP/443, allowing the adversary to gain full control over victim systems. The deployment of a tool to run on FreeBSD was considered novel, as malware targeting BSD-based systems is rare. The backdoor was identified as an ELF executable compiled with GCC 4.2.1. Palo Alto Networks customers were protected from this threat, and indicators of compromise were provided for further investigation. The attack campaign was believed to be more opportunistic in nature, aiming to gain footholds in multiple organizations with minimal effort.





Report 4

APT41, a state-sponsored hacker group, conducted four malicious campaigns in 2021, targeting government and private organizations in the US, Taiwan, India, China, Thailand, Hong Kong, Mongolia, Indonesia, Vietnam, Bangladesh, Ireland, Brunei, and the UK. The group's targets included industries such as government, manufacturing, healthcare, logistics, hospitality, finance, education, telecommunications, consulting, sports, media, and travel. APT41 used tools like Acunetix, Nmap, JexBoss, sqlmap, and fofa.su to conduct reconnaissance and gain initial access. They employed SQL injection attacks to breach websites and gain access to servers, using a custom Cobalt Strike Beacon as their main tool. APT41's "working" days were identified as Monday to Friday, starting at 10 AM and finishing around 7 PM (UTC+8). The threat actors used unique methods to create payloads on target servers, involving encoding payloads in multiple stages. The group's infrastructure was identified using SSL certificates and server configurations associated with Cobalt Strike. APT41's operations were characterized by Chinese strings, Pinyin format for directory names, and specific working hours. The report provides insights into the group's tactics, techniques, and procedures, aiding in threat hunting and attribution efforts.





Report 5

APT 41, a threat actor group originating from China, has been active since 2012, engaging in both financially motivated cyber operations and state-sponsored espionage activities. The group has targeted victims across various sectors, including construction, defense, healthcare, and online video game companies, in countries such as the USA, UK, Australia, and South Korea. APT 41 has been linked to multiple hacking operations, such as the ShadowPad supply-chain attack in 2017 and the Operation "ShadowHammer" targeting ASUS users in 2018. The threat actor group has demonstrated a wide range of tools and techniques, including the use of backdoors like MESSAGETAP and PipeMon, as well as malware like BIOPASS RAT and xDll. APT 41's activities have been the subject of counter operations, with international cyber defendants, including APT 41 actors, being charged in connection with computer intrusion campaigns in 2020. The threat actor group continues to evolve and conduct cyberespionage campaigns, with recent reports highlighting operations like "Earth Baku" and "Blackfly" targeting critical infrastructure and materials technology, respectively.





Report 6

Malformed report.





Report 7

Summary:
APT 41, a threat actor, has been identified as the source of the BIOPASS RAT malware that targets online gambling companies in China through a watering hole attack. The malware is capable of stealing private information by sniffing victims' screens using Open Broadcaster Software (OBS) and Real-Time Messaging Protocol (RTMP) for live streaming. The threat actor behind BIOPASS RAT is actively developing the malware, with markers indicating different versions of RAT code. Evidence suggests a potential connection between BIOPASS RAT and the Winnti Group (APT41). The malware uses sophisticated techniques to compromise victims' systems and exfiltrate data, highlighting the importance of downloading from trusted sources. Indicators of Compromise (IoCs) include file hashes, URLs, and domains associated with the malware.





Report 8

APT41, a Chinese nation-state threat actor, likely carried out a third-party attack on Air India, affecting multiple airline companies. Group-IB's Threat Intelligence team discovered the ColunmTK campaign, attributing it to APT41 with moderate confidence. Evidence of compromised workstations and exfiltration of 200 MB of data from Air India's network was found. The threat actor used sophisticated techniques, including lateral movement commands and DNS tunneling. The attack lasted for at least 2 months and 26 days, with Cobalt Strike beacons spreading in the network within 24 hours. APT41's network infrastructure and SSL certificate usage linked them to the attack. The campaign involved the use of specific tools and techniques, such as BadPotato malware and DNS tunneling. Group-IB provided indicators of compromise and MITRE ATT&CK mapping for companies to enhance their security against APT41. The attack highlights the significant threat posed by APT41 to the airline industry and the need for enhanced cybersecurity measures. (Date: 10.06.2021)





Report 9

APT41 is a Chinese state-sponsored cyberthreat group that has been active since 2012, targeting organizations globally in sectors such as travel, telecommunications, healthcare, news, and education. They use phishing emails with malicious attachments to gain access and deploy advanced malware for espionage and financially motivated activities. A recent report by BlackBerry Research & Intelligence Team uncovered APT41's infrastructure using unique Cobalt Strike activity with malleable command-and-control profiles. The threat actor uses phishing lures targeting victims in India related to new tax legislation and COVID-19 statistics to execute Cobalt Strike Beacons on victim networks. The use of customized profiles to blend into normal network traffic and the overlap of indicators of compromise with other documented campaigns suggest APT41's continued and evolving cyber operations. The report provides detailed insights into the tools, techniques, and procedures used by APT41, showcasing their capability and sophistication in conducting cyber campaigns. The evidence presented in the report points to APT41's ongoing threat activity and the need for vigilance in defending against their attacks. Date: 10.05.21.





Report 10

Malformed report.





Report 11

Summary:
- Threat actor: APT41
- Region: China-nexus group targeting various industries globally
- Operating sector: Gaming, healthcare, high-tech, higher education, telecommunications, travel services
- Novelty of tools and techniques: APT41 quickly adapts to changes, recompiles malware within hours, exploits vulnerabilities rapidly, utilizes multiple malware families (HIGHNOON, ACEHASH), and deploys backdoors for persistence
- Evidence of capability: APT41 detected exploiting CVE-2019-3396 vulnerability in Atlassian Confluence Server, utilizing China Chopper web shell, deploying HIGHNOON backdoor, and harvesting credentials using ACEHASH
- Date: Incident detected in April 2019
- Operation time window: Attack neutralized within 35 minutes of detection
- Source: Mandiant report "GAME OVER: Detecting and Stopping an APT41 Operation"
- Link: https://www.fireeye.com/blog/threat-research/2019/08/game-over-detecting-and-stopping-an-apt41-operation.html





Report 12

APT 41, a threat actor known for targeting the gaming industry in Asia, has been identified in supply-chain attacks distributing malware through compromised game developers. The attacks, attributed to the Winnti Group, involved inserting backdoors into game builds, with recent incidents affecting two games and a gaming platform application. The malware used in these attacks, although using different configurations, included the same backdoor code and mechanism for launching. The backdoor payload, which is small in size, had specific configurations for C&C server URLs and executable filenames. The threat actor used domain names related to the game or application publisher for C&C infrastructure. The malware reported information about infected machines to the C&C server and had commands for downloading and running additional executables. ESET researchers identified a second stage payload, Win64/Winnti.BN, delivered to victims, with an auto-update mechanism using a C&C server. The targets of the attacks were primarily located in Asia, with Thailand being a significant target. The threat actor's motives, whether financial gain or espionage, remain unclear. ESET products detect this threat as Win32/HackedApp.Winnti.A, Win32/HackedApp.Winnti.B, Win32/Winnti.AG, and Win64/Winnti.BN. The report provides indicators of compromise (IoCs) for the compromised files and payload samples. The attacks highlight the challenge of detecting and preventing supply-chain attacks in the gaming industry.





Report 13

Summary:
APT 41, a threat actor likely operated by a Chinese nation-state, has been identified using a new Linux backdoor named RedXOR. The backdoor targets Linux endpoints and servers, masquerading as a polkit daemon and using an XOR-based network data encoding scheme. Evidence suggests that RedXOR was developed by high-profile Chinese threat actors targeting legacy Linux systems. The threat actor has been linked to previously reported malware associated with the Winnti umbrella threat group. The backdoor exhibits similarities in techniques and functionalities with other Winnti malware, including the use of open-source kernel rootkits, network data encoding with XOR, and persistence methods. The threat actor's operation is still active, as indicated by the "on and off" availability of the Command and Control server. The malware communicates with the C2 server over TCP sockets, disguising traffic as HTTP. Commands supported by the malware include system information collection, shell functionality, and network tunneling. Intezer Protect can be used to detect and respond to the RedXOR threat, providing alerts and visibility into compromised systems. The report provides IOCs for detection and response, along with recommendations for victims of the operation. The threat landscape for Linux systems is evolving, with sophisticated threats like RedXOR posing a risk to organizations, especially those using public cloud workloads. The report offers insights into the technical analysis, communication methods, and functionalities of the RedXOR backdoor, highlighting the need for proactive security measures to defend against such threats. (Report date: 10 March 2021)





Report 14

Summary:
- Threat actor: APT41, a Chinese APT group
- Date: Operations span from as early as 2012 to the present day
- Region: China
- Operating sector: Telecommunications network provider
- Novelty of tools and techniques: APT41 deployed a new malware family named MESSAGETAP to monitor and save SMS traffic from specific phone numbers, IMSI numbers, and keywords for theft. The malware was designed to target and save SMS message contents, IMSI numbers, and phone numbers based on predefined lists. It also interacted with call detail record (CDR) databases to query, save, and steal records of high-ranking individuals. The malware used XOR decoding with a specific key and targeted sensitive data at scale, reflecting an evolving nature of Chinese cyber espionage campaigns.
- Evidence of capability: APT41's operations included state-sponsored cyber espionage missions and financially-motivated intrusions, targeting telecommunication organizations, travel services, and healthcare providers. The threat actor's ability to access critical information junctures and obtain sensitive data at scale indicates a high level of sophistication and strategic targeting.
- Source: FireEye Mandiant report titled "MESSAGETAP: Who’s Reading Your Text Messages?" dated October 31, 2019.





Report 15

Summary:
APT 41, a Chinese-speaking threat actor, was behind the MoonBounce attack, targeting victims in the transportation technology sector. The attack involved a sophisticated implant within UEFI firmware, allowing for fileless attacks with a small footprint. The threat actor demonstrated a high level of technical competence by modifying existing firmware components to introduce malicious code. The attack also involved other malware like ScrambleCross and Microcin, indicating a broader campaign. The infrastructure used by the threat actor was scattered across multiple ASNs, showing a level of sophistication in maintaining their operations. The attack aimed at establishing a longstanding foothold in the network for espionage activities. The report provides indicators of compromise and recommendations for mitigating such attacks. The operation took place in January 2022.





Report 16

Summary:
The threat actor known as APT 41, specifically the Winnti Group, targeted video gaming companies in South Korea and Taiwan developing MMO games in February 2020. They used a new modular backdoor named PipeMon to compromise victims' build systems and game servers, potentially leading to supply-chain attacks and financial gain through manipulation of in-game currencies. The Winnti Group, active since 2012, has a history of high-profile supply-chain attacks against the software industry. The threat actor's capability is evidenced by the use of custom tools like AceHash and the novel technique of compromising a victim's build environment to trojanize legitimate applications. The campaign was attributed to the Winnti Group based on indicators like C&C domains and malware used in previous campaigns. The threat actor's persistence and evasion techniques, as well as their use of stolen code-signing certificates, demonstrate their advanced capabilities. The report was published on May 21, 2020, by ESET Research.





Report 17

Summary:
APT 41, known as Operation ShadowHammer, conducted a supply chain attack targeting users of the ASUS Live Update Utility between June and November 2018. The attack affected potentially over a million users worldwide. The threat actors injected a backdoor into the utility using stolen digital certificates, making the malware mostly invisible to security solutions. The attackers focused on specific targets by matching MAC addresses, indicating a high level of sophistication and precision. The modular approach and advanced techniques used suggest a well-developed group behind the attack. Similar malware from three other vendors in Asia was also discovered, indicating a coordinated effort. Kaspersky Lab detected and blocked the malware, recommending advanced security measures to prevent future attacks. The operation was linked to the BARIUM APT group, known for previous incidents like ShadowPad and CCleaner. The full findings were presented at the Security Analyst Summit 2019 in Singapore.





Report 18

Malformed report.





Report 19

Summary:
APT 41, attributed to Chinese government intelligence officers, has been conducting advanced malware network intrusions targeting software and gaming companies in the US, Europe, Russia, and elsewhere since at least 2009. The threat actor, known as Winnti Umbrella, has been linked to various hacking groups and campaigns, including LEAD, BARIUM, Wicked Panda, GREF, PassCV, Axiom, and Winnti. The attackers have made operational security errors, revealing key information about their targets and possible locations. They use phishing emails to gain entry into target networks and have evolved to use living-off-the-land infection techniques. The threat actor's primary objective is to exfiltrate code-signing certificates to sign malware for attacks against higher-value targets, primarily political entities. The attackers have been sloppy at times but remain an advanced and potent threat. The report was published on May 5, 2018, by researchers from 401TRG and ProtectWise.





Report 20

Summary:
- Threat actor identified as APT 41 conducted a supply-chain attack known as ShadowPad targeting hundreds of large companies worldwide.
- The attack involved a backdoor planted in server management software used by various sectors including financial services, education, telecoms, manufacturing, energy, and transportation.
- The backdoor allowed attackers to download malicious modules or steal data once activated.
- Kaspersky Lab experts detected and alerted NetSarang, the software vendor, prompting the removal of the malicious code and release of an update.
- The attack was similar to PlugX malware variants used by the Winnti APT, a Chinese-speaking cyberespionage group, but a precise connection was not established.
- The malicious module was activated in Hong Kong, with potential dormant presence in other systems globally.
- NetSarang issued a statement acknowledging the unintentional inclusion of the backdoor and implemented measures to prevent future compromises.
- Kaspersky Lab products detect and protect against the ShadowPad malware.
- Users are advised to update the affected software and check for unusual DNS queries.
- The attack highlights the need for advanced network monitoring solutions to detect such sophisticated threats.





Report 21

Summary:
APT 41, also known as Winnti, has been active since at least 2012 and originates from China. The threat actor targets various industries globally, including gaming, software development, aerospace, energy, pharmaceuticals, finance, telecom, construction, and education. They use sophisticated attack methods, including supply chain and watering hole attacks. The group's core toolkit consists of malware they develop themselves. The first attack with ShadowPad, a backdoor used by Winnti, was recorded in 2017. The threat actor has been involved in supply chain attacks such as the CCleaner and ASUS hacks. The group has compromised over 50 computers, including a university in the U.S., an audit firm in the Netherlands, construction companies in Russia and China, and software developers in Germany and Russia. The threat actor has added new malware to its arsenal, such as SkinnyD, xDll, and a Python backdoor. The group's activity has increased, possibly due to the COVID-19 pandemic, as many employees are working from home on personal computers without corporate security tools. The threat actor uses various techniques for initial access, execution, persistence, defense evasion, credential access, discovery, collection, and command and control. They have been linked to other attacks and use a variety of network indicators for their operations. The report provides detailed analysis of the threat actor's infrastructure, tools, techniques, and procedures.





Report 22

Summary:
- Threat actor: APT 41
- Region: Asia
- Operating sector: Technology
- Type of company targeted: ASUS, a popular laptop manufacturer
- Date: June to at least November 2018
- Evidence of capability: Used stolen digital certificates to sign legitimate binaries, altered ASUS software to inject malicious code, targeted specific victims in Asia with surgical precision
- Novelty of tools and techniques: Used backdoor injection through ASUS Live Update Utility, compromised supply chain, used advanced modular approach to remain undetected
- Connection to previous incidents: Linked to BARIUM APT, known for ShadowPad and CCleaner incidents
- Other vendors in Asia also targeted with similar methods and techniques.





Report 23

Summary:
APT 41, a threat actor of Chinese origin, targeted TeamViewer in an undisclosed breach discovered in 2016. The attack utilized the Winnti backdoor, but no data theft was detected. TeamViewer removed potential backdoors and enhanced security measures post-attack. The threat actor behind the breach is likely part of the Winnti Umbrella group, known for targeting online game projects and software vendors. The attack was not disclosed to users due to the lack of data compromise. The threat actor's capability to evade detection and use novel techniques like the Winnti backdoor showcases their advanced capabilities. The attack was not connected to previous account hacks reported in 2016. The threat actor's focus on stealing technical trade secrets aligns with their previous targets in the software and gaming sectors. The attack highlights the importance of unique passwords and two-factor authentication to prevent unauthorized access attempts. The threat actor's association with the Winnti Umbrella group indicates a sophisticated and persistent cyber threat.





Report 24

Summary:
The report by CYFIRMA on APT 41 traces the origins of the threat actor back to the early 2000s, linking it to the reformed Chinese military. The threat actor, led by Tan Dailin, evolved from a hacking group to APT41, with a history of targeted attacks and espionage campaigns. APT41's activities included 0-day exploits, cybercrime sprees, and the use of modular malware like ShadowPad, a descendant of PlugX. The report highlights the group's transition from passion-driven hacking to state-sponsored cyber operations for both profit and espionage. The tools used by APT41, such as GinWui/NCPH, PlugX, and ShadowPad, demonstrate a progression in capabilities and techniques, with a focus on agility, distribution, and control. The report provides insights into the threat actor's evolution and its ties to the Chinese military, shedding light on their motivations and operations.

Date of Publication: 2022-07-13

Region: Not specified

Operating Sector: Not specified

Type of Company of Victims: Not specified





Report 25

Summary:
The threat actor known as SparklingGoblin, a member of the Winnti family, has been identified by ESET researchers as using a new undocumented modular backdoor called SideWalk. This backdoor was used in a recent campaign targeting a computer retail company based in the USA. SparklingGoblin has been active since mid-2020, targeting organizations globally with a focus on the academic sector. The group has used Cloudflare workers as a C&C server and Google Docs as a dead drop resolver. SideWalk, similar to CROSSWALK, is a modular backdoor that can dynamically load additional modules and handle communication behind a proxy. The threat actor exhibits similarities in tools and techniques with the Winnti Group, but has been tracked separately due to differences in modus operandi. The report provides detailed technical analysis of SideWalk's capabilities, including its encryption methods, network activity, and command and control functionalities. The report also highlights the architectural and functional similarities between SideWalk and CROSSWALK, suggesting they may be coded by the same developers. The report includes IoCs, MITRE ATT&CK techniques used by SparklingGoblin, and indicators of compromise for further investigation. The operation time window is from mid-2020 to 2021.





Report 26

APT 41, a threat actor known as the Winnti Group, has been active since at least 2012 and has targeted high-profile supply-chain attacks against the video game and software industry. Recently, a previously undocumented backdoor targeting Microsoft SQL Server 11 and 12, named skip-2.0, was discovered by ESET researchers. This backdoor allows attackers to maintain a discreet foothold inside compromised organizations by connecting stealthily to MSSQL accounts using a magic password that hides connections from logs. The backdoor, attributed to the Winnti Group, is the first MSSQL Server backdoor to be publicly documented. The backdoor exhibits novel techniques such as using a custom packer, VMProtected launcher, and hooking functions in sqllang.dll to bypass authentication and maintain stealth. The backdoor allows unauthorized access to MSSQL databases, enabling data manipulation and destruction. The Winnti Group's arsenal, including skip-2.0, shows similarities in tools and techniques, indicating a sophisticated and persistent threat actor. The report was published on October 21, 2019, by ESET researchers.





Report 27

Summary:
In November 2019, the Winnti Group targeted universities in Hong Kong using a new variant of the ShadowPad backdoor and Winnti malware. The group, active since 2012, is known for high-profile supply-chain attacks in the video game and software industries. The campaign was highly targeted, with campaign identifiers and C&C URLs containing the universities' names. The threat actor used novel techniques such as DLL side-loading and a simpler launcher for ShadowPad. The Winnti malware was also found on machines at the universities. The attack took place during civic protests in Hong Kong, indicating a politically motivated campaign. The Winnti Group's capabilities were demonstrated through the use of multiple modules in the ShadowPad backdoor. The threat actor's persistence and data exfiltration techniques were also highlighted. The report was published on January 31, 2020, by ESET researchers.





Report 28

Summary:
- Threat actor: APT41
- Region: China
- Operating sector: Wide range including nation-state governments, software development companies, computer hardware manufacturers, telecommunications providers, social media companies, and video game companies
- Novelty of tools and techniques: APT41, known for web-facing applications, has shifted focus to mobile devices with advanced Android surveillanceware named WyrmSpy and DragonEgg. These malware use modules to hide malicious intentions and avoid detection. They were first reported in October 2020 and January 2021, with the latest example detected in April 2023. The malware have sophisticated data collection and exfiltration capabilities, with DragonEgg masquerading as third-party apps like Telegram. APT41's connection to WyrmSpy and DragonEgg was established through overlapping Android signing certificates and C2 infrastructure links to Chengdu 404. The malware request extensive device permissions and use additional payloads for surveillance functionality.
- Date: July 19, 2023
- Source: Lookout Threat Intelligence

Malformed report.





Report 29

Summary:
The threat actor APT 41, also known as SparklingGoblin, has been identified as the group behind the development and deployment of a Linux variant of the SideWalk backdoor. This variant was used against a Hong Kong university in February 2021, a target previously compromised by SparklingGoblin during student protests in May 2020. The group's tactics, techniques, and procedures (TTPs) overlap with APT41 and BARIUM, utilizing loaders, backdoors, and tools like Korplug and Cobalt Strike. SparklingGoblin targets organizations in East and Southeast Asia, with a focus on the academic sector. The Linux variant of SideWalk, named StageClient, shares similarities with the Specter RAT and is attributed with high confidence to SparklingGoblin. The threat actor's capability is evidenced by the use of advanced encryption methods, network protocols, and evasion techniques in the Linux variant, showcasing their evolving toolset and operational sophistication. The report provides detailed technical analysis and IoCs for further investigation.


