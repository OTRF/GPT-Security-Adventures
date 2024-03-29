
Report 1

Summary:
- Threat actor named POLONIUM, now tracked as Plaid Rain, targeted Israeli organizations with a focus on critical manufacturing, IT, and defense industries.
- POLONIUM utilized unique tools that abused legitimate cloud services for command and control, deploying custom implants like CreepyDrive and CreepySnail.
- Evidence suggests POLONIUM collaborated with Iran's Ministry of Intelligence and Security (MOIS) based on victim overlap and common techniques.
- POLONIUM compromised over 20 Israeli organizations and an intergovernmental organization in Lebanon using tools like AirVPN and plink for C2.
- Microsoft detected and disabled POLONIUM's attack activity abusing OneDrive, suspending malicious applications and providing security updates.
- The threat actor exploited vulnerabilities like CVE-2018-13379 in Fortinet appliances to gain initial access to victims.
- Microsoft recommended actions for customers include investigating IOCs, updating security products, and enabling multifactor authentication.
- The report provides detailed information on POLONIUM's TTPs, custom implants, exploitation methods, and recommendations for detection and protection.
- The activity was observed from February 2022 onwards, targeting various sectors including critical manufacturing, IT, transportation, defense, and government agencies.
- Microsoft continues to monitor POLONIUM's activities and implement protections for customers against the threat actor.





Report 2

Summary:
The threat actor known as Polonium, believed to be based in Lebanon and potentially affiliated with Iran's MOIS, has targeted over 20 organizations in Israel and an intergovernmental organization in Lebanon in the past three months. They have been using unique tools that exploit legitimate cloud services for command and control, such as creating and using OneDrive accounts for their attacks. The actor's motivation appears to be information theft and espionage, with victims operating in sectors like engineering, defense, IT, manufacturing, media, and telecommunications. Polonium has been observed using tools like CreepyDrive, CreepySnail, and TechnoCreep. Their operations have been reported as early as September 2022 targeting Israel with Creepy malware. The threat actor's novel techniques and tools indicate a high level of capability and sophistication.





Report 3

The Polonium APT group, based in Lebanon, exclusively targets Israeli companies. First detected by Microsoft in June 2022, the group's activity was further analyzed by ESET in October 2022, revealing over a hundred malicious files. Deep Instinct's threat research team discovered three additional samples from the Polonium arsenal, showcasing new attack tools and techniques. These include an additional MegaCreep loader and files of a possible new "Creepy" malware. The group uses small components to complicate investigations and a multi-step attack flow to evade detection. The threat actor's use of custom external libraries and VisualBasic components indicates a high level of sophistication. The Polonium group's focus on Israeli companies and the novelty of their tools make them a significant threat in the cybersecurity landscape.


