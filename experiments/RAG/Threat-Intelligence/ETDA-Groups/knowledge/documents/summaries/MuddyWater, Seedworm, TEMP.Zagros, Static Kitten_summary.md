
Report 1

Summary:
The threat actor identified as MuddyWater, Seedworm, TEMP.Zagros, Static Kitten, is linked to Iranian intelligence activities and has been targeting networks globally. The group has been using open-source tools to maintain access to victim networks, with a focus on Middle Eastern, European, and North American nations. The threat actor leverages malware techniques such as side-loading DLLs and obfuscating PowerShell scripts to hide command and control functions. New samples of the tools used by the threat actor have been identified, including PowGoop instances and JavaScript files for establishing connections to malicious infrastructure. The threat actor's capabilities include espionage and ransomware activities, with the use of different naming conventions to avoid detection. The presence of these tools on a network may indicate the presence of Iranian malicious cyber actors. The report was published on January 12, 2022, by the U.S. Cyber Command's Cyber National Mission Force.





Report 2

Summary:
- Threat actor: MuddyWater, Seedworm, TEMP.Zagros, Static Kitten
- Region: Middle East, Asia, Africa, Europe, North America
- Operating sector: Telecommunications companies, governmental organizations, oil & gas, energy verticals
- Novelty of tools and techniques: MuddyWater used SimpleHelp as a legitimate remote access tool to compromise victims, deployed Ligolo reverse tunnel, MiniDump, CredNinja, and a new version of password dumper MKL64, utilized steganography to obfuscate data in digital media, and leveraged VBA/TrojanDownloader.Agent in malicious documents
- Date: Campaign started in Q4 2022, with specific incidents in October 2022
- Evidence of capability: Successful obfuscation of C&C servers, use of popular MSP tools like ConnectWise, and ongoing deployment of custom reverse tunneling tools
- Importance of visibility for MSPs and enterprises in countering threats like APT groups
- Call to action for MSPs to enhance security measures and utilize XDR tools for better threat detection and response.





Report 3

Malformed report.





Report 4

Malformed report.





Report 5

Earth Vetala MuddyWater, also known as TEMP.Zagros, Static Kitten, and Seedworm, has been targeting organizations in the Middle East and neighboring regions. The threat actor uses spearphishing emails with embedded links to distribute malicious packages, including legitimate remote admin tools like ScreenConnect and RemoteUtilities. The campaign, named Earth Vetala, has been ongoing in 2021 and targets countries like the United Arab Emirates, Saudi Arabia, Israel, and Azerbaijan. The threat actor's capabilities include downloading post-exploitation tools, such as password/process-dumping utilities and custom backdoors, to establish persistence in targeted hosts. The threat actor also uses obfuscated PowerShell scripts for communication with command-and-control infrastructure. The campaign shows evidence of targeting government agencies, academia, and tourism sectors. The threat actor's technical skills are notable, but they have shown some lack of expertise in using all tools correctly. The campaign's footprint extends to multiple countries in the Middle East, and the threat actor's activities align with interests related to Iran. The campaign's tools and techniques are novel, including the use of legitimate remote admin tools for malicious purposes. The threat actor's persistence mechanisms and post-exploitation activities demonstrate a high level of sophistication. The campaign's indicators of compromise include file names, SHA-256 hashes, and network addresses associated with the malicious activities. The threat actor's tactics align with MITRE ATT&CK techniques related to initial access, execution, persistence, privilege escalation, discovery, credential access, command and control, and defense evasion. The campaign represents a significant threat to organizations in the Middle East region.





Report 6

Summary:
A new strain of malware hosted on GitHub has been discovered that uses Word files with macros to download a PowerShell script from GitHub, which in turn downloads an image from Imgur to decode a Cobalt Strike script on Windows systems. Researchers have linked this malware to MuddyWater, a government-backed APT group targeting Middle Eastern entities. The malware uses steganography to hide the payload within the image, a novel technique. The decoded script executes a Cobalt Strike payload, allowing attackers to remotely control compromised devices. The malware emerged around December 2020, taking advantage of the holiday season to evade detection. Security researcher Florian Roth has added IOCs associated with this malware to MuddyWater IOCs list. The use of legitimate services like GitHub and Imgur for hosting malicious code is not uncommon.





Report 7

Malformed report





Report 8

