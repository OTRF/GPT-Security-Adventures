
Report 1

The threat actor known as TA551, also referred to as Shathak, has been distributing the Valak malware since April 2020 through an email distribution network. Valak is an information stealer and malware loader that relies on scheduled tasks, Windows registry updates, and Alternate Data Stream (ADS) techniques to remain persistent on infected Windows hosts. Recent Valak infections have shown an increase in obfuscated code for configuration scripts to avoid detection. The threat actor has been consistently pushing Valak malware since April 2020, targeting victims through malspam with password-protected ZIP attachments. The distribution network, Shathak/TA551, has been active since at least February 2019 and has evolved to target English, Italian, German, and Japanese-speaking recipients. The threat actor has been associated with Russian cybercriminals and has transitioned from distributing Ursnif to Valak since late April 2020. Valak infections involve an intricate process that includes follow-up malware such as IcedID and NetSupport Manager RAT-based malware. The threat actor's distribution method continues to evolve, and further waves of malspam with Valak are expected. Palo Alto Networks customers are protected from Valak by the Threat Prevention subscription for the Next-Generation Firewall. The report was published on July 24, 2020, by Unit 42 of Palo Alto Networks.





Report 2

TA551, also known as Shathak, is an email-based malware distribution campaign targeting English-speaking victims, with recent activity targeting German, Italian, and Japanese speakers. The threat actor has historically distributed information-stealing malware like Ursnif and Valak, but has shifted to exclusively pushing IcedID malware since mid-July 2020. TA551 is motivated by financial gain and operates out of Russia. The threat actor has been observed using tools such as BokBot, Gozi, Sliver, and Valak. Notably, in October 2021, TA551 utilized the 'SLIVER' Red Team Tool in new activity, showcasing novel techniques. The threat actor's operations have been reported as early as 2016, with ongoing activity documented in 2021. The victims targeted by TA551 operate in various sectors, with a focus on information theft.





Report 3

TA551, also known as Shathak, is an email-based malware distribution campaign that targets English-speaking victims but has recently expanded to target German, Italian, and Japanese speakers. Historically, TA551 has distributed malware families like Ursnif and Valak, but since mid-July 2020, it has exclusively pushed IcedID malware. The infection chain involves spoofed email chains with ZIP attachments containing Word documents with macros that install the IcedID malware on vulnerable Windows computers. The campaign has evolved over time, with changes in targeted languages and malware payloads. TA551 has a history dating back to February 2019, distributing various malware families through email-based attacks. Recent developments include changes in traffic patterns and infection artifacts, indicating an evolving campaign. The threat actor has shifted from distributing Valak and Ursnif to directly deploying IcedID as its malware payload. The report provides indicators of compromise and highlights the importance of spam filtering and system administration to mitigate the risk of infection. Palo Alto Networks Next-Generation Firewall customers are protected from this threat, and AutoFocus customers can track the activity using specific tags.





Report 4

Summary:
- Threat actor TA551, also known as Shathak, was identified by Proofpoint on October 20, 2021, using a new campaign involving the 'SLIVER' Red Team tool.
- TA551 is a highly active cybercrime actor known for distributing malware payloads such as Ursnif, IcedID, Qbot, and Emotet.
- The new activity by TA551 involves sending password-protected zipped Word documents in emails, leading to the download of SLIVER, an open-source adversary simulation and red team platform.
- SLIVER allows for information gathering, command and control functionality, token manipulation, process injection, and other features.
- This activity marks a significant departure from TA551's previous tactics, techniques, and procedures, showcasing considerable actor flexibility.
- TA551's use of SLIVER indicates a shift towards more direct capabilities for execution, persistence, and lateral movement, potentially reducing reliance on secondary access.
- The threat actor's campaigns have been associated with Maze and Egregor ransomware events in 2020.
- TA551's use of SLIVER demonstrates the increasing popularity of red teaming tools among cybercrime threat actors.
- Proofpoint observed indicators of compromise related to the campaign, including document payloads and SLIVER C2 information.
- The threat actor targets victims through email threat campaigns, compromising them to potentially enable the deployment of tools like Cobalt Strike and ransomware.





Report 5

Summary:
The threat actor known as TA551, Shathak, has been observed using IcedID malware as a dropper for other malware families and as a tool for initial access brokers. The attacker demonstrated fast movement from initial infection to lateral movement within an hour, compromising an Active Directory domain in less than 24 hours. The attacker utilized standardized attack flows, borrowed techniques from other threat groups like Conti and Lockbit, and changed the initial infection vector to evade detection. Novel techniques included using ISO and LNK files instead of phishing with malicious macros. The threat actor demonstrated quick exfiltration within two days of initial infection. The attack involved the deployment of IcedID, Cobalt Strike, and AteraAgent RMM tool for persistence and lateral movement. The attacker engaged in credential theft through Kerberoasting, DCSync attacks, and browser hooking. The threat actor also utilized network scanning, data exfiltration via rclone, and malicious network connections. Recommendations include enabling detection and prevention features, blocking password-protected zip files, and resetting Active Directory access. The report provides a detailed timeline of the attack, tools and techniques used, and recommendations for mitigation. The report was published by the Cybereason Global SOC and Incident Response Team.





Report 6

Malformed report.


