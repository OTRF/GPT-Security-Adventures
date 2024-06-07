
Report 1

Malformed report





Report 2

Malformed report.





Report 3

Summary:
The threat actor Turla, also known as Waterbug or Venomous Bear, has been observed using a new .NET/MSIL dropper for the existing backdoor JS/KopiLuwak in a G20-themed attack. The attack involves delivering a benign decoy document inviting recipients to a G20 task force meeting on the "Digital Economy". The dropper first appeared in mid-July, indicating ongoing APT activity targeting G20 participants, member nations, journalists, and policymakers. Turla is a well-documented, long-operating APT group believed to be Russian state-sponsored. The dropper contains no obfuscation or anti-analysis, and the backdoor is capable of exfiltrating data, downloading payloads, and executing commands. The attack is sophisticated, with evidence suggesting the decoy document is legitimate and not fabricated. The threat actor's continued development of the backdoor and new delivery mechanisms indicate future use of the tool. The full scope and impact of the attack cannot be fully assessed, but the potential impact on PCs running the .NET framework is high. Proofpoint researchers have notified CERT-Bund of this activity. The attack involves various indicators of compromise, including IOCs for the dropper, decoy document, and command and control servers. Suricata/Snort coverage is available for detection. The threat actor's capabilities and targeting of high-profile individuals associated with the G20 warrant further monitoring. 

Date: August 17, 2017

Region: Global

Operating Sector: Various sectors, including potentially government, technology, and media

Type of Company of Victims: Not specified

Novelty of Tools and Techniques: The threat actor Turla's use of a new .NET/MSIL dropper for the existing backdoor JS/KopiLuwak in a G20-themed attack showcases the sophistication and evolving capabilities of the threat actor. The lack of obfuscation or anti-analysis in the dropper, along with the backdoor's ability to exfiltrate data and download payloads, highlights the advanced nature of the attack. The use of a legitimate decoy document and the actor's continued development of the backdoor and delivery mechanisms demonstrate the novelty and adaptability of the tools and techniques used.





Report 4

Malformed report





Report 5

Summary:
- Threat actor: Turla, Waterbug, Venomous Bear
- Date: 14 May 2020
- Region: Europe
- Operating sector: Diplomatic entities
- Type of company: Not specified
- Evidence of capability: Developed a new Trojan with strong code similarities to COMpfun, focusing on diplomatic entities in Europe. Utilized rare HTTP status codes for C2 communication, RSA encryption, and AES-128 key generation. Capable of geolocation tracking, data gathering, keylogging, screenshots, and self-propagation to removable devices.
- Novelty of tools and techniques: Used HTTP status codes for C2 communication, RSA encryption for data exfiltration, LZNT1 compression, and one-byte XOR encryption for data hiding. Implemented unique features like geolocation using legitimate web services and thread synchronization timeout calculation.
- Malware indicators: Trojan 32-bit MD5: A6AFA05CBD04E9AF256D278E5B5AD050, Trojan 64-bit MD5: 1BB03CBAD293CA9EE3DDCE6F054FC325, IPs: 95.183.49.10, 95.183.49.29, 200.63.45.35.





Report 6

Summary:
The threat actor known as Turla, Waterbug, or Venomous Bear has been identified as the operator behind the Reductor malware, a successor to the COMpfun malware. The Reductor malware is capable of compromising encrypted web communications by manipulating digital certificates and marking outbound TLS traffic with unique host-related identifiers. The threat actor has exclusive capabilities to replace legitimate installers with infected ones on the fly, indicating a high level of control over the target's network channel. The Reductor malware was developed by the authors of the COMPfun Trojan, with strong code similarities between the two families. The campaign using Reductor started in April 2019 and targeted victims in Russia and Belarus. The threat actor uses innovative techniques, such as patching browser PRNG functions to mark TLS traffic without directly touching network packets. The Reductor malware spreads through infected software installers and leverages the COMpfun Trojan for distribution. The threat actor demonstrates creativity and sophistication in their malware design and infection methods. The campaign aligns with previous Turla interests, showcasing the threat actor's advanced capabilities and strategic targeting.





Report 7

