
Report 1

Summary:
- Threat actor UTA0178 exploited two zero-day vulnerabilities in Ivanti Connect Secure VPN devices, allowing unauthenticated remote code execution.
- The attack was detected by Volexity in December 2023, with evidence of lateral movement and webshell placement on internal and external servers.
- Volexity identified two zero-day exploits used by the threat actor, enabling full unauthenticated command execution on the VPN appliance.
- The threat actor, attributed to a Chinese nation-state-level actor, leveraged the exploits to steal data, modify files, and exfiltrate credentials.
- The attacker used webshells, proxy utilities, and file modifications for credential harvesting and lateral movement within the network.
- The attacker's tools and techniques included modifying legitimate components, deploying webshells, and capturing credentials through JavaScript modifications.
- Volexity recommends organizations monitor network traffic, analyze VPN device logs, and execute the Integrity Checker Tool to detect compromise.
- The threat actor's infrastructure and indicators were identified, including IP addresses and domains associated with UTA0178.
- Volexity acknowledges Ivanti's support in addressing the vulnerabilities and protecting organizations using Ivanti Connect Secure software.
- The report was published on January 10, 2024, by Volexity, providing detailed insights into the threat actor's activities and exploitation methods.





Report 2

Summary:
- Threat actor UNC5221 targeted Ivanti Connect Secure VPN with zero-day exploits, impacting Ivanti Connect Secure VPN and Ivanti Policy Secure appliances.
- The threat actor leveraged custom malware families, including ZIPLINE, THINSPOOL, LIGHTWIRE, WIREFIRE, and WARPWIRE, for post-exploitation activities.
- UNC5221 used PySoxy tunneler and BusyBox for post-exploitation activities, demonstrating advanced capabilities.
- The threat actor's use of THINSPOOL for persistence and detection evasion, along with the deployment of web shells, indicated a sophisticated and targeted attack.
- UNC5221 primarily targeted out-of-support Cyberoam VPN appliances for C2 communication.
- The threat actor's activity suggests an espionage-motivated APT campaign, targeting high-priority victims.
- Mandiant recommended implementing Ivanti's mitigation measures and following patch release schedules.
- The threat actor's use of zero-day exploits, edge device compromise, and C2 infrastructure highlighted espionage actors' evolving tactics.
- The report did not link UNC5221 to a known group, indicating a novel threat actor.
- The report provided indicators of compromise (IOCs) and YARA rules for detection and mitigation.

Date: January 10, 2024
Operating Sector: Private Industry
Type of Company: Ivanti Connect Secure VPN
Region: Global

Source: https://www.mandiant.com/resources/blog/suspected-apt-targets-ivanti-zero-day





Report 3

Summary:
- Threat actor UTA0178 exploited two zero-day vulnerabilities (CVE-2024-21887 and CVE-2023-46805) in Ivanti Connect Secure (ICS) VPN appliances globally.
- Volexity observed evidence of compromise of over 1,700 devices worldwide, targeting victims from various sectors including government, military, telecommunications, defense contractors, technology, banking, finance, accounting, consulting, aerospace, aviation, and engineering.
- The threat actor used a webshell named GIFTEDVISITOR with a unique AES key on each victim system, indicating sophistication and novelty in their techniques.
- The exploitation began on January 11, 2024, and continued with evidence of other threat actors attempting to exploit the vulnerabilities.
- Volexity assessed with medium confidence that the widespread exploitation was undertaken by UTA0178 based on the webshell used and the speed of the attacks post-publication of exploit details.
- The threat actor UTA0188 was also observed attempting exploitation on patched ICS VPNs, indicating multiple threat actors with access to the exploit.
- Volexity recommended organizations to apply the mitigation provided by Ivanti, run the Integrity Checker Tool, and respond to compromise following their guidelines.
- The threat actor's capability to compromise thousands of machines globally and the involvement of multiple threat actors highlight the severity and complexity of the attack.
- The report provides a detailed timeline of findings and actions taken by Volexity to address the threat actor's activities.
- The report emphasizes the need for organizations to take immediate action to protect their systems from further exploitation.





Report 4

UNC5221, also known as UTA0178, is a threat actor that has been actively exploiting vulnerabilities in Ivanti Connect Secure VPN and Ivanti Policy Secure appliances since December 2023. The vulnerabilities, CVE-2023-46805 and CVE-2024-21887, allow for authentication bypass and command injection, leading to network compromise. The threat actor's motivation is information theft and espionage, with victims targeted worldwide in various sectors. UNC5221 has been observed using a variety of tools such as GIFTEDVISITOR, GLASSTOKEN, and PySoxy, indicating a high level of sophistication. The use of zero-day exploits and novel techniques by UNC5221 demonstrates their advanced capabilities in cyber operations. The threat actor's activities are currently under active analysis by Mandiant and Ivanti, with ongoing efforts to track and mitigate their operations.


