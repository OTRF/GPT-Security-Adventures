
Report 1

Malformed report





Report 2

Summary:
The APT trends report for Q1 2021 by Kaspersky highlights significant findings related to threat actors such as SolarWinds, HAFNIUM, and Kimsuky. The report discusses the overlap between the Sunburst backdoor and Kazuar, as well as the exploitation of Microsoft Exchange zero-day vulnerabilities by multiple actors. A campaign targeting governmental entities in Russia using Exchange zero-day exploits was also discovered. Additionally, the report covers activities of threat actors in Europe, Russian-speaking regions, China, the Middle East, and Southeast Asia. Novel tools and techniques, such as the use of a new method by Kimsuky to deliver malware, were identified. The report emphasizes the evolving tactics of threat actors and the need for continuous monitoring and analysis to detect sophisticated attacks.





Report 3

Malformed report.





Report 4

Summary:
- Threat actor: Kimsuky, Velvet Chollima
- Region: Focused on U.S. national think tanks, expanded to cryptocurrency industry
- Operating sector: Think tanks, cryptocurrency industry
- Date: Attacks continued through March and April 2019
- Evidence of capability: BabyShark malware used for espionage and financial gain, secondary payloads KimJongRAT and PCRat used as "Cowboys"
- Novel tools and techniques: Denylisted IP addresses, multi-stage infection chain, remote administration commands, Cowboy Converter tool for encoding payloads
- Malware capabilities: BabyShark steals email and login credentials, exfiltrates data to C2 server
- Exploited vulnerability: CVE-2018-8174 used for loading malware via malicious URLs
- Protection measures: Palo Alto Networks provides detection and prevention for mentioned malware families and exploits
- Indicators of Compromise: Malicious Word Macro Document, PCRat, KimJongRAT, Cowboy Loader, Cowboy Converter
- Conclusion: Threat actor likely to continue attacks, expanding into new industries; shared intelligence with Cyber Threat Alliance members.





Report 5

Summary:
The threat actor known as Kimsuky, also referred to as Velvet Chollima, has been active since at least 2012 and is believed to operate on behalf of the North Korean regime. They have targeted various sectors including pharmaceutical/research companies, government institutions, human rights groups, and think tanks in countries like the United States, Russia, and Europe. Evidence shows that Kimsuky has developed a new modular spyware suite called KGH_SPY and a stealthy malware called CSPY Downloader, both previously undocumented. The threat actor has employed anti-forensics techniques, backdating creation timestamps, and using sophisticated evasion capabilities. The tools and techniques used by Kimsuky show a high level of sophistication and novelty, with some payloads remaining undetected by antivirus vendors. The infrastructure overlaps with previously identified Kimsuky malware, indicating a consistent pattern of behavior. The threat actor has targeted organizations related to human rights violations, although the full extent of their victims remains unclear. The report provides detailed analysis of the tools, infrastructure, and tactics used by Kimsuky, highlighting their advanced capabilities and ongoing cyber espionage operations.





Report 6

Summary: ASEC discovered a CHM malware assumed to be created by the Kimsuky group, targeting victims through email attachments disguised as North Korea-related questionnaires. The malware exfiltrates user information and uses novel techniques like encoding commands and keylogging. The threat actor distributes the malware persistently through PowerShell scripts and phishing emails, with evidence of similar attacks in the past. Victims targeted include those in the operating sector of human rights activists and defectors. The threat actor's capability is demonstrated through the use of advanced tools and techniques, posing a significant risk to targeted entities. (Date: March 13, 2023)





Report 7

Summary:
The threat actor Kimsuky group was confirmed to distribute xRAT (Quasar RAT) malware on January 26, 2022. The attacker used a variant of Gold Dragon on the first infected PC on January 24, with evidence including process hollowing and termination of security software. The attacker distributed Gold Dragon through an exclusive installer and also installed xRAT (cp1093.exe) for remote control and info-stealing features. Novel techniques included process hollowing and distributing an uninstaller to delete traces of the attack. The threat actor's capability was demonstrated through modularized info-leaking features and constant monitoring by AhnLab. The victims targeted were not specified in the report.





