
Report 1

Malformed report





Report 2

Malformed report





Report 3

Malformed report.





Report 4

Summary:
The threat actor APT28, also known as Sofacy Group or Fancy Bear, is a Russian cyber espionage group linked to the Russian military intelligence agency GRU. They target Aerospace, Defense, Government Agencies, International Organizations, and Media sectors. APT28 has been active since 2008, with a significant increase in attacks between 2018 and 2019. Their evolution in weaponization, delivery, and installation techniques shows a shift towards internal professional resources and self-developing capabilities. They have used sophisticated dropper technology and exploited vulnerabilities in Windows, Adobe Flash, and Oracle technologies. Their installation procedures have evolved from scripting to PowerShell scripting and advanced development techniques. Overall, APT28's skill sets have rapidly advanced in recent years, indicating a significant enhancement in their development, obfuscation, and evasion techniques.

Date: December 5, 2019

Region: Global
Operating Sector: Aerospace, Defense, Government Agencies, International Organizations, Media
Type of Company: N/A





Report 5

Summary:
- Threat actor: APT28 (Sofacy, Fancy Bear, Sednit)
- Date: Campaign detected on 9 August, likely started on 5 August
- Target: Specific government body in Azerbaijan, likely NATO members or countries involved in NATO exercises
- Malware: Zebrocy Delphi version with low AV detection rates
- Technique: Used NATO theme as lure, disguised malware as JPEG file with ZIP concatenation
- Capability: High confidence attribution to APT28 based on TTPs
- Novelty: Correlation with ReconHell/BlackWater attack, use of corrupted XLS file as lure
- Tools: Zebrocy malware variants with Delphi executable and Go language versions
- Behavior: Malware creates scheduled task, communicates with C2 in France
- IOCs: C2 URL, malicious file hashes
- MITRE ATT&CK: Multiple tactics and techniques used for execution, defense evasion, discovery, collection, C2, and exfiltration.





Report 6

Summary:
The report discusses the activities of the threat actor Sofacy, also known as APT28, Fancy Bear, and Tsar Team, in 2017. Sofacy is a highly active and prolific APT group known for its innovative malware set and high volume 0day deployments. The group has been involved in cyber-espionage activities for years, targeting various sectors including military, diplomatic, and defense organizations. In 2017, Sofacy focused on NATO, Ukrainian partners, Central Asia, and later shifted towards the Middle East and further east. The group deployed various malware such as GAMEFISH, Zebrocy, and SPLM, with a focus on spearphishing and credential phishing. Sofacy demonstrated good operational security and utilized encrypted communications over HTTPS. The report highlights the group's evolving and modified malware code, infrastructure setup, and targeting strategies. The report concludes with insights into the group's activities in 2018 and recommendations for network security measures to detect and mitigate Sofacy's threats.





Report 7

Summary:
- Threat actor: FancyBear/APT28, Ghostwriter/UNC1151, Mustang Panda or Temp.Hex
- Region: Ukraine and surrounding region
- Operating sector: Ukrainian media company (UkrNet), Polish and Ukrainian government and military organizations, European entities
- Date: Last 12 months, past two weeks
- FancyBear/APT28 conducted large credential phishing campaigns targeting ukr.net users using newly created Blogspot domains.
- Ghostwriter/UNC1151 targeted Polish and Ukrainian government and military organizations with credential phishing campaigns.
- Mustang Panda or Temp.Hex targeted European entities with lures related to the Ukrainian invasion using malicious attachments.
- DDoS attacks observed against numerous Ukraine sites, with Project Shield offering protection.
- Google's Threat Analysis Group continues to monitor and take action against threat actors globally.





Report 8

Malformed report





Report 9

Summary:
In June 2015, a report by netzpolitik.org detailed a digital attack on the German Parliament's Left Party infrastructure in the Bundestag. The attack involved malware found on servers, including a custom utility acting as a tunnel for maintaining network access. The artifacts retrieved suggest the involvement of the state-sponsored Sofacy group (APT28), known for targeting high-profile entities. The attackers used tools like Winexe for lateral movement and maintaining persistence. The attack, possibly lasting a few weeks, aimed at data exfiltration, indicating an experienced threat actor. The Command & Control server used in the attack was traced to CrookServers, with potential ties to previous Sofacy Group activities. The report also mentioned similarities with malware samples reported by root9B. The attribution to Sofacy Group was based on historical data and operational mistakes made by the attackers. The report highlighted the sophistication and capabilities of the threat actor, raising concerns about potential future attacks.





Report 10

Malformed report





Report 11

Summary:
Fancy Bear, also known as APT28, is a Russian cyber espionage group associated with the Russian military intelligence agency GRU. They are known for using zero-day exploits, spear phishing, and malware to target government, military, and security organizations. Fancy Bear has been active since the mid-2000s and has targeted various entities, including the Democratic National Committee, German and French elections, and the World Anti-Doping Agency. They have been linked to attacks on journalists, political organizations, and even the Ukrainian artillery. Fancy Bear's tactics are sophisticated and consistent with state-sponsored cyber espionage. The group has been indicted by the United States for their involvement in cyber intrusions affecting various entities worldwide. Their activities have been ongoing and continue to pose a threat to cybersecurity.





Report 12

