
Report 1

The report provides insights into the operations of the Lazarus Group, a threat actor known for disruptive cyber attacks. The group has targeted various industries, including financial institutions like a Bangladeshi bank, and has expanded into cryptocurrency attacks using RATANKBA malware. Lazarus employs a variety of tools and tactics, such as DDOS attacks, wipers with time-based triggers, and misdirection techniques like false flags and backdoor commands in Romanized Russian. The group also uses protectors for their tools and anti-forensics techniques to cover their tracks. Organizations are advised to ensure network security, update systems regularly, and consider multilayered security solutions like Trend Micro™ Deep Discovery™ and Trend Micro™ Office Scan™ to defend against Lazarus and similar threats. The report was published on January 25, 2018, by Trend Micro.





Report 2

Summary:
The Lazarus Group, also known as Hidden Cobra or Labyrinth Chollima, conducted a series of cyberattacks on the Korean peninsula on June 25, coinciding with the anniversary of the Korean War. The attacks, including DDoS attacks and hard disk wiping, were attributed to the DarkSeoul gang and Trojan.Castov. The DarkSeoul gang has been responsible for multiple high-profile attacks against South Korea over the past four years, demonstrating a pattern of destructive payloads and coordinated attacks on historically significant dates. The gang's methods include the use of legitimate third-party patching mechanisms, specific encryption and obfuscation techniques, and command-and-control structures. While nation-state attribution is challenging, South Korean media reports suggest the attackers may be linked to North Korea. The DarkSeoul gang's technical sophistication and financial support enable them to carry out politically motivated cybersabotage attacks on organizations in South Korea. The Castov DDoS attack, involving Trojanized applications and compromised servers, showcases the group's novel techniques in conducting cyber operations. The threat actor's capability to execute high-profile and damaging attacks over several years sets them apart in the realm of cyber threats.





Report 3

Summary:
On April 11th, 2023, Mandiant conducted an interim assessment on the 3CX network and product, attributing the intrusion to a cluster named UNC4736 with a North Korean nexus. The threat actor infected targeted 3CX systems with TAXHAUL malware on Windows, utilizing unique cryptographic keys for decryption to hinder analysis. They also deployed a MacOS backdoor named SIMPLESEA for communication via HTTP. The threat actor achieved persistence on Windows through DLL side-loading and utilized command and control infrastructure including domains like azureonlinecloud[.]com. The tools and techniques used by the threat actor, such as unique key decryption and DLL side-loading, demonstrate advanced capabilities. The novelty of the malware variants and infrastructure used by the threat actor indicates a sophisticated and evolving threat landscape. The victims targeted were likely in the telecommunications sector, given the nature of the 3CX product.





Report 4

Summary:
The APT trends report for Q1 2021 by Kaspersky highlights significant findings in the cybersecurity landscape. The report discusses the SolarWinds supply-chain attack, the HAFNIUM actor exploiting Microsoft Exchange zero-days, and a campaign targeting governmental entities in Russia using Exchange zero-day exploits. It also covers activities by threat actors like Kazuar, Gamaredon, Sandworm, and various APT groups targeting different regions and industries. Novel tools and techniques, such as the FourteenHi malware family and the EdwardsPheasant backdoors, were discovered. The report also mentions Lazarus group's campaigns targeting security researchers and defense industries using zero-day vulnerabilities. Overall, the report provides insights into evolving threat actor capabilities and tactics observed during the first quarter of 2021.





Report 5

Summary:
The report discusses the activities of APT actors, specifically the Lazarus Group, Hidden Cobra, and Labyrinth Chollima, targeting journalists and media organizations. The threat actors, believed to be state-aligned, have been observed since early 2021 using various techniques such as web beacons for reconnaissance and sending malware to gain access to networks. The focus on media by APTs is to gather sensitive information, spread disinformation, or influence political atmospheres. Evidence shows sustained efforts by threat actors aligned with China, North Korea, Iran, and Turkey targeting journalists and media personnel. The novel techniques used include customized phishing emails, credential harvesting campaigns, and posing as journalists to engage targets. The report highlights the importance of vigilance and verifying sources to prevent falling victim to APT attacks. The operations occurred between January 2021 and March 2022, with a resurgence of targeting observed in 2022. The threat actors have shown a pattern of evolving their tactics to suit current events and political environments.





Report 6

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, launched a new campaign targeting a software vendor through the exploitation of vulnerabilities in high-profile software. The attack involved the use of the SIGNBT malware, which demonstrated a high level of sophistication and employed advanced evasion techniques. The threat actor utilized the LPEClient tool for victim profiling and payload delivery, showcasing their capability to execute targeted attacks. The campaign involved the creation of a loader process to establish persistence on compromised systems and the delivery of additional malware variants that execute in memory without touching the disk. The Lazarus Group's activities transcend geographic boundaries and industry sectors, showcasing sophisticated methods and unwavering motivations. The campaign was detected in October 2023 and highlights the threat actor's persistence and determination in infiltrating and maintaining control over victim systems.





Report 7

Malformed report.





Report 8

Summary:
The Lazarus Group, also known as Hidden Cobra or Labyrinth Chollima, has been identified as the threat actor behind the deployment of a new backdoor named Vyveva. This backdoor was used in an attack against a freight logistics company in South Africa, with evidence suggesting targeted deployment. The backdoor communicates with its C&C server via the Tor network and features capabilities for file exfiltration, timestomping, and gathering information about the victim computer. The attack, discovered in June 2020, indicates an intent for espionage. Vyveva shares code similarities with older Lazarus samples, leading to a high-confidence attribution to the Lazarus APT group. The backdoor's components include an installer, loader, and main payload, with the installer creating a service for persistence and storing configuration in the registry. The backdoor's functionality includes 23 commands for various operations, with the use of encryption and Tor services. The attack demonstrates Lazarus's extensive malware arsenal and geographical targeting, highlighting the group's capabilities in cyber espionage. The report provides technical analysis and indicators of compromise related to the Vyveva backdoor. (Date: June 2020, Operation Time Window: December 2018 - April 2021)





Report 9

Summary:
The Lazarus Group, also known as Hidden Cobra, conducted Amazon-themed campaigns in the Netherlands and Belgium in the autumn of 2021. The attacks involved spearphishing emails containing malicious Amazon-themed documents targeting an aerospace company employee in the Netherlands and a political journalist in Belgium. The attackers used a set of malicious tools, including the first recorded abuse of the CVE-2021-21551 vulnerability affecting Dell DBUtil drivers. This tool disabled security solutions on compromised machines using novel techniques against Windows kernel mechanisms. Additionally, Lazarus deployed their fully featured HTTP(S) backdoor known as BLINDINGCAN. The complexity of the attack indicates a large, organized team behind Lazarus, known for high-profile incidents like the Sony Pictures hack and WannaCry outbreak. The attacks were attributed to Lazarus based on specific modules, code-signing certificates, and intrusion approaches consistent with previous campaigns. The tools used in the attack showcased advanced capabilities and novel techniques, highlighting Lazarus' expertise in cyberespionage, cybersabotage, and financial gain pursuits. The report provides detailed technical analysis and IoCs for further investigation.





Report 10

Summary:
The Lazarus threat group, also known as Hidden Cobra and Labyrinth Chollima, has been active since 2009, primarily targeting Korea but expanding to defense, advanced technology, and finance sectors globally since 2016. They use spear phishing and supply chain attacks, disguising malware as legitimate programs. Recent attacks involved exploiting vulnerabilities in Korean financial security software and web security software. The group uses a variety of backdoors, with Volgmer being used since 2014 and Scout downloader since 2022. Volgmer encrypts configuration data in the registry, while Scout downloads and executes malware in memory. The threat actor employs anti-forensic techniques like timestomping and file deletion. The report provides detailed analysis of Volgmer and Scout malware variants, including their operation mechanisms and communication protocols. The threat actor's capability and use of novel techniques make them a significant cybersecurity concern.





Report 11

Summary:
The report discusses the evolution of the TrickBot group from a banking malware to a sophisticated, universal, module-based crimeware solution targeting corporations. TrickBot's success lies in its automation, decentralization, and integration capabilities, allowing it to offer cybercrime-as-a-service. The report highlights the emergence of the Anchor project, a new addition to TrickBot's modules, which integrates APT tools and techniques, bridging the gap between crimeware and APT operations. The Anchor project is attributed to the Lazarus Group, an APT group associated with North Korea, showcasing the convergence of cybercrime territories. The report emphasizes the novelty and sophistication of the tools and techniques used by TrickBot, marking a significant shift in the cybercrime landscape. The operation time window is not specified in the report.

Malformed report.





