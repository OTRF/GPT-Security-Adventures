
Report 1

Summary:
The threat actor "Pacha Group" has been targeting Linux servers since September 2018 and has recently expanded its operations to cloud-based environments. They are actively disrupting other crypto-mining groups, particularly "Rocke Group," known for targeting cloud environments. Pacha Group's new variants share code with previous ones, with low detection rates. They have implemented advanced evasion and persistence techniques, including a blacklist of miners used by Rocke Group and IP blacklisting. Pacha Group's infrastructure includes a user-mode rootkit and customized versions of functions to hide processes. They have also added IP blacklisting using a unique technique to disrupt routing processes. The evidence suggests a competition for cryptocurrency mining foothold on the cloud between Pacha Group and Rocke Group. The report provides IOCs and a YARA rule for detection. Date of report: 9 May 2019. Operating sector: Cloud-based environments. Type of company: Threat intelligence.





Report 2

Rocke, a China-based cryptomining threat actor, has evolved its tactics by changing its Command and Control (C2) infrastructure to self-hosted solutions and DNS text records, moving away from Pastebin. The actor has added functionality to exploit ActiveMQ servers vulnerable to CVE-2016-3088. This change in technique showcases the threat actor's sophistication and makes detection more challenging. Rocke primarily focuses on illicit cryptomining, targeting compromised machines. The threat actor's capability to adapt and use novel techniques, such as DoH requests for encrypted instructions, demonstrates their evolving capabilities. Enterprises should ensure software is up-to-date and strong passwords are used to mitigate the risk of Rocke-styled campaigns. The threat actor's activities were observed during the summer of 2019, with ongoing updates and changes to their malware. The report provides IOCs and MITRE ATT&CK techniques associated with Rocke's operations.





Report 3

The threat actor known as Rocke Group, associated with the Iron cybercrime group, has been evolving their Linux coin mining malware to evade detection by cloud security products. The samples collected in October 2018 revealed that Rocke Group developed new code to uninstall five different cloud security protection and monitoring products from compromised Linux servers. These products were developed by Tencent Cloud and Alibaba Cloud, leading cloud providers in China. This marks the first malware family capable of targeting and removing cloud security products, posing a new challenge for the Cloud Workload Protection Platforms market. The malware exploits vulnerabilities in Apache Struts 2, Oracle WebLogic, and Adobe ColdFusion to deliver the coin mining malware to victim machines. The Rocke Group's malware exhibits behaviors such as achieving persistence, killing other crypto mining processes, adding iptables rules, and uninstalling cloud security products. The malware's capability to evade detection by cloud security products by following uninstallation procedures provided by Alibaba Cloud and Tencent Cloud is a novel trend in malware targeting public cloud infrastructure. The threat actor's C2 infrastructure has been identified, and mitigation efforts are ongoing in collaboration with Tencent Cloud and Alibaba Cloud.





Report 4

Summary:
- Threat actor: Rocke, Iron Group
- Region: Global
- Operating sector: Cryptomining
- Type of company targeted: Mining companies
- Date: May 28, 2019
- Capability evidence: Constantly adding new features to malware, exploiting Jenkins servers, evolving attack stages, using dynamic and flexible execution methods, employing persistence and stealth mechanisms, spreading through SSH and exploiting vulnerabilities in Jenkins, using XMRig CPU miner, embedding configuration in binary, utilizing hook library for stealth, actively updating campaign with new features.
- Novelty of tools and techniques: Using Pastebin for hosting malicious scripts, adding loader stage before payload execution, employing custom UPX compression, adding CRON jobs for script execution, using hooking library for hiding operations, embedding miner configuration in binary, targeting Jenkins vulnerabilities for propagation.





Report 5

Summary:
- Threat actor: Rocke Group
- Date: January 28, 2021
- Region: Global
- Operating sector: Cloud
- Type of company: Not specified
- Evidence of capability: Rocke Group updated their cryptojacking malware to evade detection by cybersecurity companies, including new rootkit and worm capabilities.
- Novelty of tools and techniques: The malware, named Pro-Ocean, uses hiding techniques like LD_PRELOAD, rootkit capabilities, and worm capabilities to infect cloud applications and mine Monero efficiently.
- Tools used: XMRig miner, UPX packing, Bash scripts, Python infection script.
- Targets: Cloud applications like Apache ActiveMQ, Oracle WebLogic, Redis, with a focus on cloud providers in China.
- Protection: Palo Alto Networks Prisma Cloud customers are protected from Pro-Ocean through Runtime Protection and Cryptominers Detection features.





Report 6

