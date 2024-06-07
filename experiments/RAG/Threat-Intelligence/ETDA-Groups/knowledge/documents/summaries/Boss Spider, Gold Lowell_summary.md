
Report 1

Boss Spider, also known as Gold Lowell, is a threat actor tracked by CrowdStrike Falcon Intelligence. They are responsible for developing and operating the Samsam ransomware. The malware uses external tools like Mimikatz, PsExec, and Sdelete for propagation and cleanup. Boss Spider has anti-forensics capabilities that make it difficult to recover the ransomware payload. The ransomware is delivered in encrypted form alongside a runner file in some cases. The payload is loaded into memory, making recovery challenging. Boss Spider targets various sectors and companies, with a focus on encrypting specific file extensions associated with data backup. The threat actor utilizes AES encryption and RSA public keys for file encryption. CrowdStrike Falcon Prevent can detect and prevent the malware before any files are encrypted. The threat actor's novel techniques and tools make them a significant threat in the cybersecurity landscape.





Report 2

Boss Spider, also known as Gold Lowell, is a financially motivated threat actor group originating from Iran. Since late 2015, they have been conducting ransomware campaigns using SamSam ransomware to target organizations in the education, government, and healthcare sectors. They exploit known vulnerabilities in Internet-facing systems to gain access and then demand payment for decryption of files. The group is associated with consistent use of tools like Mimikatz, PsExec, and SDelete. In 2018, two Iranian men were indicted for deploying ransomware attributed to Boss Spider, causing over $30 million in losses. Organizations are advised to apply security updates promptly, monitor for anomalous behaviors, and have response plans in place for ransomware incidents.





Report 3

Summary:
- Threat Actor: GOLD LOWELL associated with the SamSam ransomware campaigns.
- Region: Global, targeting small to medium-size organizations.
- Operating Sector: Various industry verticals, with a focus on opportunistic network compromises.
- Novelty of Tools and Techniques: GOLD LOWELL combines commodity and proprietary tools with publicly available exploits and techniques. They use custom ransomware tool kits, scan-and-exploit techniques, and third-party tools like Mimikatz and Hyena.
- Evidence of Capability: The threat actor demonstrates a strong understanding of encryption, Windows network environments, and the ability to escalate privileges and move laterally within compromised networks.
- Date/Operation Time Window: Ongoing since late 2015, with a notable campaign generating at least $350,000 in revenue between late-2017 and early-2018.
- Defensive Evasion: GOLD LOWELL modifies tools, evades endpoint protection, and uses Tor network for ransom payments.
- Attribution: Linguistic errors in ransom notes suggest non-native English speakers, uncertainty in attribution due to use of publicly available tools.
- Strategic and Tactical Threat Intelligence: CTU researchers provide strategic and tactical information to help organizations defend against GOLD LOWELL's activities.
- Recommendations: Prioritize security controls for Internet-facing systems, conduct regular penetration testing, monitor for anomalous behaviors, and create and test incident response plans.


