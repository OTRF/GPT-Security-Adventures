
Report 1

Malformed report.





Report 2

Summary:
The threat actor known as ACTINIUM, also referred to as Gamaredon, has been targeting Ukrainian organizations, particularly in government, military, NGOs, judiciary, law enforcement, and non-profit sectors, with a focus on exfiltrating sensitive information and maintaining access. The group operates out of Crimea and is attributed to the Russian Federal Security Service (FSB). ACTINIUM uses phishing emails with remote templates, web bugs, and malicious macro attachments to gain access. They employ a variety of malware families such as DinoTrain, DesertDown, DilongTrash, ObfuBerry, ObfuMerry, and PowerPunch, with a focus on obfuscation and agility to evade detection. The group uses a dynamic Windows function hashing algorithm in their Pterodo malware to map API components and decrypt data on-demand. Microsoft has provided indicators of compromise (IOCs) and detection methods for customers to protect against ACTINIUM activity. The report was published on February 14, 2024, by Microsoft Security Blog.





Report 3

Malformed report





Report 4

Summary:
The report discusses the discovery of a rare Linux backdoor implant named EvilGnome targeting desktop users, with capabilities including desktop screenshots, file stealing, audio recording, and downloading/executing modules. Operational similarities were found between EvilGnome and the Gamaredon Group, an alleged Russian threat group targeting individuals associated with the Ukrainian government. Evidence of hosting, infrastructure, and tool similarities between EvilGnome and Gamaredon Group was presented, indicating a potential connection. The report includes technical analysis of EvilGnome's deployment, spy agent functionality, modules, and prevention/response recommendations. The malware is fully undetected across major security solutions, and a YARA rule for detection has been created. The report concludes with the anticipation of newer versions of EvilGnome being discovered in the future. The report was published on July 17, 2019, by Intezer.





Report 5

The Gamaredon Group, a Russian state-sponsored cyber espionage group, has been actively targeting Ukrainian government organizations using a multi-stage Telegram scheme to deliver malicious payloads. The group's network infrastructure relies on Telegram for victim profiling and confirmation of geographic location before delivering the final payload. The threat actor uses obfuscated macro and PowerShell scripts, as well as spear-phishing techniques to target government organizations in Ukraine. The Gamaredon Group's novel approach includes using Telegram accounts to dynamically change IP addresses during Eastern European working hours, indicating human-operated activity. The group's targets include strategic industries in Ukraine, such as the military and law enforcement. The threat actor has been attributed to Russia based on the nature of the targets and network infrastructure. The BlackBerry Research & Intelligence Team has traced the group's activity to Crimea and identified communication between the C2 and the group's node. The group's use of Telegram and dynamic IP addresses make tracking and analyzing their attacks challenging for security researchers. The threat actor's tactics demonstrate a sophisticated and persistent threat to Ukrainian organizations.





Report 6

Summary:
- Threat actor: Gamaredon (Primitive Bear) Russian APT Group
- Region: Ukraine
- Operating sector: Government
- Date: February 3, 2022
- Evidence of capability: Gamaredon has been targeting Ukrainian government officials and organizations since 2013, with recent activity observed in attempts to compromise a Western government entity in Ukraine.
- Novel tools and techniques: Gamaredon recycles domains, rotates them across new infrastructure, and uses remote template injection techniques in malicious documents to pull down code, with recent samples leveraging a unique approach to establish C2 communication.
- Infrastructure: Gamaredon has three large clusters of infrastructure used for phishing and malware purposes, with over 700 malicious domains, 215 IP addresses, and over 100 malware samples identified.
- Mitigations: Recommendations include searching for indicators of compromise, blocking active infrastructure IoCs, implementing DNS security solutions, and applying additional scrutiny to network traffic communicating with AS 197695.
- Protection for customers: Palo Alto Networks products provide coverage against the malware techniques used by Gamaredon.
- Additional resources: Indicators of Compromise (IoCs) and additional resources are available on the Unit 42 GitHub for further investigation and defense against the threat group.





Report 7

Gamaredon APT Group has been active since 2013, primarily targeting Ukrainian government institutions. In March, they used Covid-19 as a lure in their campaigns, targeting victims in European countries. The group's early campaigns were politically motivated, with ties to the Ukrainian revolution in 2014. They have evolved their tactics over the years, with recent activities in February 2020 and exploiting the pandemic in March. The group's novel techniques include using template injection for loading malicious macros and obfuscating VBS files. The threat actor's mistakes in coding suggest ongoing development of their malware. The attacks were traced back to IP addresses from Russian hosting companies, indicating the use of VPS as their attack base. The group's use of socially relevant topics like Covid-19 highlights their adaptability and persistence in targeting victims.





