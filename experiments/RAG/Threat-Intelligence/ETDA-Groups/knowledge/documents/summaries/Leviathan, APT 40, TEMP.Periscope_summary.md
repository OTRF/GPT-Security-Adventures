
Report 1

Summary:
- Threat actor: APT40, also known as Leviathan and TEMP.Periscope, is a China-nexus state-sponsored cyber espionage group.
- Operating region: The threat actor has targeted countries strategically important to China's Belt and Road Initiative, including the United States, United Kingdom, Germany, and others.
- Operating sector: APT40 targets crucial technologies in engineering, transportation, defense, and maritime industries.
- Novelty of tools and techniques: APT40 uses a variety of techniques for initial compromise, including web server exploitation, phishing campaigns, and strategic web compromises. They leverage web shells, backdoors, and credential harvesting tools for establishing foothold and lateral movement. The threat actor maintains presence using backdoors and tools like AIRBREAK and PHOTO. APT40 has developed tools like PAPERPUSH for data targeting and theft.
- Evidence of capability: APT40's targeting aligns with Chinese state interests, and technical artifacts indicate the actor is based in China. The group's operational times suggest a China-based infrastructure procurement process. They have used IP addresses located in China for operations.
- Date: The report was last updated on August 10, 2023.

Overall, APT40 is a sophisticated threat actor with a focus on maritime issues and traditional intelligence targets, likely to continue their cyber espionage operations in the near and medium term.





Report 2

Summary:
Chinese Espionage Group TEMP.Periscope targeted Cambodia ahead of the July 2018 elections, compromising government entities and opposition figures. The group also targeted defense industrial bases in the US and a European chemical company. TEMP.Periscope has an extensive intrusion architecture, a wide array of malicious tools, and the capability to run large-scale intrusions concurrently. Evidence points to Chinese origin, with IP addresses from Hainan, China used for remote access. The group's malware suite includes new tools like EVILTECH and DADBOD. The threat actor's activities indicate a focus on maritime-related targets and political systems of strategically important countries. The operation time window extends from at least April 2017 to the present, with ongoing operations focusing on Cambodia's government and elections. The threat actor is expected to continue targeting government agencies, military, international organizations, and private industry, particularly in the maritime sector. The report was last updated on August 23, 2022.





Report 3

Chinese threat actor TEMP.Periscope targeted a UK-based engineering company in early July 2018 using Russian APT techniques. The attack also targeted a Cambodian journalist covering politics and human rights. TEMP.Periscope reused TTPs from Russian groups Dragonfly and APT28 to gain access to sensitive data. The attack used a unique technique to acquire SMB credentials using a "file://" path in a spearphish. The threat actor also leveraged the open source tool Responder for credential harvesting. The attack was linked to a C2 domain used in a previous campaign targeting Cambodian entities. Recorded Future assesses with medium confidence that TEMP.Periscope adapted TTPs from other groups to target the engineering company. The threat actor is expected to continue targeting high-tech defense and engineering sectors. The report highlights the trend of threat actors emulating each other's techniques to obfuscate attribution. Recorded Future recommends network defense measures to detect and block TEMP.Periscope's intrusion attempts.





Report 4

Summary:
Leviathan, also known as APT 40 and TEMP.Periscope, is a state-sponsored threat actor linked to China's Ministry of State Security, operating since at least 2013. The group targets crucial technologies and intelligence in sectors like defense, engineering, transportation, and maritime industries, with a focus on countries involved in the Belt and Road Initiative. They have used a variety of tools like Cobalt Strike, Gh0st RAT, and PlugX, showing advanced capabilities. Their operations include spear-phishing campaigns against maritime and defense targets, as well as targeting specific companies and government entities in countries like the UK, Cambodia, and Malaysia. Counter operations have been launched against Leviathan, with Chinese nationals charged for global computer intrusion campaigns. The threat actor's activities demonstrate a persistent and evolving threat to global cybersecurity.





Report 5

Leviathan, also known as APT 40 or TEMP.Periscope, is an espionage threat actor targeting defense contractors, universities with military research ties, legal organizations, and government agencies in the United States and Western Europe. The actor has a particular interest in naval industries, including shipbuilding and related research. Operating since at least 2014, Leviathan uses custom JavaScript malware such as "Orz" and "NanHaiShu", Cobalt Strike, SeDll JavaScript loader, and MockDll dll loader for its attacks. The actor delivers malicious payloads through emailed attachments and URLs, often using fraudulent domains and stolen branding. Leviathan exploits vulnerabilities like CVE-2017-0199 and CVE-2017-8759, and employs techniques like lateral movement through compromised organizations. The threat actor has been observed targeting maritime and defense interests, with a focus on naval and maritime defense. The most recent activities were detected in September 2017, targeting a US shipbuilding company and a US university research center. Leviathan's tools and techniques are continuously evolving, making it a persistent and sophisticated threat actor in the cybersecurity landscape.