Report 12

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been targeting Korean companies related to national defense, satellites, software, and media press since approximately a year ago. They have been utilizing anti-forensic techniques to evade detection and hinder forensic investigations. The group has been employing data hiding, artifact wiping, and trail obfuscation techniques to conceal their malicious activities. One of their notable tactics includes modifying timestamps of files to match legitimate Windows files, aiming to evade timeline analysis. The Lazarus Group's malware operates by encrypting files and disguising them within system folders to avoid detection by security products. This group's meticulous approach to covering their tracks has been observed in recent incidents, with other APT groups also adopting similar anti-forensic techniques. The report was published on February 23, 2023, by the AhnLab ASEC analysis team.





Report 13

Malformed report.





Report 14

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, is a notorious hacking group responsible for the theft of $81 million from the Central Bank of Bangladesh in 2016. Operating in South-East Asia and Europe, they target financial institutions, casinos, software developers for investment companies, and crypto-currency businesses. Their modus operandi involves breaching a bank's system, establishing a foothold, conducting internal reconnaissance, and deploying malware to steal money. The group has been active since 2009, with attacks in at least 18 countries. They invest in new variants of malware to evade security solutions, with the latest samples detected in March 2017. Kaspersky Lab has successfully detected and blocked their malware, urging organizations to scan for Lazarus malware and report intrusions to law enforcement. The threat actor's capability and persistence pose a significant risk to targeted businesses worldwide.





Report 15

Summary: CoinsPaid, an Estonian crypto-payments service provider, reported a cyber attack on July 22, 2023, resulting in the theft of $37,200,000 worth of cryptocurrency, blaming the North Korean hacking group Lazarus. The attack was sophisticated and financially motivated, with evidence pointing to Lazarus as the perpetrator. CoinsPaid's response included fortifying systems and minimizing impact, with assistance from various entities in the investigation. The incident follows a similar $60,000,000 cryptocurrency heist on Alphapo, also attributed to Lazarus, indicating a trend of targeting cryptocurrency payment processors. Previous attacks by Lazarus include thefts from Atomic Wallet, Harmony Horizon, and Axie Infinity, totaling millions of dollars. The company expects to fully offset the revenue hit and rebound swiftly, maintaining service delivery without disruptions.





Report 16

Summary:
The report from JPCERT/CC on January 20, 2021, highlights the tools commonly used by the Lazarus group, also known as Hidden Cobra. The threat actor utilizes Windows commands and tools for lateral movement, information theft, and creating backdoors in infected networks. The tools mentioned include AdFind, SMBMap, Responder-Windows, XenArmor Email Password Recovery Pro, XenArmor Browser Password Recovery Pro, WinRAR, TightVNC Viewer, ProcDump, tcpdump, and wget. These tools are used for various purposes such as collecting information from Active Directory, extracting credentials from email clients and browsers, and creating backdoors using VNC and other applications. The report emphasizes that these tools are widely available and commonly known, making them difficult for anti-virus software to detect. The evidence presented in the report showcases the capability of the Lazarus group in utilizing these tools for malicious activities. The report does not specify a particular region or operating sector of the victims targeted by the threat actor.





Report 17

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, discovered by the Threat Analysis Group on February 10, 2022, exploited a remote code execution vulnerability in Chrome, CVE-2022-0609. The two North Korean government-backed attacker groups, Operation Dream Job and Operation AppleJeus, targeted U.S.-based organizations in news media, IT, cryptocurrency, and fintech industries. The campaigns used the same exploit kit, with evidence of active deployment starting on January 4, 2022. The attackers employed novel techniques, including serving hidden iframes triggering the exploit kit and using unique IDs in email campaigns to enforce a one-time-click policy. The exploit kit contained multiple stages and components, with safeguards to protect their exploits, such as AES encryption and specific timing for serving the iframe. The attackers made multiple attempts to use the exploit even after the vulnerability was patched on February 14, emphasizing the importance of applying security updates promptly. The Threat Analysis Group shared their findings to raise awareness and improve user protections.





Report 18

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, a North Korea-based hacking group, was planning a massive phishing attack disguised as COVID-19 relief efforts against the US, UK, Japan, Singapore, India, and South Korea. The threat intelligence and cybersecurity platform company CYFIRMA uncovered this plan, targeting over five million individuals and businesses, including small, medium, and large enterprises. The hackers planned to send phishing emails from spoofed Ministry of Manpower email accounts offering additional payments to employees. The campaign was set to launch on June 20, 2020, with evidence showing detailed plans for a global phishing campaign impersonating government agencies and trade associations. The hackers were planning to set up phishing sites within 24 hours, using various email templates impersonating government departments and business associations. The use of phishing attacks, especially during the COVID-19 pandemic, highlights the Lazarus Group's capability and the novelty of their techniques in targeting multiple countries and sectors.





Report 19

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, continues to target cryptocurrency businesses, with a focus on financial gain. Their tactics, techniques, and procedures have evolved to avoid detection, including the ability to target macOS. Evidence shows that Lazarus has been active since at least November 2018, utilizing PowerShell for Windows systems and macOS malware. The threat actor is well-organized, using custom PowerShell scripts to communicate with C2 servers and execute commands. They distribute malware through carefully crafted documents, with a focus on South Korean businesses. The group uses different servers for hosting malware and C2 scripts, with servers located in various regions. Lazarus has expanded its attacks to macOS, indicating a shift towards targeting Apple products. The threat actor continues to develop new ways to evade detection and stay under the radar longer. The report advises caution for cryptocurrency and technological startup industries, recommending the use of antivirus software and avoiding suspicious software installations. The group's malware samples show a variety in terms of compiled code, targeting both 32-bit and 64-bit Windows platforms. The report highlights the overlap of current campaigns with previous HWP-based attacks and emphasizes the importance of staying vigilant against Lazarus's evolving tactics. The report was published on March 26, 2019, by Kaspersky's Global Research and Analysis Team (GReAT).





Report 20

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, targeted South Korea and the US in a cyber-attack that paralyzed important government offices in both countries. The attack, suspected to be carried out by North Korean hackers, targeted websites of key organizations in South Korea, including the Blue House, the defense ministry, and major banks. The White House, Pentagon, and New York Stock Exchange in the US were also targeted but managed to deflect the attack. The attack was believed to be a form of cyber-warfare, with speculation on whether North Korea launched it themselves or had assistance. The attack involved the use of malicious software that infected PCs to repeatedly visit targeted websites, with a significant number of infected PCs located in South Korea. The attack was sophisticated and well-prepared, possibly involving the collaboration of a certain organization or state. The incident highlighted the capability of the threat actor to launch coordinated cyber-attacks on government websites, showcasing their advanced tools and techniques. The attack occurred on July 8, 2009, and raised concerns about the involvement of North Korea or China in such cyber operations.





Report 21

Summary:
- Threat Actor: Lazarus Group, Hidden Cobra, Labyrinth Chollima
- Region: South Korea
- Operating Sector: Banking Networks and Broadcasters
- Date: March 20, 2013
- Evidence of Capability: Paralyzed three major South Korean banks and two largest broadcasters' networks, causing disruptions in ATM withdrawals and news broadcasting.
- Novelty of Tools and Techniques: Used malware named "DarkSeoul" to evade antivirus products and render computers unusable, more complex than a denial of service attack.
- Suspected Origin: Some experts suspected North Korea, but the attack originated from an Internet provider address in China.
- Response: South Korean government raised alert against cyberattacks and initiated investigations to determine the source.
- Impact: Banks reported temporary blockages in Internet banking servers and erasure of files, while broadcasters' computers were frozen.
- Conclusion: The attack was sophisticated, possibly state-sponsored, and aimed to send a clear message without causing physical harm.





Report 22

Malformed report





Report 23

Malformed report.





Report 24

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, operating under the name DEV-0139, targeted the cryptocurrency industry in a sophisticated attack. The threat actor, posing as representatives of a cryptocurrency investment company, gained the trust of targets in Telegram chat groups before sending a weaponized Excel file named "OKX Binance & Huobi VIP fee comparision.xls." This file contained a malicious macro that initiated a series of activities, including dropping a backdoor into the system. The threat actor used advanced techniques like DLL side-loading and DLL proxying to evade detection. The attack also involved the delivery of a payload through a fake application called CryptoDashboardV2. The threat actor demonstrated a deep understanding of the cryptocurrency industry and targeted smaller companies in addition to larger ones. Microsoft Defender Antivirus and Microsoft Defender for Endpoint provide detection and mitigation against the threat components associated with this attack. The report includes indicators of compromise, MITRE ATT&CK techniques used, and detection details for defenders to identify and respond to similar attacks. The operation time window for this attack was from October 2022 onwards.





Report 25

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been targeting victims in the cryptocurrency sector in the region of North Korea. The threat actor has demonstrated advanced capabilities through the use of novel tools and techniques. In a recent operation on November 27, 2023, the group utilized macOS RustBucket droppers to deliver KandyKorn payloads, showcasing a sophisticated multi-stage attack. The KandyKorn campaign targeted blockchain engineers of a crypto exchange platform using Python scripts to deliver a backdoor RAT named 'KandyKorn'. The DPRK threat actors have been observed mixing components from different campaigns, indicating a high level of adaptability and sophistication. The use of SwiftLoader droppers to deliver KandyKorn payloads highlights the group's evolving tactics. The threat actor's reuse of infrastructure and shared components allows for a wider understanding of their activity and the discovery of new indicators of compromise. SentinelOne customers are protected from both KandyKorn and RustBucket malware, showcasing the effectiveness of their cybersecurity platform.





