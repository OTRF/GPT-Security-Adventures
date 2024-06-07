
Report 1

Malformed report.





Report 2

Summary:
The APT trends report for Q1 2020 by Kaspersky highlights the activities of various threat actors, including Promethium and StrongPity. The report mentions COVID-19 themed lures used by APT groups like Kimsuky, APT27, Lazarus, and ViciousPanda to target victims, including health and humanitarian organizations. In January 2020, a Chinese-speaking APT group named TwoSail Junk was discovered utilizing a full remote iOS exploit chain to target users in Hong Kong. Russian-speaking APT groups like Sofacy and Gamaredon were also active, with the latter deploying a new second-stage payload called "Aversome infector." In the Middle East, StrongPity targeted victims in Turkey with an updated backdoor named StrongPity2, while a new Trojan called Milum was discovered in a campaign named WildPressure. The report also mentions the activities of threat actors in Southeast Asia and the Korean Peninsula, including Lazarus, DarkHotel, and DarkHotel's involvement in a campaign targeting companies in South Korea and Japan. The report concludes with insights on the continuous growth of APT activity in Asia, the exploitation of software vulnerabilities, and the use of mobile platforms for infections.





Report 3

Malformed report.





Report 4

Summary:
The threat actor "Promethium, StrongPity" has been identified by Alien Labs conducting ongoing malware campaigns since the second half of 2018 up to July 2019. The threat actor has been deploying malicious versions of trusted software like WinBox router management software, WinRAR, and others to compromise targets. StrongPity has been active since at least 2012 and has been using various tactics to evade detection, such as rerouting users to download malware instead of legitimate software. The threat actor continues to operate successfully with new samples of malware identified in early July 2019, indicating a toolset rebuild in response to previous public reporting. The malware communicates with C2 servers over SSL and targets technically-oriented victims. The threat actor's TTPs and the use of legitimate software to deliver malware remain consistent with past operations, showcasing operational success with minimal modifications to evade detection. The report provides indicators of compromise and technical details on the identified malware samples. 

Date: July 17, 2019
Region: Global
Operating Sector: Various
Type of Company: Not specified





Report 5

Summary:

The threat actor known as Promethium, StrongPity, targeted Italian and Belgian encryption users in the summer of 2016. The group is technically capable, deploying zero-day exploits, spearphishing tactics, and maintaining a modular toolset. They focused on users of encryption tools like WinRAR and TrueCrypt, with a particular interest in encrypted data and communications. The threat actor used creative waterholing and poisoned installer tactics to distribute malware, showing determination, innovation, and recklessness. The group set up fake distribution sites mimicking legitimate ones to deliver trojanized installers, affecting systems in multiple countries. The malware components dropped by StrongPity included keyloggers, data stealers, and backdoors, indicating a focus on stealing sensitive information. The group's activity peaked in the summer of 2016, targeting encryption-enabled software applications with watering hole and social engineering tactics. The report highlights the need for verifying the integrity of downloaded files and the importance of strong anti-malware solutions in the face of such threats. The StrongPity APT group's activities are available for further analysis to customers of Kaspersky Intelligent Services.





Report 6

Promethium, also known as StrongPity, is an activity group that has been active since at least 2012, primarily targeting Turkish victims. The group has been linked to information theft and espionage, with observed attacks in various countries including Algeria, Belgium, Canada, and the USA. Promethium utilizes Truvasys, a first-stage malware that has evolved over the years to masquerade as common computer utilities. The group has been reported to adapt quickly to new information and stay under the radar with minimal code changes. StrongPity, StrongPity2, and StrongPity3 are among the tools used by this threat actor. Recent operations include a data exfiltration campaign in Turkey in February 2020 and the deployment of Android malware in July 2021. The threat actor has shown a capability to continuously evolve their tools and techniques to target a wide range of victims in different sectors and countries.





Report 7