Report 6

Summary:

Malaysia has issued a warning about a Chinese hacking campaign targeting government projects. The threat actor, identified as Leviathan, APT 40, TEMP.Periscope, has been using novel tools and techniques to infiltrate government systems. The victims targeted are in the government sector in Malaysia. The threat actor's capabilities include sophisticated cyber espionage tactics. The operation time window for this campaign is not specified in the report. The report provides evidence of the threat actor's advanced capabilities and their focus on government projects in Malaysia.





Report 7

Summary:
- Threat actor: GADOLINIUM, also known as APT 40, TEMP.Periscope
- Region: Worldwide focus, with recent expansion to Asia Pacific region
- Operating sector: Initially focused on maritime and health industries, expanded to higher education and regional government organizations
- Type of company: Not specified
- Evidence of capability: Nation-state activity group compromising targets for nearly a decade, evolving attack techniques, use of cloud services and open-source tools, custom-crafted malware families, and modification of toolchain to use open-source toolkits
- Novelty of tools and techniques: Use of cloud services for delivery of attacks, hosting commands on GitHub, embedding commands in TechNet profiles, use of malicious Access database files, utilization of Outlook tasks for command and control, and modification of PowerShell Empire toolkit
- Operation time window: Attacks observed from 2016 to 2020
- Date of report: Published on June 14, 2024

Overall, the threat actor GADOLINIUM has demonstrated a high level of sophistication and adaptability in their attack techniques, utilizing cloud services and open-source tools to enhance their capabilities. Their recent expansion into new sectors and regions indicates a growing threat landscape that requires continuous monitoring and proactive defense measures.





Report 8

Summary:
- Threat actor: Suspected Chinese Cyber Espionage Group TEMP.Periscope, also known as Leviathan and APT 40.
- Region: United States, Europe, Hong Kong.
- Operating sector: Engineering and Maritime Industries.
- Type of company targeted: Research institutes, academic organizations, private firms.
- Evidence of capability: Active since at least 2013, targeting maritime-related targets across various verticals.
- Novelty of tools and techniques: Leveraged a large library of malware, including AIRBREAK, BADFLICK, PHOTO, HOMEFRY, LUNCHMONEY, MURKYTOP, China Chopper.
- Operation time window: Ongoing wave of intrusions since early 2018, with a sharp escalation detected since summer 2017.
- TTPs: Spear phishing, use of compromised email accounts, lure documents, stolen code signing certificates, use of bitsadmin.exe and PowerShell, leveraging WMI for persistence.
- Implications: Targeting sectors for economic advantage, research and development data, intellectual property.
- Date: First reported on March 16, 2018.





Report 9

Summary:
The report focuses on the Hainan Xiandun Technology Development Company in Hainan Province, China, and its connection to APT activity. The company, along with several others in the region, is described as a front for offensive hacking skills recruitment, despite claiming to focus on information security and cyber defense. Job adverts for penetration testers and English translators reveal overlapping contact details and office locations among these companies. The report highlights the novelty of these companies' recruitment for offensive cyber skills, such as Windows Trojan shellcode development and PE encryption, suggesting a link to APT activity. The evidence presented points to these companies being fronts for APT operations, similar to other known APT groups in China. The report was published on January 9, 2020, and provides insights into the interconnected network of technology companies in Hainan involved in potential cyber threats.





Report 10

The report identifies Gu Jian, a former member of the PLA and academic specializing in Information Security at Hainan University, as the contact person for Hainan Xiandun, a front company for APT activity. The report reveals close associations between Hainan front companies and the academic world, with job adverts posted on university websites. Gu Jian is involved in organizing the Hainan Network Information Security Technology Competition, seeking new ways of password cracking beyond common techniques. The report highlights Mr. Gu's inexplicable wealth and offers of large sums of money for innovative password cracking skills. The Dean of Mr. Gu's faculty, Huang Mengxing, is also mentioned, raising questions about his knowledge of the department's support for APT activity. The report provides evidence of the threat actor's capability in developing novel techniques for cyber attacks and targeting academic institutions in the Hainan region. The operation time window is indicated as starting in September 2013 and continuing in 2016.