Summary:
- Threat actor: Rocke, Iron Group
- Region: China-based
- Operating sector: Cloud environments
- Type of company: Organizations targeted for cryptomining operations
- Capability evidence: Conducting operations with little interference and limited detection risk, maintaining network connections with known Rocke command-and-control domains, releasing new tool called Godlua for additional scripted operations
- Novelty of tools and techniques: Use of Golang programming language, backdoor Godlua, DoS attacks, network proxying, shell capabilities, unique network traffic identification patterns within NetFlow traffic
- Date: Research conducted from December 2018 to June 16, 2019
- Operation time window: Ongoing activities observed until at least June 10, 2019
- Mitigation strategies: Update cloud systems, use cloud monitoring products, review network configurations, use threat intelligence feeds, investigate network traffic for malicious connections
- Protection for Palo Alto Networks customers: C2 domains identified as malicious, illegitimate tools detected by WildFire and Traps, malware signatures released via antivirus, C2 domains covered by PAN-DB URL Filtering
- Indicators of Compromise: Domains sowcar[.]com, thyrsi[.]com, w2wz[.]cn, baocangwh[.]cn, z9ls[.]com, gwjyhs[.]com, heheda[.]tk, cloudappconfig[.]com, systemten[.]org; IPs 43.224.225[.]220, 67.21.64[.]34, 103.52.216[.]35, 104.248.53[.]213, 104.238.151[.]101, 198.204.231[.]250, 205.185.122[.]229; Hashes provided for file samples
- Malware capabilities: Modular functionality, DoS operations, LUA switch functionality, beaconing capabilities, heartbeat style of activity, third-stage malware component
- Detection methods: NetFlow data analysis, identification of network traffic patterns, investigation of connections to known malicious domains or IPs
- Mitigation recommendations: Update cloud systems, use cloud monitoring products, review network configurations, use threat intelligence feeds, investigate network traffic for malicious connections

Overall, the report provides detailed insights into the activities and capabilities of the Rocke threat actor, focusing on their cryptomining operations targeting cloud environments and the use of novel tools and techniques to evade detection and conduct malicious activities.





Report 7

Summary:
The threat actor Rocke, also known as Iron Group, has been active since 2018, with a focus on financial gain. Operating from China, they have targeted various sectors and countries using tools like Godlua, Kerberods, LSD, Pro-Ocean, and Xbash, along with 0-day vulnerabilities. Their tactics have evolved over time, with a shift in C2 infrastructure and the development of new malware variants like Pro-Ocean. They have been involved in multiple hacking operations, targeting cloud environments and seeking to exploit systems like Jenkins for increased infection rates. Counter operations have been reported against Rocke Group, indicating ongoing efforts to mitigate their activities.





Report 8

Rocke Group, a Chinese-based threat actor known for running cryptojacking malware on Linux machines, has been active since 2018. In April 2021, a new malware variant developed by Rocke Group was discovered targeting cloud environments, infecting machines using saved SSH keys and weak passwords. The threat actor exploits vulnerabilities in platforms like Jenkins, Redis, and ActiveMQ to spread the malware. The malware is packed with a modified UPX, making it harder to detect, and uses public SSH keys to infect other machines on the network. Rocke Group implements evasion techniques like library hijacking to hide its activity, and uses an XMRig Miner to mine Monero cryptocurrency. The threat actor's capabilities include creating persistence through scheduled tasks and exploiting vulnerabilities for propagation. Intezer's runtime protection solution can help detect and respond to such attacks by providing visibility into all code running in systems. The report provides IoCs for detection and response, as well as proactive measures to protect against Rocke Group's attacks. The campaign showcases advanced evasion techniques and the use of DNS over HTTPs for communication with C2 servers. Overall, Rocke Group's evolving tactics and techniques highlight the need for robust runtime protection in cloud environments.





Report 9

Rocke, also known as Iron Group, is a threat actor primarily associated with cryptocurrency mining payloads and the Xbash malware family. Recent campaigns by Rocke have shown a combination of cryptocurrency mining payloads with scripts to establish persistence and uninstall security software. The adversary has been active since at least April 2018, targeting Linux systems. Rocke has been observed exploiting remote code execution vulnerabilities in various public-facing services like Oracle Weblogic and Apache Struts. The threat actor uses techniques such as downloading and deobfuscating code, stopping competing miners, discovering competing miners using network connections, persisting with cron jobs, defense evasion through process injection and changing timestamps, and lateral movement using SSH. Rocke's novel techniques include hiding processes with process injection and changing timestamps to hinder forensic analysis. The threat actor's behavior exhibits clear malicious intent, and detection capabilities for Linux endpoints can be enhanced by following recommended steps. The report provides detailed insights into Rocke's tactics, techniques, and procedures, offering guidance on how to detect and defend against this threat actor. (Source: https://redcanary.com/blog/rocke-cryptominer/)