Summary:
- Threat actor: Fighting Ursa Aka APT28, Fancy Bear, Sednit
- Region: Russia, Ukraine, NATO member countries, Ukraine, Jordan, United Arab Emirates
- Operating sector: Critical infrastructure, energy, transportation, telecommunications, information technology, military industrial base
- Type of company: Ministries of Defense, Ministries of Foreign Affairs, Ministries of Internal Affairs, Ministries of the Economy
- Evidence of capability: Exploited zero-day vulnerability CVE-2023-23397 in Microsoft Outlook without user interaction, targeted at least 30 organizations in 14 nations, conducted multiple campaigns over 20 months, used co-opted Ubiquiti networking devices for attacks
- Novelty of tools and techniques: Relayed NTLM authentication messages to impersonate victims, targeted high-value organizations, continued using known exploit despite public attribution
- Operation time window: First campaign between March-December 2022, second campaign in March 2023, third campaign between September-October 2023
- Source: Unit 42 Palo Alto Networks report titled "Fighting Ursa Aka APT28: Illuminating a Covert Campaign" dated December 7, 2023 at 6:00 AM.





Report 13

The report discusses a methodology used to develop Hex-Rays' Interactive Disassembler (IDA) signatures for a recently published APT28 sample. The sample, identified as x-tunnel, is a tool used by APT28 to make a compromised host inside a firewall act as a traffic proxy. The sample was uploaded by the U.S. CyberCom Cyber National Mission Force on May 17. Analysis of the sample shows capabilities including remote command execution, UDP tunnelling, TLS encryption, proxy support, and persistent HTTP via the HTTP keep-alive header. The sample, produced using Microsoft Visual C++, hints at code obfuscation/virtualization and static linking. The report details the process of building custom IDA signatures for the OpenSSL and Poco frameworks to analyze the sample. The use of custom signatures reduces the amount of unidentified code and simplifies the analysis effort. The report emphasizes the importance of mirroring the threat actor's build environment for accurate signature generation. The Lumina metadata for the Poco and OpenSSL libraries has been pushed to Hex Rays for further analysis. The report provides insights into the evolving capabilities of the threat actor and the novel techniques used in the sample.





Report 14

Summary: The threat actor identified as APT28, also known as Fancy Bear or Sednit, has been targeting government entities, businesses, universities, research institutes, and think tanks in France since the second half of 2021. The group, considered part of Russia's military intelligence service GRU, exploited vulnerabilities in WinRAR and Microsoft Outlook to compromise critical networks in France. A newly published report from ANSSI revealed that APT28 used brute-forcing, leaked databases, and phishing campaigns to gain initial access to targeted networks. The threat actor employed tools like Mimikatz, reGeorg, and VPN clients like SurfShark and NordVPN in their attacks. Data access and exfiltration were core objectives for APT28, with the group using legitimate cloud services for command and control infrastructure to avoid detection. ANSSI recommended a comprehensive security approach with a focus on email security to defend against APT28's tactics. The report was published on October 26, 2023.





Report 15

Summary:
Google has notified over 14,000 Gmail users of a spear-phishing attack conducted by APT28, also known as Fancy Bear, a state-sponsored hacking group linked to Russia's military intelligence. The campaign targeted users across various industries, with 86% of the warnings sent in a single month. The threat actor, APT28, has a history of using spear-phishing emails to gain access to sensitive information and networks. Google's Threat Analysis Group blocked all emails from this campaign and recommended high-risk users to enroll in the Advanced Protection Program. This is not a new feature, as Google has been sending alerts about state-sponsored attacks since 2012. The operation took place in late September 2021.





Report 16

Summary: APT28, also known as Fancy Bear, targeted Ukrainian government bodies with malicious emails disguised as Windows update guides. The Russian state-sponsored hacking group used fake @outlook.com email addresses and PowerShell commands to deliver a payload for information harvesting. This attack, reported by the Computer Emergency Response Team of Ukraine, highlights APT28's capability to impersonate system administrators and abuse legitimate applications like Mocky for data exfiltration. Google's Threat Analysis Group revealed that 60% of phishing emails targeting Ukraine in Q1 2023 originated from Russian threat actors, with APT28 being a major contributor. APT28 has also been reported exploiting zero-day vulnerabilities in routers and Outlook to target US, EU, and European government organizations. Chinese hackers have similarly used Windows updates as a lure in attacks against Russian government agencies. The report was published on April 30, 2023.





Report 17

Malformed report.





Report 18

Summary:
- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Region: France
- Operating sector: Media (TV5Monde)
- Date: April 2015
- Evidence of capability: Highly targeted malicious software used to destroy TV network's systems, sophisticated and targeted attack, use of bespoke malicious software, seven different points of entry, physical-world consequences, destructive intent.
- Novelty of tools and techniques: Highly targeted attacks with physical-world consequences, indicative of a new trend in cyber-attacks.
- Victims: TV5Monde, a French TV network.
- Financial impact: €5m in the first year, over €3m every following year for new protection.
- Operational impact: Staff had to return to using fax machines, special authentication procedures needed, flash drives have to be tested before being inserted, efficiency costs.
- Conclusion: TV5Monde was targeted by a group of Russian hackers known as APT 28, with the attack being designed to destroy the channel.





Report 19

Summary:
- Threat actor: Fancy Bears (Sofacy, APT 28, Sednit)
- Region: Global (specifically targeting IAAF)
- Operating sector: Sports (IAAF)
- Date: Unauthorized remote access on February 21, 2017
- Capability: Compromised athletes' Therapeutic Use Exemption (TUE) applications, sophisticated intrusion
- Novelty: Use of advanced tools and techniques, targeting sensitive medical information of athletes
- Evidence: Context Information Security discovered the attack, previous attacks on World Anti-Doping Agency
- Targeted victims: Athletes who applied for TUEs since 2012
- No Russians with TUEs named, highlighting potential bias in targeting
- No mention of IAAF information on Fancy Bears' website

