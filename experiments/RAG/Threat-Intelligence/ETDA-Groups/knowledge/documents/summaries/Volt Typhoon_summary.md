
Report 1

Summary:
The threat actor known as Volt Typhoon targeted government, manufacturing, and critical infrastructure sectors with a critical severity level impact, including data loss and OS and file corruption. Fortinet's analysis of CVE-2023-27997 revealed a heap buffer overflow in SSL-VPN pre-authentication, which was exploited in a limited number of cases. The threat actor utilized tactics like "living off the land" to evade detection and exploited vulnerabilities such as FG-IR-22-377/CVE-2022-40684 for initial access. Fortinet recommends immediate firmware upgrades and ongoing mitigation efforts to prevent exploitation by threat actors like Volt Typhoon. The operation time window for this campaign was not specified in the report.





Report 2

Summary:
- Threat actor: China's Volt Typhoon APT
- Region: United States
- Operating sector: US critical infrastructure, military bases, businesses, and individuals
- Date: July 31, 2023
- Evidence of capability: Malware found in networks controlling communications, power, and water feeding US military bases, potential for disruptive attacks on critical infrastructure, insider breach affecting Air Force and FBI communications
- Novelty of tools and techniques: Use of destructive malware, broader campaign targeting critical systems, potential for disruptive attacks on military response and supply chains
- Concerns: Precursor to military disruption and destructive attacks, difficulty in assessing full footprint of infestation, potential for broader impact on civilian life in the event of conflict.





Report 3

Summary:
The threat actor known as BRONZE SILHOUETTE, also referred to as Volt Typhoon, is a Chinese cyberespionage group targeting U.S. government and defense organizations since 2021. They exhibit a high level of operational security, using preinstalled binaries and defense evasion techniques to avoid detection. The threat actor utilizes web shells for persistence and relies on living-off-the-land binaries for their operations. They have been observed exfiltrating sensitive data, such as AD databases, to external IP addresses. BRONZE SILHOUETTE's use of compromised infrastructure in their C2 proxy network complicates attribution and reduces the likelihood of detection. The group's focus on operational security and adherence to a blueprint indicate a high level of operational maturity. The tactics and techniques employed by BRONZE SILHOUETTE align with those of other state-sponsored Chinese threat groups, suggesting they operate on behalf of the People's Republic of China. The threat actor's tradecraft developments have likely been influenced by increased pressure to avoid public scrutiny of cyberespionage activities. The report covers incidents from June 2021 to June 2022, highlighting the threat actor's capabilities and novel techniques.





Report 4

Summary:
- Threat actor named Volt Typhoon, tracked as VANGUARD PANDA, targeted U.S.-based critical infrastructure entities since mid-2020.
- Used ManageEngine Self-service Plus exploits for initial access, custom webshells for persistence, and living-off-the-land techniques for lateral movement.
- Evidence of familiarity with target environment through reconnaissance commands and specific actions.
- Used webshells masquerading as legitimate files, backdoored Apache Tomcat library for persistence.
- Novelty in using backdoored Apache Tomcat library for persistent access, extensive log clearing, and artifact deletion to hinder forensic analysis.
- CrowdStrike's Falcon Complete MDR contained and remediated the intrusion, providing actionable recommendations for defense.
- Recommendations include indicators to detect VANGUARD PANDA components and YARA rules for detection.
- Collaboration between Falcon Complete, Falcon OverWatch, and CrowdStrike Intelligence for proactive threat hunting and remediation.
- Date: May 24, 2023, with ongoing activity until June 22, 2023.
- Region: U.S.-based critical infrastructure entities.
- Operating Sector: Multiple sectors.
- Type of Company: Critical infrastructure entities.





Report 5

