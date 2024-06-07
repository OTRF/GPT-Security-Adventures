
Report 1

Summary:
The threat actor known as Cycldek, also referred to as Goblin Panda and Conimes, has been active in conducting targeted operations against governments in Southeast Asia over the past two years. The group consists of two operational entities under a mutual quartermaster, utilizing an extensive toolset for lateral movement and information stealing in targeted networks. One of the newly revealed tools, USBCulprit, relies on USB media to exfiltrate victim data, suggesting an attempt to reach air-gapped networks or rely on physical presence for the same purpose. The group has been observed using politically themed RTF documents with 1-day exploits to deliver malware like NewCore RAT. The analysis of the implants affiliated with Cycldek indicates a single actor with different geographical focuses for each cluster of activity. The group's activities show an evolution and persistence in targeting high-profile entities in Southeast Asia. The report provides IOCs for RedCore, BlueCore, and the lateral movement and info-stealing toolset used by Cycldek.





Report 2

Malformed report.





Report 3

Goblin Panda, Cycldek, and Conimes are threat actors primarily targeting entities in Southeast Asia, particularly Vietnam, operating in the defense, energy, and government sectors. They have been active since 2013, with a focus on information theft and espionage. The actors have been observed using malware variants such as PlugX and HttpTunnel. Their tools and techniques include Dropper, PlugX, ProcDump, and others. Notable hacking operations include attacks on airports in Vietnam and government organizations in Southeast Asian countries. The threat actors have shown capability in using new TTPs and have been active in various countries including Cambodia, India, Indonesia, Malaysia, and the USA. The most recent report dates back to 2020.





Report 4

Summary:
- Threat actor: Goblin Panda
- Operating region: Southeast Asia, particularly Vietnam
- Operating sector: Defense, energy, government
- Evidence of capability: Use of malware variants PlugX and HttpTunnel, targeting of entities in Southeast Asia, use of exploit documents with Vietnamese-language lures and themes, targeting of entities in Laos
- Novel tools and techniques: Use of CVE-2012-0158 exploit code, side-loading malware implant tracked as QCRat, use of legitimate executable and side-loading implant Dynamic Link Library (DLL), new implant configuration files stored as a .tlb file
- Date of operation: Renewed activity targeting Vietnam observed last month
- Conclusion: Unlikely that Goblin Panda will abandon efforts to collect intelligence from South East Asian neighbors and businesses operating in the region.





Report 5

Summary:
- Threat actor: Goblin Panda, Cycldek, Conimes
- Region: Vietnam
- Operating sector: Vietnamese organizations
- Date: September 05, 2017
- Evidence of capability: Exploited vulnerability CVE-2012-0158, used decoy documents with politically themed texts, employed DLL hijacking to evade security programs, utilized a rehashed RAT named "NewCore" capable of various malicious activities, compiled on March 16, 2017, and linked to Chinese hacking group 1937CN.
- Novelty of tools and techniques: Used file-less execution of malware, passed C&C information as a parameter, employed XOR encryption for communication, and derived from publicly available backdoor source codes.
- Conclusion: The NewCore RAT, although a rehashed version, effectively evaded AV detection through sophisticated techniques, highlighting the need for patching vulnerabilities and continuous monitoring for such threats.





Report 6

Summary:
A Cycldek-related threat actor was identified in a campaign observed between June 2020 and January 2021, targeting organizations primarily in Vietnam in government, military, health, diplomacy, education, and political sectors. The threat actor utilized a sophisticated toolchain involving FoundCore Loader, FoundCore payload, RoyalRoad documents, DropPhone, and CoreLoader. The malware samples exhibited advanced obfuscation techniques, including opaque predicates and dead code, to evade detection and analysis. The threat actor demonstrated capabilities in remote administration, persistence establishment, and data exfiltration. The campaign showed similarities to the LuckyMouse APT group but also shared code with the Cycldek threat actor, leading to a low-confidence attribution to Cycldek. The threat actor's tactics and tools indicate a significant advancement in sophistication, with interdependent components making analysis challenging. The report highlights the importance of information sharing among researchers to fully understand the threat landscape.