Overall, the threat actor Fancy Bears demonstrated advanced capabilities in targeting sensitive medical information of athletes, highlighting the need for increased cybersecurity measures in the sports sector.





Report 20

Malformed report.





Report 21

Summary:
- Threat actor: ITG05, also known as APT28, Fancy Bear, Sednit
- Date: December 8, 2023
- Region: Targets based in at least 13 nations worldwide, including Hungary, Türkiye, Australia, Poland, Belgium, Ukraine, Germany, Azerbaijan, Saudi Arabia, Kazakhstan, Italy, Latvia, and Romania
- Operating sector: Academic, finance, and diplomatic centers
- Type of company: Academic, finance, think tanks, educational organizations, government, and non-government organizations
- Evidence of capability: ITG05 leveraged the ongoing Israel-Hamas conflict to deliver the Headlace malware, targeting entities with influence on humanitarian aid allocation
- Novelty of tools and techniques: ITG05 used authentic documents from reputable organizations as lure materials, including the United Nations, Bank of Israel, and European Parliament, and employed multi-component malware like Headlace with advanced capabilities such as continuous downloading of secondary payloads using MSEdge in headless mode.





Report 22

Summary:
Cluster25 researchers identified a threat actor linked to APT28 (Fancy Bear) using a PowerPoint file to deliver Graphite implants. The lure document exploited a code execution technique triggered by a mouse-over event in presentation mode. The malware variant used Microsoft Graph API and OneDrive for C&C communications. The threat actor targeted entities in the defense and government sectors of Europe and Eastern Europe. The campaign preparation was traced back to January-February 2022, with recent activity observed in Q3 2022. The malware communicated with the C&C through Microsoft GraphAPIs and utilized various evasion techniques. The threat actor's capabilities and novel techniques indicate ongoing activities with geopolitical objectives. The report includes indicators of compromise, detection rules, and AT&T matrix tactics used by the threat actor. The campaign is attributed to APT28, with potential targets in defense and government sectors of Europe and Eastern Europe.





Report 23

Summary:
The threat actor known as Sofacy, APT 28, Fancy Bear, or Sednit targeted victims in the Windows x64 DLL PE Compilation Timestamp on 4th July 2018. The threat actor utilized a multi-threaded DLL backdoor to gain full access and control over the target host, allowing for file upload/download, process creation, command shell interaction, and C2 communication. The implant was written in C++ and statically linked against OpenSSL and the Poco C++ framework. Notably, the threat actor employed unique techniques such as substituting PE export addresses, creating a unique CRC-32 host fingerprint, and using RSA encryption for C2 communication. The threat actor also implemented a Domain Generation Algorithm (DGA) for generating backup C2 domain names. Despite lacking modularity, the implant provided functions for spawning processes, creating/deleting files, launching shells, and setting C2 check-in intervals. The threat actor's use of XOR encryption keys for string decryption and lack of tunneling capabilities differentiated this implant from previous APT-28 tools. The report provides indicators of compromise (IoCs) and Yara signature rules for detection. The operation time window was not specified in the report.





Report 24

Summary:
- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Region: United States
- Operating sector: Political organizations, including the International Republican Institute and the Hudson Institute think tanks
- Date: August 21, 2018
- Microsoft thwarted Russian attempts to launch cyber-attacks against US conservative groups.
- Fancy Bear hacking group was behind the attacks, trying to steal data through mimicked domains.
- Evidence of capability: Microsoft seized domains associated with Senate offices and services.
- Novelty of tools and techniques: Spear phishing campaign to steal login information.
- Microsoft shut down 84 websites associated with Fancy Bear in two years.
- No evidence of the seized domains being used in attacks, but potential for future assaults.





Report 25

Summary:
- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Region: Europe
- Operating sector: Think tanks critical of Russia
- Type of company: German Marshall Fund, Aspen Institute Germany, German Council on Foreign Relations
- Date: Last three months of 2018
- Evidence of capability: Spear-phishing attacks targeting European employees
- Novelty of tools and techniques: Phony websites to infiltrate victims' systems, use of legal strategy to disable domains
- Ongoing effort to target democratic organizations
- Microsoft expanding cybersecurity protections for candidates, campaign offices, think tanks, and political organizations under attack.





Report 26

Summary:
- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Region: United States
- Operating sector: Government agency
- Date: June 14, 2016
- Evidence of capability: Identified spear phishing email targeting US government, use of Carberp variant of Sofacy Trojan with new persistence mechanism, use of Carberp source code, network beacons to C2 servers, deployment of secondary payloads
- Novelty of tools and techniques: Unique persistence mechanism using Microsoft Office applications, encryption of network beacons, use of one-off infrastructure to evade detection
- Infrastructure: New C2 domains, overlap with previous Sofacy-related C2s, use of AutoFocus for correlation
- Conclusion: Continued attacks on government organizations, development of new tactics and techniques, Palo Alto Networks protection and detection capabilities

Malformed report.





Report 27

