
Report 1

Malformed report





Report 2

Malformed report





Report 3

Summary:
APT34, also known as OilRig, Helix Kitten, or Chrysene, deployed a phishing attack with new malware called Menorah. The attack targeted a victim in Saudi Arabia using a fake license registration form of an African government agency. The malware was designed for cyberespionage, capable of identifying the machine, reading and uploading files, and downloading other malware. APT34 is a covert cyberespionage group operating in the Middle East, targeting organizations and engaging in illicit activities. The malware variant used in this attack, similar to SideTwist, showed sophistication in its infection routine and capabilities. The group's continuous development and use of novel techniques pose a significant cybersecurity challenge. The attack process, infrastructure, and capabilities of the malware were analyzed, highlighting the group's evolving tactics. The report provides indicators of compromise (IOCs) for detection and mitigation. The report was published on Trend Micro's website in August.





Report 4

Summary:
APT34, also known as OilRig/COBALT GYPSY/IRN2/HELIX KITTEN, targeted the Jordan Government on April 26, 2022, using a new Saitama backdoor. The threat actor, attributed to the known Iranian group APT34, has been active since at least 2014, focusing on financial, governmental, energy, chemical, and telecommunication sectors in the Middle East and globally. The attack involved a malicious Excel document with a macro that executed various malicious activities, including DNS communication for command and control. The Saitama backdoor, written in .Net, utilized a finite-state machine for its operations, abusing DNS for stealthy communications. The threat actor demonstrated capabilities such as compression, long random sleep times, and predefined commands for reconnaissance. The attack showed similarities to previous APT34 campaigns in terms of maldoc structure, victim targeting, and communication methods. Malwarebytes customers were protected from this attack.





Report 5

Malformed report





Report 6

Malformed report.





Report 7

Summary:
The threat actor known as APT34, also referred to as OilRig, Helix Kitten, and Chrysene, has been identified as an Iran-nexus cluster of cyber espionage activity since at least 2014. Operating primarily in the Middle East region, APT34 targets industries such as energy, utilities, government, and oil and gas, with a focus on financial, energy, and government entities. In a recent phishing campaign identified by FireEye in June 2019, APT34 used tactics such as masquerading as a member of Cambridge University and utilizing LinkedIn to deliver malicious documents. The threat actor introduced three new malware families, including TONEDEAF, VALUEVAULT, and LONGWATCH, showcasing their evolving capabilities. APT34's use of PowerShell development and Golang indicates a novel approach to cyber espionage. The threat actor's persistence and sophistication in targeting key organizations align with Iran's strategic intelligence goals. The activity observed highlights the need for organizations to remain vigilant in their defenses against evolving threats. The report provides detailed technical analysis of the malware families used by APT34, emphasizing the importance of proactive cybersecurity measures. The report was published by Mandiant on July 18, 2019, with ongoing updates on the threat actor's activities.





Report 8

The threat actor known as Helix Kitten, also identified as APT34, OILRIG, and Chrysene, is an Iranian hacker group involved in cyberespionage and cyberwarfare. The group has been active since at least 2014 and has targeted organizations in the financial, energy, telecommunications, and chemical industries, as well as critical infrastructure systems. Helix Kitten utilizes Microsoft Excel macros, PowerShell-based exploits, and social engineering techniques to gain access to its targets. In April 2019, the source code of APT34's cyber-espionage tools was leaked through Telegram. The group's capabilities and novel techniques pose a significant threat to organizations in various sectors. (Date of last edit: February 14, 2024)





Report 9

Summary:

The threat actor known as Helix Kitten, likely Iranian-based, has been active since late 2015, targeting organizations in various sectors including aerospace, energy, financial, government, hospitality, and telecommunications. They use a custom PowerShell implant called Helminth delivered through macro-enabled Microsoft Office documents for spear-phishing attacks. They also utilize the ISMDoor implant for attacks in the Middle East region, with infrastructure overlaps with ISMAgent. The actor uses DNS transport layer protocol for command and control, with dedicated domains for C2 infrastructure. In the summer of 2018, they targeted entities in Bahrain and Kuwait, and in November 2018, they were observed targeting a customer in the telecommunications sector. This shift in targeting suggests a potential for bulk data collection and rerouting communications. The ultimate objective remains unclear, but the addition of the telecommunications sector to their target scope is a notable development. The threat actor is associated with names like OilRig, APT34, and IRN2. Their use of novel tools and techniques, along with their evolving targeting strategies, pose a significant threat to organizations in the region.