Report 8

Summary:
Gamaredon APT, a threat actor linked to the Russian military, has intensified cyberattacks on Ukrainian military and security institutions since December. They have targeted Ukrainian national security entities, including the Hetman Petro Sahaidachnyi National Ground Forces Academy, with cyber-espionage activities and spyware implants. The group has enhanced its toolset, introducing a modified version of their Pterodo malware that collects system data and utilizes Microsoft.Vbe.Interop. They have also integrated Nginx forwarders and dynamic DNS providers to process traffic from compromised victim machines. Gamaredon's offensive capabilities have impacted over five thousand unique Ukrainian entities, showcasing their ability to integrate cyber-offense measures into traditional warfare models. The threat actor's operations have been ongoing since 2014 in Eastern Ukraine, demonstrating their persistence and evolving tactics. The report was published on February 5, 2020, by Threatpost.





Report 9

The Gamaredon Group, also known as Winterflounder, Primitive Bear, and other aliases, is a state-sponsored threat actor originating from Russia. The group has been active since at least 2013 and is motivated by information theft and espionage. They have targeted sectors such as defense, government, law enforcement, NGOs, diplomats, and journalists in various countries, including Ukraine, the USA, and many others. The group has been observed using a variety of tools and techniques, including malware like EvilGnome and PowerPunch. Their operations have intensified over the years, with multiple waves of attacks targeting Ukrainian entities, especially during times of geopolitical tension. The group has also leveraged current events, such as the COVID-19 pandemic, to lure victims into opening malicious attachments. Counter operations against the Gamaredon Group have been reported, but the group's activities continue to pose a significant threat to cybersecurity.





Report 10

Summary: The Gamaredon Group, a Russian state-sponsored cyber-espionage hacking group, has been targeting government and critical public and private organizations in Ukraine since the start of the Russian invasion. The group is known for rapid attacks, stealing data from breached systems within 30-50 minutes. They use email or messaging apps to deliver malicious attachments, PowerShell scripts, and malware like 'GammaSteel' to compromise victims. Gamaredon also modifies Microsoft Office Word templates to spread malware and targets browser cookies for account takeovers. The threat actors exfiltrate documents of interest within 30-50 minutes and plant multiple infected files to increase re-infection chances. They also infect USB sticks to breach isolated networks and frequently change IP addresses to evade detection. The best defense against Gamaredon attacks is to block unauthorized execution of specific executables. The report was published on July 15, 2023.





Report 11

Summary:

The Anomali Threat Research team identified malicious activity aligned with Gamaredon TTPs targeting Ukraine, specifically diplomats, government officials, journalists, law enforcement, military personnel, and NGOs, including the Ministry of Foreign Affairs of Ukraine. The campaign began in mid-October 2019 and was ongoing as of November 25, 2019. The threat actor utilized known Gamaredon tactics along with a new template-injection technique not previously observed. The report aims to highlight this new TTP and share IOCs for further analysis. The evidence of the threat actor's capability lies in the alignment with Gamaredon tactics and the novelty of the template-injection technique. The victims targeted were primarily in the government and diplomatic sectors in Ukraine. The report provides valuable insights for the security community to enhance awareness and defense mechanisms against Gamaredon activities.

Date: December 5, 2019
Source: Anomali Threat Research
Link: https://www.anomali.com/blog/malicious-activity-aligning-with-gamaredon-ttps-targets-ukraine#When:15:00:00Z





Report 12

Gamaredon Group, also known as Primitive Bear, Shuckworm, and ACTINIUM, is an advanced persistent threat (APT) based in Russia. They target state institutions of Ukraine and western government entities located in Ukraine. Gamaredon leverages malicious office files distributed through spear phishing, using a PowerShell beacon called PowerPunch for subsequent malware execution. Popular malware families they deploy include Pterodo and QuietSieve. Their network infrastructure analysis revealed domains registered dominantly by REG[.]RU, with changing patterns in registrant emails and domain creation dates as recent as March 2022. Gamaredon's arsenal includes malicious office documents with macros and the constantly evolving custom backdoor Pterodo. They use a variety of TLDs and ASNs for their operations. Cisco Global Threat Alerts tracks Gamaredon activity, enriching threat descriptions with MITRE references. The group's detection examples involve communication attempts with sinkholed domains. Gamaredon's tactics and techniques are continuously evolving, posing a significant threat to Ukrainian state organizations. (Source: https://blogs.cisco.com/security/network-footprints-of-gamaredon-group)





Report 13

