
Report 1

Summary:
The threat actor FIN7, known for its cybercrime activities, has continued its operations despite arrests in 2018. The threat actor targets companies to steal financial assets and data, using sophisticated spear phishing campaigns with social engineering tactics. They have developed novel tools and techniques, such as a homemade builder for malicious Office documents and the GRIFFON implant, a lightweight JScript validator-style malware. The threat actor has also been linked to other groups like CobaltGoblin/EmpireMonkey and AveMaria, showing interconnected activities. The FIN7 threat actor has extended its operations to target banks in Europe and Central America, stealing millions of euros. The threat actor's infrastructure mistakes have allowed researchers to track their activities. The report also mentions a new group called CopyPaste targeting financial entities in an African country. Despite arrests and disruptions, the threat actor continues to operate effectively, benefiting from unpatched systems and effective spear phishing campaigns.





Report 2

FIN7 is a financially-motivated threat group that has primarily targeted the U.S. retail, restaurant, and hospitality sectors since mid-2015, using point-of-sale malware. They have been observed attacking sectors such as Casinos and Gambling, Construction, Education, Energy, Financial, Government, High-Tech, Hospitality, Retail, Technology, Telecommunications, and Transportation in countries like Australia, France, Malta, UK, and USA. The threat actor has been linked to high-profile breaches in companies like Red Robin, Chili’s, Arby’s, Burgerville, Omni Hotels, Saks Fifth Avenue, and more. FIN7 has been known to use a variety of tools such as Carbanak, Cobalt Strike, Mimikatz, and more, with novel techniques like leveraging Shim Databases for persistence and fileless attacks targeting restaurants. The group has been active since 2013, with reported operations up to 2023, and has faced counter operations resulting in arrests of key members. The threat actor has shown innovation in their attacks, with new tools like BOOSTWRITE and RDFSNIFFER being identified in 2019 and 2021.





Report 3

Summary:
The threat actor FIN7, also known as Carbanak, has been identified by Proofpoint researchers to have unleashed a new JScript backdoor named Bateleur. The threat actor has targeted U.S.-based chain restaurants, among other sectors like hospitality organizations, retailers, and suppliers. The Bateleur backdoor employs sophisticated anti-analysis and sandbox evasion techniques to expand its victim pool. The backdoor has capabilities such as retrieving system information, executing custom commands and PowerShell scripts, taking screenshots, and exfiltrating passwords. The threat actor has shown the ability to update the backdoor rapidly, with Bateleur evolving from version 1.0 to 1.0.4.1 in less than a month. The backdoor is attributed to FIN7 based on similarities in email campaigns, the use of Tinymet Meterpreter downloader, and shared components like a password stealer module. The threat actor continues to adapt its tactics and tools to avoid detection and target new victims. The operation time window for this activity was observed starting in early June 2017.





Report 4

Summary:
The threat actor FIN7, known for targeting US businesses to steal payment card data, demonstrated high-paced innovation in an attack between October 8 to 10, 2017. FIN7 is sophisticated and organized, using customized spear-phishing lures with malicious attachments to move laterally across networks. Evidence suggests a connection to the Carbanak Gang. Recent attacks by FIN7 have shown rapid dynamic changes, including a new attack in October 2017 documented by Icebrg. The group employs anti-forensic techniques to evade detection. Morphisec has closely monitored FIN7, highlighting their use of fileless attacks and DLL variants injected into malicious documents. The group's ability to bypass security solutions showcases their capability and the novelty of their techniques.





Report 5

Summary:
- Threat actor: FIN7
- Region: United States
- Operating sector: Large restaurant chains, hospitality, financial service organizations
- Date: April 2017
- FIN7 evolved phishing techniques by using hidden shortcut files (LNK) and VBScript functionality launched by mshta.exe to infect victims.
- Targeted organizations received spear phishing emails with malicious DOCX or RTF files containing the LNK file and VBScript technique.
- FIN7 ensured delivery of emails by calling targeted stores and walking them through the infection process.
- Persistence mechanisms included scheduled tasks, auto-start registry entries, and creation of named schedule tasks.
- Novelty: FIN7 used unique infection and persistence mechanisms, moving away from weaponized Microsoft Office macros.
- Tools and techniques: FIN7 utilized VBScript, PowerShell scripts, Cobalt Strike stager, and HALFBAKED backdoor variant.
- Evidence of capability: FIN7 demonstrated advanced phishing tactics and evasion techniques to target financial information.





Report 6

Summary:
The threat actor FIN7, also known as Carbanak, has been identified in a new campaign targeting the restaurant industry by Morphisec in November 2018. FIN7 is a sophisticated threat group known for evading security systems and targeting specific industries like hospitality. The group has been linked to high-profile breaches in various companies. The campaign involved social engineering techniques to deliver a backdoor component through obfuscated JavaScript. The threat actor used a password-protected document with a legitimate VPN tool's branding to trick victims into enabling macros. The document was created in February 2018 and submitted from Latvia. The backdoor component communicated with a C2 server and collected information like MAC address and computer domain. The threat actor's capability to continuously evolve their techniques and tools, as well as their persistence in targeting specific industries, demonstrates their advanced capabilities and ongoing threat to organizations.





