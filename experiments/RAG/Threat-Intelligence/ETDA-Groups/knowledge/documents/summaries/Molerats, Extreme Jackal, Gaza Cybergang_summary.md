
Report 1

Summary: The threat actor known as "Molerats, Extreme Jackal, Gaza Cybergang" has been suspected of launching new attacks in the Middle East. The report does not specify the region or operating sector of the victims targeted. The threat actor's capability is evidenced by their use of novel tools and techniques. The report does not provide a specific date or operation time window for the attacks. The source link provided seems to be malfunctioning, leading to a lack of detailed information. Therefore, the report is considered as a "Malformed report".





Report 2

Malformed report





Report 3

Summary:
- Threat actor identified as DustySky, linked to Gaza Cybergang, targeted government interests in the region.
- Used Downeks downloader to infect victims with Quasar RAT, focusing on hiding the tool and using decoy documents.
- Quasar RAT samples observed in attacks on government targets in the Middle East.
- Quasar RAT is an open-source .NET-based RAT with customizations and vulnerabilities.
- Downeks used for basic capabilities like downloading, executing files, screen capture, persistence, and AV check.
- Downeks communicated with C2 servers using HTTP POST requests.
- Static encryption keys found in Downeks code.
- Palo Alto Networks protected customers from Downeks and Quasar RAT samples.
- Indicators of Compromise (IoCs) include C2 domains and SHA256 hashes of Quasar and Downeks samples.
- Report dated January 30, 2017, by Unit 42 from Palo Alto Networks.





Report 4

Summary:
The threat actor known as Gaza Cybergang, consisting of sub-groups like Molerats, has been targeting Palestinian entities and Israel since at least 2012, focusing on intelligence collection and espionage. They have upgraded their malware arsenal with a backdoor called Pierogi++, first used in 2022 and seen throughout 2023. The threat actor has shown consistent targeting of Palestinian entities, with no significant changes observed since the start of the Israel-Hamas war. The use of novel tools and techniques, such as the Pierogi++ backdoor, indicates the threat actor's continuous evolution and consolidation process. The threat actor's activities suggest ties with other groups like WIRTE, showcasing the intertwined nature of the Gaza Cybergang cluster. The threat actor's capabilities and persistence underscore the need for sustained vigilance and collaborative efforts to address the challenges posed by them. (Date: December 14, 2023)





Report 5

Summary:
The Gaza Cybergang, operating since 2012 in the MENA region, targets government entities, oil and gas, media, activists, politicians, and diplomats. In 2017, they were found infiltrating an oil and gas organization for over a year. They used the CVE 2017-0199 vulnerability and Microsoft Access files with macros to reduce detection rates. Mobile malware traces were also detected. The group has evolved from using RATs to more sophisticated techniques, like exploiting vulnerabilities for remote code execution. They have been active in social engineering attacks related to political events. Kaspersky Lab products successfully detect and block their attacks. The group is expected to intensify attacks in the future. Customers of Kaspersky Intelligence Reporting Service can access more information.





Report 6

Summary:
The threat actor known as Gaza cybergang is a politically motivated Arabic cybercriminal group operating in the MENA region, targeting countries like Egypt, United Arab Emirates, and Yemen since 2012, with increased activity in Q2 2015. They have been observed sending malware files to IT and IR staff, leveraging their access and permissions within organizations. The group primarily uses common RATs like XtremeRAT and PoisonIvy for infections. They show interest in government entities, especially embassies, and use specialized file names and domains for social engineering. The Gaza cybergang's novel approach includes targeting IT and IR personnel, as evidenced by recent malware file names. The group's operations include names like DownExecute and MoleRATs. Kaspersky Lab products successfully detect and block attacks by this threat actor. The report provides detailed information on file names, phishing attempts, IP addresses, domain names, malware hashes, and additional references related to Gaza cybergang's activities.





Report 7