Summary:
- Threat actor: Gamaredon Group
- Region: Ukraine
- Operating sector: Middle Eastern targeting, previously targeted Ukrainian interests
- Type of company of victims targeted: Saudi organizations, Saudi International Petrochemical Company
- Date: 12th December 2019
- Evidence of capability: Overlaps in operational infrastructure between BlueAlpha and Iranian APTs, significant overlapping domains indicating a departure from previous Gamaredon activity
- Novelty of tools and techniques: Mimicking TTPs of Iran-nexus groups, potential operational collaboration between Iran-nexus group and BlueAlpha
- Attribution: Gamaredon Group attributed to FSB, BlueAlpha likely a Russian state-sponsored threat actor
- Conclusion: Russian state-sponsored groups likely to continue using false flags and leveraging operational infrastructure of other threat actors for cyber operations.





Report 14

Summary:
- Threat actor: Primitive Bear (Gamaredon)
- Region: Ukraine
- Operating sector: Government officials targeted
- Date: Campaign took place from January through at least late March 2021
- Evidence of capability: Russia-sponsored cyberespionage group targeting Ukrainian government officials with malicious files, using decoy documents themed around current events
- Novelty of tools and techniques: Distribution of .docx files attempting to download .dot files via remote templates, use of template injection, and crafting phishing themes based on authentic events
- Unclear final objective due to remote template domains being down at the time of discovery
- Motivated by cyberespionage, targeting regional foes with likely illicitly obtained private documents
- Hybrid warfare tactics observed, aligning decoy documents with real-world conflicts before significant events occurred.





Report 15

Summary:
The Gamaredon Group, a pro-Russian CyberSpy APT, has intensified its targeting of Ukrainian security institutions, particularly the military and law enforcement. The group has evolved by introducing new components to enhance its offensive capabilities, conducting cyber espionage actions against institutions like the Hetman Petro Sahaidachnyi National Ground Forces Academy. Gamaredon's activities serve as a testing ground for the Russian military to observe the potential of cyber warfare in contemporary conflicts. The group's operations demonstrate the integration of cyber offense measures into traditional warfare models, showcasing the fifth cyber domain's significance. Gamaredon's recent tools and techniques include the usage of macro payloads and obfuscated .NET applications, indicating technical enhancements and persistent targeting of Ukrainian NatSec entities. The group's activities align with the political and security dynamics in the region, serving as a substitute for traditional kinetic strikes in the ongoing conflict. The report provides indicators of compromise and attack patterns associated with Gamaredon's operations. The threat actor's activities highlight the evolving nature of cyber warfare and its role in modern confrontations. 

Region: Ukraine
Operating Sector: Military and Security Institutions
Type of Company: Not specified
Capability of Threat Actor: Demonstrated technical determination and persistent targeting
Novelty of Tools and Techniques: Usage of macro payloads, obfuscated .NET applications, and targeted lures
Date: February 5, 2020
Operation Time Window: Ongoing

Source: https://labs.sentinelone.com/pro-russian-cyberspy-gamaredon-intensifies-ukrainian-security-targeting/





Report 16

Summary:
The Russia-backed hacker group Gamaredon has been targeting Ukrainian organizations with info-stealing malware since June 2013. Operating from Sevastopol in Russia-occupied Crimea, the group uses variants of PowerShell info-stealer malware named GammaLoad and GammaSteel. These custom-made implants can exfiltrate files, steal credentials, and take screenshots. Gamaredon employs phishing emails with malicious LNK files distributed in RAR archives to gain initial access, targeting government organizations, critical infrastructure, and defense agencies. The group's recent activity involves multi-stage deployment of malware to maintain persistence, evolving their tactics to avoid detection. In 2022, Ukraine reported over 70 incidents related to Gamaredon, with Latvia also falling victim to their phishing attacks. The group's main goal is to conduct targeted cyberintelligence operations, posing a significant threat to Ukraine's cybersecurity.





Report 17

Summary:
- Threat actor: Russia's Trident Ursa (aka Gamaredon APT)
- Region: Ukraine
- Operating sector: Government, Malware
- Type of company of victims targeted: Large petroleum refining company within a NATO member nation
- Date: December 20, 2022
- Evidence of capability: Trident Ursa remains a dedicated access creator and intelligence gatherer, with over 500 new domains, 200 samples, and other Indicators of Compromise (IoCs) mapped out in the past 10 months.
- Novelty of tools and techniques: Trident Ursa uses fast flux DNS, legitimate web services to bypass DNS, messaging services for C2 IP lookup, and separate IPs for root domains and subdomains to hide true IP assignment. They also use various malware types, including phishing using HTML files and Word documents, as well as droppers like 7ZSfxMod_x86.exe and myfile.exe.
- Conclusion: Trident Ursa is an agile and adaptive APT group that continues to operate since at least 2014, posing a significant threat to Ukraine and its allies. They rely on routine phishing attempts, publicly available tools, and obfuscation to execute their operations, making them a persistent threat that requires active defense measures.