Summary:
- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Region: Global, possibly associated with the Russian government
- Operating sector: Various, including Russian dissidents, journalists, U.S. Defense Contractors, NATO forces, and White House staff
- Type of company of victims: Not specified
- Date: Attack started on August 4, 2015
- Evidence of capability: Utilized a Java zero-day exploit, sophisticated spear phishing campaign, targeted malware delivery, and connection to command and control server
- Novelty of tools and techniques: Used a unique URL redirection to deliver Java exploit, downloaded second stage binary for execution, and targeted Mac or Linux users as well
- Conclusion: Likely part of the larger Pawn Storm campaign, associated with Sednit/Sofacy, APT 28, and Russian government
- Recommendations: Be vigilant against phishing attacks and update Java to patch vulnerabilities

Malformed report.





Report 28

Summary:

Norway has attributed the August 2020 Parliament hack to the Russian hacking group APT28, also known as Fancy Bear or Sednit. The victims targeted were in the government sector, specifically the Parliament. The evidence of the threat actor's capability is demonstrated by their successful breach of the Parliament's systems. APT28 is known for using novel tools and techniques, showcasing their advanced cyber capabilities. The operation time window for this attack was in August 2020.





Report 29

Summary:
- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Operation RussianDoll: Leveraged Adobe & Windows Zero-Day Exploits
- Highly-targeted attack by APT28 likely from Russia
- Date: Attacks detected starting on April 13th, 2015
- Adobe patched vulnerability CVE-2015-3043
- Microsoft working on fix for CVE-2015-1701
- Exploits involved HTML/JS launcher, Flash exploit, shellcode, and payload
- Malware variant linked to APT28 backdoors CHOPSTICK and CORESHELL
- Targeted an international government entity in an industry vertical aligned with APT28 targeting
- Novelty: Exploited zero-day vulnerabilities, used advanced techniques like ROPless Flash exploit, and delivered sophisticated malware payloads.





Report 30

Summary:
The threat actor identified as Sofacy, APT 28, Fancy Bear, and Sednit targeted the Democratic National Committee (DNC) in the United States in 2016. CrowdStrike, a cybersecurity company, was hired to investigate the breach and identified two sophisticated Russian intelligence-affiliated adversaries, COZY BEAR and FANCY BEAR, operating separately on the DNC network. COZY BEAR used the SeaDaddy implant and Powershell backdoor for intrusion, while FANCY BEAR deployed X-Agent malware and X-Tunnel network tunneling tool. The adversaries engaged in anti-forensic measures and targeted various sectors beyond politics. The intrusion was detected in April 2016, with remediation lasting from June 10-13, 2016. The tools and techniques used by the threat actors demonstrated advanced capabilities and extensive operational security. The investigation concluded that Russia was behind the DNC data breach, with evidence supported by the U.S. Intelligence community and independent reports. The threat actors' activities were consistent with nation-state adversaries associated with Russian intelligence. The report provides detailed indicators of compromise and insights into the threat actor's tactics, techniques, and procedures. The operation window for the investigation and remediation was from April to June 2016.





Report 31

Summary:
The threat actor known as Sofacy, APT 28, Fancy Bear, or Sednit, also referred to as Pawn Storm, has been observed using unsophisticated attack methods such as brute force attacks and simple remote access trojans (RATs) in their operations. In 2020, they targeted ministries of foreign affairs, embassies, the defense industry, and the military, as well as a wider range of industries globally. The threat actor used Google Drive and IMAP RATs for attacks, with evidence of compromised military and government-related email addresses being used in their malware. The actor showed a learning curve in malware development, with incremental improvements like encryption and the addition of a keylogger. The group also engaged in brute force attacks on internet-facing services like email, LDAP, Microsoft Autodiscover, SMB, and SQL. The activities of Pawn Storm were monitored closely by Trend Micro, with indicators of compromise provided for detection and response. Trend Micro recommends their XDR solution for comprehensive monitoring and response to such threats. 

Date: 2020

Region: Global

Operating Sector: Ministries of foreign affairs, embassies, defense industry, military, various industries

Type of Company: Not specified





Report 32

Malformed report





Report 33

Summary:
- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Region: Netherlands
- Operating sector: Government (Netherlands ministeries)
- Date: Hack attempts in the past six months
- Evidence: Attempted intrusion into Dutch ministeries by Russian groups APT28 and APT29 (Cozy Bear and Fancy Bear), known for phishing emails and setting up fake websites to obtain login credentials.
- Novelty: Use of sophisticated phishing techniques and fake websites to target government personnel.
- No sensitive information obtained during the hack attempts.
- Source: Volkskrant article by Huib Modderkolk on February 4, 2017.
- AIVD expressed concerns about digital attacks from Russia, China, and Iran.
- Overall, the threat actor demonstrated capability in targeting government entities with advanced phishing tactics.





Report 34

Summary:
- Threat actor: Fancy Bears, APT 28, Sednit
- Region: Russia
- Operating sector: International Olympic Committee, United States Olympic Committee, third-party groups associated with the organizations
- Date: January 10, 2018
- Evidence of capability: Fancy Bears targeted antidoping investigators, published stolen emails, linked to Russia's primary intelligence agency GRU, attempted to discredit individuals involved in investigating Russian doping schemes
- Novelty of tools and techniques: Used phishing schemes to breach email accounts, published stolen emails to undermine WADA and IOC, attempted to revive claims of systemic cheating by Russian athletes
- Overall, the hack was seen as an attempt to save face on the international sports stage, but unlikely to change the IOC's decision to ban Russia.





Report 35