Summary:
The threat actor known as Turla, Waterbug, or Venomous Bear has been targeting various institutions for many years, with recent discoveries of new versions of Carbon, a second stage backdoor in their arsenal. The group operates in a meticulous and staged manner, conducting reconnaissance before deploying sophisticated tools like Carbon. The Carbon backdoor is used to steal sensitive information and shares similarities with the Uroburos rootkit. The group regularly updates their tools and changes file names and mutexes between versions to evade detection. Carbon's architecture includes components for installation, communication with the C&C, task handling, and code injection. The threat actor uses encryption, mutexes, and P2P communication channels to maintain stealth and persistence. The group also injects a communication library into remote processes and supports additional plugins for extended functionalities. The threat actor checks for packet capture software and ensures internet availability before communication. The Carbon framework encrypts files with CAST-128 and uses RSA keys for secure communication with the C&C server. The threat actor's tools and techniques show sophistication and continuous development, posing a significant threat to targeted institutions. The report was published on March 30, 2017, by ESET Research.





Report 8

Summary:
- Threat actor: Turla, Waterbug, Venomous Bear
- Region: Eastern Europe, specifically focused on Ukraine
- Operating sector: Government, media organizations, financial sector, NGOs, think tanks, journalists
- Date: July 19, 2022
- Turla group attributed to Russia's FSB distributed Android apps for DoS attacks against Russian websites, hosted on a domain spoofing the Ukrainian Azov Regiment.
- Pro-Ukrainian developers created the StopWar app, inspiring Turla's CyberAzov DoS app.
- Russian GRU actors exploited the Follina vulnerability (CVE-2022-30190) after it was patched by Microsoft.
- Financially motivated actors targeted Ukraine using the Follina exploit in password-protected archives.
- Ghostwriter/UNC1151 targeted Polish users with phishing techniques.
- COLDRIVER targeted government officials, politicians, NGOs, journalists with credential phishing emails.
- Malicious campaigns observed leveraging compromised email addresses of a Regional Prosecutor's office of Ukraine to deliver Cobalt Strike via malicious Microsoft Excel documents with VBA macros.





Report 9

Malformed report





Report 10

Malformed report.





Report 11

Summary:
The Turla APT Group, also known as Waterbug and Venomous Bear, is a highly sophisticated threat actor targeting government entities, intelligence agencies, military, educational, research, and pharmaceutical industries globally. Operating since at least 2004, Turla stands out for its satellite-based command-and-control mechanism and ability to fly under the radar. The group has used complex tools like Carbon, Kazuar, Gazer, Neuron, Nautilus, ComRAT v4, and Crutch, with novel techniques such as Linux targeting, phishing campaigns, and backdoors written in .NET and Python. Turla's recent activities include the emergence of TinyTurla, a reconnaissance campaign in May 2022, and attacks using Capibar and Kazuar in July 2023 targeting Ukrainian defensive assets. The threat actor continues to evolve its tools and techniques, emphasizing the need for organizations and governments to remain vigilant and implement robust security measures.





Report 12

Malformed report.





Report 13

Summary:
- Threat Actor: Turla, Waterbug, Venomous Bear
- Region: Not specified
- Operating Sector: Not specified
- Type of Company: Not specified
- Date: February 19, 2021
- Evidence of Capability: Unit 42 researchers discovered IronPython scripts used by Turla to load and run malware tools on victim systems, utilizing the Bring Your Own Interpreter (BYOI) method. The IronNetInjector toolchain, a blend of IronPython and an embedded process injector, was identified as a new malware loading tool. The toolchain includes obfuscated function and variable names, encrypted strings, and the ability to load .NET assemblies or native PEs into processes.
- Novelty of Tools and Techniques: The IronNetInjector toolset represents a shift from PowerShell towards .NET, likely due to improved detection of PowerShell-based threats. The toolset contains clean code with detailed log and error messages, and the IronPython scripts are obfuscated to avoid detection. The toolset is primarily used to load ComRAT malware, with some instances of the RPC backdoor and unknown payloads. The method of running IronPython scripts and deploying the interpreter to victim systems remains unclear.





Report 14

