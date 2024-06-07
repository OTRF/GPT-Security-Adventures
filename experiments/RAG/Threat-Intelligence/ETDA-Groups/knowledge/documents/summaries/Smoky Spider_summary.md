
Report 1

Summary:
The threat actor "Smoky Spider" is associated with the Smoke Malware Loader, a modular malware loader with various features such as progressive download, geo-targeting, and password stealing capabilities from popular applications and browsers. The Smoke Malware Loader also includes modules for SOCKS-connection and turning infected hosts into stepping stones for cybercriminal activities. The pricing for the loader and its modules ranges from 10 to 250 WMZ. The threat actor targets SMBs, managed service providers, and individuals, with a focus on stealing sensitive information and compromising online activities. The novelty of the tools and techniques used by the threat actor lies in the modular nature of the loader and the extensive list of applications and browsers from which passwords can be stolen. The report was published on February 3, 2012, by Webroot Blog.





Report 2

Summary:
- Threat actor "Smoky Spider" targeted victims in Japan in the operating sector of cybercrime.
- The threat actor used a fake tsunami warning email to distribute the Smoke Loader malware, a commodity malware used since 2011.
- Smoke Loader is a modular loader capable of installing various payloads, including backdoors, ransomware, cryptominers, and banking Trojans.
- The threat actor registered a fake Japanese government agency domain to distribute the malware.
- Smoke Loader employs advanced techniques such as code obfuscation, subroutines decryption, and PROPagate trick for injection.
- The threat actor also used another commodity malware, AzoRult, in the same campaign to steal credentials and cryptocurrencies.
- The attacker registered multiple domains, including thunderbolt-price[.]com, for distributing malware.
- Palo Alto Networks customers are protected from this threat through various security measures.
- IoCs include samples of Smoke Loader, AzoRult, and Marcher, as well as infrastructure URLs.
- The threat actor also supports .bit Top Level Domains for resolving domains.
- The report was published on December 19, 2018, by Unit 42 of Palo Alto Networks.





Report 3

Malformed report





Report 4

Summary:
The threat actor "Smoky Spider" has been identified as the Retefe banking Trojan, which has recently resurfaced with a new campaign using Smoke Loader as an intermediate loader. The malware has been targeting German and Swiss users, employing new techniques such as using Object Linking and Embedding (OLE) packages to deliver Smoke Loader. Evidence suggests that the threat actor has incorporated changes like abusing shareware applications and moving away from Tor to stunnel for stealthier operations. The Retefe banking Trojan has a history of using fake certificates and leveraging exploits like EternalBlue. Security professionals are advised to use ahead-of-threat detection and inspect macro code in Microsoft Office documents to defend against banking Trojans. The report was published on May 7, 2019, by David Bisson on Security Intelligence. The victims targeted by this threat actor are primarily in the banking and finance sector in Germany and Switzerland.





Report 5

Summary:
The threat actor "Smoky Spider" is associated with the botnet software Smoke Loader, which has been active since 2011 and has over 1,500 active samples in the last six months. The threat actor utilizes a sophisticated admin panel that includes modules for information stealing, DDoS attacks, keylogging, and more. The admin panel also supports user-defined programs, making it highly flexible and customizable. The threat actor has been observed using special modified samples to evade detection and hide the command and control (C2) infrastructure. These modified samples have unique characteristics, such as storing C2 information in plaintext and bypassing verification mechanisms. The threat actor sells Smoke Loader for around $850 in the black market and offers customized systems for each buyer. The threat actor's capability includes using multiple C2 URLs and employing advanced patch codes to modify the software. The threat actor's tools and techniques demonstrate a high level of sophistication and adaptability. The report provides detailed insights into the operation and capabilities of the threat actor "Smoky Spider" in the cyber landscape.





Report 6