In November, the Russian threat actor Sofacy, also known as APT28, Fancy Bear, and Sednit, used COVID-19 phishing lures to deliver the Go version of Zebrocy. The victims targeted were mainly governments and commercial organizations engaged in foreign affairs. The malware was delivered through a Virtual Hard Drive (VHD) file requiring Windows 10 to access. The samples were attributed to Sofacy due to shared genomes with previous campaigns. The threat actor switched from delivering the Delphi version of Zebrocy to the Go version in November. Zebrocy is a downloader used by Sofacy since 2015, known for evolving in different programming languages. The malware collects information about infected hosts and uploads it to the command and control server. The threat actor has been targeting victims in various countries, mainly in foreign affairs sectors. The malware samples were detected as genetically similar to previous Sofacy malware. The infrastructure used by the threat actor appears to be new, with the malware being obfuscated and using anti-debugging checks. The threat actor has been using COVID-19 themed lures to deliver the malware, indicating ongoing threats in this area.





Report 36

Summary:
- Threat actor: Fancy Bear (also known as APT28, Sednit)
- Target: French Presidential Candidate Macron
- Date: April 24, 2017
- Evidence: Cybersecurity firm Trend Micro found that Fancy Bear created phishing domains similar to Macron's official campaign website to launch attacks.
- Novelty: Fancy Bear has a history of successful phishing attacks targeting high-value individuals.
- Region: France
- Operating Sector: Political campaign
- Capability: Fancy Bear's phishing techniques are sophisticated and effective, with a focus on tricking victims into giving away passwords.
- Company Type: Macron's campaign used Microsoft Outlook for emails.
- Despite public exposure, Fancy Bear continues its operations without slowing down.





Report 37

Summary:
- Threat actor: APT28 (aka Fancy Bear, Sofacy)
- Region: Ukraine
- Operating sector: Government, critical organizations
- Date: May 2022
- Evidence of capability: APT28 exploited Follina vulnerability in phishing campaigns to install CredoMap malware and Cobalt Strike beacons targeting Ukrainian recipients.
- Novelty of tools and techniques: CredoMap malware detected by AV engines as a password-stealing Trojan, exfiltrates data via IMAP, Cobalt Strike beacon used in parallel campaign with recent compilation date.
- APT28 known for cyber espionage, active since 2007, with ties to Russian government, targeting governments, military, and security organizations.
- CERT-UA advises vigilance against email-delivered threats, especially spear-phishing attacks.





Report 38

Summary:
- Threat actor: Fancy Bear, APT 28, Sednit
- Region: Russia
- Operating sector: Cybersecurity
- Victims: World Anti-Doping Agency, Democratic National Committee
- Date: August 23, 2016
- Evidence of capability: Infiltrated WADA website, targeted DNC, used phishing emails, spoofed official domains
- Novelty of tools and techniques: Registered new domains consistent with Fancy Bear tactics, targeted whistleblowers, linked to Russian government
- Connection to Russian political figures, retaliation against whistleblowers, potential for more cyberattacks
- Evidence linking Russian government to DNC infiltration, denial by Kremlin
- Multiple cybersecurity firms provided evidence of Russian involvement
- Focus on retaliatory influence, propaganda efforts, and augmenting security posture against Russian cyber operations.





Report 39

Summary: A threat actor identified as APT28, also known as Fancy Bear or Sednit, has been actively exploiting a critical Outlook bug (CVE-2023-23397) to hijack Microsoft Exchange accounts and steal sensitive information. The targeted entities include government, energy, transportation, and other key organizations in the United States, Europe, and the Middle East. APT28 has been leveraging this vulnerability since April 2022, using specially crafted Outlook notes to steal NTLM hashes and perform lateral movement within victim environments. Despite security updates and mitigation recommendations, the attack surface remains significant, with ongoing attacks exploiting other vulnerabilities like CVE-2023-38831 in WinRAR. The threat actor's capability to exploit zero-day vulnerabilities and conduct targeted attacks against various sectors demonstrates their advanced tactics and persistence. The most effective defense strategy recommended is to reduce the attack surface and ensure regular software updates with the latest security patches. The report was published on December 4, 2023, by BleepingComputer.





Report 40

Summary:
- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Date: February 10, 2015
- Region: United States
- Operating sector: Military spouses
- Evidence: Russian hackers posed as IS to threaten military wives, targeting five military wives with death threats under the guise of CyberCaliphate, but were actually linked to Russian hacking group Fancy Bear or APT28.
- Novelty: The false flag operation showcased the difficulty of attributing blame in the cyber realm, with Russian hackers borrowing identities to mislead investigators, similar to their interference in the 2016 U.S. election.
- Tools and techniques: The threat actor used sophisticated tactics to target high-profile military spouses, creating fear and confusion, and manipulating media coverage.
- Impact: The threat actor's actions led to heightened tensions and anti-Muslim sentiment, showcasing the effectiveness of their disinformation campaign.
- Conclusion: The threat actor's targeting of military spouses and media outlets demonstrated their capability to manipulate public perception and generate widespread attention through cyber operations.





Report 41

Summary:

- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Date: 09/20/2016
- Region: Germany
- Operating sector: Political parties and federal Bundestag parliamentary factions
- Evidence of capability: German BSI data security agency warned German political parties of cyber hackers, suspected to be Russian groups, being innovative.
- Novelty of tools and techniques: Russian groups suspected of using advanced hacking techniques.
- Source: http://www.dw.com/en/hackers-lurking-parliamentarians-told/a-19564630





Report 42

