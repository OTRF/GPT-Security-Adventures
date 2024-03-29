
Report 1

Summary:
- Threat actor identified as Lorec53, an active Russian hack group, launched phishing attacks against the Georgian government in July 2021.
- Phishing documents in Georgian language were used to deliver a secret-stealing Trojan targeting specific victims to steal various documents.
- Correlation analysis links this attack to an earlier phishing attack against the Ukrainian government, suggesting a Russian hacker composition.
- Lorec53 utilized a large number of network resources located in Russia from April to July 2021.
- The phishing campaign involved the creation of decoy files related to current political hotspots in Georgia.
- Malicious macros in the phishing documents executed a C# Dropper Trojan, which then downloaded and executed an AutoIt Stealer Trojan.
- The AutoIt Stealer Trojan was customized to steal various document types and upload them to a specified network location.
- The attacker used similar techniques in attacks against the Ukrainian government, indicating a pattern of behavior.
- The attacker's infrastructure and historical activities suggest a high level of activity and control over attack resources in the Russian network domain.
- The attacker's technical level is reflected in the use of known generation tools rather than self-developed components.

Date: July 2021
Region: Georgia
Operating Sector: Government
Type of Company: N/A

If the provided report seems to be empty, malformed, or wrongly retrieved, only output 'Malformed report'.





Report 2

Summary:
- Threat actor: UAC-0056 (AKA UNC2589, TA471)
- Region: Ukraine
- Operating sector: Government entities
- Date: July 13, 2022
- The threat actor targeted Ukraine through phishing campaigns related to the ongoing war and humanitarian disaster.
- They used macro-based documents with changing themes but similar techniques.
- Novelty: They used a Cobalt Strike payload with HTTPS beacon, unique port, sleep time, and public key.
- The payload established persistence, dropped files, and executed PowerShell commands.
- The threat actor probed the sandbox and sent reconnaissance commands to the victim's machine.
- Attribution to UAC-0056 was based on CERT UA reports and similarities in tactics.
- Malwarebytes users were protected against this campaign.





Report 3

Summary:
- Threat actor known as EMBER BEAR (aka UAC-0056, Lorec53, Lorec Bear, Bleeding Bear, Saint Bear) has been targeting government and military organizations in eastern Europe since early 2021.
- EMBER BEAR is motivated to weaponize access and data obtained during intrusions to support information operations aimed at creating public mistrust in targeted institutions and degrading government ability to counter Russian cyber operations.
- CrowdStrike Intelligence attributes destructive activity against Ukrainian networks using the WhisperGate wiper to EMBER BEAR with moderate confidence.
- EMBER BEAR's operations are assessed to support data leak operations conducted by multiple attribution fronts.
- EMBER BEAR does not have known links with previously tracked adversaries and is not currently attributed to a specific Russian organization.
- The threat actor's target profile, assessed intent, and technical tactics, techniques, and procedures (TTPs) are consistent with other GRU cyber operations.
- CrowdStrike Intelligence provides confidence descriptions for their assessments: High Confidence, Moderate Confidence, and Low Confidence.
- The threat actor's capabilities and novel techniques pose a significant risk to organizations in the region.
- Date of the report: March 30, 2022.
- Operating sector and type of company of victims targeted: Government and military organizations in eastern Europe.





Report 4

Malformed report





Report 5

Summary:
- Threat actor "SaintBear, Lorec53" targeted organizations in Ukraine, primarily energy and government sectors.
- The attack involved spear phishing emails with social engineering themes, such as criminal accusations or fake resumes.
- The attack used malicious payloads, including the document stealer OutSteel and downloader SaintBot.
- The threat actor's primary goal was data exfiltration from critical infrastructure organizations.
- The tools used, OutSteel and SaintBot, were designed for data collection and persistent access to compromised systems.
- The threat actor used various social engineering themes and infection chains to compromise systems.
- The attack vector was primarily email-based, with different infection chains used in each attack.
- The threat actor leveraged Discord's content delivery network for hosting malicious payloads.
- The attack campaign dates back to at least March 2021, targeting various organizations in Ukraine and Georgia.
- The threat actor's use of novel tools and techniques, along with evolving social engineering themes, indicate a sophisticated and persistent threat actor.





Report 6

Summary:
The threat actor known as SaintBear, also identified as Lorec53, has been active since 2021, with evidence of targeting victims in sectors such as Energy, Financial, Government, Media, and Transportation in countries like Georgia, Ukraine, and the USA. The group has been linked to phishing campaigns aimed at stealing sensitive information, with a focus on political hotspots in Georgia. The threat actor has been attributed to Russian hackers and has used a variety of tools such as Cobalt Strike, Graphiron, and SaintBot. The group's activities have been reported in various hacking operations, including spear phishing attacks and the deployment of new malware like Graphiron. The motivation behind their actions appears to be information theft and espionage. The threat actor's capabilities and novel techniques have been a cause for concern, leading to counter operations by security agencies and organizations.





Report 7

Summary: Ukraine's CERT has issued a warning about threat actors distributing fake Windows antivirus updates containing Cobalt Strike and other malware. The phishing emails impersonate Ukrainian government offices and prompt recipients to download "security updates" from a French website, leading to the installation of malicious executables. The malware chain includes GraphSteel and GrimPlant backdoors, both written in GO with capabilities for network reconnaissance, command execution, and file operations. The threat actor, identified as UAC-0056 or "Lorec53," is a Russian-speaking APT group targeting Ukrainian organizations. The tools used in this campaign demonstrate advanced capabilities and evasion techniques, highlighting the sophistication of the threat actor. (Date: March 15, 2022)