Summary:
The threat actor "Smoky Spider" has been identified as the creator of Smoke Loader, a downloader malware that has been active since 2011. The malware is used to download other malicious software and employs various deceptive techniques for self-protection. Smoke Loader injects itself into explorer.exe, deletes the original executable, and establishes connections from within the explorer process. It also installs updated versions of itself from a C&C server, making detection more difficult. The malware downloads additional modules, known as "plugins," and communicates with its C&C servers, partially encrypting traffic. Smoke Loader uses advanced obfuscation techniques and self-modifying code to evade detection. The threat actor has been observed targeting victims in various sectors, with evidence of novel tools and techniques used to maintain persistence and evade detection. The report was published on August 5, 2016, by Malwarebytes Labs.





Report 7

Summary:
The threat actor "Smoky Spider" is associated with the Smoke Loader botnet, which has been active on the black market since 2011. The botnet has over 1,500 active samples detected in the past six months, with a customizable copy available for $850. The malware downloader offers support for various plugins and functions, such as FORM GRAB, BOT LIST, and KEYLOGGER, to infiltrate targeted devices. Smoke Loader was among the top 10 malware threats detected by Check Point in December 2018, indicating a shift in typical malware attack profiles. The threat actor has shown innovation by using "PROPagate" injection techniques and delivering crypto-mining malware, browser plugins, and keyloggers. Special Smoke Loader samples have been identified, suggesting adaptability and longevity of the threat. Organizations are advised to use detection tools to combat Smoke Loader campaigns and follow integrated intelligence frameworks to stay ahead of evolving threats. Smoke Loader's elusive nature makes it challenging to detect and combat effectively. 

Date: February 26, 2019

Region: Global

Operating Sector: Various industries targeted, including banking & finance, energy & utility, government, and healthcare

Type of Company: Various industries targeted, including banking & finance, energy & utility, government, and healthcare





Report 8

Smoky Spider, also known as CrowdStrike, is a threat actor first seen in 2011. The malware downloader Smoke Loader, associated with Smoky Spider, offers support for multiple plugins and functions to help attackers infiltrate targeted devices. Smoke Loader has been observed distributing various malware such as DoppelPaymer, TinyLoader, DanaBot, BokBot, Zeus Panda, and TrickBot. The threat actor's motivation is financial gain, and their operations have been observed worldwide. Smoke Loader has been involved in various hacking operations since 2015, with improvements and new techniques being developed over time. The threat actor has been targeted by counter operations, such as behavior monitoring combined with machine learning to disrupt their activities.





Report 9

The report discusses the threat actor "Smoky Spider" targeting victims with the Smoke Loader malware, which was first identified in 2011 and recently updated with new process injection methods in 2017. The malware was modified in March 2018 to bypass Microsoft's countermeasures, indicating ongoing investment by the threat actors. The Smoke Loader attack involves a document with malicious macros that lead to the download and execution of the Trickbot banking Trojan. The malware uses PowerShell instructions to drop Smoke Loader on the target system, which then downloads Trickbot. Both Smoke Loader and Trickbot share identical file structures due to the same encryption method. Trickbot attempts to establish communication with multiple command-and-control servers and exfiltrate sensitive data. Smoke Loader is a well-established, highly configurable malware actively updated by threat groups to evade protective measures. The report provides indicators of compromise (IOCs) for Smoke Loader and Trickbot. The operation time window is not specified in the report.





Report 10

Summary:
The threat actor known as "Smoky Spider" utilizes the Smoke Loader malware, also known as Dofoil, which is a modular bot designed to drop various malware families. Despite its age, Smoke Loader continues to be used in RigEK and MalSpam campaigns. The malware exhibits capabilities such as unpacking itself and interacting with C2 servers. Smoke Loader employs obfuscation techniques, encryption methods, and assembly tricks to evade detection and analysis. The threat actor targets Russian-language speakers and employs custom imports and encryption for C2 URLs and command packets. The malware communicates with C2 servers, downloads plugins, and executes tasks based on received instructions. The CERT Polska team analyzed a sample of Smoke Loader, providing insights into its functionality and behavior. The report offers detailed technical information on the malware's operation and tactics.