Report 26

Summary:
The Lazarus Group, a threat actor sponsored by the North Korean government, exploited unpatched Zimbra devices to steal data from medical and energy sector researchers. The campaign, named "No Pineapple," operated through the end of 2022 targeting public and private sector research organizations. The threat actors exfiltrated approximately 100GB of data without causing disruptive cyber operations. The campaign was attributed to Lazarus Group with high confidence by analysts due to an overlap in techniques and a misstep by the threat actors. The motivation behind the campaign was assessed to be for intelligence benefit. The novel use of a known Zimbra bug showcases the capability of the threat actor in conducting sophisticated cyber espionage operations. (Date: February 7, 2023)





Report 27

Summary:
The Lazarus Group, also known as Hidden Cobra or Labyrinth Chollima, has been identified as the threat actor behind the Dacls Dual platform RAT targeting both Windows and Linux platforms. The Dacls RAT is a fully functional, covert program with modular functions, using TLS and RC4 double-layer encryption for C2 communication. The Lazarus Group's use of the CVE-2019-3396 N-day vulnerability to spread the Dacls Bot program has been observed. The Dacls RAT includes plugins for command execution, file management, process management, network testing, C2 connection, and network scanning. The C2 communication involves SSL connection, authentication process, and RC4 encryption. The Dacls RAT also utilizes a Reverse P2P plugin for C2 connection proxy, a technique commonly used by the Lazarus Group. The threat actor's infrastructure includes hardcoded C2 IPs and URLs. The Dacls RAT poses a significant threat to Confluence users and requires monitoring and blocking of related IPs, URLs, and domain names. The report was published on December 17, 2019, by the 360 Netlab Blog - Network Security Research Lab.





Report 28

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, conducted a supply chain attack involving a modified CyberLink installer, impacting over 100 devices in Japan, Taiwan, Canada, and the United States. The threat actor, Diamond Sleet, a North Korea-based group, utilized a legitimate CyberLink application installer signed with a valid certificate to distribute a second-stage payload. Microsoft attributes this activity to Diamond Sleet with high confidence, noting their focus on espionage, data theft, and financial gain. The threat actor used trojanized open-source and proprietary software to target organizations in IT, defense, and media sectors. The tools and techniques used by Diamond Sleet, such as the LambLoad downloader/loader, show sophistication and evasion tactics, including time-limited execution and checks to avoid security product detection. Microsoft has taken steps to mitigate the risk, including notifying affected customers and adding the malicious certificate to the disallowed list. The threat actor's novel approach and capabilities highlight the need for enhanced cybersecurity measures in the targeted sectors. (Report date: November 22, 2023)





Report 29

Malformed report





Report 30

Summary:
- Threat actor: Lazarus Group, suspected to be linked to North Korea
- Date: September 15th, 2023
- Target: CoinEx cryptocurrency exchange, with $31 million stolen
- Evidence: Elliptic analysis linked the CoinEx hack to Lazarus Group through blockchain transactions
- Novelty: Lazarus Group used mixing of funds from separate hacks, focusing on centralized cryptocurrency platforms
- Capability: North Korean groups have stolen over $340.4 million in cryptocurrency in 2023
- Techniques: Increasing use of Russia-based exchanges for money laundering
- Shift in targets: Lazarus Group targeting centralized platforms due to improved security in DeFi services
- Region: North Korea
- Operating sector: Cryptocurrency exchange

Overall, the Lazarus Group, suspected to be linked to North Korea, has been involved in a series of cryptocurrency thefts, with the most recent being the CoinEx hack. The group has shown capability in stealing significant amounts of cryptocurrency and using novel techniques such as mixing funds from separate hacks. They have also shifted their focus to centralized platforms due to improved security in decentralized finance services. The evidence points to North Korean groups using Russia-based exchanges for money laundering.





Report 31

Summary:
The report tracks the activities of the Lazarus group, a Korean-speaking threat actor, focusing on the DeathNote campaign. The group has targeted cryptocurrency businesses, defense contractors, and IT companies in Europe and South Korea. The threat actor has evolved its tactics over the years, using decoy documents, Trojanized applications, and new infection vectors like Trojanized PDF readers. The Lazarus group has been observed using backdoors, loaders, and stealer malware to compromise victims and exfiltrate data. The report provides indicators of compromise and attribution to the Lazarus group. The threat actor operates in the GMT+08 or GMT+09 time zone and leaves Korean comments in their scripts. The report emphasizes the need for organizations to stay vigilant and implement strong security measures against this skilled adversary.





Report 32

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been actively targeting Apple's macOS platform with four distinct families of malware since at least January 2020. The threat actor has shown capability in developing and evolving macOS malware, including trojanized One-Time Password apps, trojanized CryptoTrading apps, backdoors, and lightweight backdoor binaries. The tools and techniques used by the threat actor, such as the MATA framework and the use of libcurl, indicate a high level of sophistication and customization for the macOS platform. The threat actor has been vigilant in keeping up with macOS updates and has demonstrated a variety of malicious activities, including stealing cryptocurrency and maintaining backdoors. The latest activity, such as the emergence of WatchCat and MediaRemote malware, shows ongoing development and adaptation by the threat actor. The rapid iteration and diversity of malware samples suggest a deep investment in macOS-specific malware development by the Lazarus Group. The SentinelOne platform provides protection against the malware samples discussed in the report. (Report date: July 27, 2020)





Report 33

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been identified as the threat actor behind the Dtrack malware. The Dtrack malware was initially discovered as ATMDtrack, a banking malware targeting Indian banks, which evolved into a spy tool capable of keylogging, browser history retrieval, and remote access operations. The malware was designed to target financial institutions and research centers in India, with similarities to the DarkSeoul campaign attributed to the Lazarus group dating back to 2013. The Dtrack samples revealed the reuse of old code by the threat actor, indicating their capability to adapt and evolve their tools. The last activity of Dtrack was detected in September 2019, showcasing the ongoing operations of the Lazarus group. The malware's design included encrypted payloads, process hollowing shellcode, and a variety of executables for spying purposes. The droppers also contained a remote access Trojan (RAT) allowing for various operations on the victim's host. The Lazarus group's activity demonstrates their advanced capabilities in malware development and their use of similar tools for financially-motivated and espionage attacks. The report advises organizations to strengthen their network security policies, password policies, and utilize traffic monitoring software and antivirus solutions to mitigate the threat posed by the Lazarus group. The report provides IoCs for detection and further analysis.





Report 34

Summary:
The Lazarus Group, a North Korean elite hacking organization, has recently intensified its operations, conducting five confirmed attacks against crypto entities since June 3rd, with the latest targeting CoinEx on September 12th, resulting in a theft of approximately $54 million. The group has been responsible for stealing almost $240 million in cryptoassets from various companies in the past 104 days. Elliptic analysis confirms the group's involvement in these attacks, with evidence of fund laundering and consolidation. Lazarus has shifted its focus from decentralized to centralized services, possibly due to increased security measures in decentralized platforms and the susceptibility to social engineering in centralized exchanges. Elliptic continues to monitor these incidents and update their systems with new information on stolen funds. The Lazarus Group's use of social engineering and novel tactics in targeting centralized services poses a significant threat to the crypto industry.





Report 35

Malformed report.





Report 36

Summary:
- Threat actor: Lazarus Group, Hidden Cobra, Labyrinth Chollima
- Region: North Korea
- Operating sector: Cryptocurrency ecosystem
- Victims: Crypto businesses, financial institutions, public sector
- Evidence of capability: Stolen over $2 billion in cryptocurrencies in 30+ attacks in the last five years, with $200 million stolen in 2023 alone.
- Novelty of tools and techniques: Evolved targets, techniques, and money laundering patterns in a multi-chain crypto landscape, targeting DeFi ecosystem and cross-chain bridges, using phishing, supply chain attacks, and infrastructure hacks.
- Date: June 3, 2023 - North Korean hackers targeted users of Atomic Wallet, stealing approximately $100 million worth of cryptocurrency through phishing or supply chain attacks.
- Operation time window: ongoing attacks and evolving laundering methodologies.
- Tools used: TRM Forensics software for visualizing stages of the hack, TRM Phoenix for tracing funds across blockchains.
- Importance of blockchain intelligence in following stolen funds and evolving tools for investigators to combat North Korea's attacks on the crypto ecosystem.





