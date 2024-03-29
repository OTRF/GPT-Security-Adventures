
Report 1

Summary:
APT 29, also known as Cozy Bear or The Dukes, has been identified as the threat actor behind the Seaduke Trojan, a sophisticated information-stealing malware used in cyberespionage operations against high-value targets, particularly in government sectors in the United States and Europe. The Duke group has a history of targeting governmental and diplomatic organizations since at least 2010, using a range of malware tools including Cozyduke, Miniduke, and Cosmicduke. Seaduke, deployed selectively against specific targets, exhibits advanced capabilities with highly configurable frameworks and encryption layers, indicating significant investment in preparation. The group's operational sophistication includes leveraging compromised websites for attack infrastructure, rapid development of malware frameworks, and fine-tuned computer network exploitation skills. The Seaduke payload, developed in Python, shares similarities with Cozyduke in operation, with a communication protocol utilizing over 200 compromised web servers for command and control. The attackers control Seaduke through compromised websites, issuing tasks to infected machines for operations such as data exfiltration and secure file deletion. The Duke group's operational success and boldness suggest a long-term commitment to cyberespionage activities, with the potential for future attacks using evolved or new tools and techniques.





Report 2

APT29, also known as Cozy Bear or The Dukes, is a Russian espionage group likely sponsored by the Foreign Intelligence Service (SVR). Mandiant has been tracking APT29 since at least 2014 and continues to identify their operations targeting the interests of the United States, NATO, and partner countries. In 2022, APT29 focused on organizations influencing the foreign policy of NATO countries, demonstrating persistence and aggressiveness. Mandiant observed APT29 using advanced tactics targeting Microsoft 365, including disabling Purview Audit to target email inboxes without leaving logs. APT29 also exploited the self-enrollment process for Multi-Factor Authentication (MFA) in Azure AD to access dormant accounts and bypass MFA protections. Additionally, APT29 demonstrated exceptional operational security by using Azure Virtual Machines to obfuscate their last-mile access to victim environments. Mandiant expects APT29 to continue developing novel and stealthy techniques to access Microsoft 365. The report was last updated on August 10, 2023.





Report 3

Summary:
The threat actor APT 29, also known as Cozy Bear and The Dukes, is a well-resourced and organized cyberespionage group believed to be working for the Russian Federation since at least 2008. They primarily target Western governments, ministries, agencies, think tanks, and governmental subcontractors, as well as other organizations globally. The Dukes employ a wide range of malware toolsets, including MiniDuke, CosmicDuke, OnionDuke, CozyDuke, and others, and engage in large-scale spear-phishing campaigns against governmental institutions. They have been involved in various hacking operations targeting different sectors and countries, with a focus on information theft and espionage. The threat actor has been linked to attacks on the Pentagon, the Democratic National Committee, U.S. think tanks, European ministries, and COVID-19 vaccine development organizations. The Dukes have been active in recent years, launching new campaigns and using novel techniques such as FoggyWeb, MagicWeb, and GraphicalProton malware. Counter operations against the threat actor have been reported, including indictments and executive orders to block harmful foreign activities.





Report 4

Malformed report





Report 5

Cloaked Ursa (APT29), also known as Cozy Bear, has been identified as a threat actor group affiliated with the Russian government. They have been historically targeting various sectors, including diplomatic missions. In their recent campaigns between May and June 2022, they targeted Western diplomatic missions, specifically embassies in Portugal and Brazil. The threat actor group used trusted online storage services like Google Drive and DropBox to deliver malicious payloads, making detection challenging. The use of encryption further complicates the detection of malicious activities. The campaigns involved phishing emails with malicious HTML files (EnvyScout) that served as droppers for additional malicious files, including a Cobalt Strike payload. The threat actor group has been attributed to Russia's Foreign Intelligence Service (SVR) by the United States and the United Kingdom. The campaigns demonstrate the sophistication and evolving capabilities of Cloaked Ursa in leveraging popular cloud storage services for malicious activities. The use of Google Drive in their recent campaigns marks a novel tactic for the threat actor group. The campaigns targeted diplomatic missions, showcasing the threat actor's ability to tailor their attacks to specific sectors and regions. The report provides detailed technical analysis of the tools and techniques used by the threat actor group, including the deobfuscation of payloads and the execution flow of malicious files. The report also includes indicators of compromise (IoCs) and XQL hunting queries for Cortex XDR to aid in detection and mitigation efforts. The activity was disclosed to Google and DropBox, who took action to block the malicious activity.