The threat actor known as Molerats, Extreme Jackal, Gaza Cybergang has been active since at least 2012 and recently used a legitimate tool to shield their backdoor from analysis attempts. The backdoor, referred to as Spark and EnigmaSpark, was deployed in a phishing campaign by the MoleRATs group, a low-budget division of the Gaza Cybergang. The threat actor used evasion tactics to hide signs of compromise, including using the Enigma Protector software and a fake host header in the HTTP POST request. The operation targeted Arabic speakers interested in Palestine's potential acceptance of the peace plan, indicating a politically-motivated attack. The threat actor has been deploying variants of the backdoor since March 2017, with at least 15 command and control domains identified. The hackers used novel techniques such as protecting the macro with a password, applying base64 encoding scheme on the backdoor, and packing the malware binary with Enigma Protector. The Spark backdoor has been previously documented by researchers from various cybersecurity companies, attributing it to the MoleRATs group. The threat actor's capability includes collecting information about the victim host, encrypting and sending data to attackers, downloading other payloads, logging keystrokes, recording audio, and executing commands on infected machines. The Spark backdoor was detailed in technical analyses by various cybersecurity companies, highlighting the threat actor's use of custom tools alongside publicly available malware.





Report 8

Summary:
- Threat actor identified as Molerats APT targeted Middle East users, specifically critical members of the banking sector in Palestine, political parties, human rights activists, and journalists in Turkey.
- Campaign active since July 2021, with a switch in distribution method in December 2021.
- Tools and techniques used include macro-based MS Office files, .NET backdoor, ConfuserEx and Themida packers, Dropbox API for C2 communication, RAR files for backdoor delivery, and legitimate cloud hosting services like Google Drive.
- Evidence of threat actor capability includes domain SSL certificate overlap, passive DNS resolution overlap, and use of open-source and commercial packers.
- Novelty in tools and techniques includes the use of Dropbox API for C2 communication and data exfiltration.
- Operation time window from July 2021 to December 2021.
- Victims targeted in the banking sector in Palestine, political parties, human rights activists, and journalists in Turkey.
- Report includes technical analysis of the attack chain, C2 infrastructure, threat attribution, and data exfiltration.
- Multiple samples related to Spark backdoor discovered, with associated IOCs.
- Malware detection by Zscaler Sandbox for macro-based documents, PowerPoint files, and payloads.
- MITRE ATT&CK TTP mapping provided for the attack.
- Indicators of compromise include hashes, download URLs, associated IPs and domains, and file system artifacts.
- Report concludes with a thank you message and links to more Zscaler blogs.





Report 9

The threat actor, known as Molerats, Extreme Jackal, or Gaza Cybergang, has been active since 2012, primarily targeting the MENA region with a focus on government entities, oil and gas, media, activists, politicians, and diplomats. The group is believed to be sponsored by Hamas and is motivated by information theft and espionage. They have targeted various sectors including aerospace, defense, embassies, energy, financial, government, high-tech, media, oil and gas, telecommunications, journalists, and software developers across multiple countries. The threat actor has been observed using a wide range of tools and techniques, including malware such as Poison Ivy, QuasarRAT, and XtremeRAT. Notably, they have been linked to operations such as "Molerats," "DustySky," "TopHat," and "SneakyPastes," with new campaigns emerging periodically, such as "Spark," "Pierogi," and "Ugg Boots 4 Sale." The group has shown a capability for continuous attacks and adaptation, utilizing novel methods like MS Access Macros, CVE 2017-0199, and mobile espionage. Counter operations have been reported by various cybersecurity firms, highlighting the ongoing threat posed by this sophisticated threat actor.





Report 10