Summary: A Russian state-sponsored threat actor known as APT28, Fancy Bear, or Strontium targeted Ukraine between December 15 and 25, 2023, using a new malware called MASEPIE. The threat actor deployed phishing emails to deliver the malware, which utilized PowerShell commands and a Python downloader to establish persistence on infected devices. The malware's primary function was to download additional malware and steal data, while additional tools like STEELHOOK and OCEANMAP were used for data theft and remote command execution. The attack demonstrated rapid deployment of tools within an hour of compromise, indicating a well-coordinated and sophisticated operation targeting government entities, businesses, universities, research institutes, and think tanks in Western countries and NATO organizations. The threat actor's use of novel techniques and tools highlights their advanced capabilities in cyber operations.





Report 43

Summary:
- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Region: Netherlands
- Operating sector: Peace organization (PAX)
- Date: November 2017
- Evidence of capability: Phishing attacks targeting PAX, creation of fake domain names resembling legitimate ones, use of Dutch and Lithuanian servers for attacks
- Novelty of tools and techniques: Use of phishing emails, creation of deceptive domain names, targeting organizations critical of Russian actions in Syria and Ukraine
- Trend of using Dutch servers for attacks on various targets, including political campaigns and media organizations
- No response from PAX regarding the attacks
- Connection to Russian military intelligence
- Use of hosters in the Netherlands for server rentals

Overall, the threat actor Sofacy, APT 28, Fancy Bear, Sednit targeted the Dutch peace organization PAX with phishing attacks using deceptive domain names and Dutch servers, showcasing their capability and persistence in targeting organizations critical of Russian actions.





Report 44

Summary:
- Threat actor: STRONTIUM, also known as APT 28, Fancy Bear, Sednit
- Region: Targeted US and UK organizations involved in political elections
- Operating sector: Political elections
- Type of company: Not specified
- Evidence of capability: Launched credential harvesting attacks against tens of thousands of accounts at more than 200 organizations between September 2019 and June 2020
- Novelty of tools and techniques: Shifted from spear phishing to brute-force/password-spray tooling, utilizing a pool of approximately 1,100 IPs, majority associated with Tor anonymizing service
- Date: Activity tracked since April 2020, with attacks targeting 6,912 accounts belonging to 28 organizations between August 18 and September 3
- Focus on 2020 US Presidential Election and future electoral contests in the UK
- Recommendations: Enable multi-factor authentication, monitor failed authentications, test organization's resilience with Attack Simulator in Office 365 ATP.





Report 45

Summary:
The threat actor known as Sofacy, APT 28, Fancy Bear, or Sednit, has been active since at least 2004 and is attributed to Russia's Main Intelligence Directorate. They have targeted various sectors including government, defense, and media organizations in countries worldwide, with a focus on Eastern Europe. The group has used a wide range of tools and techniques, including zero-day exploits, phishing attacks, and malware like Zebrocy and LoJax. Notably, they were involved in the 2016 DNC breach and have targeted organizations involved in elections, think tanks, and anti-doping agencies. Counter operations have been conducted by various entities, including the US Justice Department and Microsoft's Digital Crimes Unit. The threat actor continues to be active, with recent operations targeting Ukraine and using new malware variants like MASEPIE and Headlace.





Report 46

Summary:
The threat actor known as Sofacy, APT 28, Fancy Bear, or Sednit has been active since 2008, targeting military and government entities worldwide, with a focus on NATO countries and an increase in activity targeting Ukraine. The group has developed a variety of backdoors and tools, including CORESHELL, SPLM, JHUHUGIT, and AZZY implants. In August 2015, a new wave of attacks was observed, utilizing a new generation of USB stealers exclusively targeting high-profile victims. The group's speed and use of multi-backdoor packages for resilience are notable. The attacks do not rely on zero-day vulnerabilities but are delivered through separate malware. The group has increased its activity significantly in recent years, focusing on defense-related targets. The best defense against such attacks is a multi-layered approach combining anti-malware technologies, patch management, and host intrusion detection. The group's new tools and techniques, such as the USB stealers, demonstrate their evolving capabilities.





Report 47

Summary:
- Threat actor: Sofacy (APT28, Fancy Bear, Sednit)
- Date: February 28, 2018
- Region: Global
- Operating sector: Government entities (Ministries of Foreign Affairs)
- Evidence of capability: Used phishing emails with malicious Excel attachments containing hidden macro scripts to deliver loader Trojan (SofacyCarberp variant) for reconnaissance and C2 communication.
- Novelty of tools and techniques: Leveraged Luckystrike open-source tool for macro generation, used custom algorithm for payload decryption, employed hashing algorithm for API resolution, injected code into browsers for C2 communication, simulated keyboard input for taking screenshots.
- Persistence and similarity in tooling: Continues to be persistent in attack campaigns, uses similar tooling as in the past, indicating potential success despite available threat intelligence.
- Protection measures: WildFire detects SofacyCarberp payloads, AutoFocus tracks related tools, Traps blocks delivery documents and payloads.
- IOCs: SHA256 hashes, domains, email subject, and filenames provided.
- Conclusion: Sofacy group remains active and well-documented, with persistent attack campaigns using known and novel techniques.





Report 48

