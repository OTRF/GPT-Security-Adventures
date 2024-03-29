
Report 1

Summary:
- Threat actor: APT36, Transparent Tribe
- Region: India
- Operating sector: Defence organizations and Government organizations in India
- Date: July 8, 2020
- APT36 targeted personnel in India using a "honey trapping" technique, luring targets with fake profiles of attractive women to download malware.
- APT36 utilized the Crimson RAT tool for data-stealing activities and sending data to a CnC server.
- The threat actor used two infection chains involving spear-phishing emails with macro-loaded documents or direct dropper modules.
- APT36 targeted individuals related to the Indian Defence sector, focusing on personal accounts due to firewall restrictions.
- The Crimson RAT tool exhibited capabilities such as process manipulation, file operations, screen capture, and data exfiltration.
- APT36's targeting of organizations in India's eastern states was noted, indicating a shift in their usual strategic interests.
- IOCs associated with the "honey trap" campaign were provided for identification and mitigation efforts.





Report 2

Malformed report





Report 3

Malformed report.





Report 4

APT36, also known as Transparent Tribe, targeted victims in the defense, embassies, and government sectors in India. The threat actor used a decoy health advisory document to spread a Remote Administration Tool (RAT) during the coronavirus pandemic. APT36, a Pakistani state-sponsored group, has been active since 2016 and is known for using spear phishing and watering hole attacks. The group has a history of deploying RATs like BreachRAT, DarkComet, Luminosity RAT, and njRAT to compromise sensitive data from Indian military and government databases. The Crimson RAT used by APT36 in this campaign was written in .Net and had capabilities such as stealing credentials, listing running processes, and capturing screenshots. The threat actor's use of novel phishing patterns and Urdu-named directories indicates a new approach in their tactics. Malwarebytes users were protected against this attack, which highlights the importance of endpoint protection systems and keeping software up-to-date to defend against such threats. The operation was reported on March 16, 2020.





Report 5

Summary:
The APT trends report for Q1 2020 by Kaspersky highlights the activities of threat actors such as Transparent Tribe, APT 36. The report covers various regions including the Middle East, Southeast Asia, and the Korean Peninsula. The threat actors targeted victims in different sectors, including military entities and government organizations. Evidence of the threat actor's capabilities was demonstrated through the use of novel tools and techniques, such as a watering-hole utilizing a full remote iOS exploit chain and a new module named USBWorm. The report also mentions the exploitation of the COVID-19 pandemic by threat actors for spear-phishing campaigns. Overall, the report emphasizes the continuous growth of APT activities in Asia and the evolving tactics of both established and emerging threat actors.





Report 6

Summary:
- Threat actor: APT36 (Transparent Tribe)
- Region: Believed to be operating on behalf of Pakistan state with a focus on countries like India
- Operating sector: Military organizations, government entities
- Novelty of tools and techniques: Main malware dubbed "Crimson RAT" used for espionage, payload delivery through malicious documents and compressed files, multi-stage dropper with encrypted payloads, basic persistence mechanism, C2 communication via simple TCP protocol
- Date: Since 2013
- Conclusion: Despite lackluster tradecraft, APT36 has been successful in executing espionage campaigns, but customers are protected against this threat.





Report 7

Summary:
The threat actor "Transparent Tribe, APT 36" has been identified by SentinelOne for distributing the CapraRAT mobile remote access trojan (RAT) through Android applications that mimic YouTube. The group targets military, diplomatic personnel, and the Indian Education sector in India and Pakistan. CapraRAT is a highly invasive tool allowing control over infected Android devices, with capabilities such as recording audio and video, collecting messages and call logs, and modifying system settings. The group uses social engineering to distribute weaponized apps outside the Google Play Store. The RAT's configuration and C2 infrastructure show similarities to Transparent Tribe's Windows tool, CrimsonRAT. The threat actor's use of YouTube-themed apps is a novel tactic in their espionage efforts. Defensive measures include avoiding third-party apps and evaluating permissions requested by unfamiliar applications. CapraRAT is detectable by SentinelOne's Singularity Mobile solution. The report was published on September 18, 2023.





Report 8

Summary:
A cyber attack campaign targeted the Central Bureau of Investigation (CBI) and potentially Indian Army officials by impersonating the Indian think tank IDSA. The attackers used spear-phishing emails with malicious Excel files to infect victims with malware capable of downloading additional components and spying on systems. The attackers employed anti-analysis techniques like password-protected macros and storing malicious content in a TextBox within the UserForm to evade detection. The malware communicated with a C2 server, validated connections, sent system and process information, and had functionalities for downloading and executing files, updating itself, and deleting/uninstalling. The C2 domain qhavcloud[.]com was associated with the attack, along with a hard-coded IP address in Pakistan. The attack showed similarities to previous campaigns targeting Indian government entities, suggesting possible involvement of a Pakistan state-sponsored cyber espionage group. Indicators of compromise were provided for detection and mitigation. The attackers demonstrated advanced techniques to remain undetected and gain long-term access to compromised systems. 