Summary:
Iranian government-sponsored threat actor group MuddyWater, also known as Seedworm, TEMP.Zagros, and Static Kitten, has been conducting cyber espionage and malicious operations targeting government and private-sector organizations globally since 2018. The victims include sectors such as telecommunications, defense, local government, and oil and natural gas in Asia, Africa, Europe, and North America. MuddyWater, a subordinate element of the Iranian Ministry of Intelligence and Security, uses publicly reported vulnerabilities, open-source tools, and tactics like side-loading DLLs and obfuscating PowerShell scripts to gain access to victim networks and deploy ransomware. The threat actor group has been observed using various malware variants like PowGoop, Small Sieve, Canopy, Mori, and POWERSTATS. The group also exploits unpatched vulnerabilities like CVE-2020-1472 and CVE-2020-0688. The report provides detailed technical information on the tools, techniques, and procedures used by MuddyWater, along with indicators of compromise and mitigation strategies. The report was last revised on February 24, 2022.





Report 9

The report details the activities of the Iranian threat group TEMP.Zagros, also known as MuddyWater, in a spear phishing campaign observed from January 2018 to March 2018. The threat actor targeted government and defense entities in Central and Southwest Asia with malicious macro-based documents containing geopolitical themes. The threat actor utilized the latest code execution and persistence techniques, including the re-use of an AppLocker bypass and lateral movement techniques for indirect code execution. The campaign involved two parts with a shift in tactics, techniques, and procedures after about a month. The threat actor leveraged INF and SCT files for indirect code execution to evade security products. The report provides a detailed analysis of the malware's capabilities, including encryption, decryption, data retrieval, and interaction with the command and control server. The threat actor demonstrated the ability to quickly update their malware with novel techniques, making it challenging for security products to detect. The report includes indicators of compromise and network indicators for further investigation.





Report 10

Summary:
- Threat actor: MuddyWater, Seedworm, TEMP.Zagros, Static Kitten
- Date: April 2023
- Region: Iran
- Operating sector: Hybrid environments, on-premises, and cloud environments
- Type of company targeted: Not specified
- Evidence of capability: Destructive operations by MERCURY, a nation-state actor linked to the Iranian government, in partnership with DEV-1084. DEV-1084 used highly privileged compromised credentials to perform mass destruction of resources in both on-premises and cloud environments.
- Novelty of tools and techniques: DEV-1084 used known vulnerabilities in unpatched applications for initial access, extensive reconnaissance, and discovery, and leveraged tools like Rport, Ligolo, and a customized PowerShell script backdoor. They also abused OAuth applications for malicious activities in the cloud.
- Tools and techniques used: Web shells, remote access tools, PowerShell backdoors, credential theft, lateral movement, scheduled tasks, WMI, remote services, SSH tunneling, tampering with security tools, ransomware deployment, and email impersonation.
- Mitigations: Recommendations for securing on-prem and Azure AD environments, and detection details for Microsoft 365 Defender, Microsoft Defender for Cloud Apps, Azure AD Identity Protection, Microsoft Defender for Identity, Microsoft Defender Antivirus, and Microsoft Defender for Endpoint.





Report 11

Summary: Iranian state-backed hacking groups, Mango Sandstorm and Mint Sandstorm, have been observed exploiting the CVE-2023-27350 vulnerability in PaperCut MF/NG print management servers. The attacks are opportunistic and target organizations across sectors and geographies. The threat actors have been linked to Iran's Ministry of Intelligence and Security and Islamic Revolutionary Guard Corps. The vulnerability allows for pre-authentication critical remote code execution and has been used by ransomware gangs like Clop and LockBit. Security researchers have released PoC exploits for the bug, and a new attack method has been identified that can bypass existing detections. Defenders are advised to upgrade their PaperCut software to versions 20.1.7, 21.2.11, and 22.0.9 to mitigate the risk. The attacks have been ongoing since May 5, 2023, and continue to pose a threat to large companies, state organizations, and educational institutes globally.





Report 12

Summary:
- Threat actor: MuddyWater, Seedworm, TEMP.Zagros, Static Kitten, also known as MERCURY
- Region: Middle East
- Operating sector: NGOs, intergovernmental organizations, government humanitarian aid, human rights organizations, network technology providers
- Evidence of capability: Exploiting Zerologon vulnerability, targeting high number of refugee-related organizations, incorporating public exploits into attacker playbooks
- Novelty of tools and techniques: Utilizing Zerologon bug, weaponized proof-of-concept code, incorporating exploits into playbooks
- Date: Attacks began after public Zerologon PoC, with first exploitation attempts detected around the same time as proof-of-concept code publication.





Report 13