Summary:
The threat actor known as StrongPity, also referred to as APT-C-41 and PROMETHIUM, has been active since 2012 and targets specific users by adding backdoors to legitimate software. They have been observed in campaigns targeting users in Belgium, Italy, Turkey, Syria, and other regions, focusing on niche user groups interested in encryption software. StrongPity has been detected using zero-day vulnerabilities in software like Adobe Flash and has been linked to nation-state cyber surveillance activities. The threat actor employs tactics like water holing and has been observed using trojanized versions of popular software like WinRAR, CCleaner, and TeamViewer. StrongPity's backdoor collects files with specific extensions and sends them to a central server operated by the threat actor. The actor has expanded its global reach through mass phishing email campaigns and has targeted victims in Europe, Northern Africa, Canada, and Asia. The threat actor's tools and techniques, including anti-debugging functionality and obfuscation techniques, indicate a high level of sophistication. LMNTRIX and other security companies have reported on StrongPity's activities, highlighting the actor's focus on financial organizations, industrial plants, and educational institutes. The threat actor's extensive data collection program and infrastructure suggest a well-organized and persistent cyber threat. The StrongPity backdoor is well-detected by the antivirus industry, indicating a focus on targeting individuals rather than company networks. The threat actor's ability to evade detection and maintain a large data processing infrastructure raises concerns about the extent of their operations. The novelty of StrongPity's tools and techniques lies in their use of trojanized software and sophisticated data collection methods. The threat actor's activities demonstrate a long-standing presence in the cyber threat landscape and a continued focus on geopolitical targets. (Date: Ongoing)





Report 8

Summary:
The StrongPity APT group deployed Android malware for the first time, targeting the Syrian e-Gov website. This marks a novel approach for the threat actor, showcasing their capability to develop and distribute malicious Android applications. The group repackaged benign applications to deliver trojanized versions, stealing contact lists and specific file extensions from victims' devices. Evidence suggests that StrongPity is actively developing new malicious components for Android platforms, using compromised websites and fake apps to distribute malware. The threat actor's tactics, techniques, and procedures (TTPs) on Windows platforms show similarities in file harvesting and exfiltration methods. The Android malware samples were attributed to StrongPity based on infrastructure links and shared TTPs. The group's development of new Android trojans indicates an ongoing threat to mobile devices. The report provides indicators of compromise (IOCs) for detection and mitigation.





Report 9

Summary:
- Threat actors PROMETHIUM and NEODYMIUM targeted individuals in Europe in early May 2016 using a zero-day exploit for CVE-2016-4117 in Adobe Flash Player.
- PROMETHIUM primarily used Truvasys malware, masquerading as common computer utilities, while NEODYMIUM used a backdoor malware called Wingbird.
- PROMETHIUM distributed links through instant messengers, while NEODYMIUM used spear-phishing emails with attachments to deliver the exploit code.
- Both threat actors showed capability in using advanced malware and exploiting memory corruption vulnerabilities.
- Microsoft Defender ATP was able to detect and respond to the attacks by capturing behavioral signals and using machine learning analytics.
- The attacks were unusual as the threat actors targeted individuals for information gathering rather than monetary gain or economic espionage.
- The use of the same zero-day exploit, timing of the campaigns, and geographic location of victims suggested a possible connection between PROMETHIUM and NEODYMIUM.
- The report provides details on the behavior of the malware used by NEODYMIUM and indicators of compromise for both threat actors.
- The report also highlights the importance of post-breach detection and the capabilities of Windows Defender ATP in detecting and responding to advanced attacks.
- For more information, refer to the Microsoft Security Intelligence Report volume 21.





Report 10

The threat actor known as Promethium or StrongPity targeted regions in Turkey and indirectly into Syria, as well as Egypt, utilizing Sandvine/Procera Deep Packet Inspection hardware to insert malware into benign Internet traffic. The threat actor adapted quickly after being exposed by researchers, changing infrastructure and utilizing new domains and IP addresses to stay under the radar. The malware targeted legitimate application installers like Internet Download Manager, VLC Player, and Avast. The threat actor used unique encoding methods for string obfuscation, such as pushing encoded Unicode strings onto the stack and XORing them against a single byte key. The malware communicated over SSL on port 443 to C2 servers using unique User-Agent strings. The threat actor's capability to adapt quickly and use novel techniques to evade detection was evident in their response to threat intelligence reports. The report was published on October 23, 2018, by Cylance Threat Intelligence Bulletin.


