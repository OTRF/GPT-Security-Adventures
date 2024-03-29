
Report 1

Summary:
The threat actor TEMP.Veles, also known as Xenotime and ATK 91, is a Russia-based group sponsored by the Central Scientific Research Institute of Chemistry and Mechanics. They target critical infrastructure sectors such as energy, manufacturing, and oil and gas in countries like Saudi Arabia and the USA. TEMP.Veles is known for using the TRITON malware framework to manipulate industrial safety systems, showcasing their capability for sabotage and destruction. Their activities date back to 2014 with the TRISIS malware and have expanded to include the electric utility sector in 2019. The group has been targeted by counter operations, including US Treasury sanctions in 2020 and DOJ indictments of Russian government officials in 2022. Their use of novel tools like Cryptcat, Mimikatz, and Triton sets them apart as a significant threat in the cybersecurity landscape.





Report 2

The threat actor known as "TEMP.Veles" targeted victims in the Middle East, specifically focusing on safety instrumented systems (SIS) in the region. The malware, named TRISIS, was developed to target Schneider Electric's Triconex SIS, marking the fifth ever ICS-tailored malware and the first to directly target SIS. The attack resulted in operational impact for at least one victim in the Middle East. The malware's tradecraft represents an escalation in attacks seen to date, as it is specifically designed to target the safety function of the process. While the malware is not highly scalable, it serves as a blueprint for other adversaries looking to target SIS. The attack highlighted the importance of proper configuration and security measures for SIS controllers to mitigate such threats. The Dragos team provided detailed analysis and recommendations in their report, emphasizing the significance of this event for the community. The report was released on December 14, 2017, and is available to Dragos threat intelligence customers for further information and technical details.





Report 3

The threat actor known as TRITON has been active since at least 2014 and has targeted critical infrastructure facilities. The actor has been linked to a Russian government-owned technical research institute in Moscow. They have used a custom attack framework to manipulate industrial safety systems, causing process shutdowns. The actor leveraged a variety of custom and commodity intrusion tools, focusing on anti-virus evasion and maintaining access to IT and OT networks. The actor's tools and techniques indicate a deep interest in ensuring prolonged and persistent access to the target environment. They have demonstrated a strong development capability for custom tooling and have shown a preference for Windows systems as conduits to the ultimate target. ICS asset owners are advised to prioritize detection and defense across Windows systems in both IT and OT. The actor's TTPs and custom tooling have been shared to help defenders hunt for related activity and improve defenses. FireEye's SmartVision technology can help detect attackers during lateral movement activities in IT and OT networks. The report provides detailed insights into the actor's methodologies and discovery strategies, including tips for identifying evidence of their activity. The report encourages a focus on "conduit" systems to identify and stop ICS-focused intrusions. The actor's capabilities and activities have been shared to raise awareness and encourage proactive defense measures. The report includes appendices with discovery rules, technical analysis of custom attack tools, and MITRE ATT&CK JSON raw data. (Source: https://www.fireeye.com/blog/threat-research/2019/04/triton-actor-ttp-profile-custom-attack-tools-detections.html)





Report 4

Summary:
- Threat actor TEMP.Veles, linked to the TRITON intrusion impacting industrial control systems, is likely supported by the Russian government-owned research institute CNIIHM in Moscow.
- Evidence includes malware development activity supporting TEMP.Veles, testing of malicious software, and IP address usage by TEMP.Veles for monitoring and reconnaissance.
- Behavior patterns, file creation times, and language artifacts suggest TEMP.Veles operators are based in Moscow, consistent with CNIIHM involvement.
- CNIIHM possesses the institutional knowledge and personnel to assist in TRITON and TEMP.Veles operations, with research divisions experienced in critical infrastructure and military equipment development.
- Unlikely that CNIIHM employees conducted TEMP.Veles activity without approval, as the institute's characteristics align with the specialized nature of TRITON framework development.
- Date: Oct 23, 2018. 

Source: https://www.fireeye.com/blog/threat-research/2018/10/triton-attribution-russian-government-owned-lab-most-likely-built-tools.html





Report 5

Summary:
State-sponsored Russian cyber actors targeted the global Energy Sector, including U.S. and international organizations, from 2011 to 2018. The threat actors used multiple intrusion campaigns, deploying ICS-focused malware and exfiltrating data. Novel tools like Havex malware and TRITON (HatMan) malware were used to manipulate safety systems in oil refineries and energy companies. The threat actors, including FSB officers and TsNIIKhM employees, were indicted by the U.S. Department of Justice in March 2022. The threat actors targeted U.S. Energy Sector networks, deployed sophisticated malware, and engaged in reconnaissance, lateral movement, and data collection activities. Mitigations include implementing network segmentation, enforcing MFA, and managing privileged accounts to reduce the risk of compromise. The threat actors continue to pose a threat to U.S. Energy Sector networks, urging organizations to apply recommended mitigations. The report provides detailed technical information on the tactics, techniques, and procedures used by the threat actors, as well as recommendations for securing enterprise and ICS/OT environments. The report was last revised on March 24, 2022.





Report 6

Summary:
The threat actor known as XENOTIME, previously focused on oil and gas sectors, has expanded its targeting to the electric utility sector, indicating a trend of ICS-targeting adversaries diversifying their targets. The threat actor has demonstrated capabilities in disrupting critical infrastructure and has shown interest in targeting safety instrumented systems (SIS) for disruptive or destructive purposes. XENOTIME's activities include external scanning, network enumeration, and attempts at external access, with a focus on North American and European companies. While no successful intrusions into electric utility organizations have been reported, the persistent attempts and expansion in scope are concerning. The threat actor's novelty lies in its willingness to compromise process safety in ICS environments, posing a significant risk to lives and infrastructure. The report emphasizes the importance of asset identification, threat behavior detection, and response and recovery planning for ICS operators to mitigate the risks posed by XENOTIME's activities. The expansion of XENOTIME's targeting to the electric sector highlights the need for cross-industry collaboration and proactive security measures in industrial environments.





Report 7

XENOTIME is a threat group that has been active since at least 2014 and is considered the most dangerous threat activity publicly known. They are known for intentionally compromising and disrupting industrial safety instrumented systems, which can lead to loss of life and environmental damage. XENOTIME rose to prominence in December 2017 when they targeted Schneider Electric’s Triconex safety instrumented system with the TRISIS malware, causing industrial systems in a Middle Eastern facility to shut down. This incident represented a shift in the capabilities and consequences of ICS malware. XENOTIME's TRISIS malware framework was highly tailored and required specific knowledge of the Triconex infrastructure, indicating a high level of sophistication. The group has been identified targeting safety systems beyond Triconex and operates globally, impacting regions far outside of the Middle East. XENOTIME has no known associations with other activity groups. Their custom malware framework and tailored credential gathering tools demonstrate their capability to cause potential disruptive or destructive events. Dragos assesses with moderate confidence that XENOTIME intends to establish the required access and capability for future attacks.