Report 6

Summary:
The threat actor known as Cozy Bear, also classified as APT29, is a Russian hacker group associated with Russian intelligence agencies. They have been involved in cyber espionage and cyber warfare activities since at least 2008. Cozy Bear has targeted various sectors, including military, government, energy, diplomatic, and telecom sectors, as well as commercial entities and government organizations in countries like Germany, Uzbekistan, South Korea, and the US. They have used sophisticated malware tools like CozyDuke, Show.dll, and Seaduke, with capabilities for data exfiltration, remote access, and stealthy operations. Notably, Cozy Bear was responsible for the SUNBURST malware supply chain attack in 2020, affecting approximately 18,000 SolarWinds clients, including several US federal agencies. The group has also been linked to attacks on the Democratic National Committee, US think tanks, NGOs, the Norwegian government, Dutch ministries, and the Republican National Committee. Cozy Bear's activities have shown a high level of technical capability and persistence, with novel tools and techniques like the 'HAMMERTOSS' remote access tool and the 'MagicWeb' attack method. The group's operations have spanned over a decade, with evidence of ongoing development and adaptation of their toolsets.





Report 7

Malformed report





Report 8

Summary:
- Threat actor: Cloaked Ursa (APT 29, Cozy Bear, The Dukes)
- Region: Global, with a focus on targeting diplomatic missions in Ukraine
- Operating sector: Government, specifically diplomatic missions
- Date: Campaign observed in July 12, 2023
- Evidence of capability: Cloaked Ursa used novel phishing lures focusing on diplomats themselves rather than countries they represent, targeting at least 22 of over 80 foreign missions in Kyiv. They repurposed legitimate advertising flyers to deliver malicious payloads, demonstrating sophisticated social engineering tactics.
- Tools and techniques: Cloaked Ursa used unconventional lures, Windows shortcut files masquerading as image files, and injected shellcode into running processes. They leveraged Microsoft Graph API and Dropbox API for command and control communication, showcasing advanced technical capabilities.
- Protection: Palo Alto Networks customers receive protections against these threats through products like Cortex XDR, WildFire, and Cloud-Delivered Security Services.
- Recommendations: Diplomatic missions are advised to train employees on cybersecurity threats, be cautious of URL redirection, downloads, and attachments, and verify file extensions to prevent compromise.





Report 9

Summary:
The threat actor known as NOBELIUM, linked to APT 29, Cozy Bear, and The Dukes, has been identified by Microsoft as using a newly detected malware called FoggyWeb. This malware serves as a persistent backdoor targeting Active Directory Federation Services (AD FS) servers. NOBELIUM has been observed using FoggyWeb to exfiltrate sensitive information, such as configuration databases and certificates, from compromised AD FS servers. The malware was first observed in the wild as early as April 2021. NOBELIUM has been known to employ custom-built malware and tools, showcasing significant operational resources. Microsoft has provided mitigation guidance and indicators of compromise (IOCs) for organizations to protect their AD FS servers from NOBELIUM attacks. The threat actor's capability to develop sophisticated tools like FoggyWeb highlights their advanced tactics and techniques. The report was published on September 27, 2021, by the Microsoft Security Blog.





Report 10

Summary: The French national cyber-security agency ANSSI has warned of Nobelium cyberspies, a Russian-backed hacking group, targeting French organizations since February 2021. The threat actor compromised email accounts of French orgs to deliver malicious emails targeting foreign institutions. ANSSI identified overlaps in tactics with the SolarWinds supply chain attack in 2020. Nobelium used virtual private servers (VPS) from hosting companies, mainly favoring servers from OVH. The group targeted Active Directory Federation Services (AD FS) servers and managed service providers (MSPs) globally, using a new backdoor named FoggyWeb. Microsoft reported Nobelium as the most active Russian hacking group between July 2020 and June 2021. Mandiant linked the group to breaching government and enterprise networks worldwide with a new backdoor called Ceeloader. The threat actor's capabilities include sophisticated phishing campaigns and targeting high-profile organizations in the IT supply chain. 