Sofacy, also known as APT 28, Fancy Bear, or Sednit, has been identified as the threat actor behind a global attack involving the deployment of a new 'Cannon' Trojan. The attack, intercepted by Unit 42 in late October and early November 2018, targeted government entities in North America, Europe, and a former USSR state. The weaponized documents used a technique to load remote templates containing a malicious macro, making automated analysis challenging. The Cannon Trojan, a novel tool observed for the first time, utilizes an email-based C2 communication channel, a less common tactic compared to HTTP or HTTPS. This approach may decrease the chance of detection, as sending emails via non-sanctioned providers may not raise suspicion. The Cannon Trojan functions primarily as a downloader, relying on emails to communicate with the C2 server, and has a heavy reliance on EventHandlers with timers to run its methods in a specific order, potentially increasing its evasion capability. The threat actor behind Sofacy continues to target government organizations in the EU, US, and former Soviet states, delivering payloads such as the Zebrocy tool. The delivery documents used in these attacks leverage remote templates, making analysis challenging without an active C2 server. The use of the recent Lion Air disaster as a lure in one of the attacks demonstrates the threat actor's willingness to exploit current events for social engineering. The Cannon Trojan, with its unique communication method using SMTPS and POP3S, presents a new challenge for detection due to its legitimate email service provider hosts and encryption layers. Palo Alto Networks customers are protected from this threat through various security measures.





Report 49

Summary:
The Sofacy group, also known as APT 28, Fancy Bear, or Sednit, conducted parallel attacks targeting government, diplomatic, and strategic organizations primarily in North America and Europe. In June 2018, a new campaign utilizing the Zebrocy tool was discovered, delivered through phishing attacks with malicious Microsoft Office documents and simple executable file attachments. This campaign targeted government organizations dealing with foreign affairs in different geopolitical regions, casting a wider net within the target organizations compared to previous attacks. Additionally, the Sofacy group leveraged the Dynamic Data Exchange (DDE) exploit technique to deliver different payloads, including Zebrocy and the Koadic toolkit, a freely available open-source penetration testing toolkit. The group used various programming languages for Zebrocy variants, such as Delphi, AutoIt, and C++, and employed sophisticated obfuscation techniques in their attacks. The attacks were largely perpetrated through spear phishing campaigns, showcasing the group's evolving capabilities and novel techniques. The report provides detailed technical analysis, indicators of compromise (IOCs), and insights into the Sofacy group's ongoing targeted attack campaigns.





Report 50

Sofacy, also known as APT 28 or Fancy Bear, targeted a European government agency in March 2018 using an updated variant of DealersChoice, a Flash exploitation framework. The attack involved spear-phishing emails with malicious Microsoft Word attachments that required user interaction to trigger the malicious Flash object. The Flash object contained an evasion technique where it only loaded if the user scrolled to a specific page in the document, a novel approach not previously observed. Sofacy's developers modified open-source ActionScript code to load embedded Flash objects from a command and control server, demonstrating advanced capabilities. The attack process involved multiple interactions with the C2 server to successfully exploit the victim's system. The use of sophisticated techniques and the targeting of a specific sector, a European government agency, indicate the threat actor's high level of sophistication and persistence.





Report 51

Summary:
- Threat actor: Sofacy, also known as APT28, Fancy Bear, Sednit
- Date: September 26, 2016
- Region: Global
- Operating sector: Aerospace industry
- Type of company: Not specified
- Evidence of capability: Identified a new OS X Trojan 'Komplex' associated with Sofacy group targeting individuals in the aerospace industry running OS X. Komplex shares traits with Carberp variant used by Sofacy on Windows systems. Komplex uses an 11-byte XOR algorithm for decryption and communicates with C2 servers using HTTP POST requests. Code overlaps suggest Komplex is linked to a Trojan delivered through MacKeeper vulnerability. Infrastructure overlaps with apple-iclouds[.]net and itunes-helper[.]net domains tied to Sofacy activity. 
- Novelty of tools and techniques: Komplex Trojan showcases Sofacy's evolution towards multi-platform attacks, capable of downloading files, executing commands, and interacting with the system shell. Design similarities with Sofacy's Carberp variant indicate potential cross-platform capabilities. 
- Malware indicators: Hashes: 2a06f142d87bd9b66621a30088683d6fcec019ba5cc9e5793e54f8d920ab0134, C2 Locations: appleupdate[.]org, apple-iclouds[.]net, itunes-helper[.]net, IP 185.10.58.170.





Report 52

Summary:
- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Campaign name: Steal-It Campaign
- Date: September 06, 2023
- Operating sector: Not specified
- Regions targeted: Australia, Poland, Belgium
- Victims: Not specified
- Capability: Customized PowerShell scripts, geofencing strategy, use of Mockbin APIs for exfiltration
- Novelty: Customized PowerShell scripts, geofencing strategy, use of Mockbin APIs
- Tools and techniques: Customized PowerShell scripts, LNK files in zip archives, exfiltration via Mockbin APIs
- Attribution: APT28 (Fancy Bear) with medium confidence level
- Conclusion: Steal-It campaign demonstrates targeted geofencing strategy and sophisticated tactics with a focus on technical expertise and persistence.





Report 53

Summary:
The threat actor known as TA422, also identified as APT28, Fancy Bear, and Sednit, has been observed by Proofpoint researchers conducting phishing campaigns targeting organizations in Europe and North America since March 2023. The threat actor exploited patched vulnerabilities, including CVE-2023-23397 and CVE-2023-38831, to target government, aerospace, education, finance, manufacturing, and technology sector entities. TA422 used sophisticated techniques such as leveraging TNEF files in Microsoft Outlook to obtain NTLM password hashes and hosting SMB listeners on compromised Ubiquiti routers. The threat actor also utilized Mockbin and InfinityFree for URL redirection in their campaigns. The novelty of the tools and techniques used by TA422, along with the repeated large-scale exploitation of disclosed vulnerabilities, indicates a high level of capability and persistence. The operation time window for the observed activity ranges from March 2023 to November 2023. 