Report 7

FIN7, a threat actor operating in the financial sector, has evolved its tactics and techniques over time, with evidence suggesting a shift towards targeted ransomware operations involving various ransomware strains. The threat actor has been associated with ransomware operations such as REVIL, DARKSIDE, BLACKMATTER, and ALPHV. FIN7 has demonstrated the capability to merge multiple UNC groups into its core cluster, with notable shifts in activity including the use of novel malware like POWERPLANT and BIRDWATCH variants. The threat actor has diversified its initial access techniques to include software supply chain compromise and stolen credentials, in addition to traditional phishing methods. FIN7's preference for PowerShell-based loaders and unique PowerShell commands has been a consistent pattern in their operations. The threat actor has also been observed leveraging new versions of the BIRDWATCH downloader, such as CROWVIEW and FOWLGAZE. FIN7 has targeted organizations across various sectors, including finance, manufacturing, and government, with evidence of data theft extortion and ransomware deployment. The threat actor's capability to develop and deploy advanced malware like POWERPLANT, along with the novelty of their techniques, indicates a high level of sophistication. The report covers FIN7's activities from 2020 to 2021, highlighting their use of obfuscation techniques, supply chain compromise, and reconnaissance utilities like EASYLOOK and BOATLAUNCH. Additionally, the threat actor has been associated with phishing campaigns distributing BIRDWATCH and other malware families like WINGNIGHT and FLYHIGH. Despite indictments and sentencing of some members in the past, FIN7 remains active and continues to evolve its criminal operations, with potential links to ransomware operations like MAZE, RYUK, and ALPHV. The report provides detailed insights into FIN7's attribution methodology, infrastructure analysis, and the evolution of their malware capabilities.





Report 8

Summary:
- Threat actor: FIN7
- Region: Global
- Operating sector: Cybercrime
- Victims: Companies targeted for ransomware attacks
- Date: October 21, 2021
- Evidence: FIN7 recruits talent through fake company "Bastion Secure" for ransomware operations, using tools Carbanak and Lizar/Tirion previously attributed to FIN7.
- Novelty: FIN7 expands into ransomware, recruits IT specialists through fake company, uses disinformation tactics, and offers low salaries to retain profits.
- Conclusion: FIN7's use of fake companies to recruit unwitting accomplices for criminal activities showcases their greed and sophistication in cybercrime operations.





Report 9

Summary:
On June 7, 2017, Morphisec Lab identified a new fileless attack by the threat actor FIN7 targeting restaurants in the US. The attack allows hackers to seize system control and steal financial information using evasive techniques to bypass security solutions. FIN7, associated with the Carbanak gang, has a history of successful attacks on banks, SEC personnel, and large restaurant chains. The attack involves a malicious Word document in phishing emails, executing fileless attacks using DNS queries to deliver shellcode. The attack's shellcode technique is novel, using DNS messaging directly from memory to evade detection. The attack demonstrates FIN7's constant upgrades in evasion techniques, posing a severe risk to enterprises. Enterprises need new defenses resilient to fileless attacks like Morphisec's Endpoint Threat Prevention. The attack artifacts include document hashes and attacker email accounts. The attack highlights the rise of fileless attacks and the need for advanced defenses in the evolving threat landscape.





Report 10

Summary:
- Threat actor: FIN7
- Region: Eastern Europe
- Operating sector: Primarily targets US-based companies across various industries, with a focus on hospitality and retail sectors
- Type of company of victims: POS service provider
- Evidence of capability: Used malicious Windows 11 Alpha-themed Word documents with Visual Basic macros to drop JavaScript backdoor, targeting a POS provider aligns with previous FIN7 activity, use of JavaScript backdoors historically associated with FIN7
- Novelty of tools and techniques: Used decoy Word documents with VBA macros, JavaScript backdoor with obfuscated strings and XOR cipher, language checks to terminate infection if Eastern European languages detected
- Operation time window: Late-June to late-July 2021
- Source: Anomali Threat Research report dated September 2, 2021

Malformed report.





Report 11

Summary:
- Threat actor: FIN7 or a threat actor utilizing FIN7 tradecraft
- Region: Global
- Operating sector: Veeam Backup & Replication software
- Type of company: Not specified
- Date: Attacks occurred in late March 2023
- Evidence of capability: Utilized recently patched Veeam Backup & Replication vulnerability, CVE-2023-27532, to gain initial access. Used POWERTRASH, DICELOADER, and new tools like POWERHOLD and DUBLOADER for persistence and lateral movement. Conducted reconnaissance, discovery, credential theft, and lateral movement using custom scripts and PowerShell commands.
- Novelty of tools and techniques: Developed new tools like POWERHOLD and DUBLOADER, mimicked legitimate files like libcurl.dll, and used unique PowerShell scripts for persistence and lateral movement.
- Recommendations: Affected companies advised to patch and configure backup servers appropriately. WithSecure™ Elements Endpoint Detection and Response and WithSecure™ Countercept Detection and Response can help detect and respond to such attacks.