Date: 7 years ago
Region: India
Operating Sector: Government (Central Bureau of Investigation) and potentially Defense (Indian Army)
Type of Company: N/A





Report 9

Summary:
The threat actor APT-36, also known as Transparent Tribe, targeted Indian government organizations, military personnel, and defense contractors with a new Linux malware campaign named Poseidon. The malware was distributed through a backdoored version of the Kavach authentication tool, a 2FA solution provided by the Indian government. Poseidon, a second-stage payload, is a general-purpose backdoor that allows attackers to log keystrokes, capture screens, upload/download files, and administer systems remotely. The malware infrastructure used by APT-36 was linked to earlier campaigns, indicating a continued focus on Indian targets. The threat actor's activities could lead to significant repercussions, including data loss, compromised systems, financial losses, and reputational damage. The novel techniques and tools used by APT-36 highlight the evolving threat landscape and the importance of robust cybersecurity measures. The report provides technical analysis of the malware samples and indicators of compromise associated with the campaign. The Uptycs XDR solution offers detection and protection against the Poseidon malware used by APT-36. The report emphasizes the need for vigilance and cybersecurity best practices to mitigate the risks posed by Transparent Tribe and other threat actors.





Report 10

Summary:
- Threat actor: APT-36 (Transparent Tribe)
- Region: India
- Operating sector: Indian governmental organizations
- Date: Throughout 2022
- Evidence of capability: APT-36 targeted Indian government employees using malvertising, credential harvesting attacks, and a new data exfiltration tool named "Limepad." They abused Google Ads to push malicious domains to the top of search results and used PyInstaller to compile malicious binaries. The threat actor registered multiple new domains and controlled third-party application stores to distribute backdoored versions of Kavach applications.
- Novelty of tools and techniques: APT-36 evolved their tactics by incorporating new distribution methods and tools, including the Limepad data exfiltration tool. They used a time zone check to ensure execution only on machines configured with India time zone. The threat actor also conducted credential harvesting attacks by spoofing official Indian government websites.
- Conclusion: APT-36 remains a prevalent threat group targeting Indian governmental organizations, leveraging various tactics to lure victims. Users are advised to exercise caution while downloading applications and verify sources. Zscaler continues to monitor and protect against these threats.





Report 11

Summary:
APT36, also known as Earth Karkaddan, a politically motivated APT group, targeted Indian military and diplomatic resources using social engineering and phishing lures to deploy the Crimson RAT malware. In late 2021, they leveraged CapraRAT, an Android RAT similar to Crimson RAT. The crossover in tools' functions and capabilities is detailed in the investigation based on data from January 2020 to September 2021. Earth Karkaddan used spear-phishing emails with various lures to deceive victims. The group also employed ObliqueRat malware in campaigns, distributed through social engineering tactics. CapraRAT, a custom Android RAT used by Earth Karkaddan, showed similarities to Crimson RAT. The group's capability to deploy malware on both Windows and Android systems indicates their evolving tactics. The report provides insights into the group's attack chains, tools, and techniques, emphasizing the need for enhanced security measures to defend against APT attacks. The investigation reveals the group's persistence in stealing information through sophisticated methods.





Report 12

Summary:
The Securonix Threat Research team identified a new malicious attack campaign by the threat actor STEPPY#KAVACH targeting the Indian government. The campaign involved phishing emails with .LNK files initiating code execution to download and run a C# RAT payload. The attack shared similarities with APT36/SideCopy/TransparentTribe campaigns targeting Indian government employees. The RAT files referenced .pdb files and were hosted on IP addresses from Germany. The attack chain involved JavaScript execution, file downloads, and C2 communications. The RAT payload, mm1.exe, had capabilities for C2 command execution, additional payload download, screenshots, and file exfiltration. The attack was ongoing for a year, indicating active threat actors with inside knowledge of Indian government systems. Securonix provided recommendations and detection queries for mitigation. The attack utilized various MITRE ATT&CK techniques and referenced previous reports on Transparent Tribe campaigns. The report provided technical insights and detection methods using Securonix. 

Date: Not specified in the report. 

Region: India

Operating Sector: Indian Government

Type of Company: Threat Intelligence/Security Solutions

Evidence of Capability: Use of phishing emails, C# RAT payload, .LNK files, JavaScript execution, C2 communications, file downloads, and various attack techniques. 

