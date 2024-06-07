
Report 1

The APT-C-23 threat group, also known as Two-tailed Scorpion, has evolved its Android spyware targeting the Middle East region. The group has been active since at least 2017, with new versions of the spyware being discovered in 2020. The Android spyware, detected as Android/SpyC23.A, has advanced spying capabilities, including reading notifications from messaging apps, call recording, and screen recording. The spyware is distributed through a fake Android app store using well-known apps as lures. The threat actor has been using novel techniques such as dismissing notifications from built-in Android security apps. ESET telemetry data shows that Android/SpyC23.A has been in the wild since May 2019, with recent detections in Israel in June 2020. The spyware can perform various actions such as taking pictures, recording audio, exfiltrating call logs, and stealing files with specific extensions. The C&C communication of the malware has been updated to be more covert and dynamic. To prevent falling victim to such spyware, Android users are advised to only install apps from the official Google Play Store.





Report 2

Summary:
The threat actor "Desert Falcons" or Arid Viper is an espionage-motivated cyber threat actor with Hamas-aligned interests targeting Android devices since 2017. They have developed and distributed SpyC23, an Android spyware family, through weaponized apps posing as Telegram or a dating app called Skipped. The actor has a history of using mobile malware, including at least four Android spyware families. Arid Viper's focus on Arabic speakers is a new development, indicating a shift from targeting Israeli military personnel. The threat actor employs social engineering tactics to deliver malware and uses anti-analysis and obfuscation techniques to evade detection. The C2 infrastructure used by the actor follows a naming scheme with Western-sounding people's names. The presence of code from older Arid Viper Android spyware families in SpyC23 strengthens the connection between the group's various iterations of tools. The threat actor continues to thrive in the mobile malware space, targeting military personnel, journalists, and dissidents in the Middle East. The report was published on November 6, 2023, by SentinelOne.





Report 3

The threat actor known as "Desert Falcons" targeted over 100 Israeli servicemen around July last year, compromising their devices and exfiltrating data to a command and control server. The attack, which remains active as of February 2017, focuses on Android OS devices and involves sophisticated intelligence gathering techniques, including accessing video and audio capabilities, SMS functions, and location data. The threat actor heavily relies on social engineering, using social networks to lure victims, particularly IDF soldiers, into sharing confidential information and downloading malicious applications. The operation exhibits relatively unsophisticated technical merit but utilizes novel social engineering tactics. The threat actor's tools include a dropper with obfuscation features, customized payloads, and a network protocol based on HTTP POST requests. The payload, named "WhatsApp_Update," allows for manual and scheduled data collection, real-time command execution, and various intrusive capabilities like eavesdropping and taking pictures. The operation is considered a targeted attack against the Israeli Defense Force, aiming to gather intelligence on ground forces, tactics, and equipment. The IDF, in collaboration with Kaspersky Lab researchers, has identified victims, mostly IDF servicemen serving around the Gaza strip. The threat actor's activities are ongoing, with further details expected to be disclosed at the upcoming Security Analyst Summit.





Report 4

Desert Falcons, also known as APT-C-23, is a threat actor sponsored by Hamas, operating from Gaza since 2011. They have targeted victims in critical infrastructure, defense, education, government, media, and transportation sectors across multiple countries, including Israel, Palestine, and others. The threat actor has developed advanced malware tools like Barb(ie) Downloader, ViperRAT, and GnatSpy to conduct espionage and information theft operations. They have been linked to various hacking campaigns like Operation "Arid Viper" targeting Israeli organizations and "Bearded Barbie" targeting Israeli officials. The threat actor has shown a high level of sophistication and persistence, continuously evolving their tools and techniques, as seen in the discovery of new variants of Android spyware like PyMICROPSIA and Mantis. Counter operations have been conducted against Desert Falcons, such as Operation "Rebound" by the IDF and ISA to dismantle a Hamas operation targeting IDF soldiers.





Report 5

Malformed report





Report 6

The threat actor known as "Two-tailed Scorpion/APT-C-23" conducted a multi-platform surveillance campaign against Palestinians through a mobile surveillanceware family called FrozenCell. The threat targeted employees of Palestinian government agencies, security services, Palestinian students, and individuals affiliated with the Fatah political party. The threat actor used phishing campaigns to distribute malicious executables impersonating individuals associated with government agencies and political parties. FrozenCell was capable of recording calls, extracting SMS messages, geolocating devices, retrieving accounts, and exfiltrating various types of files. The threat actor used OpSec fails and cryptography to hide exfiltrated content, with indicators of compromise identified for both mobile and desktop platforms. The threat actor's infrastructure included multiple domains used for malicious activities. The campaign was discovered on October 5, 2017, and is ongoing, with evidence of continued activity and data exfiltration.





Report 7