Report 37

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been identified as a highly prolific advanced threat actor targeting the defense industry and developing supply chain attack capabilities. Operating since at least 2009, Lazarus has been involved in large-scale cyber-espionage and ransomware campaigns, with recent activities observed in June 2021. The threat actor utilized the multi-platform MATA framework to target Windows, Linux, and macOS systems for cyber-espionage purposes. Notably, Lazarus has been expanding its capabilities by targeting a South Korean think tank and an IT asset monitoring solution vendor, showcasing a novel approach to supply chain attacks. The group's use of updated tools like the DeathNote cluster and BLINDINGCAN malware indicates a continuous evolution in their tactics. The report highlights the need for vigilance and defense efforts against such sophisticated threat actors. Date: October 26, 2021.





Report 38

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, is a threat actor that has been active since at least 2009, with evidence suggesting possible activity as far back as 2007. The group has targeted organizations in the U.S., South Korea, and South Korean manufacturing industries, with a focus on cyber espionage. They have been linked to attacks using malware such as Dozer, Koredos, Jokra, Castov, and Destover, which have been used in distributed denial of service (DDoS) attacks, data theft, and destruction of computer systems. The group gained widespread attention in 2014 for the high-profile attack on Sony Pictures Entertainment, where they used the Backdoor.Destover malware to wipe infected systems. In 2016, Lazarus was behind the sophisticated SWIFT attacks that resulted in the theft of $81 million from the Bangladesh Central Bank. In 2017, they were linked to the WannaCry ransomware attacks that affected organizations worldwide. Despite their long history and evolving tactics, Lazarus has shown signs of sloppiness in their attacks, indicating a degree of inconsistency in their operations. The group's capabilities and use of novel tools and techniques make them a persistent and audacious threat in the cybersecurity landscape.





Report 39

Summary:
The Lazarus Group, also known as Hidden Cobra, targeted Japanese organizations with malware named VSingle and ValeforBeta. VSingle is an HTTP bot that executes arbitrary code and communicates with C2 servers using obfuscation techniques. ValeforBeta, developed in Delphi, uploads and downloads files and communicates with C2 servers via HTTP POST requests. The threat actor used tools like 3Proxy, Stunnel, and Plink for communication. The report, dated March 22, 2021, highlights the capabilities of Lazarus in targeting Japanese organizations with novel tools and techniques. The threat actor's use of authentication proxies and encryption keys demonstrates advanced capabilities in cyber operations. The report warns organizations to be vigilant against communication with C2 servers listed in the report.





Report 40

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been identified as a threat actor targeting financial institutions using a remote controller tool called RATANKBA. The group has been active since late 2016 and has evolved its tactics by using a PowerShell script instead of traditional PE executable forms. Evidence suggests that the group has targeted victims in India and neighboring countries, particularly smaller organizations or individual users, rather than larger enterprises. The threat actor's capabilities include using a variety of lure documents to deliver the malware, communicating with a command-and-control server, and manipulating victim hosts through a remote controller tool. The attackers have shown interest in cryptocurrencies like Bitcoin and Ant Share. Defending against RATANKBA requires multilayered security strategies, network scanning, employee education on social engineering, and endpoint hardening. The Lazarus Group's operations have been notable for their scale and impact, making them a significant threat in the cybersecurity landscape.





Report 41

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, conducted Operation Dream Magic, a watering hole attack exploiting the MagicLine vulnerability. The attack targeted companies and institutions through a malicious link inserted in a news website article, utilizing C2 on vulnerable Korean websites. AhnLab coordinated a response involving multiple teams to address the threat, including analysis, technical support, and collaboration with national agencies. The operation showcased the group's capability to exploit vulnerabilities and conduct targeted attacks for financial gain. The use of the MagicLine vulnerability and the collaboration with national agencies marked a novel approach by the threat actor. The report was posted on October 17, 2023, providing insights into the attribution of the operation to the Lazarus Group.





Report 42

Summary:
The threat actor Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, is believed to be state-sponsored by North Korea. They have been active since 2007 and are motivated by financial gain to circumvent sanctions. Lazarus Group has targeted various sectors globally, including aerospace, defense, energy, finance, government, healthcare, media, shipping, and technology. They have used a wide range of tools and techniques, including malware like WannaCry, DarkSeoul, and AppleJeus, as well as various RATs and ransomware. Notable operations include the Sony Pictures breach in 2014 and the WannaCry ransomware attack in 2017. The group has been linked to multiple cryptocurrency-related attacks and supply chain compromises. Counter operations against Lazarus Group have been conducted by various entities, including sanctions and indictments by the US and EU. The group continues to pose a significant threat to organizations globally.





Report 43

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, exploited the Log4Shell vulnerability (CVE-2021-44228) in April 2022 to distribute NukeSped malware. The attack targeted companies in Korea using VMware Horizon products without security patches, mainly in the virtual desktop solutions sector for remote working and cloud infrastructure operations. NukeSped is a backdoor malware variant developed with C++ and uses encryption algorithms like DES and RC4 for communication with C&C servers. The malware can perform keylogging, take screenshots, and execute file and shell tasks. Additionally, the attackers installed INFOSTEALER malware to collect sensitive information like passwords and email account details. The Lazarus Group's use of NukeSped and Jin Miner malware strains demonstrates their advanced capabilities and novel techniques in exploiting vulnerabilities and conducting targeted attacks.





Report 44

Summary:
The Lazarus Group, also known as Hidden Cobra, conducted a recruitment-themed cyber attack targeting a pharmaceutical company in September 2020. The threat actors used malicious documents with job offers to deliver malware through macros, leading to reconnaissance activities on compromised computers. The group utilized unique tools like Trojan-Downloader Agamemnon and Trojan-Backdoor CommsCacher for remote command execution. The attack was attributed to Lazarus Group, a North Korean government-sponsored APT group known for cyber espionage. The threat actors employed phishing tactics through various platforms and created a fake General Dynamics Mission Systems website. The group demonstrated a high level of preparedness and individualized approach to compromising hosts. The incident was investigated by experts from Positive Technologies and involved tracking the group's activities in a similar geographical segment. The attack showcased a range of MITRE TTPs used by the Lazarus Group, indicating their advanced capabilities and sophisticated techniques. The report provides detailed IOCs and insights into the group's tactics, techniques, and procedures.

Date: September 2020
Region: Global
Operating Sector: Pharmaceutical
Type of Company: Pharmaceutical Company
Novelty: Unique tools and techniques used by the Lazarus Group for cyber attacks.





Report 45

Summary: The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been targeting Windows IIS web servers, as confirmed by the AhnLab Security Emergency Response Center (ASEC) on May 23, 2023. The threat actor utilizes the DLL side-loading technique to run malware, specifically using the msvcr100.dll and Wordconv.exe files to execute malicious commands. This technique allows them to establish a foothold, steal certificates, and perform lateral movement within the victim's network. The Lazarus Group has been continuously changing the names of the normal processes used in their attacks to evade detection. Companies are advised to proactively monitor abnormal process execution relationships to prevent information exfiltration and lateral movement by the threat group. The group is considered highly dangerous and actively launches attacks worldwide, primarily targeting poorly managed or vulnerable web servers. The AhnLab products detect and block the malware used by the Lazarus Group in these attacks.





Report 46

Summary:
The Lazarus Group, also known as Hidden Cobra, has been identified as a threat actor controlled by the North Korean government. They have developed a new malware called Hoplight, capable of securely connecting to a control server and uploading stolen files. The malware consists of nine files, with seven acting as proxy applications to mask traffic and two creating secure connections. The group has a history of financial crime rather than espionage, with a focus on helping North Korea generate revenue. The Lazarus Group has been known for high-profile attacks, such as the 2014 Sony Pictures breach. The malware package allows for remote control and spyware activities, including reading and writing files, modifying processes, and connecting to remote hosts. The group typically uses spear-phishing techniques to distribute malware. The report was published on April 10, 2019.





Report 47

Summary:
The Lazarus threat group, also known as Hidden Cobra and Labyrinth Chollima, has been targeting Windows Internet Information Service (IIS) web servers for malware distribution. The group, believed to be nationally funded, uses the watering hole technique for initial access, exploiting vulnerabilities in INISAFE CrossWeb EX V6. They have been observed attacking IIS servers and using them to distribute malware, including the JuicyPotato privilege escalation malware. The threat actor has been active since at least May 2023, with ongoing attacks against unpatched systems. The Lazarus group's novel use of malware strains generated by IIS web servers and privilege escalation tools like JuicyPotato demonstrates their advanced capabilities. The report was posted on July 24, 2023, by AhnLab Security Emergency Response Center (ASEC).





Report 48

The Lazarus threat group, also known as Hidden Cobra and Labyrinth Chollima, has been actively exploiting vulnerabilities in Korean finance security solutions, including INISAFE CrossWeb EX, MagicLine4NX, VestCert, and TCO!Stream. The group has been targeting Korean companies using these software solutions, prompting ASEC to issue warnings and recommendations for updating to the latest versions. The threat actor utilizes novel techniques such as the BYOVD technique to disable anti-malware programs and propagate malware internally via the TCO!Stream vulnerability. ASEC has reported the vulnerabilities to the Korea Internet & Security Agency (KISA) and provided information on affected versions and resolved versions for each software. The threat actor's malware, behavior, and URLs have been detected and blocked by AhnLab using various aliases. The activity of the Lazarus group was observed from April 26, 2022, to June 11, 2023, with a focus on exploiting new vulnerabilities and targeting Korean companies in the finance sector.





