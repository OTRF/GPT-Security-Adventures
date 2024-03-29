
Report 1

Malformed report





Report 2

Summary:
- Threat actor: Pirate Panda, APT 23, KeyBoy
- Date: April 30, 2020
- Region: Vietnam, specifically targeting government employees in the Municipality of Da Nang
- Operating Sector: Government data center
- Evidence of Capability: Spear phishing email containing a malicious Excel document dropping a DLL providing CMD reverse shell over HTTP, code similarities to exile-RAT associated with Pirate Panda
- Novelty of Tools and Techniques: Use of DLL Side-Loading technique, communication with C2 skypechatvideo[.]online, genetic similarity to exile-RAT and keyboy RATs
- Targeted Victims: Government employees likely working in a data center
- Potential Impact: Access to vast amounts of sensitive information if successful
- Conclusion: Consistent with previous data center targeting by APTs, potential compromise of government-run data center for sensitive information access.





Report 3

Malformed report





Report 4

Summary:
The threat actor known as KeyBoy targeted members of the Tibetan Parliament in August and October 2016 using known exploits to deliver a custom backdoor. The operation focused on avoiding basic antivirus detection, showing a development cycle aimed at exploiting targets with minimal technical sophistication. The threat actor reused older exploits against the Tibetan community due to their limited technical capacity and lack of security controls. KeyBoy, a backdoor first disclosed in 2013, was used in the operation, with evidence of a development cycle focused on evading detection. The threat actor used social engineering tactics and repurposed content to target victims, showing a systematic technical adaptation to reduce detection. The operation targeted the Tibetan Parliamentarians, showing signs of a sophisticated and persistent threat actor. The threat actor's infrastructure was based in China and Hong Kong, with limited passive DNS information available. The threat actor's persistence and evolution of tools and techniques indicate a high level of sophistication and a continuous effort to avoid detection. The operation highlights the ongoing threat to the Tibetan community and the need for increased security awareness and diligence.





Report 5

Malformed report





Report 6

Malformed report





Report 7

The threat actor known as 'KeyBoy' targeted Tibetan and Chinese Pro-Democracy Activists on June 6, 2013, exploiting unknown vulnerabilities in Microsoft Office, patched by MS12-060. Rapid7's analysis revealed that 'KeyBoy' also targeted interests in Vietnam and India. The threat actor used services like changeip.com to establish free subdomains, blending in with legitimate traffic to evade detection. The attackers registered their own second-level domain, phmail.us, linked to malicious activity since December 2011. The threat actor employed a tactic of intermittently providing routable IPs to certain requesters, possibly to evade detection. TRAC recommends analyzing DNS traffic for IoCs and maintaining the latest patches to thwart attacks. The novelty of the threat actor's techniques lies in the use of free subdomains and intermittent IP responses to avoid detection.





Report 8

Tropic Trooper, also known as Pirate Panda, APT 23, KeyBoy, is a state-sponsored threat actor originating from China. Since 2011, they have targeted government, healthcare, transportation, and high-tech industries in Taiwan, the Philippines, and Hong Kong. They have used a variety of tools such as 8.t Dropper, CREDRIVER, Poison Ivy, and USBferry to conduct information theft and espionage. Their operations include "Operation Tropic Trooper" targeting Taiwanese and Philippine military agencies, as well as campaigns against Vietnam, India, and the Tibetan community. Notably, in 2017, they expanded to mobile platforms with the Titan surveillanceware. The threat actor's activities have been ongoing, with the latest reported operation in 2020 targeting transportation and government organizations. Their use of novel tools and techniques, along with their persistent targeting of specific sectors and regions, demonstrate their advanced capabilities and ongoing threat to targeted entities.





Report 9

Summary:
- Threat actor: Tropic Trooper, also known as Pirate Panda, APT 23, KeyBoy
- Date: November 16, 2017
- Region: Taiwan and the Philippines
- Operating sector: Enterprises and military units
- Type of company: Not specified
- Evidence of capability: Titan surveillanceware with advanced functionalities such as call history retrieval, text message retrieval, location tracking, and more.
- Novelty of tools and techniques: Titan evolved from Java to native libraries, uses legitimate app icons, and iterates through command and control servers.
- Infrastructure: Domains and IP addresses associated with Titan, with ongoing research on live servers.
- Conclusion: Lookout continues to track Titan variants due to its links to targeted attacks against enterprises and defense institutions.