Report 8

Summary:
The threat actor known as ARCHIPELAGO, linked to North Korea, has been targeting individuals with expertise in North Korea policy issues such as sanctions, human rights, and non-proliferation. The victims include government and military personnel, think tanks, policy makers, academics, and researchers in South Korea, the US, and elsewhere. ARCHIPELAGO employs sophisticated phishing tactics, such as posing as media outlets or think tanks to lure targets into clicking on malicious links that lead to credential harvesting pages. They have also used novel techniques like encoding malware payloads in Google Drive file names and delivering malware via ISO files. Additionally, ARCHIPELAGO has utilized malicious Chrome extensions to steal usernames, passwords, and browser cookies. Google's Threat Analysis Group has been actively monitoring and disrupting ARCHIPELAGO's activities to protect users and improve the security of Google's products. The report was published on April 5, 2023.





Report 9

Summary:
The North Korean APT group Kimsuky has evolved its tactics by splitting into two subgroups: CloudDragon and KimDragon. Operating since 2012, they primarily target South Korea, Japan, and the US using social engineering, spear-phishing, and watering hole attacks. CloudDragon targets a broader geographical footprint, including Japan and EU countries, while KimDragon focuses on India. They use different malware tools like TroiBomb, RoastMe, and Lovexxx. CloudDragon has adopted supply chain attacks and cross-platform attacks, targeting industries like financial institutions and aerospace. They have also developed new phishing techniques like ProxyMirror to mimic legitimate websites. The group has expanded its attacks to mobile devices, indicating an evolution in their capabilities. The report was published on May 7, 2021, by Dark Reading.





Report 10

Summary:
The threat actor Kimsuky, also known as Velvet Chollima, is a state-sponsored group originating from North Korea. They have been actively engaged in cyber-espionage campaigns since 2012, targeting various sectors such as defense, education, energy, government, healthcare, manufacturing, and think tanks in countries like Japan, South Korea, Thailand, the USA, and Europe. Kimsuky has been observed using a wide range of tools and techniques, including malware like BabyShark, Gh0st RAT, and xRAT, as well as social engineering tactics to target high-profile individuals and organizations. The group has been linked to multiple operations such as "Baby Coin," "Stolen Pencil," "Mystery Baby," and "Covert Stalker," showcasing their evolving capabilities and persistence in conducting information theft and espionage activities. Counter operations have been undertaken by entities like Microsoft and the US Treasury to combat Kimsuky's illicit cyber activities.





Report 11

Summary:
The threat actor "Kimsuky APT," also known as Thallium, Black Banshee, and Velvet Chollima, is a North Korean group targeting South Korean government entities since 2012. They conduct cyber espionage operations using the AppleSeed backdoor. The group has targeted high-profile individuals within the South Korean government, including the Ministry of Foreign Affairs and Trade counselor. Additionally, they have collected information on universities and companies in South Korea. Kimsuky sets up phishing infrastructure to mimic popular websites and uses spearphishing emails to collect email addresses. They have developed novel phishing techniques to target victims in both English and Korean. The threat actor reuses phishing infrastructure for command and control communications, including using the AppleSeed backdoor for Windows and Android users. The AppleSeed backdoor is highly obfuscated and uses custom encryption algorithms for strings and API calls. Kimsuky's recent campaign targeted the Ministry of Foreign Affairs of South Korea. The group's activities align with previously reported tactics and techniques. The report includes detailed analysis of the AppleSeed backdoor's functionalities and MITRE ATT&CK techniques used by the threat actor. The operation was active as of June 1, 2021.





Report 12

Summary: The threat actor Kimsuky, also known as Velvet Chollima, has been distributing CHM malware under various subjects, as reported by ASEC on June 21, 2023. The threat actor has shifted from using document files to CHM files for malware distribution, targeting victims with subjects like cryptocurrency, tax accounting, and contracts. The CHM malware generates a normal help window upon execution, making it difficult for users to detect malicious behavior. The threat actor uses personalized topics to deceive users, such as tax investigation return forms and financial transaction data. The malware's operation process involves downloading additional scripts to exfiltrate user information and download more malicious files. The threat actor has been increasing malware distribution targeting specific users using personal information, with a focus on CHM files in APT attacks. The report provides detailed information on the operation process, malicious scripts, and exfiltrated information, highlighting the threat actor's capabilities and novel techniques.