Report 10

Summary:
- Threat actor: APT34 (also known as OilRig, Helix Kitten)
- Region: Iran
- Operating sector: Various international organizations, mainly in the Middle East
- Type of company targeted: Westat, a US-based company providing research services to US government agencies and businesses
- Date: January 30, 2020
- Evidence of capability: APT34 employed an updated toolset targeting Westat employees or customers, using phishing documents and a highly modified version of the TONEDEAF malware named TONEDEAF 2.0
- Novelty of tools and techniques: TONEDEAF 2.0 contained new stealthy features, dynamic importing, string decoding, and victim deception methods, indicating an evolution in APT34's operations
- Transition to HTTPS for C2 communication observed, possibly to improve OPSEC capabilities
- Usage of a new malware variant, VALUEVAULT 2.0, alongside TONEDEAF 2.0, indicating a more minimalistic approach for browser credential theft
- Conclusion: APT34 has evolved its operations with upgraded toolsets to evade detection, as revealed by technical analysis of new malware variants.





Report 11

Summary:
- Threat actor: APT34 (OilRig, Helix Kitten)
- Operation name: Karkoff 2020
- Target: Lebanon Government
- Date: 03/02/2020
- Evidence of capability: A new implant "Karkoff" used by APT34, targeting Lebanon Government, with changes in techniques and procedures.
- Novelty of tools and techniques: New reconnaissance logic in the Karkoff implant, exploiting Microsoft Exchange Server for communication.
- Evidence of activity: Compromised Microsoft Exchange Server belonging to Lebanon government entity.
- Persistence: Malicious Excel macro embedded in an Excel document, downloading and executing monitor.exe.
- Indicators of Compromise: Hashes and Yara rules provided.
- Conclusion: APT34 continues to improve its cyberespionage capabilities, with evidence of ongoing activity against Lebanon Government.





Report 12

Summary:
In mid-July 2022, the Albanian government was targeted by Iranian state-sponsored threat actors, leading to destructive cyberattacks and data leaks. Microsoft's Detection and Response Team (DART) was engaged to investigate the attacks. Multiple Iranian actors were identified, with DEV-0842 deploying ransomware and wiper malware. DEV-0861 gained initial access and exfiltrated data, while DEV-0166 exfiltrated mail. The threat actors used novel techniques, such as exploiting vulnerabilities in SharePoint servers and using unique email exfiltration tools. The attack involved ransomware and wiper malware with forensic links to Iranian state actors. The threat actors engaged in information operations targeting corrupt government officials and supporting terrorists. Microsoft telemetry and forensic evidence pointed to Iranian state sponsorship of the attacks. The threat actors evaded defenses, exfiltrated data, and deployed encryption and wiping binaries. Microsoft recommends adopting security measures to mitigate such threats. The report provides indicators of compromise and detection methods for customers to investigate and prevent similar attacks. The operation time window was from May 2021 to January 2022.





Report 13

Summary:
APT34, also known as OilRig, Helix Kitten, and Chrysene, targeted organizations in the Middle East for cyberespionage in December 2022 using a new backdoor malware. The threat actor, APT34, has a history of targeting various sectors, including financial, government, energy, chemical, and telecommunications industries in the Middle East. The malware used in this campaign is capable of stealing user credentials and exfiltrating data through compromised email accounts, a technique previously unseen from APT34. The group's evolution in tools and techniques, such as leveraging legitimate mail traffic for data exfiltration, indicates a high level of sophistication and adaptability. The campaign's routine is likely part of a larger chain of deployments, emphasizing the need for organizations to enhance their security measures. The report provides detailed insights into the attack flow, tools used, and indicators of compromise, highlighting the ongoing threat posed by APT34 in the region.