Report 10

Summary:
- Threat actor: Tropic Trooper, also known as Pirate Panda, APT 23, KeyBoy
- Region: Asia Pacific, specifically targeting Taiwan
- Operating sector: Taiwanese Government and Fossil Fuel Provider
- Date: November 22, 2016
- Novelty of tools and techniques: Tropic Trooper used Poison Ivy RAT, Yahoyah malware, and possibly PCShare malware, exploiting CVE-2012-0158. They employed spear-phishing emails with decoy documents related to political events in Taiwan. The threat actor demonstrated capability in bypassing traditional antivirus solutions and used various C2 infrastructure for communication. The payload delivered included Poison Ivy Trojan with specific configurations for C2 communication. The threat actor has been active since at least 2011 and continues to reuse payloads within their exploit documents.





Report 11

Summary:
The threat actor known as Earth Centaur, previously identified as Tropic Trooper, is a sophisticated cyberespionage group targeting transportation companies and government agencies related to transportation. The group has been active since 2011 and has recently been observed attempting to access internal documents and personal information on compromised hosts. Evidence suggests that the threat actor is proficient at red teamwork, bypassing security settings, and using backdoors with different protocols to evade detection. Novel tools and techniques include the use of custom backdoors like ChiserClient, HTShell, Lilith RAT, and SmileSvr, as well as credential dumping and indicator removal techniques. The threat actor's activities indicate a high level of sophistication and capability, with a focus on data exfiltration and network penetration. The report provides detailed technical analysis and indicators of compromise for security teams to enhance their defenses against this threat actor.

Date: N/A

Region: Global

Operating Sector: Transportation and Government

Type of Company: N/A





Report 12

Summary:
The threat actor known as Tropic Trooper, also referred to as KeyBoy, has been observed targeting Taiwanese, Philippine, and Hong Kong entities in sectors such as government, healthcare, transportation, and high-tech industries. They have displayed a high level of organization and have developed their own cyberespionage tools, with recent campaigns showcasing new behaviors in maintaining network footholds. The threat actor employs exploit-laden Microsoft Office documents to deliver malware, utilizing techniques such as DLL hijacking and injection to evade detection. Tropic Trooper's use of SSL protocol for C&C communication and the ability to easily update C&C servers indicate a sophisticated and adaptable threat actor. The report emphasizes the importance of proactive incident response strategies and provides indicators of compromise for detection and mitigation. The campaign's use of socially engineered documents and blending with legitimate traffic underscores the need for robust cybersecurity measures and employee awareness. The report also highlights best practices for organizations to defend against such threats, including patch management, network segmentation, and monitoring. The threat actor's use of PDB strings in malware analysis provides insights into their operations and tactics, aiding in the development of effective response strategies.





Report 13

Tropic Trooper, a threat actor group targeting government, military, healthcare, transportation, and high-tech industries in Taiwan, the Philippines, and Hong Kong, has been active since 2011. The group uses spear-phishing emails with weaponized attachments to exploit known vulnerabilities for information theft and espionage. Their latest activities involve targeting Taiwanese and Philippine military's physically isolated networks through a USBferry attack, with victims including military/navy agencies, government institutions, military hospitals, and a national bank. The USBferry malware, with at least three versions, performs different commands on specific targets, maintains stealth, and steals critical data through USB storage. The group has been active since 2014, focusing on stealing defense-, ocean-, and ship-related documents. Tropic Trooper uses backdoors, steganography, and other tools to infiltrate networks and evade detection. The group's tactics highlight the importance of enforcing the principle of least privilege, keeping systems updated, and monitoring the network perimeter to defend against advanced persistent threats. Trend Micro solutions like Apex One and Deep Discovery can provide actionable threat intelligence and proactive response capabilities.