The threat actor known as Turla, Waterbug, or Venomous Bear has been linked to the development and use of the Kazuar backdoor Trojan, a multiplatform espionage tool written in the .NET Framework. The Kazuar Trojan offers complete access to compromised systems and includes a unique feature of exposing its capabilities through an API to a built-in webserver. Evidence suggests that the Turla threat actor group has used Kazuar in attacks targeting embassies, defense contractors, educational institutions, and research organizations globally. The Kazuar malware has a sophisticated command set and the capability to remotely load additional plugins to enhance its functionality. The threat actor group behind Kazuar has been known to iterate their tools, with code lineage tracing back to at least 2005. The Kazuar Trojan is notable for its cross-platform capabilities, with code paths for Unix systems, and its remote API functionality that allows actors to issue commands via inbound HTTP requests. The threat actor group using Kazuar has been observed using compromised WordPress blogs as command and control servers. The Kazuar Trojan's extensive command set includes unique commands for cross-platform functionality, plugin administration, and a remote API for interacting with compromised systems. The threat actor group behind Kazuar may compile payloads for both Windows and Unix systems using the same codebase. The Kazuar backdoor Trojan is a tool of interest due to its novel features and capabilities, making it important to monitor for potential future attacks.





Report 15

Summary:
- Threat actor: Turla APT (also known as Waterbug, Venomous Bear)
- Date: December 9, 2014
- Region: Primarily targeting municipal governments, embassies, militaries, and industrial targets in the Middle East and Europe
- Operating sector: Critical Infrastructure, Government, Web Security
- Novelty of tools and techniques: Turla APT campaigns expanded to infect Linux servers, previously focused on Windows systems; Linux version of Turla backdoor based on public sources like cd00r; uses TCP/UDP packets for command and control; Linux variant first sample caught in the wild
- Evidence of capability: Used in espionage campaigns, combination of commodity exploits and zero-day attacks, infected over 100 websites including government sites and enterprises
- Connection to other threats: Linked to Agent.btz worm, shares characteristics but authors not linked
- Tools used: Backdoor based on cd00r, ELF executable linked against GNU C library, OpenSSL, libpcap
- Impact: Allows undetected remote commands, interception of packets without root access
- Conclusion: Turla APT shows sophistication in targeting critical infrastructure and government entities with advanced tools and techniques.





Report 16

Summary:
- Threat actor: Turla, Waterbug, Venomous Bear
- Region: Ukraine and Eastern Europe
- Operating sector: Defense industry
- Type of company: Microsoft Exchange servers
- Date: July 19, 2023
- Evidence of capability: Turla threat actors targeted defense sector with new 'DeliveryCheck' malware backdoor, exfiltrated data using Rclone tool, utilized Microsoft Exchange server-side component to turn servers into malware control centers, dropped KAZUAR information-stealing backdoor
- Novelty of tools and techniques: Use of PowerShell command, scheduled task impersonating Firefox browser updater, embedding and launching malware payloads from XSLT stylesheets, installation of malware-distribution server on Exchange servers using Desired State Configuration
- Detection rate: Only 14/70 vendors on VirusTotal detected DeliveryCheck sample as malware, expected to increase

Malformed report.





Report 17

Summary:
The report discusses the possible connection between the historical APT attack known as Moonlight Maze, which targeted the Pentagon and NASA in the late 1990s, and the modern-day threat actor Turla. The investigation reveals that Turla, an active group, may have ties to the Moonlight Maze campaign. Evidence suggests that Turla utilized backdoors based on the Unix program LOKI2, dating back to 1996, indicating a long-standing capability of the threat actor. The use of Linux backdoors in Turla, detected by Kaspersky Lab in 2014, further supports the link to Moonlight Maze. The report emphasizes the importance of understanding past cyber incidents to effectively respond to current and future threats. The findings highlight the longevity and adaptability of tools and techniques used by threat actors, with code created over 20 years ago still being utilized in modern attacks. The report was published on April 3, 2017, by Kaspersky Lab.





Report 18

Summary:
The threat actor Turla, also known as Waterbug or Venomous Bear, has been active for at least ten years, targeting governments and sensitive businesses such as the defense industry. In January 2018, a campaign called Mosquito was analyzed, revealing a shift towards more generic tools, including the use of the open-source exploitation framework Metasploit. This marks a significant change in Turla's Tactics, Techniques, and Procedures (TTPs). The typical vector of compromise involves a fake Flash installer targeting embassies and consulates in Eastern Europe. The threat actor uses Metasploit shellcode to drop a legitimate Flash installer before deploying the Mosquito backdoor. The campaign shows evidence of manual exploitation control and utilizes various tools for persistence and privilege escalation. The evolution of the Turla Mosquito campaign highlights the threat actor's adaptability and sophistication in utilizing novel tools and techniques. The report was published on May 22, 2018, by ESET Research.