Report 13

Summary:
The threat actor Kimsuky, a North Korean state-sponsored APT group, has been observed conducting ongoing attacks globally, targeting organizations in Asia, North America, and Europe. They have evolved their reconnaissance capabilities with a new malware component called ReconShark, delivered through spear-phishing emails and malicious macros. Recent campaigns have targeted organizations like Korea Risk Group (KRG) and individuals in the United States, Europe, and Asia. ReconShark exfiltrates valuable information about the infected platform without storing it on the filesystem, deploying further payloads in a multi-stage manner. The infrastructure analysis reveals the use of shared hosting servers and specific domains for command and control. The evolving nature of Kimsuky's tactics underscores the need for vigilance and collaboration to protect against such attacks. The report was published on May 4, 2023, by SentinelOne.





Report 14

Summary: The threat actor known as Kimsuky, supported by North Korea, has been active since 2013, targeting various sectors including national defense, defense industries, the press, diplomatic sector, national organizations, and academic fields. They primarily use spear phishing attacks to gain initial access, with recent attacks involving LNK shortcut-type malware distributed through compressed files. The threat actor installs remote control malware like XRat, Amadey, and RftRAT to control infected systems and steal information. Recent attacks have shown the use of AutoIt to create malware, specifically Amadey and RftRAT. The group also deploys keyloggers, Infostealers, and tools like Mimikatz and RDP Wrapper for information theft. The threat actor continuously evolves their tactics to bypass security products and exfiltrate data from infected systems. The report was published on December 8, 2023, by ASEC.





Report 15

Summary:
The threat actor Kimsuky, supported by North Korea, has been targeting web servers since 2013, expanding their attacks beyond South Korea since 2017. They recently attacked a Korean construction company's Windows IIS web server, exploiting vulnerabilities and using social engineering tactics. Kimsuky installed the Metasploit Meterpreter backdoor malware and a proxy malware developed in GoLang. The use of Meterpreter, an open-source tool, showcases the threat actor's capabilities, with novel techniques like developing malware in GoLang to evade detection. The attack aimed to gain control over the web server, emphasizing the importance of patching servers and using protection software to prevent exploitation. The malware used in the attack includes Meterpreter and proxy malware, with specific indicators of compromise provided for detection. The attack highlights the ongoing threat posed by Kimsuky and the need for proactive cybersecurity measures.





Report 16

The Kimsuky group, known as Velvet Chollima, targeted North Korea-related personnel through phishing attacks, creating a fake webmail website resembling national policy research institutes. The threat actor used tactics like autocompleting IDs of trade, media, and North Korea-related individuals to obtain account credentials. The group's capability was evidenced by the use of reverse DNS data-related IP/domain addresses and relevant files. The novelty of the attack lies in the increasing use of web sources of well-known websites and impersonation of portal websites and organizations' webmail infrastructures. Users were advised to verify URLs and certificates before logging in. The report was posted on May 22, 2023, by AhnLab Security Emergency Response Center (ASEC).





Report 17

Summary:
- Threat actor: Kimsuky, Velvet Chollima
- Region: North Korea
- Operating sector: Non-government sector, experts in North Korean affairs
- Type of company: Subscription-based news and analysis service focusing on North Korea
- Date: June 6, 2023
- Evidence of capability: Kimsuky engaged in a social engineering campaign targeting experts in North Korean affairs, stealing Google and subscription credentials, and delivering reconnaissance malware. They used spoofed URLs, websites imitating legitimate platforms, and Office documents weaponized with ReconShark malware.
- Novelty of tools and techniques: Kimsuky's focus on establishing rapport with targets before initiating malicious activities, impersonating legitimate entities like NK News, and using personalized phishing tactics to capture credentials demonstrate their evolving social engineering tactics. Their use of ReconShark malware and password-protected documents for precision attacks showcases their advanced capabilities.
- Overall, Kimsuky's activities highlight their dedication to social engineering and strategic intelligence gathering, emphasizing the need for increased awareness and security measures to mitigate risks posed by this persistent threat actor.





