
Report 1

Summary:
APT35, also known as Charming Kitten, a cyber-espionage group associated with an Iran-based nation state threat actor, was discovered by Darktrace in a pre-infected environment in the EMEA region. The threat actor had infected a corporate device through spear phishing, exhibiting 'low and slow' behavior by remaining undetected and engaging in command and control (C2) beaconing. Darktrace's Cyber AI Analyst detected the C2 activity without signatures or threat intelligence, leading to the isolation of the infected device by the internal security team. The threat actor, APT35, was found to be lying low and waiting for further instructions. Darktrace's AI capabilities allowed for the quick identification of the infected device, assessment of the impact of the intrusion, and prevention of further malicious activity. The threat actor's use of known malicious domains and the sophistication of the attack highlighted the need for unsupervised machine learning to detect and defend against evolving threats. The incident demonstrated the value of Darktrace in detecting pre-existing infections and 'low and slow' attacks, showcasing the importance of AI in understanding and responding to cyber threats. The report was published on April 22, 2021.





Report 2

Summary:
The report discusses the activities of threat actors targeting journalists and media organizations, specifically focusing on APT actors such as TA412, TA459, TA404, TA482, TA453, TA456, and TA457. These threat actors, believed to be aligned with state interests of China, North Korea, Iran, and Turkey, have been observed using various techniques such as web beacons for reconnaissance, credential harvesting, and sending malware to gain access to sensitive information. The campaigns have targeted journalists and media personnel, particularly those covering topics of state-designated import. The report highlights the evolving tactics of these threat actors, including the use of benign emails, social media account credential phishing, and impersonation of journalists to gather intelligence and manipulate public perceptions. The activities have been ongoing since early 2021, with specific campaigns targeting US-based journalists and media organizations. The report emphasizes the importance of vigilance and caution for individuals operating in the media sector to protect themselves from becoming victims of APT attacks. The threat actors have shown a sustained effort to target journalists and media organizations, indicating a persistent threat to this sector. The report provides detailed insights into the operations of these threat actors, their motivations, and the tools and techniques they employ to achieve their objectives.





Report 3

Summary:
The threat actor known as TA453, also referred to as Charming Kitten, targeted senior medical professionals specializing in genetic, neurology, and oncology research in the United States and Israel in a credential phishing campaign named BadBlood. The campaign, which took place in late 2020, used social engineering lures related to Israeli nuclear capabilities and a forged Microsoft login page to harvest user credentials. TA453 targeted less than 25 senior professionals at medical research organizations in the US and Israel, indicating a shift in their usual targeting. While Proofpoint researchers could not conclusively determine the motivation behind the campaign, it is consistent with TA453's historical alignment with Islamic Revolutionary Guard Corps (IRGC) collection priorities. The use of novel tactics and techniques, such as the actor-controlled Gmail account and forged Microsoft login page, demonstrates the capability of the threat actor. The campaign signifies a potential evolution in TA453's targeting priorities towards the medical sector, reflecting a broader trend of espionage-focused threat actors targeting medical research globally. The threat actor's historical association with IRGC intelligence collection priorities further supports the attribution to TA453. The campaign utilized multiple actor-controlled domains and URLs for phishing attempts, indicating a coordinated effort by the threat actor. Further analysis of TA453 campaigns will determine if the targeting of medical professionals is a lasting shift or a temporary change in collection priorities. The campaign highlights the increasing targeting of the medical sector by threat actors for intelligence purposes.





Report 4

Summary:
- Threat actor: COBALT MIRAGE (linked to COBALT ILLUSION)
- Region: Targets organizations in Israel, U.S., Europe, and Australia
- Operating Sector: U.S. philanthropic organization targeted in January 2022
- Type of Company: U.S. local government network targeted in March 2022
- Capability: Uses BitLocker, DiskCryptor for ransomware attacks, ProxyShell exploits, FRP tool, PowerShell commands, LSASS dump
- Novelty: Custom Go binary (dllhost.exe) with FRP references, use of Python-based scripts, sending ransom notes to local printers
- Date: Operations ongoing since at least June 2020, with specific incidents in January and March 2022
- Tools: FRPC, Ngrok tunneling tool, wmiexec.exe, network scanners
- Recommendations: Patch high-severity vulnerabilities, implement multi-factor authentication, monitor for indicators of compromise

