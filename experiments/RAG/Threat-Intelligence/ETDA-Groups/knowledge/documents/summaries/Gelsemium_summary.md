
Report 1

Summary:
The threat actor Gelsemium, also known as the Gelsemium group, has been active since at least 2014 and is believed to originate from China. Their primary motivation is information theft and espionage. They have targeted victims in various sectors such as education, gaming, government, high-tech, NGOs, and religious organizations across multiple countries including Argentina, China, Iran, Japan, Russia, and the UAE. Gelsemium has been associated with the use of a variety of tools including ASPXSpy, Cobalt Strike, and Gelsemine. Notable hacking operations include "Operation TooHash" in 2014, "Operation NightScout" in 2021 targeting the update mechanism of NoxPlayer, and the discovery of a poorly detected backdoor in 2021 by Kaspersky. The threat actor's capabilities were further evidenced by the discovery of rare backdoors tied to Gelsemium in a targeted attack on a Southeast Asian government in mid-2022. The group's novel techniques and tools have posed a significant challenge to cybersecurity efforts.





Report 2

The threat actor known as "Gelsemium" has been identified by Kaspersky for deploying a poorly detected backdoor named SessionManager within the Internet Information Services (IIS) web server, primarily targeting governmental institutions and NGOs in Africa, South Asia, Europe, and the Middle East. The backdoor, first utilized in late March 2021, allows for a wide range of malicious activities, including email collection and complete control over the victim's infrastructure. The SessionManager backdoor enables persistent and stealthy access to compromised servers, with a poor detection rate that has allowed it to remain undetected in over 90% of targeted organizations. The threat actor behind SessionManager has shown a particular interest in NGOs and government entities, as well as medical organizations, oil companies, and transportation companies. Kaspersky experts believe that the Gelsemium threat actor may be responsible for leveraging the SessionManager backdoor as part of its espionage operations. The use of this backdoor highlights a trend among threat actors to exploit vulnerabilities within Microsoft Exchange servers, emphasizing the importance of threat intelligence and proactive defense strategies to mitigate such risks.





Report 3

Summary:
- Threat actor "Gelsemium" conducted a supply-chain attack targeting online gaming communities in Asia, specifically using the update mechanism of NoxPlayer, an Android emulator for PCs and Macs.
- The attack involved the distribution of three different malware families to selected victims in Taiwan, Hong Kong, and Sri Lanka, with surveillance-related capabilities rather than financial gain.
- The attack was highly targeted, affecting only 5 out of over 100,000 NoxPlayer users, indicating a focus on intelligence collection within the gaming community.
- The attack leveraged compromised BigNox infrastructure to host malware and deliver tailored malicious updates, with evidence suggesting tampering with the update mechanism.
- Novel tools and techniques were used, including the deployment of malware variants with keylogging capabilities and the use of trident bundles to disguise malicious components.
- The attack timeline spanned from September 2020 to January 2021, with the threat actor demonstrating a sophisticated understanding of supply-chain compromise tactics.
- The threat actor's intent appeared to be focused on collecting intelligence on specific targets involved in the gaming community, showcasing a unique approach to cyberespionage operations.
- The attack highlights the ongoing threat of supply-chain attacks in the cyber landscape, emphasizing the need for vigilance and proactive security measures.
- The report provides detailed IoCs, malware analysis, and MITRE ATT&CK techniques associated with the attack, offering valuable insights for threat intelligence and mitigation efforts.





Report 4

Summary:
- Threat actor "Gelsemium" targeted a Southeast Asian government entity with a cluster of activity observed by Unit 42.
- The activity spanned over six months between 2022-2023 and featured rare tools and techniques, including web shells, OwlProxy, and SessionManager backdoors.
- The combination of tools used by the threat actor, particularly SessionManager and OwlProxy, is unique and previously associated with Gelsemium APT group.
- Gelsemium APT group has been operational since 2014, targeting a diverse range of entities in East Asia and the Middle East.
- Limited information has been available about Gelsemium's tactics, techniques, and procedures, making this cluster of activities significant.
- The threat actor behind CL-STA-0046 demonstrated the capability to adapt to mitigation processes by delivering new tools.
- Protections and mitigations provided by Palo Alto Networks products include Advanced WildFire, Advanced URL Filtering, DNS Security, Cortex XDR, and Cortex XSIAM.
- Indicators of compromise include web shells, the Potato Suite, Demo.exe, OwlProxy, SessionManager, Cobalt Strike, SpoolFool, EarthWorm, and specific infrastructure.
- The activity highlights the need for enhanced security measures and proactive threat intelligence sharing among government entities in Southeast Asia.
- Unit 42 associates the activity observed with Gelsemium APT group with a moderate level of confidence, emphasizing the importance of multilayered defense against evolving threat actors.