Report 18

Kimsuky, a threat actor, targeted South Korean research institutes with a fake import declaration disguised as a malicious JSE file. The threat actor used a backdoor to steal information and execute commands. The attack involved obfuscated PowerShell scripts, Base64-encoded backdoor files, and legitimate PDF files to avoid detection. The backdoor was created in the %ProgramData% path and used rundll32.exe for execution. The threat actor exfiltrated system information using commands like wmic and ipconfig. Novel techniques included encoding command execution results and using the curl tool to upload information to a C2 server. The attack targeted specific victims, emphasizing the need to avoid running attachments from unknown sources. The operation was detected on November 30, 2023.





Report 19

Summary: The Kimsuky threat group, supported by North Korea, has been active since 2013, targeting various sectors including national defense, diplomatic, academic, defense, media industries, and national organizations. They use spear phishing attacks to exfiltrate internal information and technology from their targets. The group installs backdoors and Infostealers to control infected systems. They utilize open-source malware like xRAT and legitimate tools like Remote Desktop Protocol (RDP) for remote control. Recently, they have been using new malware called "RevClient" to receive commands from a C&C server. The threat actor continuously updates their malware, such as BabyShark, and installs additional payloads like injectors and RDP-related malware. The Kimsuky group's tactics involve changing RDP services, adding user accounts, and enabling multiple sessions to control infected systems. Their use of novel tools and techniques, along with continuous updates to their malware, demonstrates their evolving capabilities. The report was posted on October 17, 2023, by AhnLab.





Report 20

Summary:
The Kimsuky threat group, supported by North Korea, has been active since 2013, targeting South Korean research institutes, energy corporations, and other countries. They use AppleSeed malware and remote control tools like Meterpreter and VNC for system control. Recently, they have been using Chrome Remote Desktop for remote control. The threat actor installs various malware like Infostealers, RDP Patcher, and Ngrok to maintain control over infected systems. They also use a batch file to execute Chrome Remote Desktop host installer for remote control. The group employs spear-phishing attacks with disguised document files to distribute malware. The report provides detailed information on the malware used, including IOCs and behavior detections. The threat actor's capability is evidenced by their use of novel tools and techniques like Chrome Remote Desktop for remote control. The report was posted on July 7, 2023, by ASEC.





Report 21

Summary:
- Threat actor: Kimsuky, a North Korean APT group.
- Targeted victims: North Korea-focused information services, human rights activists, and DPRK-defector support organizations.
- Operating sector: Information services and human rights advocacy.
- Novelty of tools and techniques: Kimsuky uses a variant of the RandomQuery malware for file reconnaissance and information exfiltration, distributed through CHM files. They strategically employ new TLDs and domain names to deceive targets.
- Date: Campaign ongoing as of May 23, 2023.
- Evidence of capability: Kimsuky's consistent distribution of custom malware for reconnaissance operations and use of less common TLDs for infrastructure indicate advanced capabilities in targeted attacks.





Report 22

Summary:
The threat actor known as Kimsuky, also referred to as Thallium, Black Banshee, and Velvet Chollima, is a prolific and active threat actor primarily targeting Korea-related entities. In early 2022, they targeted the media and a think-tank in South Korea with spear-phishing emails containing macro-embedded Word documents. The actor utilized HTML Application files and Visual Basic Scripts to infect victims and deliver payloads. They operated multi-stage command and control servers with various commercial hosting services globally. The threat actor employed victim verification methodology in their C2 servers to ensure the incoming requests were from the intended victims. The targets of this operation are likely individuals related to politics, diplomacy, journalism, and academia. The threat actor used various domains and IPs for hosting malicious documents and C2 operations. The actor's novel techniques include using legitimate blog services and unique user-agent strings to evade detection. The report provides indicators of compromise and insights into the threat actor's tactics, techniques, and procedures. The operation time window was reported on August 25, 2022.





Report 23