Report 49

Summary:
The Lazarus Group, known for its financial motivations and targeting the cryptocurrency industry, recently Trojanized a DeFi application in November 2021 to deliver malware. The malware is a full-featured backdoor with capabilities to control compromised victims, showing overlaps with other Lazarus tools. The threat actor exclusively used compromised web servers in South Korea for this attack, with a multi-stage infrastructure common in Lazarus operations. The malware's backdoor creation involved disguising as Google Chrome and communicating with C2 servers using RC4 encryption and base64 encoding. The Lazarus Group's attribution is highly confident due to similarities with previous malware clusters like CookieTime. The group's interest in the cryptocurrency industry remains strong, as seen in previous attacks on DeFi wallet programs. The report provides indicators of compromise and MITRE ATT&CK mapping for the analyzed activity.





Report 50

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been observed targeting defense contractors with malicious documents potentially aimed at engineering job candidates and employees in classified roles in the U.S. and Europe. The campaign, active in spring 2021, involves renaming system utilities to obfuscate their activities. The threat actor has a history of using DDoS botnets, keyloggers, RATs, and drive wiper malware. Recent documents impersonate defense contractors like Boeing and BAE systems, containing macro malware that evolves with each target. The group uses techniques to evade detection, such as encoding files and injecting malicious payloads into legitimate processes. The C&C communication is done through compromised domains like shopweblive[.]com. The campaign showcases Lazarus' consistent tactics and procedures, emphasizing the importance of monitoring their activities. The report provides detection methods and associated indicators for defenders to use. Date: July 6, 2021. Region: U.S. and Europe. Operating Sector: Defense contractors. Type of Company: Engineering job candidates and employees.





Report 51

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, targeted entities related to COVID-19 research in a campaign discovered on December 23, 2020. The threat actor attacked a pharmaceutical company and a government health ministry using different malware clusters, including wAgent and Bookcode. The Lazarus Group deployed sophisticated malware with unique tactics, techniques, and procedures (TTPs) in each attack, showcasing their capability to adapt and evolve. The malware clusters used by the threat actor showed novel infection schemes and persistence mechanisms, indicating advanced technical capabilities. The attribution of the activity to the Lazarus Group was based on similarities in malware naming schemes, infection techniques, and post-exploitation methods. The threat actor's interest in COVID-19-related intelligence highlights the need for heightened cybersecurity measures in organizations involved in vaccine research and crisis handling.





Report 52

Summary: The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, was linked to a $60 million cryptocurrency heist on the Alphapo payment processing platform on July 23, 2023. The attack targeted a centralized crypto payment provider for gambling sites, e-commerce subscription services, and other online platforms. The theft included various cryptocurrencies drained from hot wallets, facilitated by a leak of private keys. The Lazarus Group, a North Korean threat actor with ties to the government, has been previously linked to other high-profile heists. They typically use fake job offers to compromise employees of crypto firms and gain unauthorized access to execute attacks costing millions of dollars. Evidence suggests that the attackers likely stole private keys in this attack, allowing access to the wallets. The involvement of the Lazarus Group in the Alphapo hack has not been independently confirmed at this time.





Report 53

Summary:
The Lazarus Group, a North Korean state-sponsored hacking group, targeted security researchers with a trojanized version of the IDA Pro reverse engineering application. The pirated version of IDA Pro contained malicious DLLs that, when installed, created a new task in the Windows Task Scheduler to launch a remote access trojan called NukeSped. This allowed threat actors to steal files, take screenshots, log keystrokes, and execute commands on the researcher's device. The malware was attributed to Lazarus activity, with evidence linking it to previous attacks by the group. Lazarus has a history of targeting security researchers with backdoors and remote access trojans, using tactics like fake online personas and zero-day exploits. The trojanized IDA Pro installer was discovered in Q1 2020 and has been distributed since then.





Report 54

The Lazarus Group, also known as Hidden Cobra or Labyrinth Chollima, has been identified targeting an Israeli defense company, expanding their attack horizon. The threat actor has shown capabilities in targeting high-profile organizations in the defense sector. The use of novel tools and techniques by the Lazarus Group indicates a sophisticated level of cyber expertise. The operation time window for this specific attack was not provided in the report. The targeting of a defense company in Israel suggests a focus on strategic industries and potentially sensitive information. The report highlights the ongoing threat posed by the Lazarus Group to critical infrastructure and national security.





Report 55

Summary:
The Lazarus Group, also known as Hidden Cobra, was likely behind recent attacks at an online casino in Central America and other targets in late 2017. The group utilized its malicious toolset, including the disk-wiping malware KillDisk, which was executed on compromised machines. The Lazarus Group's toolset is broad and includes custom tools as well as projects available from GitHub or provided commercially. The attackers used a TCP backdoor, a session hijacker, a loader/installer, and variants of KillDisk in the attack on the online casino. The KillDisk variants detected in the casino's network shared code similarities with variants used in previous Lazarus attacks. The attackers also used tools like Browser Password Dump and a modified version of Mimikatz. The attack involved multiple steps and tens of protected tools, indicating a large-scale effort by the attackers. The use of Lazarus tools in the attack suggests a high level of sophistication and capability by the threat actor. The report was published on April 3, 2018, by ESET Research.





Report 56

Summary:
The Lazarus Group targeted a Spanish aerospace company by luring employees with trojanized coding challenges. ESET researchers discovered a new backdoor named LightlessCan used by Lazarus, indicating a high level of sophistication. The attackers obtained initial access through a spearphishing campaign via LinkedIn, masquerading as a Meta recruiter. The attack involved multiple execution chains delivering payloads via DLL side-loading, with the most notable being the LightlessCan backdoor. This new backdoor represents a significant advancement compared to its predecessor, BlindingCan, mimicking native Windows commands for stealthier execution. The attack was attributed with high confidence to Lazarus, particularly to its Operation DreamJob campaign. The final goal of the attack was cyberespionage, targeting aerospace companies aligning with North Korea's interests. The attack showcased novel techniques and tools, indicating the evolving capabilities of the Lazarus Group. The operation time window was not specified in the report.





Report 57

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been identified as a threat actor targeting big game companies in Europe. In two separate incidents between March and May 2020, they used a ransomware family called VHD and a spreading utility reminiscent of APT groups. The ransomware encrypts files using AES-256 and RSA-2048, with unorthodox cryptography techniques. The Lazarus Group also deployed a backdoor called MATA, indicating a high level of sophistication. The group's operations deviate from typical cybercrime ecosystems, suggesting they may be operating independently. The VHD ransomware is believed to be owned and operated solely by Lazarus. The group's motives and profitability remain unclear, but their capabilities and novel techniques pose a significant threat to targeted companies.





Report 58

Summary:
The Lazarus Group conducted a supply-chain attack in South Korea using a novel approach to deliver malware via legitimate South Korean security software and stolen digital certificates. The attack leveraged the WIZVERA VeraPort software, commonly used by South Korean internet users, to deliver Lazarus malware from compromised websites. The attackers used illegally obtained code-signing certificates to sign the malware samples, camouflaging them as legitimate software. The attack required specific preconditions to be successful, limiting its scope. The Lazarus Group's toolset is extensive, with past attacks targeting various sectors, including banks, defense contractors, and casinos. The attack was attributed to the Lazarus Group based on community agreement, toolset characteristics, victimology, network infrastructure, and eccentric approach. The malware analysis revealed similarities with previous Lazarus operations, showcasing a multi-stage deployment process. The attack highlights the increasing trend of supply-chain attacks and the need for enhanced security measures to prevent such incidents. The report was published on November 16, 2020, by ESET researchers.





Report 59

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, targeted macOS users dreaming of jobs in the crypto sector in their 'Operation In(ter)ception' campaign. The threat actor, linked to North Korea, has been using lures for job offers since at least 2020, including targeting aerospace and defense contractors. The campaign involved distributing macOS malware through decoy PDF documents advertising positions at cryptocurrency exchanges like Coinbase and Crypto.com. The malware used in the campaign showed evidence of advanced capabilities, including the use of universal Mach-O binaries capable of running on Intel and M1 Apple silicon machines. The threat actor showed little effort to encrypt or obfuscate the binaries, possibly indicating short-term campaigns. SentinelOne customers were protected against the malware variants used in this campaign. The Lazarus Group's continued targeting of individuals involved in cryptocurrency exchanges suggests a combined effort to conduct espionage and cryptocurrency theft. The campaign was observed in September 2022.