Region: Europe and North America
Operating Sector: Government, aerospace, education, finance, manufacturing, and technology
Type of Company: Various sectors targeted, including defense, aerospace, technology, government, and manufacturing.





Report 54

Summary:
- Threat Group-4127, also known as APT 28, Fancy Bear, Sednit, and Sofacy, targets Google Accounts primarily linked to governments, military, NGOs, and individuals associated with U.S. politics.
- The group operates from Russia and gathers intelligence on behalf of the Russian government.
- In June 2016, they targeted email accounts related to Hillary Clinton's presidential campaign and the U.S. Democrat National Committee using spearphishing techniques.
- They used the Bitly URL-shortening service to hide the location of a spoofed Google login page, targeting over 1,800 Google Accounts.
- The threat actor targeted individuals in Russia, former Soviet states, U.S. military and government personnel, defense and government supply chain, authors, journalists, and political activists.
- The threat actor's novel technique involved using Base64-encoded values in phishing URLs and creating over 3,000 shortened links to target Google Accounts.
- The threat actor poses a broad threat to individuals and groups associated with U.S. politics, government, defense, and those commenting on Russia.
- The success of the phishing campaign indicated that recipients often clicked on the malicious links, potentially compromising their Google Accounts.
- Organizations and individuals operating in Russia, former Soviet states, Western Europe, and the U.S. are at risk of being targeted by Threat Group-4127.
- Recommendations include educating users about spearphishing risks, exercising caution with shortened links, and checking full URLs before clicking. 

Date: June 2016 (specific operation time window not provided)

Source: https://www.secureworks.com/research/threat-group-4127-targets-google-accounts





Report 55

Summary:
- Threat actor: Sofacy, APT 28, Fancy Bear, Sednit
- Region: Ukraine, with a focus on Russia
- Operating sector: Energy, Defense, Information Operations
- Novelty of tools and techniques: FROZENBARENTS (GRU Unit 74455) used versatile offensive capabilities including credential phishing, mobile activity, malware, and exploitation of services. They targeted sectors like government, defense, energy, transportation, education, and humanitarian organizations. FROZENLAKE (APT28) used reflected cross-site scripting (XSS) on Ukrainian government websites for phishing. PUSHCHA targeted regional webmail providers. Russian Information Operations included leveraging YouTube, Blogger, and other platforms to shape public perception of the war in Ukraine.
- Date: First quarter of 2023
- Source: https://blog.google/threat-analysis-group/ukraine-remains-russias-biggest-cyber-focus-in-2023/





Report 56

Summary:
- Threat actor: Fancy Bear (also known as APT28), associated with Russian military intelligence agency GRU.
- Date: September 5th, 2023.
- Region: Ukraine.
- Operating sector: Critical energy facility.
- Evidence of capability: Attempted intrusion thwarted by cybersecurity expert within the targeted organization.
- Novelty of tools and techniques: Unusual phishing email containing images and a BAT file, as well as installation of Tor for anonymous browsing.
- Previous history: Fancy Bear known for attacking U.S. Democratic National Committee during 2016 elections.
- Response: Employee identified cyberthreat and restricted access to certain web resources.
- Concerns: Potential for new blackouts in Ukraine's energy infrastructure due to Russian actions.
- Conclusion: Ongoing cyberwar between Ukraine and Russia with potential impact on cyberspace activity.





Report 57

Summary:
- Threat actor: APT28 or Fancy Bear, attributed to Russia GRU
- Region: Eastern Europe, specifically targeting users in Ukraine
- Operating sector: Critical infrastructure entities including oil and gas, telecommunications, and manufacturing
- Novelty of tools and techniques: Using a new variant of malware distributed via email attachments in password-protected zip files to steal cookies and saved passwords from browsers
- Date: May 03, 2022
- Evidence of capability: Targeting high-risk individuals in Ukraine, using unique links per target to download malicious files, and sending credential phishing emails to government officials, politicians, NGOs, and journalists
- Collaboration with Yahoo! Paranoids Advanced Cyber Threats Team
- Actions taken: Blocking phishing domains through Google Safe Browsing, alerting targeted users, and adding identified websites and domains to Safe Browsing for protection.





Report 58

Summary:
The threat actor known as Zebrocy, associated with APT 28, Fancy Bear, and Sednit, is a Russian-speaking APT group with a lineage dating back to 2013, sharing similarities with BlackEnergy and Sofacy. Zebrocy's malware activities involve a mix of languages and technologies, including spearphishing operations, browser credential theft, keylogging, and Windows credential theft. The group's malware set includes a variety of backdoors implemented in languages like C#, Python, and Go, with a focus on profiling targets and developing bespoke second-stage credential harvesters. Zebrocy's infrastructure overlaps with both Sofacy and BlackEnergy, demonstrating a commitment to gaining access to targeted networks. The threat actor's innovative malware set and consistent copy/paste tendencies set them apart from other APT groups. Zebrocy's ongoing activity indicates a long-term strategy targeting government and military-related organizations. The report was published on June 3, 2019, by Kaspersky's Global Research and Analysis Team (GReAT).


