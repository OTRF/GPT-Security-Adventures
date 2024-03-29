
Report 1

Malformed report





Report 2

Summary:
- Threat actor: Mallard Spider
- Region: United States
- Operating sector: Various, including healthcare, construction, finance, legal, US government agencies, and industrial entities
- Type of company targeted: Organizations around the world
- Capability: Mallard Spider, operating as ProLock ransomware, has been stealing data from compromised networks before encrypting systems, with ransoms ranging from $175,000 to over $660,000.
- Novelty of tools and techniques: Mallard Spider partners with the QakBot banking trojan gang, uses phishing emails with malicious attachments, stolen credentials, and exploits system configuration flaws to breach systems.
- Date: FBI issued a second alert on September 1, 2020, following a previous alert on May 4, 2020.
- Recommendation: FBI advises affected organizations not to pay ransoms, report attacks to the FBI field office, back up data offline, keep software updated, use two-factor authentication, disable unused RDP instances, and disable automatic attachment downloads in email clients.





Report 3

Summary: The FBI issued a warning about the ProLock ransomware decryptor not working properly, affecting organizations in sectors such as healthcare, government, financial, and retail in the US. The decryptor malfunction results in data loss, especially for files larger than 64MB. ProLock, previously known as PwndLocker, partners with the QakBot banking trojan to gain access to victim networks, escalating its activity since March. The threat actor targets high-value systems and important data for encryption, demanding ransom amounts ranging from $175,000 to over $660,000. ProLock operators ensure no file recovery options are left without payment, using methods like deleting or encrypting backups and volume shadow copies. The threat actor's use of novel techniques, such as extracting payloads from image files and siphoning data using command-line tools, demonstrates their capability and sophistication. Date: May 18, 2020.





Report 4

Summary:
The threat actor Mallard Spider, also known as Gold Lagoon, has been active since 2008 and has evolved to distribute various malware, including ProLock ransomware, through phishing techniques. They have been observed using tools like Egregor, Mimikatz, and QakBot, with reported hacking operations targeting various sectors and countries. Mallard Spider's motivation is financial gain, and they have been involved in ransomware attacks like PwndLocker rebranding to ProLock. The threat actor has shown capability in partnering with other ransomware like Egregor and using novel techniques such as infecting victims through Windows Defender Antivirus phishing bait. The latest report in 2021 highlights their continued activity and evolving tactics.





Report 5

Summary: ProLock Ransomware, in collaboration with QakBot trojan, targeted businesses and local governments, demanding high ransoms for file decryption. The threat actor, operating in the region of Diebold Nixdorf, a company known for ATMs, utilizes novel techniques similar to high-profile ransomware groups like Sodinokibi and Maze. ProLock gains access through QakBot distribution and public-facing RDP servers, using PowerShell and malicious macros for payload execution. The threat actor exfiltrates data using cloud storage services and encrypts files with unique extensions. The report provides insights into ProLock's tactics, techniques, and procedures, aiming to enhance defense strategies against this threat actor. Date: May 14, 2020.





Report 6

Summary: ProLock ransomware, operated by Mallard Spider, has increased payment demands and victim count targeting enterprise networks in Europe and North America. The threat actor rebranded from PwndLocker and demands ransoms ranging from $175,000 to over $660,000, with recent averages reaching $1.8 million. Mallard Spider utilizes simple yet effective tactics, partnering with QakBot banking trojan to map networks, move laterally, and deploy ransomware. The threat actor employs novel techniques such as large VBScripts to deliver QakBot and tools like Bloodhound and ADFind for profiling environments. ProLock's toolkit includes Mimikatz and exploits Windows vulnerability (CVE-2019-0859) for privilege escalation. Despite using standard tools, ProLock attacks remain largely undetected, allowing for data theft and file encryption. The FBI has issued alerts regarding this threat actor, warning of potential data loss with the decryption tool. Group-IB has not verified this claim as none of their customers paid the ransom. (Source: Bleeping Computer, Date: September 10, 2020)





Report 7

Summary: The threat actor known as Mallard Spider, previously operating as PwndLocker, rebranded as ProLock Ransomware after fixing a crypto bug that allowed for a free decryptor. The ProLock Ransomware targets corporate networks and is distributed through a BMP image file named WinMgr.bmp. The threat actor uses steganography to hide the ransomware executable within the image file, evading detection by security software. The encryption method used by ProLock is similar to PwndLocker, encrypting files and appending the extension .proLock. Victims are instructed to pay a ransom in BTC for decryption, with ransom amounts assigned to each victim. The threat actor has fixed the encryption flaw that allowed for free decryption, making recovery from backups necessary for victims. The operation time window for this threat actor is ongoing, with evidence of targeting corporate networks. 

Date: Ongoing operation.





Report 8

Summary:
The threat actor Mallard Spider, also known as QBot malware, has been observed replacing IcedID in malspam campaigns targeting victims in the banking sector. The threat actor has demonstrated the capability to switch between trojans, with QBot and IcedID often serving as intermediary stages in longer infection chains leading to ransomware attacks. Evidence suggests that the threat actor is utilizing updated XLM macros to deliver the payload, posing as legitimate documents like DocuSign to deceive users. Additionally, the threat actor has been associated with the use of EtterSilent, a malicious document builder that bypasses security mechanisms. The switch back to QBot indicates a significant update to the malware, with changed decryption algorithms for internal configuration, disrupting extraction efforts. The novelty of the tools and techniques used by Mallard Spider, along with their adaptability in rotating payloads, poses a significant threat to organizations in the targeted sectors. (Date: April 13, 2021)