Report 60

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been linked to a Linux malware campaign targeting Linux users in Operation DreamJob, using social engineering techniques with fake job offers. The Linux malware, named SimplexTea, was distributed through an OpenDrive cloud storage account, marking the first public mention of this North Korea-aligned threat actor using Linux malware. This discovery also confirmed with high confidence that Lazarus was behind the 3CX supply-chain attack on the international VoIP software developer and distributor, 3CX. The attack, discovered in March 2023, involved trojanized desktop applications for Windows and macOS, enabling attackers to download and run arbitrary code on compromised machines. The attack was attributed to Lazarus by multiple security researchers, with evidence linking the attack to the threat actor's known techniques and infrastructure. The Linux malware used in the Operation DreamJob campaign, along with the novel techniques and tools employed, further solidified the connection between Lazarus and the 3CX supply-chain attack. The attack timeline suggests that the threat actor had access to 3CX's network since late 2022, highlighting the persistence and capabilities of the Lazarus Group. The report provides detailed technical analysis of the Linux malware and its similarities with known Lazarus tools, reinforcing the attribution to the threat actor. The use of Linux malware in this operation showcases Lazarus's ability to target all major desktop operating systems, including Windows, macOS, and Linux. The report concludes that supply-chain attacks like the one on 3CX can have devastating impacts, emphasizing the importance of cybersecurity measures to prevent such incidents.





Report 61

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been identified by Qualys Threat Research to be conducting a new campaign targeting the defense sector, specifically job applicants for Lockheed Martin Corporation in the United States. This campaign, named "LolZarus," incorporates novel techniques such as using lolbins in phishing lures, with some lolbins being used for the first time by the group. The threat actor utilizes sophisticated methods like control flow hijacking, shellcode execution, and beaconing to maintain persistence and exfiltrate data. The campaign shows significant overlap with previous Lazarus activities, indicating a consistent modus operandi. The group's evolving capabilities and use of lesser-known techniques highlight their adaptability and persistence in the cyber threat landscape. The report provides indicators of compromise (IOCs) and MITRE ATT&CK mappings for organizations to detect and respond to similar threats. The operation time window for this campaign is from December 23, 2022, to the present.





Report 62

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been identified as the threat actor behind the MATA multi-platform targeted malware framework. The framework targets Windows, Linux, and macOS operating systems and consists of components such as loader, orchestrator, and plugins. The threat actor has used this framework aggressively since April 2018 to infiltrate corporate entities globally, including victims in Poland, Germany, Turkey, Korea, Japan, and India. The malware framework was used for cybercrime activities, including stealing customer databases and distributing ransomware. The MATA framework is linked to the Lazarus APT group, as evidenced by unique filenames and configuration data similarities with previous Lazarus variants. The threat actor's evolving capabilities and cross-platform targeting make MATA a significant threat that requires continuous monitoring to protect against. The report was published on July 22, 2020, by Kaspersky's Global Research and Analysis Team (GReAT).





Report 63

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been observed exploiting the TeamCity CVE-2023-42793 vulnerability since early October 2023. Microsoft identified two North Korean threat actors, Diamond Sleet and Onyx Sleet, utilizing unique sets of tools and techniques following successful exploitation of the vulnerability affecting JetBrains TeamCity server. Diamond Sleet, known for espionage and data theft, deployed the ForestTiger backdoor and conducted credential dumping via LSASS memory. On the other hand, Onyx Sleet targeted defense and IT services organizations, creating a new user account named krtbgt and deploying a proxy tool named HazyLoad for persistent access. Microsoft recommends applying updates released by JetBrains, investigating indicators of compromise, and using Microsoft Defender Antivirus for protection. The threat actors exhibited novel techniques such as DLL search-order hijacking and user account creation, indicating a high level of sophistication in their operations. Date of publication: October 18, 2023.





Report 64

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, a sophisticated North Korean APT, conducted a new campaign on January 18, 2022, targeting victims with spear phishing attacks using job opportunity-themed malicious documents. The threat actor leveraged a novel technique by using the Windows Update client and GitHub as a command and control server. The attack involved control flow hijacking through KernelCallbackTable, shellcode injection, and code injection to achieve persistence and execute malicious payloads. The malware components included DLLs responsible for injecting additional modules, dropping malicious files, and communicating with the C2 server via GitHub. The threat actor used GitHub for C2 communication, a rare choice that makes detection challenging. The campaign targeted individuals seeking job opportunities at Lockheed Martin, a known tactic of Lazarus. The malware used in the campaign was attributed to Lazarus based on infrastructure overlap, attack techniques, and previous campaigns. The report provides detailed technical analysis of the attack chain, malware components, and IOCs. The campaign demonstrated Lazarus' capability to update its toolset and evade security mechanisms with new techniques. 

Date: January 27, 2022

Region: North Korea

Operating Sector: Defense industry

Type of Company: Lockheed Martin (American global security and aerospace giant)

Evidence of Capability: Novel use of Windows Update client and GitHub for C2 communication, control flow hijacking through KernelCallbackTable, shellcode injection, and code injection techniques.

Novelty of Tools and Techniques: Unusual use of Windows Update client, GitHub as C2 server, control flow hijacking through KernelCallbackTable, and custom hashing method for resolving APIs.

Malware Components: stage1_winword.dll, stage2_explorer.dll, drops_lnk.dll, stage3_runtimebroker.dll, wuaueng.dll, core_module.dll, GetBaseInfo.dll

IOCs: Multiple malicious documents, domains, and payloads used in the campaign.





Report 65

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, conducted a targeted supply chain attack in July 2023, affecting a US-based software solutions entity through a sophisticated spear phishing campaign aimed at JumpCloud, a zero-trust directory platform service. Mandiant attributed these intrusions to UNC4899, a Democratic People's Republic of Korea (DPRK)-nexus actor with a history of targeting companies within the cryptocurrency vertical. The threat actor leveraged JumpCloud to gain initial access to victim environments, targeting MacOS keychains and reconnaissance data associated with executives and internal security teams. The threat actor deployed backdoors such as FULLHOUSE.DOORED and STRATOFEAR, with novel techniques such as using Apple's XProtect Behavioral Service to identify malicious files. The threat actor's operational security fumble revealed the use of Operational Relay Boxes (ORBs) and VPN providers to obscure their source address, with occasional lapses leading to exposure of their true origins. Mandiant assessed the threat actor as UNC4899, a cryptocurrency-focused group under the RGB, with shared infrastructure and tooling among multiple North Korean groups. The campaign exemplifies the cascading effects of supply chain attacks targeting service providers to compromise downstream victims, with a focus on the cryptocurrency industry. Mandiant predicts continued development of MacOS malware by DPRK cryptocurrency units to target high-value individuals within the cryptocurrency industry.





Report 66

Summary:
- Threat actor: Lazarus Group, Hidden Cobra, Labyrinth Chollima
- Region: North Korea
- Date: June 24, 2022
- Victims: Blockchain company Harmony
- Evidence: $100 million hack, laundering through Tornado Cash, targeting DeFi services, compromising cryptographic keys, automated laundering process
- Novelty: Use of blockchain bridges, social engineering attacks, consistent interest in DeFi services
- Tools and Techniques: Compromising multi-signature wallets, automated laundering processes, targeting APAC-based targets
- Collaboration: Harmony working with FBI, offering $10 million bug bounty
- Trend: Increase in blockchain bridge attacks, association with North Korean state-sponsored hacking campaigns
- Source: The Record Media

Overall, the Lazarus Group, with ties to North Korea, orchestrated a $100 million hack on blockchain company Harmony, utilizing novel techniques such as compromising cryptographic keys and automated laundering processes through Tornado Cash. The group's consistent interest in DeFi services and targeting of APAC-based targets indicate a sophisticated and persistent threat actor. Collaboration with law enforcement agencies and the trend of blockchain bridge attacks highlight the evolving landscape of cyber threats.





Report 67

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, linked to North Korea, stole $600 million in cryptocurrency in 2023, with potential for a total of $700 million. They were responsible for almost a third of all funds stolen in crypto attacks last year, despite a 30% reduction from 2022. The DPRK's hacking methods involve compromising private keys and seed phrases to transfer assets to North Korean-controlled wallets. They then convert the assets to hard currency using high-volume OTC brokers. North Korea's money laundering tactics have evolved to evade international law enforcement, shifting from Tornado Cash and ChipMixer to the BTC service Sinbad. With nearly $1.5 billion stolen in the past two years, North Korea's hacking capabilities require continuous vigilance and innovation from businesses and governments. Despite advancements in cybersecurity and international collaboration, further disruptions are expected in 2024 from this prolific cyber-thief.





Report 68