Report 14

Summary:
The threat actor known as OilRig, APT 34, Helix Kitten, Chrysene, has been identified targeting the energy sector in the Middle East with a new destructive wiper called ZeroCleare. The attack, discovered by IBM X-Force, involved the use of sophisticated malware that overwrites the master boot record and disk partitions on Windows-based machines. The attackers, suspected to be Iran-based nation-state adversaries, used living-off-the-land tactics and legitimate tools like EldoS RawDisk to execute the attack. The campaign, which targeted organizations in the energy and industrial sectors, is believed to be one of the first to use this new wiper, indicating the threat actor's evolving capabilities. The attack, attributed to the ITG13 threat group and another Iran-based group, showcases a collaboration between threat actors for a complex, targeted operation. The attack aligns with Iranian objectives in the region and highlights the rising concern of destructive attacks on critical infrastructure, particularly in the energy sector. The use of destructive malware like ZeroCleare poses a significant risk to organizations, emphasizing the importance of early detection, defense-in-depth strategies, and effective response plans to mitigate the impact of such attacks.





Report 15

Summary:
- Threat actor: APT34, also known as OilRig, Helix Kitten, Chrysene, suspected to be an Iranian threat group.
- Region: Middle East, with a focus on government organizations.
- Operating sector: Targeted industries include financial, government, energy, chemical, and telecommunications.
- Evidence of capability: APT34 has been operational since at least 2014, using a mix of public and non-public tools, including spear phishing and social engineering tactics.
- Novelty of tools and techniques: APT34 leveraged the CVE-2017-11882 exploit to deploy custom PowerShell backdoors POWRUNER and BONDUPDATER, demonstrating the group's ability to quickly incorporate exploits for targeting.
- Date: The report was published on Dec 7, 2017, with ongoing observations until Nov 28, 2022.
- Conclusion: APT34's continuous updates to malware and incorporation of DGA for C2 communication indicate a commitment to evolving tactics for targeting entities in the Middle East region.





Report 16

OilRig, also known as APT 34, Helix Kitten, and Chrysene, is a threat group with suspected Iranian origins that has been active since at least 2014. The group has targeted a variety of industries, including financial, government, energy, chemical, and telecommunications, primarily within the Middle East region. Evidence suggests that OilRig carries out supply chain attacks and works on behalf of the Iranian government. The threat actor has been observed using a wide range of tools and techniques, including Alma Communicator, Mimikatz, and ZeroCleare, among others. OilRig has been involved in various hacking operations, such as the Shamoon Attacks in 2012 and the deployment of new Trojans like OopsIE in 2018. The threat actor has also been linked to destructive malware like Shamoon v2 and v3. Counter operations against OilRig include the leak of hacking tools belonging to the group in 2019, possibly orchestrated by the CIA. OilRig continues to be a significant threat, with new campaigns and malware targeting the Middle East region as recently as 2022.





Report 17

Summary:
- Threat actor: OilRig, also known as APT 34, Helix Kitten, Chrysene
- Region: Middle East
- Operating sector: financial, government, energy, chemical, telecommunications
- Capability: Supply chain attacks, sophisticated spear phishing campaigns
- Novelty of tools and techniques: Evolution in delivery, exploit, install, and command techniques over time
- Date: Techniques evolution analyzed from 2016 to August 2019
- Evidence: MITRE reference codes used to analyze techniques
- Attribution: Suspected Iranian origins, targeting aligns with nation-state interests
- Evolution: Introduction of custom command and control protocols, layered security in control techniques
- Notable technique: Process Hollowing used in group_b, seen as unique and not previously observed
- Source: Marco Ramilli Web Corner, August 7, 2019





Report 18

