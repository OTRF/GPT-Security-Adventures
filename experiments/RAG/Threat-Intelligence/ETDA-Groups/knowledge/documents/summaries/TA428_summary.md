
Report 1

Summary:
A threat actor, identified as the Chinese-speaking APT group LuckyMouse, targeted government agencies and a National Data Center of Mongolia in East Asia. The attack involved planting backdoors and keyloggers to gain long-term access to government networks. The threat actor used a variety of tools, including Polpo and LuckyBack backdoors, indicating an updated toolset. The attack was carried out through a vulnerable company providing services to the agencies and email spear-phishing with a weaponized document. The threat actor utilized tactics consistent with previous reports of LuckyMouse but also employed previously undocumented tactics. The attack involved the use of various tools for cyber-espionage, lateral movement, and data exfiltration. The operation time window was during the summer of 2020. The report provides detailed information on the tools and techniques used by the threat actor, including RATs, backdoors, UAC bypass tools, port scanners, and password dumpers. The threat actor also utilized encryption methods to hide IP addresses in C&C responses. The report includes indicators of compromise and MITRE ATT&CK techniques used in the attack.





Report 2

Summary:
- Threat actor TA428, linked to China, has been targeting IT companies in Russia and Mongolia.
- The group uses infrastructure, tactics, and victim organizations that indicate continued engagement in intrusion activities in the region.
- Evidence of the threat actor's capability includes the use of malware such as Royal Road, Poison Ivy, and PlugX, as well as novel techniques like DLL hijacking and backdoor installation.
- The group has been active since at least 2013 and targets organizations of high strategic value to China.
- TA428 has been attributed to campaigns targeting defense and aviation organizations in Russia and Mongolia.
- Indicators of compromise related to the campaign have been identified.
- The threat actor uses spoofed domains and lure documents to target victims.
- The group's activities align with previous reports by Proofpoint and NTT Security.
- The report was published on March 17, 2021, by Recorded Future's Insikt Group.





Report 3

Summary:
- Threat actor TA428 conducted a targeted APT campaign named "Operation LagTime IT" targeting government information technology agencies in Eastern Asia, specifically focusing on government agencies overseeing various sectors.
- The threat actors utilized spear phishing emails with malicious RTF attachments exploiting Microsoft Equation Editor vulnerability CVE-2018-0798 to deliver custom malware named Cotx RAT.
- TA428 also used Poison Ivy payloads with overlapping command and control infrastructure with Cotx RAT campaigns.
- The Cotx RAT malware was persistent, utilizing AES-192 encryption, DLL search-order hijacking, and side-loading techniques for execution.
- The Poison Ivy malware communicated with a specific IP address and shared passwords across different campaigns.
- The threat actors demonstrated persistence and a focus on high-value targets, indicating a continuation of targeted activity aligned with Chinese state interests.
- The operation showed operational and tactical resemblance to previous APT activities by TA428, indicating a known threat actor with advanced capabilities.
- The campaign targeted government agencies responsible for IT, scientific research, domestic affairs, foreign affairs, and political processes.
- The threat actors utilized novel techniques and tools, including custom malware and spear phishing tactics, to compromise victims in the region.
- The operation was ongoing from early 2019, with evidence of targeting and delivery methods observed in the report.

Date: July 24, 2019

Region: Eastern Asia
Operating Sector: Government Information Technology Agencies
Type of Company: Government Agencies

Evidence of Capability: Custom malware, spear phishing, encryption techniques, DLL search-order hijacking, side-loading, persistent targeting, and shared infrastructure with previous APT activities.





Report 4

TA428, also known as Panda or ThunderCats, is a threat actor originating from China that has been active since 2013. The threat actor has targeted government agencies, industrial plants, design bureaus, and research institutes in countries such as Afghanistan, Belarus, Mongolia, Russia, Ukraine, and East Asia. TA428 has been involved in information theft and espionage, using novel techniques such as malicious RTF document attachments in spear phishing emails. The threat actor has collaborated with other groups like Emissary Panda and LuckyMouse in operations like Operation StealthyTrident. TA428 has been observed using a variety of tools including Cotx RAT, Poison Ivy, and PlugX. Notable hacking operations include Operation "LagTime IT" in 2019, where they exploited a Microsoft Equation Editor vulnerability to deliver malware, and Operation "StealthyTrident" in 2020, where they compromised the Able Desktop chat software used by government agencies in Mongolia. The threat actor continues to target industrial enterprises and public institutions, showcasing their persistence and capability in carrying out targeted attacks.





Report 5

Summary:
In January 2022, Kaspersky ICS CERT detected a targeted attack on industrial enterprises and public institutions in East European countries, Afghanistan, and other regions. The attackers used phishing emails with malicious code exploiting the CVE-2017-11882 vulnerability to gain initial access. They deployed multiple backdoors, including a new one, for redundant communication and data theft. Lateral movement was achieved using the Ladon hacking utility and standard Windows utilities. The attackers hijacked domain controllers to gain full control of systems. The attack was attributed to APT TA428 based on TTP overlaps and previous research. The attackers exfiltrated sensitive data to servers in China. The campaign is ongoing, and organizations are advised to enhance security measures. The full report with technical details is available on the Kaspersky ICS CERT website.





Report 6

Malformed report





Report 7

Summary:
- Threat actor 'TA428' targeted Russian government organizations, including the FSB, using the 'Mail-O' malware in May 2021.
- Initial speculation pointed towards Western governments as the culprits, but analysis disproved this hypothesis.
- 'TA428' is linked to Chinese origin and has a history of attacks against South East Asian and Russian targets.
- The Mail-O malware acts as a downloader disguised as legitimate software, with a compilation timestamp of 2019-12-20.
- The malware exports functions 'ServiceMain' and 'Entery', with capabilities to launch processes and communicate with external servers.
- Connections to other malware variants like PhantomNet and SManager suggest shared tooling among threat actors.
- The threat actor 'TA428' demonstrates custom-tailored region-specific supply chain attacks, indicating high intelligence collection efforts.
- The ThunderCats operation under 'TA428' showcases novel techniques and capabilities, challenging the perception of Western malware superiority.
- The report provides a YARA rule for detecting overlaps in exported functions, highlighting the complexity of attributing cyber attacks.
- Date of report: June 8, 2021. Operating region: China, Russia. Targeted sector: Russian government institutions.