Novelty of Tools and Techniques: The use of .LNK files, C# RAT payload, JavaScript execution, and specific targeting of Indian government systems. 

Malformed report.





Report 13

Summary: The threat actor known as Transparent Tribe, APT 36, was involved in a cyber-espionage operation targeting the Indian Army. The threat actor utilized an Android app called SmeshApp, which was used to collect data on Indian troop movements. The app, disguised as a simple IM application, gathered geolocation data, photos, emails, messages, and call history from users and sent it to a server in Germany rented by an individual in Karachi, Pakistan. The operation involved honeytraps and a social media spam campaign to lure Indian army personnel into using the app. Indian officials issued warnings against using SmeshApp in February 2016, following suspicions of data collection. Google intervened and removed the app from the Play Store on March 15, 2016. The threat actor's capability to exploit mobile apps for espionage purposes and the novelty of using such tactics in the region demonstrate the evolving nature of cyber threats. 

Date: February 2016 - March 15, 2016
Region: India, Pakistan
Operating Sector: Military
Type of Company: Indian Army

Source: https://news.softpedia.com/news/smeshapp-removed-from-play-store-because-pakistan-used-it-to-spy-on-indian-army-501936.shtml





Report 14

Transparent Tribe, also known as APT 36, is a threat actor originating from Pakistan that has been actively targeting victims in the defense, education, embassies, and government sectors across multiple countries, including India, Afghanistan, and the USA. The group has been linked to various aliases and has been observed using a wide range of tools and techniques, including the Andromeda botnet and a variety of remote access Trojans (RATs) such as Crimson RAT, QuasarRAT, and ObliqueRAT. Transparent Tribe's operations date back to at least 2012, with notable campaigns like "Operation Transparent Tribe" in 2016 and "Operation Honey Trap" in 2020 targeting Indian military and defense organizations. The threat actor has shown an evolution in its capabilities, with new campaigns using bespoke malware and novel tools like USBWorm and CapraRAT. Recent reports indicate that Transparent Tribe continues to pose a significant threat, with new attack campaigns targeting Indian government officials and the education sector. The group's motivation appears to be information theft and espionage, with a focus on collecting sensitive data about troop movements and military activities. The threat actor's persistence, wide-ranging targets, and use of advanced tools highlight the ongoing threat posed by Transparent Tribe to organizations in the region.





Report 15

Summary:
The threat actor Transparent Tribe, also known as APT 36, has been active since 2013 and continues to target Indian military and government personnel. In a recent report by Kaspersky, it was revealed that Transparent Tribe has developed a new Android implant disguised as a porn-related app and a fake COVID-19 tracking app to spy on mobile devices. The group has also been linked to the ObliqueRAT malware. The Android implant used by Transparent Tribe is a modified version of the AhMyth Android RAT, with new features added by the attackers for improved data exfiltration. The group has been distributing trojanized code through pandemic-tracking applications and malicious documents. The report provides IoCs for further investigation. Transparent Tribe is constantly evolving and expanding its operations, with a focus on infecting mobile devices and developing new custom tools. The group's activities are expected to continue, and monitoring efforts are ongoing.





Report 16

Summary:
- Threat actor: Transparent Tribe, APT 36
- Region: Pakistan
- Operating sector: Espionage operations against Indian diplomats and military personnel in Saudi Arabia and Kazakhstan
- Type of company targeted: Indian public fund
- Date: February 21, 2020
- Evidence of capability: Custom RATs exfiltrating information, taking screenshots, and recording webcam streams
- Novel tools and techniques: Malicious macro document disguised as a request for a DSOP FUND, self-extracting macro creating folders and executing scripts, Python stub malware with encrypted communication, modular implant downloading components from C2, sophisticated encryption methods, persistence through LNK file creation in startup menu
- Indicators of Compromise: Hashes, Yara rules
- Conclusion: Transparent Tribe resurfaced after years of inactivity, targeting defense personnel with espionage and counterintelligence campaigns. Possible link to current tensions between countries.





Report 17

Transparent Tribe, also known as APT36, a Pakistan-aligned threat actor, has expanded its interest in the Indian education sector. The group has been observed distributing Crimson RAT malware through malicious Office documents, using techniques such as OLE embedding. Transparent Tribe, active since at least 2013, has previously targeted Indian military and government personnel but has now shifted focus to educational institutions and students in the Indian subcontinent. The group's malware arsenal includes Crimson RAT, with various versions and capabilities, such as exfiltrating system information and capturing screenshots. Transparent Tribe has been observed experimenting with different malware staging techniques, including the adoption of OLE embedding. The threat actor also employs obfuscation techniques, such as Eazfuscator, to protect their Crimson RAT implementations. This activity was reported on April 13, 2023, by SentinelOne.


