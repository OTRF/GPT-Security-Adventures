
Report 1

Summary:
- Threat actor: BlueNoroff, APT 38, Stardust Chollima
- Region: Global
- Operating sector: Financial, cryptocurrency exchanges, venture capital firms, banks
- Date: May 31, 2023
- Evidence: New macOS malware variant discovered by Jamf Threat Labs attributed to BlueNoroff APT group targeting financial institutions. Malware communicates with a malicious domain swissborg[.]blog, mimicking a legitimate cryptocurrency exchange. Malware uses Objective-C to execute shell commands, evade detection, and gather macOS version information.
- Novelty: Malware uses a simple remote shell capability, different from previous RustBucket campaign, but aligns with BlueNoroff's tactics. Malware logs activities, sends POST requests to C2 server, and operates as a functional tool for attackers.
- Tools and techniques: Malware uses NSURLSession class, Objective-C NSProcessInfo functionality, and system() function for command execution.
- Conclusion: Malware named ObjCShellz is part of the RustBucket campaign, indicating a multi-stage malware delivery via social engineering. Malware is functional and aligns with BlueNoroff's previous attacks.





Report 2

Bluenoroff, APT 38, and Stardust Chollima, threat actors known for targeting financial institutions, have been linked to attacks on banks in the Philippines, Bangladesh, Vietnam, and Ecuador. The attacks involved the use of malware to cover up fraudulent transfers, with evidence of code similarities to historic attacks by Lazarus. Symantec discovered new malware tools, Backdoor.Fimlis, Backdoor.Fimlis.B, and Backdoor.Contopee, used in limited targeted attacks in South-East Asia, with connections to Trojan.Banswift. These tools were attributed to the same threat group due to distinctive code sharing. Lazarus, the threat group behind Backdoor.Contopee, has a history of aggressive attacks since 2009, including the destructive Trojan Backdoor.Destover. The ongoing danger posed by these threat actors highlights the need for continued vigilance by financial institutions. Symantec and Norton products offer protection against these threats with specific detections. The attacks demonstrate the capability and adaptability of the threat actors, posing a significant risk to the financial sector.





Report 3

Malformed report





Report 4

Bluenoroff, APT 38, and Stardust Chollima are threat actors highlighted in the APT trends report Q2 2020 by Kaspersky. The report discusses various activities observed during the quarter, including attacks on supercomputing centers in the UK and Europe, targeting academic data centers for CPU mining purposes, and malicious activity related to COVID-19 vaccine research. The threat actors mentioned demonstrate capabilities in conducting tailored hacking operations, utilizing new malware variants, and targeting specific sectors such as financial institutions, health institutions, and government entities. Novel techniques include the use of typo-squatting domains, DLL side-loading for executing implants, and multi-stage infection procedures. The report also mentions Chinese-speaking threat actors engaging in ongoing malicious activities and the exploitation of software vulnerabilities by APT actors. The threat landscape continues to be influenced by geopolitical motives, financial gain, and the exploitation of the COVID-19 pandemic as a lure for victims. The report provides insights into the evolving tactics, techniques, and procedures of APT threat actors during the specified time frame.





Report 5

Bluenoroff, APT 38, and Stardust Chollima, identified as Lazarus group, targeted Far Eastern International Bank in Taiwan in October 2017. The attackers compromised the bank's system connected to the SWIFT network, transferring funds to overseas beneficiaries. Malware samples uploaded to repositories included Lazarus group tools and a rare ransomware variant called 'Hermes'. The ransomware was used as a distraction during the heist. The attackers used sophisticated techniques like embedding files within files and creating persistence mechanisms. The malware spread across the victim's network, targeting specific anti-virus processes and copying itself to other devices. The attackers created SWIFT messages to transfer funds to Cambodia, the US, and Sri Lanka, with most of the stolen funds being recovered. The Lazarus group's evolving modus operandi includes disrupting victims with ransomware and different message formats. The attack highlights the importance of network hardening and monitoring for financial institutions. The report provides indicators of attack and a YARA rule for detection.





