
Report 1

Andromeda Spider, also known as Gamaru and Wauchos, is a threat actor that operates a modular and HTTP-based botnet first discovered in late 2011. The threat actor has shown the capability to evolve and harden its methods over time, with increased complexity in loader and AV evasion techniques. The Andromeda botnet has been observed being used by Transparent Tribe and APT 36, with a motivation for financial gain. The threat actor has targeted victims worldwide across various sectors. The threat actor's tools and techniques have evolved from version 2.06 to 2.10, demonstrating improvements in loader evasion and payload variations. A takedown effort in December 2017 led to the arrest of the suspected botnet owner, potentially ending the reign of the Andromeda botnet. The threat actor's country of origin is Belarus. The threat actor was dismantled in an international cyber operation in November 2017.





Report 2

Summary:
The threat actor "Andromeda Spider" has been active since late 2011 and is known for its long-running and prevalent malware campaigns. The threat actor primarily targets victims through various methods such as spam email campaigns, illegal download sites, and exploit kits like Neutrino and Angler. The threat actor constantly evolves its malware by changing PE packers and obfuscators to avoid detection by antivirus software. Additionally, Andromeda employs sophisticated techniques like custom encryption, API function hashing, and anti-vm tricks to complicate analysis and evade detection. The threat actor uses hardcoded NTP domains for communication, injects system libraries, and offers modular plugins for functionalities like keylogging and remote control. The threat actor's persistence techniques involve injecting into system processes like msiexec.exe and camouflaging malware binaries among legitimate system files. Andromeda's C&C communication is encrypted with RC4 and uses JSON format for requests. The threat actor's C&C servers are hosted on multiple domains and the malware downloads plugins from Source Forge repository. Overall, Andromeda demonstrates a high level of sophistication and persistence in its malicious activities, making it a challenging threat to analyze and combat.





Report 3

Summary:
The threat actor "Andromeda Spider," also known as Gamaru and Wauchos, is a modular HTTP-based botnet that was discovered in late 2011. It evolved through versions 2.06 to 2.10, with the latest version seen in 2015. The threat actor used sophisticated techniques to evade detection, including complex loader structures and anti-VM and anti-analysis features in the payload. The C&C communication evolved with different message formats for Action Request and Task Report. The threat actor was capable of stealing information, communicating with the C&C server, and downloading additional malware onto the system. The suspected botnet owner was arrested in December 2017, potentially marking the end of the Andromeda era. The threat actor targeted victims in various sectors, with evidence of novel tools and techniques used to evade detection and analysis. The report provides detailed technical information on the evolution and capabilities of the threat actor.