Summary:
- Threat actor: MuddyWater, Seedworm, TEMP.Zagros, Static Kitten
- Region: Israel, Jordan, Iraq, and potentially Israel
- Operating sector: Various, including a Jordanian company, an Iraqi telecommunications provider, and Israeli targets
- Date: Activities observed from July 2023 to October 2023
- Evidence of capability: MuddyWater suspected to have used a new C2 framework called MuddyC2Go since at least 2020, with changes in TTPs including password-protected archives and new executables for connecting to C2 servers
- Novelty of tools and techniques: MuddyWater shifted from PhonyC2 to MuddyC2Go, a Go-based C2 framework, with unique URL patterns and PowerShell payloads, indicating sophistication and adaptability
- Conclusion: Recommendations include disabling unnecessary PowerShell and close monitoring, as MuddyC2Go generates PowerShell payloads for executing objectives in the Cyber Kill Chain. Deep Instinct identified active MuddyC2Go servers and associated IOCs for tracking and mitigation efforts.





Report 14

MuddyWater, Seedworm, TEMP.Zagros, and Static Kitten are threat actors associated with state-sponsored cyber espionage activities originating from Iran. They have been active since at least 2017, targeting victims primarily in the Middle East and Central Asia, with a focus on governments, telcos, and oil companies. The threat actors use advanced tools and techniques, such as in-memory vectors leveraging Powershell and "Living off the land" attacks to maintain a low detection profile. They have targeted victims in various sectors, including defense, education, energy, finance, government, healthcare, and telecommunications, across multiple countries. The threat actors have been linked to various hacking operations, with new campaigns and evolving tactics observed over the years. Counter operations have been reported against these threat actors, including leaks of their cyber-espionage activities. The threat actors continue to pose a significant risk to organizations in the targeted regions.





Report 15

MuddyWater, a threat actor group, launched a new social engineering campaign against Israeli targets during the Israel-Hamas war. The campaign utilized updated Tactics, Techniques, and Procedures (TTPs) including a new file-sharing service called "Storyblok" to host archives containing a multi-stage infection vector. The campaign involved spear-phishing emails that led victims to download malicious archives containing hidden files and an LNK file that initiated the infection process. The threat actor used a legitimate remote administration tool called "Advanced Monitoring Agent" to gain access to infected hosts. This campaign marked the first public report of MuddyWater using this specific remote administration tool. The threat actor continued to target Israeli entities with advanced TTPs, showcasing their capability to adapt and evolve their techniques. The report also mentioned the use of a new Command and Control (C2) framework named MuddyC2Go by MuddyWater, indicating their ongoing development of novel tools and techniques. The operation time window was not specified in the report.





Report 16

Summary:
MuddyWater, a relatively new APT group, has expanded its operations since 2017, targeting governmental entities in Iraq and Saudi Arabia, as well as other countries in the Middle East, Europe, and the US. The group has recently increased spear-phishing attacks on government bodies, military entities, telcos, and educational institutions in Jordan, Turkey, Azerbaijan, and Pakistan. The attacks involve social engineering to enable macros and utilize a range of compromised hosts for delivery. The group's toolkit includes advanced PowerShell code for CnC communication, victim system reconnaissance, and various supported commands. The attackers have made OPSEC mistakes, revealing potential attribution clues. The attacks are ongoing, with victims in multiple countries. The group is actively developing new methods and techniques to evade security products. Kaspersky Lab predicts intensified attacks in the future and recommends implementing security measures to protect against such threats.





Report 17

Summary:
Between February and October 2017, a threat actor named "MuddyWater" conducted targeted attacks primarily in the Middle East, with additional targets in India and the USA. The attacks involved the use of a slowly evolving PowerShell-based first-stage backdoor called "POWERSTATS". The threat actor utilized tools like Meterpreter, Mimikatz, Lazagne, and Invoke-Obfuscation, with some of their recent attack documents hosted on GitHub. The attackers also compromised third-party organizations to send malicious documents to further targets. Despite previous attributions to the FIN7 threat actor group, the research suggests that the MuddyWater attacks are espionage-related and distinct from FIN7 activity. The report highlights the challenges in attributing attacks and emphasizes the importance of independent analysis. The threat actor's infrastructure and malicious documents have been identified and blocked by Palo Alto Networks' security measures.





Report 18

Summary:
- Threat actor: MuddyWater, also known as Static Kitten and Mercury, likely affiliated with Iran's Ministry of Intelligence and Security.
- Operating region: Middle East, Asia, Africa, Europe, and North America.
- Operating sector: Government and private organizations in telecommunications, local government, defense, oil, and natural gas.
- Novelty of tools and techniques: MuddyWater utilized legitimate remote administration tools like RemoteUtilities, ScreenConnect, and Syncro in spearphishing campaigns.
- Date of operation: Campaign observed in October 2022, possibly starting in September.
- Evidence of capability: MuddyWater targeted countries like Armenia, Azerbaijan, Egypt, Iraq, Israel, Jordan, Oman, Qatar, Tajikistan, and United Arab Emirates.
- Targeted victims: Egyptian hosting company and Israeli hospitality industry.
- Tools used by threat actor: Syncro, a remote administration tool, was a new addition to MuddyWater's arsenal.
- Tactics observed: Spearphishing with links to archives hosted on platforms like Dropbox, OneDrive, and OneHub.
- Recommendations: Security teams advised to monitor for uncommon remote desktop solutions.