Report 6

Summary:
- Threat actor: Bluenoroff, APT 38, Stardust Chollima
- Date: June 13, 2018
- Region: Chile
- Operating sector: Financial institution
- Victims: Banco de Chile
- Evidence of capability: $10 million stolen from Banco de Chile through SWIFT network compromise
- Novelty of tools and techniques: Wiper malware used as distraction, "zero-day virus" identified as modified Buhtrap malware component
- Attribution uncertainty: Possible involvement of Lazarus Group (North Korea-linked) or Buhtrap (Russian-speaking group)
- Forensic analysis points to Eastern European or Asian groups
- Trend of cyber-attacks targeting payment transfer systems, with Banco de Chile being the latest victim.





Report 7

Malformed report





Report 8

BlueNoroff, a financially motivated threat actor, has introduced new methods to bypass security measures and deliver malware. The group has been active since October 2022 and has adopted new malware strains in its arsenal. BlueNoroff is known for using Word documents and shortcut files for initial intrusion, but has recently started using new methods such as ISO and VHD file formats to evade security measures. The group has also experimented with new file types like Visual Basic Script and Windows Batch files for malware delivery. BlueNoroff has created fake domains impersonating venture capital companies and banks, with a focus on Japanese financial entities. The group has been active in targeting victims in the UAE and Japan, indicating a keen interest in financial markets in these regions. The threat actor has shown capability in evading detection through Living Off the Land Binaries (LOLBins) and has used various techniques to deliver and execute payloads. The group's activities suggest a continued focus on financial entities and a willingness to adapt and innovate in their cyberattacks.





Report 9

Bluenoroff, also known as APT 38 and Stardust Chollima, is a subgroup of the Lazarus Group, operating out of North Korea since 2014. The threat actor's primary motivation is financial crime, targeting various sectors and countries globally. Bluenoroff has been involved in multiple high-profile attacks, including SWIFT attacks on banks in the Philippines, Ecuador, and India, as well as attempted heists in Mexico and Chile. The group has demonstrated advanced capabilities with the use of sophisticated malware like Duuzer backdoor Trojan and new macOS malware variants. Bluenoroff's novel techniques include spear-phishing emails with disguised Windows shortcut files and spoofing venture capital firms in Japan, Vietnam, and the US. The threat actor continues to evolve, with recent operations like the RustBucket campaign and plans for new crypto-theft attacks, prompting increased vigilance and counter operations by cybersecurity authorities.





Report 10

Summary:
Bluenoroff, a North Korea-nexus intrusion set, has been observed conducting financially-driven campaigns targeting cryptocurrency exchanges and venture capital entities in Europe, Asia, the U.S., and the UAE since 2017. In April 2023, Bluenoroff was found targeting macOS systems with the RustBucket malware, written in Rust and Objective-C, marking a shift towards cross-platform language in their malware development efforts. The malware uses a fake PDF reader to trigger malicious activity, demonstrating novel techniques to evade detection. Bluenoroff's infrastructure includes phishing emails and social network exploitation, with a focus on typosquatting legitimate financial and technology entities. The threat actor's adaptation efforts and expansion of offensive capabilities indicate a continued threat in the short to medium term. Sekoia.io analysts have provided YARA rules and technical details to aid in detection and monitoring of Bluenoroff's activities. The report was published on May 22, 2023, by Sekoia.io.





Report 11

Summary:
Bluenoroff, a splinter group of the Lazarus APT, has been targeting financial institutions, casinos, financial trade software development companies, and cryptocurrency businesses primarily in Southeast Asia and developing countries. The group is known for its involvement in the $850 million fraudulent SWIFT network transactions against the Bangladesh Central bank in February 2016. Bluenoroff has shown a unique interest in SWIFT software, developing patches to steal money without leaving traces. The group has adopted tactics like watering hole attacks and cryptocurrency mining, indicating a shift towards profit-driven motives. Evidence suggests a link between Bluenoroff, North Korea, and Lazarus, with connections to command and control servers in Europe and North Korea. The group's capabilities and novel techniques, such as using iframes for redirection and exploiting vulnerabilities, demonstrate their evolving sophistication. The report was published on April 3, 2017, by Threatpost.