Date: December 6, 2021

Region: France

Operating Sector: Cybersecurity

Type of Company: French organizations, government agencies, managed service providers, cloud service providers, governments, think tanks, private companies, political interests.





Report 11

Summary:
APT 29, also known as Cozy Bear, targeted Ministries of Foreign Affairs of NATO aligned countries, including the German Embassy, with malicious PDF documents containing diplomatic invitation lures. The threat actor used a variant of the Duke malware, linked to Russian state-sponsored cyber espionage activities, for payload delivery. The threat actor employed Zulip, an open-source chat application, for command-and-control to evade detection. Novel techniques included HTML smuggling, DLL sideloading, Windows API hashing, XOR encryption, and hiding C2 communication in legitimate web traffic. The threat actor used reconnaissance PDF documents to notify successful email attachment openings. The campaign was attributed to APT29, a Russian state-sponsored threat actor known for targeting governments, political organizations, and critical industries in the US and Europe. The operation occurred on August 10, 2023, with updates on October 5, 2023.





Report 12

Malformed report.





Report 13

Summary:
- Threat actor: APT29, Cozy Bear, Nobelium (Microsoft calls them Midnight Blizzard)
- Date: June 21st, 2023
- Region: Targeting governments, IT service providers, NGOs, defense, and critical manufacturing industries
- Evidence of capability: Responsible for SolarWinds supply chain attack in 2020, cyberattacks during the war in Ukraine
- Novelty of tools and techniques: Using password spray, brute force, token theft techniques, low-reputation proxy services to conceal IP addresses, frequently switching between IP addresses
- Victims: Governments, IT service providers, NGOs, defense, and critical manufacturing industries
- Microsoft informed targeted customers but did not disclose specific victim names.





Report 14

Summary:
- Threat actor: NOBELIUM, also known as APT 29, Cozy Bear, The Dukes
- Region: US, Europe, Central Asia
- Operating sector: Government organizations, NGOs, IGOs, think tanks
- Date: August 26, 2022
- NOBELIUM used a post-compromise capability called MagicWeb to maintain persistent access in compromised environments.
- MagicWeb was deployed during an ongoing compromise to maintain access during remediation steps.
- NOBELIUM targeted AD FS servers by replacing a legitimate DLL with a malicious one to facilitate covert access.
- MagicWeb manipulates user authentication certificates to subvert authentication processes.
- The threat actor used unique tradecraft per target, making detection challenging.
- Microsoft recommends implementing a holistic security strategy and migrating to Azure AD for robust security.





Report 15

Malformed report





Report 16

Summary:
- Threat actor: Midnight Blizzard (previously tracked as NOBELIUM), also known as APT 29, Cozy Bear, The Dukes.
- Region: Russia-based threat actor attributed by the US and UK governments as the Foreign Intelligence Service of the Russian Federation (SVR).
- Operating sector: Primarily targets governments, diplomatic entities, non-government organizations (NGOs), IT service providers in the US and Europe.
- Type of company of victims targeted: Government, NGOs, IT services, technology, discrete manufacturing, and media sectors.
- Date: Ongoing since early 2018.
- Evidence of capability: Utilizes diverse initial access methods, advanced techniques to compromise authentication mechanisms, and persistent espionage objectives.
- Novelty of tools and techniques: Utilizes token theft techniques, authentication spear-phishing, password spray, brute force attacks, and social engineering lures over Microsoft Teams.
- Latest attack: Conducts targeted social engineering attacks using credential theft phishing lures sent as Microsoft Teams chats to steal credentials and gain access to Microsoft 365 accounts.
- Recommendations: Implement phishing-resistant authentication methods, apply Conditional Access authentication strength, educate users about social engineering attacks, and specify trusted Microsoft 365 organizations.
- Indicators of compromise: Malicious actor-controlled subdomains used in the attack.
- Hunting guidance: Customers can use Microsoft Purview and Microsoft Sentinel to identify and detect related activity in their environment.