Report 19

MuddyWater, a cyber espionage group affiliated with the Iranian Ministry of Intelligence and Security, has been identified using a new custom-made C2 framework named PhonyC2 since at least 2021. The framework was used in an attack on the Technion Institute and is currently active in a PaperCut exploitation campaign. PhonyC2 is continuously updated by MuddyWater to evade detection, with evidence linking it to previous attacks and infrastructure used by the threat actor. The framework utilizes social engineering for initial access and employs PowerShell activity to infect systems. PhonyC2 is structurally similar to MuddyC3, a previous framework by MuddyWater, and shows capabilities for persistence, command execution, and data encoding. The threat actor's use of novel tools and techniques, along with the evolving nature of PhonyC2, demonstrates their advanced capabilities and adaptability in cyber operations. The report provides detailed analysis of the framework's code, server infrastructure, and indicators of compromise, highlighting the ongoing threat posed by MuddyWater. (Date: June 29, 2023)





Report 20

Summary:
A potential MuddyWater campaign targeting organizations in Turkey, Pakistan, and Tajikistan has been detected in the Middle East. The threat actor, known for espionage activities, has similarities with previous MuddyWater campaigns. The attackers use decoy documents mimicking government organizations and employ obfuscation techniques in their tools. The campaign utilizes malicious delivery documents in the Tajik language to target government organizations and telecommunication companies. The malware drops obfuscated Visual Basic and PowerShell scripts for persistence and backdoor functionality. Communication with the command-and-control server is done via XML messages with supported action commands. Trend Micro solutions like Deep Discovery and Email Security can help mitigate such threats. Indicators of compromise include hashes and scriptlets related to applocker bypass. The threat actor is actively monitoring connections to the C&C server, indicating a sophisticated operation.





Report 21

Summary:
The report discusses a potential MuddyWater campaign that uses a PRB-Backdoor, targeting victims through malicious Word documents with embedded macros. The threat actor, MuddyWater, was first sighted in 2017 targeting the Saudi government and has since evolved its techniques. The new samples encode PowerShell scripts within the document itself, avoiding direct downloads. The backdoor payload, PRB-Backdoor, communicates with a Command-and-Control server for various commands. The threat actor behind MuddyWater continues to evolve tools and techniques, making them more effective and persistent. Countermeasures include user awareness and solutions like Trend Micro™ Deep Discovery™ and Hosted Email Security. The report provides technical details, indicators of compromise, and countermeasures against such targeted attacks. Date: May 2018. Region: Global. Operating Sector: Various industries. Type of Company: Not specified.





Report 22

Summary:
- Threat actor: Probable Iranian Cyber Actors, Static Kitten
- Region: Middle East, specifically targeting UAE and Kuwait Government Agencies
- Operating sector: Government agencies
- Date: February 10, 2021
- Evidence of capability: Utilizing ScreenConnect Remote Access Tool with custom launch parameters targeting MOFA, using Ministry of Foreign Affairs-themed files and URLs
- Novelty of tools and techniques: Masquerading as legitimate government documents, utilizing Onehub file storage service for malicious purposes, targeting government employees with geopolitical-themed lures
- TTPs: Masquerading, Phishing, Remote Access Software, Spearphishing Attachment, User Execution
- IOCs: IP addresses, URLs, hashes of malicious files
- Conclusion: Static Kitten likely focused on cyberespionage for data theft from government agencies. Ongoing monitoring for further malicious activity.





Report 23

Summary:
A suspected Iranian state-sponsored threat actor, likely ITG17 or 'MuddyWater,' targeted an unnamed Asian airline in 2019 to steal flight reservation data using a newly discovered backdoor named 'Aclip' that abuses the Slack API for covert communications. The threat actor's capability was evidenced by the use of the Aclip backdoor, which establishes persistence on infected devices, exfiltrates data, and receives commands via Slack API functions. The novelty of the tools and techniques used by the threat actor included the abuse of Slack for malicious communications, with IBM researchers linking the attack to MuddyWater/ITG17 based on custom malware samples. The threat actor's activity was detected in March 2021, prompting Slack to shut down reported workspaces used for malicious purposes. IBM recommended strengthening PowerShell security measures to defend against similar attacks, highlighting the evolving nature of messaging application abuse by malicious actors. Date: December 15, 2021. Targeted victims: Asian airline.