Report 12

Summary: Microsoft warns of the BlueNoroff North Korean hacking group planning new crypto-theft attacks through social engineering campaigns on LinkedIn. The threat group, also known as Sapphire Sleet, targets cryptocurrency companies for theft using malware hidden in malicious documents distributed via private messages on social networks. Recently, they have created fake skills assessment portals to lure targets. Evidence shows a connection to the largest crypto hack in history and previous cyberattacks targeting banks and cryptocurrency exchanges globally. Novelty lies in the use of new websites for hosting malicious payloads and the development of ObjCShellz macOS malware for backdooring Macs. The threat actor's capability is demonstrated by their ability to evade detection and target a wide range of victims across different regions. Date: November 10, 2023.





Report 13

Summary:
- Threat actor: Bluenoroff, APT 38, Stardust Chollima
- Region: Global
- Operating sector: Financial organizations, particularly cryptocurrency-related companies and individuals
- Date: December 5, 2023
- Evidence of capability: New variety of malicious loader targeting macOS, linked to BlueNoroff APT gang
- Novel tools and techniques: Loader found inside a ZIP archive disguised as a PDF file, with a valid signature that was later revoked
- Execution process: Decrypts payload using XOR encryption, runs AppleScript code, assembles and executes shell command
- C&C server: Hosted at hxxp://on-global[.]xyz, domain registered on October 20, 2023
- Indicators of compromise: Files include EdoneViewer, .pw file, and ZIP archive with PDF decoy
- Detection: Trojan can be detected by most anti-malware solutions.





Report 14

Summary:
- Threat actor: Lazarus Group, also known as Bluenoroff, APT 38, Stardust Chollima
- Region: India
- Operating sector: Banking
- Date: August 10-13, 2018
- Victims: Cosmos Co-operative Bank in India
- Evidence of capability: Stole $13.5 million through sophisticated ATM and SWIFT network attacks
- Novelty of tools and techniques: Used targeted malware exploits to set up a malicious ATM/POS proxy switch, bypassing traditional security measures
- Attack involved increasing withdrawal limits on targeted accounts, making international ATM withdrawals and unauthorized money transfers
- Attackers gained access to SWIFT environment to transfer $2 million to a Hong Kong account
- Attack bypassed Interpol-recommended measures for protecting ATM infrastructure

Overall, the Lazarus Group demonstrated advanced capabilities in executing a complex financial cyber attack, highlighting the need for enhanced security measures in the banking sector.





Report 15

Summary:
In a recent incident, North Korean threat actors, believed to be associated with the Lazarus Group, targeted the Chilean ATM network through a sophisticated cyber-attack. The attack was initiated through a job interview conducted via Skype, where the victim was tricked into downloading and running a malicious file named ApplicationPDF.exe. The malware, identified as PowerRatankba, collected sensitive information from the victim's work PC and sent it to a remote server. This incident highlights the capability of the threat actor to use novel techniques to infiltrate high-profile networks. The victim, Redbanc, a financial firm with connections to all Chilean banks, fell victim to this attack, showcasing the potential impact of a single compromised device on an entire network. The incident serves as a reminder of the ongoing threat posed by sophisticated threat actors in the cyber landscape. (Date: Not specified)





Report 16

Summary:
Between September 2022 and March 2023, North Korean hackers associated with APT38 targeted financial institutions and venture capital firms in the U.S., Vietnam, and Japan by spoofing domains. The group used 74 domains and 6 malicious files in their campaign. This activity is linked to previous attacks by APT38 on cryptocurrency firms. The novelty of this campaign lies in the targeting of venture capital firms, a departure from previous targets like SWIFT and cryptocurrency exchanges. The hackers aimed to steal money and sensitive information from investment banking and venture capital firms. The campaign continued from January to March 2023, with additional IP addresses and domains being used. The North Korean hackers are likely to continue launching financially-motivated attacks due to international sanctions.