Summary:
The threat actor "Desert Falcons" has been identified as the group behind the new GnatSpy mobile malware family, which is a variant of VAMP. The threat actor targeted various sectors in the Middle East, with victims including individuals and specific targeted groups. The GnatSpy malware shows increased sophistication and capabilities compared to previous versions, with improved app structure organization and evasion techniques. The threat actor behind GnatSpy is persistent and continuously improving their malware, indicating ongoing illicit activities. Trend Micro researchers have detected and provided indicators of compromise for the GnatSpy malware. The threat actor's activities are still active and evolving, posing a significant risk to mobile security. 

Date: Not specified in the report.

Malformed report.





Report 8

Summary:
The threat actor known as Desert Scorpion has been identified by Lookout researchers targeting individuals in the Middle East, specifically in Palestine. The actor uses phishing campaigns on platforms like Facebook to distribute their malicious apps. The surveillanceware family ties together two malware families, Desert Scorpion and FrozenCell, indicating the evolving capabilities of the threat actor. The second stage payload of Desert Scorpion includes a wide range of malicious capabilities, such as recording audio and video, retrieving text messages, and tracking device location. The actor's tactics involve separating malicious functionality into separate stages and utilizing social engineering via social media platforms. The threat actor's low-cost, low-sophistication approach has been successful in targeting individuals in the Middle East. Lookout Threat Intelligence continues to monitor the actor's activities and infrastructure to prevent further attacks. (Date: April 16, 2018)





Report 9

Summary:
- Threat actor "Desert Falcons" linked to APT C-23 has developed new variants of Android spyware enhanced for stealth and persistence.
- Operating in the Middle East since 2017, the spyware targets victims in the region, presenting itself as an update app with generic icons and names.
- The spyware uses social engineering to gain permissions on the target's phone, disguising itself as legitimate apps like Chrome or Google.
- New variants can switch command-and-control servers to evade detection and continue operating even after domain takedowns.
- The spyware collects data such as text messages, contacts, call logs, images, and documents, and can record audio and video.
- Sophos researchers found Arabic language strings in the code, indicating a Middle Eastern focus.
- Recommendations include being cautious of app permissions, monitoring app behavior, and using mobile security solutions like Intercept X for Mobile.
- Users are advised to install apps from trusted sources, update OS and apps via official channels, and use anti-malware applications.
- Sophos has published indicators of compromise for the spyware on its Github page.
- The threat actor's use of new techniques and evasion tactics highlights the ongoing development and sophistication of the spyware.





Report 10

Summary:
The threat actor known as "Desert Falcons" has resurfaced with a campaign named Operation Arid Viper targeting organizations primarily in the Middle East, specifically in Israel. The campaign involves delivering a backdoor and spyware through phishing emails promising pornographic or auto accident videos. The malware is capable of filtering out files and exfiltrating data, including keylogging and browser data theft. The threat actor has shown capability in encrypting exfiltrated data using AES-256 in CBC mode. The campaign exhibits novel techniques such as using links instead of attachments, new lures, and encryption for exfiltrated data. The threat remains a risk for organizations in Israel and elsewhere, with indicators of compromise provided for detection. The campaign demonstrates the threat actor's persistence and evolving tactics despite a low profile. The report was published on September 18, 2015, by Proofpoint.





Report 11

Summary:
The threat actor "Desert Falcons" conducted an operation named "Operation Bearded Barbie" targeting Israeli officials, specifically high-profile individuals working in defense, law enforcement, and emergency services. The threat actor, identified as APT-C-23, is politically motivated and operates on behalf of Hamas. They used sophisticated social engineering techniques to deliver new backdoors for Windows and Android devices, including tools like Barb(ie) Downloader and BarbWire Backdoor. The campaign showed a novel approach by targeting Israeli individuals, using fake Facebook profiles to engage with victims. The threat actor upgraded their malware arsenal with enhanced stealth mechanisms and focused on operational security. The campaign demonstrated a significant advancement in APT-C-23's capabilities, showcasing more sophisticated tools and techniques. The operation timeframe was not specified in the report.





Report 12

Malformed report





Report 13

The threat actor "Desert Falcons" has been identified as AridViper, targeting the Middle Eastern region. They have developed a new information-stealing Trojan named PyMICROPSIA, built with Python, showing active development to bypass defenses. The malware family has capabilities such as file uploading, payload downloading, browser credential stealing, keylogging, and more. PyMICROPSIA uses Python libraries like PyAudio and mss for audio recording and screenshots. The C2 protocol is HTTP POST-based with various URI paths for different functionalities. The threat actor is exploring new attack vectors by checking for other operating systems like "posix" or "darwin". PyMICROPSIA downloads additional payloads for keylogging and persistence. The malware shows similarities with previous AridViper tools like MICROPSIA, with Disney references in C2 commands. The malware is still under active development, with incomplete code sections and ongoing implementation. The threat actor's infrastructure includes domains like baldwin-gonzalez[.]live and jaime-martinez[.]info. Palo Alto Networks customers are protected from these attacks.