Summary:
- Threat actor: Lazarus Group, Hidden Cobra, Labyrinth Chollima
- Region: North Korea
- Operating sector: Online retail
- Victims: Large US retailers, international fashion chain Claire's, Italian modeling agency, vintage music store from Tehran, family-run book store from New Jersey
- Date: May 2019 onwards
- Evidence of capability: North Korean state-sponsored hackers intercepted online payments from American and European shoppers by planting payment skimmers in online stores. They reused infrastructure from previous operations and used distinctive malware code patterns.
- Novelty of tools and techniques: North Korean hackers extended their criminal activities to digital skimming, a crime dominated by other hacker groups. They used legitimate sites as money mules and developed a global exfiltration network to sell stolen assets on dark web markets.
- Techniques used: Spearphishing attacks to obtain passwords, injection of malicious scripts into store checkout pages, interception of credit card data during transactions, and use of unique exfiltration methods.
- Conclusion: Sansec found evidence linking North Korean state-sponsored actors to large-scale digital skimming activities since at least May 2019. The threat actor has multiple independent links to previously documented North Korean hacking operations.





Report 69

Summary:
- Threat actor: Lazarus Group, Hidden Cobra, Labyrinth Chollima
- Region: North Korea
- Operating sector: Israel's defense sector
- Type of company: Multinational companies like Boeing, McDonnell Douglas, and BAE
- Evidence of capability: Sent fake job offers through LinkedIn, impersonated CEOs, used WhatsApp for communication, infected "several dozens" of companies globally
- Novelty of tools and techniques: Used fake job offers for espionage operations, similarities to previous North Korean hacking campaigns
- Date: August 12, 2020
- Operation time window: Ongoing
- No harm or disruption reported in Israel's defense sector
- McAfee-identified malware detected in Europe and the U.S.





Report 70

Summary:
The Lazarus Group, a North Korean threat actor, conducted a two-month-long cyber espionage campaign named 'No Pineapple!' between August and November 2022. The campaign targeted organizations in various sectors, including medical research, healthcare, chemical engineering, energy, defense, and a leading research university. Evidence suggests that Lazarus used new infrastructure with IP addresses, a new version of the Dtrack info-stealer malware, and a new version of the GREASE malware. The threat actor exploited Zimbra vulnerabilities to breach networks, deployed tunneling tools to bypass firewalls, and utilized custom tools like Dtrack and GREASE to steal data. Mistakes made by Lazarus, such as communication with a North Korean IP address and errors in executing commands, allowed for attribution of the campaign to the group. WithSecure's report highlights the continued intelligence gathering efforts of Lazarus, showcasing their capability to exfiltrate large amounts of data from high-profile victims.





Report 71

Summary:
- Threat Actor: Lazarus Group
- Region: APAC
- Operating Sector: Crypto Crime
- Victims: Users of Atomic Wallet
- Date: June 6, 2023
- Elliptic's analysis links Lazarus Group to the theft of $35 million in cryptoassets from Atomic Wallet users.
- The stolen funds were traced using Elliptic's software, with evidence pointing to Lazarus Group based on laundering techniques and specific services used.
- This marks the first major crypto theft publicly attributed to Lazarus Group since a $100 million exploit in June 2022.
- Elliptic continues to monitor the situation and provide updates on the stolen funds.
- The threat actor's capability is demonstrated through sophisticated laundering techniques and use of specific services for illicit activities.





Report 72

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been targeting banks, financial companies, and cryptocurrency exchanges globally. In a recent attack investigated by Kaspersky Lab, the threat actor used a trojanized cryptocurrency trading application to infect a victim's computer with the Fallchill malware. This attack marks the first time the Lazarus Group has developed malware for macOS, expanding their capabilities to target non-Windows platforms. The attackers used sophisticated techniques, including encryption and communication with a C2 server, to collect and exfiltrate victim information. The infrastructure used in the attack, including domain registration and hosting services, showed signs of anonymity and suspicious activity. The Fallchill malware used in the attack has been previously attributed to the Lazarus Group, indicating a consistent pattern of behavior. This incident highlights the importance of verifying the trustworthiness of third-party software and the need for vigilance in cybersecurity practices.





Report 73

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been identified as one of the most active and prolific APT actors targeting the cryptocurrency business sector. In their Operation AppleJeus Sequel, they have enhanced their capabilities by developing homemade macOS malware and employing multi-stage infection procedures for Windows users. The threat actor has shown novelty in their attack methodology by carefully delivering next-stage payloads without touching the disk and using authentication mechanisms. The Lazarus Group has targeted victims in the UK, Poland, Russia, and China, with a focus on cryptocurrency businesses. The threat actor has continuously evolved their malware, changing frameworks and encryption methods to avoid detection. The attack on cryptocurrency businesses is expected to continue and become more sophisticated. The campaign has utilized fake websites and malicious applications to compromise victims, showcasing a high level of operational security and persistence.





Report 74

Malformed report.





Report 75

Malformed report





Report 76

Summary:
- Threat actor: Lazarus Group, Hidden Cobra, Labyrinth Chollima
- Region: Global
- Operating sector: Technology industry
- Type of company: Technology firms, blockchain, cryptocurrency, online gambling, and cybersecurity sectors
- Date: July 18, 2023
- Evidence of capability: Low-volume social engineering campaign targeting personal accounts of technology industry employees using repository invitations and malicious npm package dependencies. Associated with a group supporting North Korean objectives targeting cryptocurrency and blockchain-related organizations.
- Novelty of tools and techniques: Impersonation of developers/recruiters on GitHub and social media platforms, use of fake personas, delivery of first-stage malware through malicious npm packages, and direct delivery of malicious software on messaging platforms. Use of domains for second-stage malware downloads and publication of malicious packages only when extending fraudulent repository invitations.
- Actions taken: Suspension of npm and GitHub accounts associated with the campaign, filing of abuse reports with domain hosts, and publication of indicators for awareness and prevention. Recommendations for affected individuals to review security logs, be cautious of social media solicitations, examine dependencies, and contact cybersecurity departments if targeted.





Report 77

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, was identified as the threat actor behind a large-scale phishing attack on NFT users in the encryption ecosystem. The attack targeted Crypto and NFT users using nearly 500 different domain names, with the earliest registration date traced back to 7 months ago. The threat actor utilized unique phishing traits commonly used by North Korean hackers, such as recording visitor data and saving it to external sites. Additionally, the hackers deployed various attack scripts and txt files with statistical information on victims, including access records and wallet information. The hackers also utilized multiple tokens like WETH, USDC, DAI, and UNI to induce victims to perform phishing operations. The threat actor was able to receive a total of 1,055 NFTs and approximately 300 ETH in profit through their sales. The investigation revealed a collaboration between North Korean hackers and Eastern Europe in phishing NFT users. The report was published on December 24, 2022, by SlowMist.





Report 78

The Lazarus Group, also known as Hidden Cobra or Labyrinth Chollima, targeted victims in the private industry sector, specifically focusing on financial and manufacturing companies. The threat actor, identified as UNC2970 from North Korea, utilized a novel technique called Bring Your Own Vulnerable Device (BYOVD) to further enable their operations. Evidence of the threat actor's capability was demonstrated through the use of advanced anti-analysis techniques and the creation of a utility named LIGHTSHOW, which manipulated kernel data-structures to evade detection. The tools used by the threat actor, such as LIGHTSHIFT and LIGHTSHOW, represented an advancement in DPRK's capabilities and showcased a concerted effort towards obfuscation throughout the chain of delivery and execution. The report, dated March 9, 2023, highlighted the threat actor's use of vulnerable drivers like Dell DBUtil 2.3 and ENE Technology drivers to evade detection, indicating a trend towards the abuse of legitimate but vulnerable drivers by threat actors. The report also mentioned Mandiant's efforts to detect and mitigate BYOVD techniques, as well as the discovery of a 0day vulnerability in a vulnerable driver used by the threat actor.





Report 79

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has resurfaced with a cyber espionage campaign similar to the Dark Seoul attack in South Korea in 2013. The TDrop2 malware variant, discovered in June 2015, targets the transportation and logistics sector in Europe through spear-phishing emails. The malware, disguised as legitimate software, uses process hollowing and encryption techniques to download and execute payloads, allowing attackers to modify C2 URLs, download malware, and perform reconnaissance on infected hosts. The malware's behavior and functionality show similarities to the original Dark Seoul/Operation Troy toolset, indicating a potential connection to the previous attacks. The attackers' use of compromised servers in South Korea and Europe for C2 communication suggests a sophisticated operation. The motives behind the resurgence of the Lazarus Group remain unclear, but monitoring of the situation continues.





Report 80

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, is believed to be run by the North Korean government and primarily motivated by financial gain to circumvent sanctions. They have been active since 2013, with notable attacks on South Korean broadcasters, financial institutions, Sony Pictures, and the widespread WannaCry ransomware outbreak in May 2017. Their activities have targeted financial institutions and cryptocurrency exchanges using Trojanized trading apps for both Windows and MacOS. The Lazarus Group's tools include DarkSeoul, Fallchill Trojan, Fastcash, Bitsran, and assorted backdoors for persistence. While their political motivations are focused on regional conflicts, their financial motivations pose a significant risk to organizations. Attribution for their attacks is challenging, making it difficult to predict their next targets. The threat actor's capabilities and novel techniques make them a persistent and evolving threat in the cybersecurity landscape.