Summary:
- Threat actor identified as Kimsuky distributed malware in the form of a batch file disguised as document viewers.
- Malware accessed Google Drive and Docs to execute document files related to military or unification.
- Threat actor utilized commands to identify anti-malware processes and download scripts based on the process type.
- Novelty in the threat actor's technique included replacing default document templates and modifying browser and email-related shortcut files.
- Threat actor targeted users with Kaspersky, Avast, and Ahnlab anti-malware processes.
- Malicious activities included downloading and executing scripts, with potential for additional unidentified activities.
- Date of identification: July 11, 2023.
- Victims targeted were users with specific anti-malware processes.
- Threat actor's capability demonstrated through sophisticated script execution and evasion techniques.
- Region: Korea, Operating Sector: Not specified, Type of Company: Not specified.





Report 24

Summary: The threat actor known as Kimsuky, Velvet Chollima has been identified distributing malware disguised as HWP document files. The malware, previously distributed in CHM and OneNote formats, is suspected to be created by the same threat group. The malware is distributed as a compressed file containing an executable disguised as an HWP document file extension. The executable contains a PowerShell command encoded in Base64, leading to keylogging and user credential leakage. The threat actor utilizes obfuscated commands and scripts to perform malicious activities, including transmitting data to specific URLs. The threat actor's capability to disguise malware and use novel techniques like PowerShell keyloggers indicates advanced capabilities. The report warns users to exercise caution when opening email attachments and executing files from unknown sources. The operation time window for the threat actor's activities spans from February 2022 to June 2023. The victims targeted by the threat actor are not explicitly mentioned in the report.





Report 25

Summary: The threat actor "Kimsuky, Velvet Chollima" has been distributing malware disguised as normal documents to broadcasting, ordinary companies, and security-related fields in the region. The threat actor utilizes template injection techniques and malicious word macro documents for execution. The malware prompts users to enable content through images and downloads additional malicious scripts. The threat actor leaks sensitive data to C&C servers, modifies system registries, and maintains connections for data exfiltration. The threat actor's capability includes continuous distribution of LockBit 2.0 ransomware disguised as resumes and Qakbot via OneNote. The threat actor's tools and techniques show a novel approach to malware distribution and data exfiltration. The operation time window is indicated by the detection dates of the malware variants.





Report 26

Summary: Kimsuky, also known as Velvet Chollima, a threat actor linked to North Korea, attempted to hack 11 officials of the UN Security Council. The targets were located in various regions, including the United States and Europe. The victims belonged to the government sector, specifically officials working for the UN Security Council. The operation took place in 2024, indicating recent activity by the threat actor. Kimsuky demonstrated advanced capabilities in cyber espionage, highlighting their expertise in targeting high-profile individuals. The use of novel tools and techniques by the threat actor suggests ongoing efforts to enhance their cyber operations.





Report 27

Summary:
The North Korean APT group 'Kimsuky' has been targeting experts on the Korean peninsula through a new spearphishing campaign, as warned by German and South Korean government agencies. The campaign involves infecting Android phones with a malicious app on Google Play and using a malicious Chromium web browser extension to gain access to victims' Google accounts. Kimsuky, also known as TA406 and Thallium, has been active since 2012, focusing on diplomats, NGOs, think tanks, and experts on Korean peninsula-related issues. The threat actor uses highly targeted spearphishing attacks, impersonating portal administrators and acquaintances to gain initial access. The group has the capability to steal emails and data stored in the cloud, posing a significant threat to global intelligence gathering. The novelty of the tools and techniques used by Kimsuky, such as the malicious app on Google Play and the Chromium extension, highlights the group's advanced capabilities. The operation time window for this campaign was reported on March 22nd, 2023.





Report 28

Summary:
On May 14, 2021, North Korean hackers, specifically the Kimsuky cyber-espionage group, breached the South Korean Atomic Energy Research Institute (KAERI) through a VPN server vulnerability. Thirteen different IPs, including one linked to Kimsuky, were identified accessing the organization's internal network. This incident follows a spear-phishing campaign by Kimsuky targeting South Korean government entities and the nuclear security officer for the International Atomic Energy Agency. North Korean cyber-espionage groups have historically shown interest in nuclear energy and arms-related targets. The US Treasury Department previously sanctioned three North Korean hacking groups for stealing funds to support the country's nuclear weapons and missile programs. The incident highlights the ongoing threat posed by North Korean threat actors in the cyber realm.