Report 17

Summary:
APT 29, also known as Cozy Bear or The Dukes, resurfaced in 2014 with a new campaign named "Miniduke is back: Nemesis Gemina and the Botgen Studio." The threat actor used a customized backdoor written in Assembler, a unique command and control mechanism involving Twitter accounts, and stealthy transfer of updates hidden inside GIF files. The threat actor continued to use old-school virus writing techniques and habits, with evidence of malware developed using these methods. The threat actor also utilized a new custom backdoor called CosmicDuke, capable of stealing various types of information, and compiled using a framework called "BotGenStudio." The victims targeted by APT 29 included government, diplomatic, energy, telecom operators, military, and individuals involved in illegal substances trafficking. The threat actor's operations involved sophisticated obfuscation techniques, encryption, and compression algorithms to evade detection. The campaign showed evidence of targeting specific individuals and organizations, with a focus on espionage and cyber attacks. The threat actor's activities were observed to follow a structured work week and specific activity hours, indicating a methodical approach to their operations. The report highlighted the advanced capabilities and novel techniques used by APT 29, showcasing their persistence and adaptability in carrying out targeted attacks.





Report 18

NOBELIUM, also known as APT29, targeted European Union countries' diplomatic entities and systems assisting Ukraine in March 2023. The threat actor, attributed to the Russian government, is known for its agility and innovative intrusion techniques. The campaign utilized spear-phishing emails with links to malicious websites hosted on compromised legitimate servers. The malware delivery involved HTML smuggling to deliver malicious files to victims' systems. NOBELIUM used anti-forensic techniques to wipe out metadata and remained persistent on infected systems by creating registry keys and directories. The threat actor utilized compromised network infrastructure and a legitimate web server to increase its technical capabilities. The C2 communication was disguised using the Notion API, aligning with previous tactics used by APT29. The campaign targeted Western countries, especially those in Western Europe, providing help to Ukraine amidst the Russian-Ukraine war. The threat actors carefully followed geopolitical events to increase the success of their infections. The report provides indicators of compromise and countermeasures to detect and mitigate the threat.





Report 19

Summary:
- Threat actor: Nobelium, also known as APT29 and Cozy Bear
- Region: Russia
- Operating sector: Embassies
- Type of company: Government departments
- Date: February 24, 2022
- Capability: Highly sophisticated group of Russian-sponsored cybercriminals
- Novelty of tools and techniques: Impersonating someone associated with the Turkish embassy in targeted email-based attacks, usage of JARM technology for server fingerprinting, creation of .ISO files with malicious JavaScript, utilization of Cobalt Strike beacon as a payload
- Impact: Compromised machines under the control of the threat actor, potential political ramifications
- Severity level: Medium





Report 20

Summary:
APT 29, also known as Cozy Bear or The Dukes, a Russia-linked threat actor, targeted nine email accounts in Norway, including those of the Labour party, foreign ministry, and defense ministry. The attack, believed to be spear phishing, aimed to obtain sensitive information. The group is linked to the Russian Security Service (FSB) and has been previously blamed for breaching the Democratic National Committee computers. The attack was considered a serious threat to democratic institutions, although no classified material was taken. The incident occurred in 2017, amidst strained relations between Norway and Russia due to the presence of U.S. Marines in Norway. The threat actor demonstrated capability in targeting government entities and using novel techniques like spear phishing.





Report 21