Date: March 12, 2019

Region: Global

Operating Sector: Financial institutions, cryptocurrency exchanges

Type of Company: Not specified





Report 81

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been identified by Unit 42 researchers at Palo Alto Networks as responsible for new attack activity targeting individuals involved with United States defense contractors. The threat actors have been reusing tools, techniques, and procedures from previous operations, such as Operation Blockbuster Sequel and Operation Blockbuster. The attacks have targeted English language speakers with decoy documents containing job role descriptions and internal policies from US defense contractors. The weaponized documents have been hosted on compromised systems, with metadata and infrastructure overlaps with previous campaigns. The threat actor's capability is evidenced by the reuse of macro source code, XOR keys, and payloads, as well as the use of fake TLS communications protocol and encoded strings within samples. The threat actor's persistence and continued operations despite public exposure indicate that they are likely to continue launching targeted campaigns. The report was published on August 14, 2017, and the threat actor's activities have been ongoing through July of 2017.





Report 82

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been identified by Unit 42 as the threat actor behind recent malware activities targeting Korean-speaking individuals. The group is linked to the 2014 Sony Pictures Entertainment attack and the 2013 DarkSeoul attacks. The malware used by the Lazarus Group includes malicious Word documents with Korean decoy files that execute Visual Basic for Applications (VBA) macros to drop and run an executable payload. The payload, with a compile timestamp of March 2nd, 2017, establishes persistence on the system and communicates with command and control (C2) servers using a "fake TLS" protocol. The C2 servers mimic legitimate domains like Twitter, Amazon, and Apple. The Lazarus Group's tools and techniques show similarities with previous Operation Blockbuster reports, indicating a consistent modus operandi. The threat actor's capability to create and distribute sophisticated malware demonstrates a high level of expertise and persistence. The recent activity suggests that the Lazarus Group continues to evolve and refine its tactics, posing an ongoing threat to targeted entities. The victims of these attacks are likely in the Korean-speaking region, with evidence suggesting that the threat actors are proficient in both Korean and English languages. The report was published on April 7, 2017, by Unit 42.





Report 83

The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, is a threat actor originating from North Korea, known for conducting criminal hacking for monetary gain. The group has targeted victims in over a hundred and fifty nations, with a focus on financial institutions, cryptocurrency exchanges, and online casinos. Evidence suggests that the group has raked in billions of dollars through various schemes, including A.T.M. heists, bank heists, ransomware attacks, and cryptocurrency thefts. The group's capabilities include offensive and intelligence-gathering cyber weapons, with a focus on financial fraud and money laundering. The group's tools and techniques have shown innovation and sophistication, with a growing emphasis on cryptocurrency-related crimes. The group's operations have been linked to the Korean People's Army and the Reconnaissance General Bureau, showcasing a high level of organization and coordination. The threat actor's activities have raised concerns about national security and the need for enhanced collaboration between government agencies and private security firms to combat cybercrime effectively.





Report 84

Summary:
The Lazarus Group, a North Korean state-sponsored advanced persistent threat (APT) group, has been targeting blockchain companies in the cryptocurrency industry since at least 2020. The group uses social engineering tactics to distribute trojanized cryptocurrency applications to victims, gaining access to their computers and stealing private keys or exploiting security gaps. The group, also known as APT38, BlueNoroff, and Stardust Chollima, has been observed targeting cryptocurrency exchanges, decentralized finance protocols, and individual holders of large amounts of cryptocurrency or valuable non-fungible tokens. The threat actor uses novel tools and techniques, such as the "TraderTraitor" campaign, which involves malicious applications written in cross-platform JavaScript code using the Electron framework. The U.S. government recommends implementing mitigations such as patch management, multifactor authentication, and educating users on social engineering and phishing attempts to protect against these cyber threats. The report was last revised on April 20, 2022.





Report 85

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, a North Korean government-backed entity, targeted security researchers in a hacking campaign. On March 17, 2021, they set up a fake company called "SecuriElite" in Turkey, offering offensive security services. The group used social media profiles and LinkedIn accounts to pose as security researchers and recruiters. While no malicious content was observed on the new website, the group has a history of using browser exploits. Security researchers identified the group using an Internet Explorer 0-day and suspect they have more zero-day vulnerabilities. The threat actor's novel techniques include setting up fake websites and social media profiles to lure victims. The campaign was documented by the Threat Analysis Group on March 31, 2021. The victims targeted were security researchers in the cybersecurity sector.





Report 86

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been identified as the threat actor behind the ongoing VMConnect supply chain attack, with evidence pointing to North Korea. The attack involves malicious Python packages posted to the Python Package Index (PyPI) repository, mimicking popular open-source tools. The threat actor has been linked to previous campaigns attributed to Labyrinth Chollima, an offshoot of Lazarus Group. The malware used in the campaign employs novel techniques such as XOR encryption and hex encoding instead of the traditional Base64 encoding. The threat actor avoids detection by executing malicious payloads only after the package is imported and called by legitimate applications. The campaign targets users of the PyPI repository, with malicious packages like request-plus, requestspro, and tablediter identified. The malware communicates with a command-and-control (C2) server and downloads additional malicious payloads. The campaign has been linked to the Lazarus Group by analyzing code similarities and shared C2 infrastructure. The ongoing VMConnect campaign highlights the need for organizations to enhance their cyber defensive capabilities against software supply chain attacks. The report provides indicators of compromise (IOCs) and emphasizes the importance of detecting and preventing supply chain attacks. The threat actor's tactics include typosquatting, impersonation, and evasion of dynamic application security testing tools. The report concludes by urging organizations to invest in training, awareness, and tools to mitigate the risks posed by software supply chain attacks.





Report 87

Summary:
The Lazarus Group, also known as Hidden Cobra or Labyrinth Chollima, has been detected by Microsoft engaging in cyberattacks targeting security researchers under the campaign named ZINC. The attacks were aimed at pen testers, private offensive security researchers, and employees at security and tech companies. The campaign, attributed with high confidence to ZINC, a DPRK-affiliated and state-sponsored group, utilized various techniques including social media credibility building, sending malicious Visual Studio projects, and a watering hole website with browser exploits. The threat actor used innovative methods like malicious pre-build events in Visual Studio projects to gain execution. The campaign involved the deployment of malware such as Comebacker and Klackring, as well as other tools like an encrypted Chrome password-stealer. The threat actor also attempted to exploit a vulnerability using an old version of the Vir.IT driver. Microsoft Defender for Endpoint provided comprehensive detection coverage for this campaign. The report includes a list of associated indicators of compromise (IOCs) and advanced hunting queries for detection and prevention. The ongoing campaign was reported in January 2021, and Microsoft shared this information to raise awareness in the cybersecurity community.





Report 88

Summary:
The Lazarus Group, also known as Hidden Cobra and Labyrinth Chollima, has been identified as a threat actor named ZINC by Microsoft. ZINC has been observed engaging in social engineering campaigns targeting employees in various sectors such as media, defense, aerospace, and IT services in the US, UK, India, and Russia. The threat actor is a state-sponsored group based in North Korea with objectives including espionage, data theft, financial gain, and network destruction. ZINC has been active since June 2022, utilizing traditional social engineering tactics and weaponizing open-source software like PuTTY, KiTTY, TightVNC, Sumatra PDF Reader, and muPDF/Subliminal Recording installer. The group has successfully compromised multiple organizations and poses a significant threat due to the wide use of the platforms and software they exploit. ZINC's capabilities include the use of custom remote access tools, sophisticated malware like ZetaNile, and strategic social engineering tactics. The threat actor has been observed conducting campaigns from late April to mid-September 2022, targeting individuals through LinkedIn and WhatsApp for malware delivery. Microsoft Defender for Endpoint provides protection against ZINC's tools and malware, and customers are advised to implement security measures like multifactor authentication and educate end-users on preventing malware infections. The report provides indicators of compromise and advanced hunting queries for detection and mitigation of ZINC's activities. The threat actor's novel techniques include the weaponization of SSH clients like PuTTY and KiTTY, as well as trojanizing PDF readers and VNC viewers for malware delivery. The report highlights ZINC's persistence, encryption methods, and C2 communication tactics, emphasizing the need for proactive security measures to counter the threat posed by this sophisticated nation-state actor.





Report 89

Summary:
The Lazarus Group, a threat actor associated with North Korea, targeted the deBridge Finance crypto platform in August 2022 using a phishing email to deliver malware. The attackers used fake PDF and text files to trick employees into launching malicious code, which collected system information and allowed for further stages of the attack. The malware achieved persistence by saving a file in the startup folder and communicated with the attacker's command and control server. The threat actor, known for targeting companies in the blockchain and cryptocurrency sector, has been linked to previous attacks using similar tactics. The Lazarus Group has a history of siphoning cryptocurrency funds, with one notable heist involving $620 million in Ethereum. The attack on deBridge Finance is part of a larger campaign targeting cryptocurrency firms with novel social engineering techniques.