Report 12

Summary:
- Threat actor identified as FIN7 conducted two recent fileless malware campaigns targeting financial institutions, government agencies, and enterprises.
- The campaigns utilized fileless malware and known penetration testing tools to spy on organizations and move data and money off networks.
- The attacks involved phishing emails with protected Word documents containing macros that executed PowerShell commands.
- The attacker used a framework to deliver attacks that left no artifacts on compromised machines.
- The framework included scripts for Mimikatz, LaZagne, and DNS Messenger to extract passwords and hashes.
- Morphisec researchers interacted with the attacker, leading to the takedown of the command and control infrastructure.
- The attacker's capability to disrupt ongoing attacks and rebuild the platform was demonstrated.
- The attacks were linked to the GCMAN and Carbanak groups responsible for significant thefts from financial institutions.
- The threat actor targeted individuals involved in SEC filings, with evidence suggesting a global attribution to one actor and platform.
- The novel use of fileless malware and known utilities in the attacks showcases the evolving tactics of the FIN7 threat actor.





Report 13

Malformed report.





Report 14

Summary:
- Threat actor: FIN7
- Region: Not specified
- Operating sector: Not specified
- Type of company of victims: Not specified
- Date: December 26, 2019
- Evidence of capability: FIN7 developed a new loader called BIOLOAD, leveraging DLL search order hijacking to load a malicious DLL into a legitimate Windows process.
- Novelty of tools and techniques: BIOLOAD shares a common codebase with BOOSTWRITE, carrying the Carbanak backdoor. It is tailored for each infected machine, uses XOR decryption, and hinders analysis by using machine-specific keys.
- Conclusion: BIOLOAD is attributed to FIN7, preceding BOOSTWRITE, and suggests the group gathers information about targets' networks. Countermeasures are recommended to detect and block such behavior.





Report 15

Summary:
The threat actor FIN7 has been observed using new tools and techniques in recent incident response engagements, including the development of two new tools called BOOSTWRITE and RDFSNIFFER. BOOSTWRITE is an in-memory-only dropper that decrypts embedded payloads using an encryption key retrieved from a remote server at runtime. RDFSNIFFER, a payload of BOOSTWRITE, is designed to tamper with NCR Corporation's “Aloha Command Center” client in the payment card processing sector. Notably, a signed BOOSTWRITE sample was identified, indicating the group's use of code signing certificates to evade detection. These new tools demonstrate FIN7's evolving capabilities and adaptation to security enhancements. The use of code signing highlights the group's resourceful tactics to bypass security controls. FireEye provides detection capabilities for these tools and highlights MITRE ATT&CK mappings for the techniques used by FIN7. Organizations are advised to remain vigilant as FIN7 continues to evolve its tactics. The report was last updated on March 30, 2022.





Report 16

Malformed report





Report 17

Summary: FIN7, a threat actor, was detected carrying out a rare BadUSB attack against a US hospitality provider. The attack was reported in 2024 by ZDNET. This incident showcases the capability of FIN7 to use novel techniques to target victims in the hospitality sector in the United States. The use of BadUSB, a type of attack that involves manipulating USB devices to compromise systems, demonstrates the advanced tactics employed by FIN7. The attack highlights the ongoing threat posed by this threat actor to organizations in the hospitality industry.





Report 18

Summary:
The report discusses the evolution of the FIN7 JSSLoader, a RAT used by the financially motivated cybercrime group FIN7 (Carbanak Group). The report provides a technical analysis of a recent attack intercepted in December 2020, focusing on the JSSLoader component. The attack chain involves phishing campaigns leading to the deployment of JSSLoader, which has capabilities such as exfiltration, persistence, auto-update, and malware downloading. The report highlights the use of a new VBScript in the attack chain and the reflective loading and execution of a Carbanak by the RAT. The C2 hosting provider used by FIN7 is identified as FranTech Solutions. The report emphasizes the advanced techniques and tactics employed by FIN7, showcasing the group's capability to adapt and evolve their tools. The analysis provides unique insights into the JSSLoader and the complete attack chain, shedding light on the group's operations. The report was updated on January 4, 2021, with contributions from Morphisec CTO Michael Gorelik. The victims targeted by FIN7 are not explicitly mentioned in the report.





Report 19

Summary:
- Threat actor: FIN7
- Region: Global
- Operating sector: Private Industry (Finance, Manufacturing)
- Type of company targeted: Financial institutions
- Date: 2017
- Evidence of capability: FIN7 leveraged the CARBANAK backdoor for persistent access, used application shim databases for persistence, injected malicious in-memory patches into the Services Control Manager process, and installed a payment card harvesting utility.
- Novelty of tools and techniques: FIN7 used a custom Base64 encoded PowerShell script to install a malicious shim database, registered the shim database using the "sdbinst.exe" utility, and patched both 32-bit and 64-bit versions of "services.exe" with their CARBANAK payload.
- Techniques used: Shellcode injection, registry key manipulation, process spawning, and DLL injection.
- Detection recommendations: Monitor for new shim database files, registry key creation/modification events, and process execution events related to the "sdbinst.exe" utility.