Summary:
The threat actor known as Molerats, Extreme Jackal, or Gaza Cybergang conducted a politically motivated APT campaign in the Middle East targeting victims in the region. The campaign used new malware variants, including SharpStage, DropBook, and MoleNet Downloader, to conduct espionage activities. The threat actor utilized phishing documents related to political events in the Middle East, specifically focusing on the normalization process between Israel and its Arab neighbors. The malware variants exhibited advanced capabilities such as backdoor functionalities, language-based execution checks, and communication with legitimate cloud platforms like Dropbox, Google Drive, Facebook, and Simplenote for command-and-control purposes. The threat actor's use of novel techniques, including communication through social media platforms for C2 instructions, demonstrated a high level of sophistication and evasion tactics. The campaign was reported in December 2020, indicating ongoing activity and development by the threat actor. The report also highlighted the potential for increased abuse of legitimate platforms by threat actors to blend in and evade detection. The evidence of the threat actor's capability and the novelty of the tools and techniques used suggest a persistent and evolving threat in the region.





Report 11

Moonlight is a threat actor targeting entities in the Middle East, particularly those related to Middle Eastern political issues, with a focus on espionage. The threat actor, identified as Moonlight, has deployed over 200 samples of malware over the last two years, using novel tactics and tools. The victims of Moonlight's attacks are primarily from the Middle East, with one notable victim being a Palestinian news organization. The threat actor uses social engineering tactics, such as sending emails with malicious attachments disguised as legitimate files, to compromise machines. Moonlight's infrastructure is simple, with dynamic domains controlled via home internet connections in the West Bank of Palestine. The threat actor deploys obfuscated versions of the H-Worm malware and njRat to gain access to victim machines. Moonlight's attacks have evolved from non-targeted to targeted, focusing on specific groups or individuals. The threat actor's aims appear to be politically motivated, with potential consequences that could lead to loss of life. Moonlight's strategy of obfuscating well-known malware has been successful at evading host-based security mechanisms. The tools and techniques used by Moonlight are typical of low-skilled but determined attackers in the Middle East. The threat actor's command-and-control infrastructure is linked to home networks in the Gaza Strip. The attackers demonstrate low operational security, and their identities remain undisclosed. The attacks by Moonlight serve as an example of the types of attacks that often go unnoticed due to their low technical sophistication. The report was published on October 26, 2016, by the Vectra AI Security Research team.





Report 12

Summary:
The report details a cyber espionage campaign targeting Palestinians, specifically the Spark Campaign, attributed to the threat actor MoleRATs (aka Gaza Cybergang). The campaign uses social engineering to infect victims with the Spark backdoor, with lure content related to geopolitical events in the Middle East. The threat actor demonstrates capability in evading detection by packing malware with Enigma Packer, checking for Arabic language settings, and using legitimate storage platforms like Dropbox for delivery. The Spark backdoor allows for data collection, keystroke logging, and C2 communication over HTTP. The report highlights similarities to previous attacks by MoleRATs and the use of specific names for C2 communication. The campaign targets Palestinian individuals and entities, likely related to the Palestinian government. The report provides indicators of compromise and MITRE ATT&CK breakdown. The operation time window is ongoing, with the report published on Cybereason's blog.





Report 13

Summary:
The threat actor known as TA402, also referred to as Molerats, Extreme Jackal, and Gaza Cybergang, has been targeting government institutions in the Middle East, particularly those involved in the ongoing conflict in the Gaza Strip. The threat actor uses custom malware called LastConn, which exhibits unique features to evade automated threat analysis and hinder manual analysis. TA402 leverages geopolitical themes to entice users to open malicious attachments or click on links, with a focus on entities in the Middle East region. The threat actor has been active since at least 2011 and is believed to be based in the Middle East, targeting various industry verticals including technology, telecommunications, financial institutions, and government offices. TA402's malware distribution tactics include spear-phishing emails with password-protected archives and Google Apps Script URLs. The threat actor's malware, LastConn, is actively developed and maintained, utilizing Dropbox for command and control capabilities. TA402's recent campaigns in early 2021 were temporarily disrupted, possibly due to regional tensions or religious holidays, but resumed in June 2021 with continued use of LastConn. Proofpoint recommends vigilance when handling password-protected archives and provides indicators of compromise for detection. The threat actor is expected to continue developing customized malware implants to evade detection and automated analysis.





Report 14