Report 19

Summary:
- Threat actor: Pensive Ursa (aka Turla)
- Region: Russian-based threat group operating since 2004, linked to the Russian Federal Security Service (FSB)
- Victims: Ukrainian defense sector targeted in July 2023
- Operating sector: European government and military organizations
- Date: October 31, 2023
- Novelty: Discovered a new, upgraded variant of Kazuar backdoor used by Pensive Ursa, with advanced anti-analysis techniques, encryption, and obfuscation practices. Kazuar targets cloud, source control, and messaging apps for credential theft. It supports over 40 distinct commands, half of which were previously undocumented. The threat actor uses hijacked legitimate websites for C2 infrastructure and communication over named pipes for peer-to-peer communication. Kazuar employs robust anti-analysis checks, including honeypot, analysis tools, and sandbox checks. The malware strengthens its connection to Pensive Ursa through similarities in functionality with Carbon. Cortex XDR provides detection and prevention against Kazuar. Palo Alto Networks customers receive protections and mitigations against this threat.





Report 20

Summary:
The threat actor known as Turla, Waterbug, or Venomous Bear has been identified as using satellite-based Internet links for command and control operations. This unique method allows the threat actor to mask their operations and avoid detection. The Turla group has been active for over 8 years and is known for its sophisticated tools, including the Uroboros rootkit. The use of satellite-based C&C mechanisms by the Turla group is considered novel and provides a high level of anonymity. The threat actor hijacks downstream bandwidth from various ISPs and uses packet-spoofing techniques. The Turla group has been observed abusing satellite DVB-S Internet providers in the Middle East and Africa. This method of attack is relatively inexpensive and easy to deploy, making it a significant concern for the IT security and counter-intelligence communities. Other APT groups, such as HackingTeam and Rocket Kitten, have also been known to use satellite-based Internet links. The Turla group's use of satellite-based Internet links poses a serious threat to cybersecurity and highlights the need for advanced defense strategies.





Report 21

Summary:
The threat actor Turla, also known as Venomous Bear, Waterbug, and Uroboros, has been active since at least 2015, targeting NATO-related entities and a broader range of victims. Recent activity includes the deployment of the KopiLuwak javascript backdoor, new variants of the Carbon framework, and changing delivery techniques for the Mosquito backdoor. The threat actor has shown capability in using advanced malware families like KopiLuwak, Carbon, Mosquito, and WhiteBear, with a focus on selective targeting of high-value entities. Novel techniques include MiTM attacks for delivering Mosquito backdoors and the use of .lnk files for KopiLuwak delivery. The threat actor's ongoing activities suggest a focus on diplomatic, foreign affairs, scientific, and energy research organizations, with a prediction of continued development and deployment into 2019. The Turla threat actor demonstrates a high level of sophistication and adaptability in their tools and techniques, making them a persistent and evolving threat in the cybersecurity landscape.





Report 22

Turla, also known as Snake, Waterbug, and Venomous Bear, is a sophisticated cyberespionage group targeting research, diplomatic, and military organizations worldwide, with a focus on NATO and CIS nations. They develop unique, advanced malware and tools, alongside open source and older techniques, making them an active, advanced threat. In June 2019, Turla infiltrated APT34's infrastructure, an unprecedented action, showing opportunistic behavior. They heavily rely on PowerShell scripts, target Microsoft vulnerabilities, and use compromised WordPress sites for C2 infrastructure. Turla's use of APT34's tools was likely uncoordinated and hostile, deceiving incident responders. They have also developed the Reductor RAT, showcasing continuous innovation. Turla is a well-funded, advanced threat group that will continue to surprise with unique operational concepts, while their consistent patterns may allow for proactive tracking of their activities.





Report 23