Date: May 12, 2022
(Source: https://www.secureworks.com/blog/cobalt-mirage-conducts-ransomware-operations-in-us)





Report 5

Charming Kitten, also known as APT35, is an Iranian government cyberwarfare group involved in cyberespionage and cyberwarfare activities primarily in the Middle East region. The threat actor has been identified using zero-days, spearphishing, malware, social engineering, and watering hole techniques. Evidence suggests that Charming Kitten has been expanding its malware capabilities and intrusion campaigns, targeting victims such as US officials, military contractors, and individuals involved in the 2015 Iran Nuclear Deal. The group has used phishing tactics to impersonate company websites and create fake accounts and DNS domains to steal passwords. Notably, in 2021, Charming Kitten developed a new data extraction tool called HYPERSCRAPE to steal data from email providers like Google, Yahoo!, and Microsoft. This tool requires the target's credentials to create a session and downloads victim's emails while hiding its fingerprint. The threat actor's activities have been linked to various incidents, including the HBO cyberattack in 2017 and election interference attempts in 2020. The group has been associated with individuals like Behzad Mesri and Mojtaba Masoumpour, facing indictments for conspiracy, computer intrusion, and espionage charges. Microsoft and other cybersecurity experts have attributed election interference attempts to Charming Kitten, highlighting the group's consistent attack vectors and victim profiles. The report provides insights into the group's evolving capabilities and novel tools, showcasing their ongoing cyber operations.





Report 6

Summary:
Charming Kitten, a threat actor believed to be operating out of Iran, has been observed by Volexity engaging in sophisticated spear-phishing campaigns aimed at credential harvesting. Recently, Charming Kitten attempted to distribute an updated version of their backdoor, POWERSTAR, with improved operational security measures to evade analysis. The new variant of POWERSTAR utilizes the InterPlanetary File System (IPFS) for hosting decryption functions and configuration details on publicly accessible cloud hosting. The threat actor employs a phishing playbook involving benign interactions with targets before delivering malicious attachments. Charming Kitten's malware, POWERSTAR, exhibits remote execution capabilities, persistence mechanisms, and reconnaissance functionalities. The threat actor's use of IPFS for C2 communication adds a novel twist to their operations, allowing for dynamic updates of C2 addresses. Volexity recommends using YARA rules to detect related activity and blocking IOCs associated with Charming Kitten's operations. The threat actor's evolving tactics and tools indicate a focus on malware-enabled espionage with a broader set of tools beyond POWERSTAR.





Report 7

Summary:
The threat actor known as Charming Kitten, also identified as APT35, conducted a targeted phishing campaign during the Christmas holidays and the beginning of the new year in 2021. The Iranian state-backed hackers targeted individuals in various sectors, including members of think tanks, political research centers, university professors, journalists, and environmental activists in regions around the Persian Gulf, Europe, and the US. The attackers used sophisticated techniques such as sending fake SMS and fake emails to steal sensitive data from victims' online accounts, particularly Gmail, Yahoo!, Outlook, and other services like Planet.com and PlanetObserver.com. Charming Kitten employed a chain of redirection links to obfuscate their operations and utilized unconventional TLDs and deceptive words in URLs to evade detection. The campaign intensified in recent days, showcasing the threat actor's continued activity and evolving tactics. The report recommends using secure authentication methods like two-factor authentication with security keys to mitigate the risk of falling victim to such attacks. Date: 2021.1.8.





Report 8

Malformed report.





Report 9

Summary:
- Threat actor: Charming Kitten (APT 35)
- Region: Iran
- Operating sector: Targeted journalists, political and human rights activists
- Type of company: Private and government institutions, think tanks, academic institutions, organizations with ties to the Baha’i community
- Date: 2020.1.30
- Evidence of capability: Novel phishing campaign targeting public figures globally, use of fake interviews to steal email account information, development of malware "pdfreader.exe" with backdoor feature, use of Google Sites for phishing attacks, use of phishing kits like Modlishka to steal passwords and 2FA codes
- Novelty of tools and techniques: Use of Google Sites, hosting phishing pages on Google Sites, use of two-step-checkup[.]site domain for phishing, development of malware "pdfreader.exe" with backdoor feature, interaction with specific IP addresses for malicious activities
- Conclusion: Charming Kitten continues to target victims for information extraction and has developed new tactics for phishing attacks.





Report 10

Summary: Iranian threat actor Charming Kitten, also known as APT 35, Cobalt Illusion, and Magic Hound, has been identified impersonating ClearSky, a security firm that previously uncovered its campaigns. The threat actor operates in the Iranian ecosystem of hackers, with researchers noting the challenges in attributing operations to specific groups due to the instability in the field. The capability of Charming Kitten to impersonate a security firm demonstrates a high level of sophistication and deception. The novelty of this tactic raises concerns about the evolving techniques used by the threat actor. The victims targeted by Charming Kitten include companies in the security sector. The report does not specify a date or operation time window. 

##################





Report 11

Summary:
In early January 2017, Iranian threat actors targeted a Middle Eastern organization using a phishing campaign that distributed the PupyRAT malware. The threat actor used shortened URLs in phishing emails that redirected to spoofed domains hosting malicious content. Recipients who clicked the URL were presented with Microsoft Office documents that attempted to run a macro and install PupyRAT, a remote access trojan. The threat actor behind this campaign is closely aligned with the COBALT GYPSY threat group, associated with Iranian government-directed cyber operations. The campaign utilized job-themed lures and legitimate email addresses for spearphishing. CTU analysis confirms that PupyRAT provides full access to victim systems. Organizations are advised to educate users on spearphishing risks, disable macros in Microsoft Office, and implement advanced malware prevention and endpoint threat detection tools. The threat indicators associated with this campaign are provided for risk assessment. Confidence in the assessment of this threat activity is high.





Report 12

Summary:
- Threat actor identified as PHOSPHORUS, an Iranian APT actor, targeted an infrastructure and construction company in the Southern U.S.
- The threat actor attempted to compromise an Exchange server, with seven attempts made and prevented by Deep Instinct.
- New malware variants and TTPs related to the threat actor were discovered, including the installation of a root certificate and blending malicious traffic with legitimate traffic.
- Novel tools and techniques used by the threat actor included creating new user accounts with default credentials and setting passwords to never expire.
- The threat actor used evasion techniques to hide malicious domains among legitimate domains, confusing analysts.
- The threat actor's activity dates back to at least 2020, exploiting vulnerabilities such as Fortinet CVE-2018-13379, Exchange ProxyShell, and log4j.
- The threat actor continuously changes payloads and infrastructure, with a focus on automated scanning and exploitation to gain access to vulnerable organizations.
- Deep Instinct's prevention capabilities thwarted the threat actor's attempts to execute payloads in a customer environment.
- Various IOCs and hashes related to the threat actor's activities were identified, showcasing the actor's evolving tactics.
- The report provides detailed insights into the threat actor's operations, highlighting the ongoing threat posed by PHOSPHORUS.





Report 13

Summary:
- Threat actor: Charming Kitten (APT 35)
- Region: Germany
- Operating sector: Iranian dissident organizations and individuals
- Date: August 10th, 2023
- The German intelligence service warned of state-sponsored cyber espionage targeting Iranian dissidents in Germany by Charming Kitten.
- The threat group used sophisticated social engineering techniques and false personas to compromise their targets.
- Charming Kitten has been linked to intelligence-gathering activities rather than financial motivation by various specialist companies.
- The hackers employed tactics like sending links to online chats leading to credential harvesting pages.
- Evidence of capability: Charming Kitten was behind an international cyber espionage campaign targeting Human Rights Watch staff.
- Novelty of tools and techniques: The threat actor used disguised credential harvesting pages and tailored social engineering tactics.
- The threat actor is believed to be linked to the IRGC, with potential threats of kidnapping or killing perceived enemies of the Iranian regime.





Report 14

Summary:
Nation-state threat actors from China, Iran, North Korea, and Turkey have been exploiting the Log4Shell vulnerability (CVE-2021-44228) to gain access to targeted networks, as reported by Microsoft on December 15th, 2021. Known threat actors include Phosphorus from Iran and Hafnium from China, with North Korean and Turkish threat actors also involved. These actors have been observed deploying ransomware and utilizing the vulnerability to attack virtualization infrastructure. Microsoft has also noted initial access brokers using the Log4Shell exploit to sell access to ransomware gangs, potentially leading to a spike in ransomware attacks. The first ransomware operation leveraging Log4Shell, named Khonsari, was identified as a low-effort skidware. Over 60 variations of the Log4Shell exploit have been observed in the wild, with attacks linked to DDoS botnets, crypto-mining operations, and commodity malware.





Report 15

Summary:
- Threat actor named "TunnelVision" is Iranian-aligned and active in the Middle-East and the US.
- Activities linked to ransomware deployment, making them potentially destructive.
- Exploits 1-day vulnerabilities in Fortinet FortiOS, Microsoft Exchange (ProxyShell), and Log4Shell.
- Utilizes tunneling tools like Fast Reverse Proxy Client (FRPC) and Plink.
- Exploited Log4j vulnerability in VMware Horizon to run PowerShell commands, deploy backdoors, harvest credentials, and perform lateral movement.
- Utilizes legitimate services like transfer.sh, pastebin.com, and webhook.site for malicious activities.
- Attribution linked to Microsoft's Phosphorus and confusion with CrowdStrike's Charming Kitten and Nemesis Kitten.
- Indicators of Compromise include domains, IPs, and a Github account used for hosting payloads.
- Date: February 17, 2022.
- Region: Middle-East and US.
- Operating Sector: Not specified.
- Type of Company: Not specified.





Report 16

Summary:
Magic Hound, also known as APT 35, Cobalt Illusion, and Charming Kitten, is an Iranian-sponsored threat group operating in the Middle East since 2014. The threat actor primarily targets organizations in the energy, government, and technology sectors with interests in Saudi Arabia. The group is linked to the Islamic Revolutionary Guard Corps (IRGC) and engages in information theft and espionage. Magic Hound has used a variety of tools like PupyRAT, Mimikatz, and PowerLess Backdoor, showing an evolving toolset. The threat actor has conducted multiple hacking operations, including Operation "Thamar Reservoir" in 2014 and phishing campaigns like PupyRAT in 2017. They have targeted individuals involved in sanctions against Iran, journalists, and high-profile executives. Counter operations have been taken against the threat actor, such as domain takedowns by Microsoft and sanctions by the U.S. Treasury against IRGC-affiliated cyber actors. The threat actor continues to refine its tactics, with recent activities targeting women in human rights and Middle East politics.





Report 17

Summary:
The Magic Hound threat actor, operating primarily in the Middle East since mid-2016, targets organizations in the energy, government, and technology sectors in Saudi Arabia. The threat actor has evolved tactics and techniques, using a diverse toolset across different attack waves. The tools used include IRC bots, Python RATs, and malicious macros in Microsoft Office documents. The adversary group may have a relationship with Rocket Kitten. The Magic Hound campaign does not rely on exploit code but uses social engineering tactics to compromise targets. The threat actor uses custom tools like MagicHound.DropIt, MagicHound.Fetch, MagicHound.Rollover, MagicHound.Retriever, and MagicHound.Leash. The tools exhibit novel capabilities such as creating persistent access, downloading secondary payloads, and executing shellcode-based payloads. The threat actor also uses open-source tools like Pupy RAT. The Magic Hound campaign is an active and persistent espionage adversary with a specific focus on the Middle East region. The threat actor's use of custom and open-source tools, along with social engineering tactics, makes them a significant threat to organizations in the targeted sectors. The latest attacks occurred in the latter half of 2016.





Report 18

Summary:
- Threat actor: Magic Hound, APT 35, Cobalt Illusion, Charming Kitten
- Region: Iran
- Operating sector: Various sectors globally
- Type of company targeted: Large companies, state organizations, education institutes
- Date: May 8, 2023
- Evidence of capability: Iranian state-backed hackers, Mango Sandstorm and Mint Sandstorm, exploiting CVE-2023-27350 in PaperCut MF/NG print management servers
- Novelty of tools and techniques: Exploiting CVE-2023-27350, a pre-authentication critical remote code execution bug, with PoC exploits released and new attack methods bypassing existing detections
- Urgency: Defenders urged to upgrade PaperCut MF and PaperCut NG software to versions 20.1.7, 21.2.11, and 22.0.9 to address the RCE bug and remove the attack vector.





Report 19

Summary:
The threat actor known as Mint Sandstorm, previously tracked as PHOSPHORUS, is an Iranian nation-state actor associated with the Islamic Revolutionary Guard Corps (IRGC). They have refined their tactics, techniques, and procedures (TTPs) to target high-value organizations, particularly in the energy and transportation sectors. Mint Sandstorm has demonstrated the capability to rapidly adopt newly disclosed vulnerabilities and use custom tooling, such as Drokbk and Soldier implants, for persistence and evasion. They have also conducted low-volume phishing campaigns using template injection to target individuals affiliated with high-profile organizations. Recent operations from late 2021 to mid-2022 targeted US critical infrastructure, potentially in response to cyberattacks attributed to Iran. Microsoft has provided mitigation and protection guidance to help organizations defend against Mint Sandstorm's sophisticated capabilities. The report was published on February 14, 2024, by Microsoft Security Blog.





Report 20

Summary:
The threat actor known as Charming Kitten, associated with APT35 and backed by the Iranian government, has been targeting high-risk users with a new data extraction tool called HYPERSCRAPE. This tool, discovered in December 2021, is used to steal user data from Gmail, Yahoo!, and Microsoft Outlook accounts by downloading victims' inboxes using acquired credentials. HYPERSCRAPE is still under active development and has been deployed against fewer than two dozen accounts in Iran. The tool is not notable for its technical sophistication but is effective in accomplishing Charming Kitten's objectives. It requires the victim's account credentials and spoofs the user agent to look like an outdated browser to enable basic HTML view in Gmail. The threat actor's commitment to developing purpose-built capabilities is evident in HYPERSCRAPE. The tool is designed to run on Windows PCs and communicates with a C2 server to relay system information. The report provides technical details on HYPERSCRAPE's operation and highlights Charming Kitten's ongoing efforts to conduct espionage aligned with Iranian government interests. The post emphasizes the importance of sharing research to raise awareness of such threats and improve threat hunting capabilities. Users are encouraged to enroll in Google's Advanced Protection Program for enhanced security. The report was published on August 23, 2022, by Google's Threat Analysis Group.





Report 21

Summary:
The threat actor known as TA453, also referred to as Magic Hound, APT 35, Cobalt Illusion, and Charming Kitten, conducted a sophisticated operation named SpoofedScholars targeting individuals of intelligence interest to the Iranian government. The operation involved masquerading as UK scholars from the University of London's School of Oriental and African Studies (SOAS) since at least January 2021. TA453 used a compromised legitimate website to deliver personalized credential harvesting pages to targets, including experts in Middle Eastern affairs, senior professors, and journalists specializing in Middle Eastern coverage. The threat actor engaged in detailed and extensive conversations with targets before providing links to the credential harvesting pages. This operation showcased an increase in TA453's sophistication compared to previous campaigns, indicating their capability to innovate and collect intelligence in support of Iranian government interests. The operation was attributed to TA453 based on tactics, techniques, and procedures (TTPs) similarities with previous campaigns and consistency with historical targeting patterns. Proofpoint recommends investigating network traffic to the compromised website and being cautious of emails from specific addresses associated with the threat actor. The operation highlights the need for academics, journalists, and think tank personnel to verify the identity of individuals offering unique opportunities and to practice caution in virtual engagements. The operation was detected on July 13, 2021, and Proofpoint has worked with authorities to conduct victim notifications.





Report 22

Summary:
- Threat actor: COBALT MIRAGE, associated with Iranian threat group.
- Region: Iran.
- Operating sector: Technology and cybersecurity-related projects.
- Type of company of victims targeted: Iranian companies linked to COBALT MIRAGE activity.
- Date: June 2022.
- Evidence of capability: Exploited ProxyShell vulnerabilities, deployed web shells, used TunnelFish malware, encrypted servers, and left ransom notes.
- Novelty of tools and techniques: Used TunnelFish, a customized variant of Fast Reverse Proxy, and copied ransom note in PDF format.
- Identified individuals and companies linked to IRGC-IO.
- Operational security failures revealed attribution.
- Recommendations: Validate patching of internet-facing systems to mitigate exposure to COBALT MIRAGE.





Report 23

Summary:
The threat actor known as Phosphorus, also referred to as Charming Kitten or APT35, has been observed increasing their activity, targeting medical research organizations, academic researchers, human rights activists, and the media sector in the US, Israel, France, and the Middle East region. They have exploited Microsoft Exchange Server vulnerabilities, including ProxyShell, to deploy malware on victims' networks. Cybereason researchers discovered a new PowerShell backdoor named PowerLess Backdoor used by Phosphorus, which runs in a .NET context to evade detection. The threat actor also has connections to the Memento Ransomware and has been seen using open-source tools like DiskCryptor and BitLocker. The Phosphorus group operates in the interest of the Iranian regime, engaging in cyber espionage and offensive cyber attacks. Their use of novel tools and techniques, along with the exploitation of fresh vulnerabilities like Log4j, demonstrates their evolving capabilities. The report provides detailed analysis of the PowerLess Backdoor, keylogger, and browser info stealer modules used by Phosphorus, as well as their infrastructure and potential connections to other tools and operations. The threat actor's activities highlight the importance of threat intelligence analysis and the need for defenders to stay vigilant against evolving cyber threats. The Cybereason XDR Platform is capable of detecting and blocking the PowerLess Trojan and other advanced TTPs used by Phosphorus.





Report 24

Summary:
The threat actor known as Ballistic Bobcat, associated with APT35/APT42 (Charming Kitten), targeted entities in Brazil, Israel, and the United Arab Emirates with a novel backdoor named Sponsor. The group, suspected to be Iran-aligned, focuses on education, government, healthcare, human rights activists, and journalists, with activity in Israel, the Middle East, and the United States. The Sponsor backdoor, deployed in September 2021, uses batch files to drop configuration files discreetly, evading detection by scanning engines. At least 34 victims were identified, with a majority in Israel, including various sectors like automotive, healthcare, insurance, law, manufacturing, and technology. The threat actor exploited vulnerabilities in internet-exposed Microsoft Exchange servers for initial access, using a diverse open-source toolset alongside the Sponsor backdoor. The group's scan-and-exploit model continues to target unpatched systems, emphasizing the importance of patching and vigilance for defenders. The report provides detailed technical analysis of the backdoor's capabilities, network infrastructure, and MITRE ATT&CK techniques used by the threat actor. The operation time window spans from September 2021 to December 2021.





Report 25

Summary:
TA453, also known as Magic Hound, APT 35, Cobalt Illusion, and Charming Kitten, has been active since at least late 2020 through 2022, deviating from its typical phishing techniques and target victimology. The threat actor has targeted a wide range of victims, including medical researchers, aerospace engineers, realtors, and travel agencies, using compromised accounts, malware, and confrontational lures. This activity reflects a flexible mandate to the Islamic Revolutionary Guard Corps' (IRGC) intelligence requirements, with a possible directive to support covert and kinetic operations. TA453's outlier campaigns have demonstrated novel techniques such as compromised accounts, malware like GhostEcho, and confrontational lures by personas like Samantha Wolf. The threat actor's aggressive side has been shown in campaigns targeting individuals with threatening messages, indicating possible collaboration with hostile Iranian state-aligned operations. TA453 is assessed to generally operate in support of the IRGC, with moderate confidence that the more aggressive activity could involve collaboration with other branches of the Iranian state. The threat actor's tools, tactics, techniques, and targeting continue to evolve in response to changing priorities, reflecting IRGC intelligence collection requirements and potential support for hostile and kinetic operations. 

Date: December 14, 2022

Region: Global

Operating Sector: Various sectors, including medical research, aerospace, real estate, and travel

Type of Company of Victims: Medical researchers, aerospace companies, real estate agencies, travel agencies, government officials, academics, and military personnel.





Report 26

Summary:
TA453, also known as Magic Hound, APT 35, Cobalt Illusion, and Charming Kitten, deployed a social engineering impersonation technique called Multi-Persona Impersonation in mid-2022. This technique involves using multiple actor-controlled personas on a single email thread to convince targets of the legitimacy of the campaign. TA453 targeted researchers, academics, policymakers, diplomats, journalists, and human rights workers, with a focus on those specializing in Middle Eastern affairs or nuclear security. The threat actor's latest evolution in techniques, such as MPI, requires more resources and a coordinated approach among personas. TA453's campaigns involved sending malicious documents through OneDrive links using remote template injection techniques, dubbed Korg by Proofpoint. The threat actor is assessed to operate in support of the Islamic Revolutionary Guard Corps (IRGC) and continues to evolve its TTPs to gather intelligence. Researchers in international security should remain vigilant when receiving unsolicited emails, especially those related to Middle Eastern studies or nuclear security. The use of MPI by TA453 is expected to evolve further as the threat actor adapts to bypass security detection measures. 

Date: September 13, 2022

Region: Global

Operating Sector: Research, Academia, Policy, Journalism

Type of Company: N/A





Report 27

Summary:
- Threat actor identified as COBALT GYPSY, associated with Iranian government-directed cyber operations.
- Targeted victims in the Middle East and North Africa (MENA) region, focusing on Saudi Arabian organizations in early 2017.
- Used fake persona "Mia Ash" to conduct phishing and social engineering attacks, establishing trust through social media.
- Utilized PupyRAT, an open-source cross-platform remote access trojan (RAT), delivered via macro-enabled Word documents.
- Mia Ash persona created in April 2016, with well-established social media profiles to build rapport with victims.
- COBALT GYPSY managed Mia Ash persona to target telecommunications, government, defense, oil, and financial services organizations.
- Threat actor used LinkedIn to contact employees, encouraging communication via email, WhatsApp, and Facebook to deliver PupyRAT.
- Attribution based on observed activity, TTPs, and connections associated with Mia Ash persona.
- COBALT GYPSY's use of social media for reconnaissance highlights the importance of social engineering training and disabling macros in Microsoft Office products.
- Recommendations include incorporating advanced malware prevention technology and endpoint threat detection tools in security strategies.

Date: Early 2017
Region: Middle East and North Africa (MENA)
Operating Sector: Telecommunications, government, defense, oil, financial services
Type of Company: Affiliated with MENA region
Novelty: Use of fake persona "Mia Ash" for social engineering and delivery of PupyRAT via social media platforms.





Report 28

Summary:
The threat actor known as "Charming Kitten" has been identified by Certfa Lab as an Iranian state-backed hacker group conducting phishing attacks targeting individuals involved in economic and military sanctions against Iran, politicians, civil and human rights activists, and journalists globally. The attackers have shown capability in targeting two-step verification codes and email accounts like Yahoo! and Gmail, emphasizing the use of Security Keys like YubiKey for protection. The attackers have utilized novel techniques such as fake Google Drive file sharing pages hosted on Google Site, fake alerts of unauthorized access, and customized phishing pages for Google and Yahoo! accounts. The threat actor has used a network of domains and IP addresses, including VPNs and proxies with Dutch and French IP addresses to hide their location. The campaign, launched before new U.S. sanctions on Iran, indicates a strategic focus on collecting information from non-Iranian political figures and authorities. Recommendations include using Security Keys for 2-factor authentication and avoiding one-tap login processes. The report provides IOCs for tracking the threat actor's infrastructure. Date: 2018.12.13. Region: Iran. Operating Sector: Economic, military, political, civil, human rights, journalism. Type of Company: N/A.





Report 29

Summary:
The threat actor known as Charming Kitten, also referred to as Threat Actor 453, is linked to Iran's Islamic Revolutionary Guard Corps and operates as a quasi-military cyber espionage organization. They target diplomats, academics, human rights workers, journalists, and government agencies, often using credential harvesting techniques through fake Zoom call invitations. The group has been active for some time and has not significantly changed its operations despite recent events in Iran, such as protests and civil unrest. Charming Kitten leverages previously obtained access to further the state's agenda, demonstrating a high level of sophistication and persistence in their cyber activities. The Iranian government also utilizes cyber surveillance and controls over telecom systems to suppress dissent and monitor communications. Additionally, Iran has a well-developed citizen hacker capability, where individuals align with the government's interests and conduct cyber activities on its behalf. The threat actor's use of novel techniques and tools, such as credential harvesting through fake Zoom calls, showcases their evolving capabilities in the cyber domain. (Date: October 18th, 2022)





Report 30

Magic Hound, also known as APT 35, Cobalt Illusion, and Charming Kitten, has been identified as a threat actor targeting victims in the Middle East region. The victims primarily belong to the government and telecommunications sectors. Evidence suggests that Magic Hound has advanced capabilities, as they have used novel tools and techniques such as the HijackLoader variant to evade detection and enhance persistence. The threat actor has been active as of February 14, 2024, with reports of extensive compromise sought by Volt Typhoon, a failed attempt to revive a botnet, and the release of a Rhysida ransomware decryptor. Magic Hound's activities pose a significant risk to critical infrastructure and highlight the importance of cybersecurity measures in the face of evolving threats.