Summary:
The Gaza cybergang, a threat actor specializing in cyberespionage, has been targeting politicians, diplomats, journalists, activists, and politically active citizens in the Middle East and central Asia. The group, known for its SneakyPastes campaign, uses phishing emails with links to malware or infected attachments to initiate attacks. The campaign is multistage, with the final stage involving the deployment of RAT malware capable of downloading/uploading files, launching applications, and encrypting information. The threat actor utilizes public services for communication and malware delivery, making detection challenging. The group's tools and techniques, while relatively simple, demonstrate a high level of sophistication in their operations. The report was published on April 10, 2019, following the Kaspersky Security Analyst Summit (SAS) in Singapore. The victims targeted by the Gaza cybergang include those in the Palestinian territories, Jordan, Israel, and Lebanon. The group's activities pose a significant threat to organizations in various sectors, including government, media, and activism.





Report 15

Summary:

TA402, also known as Molerats, Extreme Jackal, and Gaza Cybergang, targeted Middle East-based government entities from July to October 2023 using a new initial access downloader called IronWind. The threat actor utilized complex infection chains, including Dropbox links, XLL, and RAR file attachments, to deliver multifunctional malware. TA402 focused on less than five organizations per campaign and maintained a strong interest in government entities in the Middle East and North Africa. The threat actor has been tracked since 2020 and is assessed to be a Middle Eastern APT group operating in the interests of the Palestinian Territories. TA402's use of geofencing techniques and decoy documents makes detection challenging. The threat actor's ongoing innovation and persistence in cyber espionage activities suggest a continued threat to targeted entities. 

Date: November 14, 2023

Region: Middle East

Operating Sector: Government Entities

Type of Company: N/A

Novelty of Tools and Techniques: TA402 used a new initial access downloader, IronWind, and adjusted delivery methods to evade detection efforts. The threat actor employed geofencing techniques and consistently updated its malware to support cyber espionage activities. 

Malformed report.





Report 16

Summary:
The TopHat Campaign, attributed to threat actors Molerats, Extreme Jackal, and Gaza Cybergang, targeted individuals or organizations within the Palestinian Territories using Arabic language decoy documents related to current events. The attacks leveraged popular third-party services like Google+, Pastebin, and bit.ly to deliver a new malware family named "Scote" that provides backdoor access. The attackers used novel techniques such as loading shellcode from a BMP file, exploiting CVE-2017-0199, and using self-extracting executables. The malware communicated with Pastebin and Google+ profiles for command and control, with evidence of testing against security products. The campaign showed overlaps with the DustySky campaign targeting the Middle East region. The threat actor demonstrated a lack of sophistication in some coding practices. The campaign began in early September 2017 and was reported on January 26, 2018. The victims were primarily located in the Palestinian Territories and the United Arab Emirates. Palo Alto Networks customers were protected through various measures. The threat actor's activities are being monitored for further developments.





Report 17

Summary:

- Threat actor: TA402, also known as Molerats, Extreme Jackal, Gaza Cybergang
- Region: Middle East, specifically targeting organizations in the Palestinian Territories
- Operating sector: Middle Eastern governments, foreign policy think tanks, state-affiliated airline
- Date: Late 2021 to January 2022
- Evidence of capability: TA402 used a new implant called NimbleMamba, likely replacing LastConn, with complex attack chains involving geofencing and URL redirects to bypass detection
- Novelty of tools and techniques: NimbleMamba is actively developed, well-maintained, and designed for highly targeted intelligence collection campaigns, using guardrails to ensure execution on targeted machines and utilizing Dropbox API for C2 communication
- TA402 halted activities post-publication of previous research, likely to retool and update implants and delivery mechanisms
- TA402's persistence and ability to modify attack chains based on intelligence targets indicate ongoing threat
- TA402 likely operates in support of Palestinian objectives, targeting Arabic speakers in the Middle East
- TA402's campaigns mimic historical patterns and demonstrate continued effectiveness in the region

Overall, TA402 remains a persistent and evolving threat actor with a focus on highly targeted campaigns in the Middle East, utilizing advanced tools and techniques to evade detection and gather intelligence.