Report 29

Summary: North Korean threat actors breached Seoul National University Hospital between May and June 2021, stealing sensitive medical information and personal details of 831,000 individuals. The attack was attributed to the Kimsuky hacking group, utilizing seven servers in South Korea and other countries. The police identified the threat actors based on intrusion techniques, IP addresses, website registration details, and language used. The attack resulted in data exposure for patients and hospital employees, prompting the Korean National Police Agency to warn of potential future cyberattacks. North Korean hackers have previously targeted healthcare organizations with ransomware, with the Maui ransomware operation linked to the Andariel subgroup of Lazarus. The operation aimed to extort ransom payments from South Korean entities since April 2021. The police emphasized the importance of enhancing security measures to protect against organized cyberattacks. 

Date: May 10, 2023

Region: South Korea

Operating Sector: Healthcare

Type of Company: Hospital

Capability of Threat Actor: Utilized specific intrusion techniques, IP addresses, and language to breach hospital network and steal sensitive data.

Novelty of Tools and Techniques: Utilized seven servers in South Korea and other countries, linked to previous ransomware operations targeting healthcare organizations.





Report 30

Summary: Kimsuky, also known as Velvet Chollima, a North Korean state-sponsored threat actor, has been targeting retired diplomats and military officials. The victims are primarily located in South Korea and the United States. The threat actor has demonstrated the capability to conduct sophisticated cyber espionage operations, utilizing novel tools and techniques to compromise their targets. The operation time window for these attacks is ongoing, with evidence suggesting a high level of organization and persistence in their activities. The targets belong to the government and defense sectors, indicating a strategic interest in obtaining sensitive information.





Report 31

Summary:
- Threat actor: Kimsuky, Velvet Chollima
- Region: Not specified
- Operating sector: Not specified
- Type of company of victims: Not specified
- Date: March 24, 2023
- ASEC discovered OneNote malware disguised as a compensation form distributed by the threat actor.
- The malware impersonates a research center and uses malicious VBS files.
- The threat actor uses obfuscated commands and URLs to execute additional scripts.
- The malware targets security-related workers with disguised HWP files.
- Kimsuky group has been distributing malware in various forms, including CHM, LNK, and OneNote.
- Users are advised to exercise caution when opening email attachments from the threat actor.





Report 32

Summary:
The threat actor "ITG16," identified as a North Korean government state-sponsored group also known as Kimsuky or Velvet Chollima, has been active since at least 2010 and targets South Korean organizations, including diplomatic, national security personnel, human rights groups, media, utilities, and think tanks. Recent activity includes COVID-19 related phishing campaigns targeting South Korean individuals engaged in international affairs. ITG16 has evolved its tactics over time, moving from generalized phishing campaigns to more focused and stealthy attacks, adapting to stronger network defenses and security awareness training. The threat group has expanded its targets to include financial institutions and cryptocurrency exchanges, possibly reflecting North Korean government priorities to obtain illicit funds. ITG16 is known for using tools like KimJongRAT and BabyShark malware, with capabilities for credential theft and exfiltration of sensitive information. The group's techniques involve spearphishing emails with malicious macros and documents, often containing relevant lure content. ITG16's activities have been detected by third parties, with recent campaigns incorporating COVID-19 themes to target non-Korean speaking users, especially Mac OS users. Microsoft has taken action against ITG16, taking down 50 domains used in phishing campaigns targeting government employees, think tanks, and individuals in the U.S., Japan, and South Korea. The threat actor is expected to continue its operations, leveraging current geopolitical tensions and events like the COVID-19 pandemic to advance North Korean government interests politically and financially. Organizations monitoring the Korean peninsula's geopolitical landscape may predict and mitigate threats from ITG16. The group's predictability offers a small advantage for defense strategies, allowing for proactive measures against potential attacks.





Report 33

Malformed report.





Report 34

Summary:

The threat actor known as "Kimsuky, Velvet Chollima" conducted the STOLEN PENCIL campaign targeting academia, possibly originating from DPRK, since at least May 2018. The victims, primarily academic institutions with expertise in biomedical engineering, were targeted through spear-phishing emails leading to the installation of a malicious Google Chrome extension. The threat actor demonstrated poor OPSEC, using off-the-shelf tools like Remote Desktop Protocol (RDP) for persistence and password harvesting. The threat actor's toolset included tools for password theft, port scanning, and process memory dumping. The threat actor's main goal was to gain access to compromised accounts and systems via stolen credentials, with no evidence of data theft. The campaign's motives remain uncertain. The operation time window for RDP access was daily from 06:00-09:00 UTC. The threat actor's techniques were relatively basic, typical of DPRK tradecraft, with a focus on credential theft and persistence. The campaign utilized phishing domains and malicious Chrome extensions to target victims. The report was published on December 5th, 2018, by NETSCOUT.





Report 35

Summary:
The threat actor "Kimsuky" conducted a cyber-espionage campaign against South Korean think-tanks, targeting organizations such as the Sejong Institute, Korea Institute For Defense Analyses, Ministry of Unification, and Hyundai Merchant Marine. The malware used in the campaign communicated with a Bulgarian e-mail server and had Korean hieroglyphs in its compilation path. The malware had capabilities such as keystroke logging, directory listing collection, HWP document theft, remote control download and execution, and disabling firewalls. The threat actor used a modified TeamViewer client for remote control access. The attackers likely originated from North Korea, as indicated by the registration data and IP addresses used. The campaign was highly targeted and limited, with a focus on specific organizations in South Korea and China. The threat actor's novel techniques included using a web shell named HrServ and exhibiting both APT and crimeware features. The Lazarus group was also involved in a separate campaign exploiting security company products. The report provides detailed insights into the tactics, techniques, and procedures of modern Asian APT groups.





Report 36

Summary:
- Threat actor: SharpTongue, also known as Kimsuky, believed to be North Korean in origin.
- Operating region: Targets individuals in the United States, Europe, and South Korea working on topics related to North Korea, nuclear issues, and weapons systems.
- Operating sector: Individuals working for organizations in strategic interest areas.
- Novelty of tools and techniques: Deployed a malicious browser extension called "SHARPEXT" that directly inspects and exfiltrates data from a victim's webmail account without stealing usernames and passwords.
- Evidence of capability: SharpTongue's toolset is well-documented, but the use of SHARPEXT represents a new and sophisticated approach.
- Operation time window: Ongoing for over a year, with the latest version of SHARPEXT at version 3.0.
- Date of report: July 28, 2022.
- Source: Volexity Threat Research.
- For more detailed information, refer to the original report at https://www.volexity.com/blog/2022/07/28/sharptongue-deploys-clever-mail-stealing-browser-extension-sharpext/.





Report 37

Summary:
- Threat actor: Kimsuky, Velvet Chollima
- Region: South Korea
- Operating sector: Nuclear power industry
- Type of company: Korea Hydro and Nuclear Power (KHNP)
- Date: March 17, 2015
- Evidence of capability: Stole design documents on CANDU reactors, demanded shutdown of three reactors, spread malware through phishing attacks, leaked blueprints of nuclear power plants, threatened to sell data on South Korea's nuclear power reactor program
- Novelty of tools and techniques: Used malware similar to 'kimsuky' malware used by North Korean hackers, spread malware through phishing attacks, traced Internet traffic to network in northeast China near North Korean border.





Report 38

Summary:
The threat actor "Kimsuky, Velvet Chollima" is a North Korean APT group that has been targeting South Korea, with a focus on evolving its Tactics, Techniques, and Procedures (TTPs). The group was first identified by Kaspersky in 2013 and recently detailed by ESTsecurity. They use a shorter attack chain to achieve a low detection rate, starting with a malicious executable file with a ".scr" extension. The malware writes a DLL file named "AutoUpdate.dll" in the system, gaining persistence by setting a registry key. To avoid detection, the malware injects itself into the "explorer.exe" process. The threat actor communicates with a C2 server every 15 minutes, sending information about compromised machines. The group's capability to bypass AV detection and use novel techniques like process injection demonstrates their advanced capabilities. The report was published on March 3, 2020, and provides detailed technical analysis of the threat actor's activities. The victims targeted by this threat actor are not specified in the report.