Report 9

Summary:
The threat actor Mallard Spider, also known as QBot, has shifted from distributing ProLock ransomware to partnering with Egregor ransomware in bot-fueled attacks. QBot targets victims through phishing emails, stealing bank and Windows domain credentials, and providing remote access to threat actors. Egregor, active since September 2020, has quickly amassed victims worldwide, with a focus on the Manufacturing and Retail sectors. The tactics, techniques, and procedures (TTPs) used by Egregor are similar to previous attacks with ProLock, indicating a shift in ransomware operations. Security professionals are advised to monitor for CobaltStrike and QakBot when defending against Egregor. The threat landscape continues to evolve as threat actors form new partnerships, making it crucial for security professionals to stay informed and adapt their defenses accordingly.





Report 10

Summary: The threat actor Mallard Spider, also known as QBot, has been using US election-themed phishing emails to target victims with malicious payloads since at least 2009. The phishing emails are disguised as replies in stolen email threads to add legitimacy. The threat actor leverages public concerns about the 2020 US elections to lure victims into opening malicious Excel attachments. Once infected, the QBot malware steals data, logs keystrokes, deploys backdoors, and drops additional malware. The threat actor has been using aggressive tactics such as exploit kits, network share exploits, and brute-force attacks targeting Active Directory admin accounts. While primarily targeting corporate entities for a higher return on investment, the threat actor has also been involved in targeted attacks against customers of US financial institutions. The report provides indicators of compromise and details on the techniques and malware samples used in the QBot campaign. 

Date: November 4, 2020

Region: USA

Operating Sector: Financial institutions, corporate entities

Type of Company: Financial institutions, hospitality industry

Capability of Threat Actor: QBot has been active since at least 2009, using sophisticated phishing tactics, exploit kits, and aggressive brute-force attacks. The threat actor has the capability to steal data, log keystrokes, deploy backdoors, drop additional malware, and conduct targeted attacks against financial institutions and corporate entities.

Novelty of Tools and Techniques: The threat actor's use of US election-themed phishing emails, stolen email threads, malicious Excel attachments, exploit kits, network share exploits, and brute-force attacks targeting Active Directory admin accounts demonstrate a high level of sophistication and innovation in their tactics.





Report 11

Summary: Mallard Spider, also known as QBot or QakBot, has been using a new phishing bait technique involving a fake Windows Defender Antivirus theme to infect PCs. The malware steals bank credentials, Windows domain credentials, and provides remote access to threat actors for ransomware installation. Victims are targeted through malicious Excel attachments in spam emails, prompting them to enable macros to install the QBot malware. The threat actor switched to a new template on August 25th, pretending to be an alert from Windows Defender Antivirus. This tactic aims to trick users into enabling macros that download and install the Emotet malware. The use of convincing document templates makes it essential for users to recognize and avoid QBot attachments to prevent infection. The threat actor's capability to evolve their phishing techniques and use novel tactics like fake antivirus alerts poses a significant risk to organizations and individuals. 

Date: October 12, 2020

Region: Global

Operating Sector: Various industries targeted through phishing emails

Type of Company: Companies across different sectors targeted for credential theft and ransomware installation.





Report 12

Summary:
The threat actor Mallard Spider, also known as Qbot, has recently switched to a new stealthy Windows autostart method to evade detection by anti-malware solutions and security researchers. The malware, active since at least 2009, is a Windows banking trojan used for stealing banking credentials, personal information, and financial data. Victims have been targeted through phishing emails with Excel document attachments. The new persistence mechanism involves adding a registry Run key right before system shutdown and removing it upon system restart or wake-up. This technique, although novel for Qbot, has been used by other malware families like Gozi and Dridex. Additionally, Qbot has updated its installation technique by combining the malware loader and bot within a single DLL and switching to a new in-registry encrypted config. The threat actor's capability to adapt and innovate with new tools and techniques poses a significant risk to organizations. (Source: https://www.bleepingcomputer.com/news/security/qbot-malware-switched-to-stealthy-new-windows-autostart-method/)





Report 13

Summary:
- Threat actor: Mallard Spider
- Date: August 27, 2020
- Region: Global
- Operating sector: Various
- Type of company targeted: Not specified
- Capability: Mallard Spider, also known as Qbot, is a banking and information-stealing malware that has been active for over a decade. It steals email threads to use in malicious spam campaigns, downloads and installs other malware, and targets Active Directory admin accounts.
- Novelty of tools and techniques: Mallard Spider uses stolen email threads in reply-chain phishing attacks, containing ZIP attachments with malicious VBS scripts. It has added unusual capabilities and a method to evade detection by assembling itself from two encrypted halves.
- Evidence of capability: Mallard Spider has been used in highly targeted campaigns against enterprise entities, with infrequent but impactful attacks observed over the years. It has been linked to the Emotet gang and has been active in recent campaigns targeting various industries.





Report 14

Summary:
In May 2020, the threat actor "Mallard Spider" targeted Diebold Nixdorf, a major provider of ATMs and payment technology, with a ransomware attack. The attack disrupted some operations but did not affect ATMs or customer networks, only the corporate network. Diebold did not pay the ransom demanded by the attackers, who used the ProLock ransomware, a relatively uncommon strain. The attackers typically demanded six-figure ransoms. The attack was detected on April 25, and Diebold's response affected services for over 100 customers. The attackers gained access through a phishing email. The incident highlights the ongoing challenge of cybercrime for companies and the need for enhanced security measures.


