
Report 1

Malformed report





Report 2

Summary:
- Threat actor: IMPERIAL KITTEN
- Region: Middle East
- Operating sectors: transportation, logistics, technology
- Date: October 2023
- Evidence of capability: Use of public scanning tools, one-day exploits, SQL injection, stolen VPN credentials for initial access; data exfiltration using custom and open source malware targeting Middle Eastern entities
- Novel tools and techniques: IMAPLoader using email for C2, StandardKeyboard, malware using Discord for C2, Python generic reverse shell via macro-enabled Excel sheet
- Adversary profile: Iran-nexus with suspected connection to IRGC, active since 2017 targeting defense, technology, telecommunications, maritime, energy, consulting sectors
- Tactics: Social engineering, job recruitment-themed content for delivery of .NET-based implants
- Infrastructure: VPS infrastructure associated with low confidence to IMPERIAL KITTEN
- MITRE ATT&CK mapping: Various techniques used for reconnaissance, initial access, execution, persistence, defense evasion, discovery, collection, command and control, exfiltration

Malformed report.





Report 3

Summary:
- Threat actor: TA456, also known as Tortoiseshell, Imperial Kitten
- Region: Middle East, specifically targeting defense contractors supporting efforts in the Middle East
- Operating sector: Aerospace defense contractors, including smaller subsidiaries and contractors
- Capability: TA456 conducted a social engineering and malware campaign using the persona "Marcella Flores" to target an aerospace defense contractor employee with the LEMPO malware, designed for persistence, reconnaissance, and exfiltration of sensitive information.
- Novelty: TA456 demonstrated significant persistence, social engineering, and cross-platform communication, establishing them as a determined Iranian-aligned threat actor. The LEMPO malware utilized Visual Basic Script dropped by an Excel macro for reconnaissance and exfiltration.
- Date: Campaign identified in July 2021, with ongoing engagement since at least November 2020.
- Attribution: TA456 attributed to Iranian-aligned adversary focused on espionage against defense industrial base employees and contractors, with ties to Mahak Rayan Afraz (MRA) and the IRGC.
- Outlook: TA456's resourceful tactics, including benign reconnaissance and social engineering, pose a significant threat to the defense industrial base, requiring vigilance when engaging with unknown individuals.





Report 4

Tortoiseshell, also known as Imperial Kitten, is a state-sponsored threat actor originating from Iran. The group has been active since at least July 2018, targeting IT providers in Saudi Arabia with supply chain attacks to compromise their customers. Evidence suggests that the attackers gained domain admin-level access in at least two organizations. Victims operate in sectors such as Defense, IT, Shipping and Logistics, Maritime, and Shipbuilding in countries including Saudi Arabia, UAE, USA, and the Middle East. The threat actor has used tools like get-logon-history.ps1, IMAPLoader, Infostealer, LEMPO, liderc, and SysKit. Notable operations include a fake veterans job scam in 2019, targeting a defense contractor with social media personas in 2020, and a watering hole attack on shipping and logistics websites in 2023. Imperial Kitten has deployed novel malware families in Middle East-focused operations, showcasing advanced capabilities. Counter operations against the threat actor have been reported, indicating ongoing efforts to mitigate their activities.





Report 5

Yellow Liderc, also known as Imperial Kitten and Tortoiseshell, is an Iran-based threat actor that has been active since at least 2019. The threat actor has targeted various industries and countries, including the maritime, shipping, and logistics sectors in the Mediterranean, nuclear, aerospace, and defense industries in the US and Europe, and IT managed service providers in the Middle East. Yellow Liderc has been observed conducting strategic web compromises to embed JavaScript for fingerprinting website visitors and capturing victim user information. The threat actor has recently used a new malware named IMAPLoader, a .NET malware that acts as a downloader for further payloads and uses email as a C2 channel. IMAPLoader is executed via an injection technique known as 'AppDomain Manager Injection', a novel technique not previously seen with Yellow Liderc. The threat actor has also been involved in widespread phishing activity, delivering malicious Excel files that drop basic Python backdoors. The evolution of tools and techniques used by Yellow Liderc indicates a continuous threat to various sectors and regions aligned with its strategic interests. The report covers activities between 2022 and 2023, with specific indicators of compromise provided for detection and mitigation purposes.