OilRig threat actors, also known as APT 34, Helix Kitten, and Chrysene, were observed engaging in development and testing activities in April 27, 2017. The actors were seen modifying their ClaySlide delivery documents to evade antivirus detection, showcasing a structured approach to tool development. Two separate testing efforts were identified in June and November 2016, revealing the threat group's organized and professional operations model. The testing activities involved iterative changes to evade detection, such as modifying decoy contents, function names, and payload locations. The threat actors displayed a high level of sophistication in their testing techniques, including the use of base64 encoding and hexadecimal representation to obfuscate commands. The testing activities ceased with a low antivirus detection rate, indicating the actors' satisfaction with the results. The OilRig threat group's capability and novel techniques in tool development highlight their intent to use their delivery documents effectively over extended periods with subtle modifications to remain undetected.





Report 19

OilRig, also known as APT 34, Helix Kitten, and Chrysene, has been identified as a threat actor group operating in the Middle East targeting organizations, specifically the government of the United Arab Emirates. Evidence suggests that the threat group has been developing new Trojans, including ISMAgent and ISMInjector, to enhance their attacks. The ISMInjector Trojan, discovered in August 2017, is a sophisticated tool with anti-analysis techniques not seen in previous tools used by the group. The group used spear-phishing emails with malicious delivery documents to target victims, showing a novel approach in their attack methods. The delivery documents contained malicious macros and exploited CVE-2017-0199 to deliver the ISMAgent Trojan. ISMInjector, as the payload delivered by ThreeDollars, is capable of injecting the ISMAgent Trojan into another process, showcasing the group's advanced capabilities. The OilRig group's infrastructure includes C2 domains using typo-squatting techniques to evade detection. The group's use of crypters and state-machines as anti-analysis techniques indicates an increased effort to evade security measures. The OilRig group's consistent victimology, reuse of tools, and infrastructure overlap suggest a unique and previously unknown threat group. The group's activities have been ongoing since at least May 2016, with the latest observed attack in August 2017.





Report 20

OilRig, also known as APT 34, Helix Kitten, and Chrysene, has been actively updating their Clayslide delivery documents and Helminth backdoor. The threat actor has expanded their targets to include organizations in Saudi Arabia, Qatar, Turkey, Israel, and the United States. They continue to use spear-phishing emails with malicious Microsoft Excel documents to compromise victims. The malware used by OilRig has undergone updates, with four distinct variants identified in the past five months. The threat actor uses DNS command and control (C2) techniques to evade detection. The tools and techniques used by OilRig are not highly sophisticated but are continuously being improved upon. The threat actor has been observed targeting high-value companies and organizations globally. The malware deployed by OilRig is detected as malicious by WildFire, and indicators of compromise have been identified. The threat actor behind OilRig is believed to be Iranian-based, with evidence linking them to previous attacks.





Report 21

OilRig, also known as APT 34, Helix Kitten, and Chrysene, targeted a Middle Eastern telecommunications organization in April 2020 using a variant of the RDAT tool with a novel email-based command and control (C2) channel utilizing steganography to hide commands and data within bitmap images attached to emails. The threat actor has been linked to Greenbug and has been active since 2015. The RDAT tool has been under active development since 2017, with multiple variations using HTTP, DNS tunneling, and Exchange Web Services for C2 communications. The use of steganography in email attachments makes detection more challenging. Palo Alto Networks customers are protected against RDAT samples. The threat actor has been targeting organizations in the Middle East, with the most recent activity in April 2020. The RDAT tool has evolved over the years, showing the adversary's continuous development of tactics and techniques. Malicious verdicts are in place for all RDAT samples in WildFire, and DNS tunneling protocols are blocked via DNS Security. The threat actor has used various C2 domains and infrastructure in their operations.





Report 22

OilRig, also known as APT34 or Helix Kitten, is an adversary group primarily motivated by espionage operating in the Middle East region. They have been active since at least mid-2016 and have shown persistence in their operations. Between May and June 2018, OilRig targeted a technology services provider and a government agency in the Middle East, using credential harvesting and compromised accounts. The attacks involved the use of a PowerShell backdoor called QUADAGENT, which is the 12th custom-built tool attributed to OilRig. The delivery of QUADAGENT involved novel techniques such as using a bat2exe tool to generate a PE file and obfuscation using the Invoke-Obfuscation toolkit. The attacks also utilized different delivery methods, including malicious macro documents and simple PE file attachments. The use of open-source tools like Invoke-Obfuscation for obfuscation indicates the group's adaptability and sophistication. OilRig's ability to modify their tools and infrastructure to evade security controls highlights their capability as a threat actor. The attacks were part of a larger campaign observed in three waves, showcasing the group's persistence and evolving tactics. OilRig's focus on the Middle East region and their use of advanced tools and techniques make them a notable threat actor in the cybersecurity landscape.





