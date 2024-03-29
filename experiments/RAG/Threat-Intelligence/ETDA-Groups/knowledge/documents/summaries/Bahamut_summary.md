
Report 1

Malformed report.





Report 2

Summary:
In November 2022, CYFIRMA detected a cyber-attack on an Indian intelligence operative by the threat actor Bahamut, known for conducting cyber strikes in the Middle Eastern and South Asian regions. The attack involved a strategic social engineering tactic using a malicious Android app disguised as an encrypted file-sharing platform. This marked the first time Bahamut used such a decoy app in an attack. The threat actor leveraged permissions to access sensitive data like SMS, call logs, contacts, and location information. The attack was dismantled before causing damage, showcasing Bahamut's expertise in targeted social engineering attacks. The Bahamut APT group, attributed with high confidence to the attack, is known for its persistence and use of novel techniques in cyber espionage operations. This operation highlights the evolving capabilities of Bahamut in targeting intelligence operatives with sophisticated tactics.





Report 3

Summary:
- Threat actor APT Bahamut targeted individuals in South Asia with advanced Android malware disguised as a dummy chatting app named "SafeChat" delivered via WhatsApp.
- The malware exhibited similarities to tactics used by APT DoNot, with increased permissions posing a higher threat level.
- The threat actor exploited Android Libraries to extract and transmit data to a command-and-control server, utilizing sophisticated methods.
- Evidence of capability includes permissions for location tracking, accessing contacts, SMS, call logs, and encryption of data using RSA.
- The threat actor's use of the Ktor Library for data retrieval and encryption techniques align with previous tactics employed by APT DoNot.
- The attack was attributed to APT Bahamut, with a focus on spear messaging attacks on WhatsApp targeting individuals in South Asia.
- The threat actor's previous targets align with the interests of one nation state government, possibly indicating ties to Indian territory.
- Indicators of compromise include a SHA256 hash for the malicious APK and a domain/port for command and control.
- MITRE ATT&CK techniques used by the threat actor include location tracking, encryption of data, and exploitation of permissions for data collection.
- The threat actor's tactics suggest ties to Indian territory and acting in the interest of one nation state government.





Report 4

Malformed report





Report 5

Malformed report.





Report 6

Summary:
The threat actor Bahamut, also known as Bellingcat, has been active since 2016, primarily targeting individuals in the Middle East involved in human rights and activism. The victims operate in political, economic, and social sectors in countries like Egypt, Iran, Pakistan, and Qatar. Bahamut's main motivation is information theft and espionage. The threat actor has been observed using tools like Bahamut and DownPaper, with a focus on phishing campaigns and reconnaissance activities. Bahamut's operations have shown a novel approach, including the use of open-source mobile device management systems to target specific devices. The threat actor has been linked to multiple hacking operations targeting individuals in the Middle East and South Asia, with a particular focus on Android and iOS malware. Bahamut's activities have been ongoing, with reported campaigns as recent as 2023, indicating a persistent and evolving threat.





Report 7

Summary:
- Threat actor: Bahamut
- Date: June 4, 2020 - Mid-February 2021
- Region: Middle East and South Asia
- Operating sector: Entities and individuals
- Type of company: Not specified
- Capability: Utilizes anti-analysis techniques, multi-stage infection chains, social engineering, and user interaction
- Novelty of tools and techniques: Exploited CVE-2017-8570, used template injection, dropped VB executables, employed backdoor functionality
- Low confidence assessment of Bahamut's involvement due to limited unique indicators of compromise or TTPs
- Tools and techniques used align with previously observed Bahamut activity
- Malicious infrastructure included domains like lobertica.info and IP addresses like 185.175.158.227





Report 8

Malformed report.





Report 9

Summary:
- Threat actor: Bahamut
- Region: Middle East and South Asia
- Operating sector: Not specified
- Type of company: Not specified
- Capability: Bahamut is an Advanced Persistent Threat (APT) group known for phishing campaigns delivering malware with new spying capabilities targeting mobile devices.
- Novelty of tools and techniques: Bahamut returned in April 2022 with a new variant of Android malware distributed via phishing sites, targeting messaging applications like Viber, Imo, Signal, Telegram, etc., in addition to collecting Personally Identifiable Information (PII).
- Date: April 2022
- Evidence: The malware collects data from messaging apps, contact information, SMS and call logs, files, and basic device information, sending it to a Command and Control (C&C) server.
- Conclusion: Bahamut's reemergence with enhanced spying capabilities indicates a clear agenda to spy on targeted entities, with potential future changes in activities and targets.





Report 10

Summary:
The threat actor known as Bahamut has been identified by Cyble targeting users through a phishing campaign involving malicious Android APK files hosted on counterfeit Jamaat websites. The Bahamut group, operating in the Middle East and South Asia, uses phishing campaigns and malware as attack vectors. The malware identified is a variant of spyware that uploads data to a Command & Control server. The malware disguises itself as the Jamaat chat app and Muslim Youth app. The threat actor requests dangerous permissions from users, collects information such as contacts, SMS, call logs, and uploads data to the C&C server every 4 hours. The Bahamut malware uses Socket.IO for communication and HTTPS protocol to communicate with the C&C server. The group frequently uses phishing pages to deliver malware and targets users accessing Jamaat domains with Android Spyware. To protect against such threats, users are advised to install applications only from official app stores and follow cybersecurity best practices. The report provides Indicators of Compromise (IoCs) and MITRE ATT&CK® Techniques associated with the Bahamut threat actor. The operation time window for this threat actor is ongoing.