Summary:
- Threat actor: APT29, Cozy Bear, The Dukes
- Region: Global
- Operating sector: Multiple industries including think tank, law enforcement, media, U.S. military, imagery, transportation, pharmaceutical, national government, and defense contracting
- Type of company of victims: Defense, Imagery, Law Enforcement, Local Government, Media, Military, Pharmaceutical, Think Tank, Transportation, & US Public Sector
- Evidence of capability: Crafted phishing emails appearing to be from the U.S. Department of State, used unique links in each email, compromised email server of a hospital and corporate website of a consulting company, used Cobalt Strike Beacon backdoor, customized C2 profile to blend in with legitimate network traffic
- Novelty of tools and techniques: Used weaponized Windows shortcut files, decoy documents, and Cobalt Strike Beacon, selectively served payloads based on HTTP headers, reused old phishing tactics with creative new elements
- Date: November 14, 2018
- Attribution challenges: Similarities and technical overlaps with previous APT29 activity, potential reuse of old phishing tactics, sophisticated actor with deceptive historical uses
- Implications: First activity from APT29 in at least a year, organizations previously targeted by APT29 should take note, importance of investigating full scope of intrusion
- Source: https://www.fireeye.com/blog/threat-research/2018/11/not-so-cozy-an-uncomfortable-examination-of-a-suspected-apt29-phishing-campaign.html





Report 22

Summary:
The threat actor known as APT 29, Cozy Bear, or The Dukes, has been active since 2013 in a campaign named Operation Ghost, targeting Ministries of Foreign Affairs in Europe and the Washington, DC embassy of a European Union country. The Dukes have been using new malware families such as PolyglotDuke, RegDuke, and FatDuke, with the latest observed sample deployed in June 2019. The threat actor has shown capability in developing new implants and compromising high-value targets. The Dukes have employed sophisticated tactics like steganography, using social websites for C&C URLs, and leveraging Windows Management Instrumentation for persistence. The operation is ongoing and has shown strong code similarities with previous Dukes campaigns, leading to a high confidence attribution. The threat actor's tools and techniques have evolved, with a focus on persistence, lateral movement, and obfuscation to avoid detection. The Dukes have demonstrated the ability to adapt and remain under the radar while conducting espionage activities. The full report provides detailed analysis and indicators of compromise for further investigation.





Report 23

Summary:
The threat actor APT 29, also known as Cozy Bear, targeted the Democratic National Committee (DNC) in the United States in 2016. CrowdStrike, a cybersecurity company, was hired to investigate the breach and identified two sophisticated Russian intelligence-affiliated adversaries, Cozy Bear and Fancy Bear, operating separately on the DNC network. Cozy Bear used the SeaDaddy implant and Powershell backdoors for intrusion, while Fancy Bear deployed X-Agent malware and X-Tunnel network tunneling tools. The adversaries engaged in anti-forensic measures and had advanced tradecraft capabilities. The intrusion lasted from summer 2015 to June 2016, with remediation conducted by CrowdStrike from June 10-13, 2016. The tools and techniques used by the threat actors were novel and demonstrated a high level of sophistication. The evidence of exfiltration and data theft was supported by the U.S. Intelligence community and independent reports. The investigation highlighted the ongoing threat posed by nation-state actors targeting political entities. The report provides detailed indicators of compromise and technical information on the adversary's tactics, techniques, and procedures. The operation window of the attack ranged from July 2015 to June 2016. The victims targeted were in the political sector, specifically the DNC. The report was published on June 14, 2016, by CrowdStrike.





Report 24

APT 29, also known as Cozy Bear or The Dukes, targeted U.S.-based think tanks and NGOs in a series of coordinated spear phishing campaigns post the 2016 United States Presidential Election. The attacks were observed by Volexity, with emails sent from attacker-created Google Gmail accounts and compromised Harvard email accounts. The threat actor group, The Dukes, previously associated with the breach of the Democratic National Committee, used a backdoor named PowerDuke in these attacks. The PowerDuke malware, first seen in August 2016, was used in the post-election attacks on November 9, 2016. The attacks leveraged steganography in PNG files to hide components of the backdoor, a novel technique. The Dukes continue to launch sophisticated attacks targeting think tanks and NGOs, evading anti-virus and anti-malware solutions with their innovative tactics. The group's use of anti-VM macros and PowerShell scripts, along with hiding backdoors in PNG files, showcases their capability and persistence in targeting organizations for long-term access. The Dukes are likely to continue launching new attacks in the future.





Report 25