Summary:
- Threat actor: Turla, also known as Waterbug, Venomous Bear
- Region: Eastern Europe
- Operating sector: Defense, Economic Chamber, NATO eLearning platform
- Date: May 23, 2022
- Turla conducted a new phishing-based reconnaissance campaign targeting the Baltic Defense College, Austrian Economic Chamber, and NATO's eLearning platform in Eastern Europe.
- Turla, a Russian-speaking cyber espionage group believed to be operated by the FSB, used typosquatting domains to target these institutions.
- Novelty: Turla used a phishing campaign with Word documents containing external PNG files for reconnaissance purposes, leveraging HTTP requests for victim information.
- Evidence of capability: Turla has a history of targeting sensitive networks, including breaching US Department of Defense networks in the past.
- The phishing campaign aimed to gather information on defense sector interests, economic sanctions, and military strategies in Eastern Europe.
- Turla's use of tailored exploits based on victim's Word application version and monitoring capabilities through SIGINT were highlighted.
- The campaign showcased Turla's sophisticated tactics and interest in geopolitical developments in the region.





Report 24

Summary:
The threat actor known as Turla, Waterbug, or Venomous Bear has been conducting a massive cyber-espionage operation called "Epic Turla" targeting government institutions, embassies, military, education, research, and pharmaceutical companies in over 45 countries, primarily in Europe and the Middle East. The threat actor has used sophisticated techniques, including zero-day exploits, social engineering, and watering hole attacks to infect victims. The primary backdoor used in the attacks is known as "WorldCupSec," "TadjMakhal," "Wipbot," or "Tavdig." The threat actor has demonstrated the capability to upgrade to more sophisticated backdoors, such as the Carbon/Cobra system, to maintain persistence and conduct lateral movement within victim networks. The attacks are ongoing as of July 2014, with recent activity observed in August 2014. The threat actor's use of multiple tools and techniques, as well as their dynamic approach to exploiting vulnerabilities, indicates a high level of sophistication and persistence in their operations.





Report 25

Summary: The threat actor known as Turla, Waterbug, or Venomous Bear has recently updated the malware it uses against UK targets. The group has been active in targeting victims in the UK region, particularly in the government and military sectors. Evidence suggests that the threat actor has advanced capabilities and is constantly evolving its tools and techniques to avoid detection. The latest update to their malware indicates a high level of sophistication and a continued focus on cyber espionage activities. The operation time window for this activity was not specified in the report.





Report 26

Summary:
The threat actor known as Turla, also referred to as Pensive Ursa, is a Russian-based group linked to the Russian Federal Security Service (FSB) operating since at least 2004. They have targeted victims in over 45 countries across various sectors, including government entities, embassies, military organizations, education, research, and pharmaceutical companies. The group has been active in the Russian-Ukraine conflict since February 2022, targeting the defense sector in Ukraine. Turla's arsenal includes advanced malware such as Capibar, Kazuar, Snake, QUIETCANARY, Kopiluwak, Crutch, ComRAT, Carbon, HyperStack, and TinyTurla. The group's innovative stealth techniques and targeted intrusions have been highlighted by MITRE, with an evaluation scheduled for late September 2023. Palo Alto Networks' Cortex XDR provides multilayered defense against Pensive Ursa's malware, with Advanced WildFire accurately identifying samples related to the group as malicious. The threat actor's use of novel tools and techniques, such as custom communication protocols, kernel modules for stealth, and keylogger functionality, demonstrate their high level of software development capability. The group's persistence and exfiltration capabilities, as seen in the Snake malware, highlight their advanced technical expertise. The report provides indicators of compromise for each malware variant and emphasizes the importance of comprehensive security strategies to mitigate the threat posed by APT groups like Turla.





Report 27

Turla, also known as Waterbug and Venomous Bear, is a Russian-based threat group that has been active since 1996. The group has targeted victims in over 45 countries across various sectors including government, embassies, military, education, research, and pharmaceutical companies. Turla is known for conducting watering hole and spear-phishing campaigns and using in-house tools and malware to target Windows, macOS, and Linux machines. The threat actor has been involved in numerous high-profile operations such as "Moonlight Maze" in 1996, "Epic Turla" in 2013, and "Penguin Turla" in 2014. Turla has also been linked to breaches of organizations like the US Department of Defense and Swiss military firm RUAG. The group has continuously evolved its tools and techniques, with new backdoors like "Crutch" and "NewPass" being discovered in recent years. Turla's extensive reach and sophisticated capabilities make it a significant threat in the realm of cyber espionage.





