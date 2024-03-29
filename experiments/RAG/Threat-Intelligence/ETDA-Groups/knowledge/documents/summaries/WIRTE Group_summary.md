
Report 1

Summary:
The report discusses the activities of the threat actor group WIRTE in the Middle East since at least 2019. The threat actor utilizes VBS/VBA implants in MS Excel droppers to drop their first-stage implant, which collects system information and executes arbitrary code. The victims targeted are mainly in the Middle East, with a focus on government, diplomatic entities, law firms, and financial institutions. The threat actor is attributed with high confidence to the WIRTE group, with a suspected low confidence relation to the Gaza Cybergang. The threat actor employs living-off-the-land techniques and COM hijacking for persistence. The report highlights the use of new tools and techniques by the threat actor, such as LitePower stager and custom user-agents for C2 communications. The threat actor's TTPs indicate an evolution in their toolset and operational methods to remain undetected for extended periods. The report provides indicators of compromise for detection and mitigation.





Report 2

The threat actor WIRTE Group, also known as LAB52, was first identified by the DFIR team of S2 Grupo in August 2018. They primarily target victims in the Middle East, specifically in sectors such as Defense, Government, and diplomats. Despite using seemingly unsophisticated mechanisms like unencrypted communications and Powershell scripts, they are successful in infecting victims and achieving their objectives. The group's tools include EmpireProject, H-Worm, Living off the Land, and various scripts. Their motivation is information theft and espionage. The detection rate of their scripts by antivirus software is low, indicating a level of novelty in their techniques. The threat actor presents decoy documents in Arabic to their victims. The report does not specify a specific operation time window, but the threat actor has been active since at least 2018.





Report 3

Summary:
- Threat actor identified as WIRTE Group targeting the Middle East.
- Operating sector: Diplomacy of Middle Eastern countries.
- Victims targeted with unsophisticated mechanisms using Powershell and HTTP.
- Novelty in using Visual Basic Script (VBS) as a control tool.
- Date of operation: August 2018.
- Tools include Empire post-exploitation framework.
- Decoy documents in Arabic tailored to specific targets.
- Scripts with low detection rates by antivirus software.
- Persistence established through backdoors in Powershell.
- Different decoy documents for each script targeting specific interests and regions.