Report 23

OilRig, also known as APT 34, Helix Kitten, and Chrysene, has been identified using the RGDoor IIS backdoor on targets in the Middle East. The threat actor deployed the RGDoor backdoor on webservers belonging to eight Middle Eastern government organizations, as well as one financial and one educational institution. Unlike previous tools, RGDoor was developed in C++ as a compiled dynamic link library (DLL) to be used as a custom native-code HTTP module in IIS servers. This novel approach allows the threat actor to interact with the backdoor without a visual representation, unlike previous tools like TwoFace. RGDoor is capable of handling HTTP POST requests, parsing cookies, and executing commands such as "cmd$", "upload$", and "download$". The threat actor can install RGDoor using the TwoFace webshell via command-line, and the backdoor communicates with the actor through encrypted HTTP responses. Palo Alto Networks customers are protected from RGDoor with malicious verdicts in WildFire and IPS signatures. The threat actor's use of RGDoor suggests contingency plans to maintain access to compromised networks.





Report 24

OilRig, also known as APT34, targeted Israeli organizations in 2021 and 2022 with the Outer Space and Juicy Mix campaigns, using the same playbook of compromising legitimate websites for C&C communication. The threat actor used a previously undocumented C#/.NET backdoor named Solar in Outer Space and improved it to create the Mango backdoor for Juicy Mix, with additional capabilities and obfuscation methods. OilRig deployed VBS droppers to deliver the backdoors, likely spread via spearphishing emails. The threat actor also used post-compromise tools like the SC5k downloader, which used the Microsoft Office Exchange Web Services API for C&C communication, and browser-data dumpers to steal data from Chrome and Edge browsers. OilRig is a cyberespionage group active since at least 2014, believed to be based in Iran, targeting Middle Eastern governments and various business sectors. The group has a history of campaigns like DNSpionage, HardPass, and DanBot, using novel tools and techniques to exfiltrate data and maintain persistence on compromised systems. The report provides technical analysis of the backdoors, droppers, and post-compromise tools used by OilRig in the Outer Space and Juicy Mix campaigns. The report also includes MITRE ATT&CK techniques used by the threat actor and indicators of compromise (IoCs) for detection and mitigation purposes.





Report 25

OilRig, also known as APT 34, Helix Kitten, and Chrysene, targeted an insurance agency and a financial institution in the Middle East in January 2018. The threat actor attempted to deliver a new Trojan named OopsIE using a variant of the ThreeDollars delivery document. The attack on January 16, 2018, involved delivering the OopsIE Trojan directly to the victim via a link in a spear-phishing email. The OilRig group showed capability in using password-protected documents as an evasion tactic, a novel technique observed for the first time. The OopsIE Trojan was packed with SmartAssembly and obfuscated with ConfuserEx v1.0.0, demonstrating advanced techniques. The threat actor used HTTP to communicate with its C2 server, with specific URLs structured for beaconing and command execution. The OilRig group has been active in the Middle East region, showcasing adaptability in tactics while reusing certain aspects in their attacks. The indicators of compromise for the ThreeDollars and OopsIE payloads were provided, along with related infrastructure details. The report was published on February 23, 2018, by Unit 42.





Report 26

Summary:
- Threat actor: APT34, also known as OilRig, Helix Kitten, Chrysene
- Date: May 11, 2022
- Region: Jordan
- Operating sector: Governmental organization
- Type of company: Not specified
- Evidence of capability: Spearphishing attack targeting a Jordanian diplomat with a malicious Excel file containing advanced techniques like DNS tunneling and stateful programming.
- Novelty of tools and techniques: Unique Excel macro with anti-analysis techniques, malware binary with state programming, DNS tunneling for C2 communications, and a wide range of specific backdoor commands.
- Conclusion: The attack shows a high level of sophistication, resembling an APT attack by APT34, with advanced techniques and careful planning. Fortinet provides protections against the malware used in the attack.





