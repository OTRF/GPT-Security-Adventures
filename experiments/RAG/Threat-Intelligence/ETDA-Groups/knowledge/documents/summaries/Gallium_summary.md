
Report 1

Summary:
- Threat actor "Gallium" targeted a Southeast Asian government entity from early 2022 to 2023, linked to Alloy Taurus, believed to operate on behalf of Chinese state interests.
- The attacks involved exploiting vulnerabilities in Exchange Servers to deploy web shells for long-term espionage operations.
- Tools and malware used included Reshell and Zapoa backdoors, Cobalt Strike, Quasar RAT, HDoor, Gh0stCringe RAT, and a variant of Winnti malware.
- The threat actor used techniques like credential theft, lateral movement, reverse SSH tunneling, and downloading additional tools via PowerShell.
- The activity was part of a cluster identified as CL-STA-0045, with a moderate level of confidence attributed to Alloy Taurus.
- The threat actor's playbook and tools used were unique, indicating a sophisticated and persistent threat.
- The operation targeted government entities in Southeast Asia, posing a significant threat to regional security.
- Protections and mitigations were provided for Palo Alto Networks customers against the identified threats.
- The threat actor's modus operandi, victimology, and infrastructure overlaps led to the attribution of the threat actor behind CL-STA-0045 to Alloy Taurus.
- Enhanced security measures, monitoring, and threat intelligence sharing are recommended to combat evolving tactics employed by threat actors like Alloy Taurus.





Report 2

Summary:
- Threat actor: Chinese Alloy Taurus (aka GALLIUM, Softcell)
- Operating sector: Telecommunications, finance, government entities in Asia, Europe, Africa
- Novelty of tools and techniques: Identified a new variant of PingPull malware targeting Linux systems, use of backdoor Sword2033, leveraging China Chopper capabilities, integration of custom tooling
- Date: First samples of PingPull malware date back to September 2021, recent activity in South Africa and Nepal
- Evidence of capability: Active since at least 2012, routine cyberespionage campaigns, historical targeting of telecommunications companies, expansion to financial institutions and government entities
- Tools used: PingPull malware, Sword2033 backdoor, HTTP communication, AES encryption, C2 infrastructure
- Protection: Palo Alto Networks customers receive protections through Cortex XDR, WildFire malware analysis, Advanced URL Filtering, DNS Security Cloud-Delivered Security Services
- Conclusion: Alloy Taurus remains an active threat, evolving operations with new malware variants and backdoors, organizations advised to deploy protective measures

Malformed report.





Report 3

Summary:
- Threat actor named GALLIUM targeted global telecom providers predominantly from 2018 to mid-2019.
- GALLIUM exploited unpatched internet-facing services using publicly available exploits, targeting vulnerabilities in WildFly/JBoss.
- Once inside a network, GALLIUM used common tools like Mimikatz for lateral movement and credential theft.
- GALLIUM's infrastructure relied on dynamic DNS domains and reused hop points, primarily hosted in mainland China, Hong Kong SAR, and Taiwan.
- The threat actor used off-the-shelf tools like HTRAN, Mimikatz, and PsExec for reconnaissance and lateral movement.
- GALLIUM's malware included modified versions of Gh0st RAT (QuarkBandit) and Poison Ivy, with a focus on evading antimalware detection.
- Recommended defenses included maintaining web server patching, enabling cloud-delivered protection, and using behavior detection solutions.
- GALLIUM's activity was identified through Microsoft's internal practices, assigning the code name GALLIUM to the threat actor.
- The threat actor's activity levels have decreased compared to previous observations, but they are still active.
- The report provides detailed information on GALLIUM's tactics, techniques, and procedures, encouraging active defenses to protect against their attacks.





Report 4

Summary:
- Threat actor: GALLIUM
- Date: June 13, 2022
- Operating sectors targeted: Telecommunications, Government, Finance
- GALLIUM, an APT group, has been using a new remote access trojan named PingPull.
- The group has targeted telecommunications companies in Southeast Asia, Europe, and Africa, expanding to financial institutions and government entities.
- PingPull uses ICMP, HTTP(S), and raw TCP protocols for command and control communications, making it difficult to detect.
- PingPull variants allow threat actors to run commands, access reverse shells, and perform various activities on compromised systems.
- Infrastructure analysis revealed multiple subdomains and IP addresses associated with GALLIUM.
- Protections and mitigations are recommended for organizations in the targeted sectors.
- GALLIUM remains an active threat, and organizations are advised to deploy protective measures against this group.





Report 5

Summary:
The threat actor Gallium, also known as Phantom Panda, Granite Typhoon, and Alloy Taurus, has been active since 2018, with a focus on information theft and espionage. Operating from China, Gallium targets unpatched internet-facing services using publicly available exploits, particularly vulnerabilities in WildFly/JBoss. They use common tools like Mimikatz for lateral movement within compromised networks. Gallium's infrastructure consists of dynamic-DNS domains and reused hop points. The threat actor has targeted sectors such as Financial, Government, and Telecommunications, with reported hacking operations using tools like Cobalt Strike and Gh0stCringe RAT. Gallium's activity has decreased since mid-2019, but they remain a persistent threat. Notable operations include the use of the PingPull malware and ongoing cyberespionage against Southeast Asian governments.