Summary:
The threat actor known as "Volt Typhoon" has been identified by the Black Lotus Labs team at Lumen Technologies as operating a small office/home office (SOHO) router botnet called the KV-botnet. This botnet serves as a covert data transfer network for advanced threat actors and has been active since at least February 2022. The KV-botnet targets devices at the edge of networks, particularly exploiting vulnerabilities in devices like NETGEAR ProSAFE firewalls. The threat actor, identified as a state-sponsored actor based in China known for espionage and information gathering, has been linked to the Volt Typhoon group. The threat actor employs sophisticated techniques, obfuscation methods, and a well-concealed command-and-control framework. The KV-botnet has evolved over time, targeting new device types like IP cameras and engaging in mass exploitation. The threat actor's activities have been observed targeting various sectors, including an internet service provider, telecommunications firms, a U.S. territorial government entity, and a European renewable energy firm. The threat actor's operations have been associated with manual exploitation, scanning activities, and large data transfers. The KV-botnet's tools and techniques are novel, residing completely in-memory, making detection challenging. Lumen Technologies is actively monitoring and mitigating the threat posed by the KV-botnet, collaborating with partners like the Microsoft Threat Intelligence Team. The threat actor's activities are distinct from other known threat groups, and organizations are advised to implement security measures to protect against such threats. The KV-botnet's infrastructure has been null-routed, and IoCs have been shared to enhance threat intelligence and detection efforts. Organizations are encouraged to monitor for IoCs associated with the KV-botnet and similar threats to safeguard their networks. The threat actor's targeting of SOHO devices underscores the importance of regular security updates, patching, and network monitoring to prevent infections. The analysis of the KV-botnet was conducted by Black Lotus Labs, highlighting the evolving nature of cyber threats and the need for proactive cybersecurity measures.





Report 6

Summary:
The threat actor known as Volt Typhoon, also identified as Vanguard Panda and Bronze Silhouette, is a state-sponsored actor based in China focused on espionage and information gathering. Microsoft has detected targeted malicious activity aimed at critical infrastructure organizations in the United States, with a focus on post-compromise credential access and network system discovery. The campaign, active since mid-2021, has targeted sectors such as communications, manufacturing, utility, transportation, and government. The threat actor's behavior suggests a goal of performing espionage and maintaining undetected access for as long as possible. The tools used include FRP, Impacket, and Living off the Land techniques. The campaign's potential impact on critical communications infrastructure between the United States and Asia during future crises is a significant concern. Various reports and investigations have highlighted the threat actor's activities, including compromising Cisco devices and targeting U.S. government and defense organizations. The motivation behind the attacks is information theft and espionage, with observed victims in countries like Australia, India, UK, and the USA. The threat actor's capabilities and novel techniques warrant broader community awareness and enhanced security measures.





Report 7

Summary:
- Threat actor: Volt Typhoon
- Region: United States
- Operating sector: Critical infrastructure organizations
- Type of company: Communications, manufacturing, utility, transportation, construction, maritime, government, information technology, and education sectors
- Evidence of capability: State-sponsored actor based in China focusing on espionage and information gathering, active since mid-2021, targeting critical infrastructure organizations in Guam and the US, using living-off-the-land techniques, maintaining access without detection, routing traffic through compromised small office and home office network equipment, using custom versions of open-source tools for command and control.
- Novelty of tools and techniques: Reliance on living-off-the-land techniques, use of custom versions of open-source tools for C2 channel over proxy, emphasis on stealth, routing traffic through compromised network equipment.
- Operation time window: Since mid-2021
- Source: Microsoft Security Blog, May 24, 2023.





Report 8

Summary: The threat actor known as "Volt Typhoon" has been identified for compromising 30% of Cisco RV320/325 devices in a span of 37 days. The report does not specify the region or operating sector of the victims targeted. The evidence of the threat actor's capability lies in their ability to compromise a significant number of devices within a short timeframe. The tools and techniques used by Volt Typhoon are considered novel, as they were able to exploit vulnerabilities in Cisco devices efficiently. The report does not mention a specific date or operation time window for these attacks.