Report 17

Summary:
The threat actor TA444, also known as APT38, Bluenoroff, Stardust Chollima, is a North Korea state-sponsored group primarily focused on financially motivated operations, targeting banks and more recently, cryptocurrencies. They have shown an upstart mentality in their operations, testing various infection methods with a focus on cryptocurrency theft. TA444 has used a variety of file types for initial access, including MSI Installer files, Virtual Hard Drives, and Compiled HTML. They have also employed email marketing tools like SendInBlue and SendGrid to engage with victims. In December 2022, TA444 deviated from their usual operations with a credential harvesting campaign targeting various sectors in the US and Canada. The group has a strong social media presence, particularly on LinkedIn, and has demonstrated proficiency in multiple languages. TA444 has a history of deploying post-exploitation backdoors and has been linked to significant cryptocurrency thefts, surpassing $1 billion in 2022. Their operations are attributed based on malware lineage, infrastructure usage, and targeting of financial entities. TA444 remains an astute and capable adversary, adapting their methods to continue profiting from cyber intrusions. The group's activities are closely monitored by security researchers for potential future developments.





Report 18

BlueNoroff, a threat actor group, has been actively targeting cryptocurrency businesses since 2016, shifting focus from traditional banking attacks. They have been using sophisticated social engineering tactics to compromise companies, including creating fake cryptocurrency software development companies to trick victims. The group has been observed using novel infection vectors, such as zipped Windows shortcut files and weaponized Word documents, to deliver malware implants. BlueNoroff has been collecting credentials, monitoring cryptocurrency transactions, and even tampering with browser extensions to steal funds. The group has targeted victims globally, with a recent campaign observed in November 2021. BlueNoroff's tools and techniques show overlaps with their previous activities, indicating a high level of sophistication and capability. The threat actor group is known for its financial motivation and advanced malware capabilities, making them a significant threat in the cybersecurity landscape.





Report 19

Summary:
The report from Elastic Security Labs on the threat actor "Bluenoroff, APT 38, Stardust Chollima" reveals a new variant of the RUSTBUCKET malware being used by the Democratic People’s Republic of North Korea (DPRK) for financially motivated attacks against cryptocurrency service providers. The malware exhibits advanced capabilities such as built-in persistence and reduced signature detection, with the latest variant remaining undetected by VirusTotal. The threat actor employs dynamic network infrastructure for command and control, utilizing specific macOS APIs and unique identifiers for system information gathering and execution. The campaign targets a venture-backed cryptocurrency company in the United States, showcasing sophisticated defense evasion techniques to hinder analysis and detection efforts. The report provides detailed insights into the malware's code analysis, persistence mechanisms, networking infrastructure, defense evasion tactics, and victimology, highlighting the novel tools and techniques used by the threat actor. The operation time window is not specified in the report.





Report 20

Summary:
Bluenoroff, APT 38, and Stardust Chollima, threat actors, attempted a $1.36 million SWIFT heist targeting a Vietnamese bank in the fourth quarter of 2015. The attack involved suspected malware and a Trojanized PDF reader. The attack was detected by Tien Phong Commercial Joint Stock Bank in Hanoi, which quickly stopped the transfer requests. The State Bank of Vietnam is investigating the incident. SWIFT issued a security alert warning of similar attacks targeting banks' payment endpoints. The attack was attributed to the Lazarus Group, known for previous cyberattacks. The threat actor used novel techniques, including malware to infect a PDF reader and alter SWIFT transactions. The attack did not result in any financial losses. The bank has since enhanced its security measures and terminated its contract with the third-party vendor responsible for interfacing with the SWIFT network. The incident highlights the importance of robust security measures for financial institutions interfacing with the SWIFT network.