Summary:
APT 29, also known as Cozy Bear, targeted Dutch ministries, including Algemene Zaken, in the past six months. The threat actor attempted to gain access to sensitive information through phishing emails and fake websites. The APT groups responsible for the attacks are identified as APT28 and APT29, known as Cozy Bear and Fancy Bear in the United States. The attacks were unsuccessful in obtaining sensitive data. The evidence of the threat actor's capability lies in their targeted phishing tactics and use of fake websites to steal login credentials. The report does not mention the specific operating sector or type of company targeted by the threat actor. The operation time window for the hack attempts was within the past six months, as of February 2017.





Report 26

Summary:
The threat actor identified as Russian Foreign Intelligence Service (SVR) has been exploiting the JetBrains TeamCity CVE globally since September 2023, targeting servers hosting the software. The SVR has been observed using initial access gleaned from exploiting the CVE to escalate privileges, move laterally, deploy additional backdoors, and ensure persistent access to compromised networks. The SVR's recent compromise has affected a few dozen companies globally, including an energy trade association, software providers, hosting companies, and IT companies. The SVR's tools and techniques, such as GraphicalProton backdoor and Rubeus toolkit, demonstrate their capability to evade detection and maintain access to compromised environments. The FBI, CISA, NSA, SKW, CERT Polska, and NCSC recommend applying patches for the CVE, monitoring for encoded commands, enabling multi-factor authentication, keeping systems updated, and validating security controls against the threat behaviors mapped to the MITRE ATT&CK for Enterprise framework. The report provides indicators of compromise (IOCs) and mitigation strategies to enhance cybersecurity posture against the SVR threat actor.





Report 27

Summary:
APT 29, also known as Cozy Bear or The Dukes, a Russian cyber-espionage group linked to the Russian Foreign Intelligence Service (SVR), targeted the Slovak government between February and July 2021. The attacks involved spear-phishing campaigns where SVR hackers posed as the Slovak National Security Authority to deliver a Cobalt Strike backdoor via ISO image files. The SVR also used a Safari iOS zero-day exploit to infect diplomats who read emails on their iPhones. ESET and IstroSec confirmed the attacks and noted that similar tactics were used in campaigns targeting diplomats in over 13 European countries. The novelty of the tools and techniques used by the threat actor, along with evidence of their capabilities, were highlighted in reports from various cybersecurity agencies. The operation was reported on August 13th, 2021.





Report 28

Summary:
In 2017, Russian hackers breached the internal network of Dutch police during the investigation of the MH-17 crash. The breach originated from a vulnerability in an "exotic software" on a server at the Dutch Police Academy. The Dutch intelligence service, AIVD, discovered the intrusion after noticing communication with known malicious servers operated by Russian state-sponsored threat actors. The attack was linked to APT29 (Cozy Bear) or APT28 (Fancy Bear), both associated with Russian intelligence services. The hackers' activities within the police network were not fully monitored due to a lack of logging. The incident was part of Russian attempts to gain insights into the MH-17 investigation, leading to tensions between Russia and the Netherlands. The Dutch authorities are investigating making espionage a crime, as Russia continues influence operations to discredit the MH-17 findings.





Report 29

Summary:
- Threat actor: NOBELIUM, also known as APT 29, Cozy Bear, The Dukes
- Region: Global, targeting government and private sector organizations across multiple geographic regions
- Operating sector: Government and private sector organizations
- Date: Mid-2021 onwards
- Evidence of capability: Reliance on domains that emulate other brands, use of typosquat domains, misuse of brands across multiple industry verticals, use of cracked versions of Cobalt Strike tool
- Novelty of tools and techniques: Use of SOLARDEFLECTION C2 infrastructure, typosquat domains, modified server configurations to avoid detection
- Attribution: NOBELIUM's infrastructure overlaps with previously attributed network infrastructure, use of unique variations of Cobalt Strike
- Techniques: Spearphishing campaigns, typosquat redirection, use of deceptive techniques
- Objective: Operating in line with the objectives of Russia’s Foreign Intelligence Service (SVR), targeting organizations and individuals to influence strategic policy and decision-makers in targeted countries.





