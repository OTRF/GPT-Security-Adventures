
Report 1

Summary:
The APT trends report for Q2 2020 by Kaspersky highlights significant findings in the activities of threat actors. The report covers various regions, including Russian-speaking, Chinese-speaking, Middle East, Southеast Asia, and Korean Peninsula. Notable findings include the targeting of supercomputing centers in the UK and Europe, attributed to COVID-19 research, and malicious activity targeting COVID-19 vaccine research institutions by the APT-29 threat actor. Novel tools and techniques were observed, such as the Penquin_x64 backdoor variant, typo-squatting domains for spear-phishing campaigns, and the use of the Exim vulnerability by the Hades threat actor. Additionally, Chinese-speaking threat actors like CactusPete and HoneyMyte were active, along with Lazarus targeting financial institutions and academic sectors. The report also mentions the discovery of new malware frameworks like Deceptikons and MagicScroll. Overall, the report emphasizes the ongoing exploitation of the COVID-19 pandemic theme by threat actors and the evolving tactics used by APT groups.





Report 2

DeathStalker, a threat actor group, has been targeting legal entities in the Middle East with a new Janicab variant since 2020, possibly active in 2021. The threat actor has been traced back to early 2015 and targets legal, financial, and travel agencies in the Middle East and Europe. Janicab is a malware family that runs on macOS and Windows operating systems, with the Windows version having a VBscript-based implant. The threat actor continues to use YouTube, Google+, and WordPress web services as dead-drop resolvers. The threat actor has been observed targeting law firms, financial institutions, and travel agencies, with a focus on the Middle East and Europe. The threat actor group has been associated with DeathStalker based on unique TTPs, victimology, and infrastructure used. The threat actor group uses interpreted-language malware such as Python, VBE, and VBS, making application whitelisting and OS hardening effective techniques to block intrusion attempts. The threat actor's intent may involve legal disputes, financial assets, blackmailing VIPs, or competitive/business intelligence. Defenders should look for Internet Explorer processes running without GUI and frequent visits to DDRs followed by HTTP sessions pointing to IP addresses instead of domain names.





Report 3

The threat actor known as DeathStalker, also operating under the alias Deceptikons, has been targeting law firms and companies in the financial sector since at least 2012. They are believed to be mercenaries offering hacking-for-hire services or acting as information brokers in financial circles, with a focus on information theft and espionage. The group has been observed using novel tools such as Powersing, Evilnum, Janicab, PowerPepper, and VileRAT. Victims have been targeted in countries including Argentina, China, Cyprus, India, Israel, Jordan, Lebanon, Russia, Switzerland, Taiwan, Turkey, UAE, and the UK. The threat actor's activities have been linked to other groups, such as Evilnum. The latest reported hacking operations by DeathStalker include targeting legal entities with a new Janicab variant in 2020, deploying the PowerPepper implant, and continuous strikes at foreign and cryptocurrency exchanges using VileRAT.





Report 4

Summary:
The threat actor known as DeathStalker, a mercenary group, has been targeting law firms and companies in the financial sector since at least 2018. They use a PowerShell-based implant called Powersing distributed through spear-phishing emails with malicious LNK files. The group is not motivated by financial gain but rather by gathering sensitive business information. They have been linked to other malware families like Janicab and Evilnum, showing similarities in their techniques and capabilities. DeathStalker's victimology includes private entities in the financial sector, with activities observed in various countries. The group continues to develop its toolset and has been active since 2018, leveraging events like COVID-19 for implant deployment. Defenders are advised to monitor process creation related to scripting languages and be aware of infection chains based on LNK files. The group's activities serve as a baseline for defending against cyber threats in the private sector.





Report 5

DeathStalker is a threat actor identified as a cyber-mercenary organization targeting various entities globally, including law and consultancy offices, as well as FINTECH companies. Operating since at least 2012, DeathStalker has utilized malware strains like Janicab, Powersing, and Evilnum, along with intricate delivery chains involving dead-drop resolvers and anti-detection techniques. In May 2020, a new implant named PowerPepper was discovered, leveraging DNS over HTTPS for command and control communication. PowerPepper's delivery chains include obfuscation techniques like hiding malicious scripts in Word embedded shape properties and using Windows Compiled HTML Help files as archives. The implant's persistence is ensured through a Visual Basic Script loader and steganography techniques, with a signed binary proxy execution to initiate PowerPepper. The PowerPepper implant and associated delivery chains have been continuously evolving since mid-July 2020.