Report 28

Malformed report.





Report 29

Summary:
The threat actor Turla, also known as Waterbug or Venomous Bear, has been active for over ten years and has targeted various governments, especially diplomatic entities worldwide. ESET researchers discovered a new backdoor named Crutch used by Turla to exfiltrate stolen documents to Dropbox. The Crutch malware family was used from 2015 to early 2020 and was found on the network of a Ministry of Foreign Affairs in a European Union country. The threat actor has strong links to other Turla malware families like Gazer. Crutch has evolved from version 1 to version 4, with the latest version having networking capabilities for automatic file uploads to Dropbox. The threat actor's espionage activities include reconnaissance, lateral movement, and exfiltration of sensitive documents. The operators have a sense of humor, as evidenced by their commands. The working hours of the operators suggest they operate in the UTC+3 time zone. Crutch's capability to bypass security layers by using legitimate infrastructure like Dropbox showcases the threat actor's sophistication and resources. The threat actor's use of novel techniques and tools like Crutch highlights their continuous development of new backdoors. The report provides indicators of compromise and MITRE ATT&CK techniques associated with the threat actor.





Report 30

Turla, also known as Venomous Bear, has recently updated its arsenal with a new implant named "NewPass" that was observed in an attack in June 2020. The hacking group targeted at least one European Union country in the sector of diplomacy and foreign affairs. The malware, composed of different components, uses encoded files to pass information and configuration between each other. The dropper used by the threat actor has a large size of about 2.6 MB and exports a high number of functions to avoid sandbox analysis. The loader library decodes the configuration file and reads the current configuration to launch the final agent responsible for exfiltrating information. The agent communicates with the command-and-control server using encrypted HTTP requests with specific keywords. The malware supports different persistence mechanisms and uses custom encryption algorithms. The threat actor's activities align with various techniques from the ATT&CK Matrix, including execution, persistence, defense evasion, command and control, and exfiltration. The indicators of compromise include SHA256 hashes and the domain "newshealthsport.com." The operation was observed in July 2020.





Report 31

Summary:
The threat actor Turla, also known as Venomous Bear, Waterbug, and Uroboros, is a Russian-speaking group targeting diplomatic and government-related entities in regions such as the Middle East, Central and Far East Asia, Europe, North and South America, and former Soviet bloc nations. In 2019, Turla renewed its arsenal with a new tool called Topinambour, which includes modules for delivering the KopiLuwak JavaScript Trojan and a heavily obfuscated PowerShell Trojan. The threat actor used legitimate software installers infected with the Topinambour dropper to spread the malware, with campaign-related VPSs located in South Africa. The Topinambour campaign includes Easter eggs for targets and researchers, such as strings like "TrumpTower" and "RocketMan!" in the malware. The threat actor's use of multiple languages and encryption keys aims to avoid detection, with the campaign attributed to Turla due to the use of the KopiLuwak artifact. The campaign also involved a PowerShell Trojan named MiamiBeach, demonstrating the threat actor's advanced capabilities in developing and deploying sophisticated malware.





Report 32

Summary:
- Threat actor: Turla, Waterbug, Venomous Bear
- Region: Eastern Europe
- Operating sector: Critical infrastructure entities including oil and gas, telecommunications, manufacturing, defense, cybersecurity, government, military, logistics, and manufacturing organizations
- Date: May 03, 2022
- Evidence of capability: APT28/Fancy Bear targeting users in Ukraine with new malware variant, Turla targeting defense and cybersecurity organizations in the Baltics, COLDRIVER using Gmail for credential phishing, Ghostwriter targeting high-risk individuals in Ukraine, Curious Gorge active against government, military, logistics, and manufacturing organizations in Ukraine, Russia, and Central Asia
- Novelty of tools and techniques: Malware distributed via email attachments in password-protected zip files, unique links per target leading to malicious files, phishing emails linking to PDFs and DOCs hosted on Google Drive and Microsoft One Drive, credential phishing via compromised websites, domain spoofing, and government-backed attacker alerts to targeted users.


