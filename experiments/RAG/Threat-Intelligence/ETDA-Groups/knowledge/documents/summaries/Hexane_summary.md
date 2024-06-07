
Report 1

Malformed report





Report 2

Summary:
- Threat actor known as LYCEUM targeted critical infrastructure organizations in the Middle East, including oil and gas and telecommunications sectors.
- LYCEUM's activity involved obtaining and expanding access within targeted networks using tools like DanBot, DanDrop, kl.ps1, Decrypt-RDCMan.ps1, and Get-LAPSP.ps1.
- The threat actor's tradecraft resembled other known groups but lacked direct links to them.
- LYCEUM's toolkit included a remote access trojan, keylogger, and PowerShell scripts for reconnaissance and data gathering.
- The threat actor used spearphishing emails with malicious Excel attachments to deliver malware.
- LYCEUM's command and control infrastructure was registered using various registrars, with domains created for individual campaigns.
- No evidence of ICS targeting was found, but the threat actor demonstrated capabilities common in the Middle East.
- Recommendations for organizations included implementing multi-factor authentication, increasing visibility through endpoint monitoring, conducting preparedness exercises, and enhancing phishing awareness.
- Threat indicators were provided to help organizations mitigate exposure to LYCEUM's malware.
- The report was published on August 27, 2019, by Secureworks.





Report 3

Summary:

The HEXANE threat group, identified by Dragos since 2018, targets industrial control systems (ICS) related entities, primarily oil and gas companies in the Middle East, including Kuwait. They have also targeted telecommunication providers in the greater Middle East, Central Asia, and Africa. Their intrusion activities involve the use of malicious documents to drop malware and establish footholds for follow-on attacks. HEXANE's targeting of telecommunications providers follows a trend of ICS adversaries targeting third-party organizations along the supply chain. While sharing similarities with other activity groups like MAGNALLIUM and CHRYSENE, HEXANE's victimology, infrastructure, and capabilities make it a unique entity. Dragos assesses with moderate confidence that HEXANE does not currently possess the capability to disrupt ICS networks. The threat group's use of novel tools and techniques, such as newly identified detection evasion schemes, sets them apart from other observed activity groups. The full threat intelligence reports on HEXANE and other activity groups are available to WorldView Threat Intelligence subscribers.





Report 4

Summary:
The threat actor Hexane, also known as Lyceum, Cobalt Lyceum, and Siamesekitten, has been targeting industrial control systems (ICS) related entities, specifically oil and gas companies in the Middle East, including Kuwait, and telecommunication providers in the greater Middle East, Central Asia, and Africa. The group has been active since at least 2017 and has its own arsenal of tools and techniques, showing similarities with other known groups but with differing tactics, techniques, and procedures (TTPs). The threat actor's motivation is information theft and espionage, with reported hacking operations dating back to 2021, including campaigns like "Out to Sea" by OilRig. The group has been observed using tools such as DanBot, DanDrop, Decrypt-RDCMan.ps1, and others. The threat actor is believed to originate from Iran and has targeted victims in sectors such as energy, oil and gas, and telecommunications in countries like Israel, Kuwait, Morocco, Saudi Arabia, Tunisia, UAE, as well as regions in the Middle East, Central Asia, and Africa. The group's activities have been reported by various cybersecurity firms and researchers, with counter operations ongoing to mitigate the threat posed by Hexane.





Report 5

Summary:
- Threat actor: Lyceum Group, a state-sponsored Iranian APT group.
- Operating region: Middle East, targeting organizations in the energy and telecommunication sectors.
- Novelty of tools: Utilizing a newly developed .NET based DNS Backdoor, customized from an open source tool.
- Techniques used: DNS Hijacking for command and control communication, uploading/downloading files, executing system commands.
- Delivery mechanism: Macro-enabled Word document downloaded from a domain disguising as a news report.
- Operation time window: Active since 2017, recent campaign observed by Zscaler ThreatLabz.
- Evidence of capability: Customized malware for stealth communication, persistence via Startup folder, and data exfiltration.
- IOC: Docm Hash - 13814a190f61b36aff24d6aa1de56fe2, Exe Hash - 8199f14502e80581000bd5b3bda250ee.
- MITRE ATT&CK mapping: T1059, T1055, T1562, T1010, T1018, T1057, T1518, T1071.
- Conclusion: APT threat actors evolving tactics, Zscaler ThreatLabz monitoring to protect customers.





Report 6

Summary:
The threat actor known as Hexane, also referred to as the Lyceum group, has been active since 2019 and was recently identified targeting entities in Tunisia. Initially focused on the energy and telecommunications sectors in the Middle East, the threat actor used PowerShell scripts and a .NET-based remote administration tool named "DanBot". More recently, the group has evolved its arsenal to include new malware variants written in C++, named "James" and "Kevin". These variants support custom C&C protocols over DNS or HTTP. Additionally, the threat actor used a variant without network communication capabilities, possibly for proxying traffic between internal network clusters. The group's modus operandi includes stealing user credentials using PowerShell scripts and custom keyloggers. Similarities were observed between Hexane and the DNSpionage group, indicating a possible connection to the OilRig cluster of activity. The threat actor's tactics, techniques, and procedures have evolved over time, showcasing their capability to adapt and innovate. The report was published on October 18, 2021, and provides detailed insights into the threat actor's activities and tools.