Report 18

Summary:
The Gamaredon Group, a threat actor possibly linked to Russian state-sponsored hackers, has been actively targeting Ukrainian government and military agencies since mid-2013. They primarily use spear-phishing attacks with military-themed bait documents to deploy remote manipulation system binaries. The group has recently been implicated in spreading a new Linux malware called Evil Gnome. Their tools and techniques show a focus on Ukrainian organizations and resources, with a recent campaign exploiting a WinRAR vulnerability. The group's mistakes, such as poorly-obfuscated scripts and Russian language artifacts, suggest a lack of professionalism. The group's behavior and tactics indicate a more politically motivated rather than a professional cybercriminal approach. Further monitoring is needed to understand the true nature of the Gamaredon Group. The report provides IOCs and insights into the group's activities and methods.

Date: August 21, 2019

Victims: Ukrainian law enforcement and government agencies

Operating Sector: Government and military

Region: Ukraine

Novelty: Exploitation of WinRAR vulnerability, use of publicly available tools, politically motivated tactics.





Report 19

Summary:
- Threat Actor: Gamaredon Group
- Region: Ukraine
- Operating Sector: Ukrainian military and national security establishment
- Type of Company: Not specified
- Date: February 27, 2017
- Evidence of Capability: Gamaredon Group shifted to custom-developed malware, improved technical capabilities, used compromised domains, dynamic DNS providers, and Russian hosting providers for distribution.
- Novelty of Tools and Techniques: Custom-developed malware with capabilities for downloading and executing additional payloads, scanning system drives, capturing screenshots, and executing commands remotely. Evolution from off-the-shelf tools to custom implants like Pteranodon.
- Tools and Techniques: Batch scripts, wget binaries, VNC executables, custom downloaders, custom remote access implants.
- Detection: Antimalware technologies have a poor record of detecting the malware developed by the Gamaredon Group.
- Campaigns: Operation Armageddon targeted individuals involved in the Ukrainian military and national security establishment.
- Delivery Vector: JavaScript file downloading custom tools from compromised sites.
- Infrastructure: Reuse of domains, consistent monikers, themed filenames, and hardcoded network locations.
- Protection: Palo Alto Networks customers are protected through WildFire, Traps, and Threat Prevention.
- Conclusion: Gamaredon Group has been active since at least 2014, targeting Ukrainian government individuals with evolving malware capabilities. Active hunting for malicious activity is crucial for defenders to identify and protect against new threats.





Report 20

Summary:
The Gamaredon Group, a threat actor with Russian ties, continues to target Ukraine, particularly the military and law enforcement sectors. The group uses a sophisticated infection chain involving password-protected SFX archives and customized versions of UltraVNC for remote administration. The use of Matryoshka structure in the SFX archives makes detection difficult, with low AV detection rates. The group's TTPs show a focus on persistence, evasion of malware analysis tools, and data exfiltration. The recent attack campaign showcases the group's ongoing operations and interest in infiltrating the East European ecosystem, using novel techniques and tools like custom-made RATs. The attack patterns observed in 2019 indicate a consistent evolution in the group's tactics, techniques, and procedures. The report provides indicators of compromise, including hashes, URLs, components, IPs, and Yara rules for detection. The report was published on 06/04/2019 by Cybaze-Yoroi ZLAB team.





Report 21

Malformed report.





Report 22

Summary: The Gamaredon Group, a Russian state-sponsored threat actor, has been targeting Ukraine and EU government agencies through phishing campaigns. The group has been active since at least 2014 and is linked to the Russian Federal Security Service. Evidence shows that they have launched thousands of cyber-attacks against critical entities in Ukraine. The phishing emails contain malware-laden attachments disguised as information on war criminals and military assistance to Ukraine. The tools and techniques used by the group, such as custom malware development and VBScript code execution, demonstrate their advanced capabilities. The report highlights the novelty of the phishing campaigns targeting EU officials and the use of deceptive sender addresses to appear legitimate. The operation time window is not specified in the report.





Report 23

Summary:
Ukraine CERT-UA issued a warning about new attacks conducted by the Russia-linked Armageddon APT group using the GammaLoad.PS1_v2 malware. The phishing campaign targeted local state organizations with malicious attachments that led to the execution of the GammaLoad.PS1_v2 malware on victims' computers. The attack was attributed to the Armageddon APT group (UAC-0010) and was part of a long string of attacks against Ukrainian government entities. The Ukrainian CERT shared indicators of compromise for this campaign. The attack showcased the group's capability to conduct sophisticated phishing campaigns and deploy advanced malware tools. The operation took place on May 15, 2022.