Report 27

Summary:
- Threat actor: OilRig, APT 34, Helix Kitten, Chrysene
- Region: Saudi Arabia
- Operating sector: Oil and Gas
- Type of company: Not specified
- Date: November 29, 2016
- Evidence of capability: Targeted two organizations in Saudi Arabia with destructive attacks using the Disttrack payload, exhibiting knowledge of Virtual Desktop Interface snapshots and obtaining credentials from official Huawei documentation.
- Novelty of tools and techniques: Used a new, similar but different payload with hardcoded account credentials specific to the targeted organization, spread through local networks using legitimate credentials, and overwrote systems with a wiper component using a kernel driver to access and destroy data.
- Conclusion: The threat actors aimed to maximize impact by attacking during off-hours, targeting VDI solutions with stolen or default credentials, and setting a specific "kill time" for wiping systems. Organizations should be aware of these tactics and take immediate steps to evaluate and address vulnerabilities.





Report 28

The report discusses the threat actor known as OilRig, APT 34, Helix Kitten, Chrysene, operating in the Middle East region. The threat actor was found to have a sophisticated infrastructure segregated into different functions for specific malicious objectives, including credential harvesting and command and control. The threat actor used webshells like TwoFace and RunningBee to interact with compromised systems. Novel tools and techniques were identified, such as the use of Mimikatz, PsExec, and a custom Microsoft IIS web server backdoor known as RGDoor. The threat actor also utilized a webshell named LittleFace for passing commands to Windows command prompt. Evidence of a potential link between the threat actor and the OilRig campaign was found through the use of specific tools like Mimikatz. The report highlights the ongoing threat activity in the Middle East region and the need for strong security measures to counter such attacks. The operation time window for this report is September 26, 2017.





Report 29

Summary:
The OilRig campaign targeted financial institutions and technology organizations in Saudi Arabia in May 2016, with evidence of targeting the defense industry as well. The threat actors used spear-phishing emails with malicious Excel spreadsheets to deliver the Helminth backdoor, which had two variants - one in VBScript and PowerShell, and the other as a standalone Windows executable. The VBScript variant communicated with the command and control server using HTTP requests, while the PowerShell variant used DNS queries. The executable variant, installed by the HerHer Trojan, had a keylogger module to log keystrokes and clipboard contents. The threat actors used consistent infrastructure for command and control across both variants, with domains like go0gie[.]com and checkgoogle[.]org. The threat actors may be based in Iran, as indicated by WHOIS data and Persian language artifacts. The campaign was named 'OilRig' and targeted various industries in Saudi Arabia. Palo Alto Networks customers are protected from the Helminth Trojan.





Report 30

Summary:
- Threat actor identified as OilRig, APT 34, Helix Kitten, Chrysene targeted a Middle Eastern organization in a security incident.
- The TwoFace webshell was used by the threat actor to remotely access the network, with a two-layer structure enabling persistent access for almost a year.
- Commands issued by the threat actor included using the Mimikatz tool to gather credentials and move laterally through the network by copying webshells to other servers.
- IP addresses from Iran, France, USA, and Germany were involved in issuing commands to the TwoFace webshell.
- The threat actor also used another webshell named IntrudingDivisor for lateral movement and credential gathering.
- The TwoFace webshell had a loader and payload component written in C# for ASP.NET servers, with encryption and decryption methods for interacting with the payload.
- TwoFace++ loader shell was discovered with similar functionality to TwoFace, requiring a password for decryption.
- IntrudingDivisor webshell required authentication with specific integer and MD5 hash values for issuing commands.
- The threat actor relied on the TwoFace webshell for persistent access and lateral movement within the compromised network using novel techniques and tools like Mimikatz.
- Operation time window: June 2016 to May 2017.