Report 39

The report details the evolution of the threat actor Kimsuky targeting Android devices with newly discovered mobile malware named FastFire, FastViewer, and FastSpy. The malware is associated with past campaigns attributed to the Kimsuky group, with FastViewer and FastSpy used to attack South Koreans. The FastFire malware is disguised as a Google security plugin, while FastViewer disguises itself as "Hancom Office Viewer" and FastSpy is a remote access tool based on AndroSpy. The report highlights the advanced tactics of the Kimsuky group, including the use of Firebase for C&C communication and customization of AndroSpy. The threat actor's targeting strategy for mobile devices is becoming more sophisticated, necessitating caution against Android device attacks. The report provides detailed technical analysis of the malware's capabilities and infrastructure, linking them to the Kimsuky group's past activities. The report includes IoCs and mobile MITRE ATT&CK references for further investigation. Date: Oct 24, 2022.





Report 40

Summary:
The threat actor "Kimsuky" conducted a hacking operation named "Operation Covert Stalker" targeting individuals and organizations involved in North Korea, politics, diplomacy, and security. The operation involved sending phishing and hacking emails with malware attachments to steal email accounts and important materials. The threat actor exploited vulnerabilities in Windows systems and websites, created RDP accounts for persistence, and used remote control programs like Quasar RAT and TeamViewer. Victims were infected with the BlackBit ransomware, leading to ransom demands. The threat actor used web shells for C2 operations and included North Korean expressions in some malware. The report was based on 17 months of tracking and analysis, with the operation window starting on May 3rd, 2022. The tools and techniques used by the threat actor demonstrated advanced capabilities and persistence in achieving their objectives.





Report 41

Summary:
- Threat actor identified as "Kimsuky, Velvet Chollima" conducted a stealth operation named "Operation Stealth Power" targeting specific individuals in South Korea's diplomatic, security, and unification sectors, as well as North Korean defector organizations.
- The threat actor demonstrated proficiency in Korean language and utilized encrypted HWP malicious code to hack specific Korean web servers for communication.
- The operation involved PowerShel-based keylogging commands to covertly steal internal information.
- The threat actor's use of highly encrypted penetration capabilities and PowerShel-based spy functions led to the operation being named "Operation Stealth Power."
- The attack was attributed to the government-sponsored threat organization known as "Kimsuky," with an increase in cyber threats targeting South Korea.
- Novel techniques included the use of malicious HWP documents with embedded EPS files and the deployment of HTA files through the 'mshta.exe' process for further stages of the attack.
- The threat actor utilized a variety of stages and codes, including PowerShell scripts for keylogging and data exfiltration to a C2 server.
- The attack showed similarities to previous threats associated with the "Kimsuky" group, indicating a pattern of behavior and tactics.
- The threat actor's use of consistent usernames and domains across multiple attacks suggests a coordinated and persistent cyber threat campaign.
- Further analysis and intelligence reports on related threats and indicators of compromise (IoC) are expected to be provided through the "Threat Inside" service.





Report 42

Summary:
The threat actor "Kimsuky, Velvet Chollima" conducted a recent APT attack targeting South Korea, with the operation named "Operation Mystery Baby." The malicious files were created between October 31st, 00:48 KST and 13:15 KST, with different versions for 32-bit and 64-bit systems. The malware disguised itself as a specific Korean security product icon and had Korean language settings. The threat actor group is suspected to be state-sponsored and has been actively involved in cyber espionage operations. The attack combined CVE-2017-11882 vulnerability and spear phishing techniques, targeting South Korean users. The threat actor group has a history of using HWP document file vulnerabilities in their attacks. The tools and techniques used in this attack show similarities to past attacks by the same threat actor group, indicating a consistent evolution in their tactics. The threat actor group remains active and poses a significant risk, requiring enhanced security measures to prevent further damage. Date: October 31, 2018. Region: South Korea. Operating Sector: Not specified. Type of Company: Not specified.