Report 30

Summary:
The threat actor known as APT 29, Cozy Bear, The Dukes, conducted the StellarParticle campaign throughout 2021, targeting multiple organizations in various sectors. CrowdStrike observed novel tactics and techniques used by the threat actor, including browser cookie theft and Microsoft Service Principal manipulation. The threat actor deployed sophisticated malware families, such as TrailBlazer and a Linux variant of GoldMax, on victim systems. The threat actor demonstrated advanced capabilities in credential hopping, bypassing multifactor authentication using stolen Chrome browser cookies, and manipulating O365 Service Principals. The threat actor also engaged in reconnaissance activities, accessed internal knowledge repositories, and attempted to regain access through external services like FTP servers and VPN connections. The threat actor showed extensive knowledge of Windows, Linux, Azure, O365, and Active Directory, staying undetected for extended periods. The campaign is associated with the COZY BEAR adversary group and highlights the threat actor's persistence, evasion techniques, and advanced capabilities. The operation time window for the campaign was throughout 2021.





Report 31

Summary:
- Threat actor: APT29, Cozy Bear, The Dukes
- Date: May 25, 2021
- Region: United States and Europe
- Operating sector: NGOs, Research Institutions, Government Agencies, International Agencies
- Type of company: Multiple organizations
- Evidence of capability: Phishing campaign using malicious ISO file containing LNK and DLL files, with a lure referencing foreign threats to the 2020 US Federal Elections. Malware includes CobaltStrike Beacon with anti-sandbox and anti-vm checks.
- Novelty of tools and techniques: Use of ISO files as containers for embedded files, manipulation of bytes in payload, use of Firebase for data decryption and execution.
- Attribution: Attributes consistent with APT29 tactics, but not confirmed. Moderate confidence in APT29 involvement.
- Conclusion: APT29 likely responsible for phishing campaign targeting US and European organizations, using historical TTPs with slight modifications. Low static detection rates suggest successful breaches. Recommendations provided for protection against the threat.





Report 32

Summary:
APT 29, also known as Cozy Bear or The Dukes, suspected Russian threat actors, have been targeting government and business entities globally. Mandiant has identified two distinct clusters of activity, UNC3004 and UNC2652, associated with UNC2452 or Nobelium by Microsoft. The threat actors have demonstrated advanced operational security and tradecraft, compromising technology solutions, services, and reseller companies since 2020. They have used novel techniques like using an info-stealer malware campaign to gain initial access, abusing multi-factor authentication, and deploying a new bespoke downloader called CEELOADER. Post-compromise activities include data theft relevant to Russian interests and innovative techniques to maintain persistent access, hinder detection, and confuse attribution efforts. The threat actors have targeted Cloud Service Providers, compromised Microsoft 365 environments, and engaged in lateral movement between CSPs and downstream clients. They have also leveraged compromised WordPress sites, TOR, VPS, and VPN providers for command and control. Mandiant suspects the activity to be UNC2652 and UNC3004, linked to UNC2452, but attribution remains uncertain. The threat actors' operational security and exploitation of third parties highlight the need for organizations to enhance defenses and vigilance. The report provides technical details, indicators of compromise, malware descriptions, MITRE ATT&CK techniques observed, and recommendations for remediation. The threat actors' capabilities and tactics underscore the need for organizations to strengthen cybersecurity defenses and remain vigilant against evolving threats. (Date: Dec 06, 2021 - Nov 29, 2022)





Report 33

APT29, also known as The Dukes or Cozy Bear, is a cyberespionage group believed to operate under the Russian Foreign Intelligence Service (SVR) or the Russian Federal Security Service (FSB). They primarily target western governments, government ministries, agencies, political think tanks, and governmental subcontractors. APT29 is known for its stealthy tactics, blending network traffic with legitimate traffic by using compromised servers and social media sites for Command and Control (C2) infrastructure. They have used encrypted data in images for message delivery and to blend in. The group has been active since at least 2008, with notable campaigns targeting various countries and organizations. APT29's malware families include SeaDuke, PowerDuke, MiniDuke, PolyglotDuke, RegDuke, LiteDuke, and FatDuke, each with specific functionalities and communication methods. The threat actor's use of common string encryption routines and sophisticated detection evasion techniques make them challenging to detect. APT29's capabilities and continued targeting of government entities globally, especially during election periods, indicate their persistence and threat to national security. The report covers campaigns and malware used by APT29 from 2008 to 2019, showcasing their evolving tactics and capabilities.





