
Report 1

Flax Typhoon, a state-sponsored threat actor originating from China, has been active since mid-2021, targeting government agencies, education, critical manufacturing, and information technology organizations primarily in Taiwan, with some victims in Southeast Asia, North America, and Africa. The actor focuses on persistence, lateral movement, and credential access, utilizing tools such as China Chopper, Metasploit, Juicy Potato, Mimikatz, and SoftEther VPN. Flax Typhoon employs living-off-the-land techniques and hands-on-keyboard activity, exploiting known vulnerabilities in public-facing servers to gain initial access and establish persistent access over remote desktop protocol. The threat actor's motivation is information theft and espionage, with Microsoft directly notifying targeted or compromised customers to secure their environments. The report does not specify a specific date or operation time window for the observed activities.





Report 2

Flax Typhoon, a nation-state activity group based in China, has been targeting organizations in Taiwan since mid-2021, focusing on government agencies, education, critical manufacturing, and information technology sectors. The threat actor uses legitimate software and living-off-the-land techniques to gain and maintain access to networks, primarily relying on tools like China Chopper web shell, Metasploit, Juicy Potato privilege escalation tool, Mimikatz, and SoftEther VPN client. Flax Typhoon exploits known vulnerabilities in public-facing servers to establish initial access, escalates privileges, establishes persistence through RDP, and deploys a VPN connection to actor-controlled network infrastructure. The threat actor conducts credential access activities using tools like Mimikatz to target hashed passwords and SAM registry hive. Microsoft has not observed Flax Typhoon acting on final objectives in this campaign, but the threat actor's persistence and espionage intentions raise significant concerns. Mitigation against Flax Typhoon attacks involves vulnerability and patch management, proper system hardening, and monitoring for unauthorized network traffic and malicious activity. The campaign's indicators of compromise include IP addresses and TLS certificates used by Flax Typhoon's network infrastructure. The report provides detailed detection and hunting queries for Microsoft 365 Defender and Microsoft Sentinel customers to identify related activity in their networks. The report was published on July 14, 2024, by Microsoft Security Blog.