Report 34

APT29, also known as Cozy Bear or The Dukes, targeted a European diplomatic entity in early 2022 by abusing the Windows Credential Roaming feature. Mandiant has been tracking APT29, a Russian espionage group sponsored by the Foreign Intelligence Service (SVR), since at least 2014. The threat actor was observed performing LDAP queries with atypical properties against the victim's Active Directory system. A novel technique used by APT29 involved exploiting the Credential Roaming feature, introduced in Windows Server 2003 SP1, to synchronize certificates and credentials between devices. A vulnerability (CVE-2022-30170) was identified in the Credential Roaming service, allowing for arbitrary file write and remote code execution. Microsoft released patches to address this issue in September 2022. The attacker's perspective highlighted scenarios where attackers could abuse Credential Roaming for privilege escalation. Organizations are advised to apply the necessary patches and investigate past use of Credential Roaming to ensure proper clean-up. This report provides valuable insights into APT29's tactics and the exploitation of Windows Credential Roaming.





Report 35

Summary:
APT29, also known as Cozy Bear or The Dukes, is a Russian espionage group tracked by Mandiant since 2014, likely sponsored by the Foreign Intelligence Service (SVR). They have been conducting extensive phishing campaigns targeting diplomatic organizations in Europe, the Americas, and Asia since early 2021. APT29 has been observed utilizing new malware families in 2022, BEATDROP and BOOMMIC, to evade detection through retooling and abuse of Atlassian's Trello service for command and control. The phishing emails masquerade as administrative notices related to embassies and use legitimate but compromised email addresses. APT29 has shown an operational shift in their tactics, moving from BEATDROP to a novel C++ BEACON loader in their latest campaigns. They have been observed quickly escalating privileges, conducting reconnaissance, lateral movement, and maintaining presence within compromised environments. The group's goal appears to be long-term access for intelligence collection purposes. Mandiant anticipates sustained waves of phishing activity by APT29 employing novel tools and infrastructure to hinder detection, likely directed against diplomatic missions and foreign policy information. The recent geopolitical events, such as the invasion of Ukraine, are expected to influence the intensity and urgency of APT29's collection operations. The malware families utilized by APT29 include BEATDROP, BOOMMIC, ROOTSAW, and BEACON, with various technical indicators and MITRE ATT&CK TTPs associated with their activities. The report provides detailed insights into APT29's sophisticated cyber operations and their evolving tactics to achieve their espionage objectives. (Source: Mandiant)





Report 36

Summary:
- Threat actor APT29, also known as Cozy Bear or The Dukes, merged with UNC2452, a Russia-based espionage group.
- APT29 is a highly sophisticated threat actor sponsored by the Russian Foreign Intelligence Service (SVR).
- The threat actor has been active since at least 2014 and has shown a high operational tempo and scale, targeting diplomatic entities in Europe, North America, and Asia.
- APT29 targets Western and European governments, as well as industries like education, telecommunications, and medical research entities.
- The threat actor focuses on gaining access to email mailboxes, cloud-based resources, and source code repositories.
- APT29 uses advanced tradecraft, varying intrusion vectors, and heightened operational security (OPSEC) to avoid detection.
- The threat actor has a proven ability to adapt quickly during operations, bypassing security controls and maintaining access through remediation efforts.
- APT29 has a strong understanding of Microsoft tools and cloud environments, allowing them to move easily between on-premises and cloud resources.
- The threat actor has evolved to maintain a light malware footprint and uses innovative techniques to gain persistent access to targets.
- Mandiant predicts that APT29 will continue to evolve its operational and behavioral tactics based on its advanced skillset and ability to creatively employ novel tools and techniques.


