
Report 1

Summary:
The threat actor known as TA516 has been identified in a recent AZORult campaign that utilizes a novel triple-encryption technique to evade detection. The campaign, observed in February 2020, targets victims through malspam emails containing malicious attachments with three layers of encryption. The use of a triple-encrypted AZORult downloader distinguishes this campaign, with the malware being popular on Russian forums and previously associated with a hacker linked to singer-songwriter Drake. The threat actor employs various obfuscation techniques, including abusing the "\objupdate" mechanism in RTF files and memory patching to bypass security measures. The campaign demonstrates a high level of sophistication in its use of Word, Excel, PowerShell, and three layers of encryption, posing a challenge for signature and heuristics-based detection tools. Despite the complexity of the attack, the effectiveness of the payload in avoiding detection remains uncertain.





Report 2

Summary:
- Threat actor "TA516" conducted a campaign spreading AZORult malware disguised as a fake ProtonVPN installer for Windows.
- The campaign started in November 2019 and used a fake ProtonVPN website to distribute the malware.
- The threat actor registered a domain protonvpn[.]store in Russia for this campaign.
- Victims were infected through malvertising on counterfeit websites.
- Once installed, the malware collected machine information and communicated with a C2 server.
- The malware was designed to steal cryptocurrency, FTP logins, email credentials, browser information, and more.
- Samples associated with the campaign were identified with MD5 hashes.
- Kaspersky products detect this threat as HEUR:Trojan-PSW.Win32.Azorult.gen.
- The threat actor demonstrated capability in data theft, cryptocurrency theft, and malvertising.
- The use of a fake ProtonVPN installer and the malware's capabilities indicate a novel approach by the threat actor.





Report 3

Malformed report.





Report 4

Summary:
- Threat actor "TA516" conducted a new AZORult campaign that abused a popular VPN service to steal cryptocurrency.
- The campaign started in November 2019 and is ongoing, targeting personal information and cryptocurrency from infected users.
- AZORult is a widely used Trojan stealer with capabilities to collect various data, posing a serious threat to infected devices.
- The threat actor created a phishing copy of a VPN service's website to distribute the malware.
- The attackers spread links to the fake website through advertisements, leading victims to download a fake VPN installer that drops the AZORult botnet implant.
- Once implanted, AZORult collects information and steals cryptocurrency from wallets, FTP logins, email credentials, and more.
- Kaspersky detected and informed the VPN service about the issue, recommending caution when surfing online and using cybersecurity solutions.
- The campaign highlights the vulnerability of personal data and the importance of data protection measures.
- Kaspersky advises users to verify website authenticity, store cryptocurrencies securely, and use reliable security solutions.
- Date of report: February 18, 2020.

##################





Report 5

Summary:
- Threat actor TA516 released a new version of the AZORult stealer with improved features, spreading alongside ransomware in a new campaign.
- The campaign targeted North America on July 18, 2018, using employment-related subjects in emails.
- The new version of AZORult includes stealing browser history, cryptocurrency wallets, and improved loader functionality.
- The threat actor TA516 has a history of using similar resume lures to distribute malware.
- The malware campaign involved password-protected documents that downloaded AZORult and Hermes 2.1 ransomware.
- The impact of the attack includes potential financial losses and business disruption for affected organizations.
- The threat actor leveraged the new capabilities of AZORult to distribute Hermes ransomware within a day of the update being announced.
- Indicators of Compromise (IOCs) include malicious document SHA-256 hashes and URLs for AZORult and Hermes payloads.
- The campaign highlights the continuous evolution of malware to introduce new features and increase effectiveness in cyber attacks.





Report 6

TA516, also known as SmokingDro, has been active since 2016 and is known for distributing the SmokeLoader downloader, which then downloads additional malware, often banking Trojans, for financial gain. The threat actor has used malicious macros in fake resumes and JavaScript hosted on Google Drive to distribute malware like Panda Banker and coinminers via SmokeLoader. TA516 has been observed using tools such as AZORult, Chthonic, Smoke Loader, and Zeus Panda. The threat actor has been involved in various hacking operations, including using legitimate PayPal accounts to distribute malware and adopting novel techniques like triple-encryption and spreading as a fake ProtonVPN installer. The victims targeted by TA516 operate worldwide in various sectors, with a focus on financial crime. The threat actor's capabilities and use of advanced techniques make them a significant threat in the cybersecurity landscape.





Report 7

Summary:
Threat actors, identified as "TA516," have been using legitimate PayPal accounts to distribute the Chthonic Banking Trojan. The campaign was observed in July 2016, with emails appearing to come from PayPal requesting money. The emails contained malicious URLs that, when clicked, led to the download of an obfuscated JavaScript file that ultimately delivered the Chthonic Trojan. Notably, the Trojan also downloaded a second-stage payload, a previously undocumented malware called "AZORult." The threat actors used social engineering tactics to trick recipients into clicking on the malicious links. Despite the relatively small scale of the campaign, the technique of using legitimate services like PayPal to distribute malware poses a significant risk to users without adequate anti-malware protection. The threat actors' ability to bypass traditional defenses highlights the need for enhanced security measures. The report includes indicators of compromise and technical details of the attack, showcasing the sophistication and novelty of the threat actor's tools and techniques.


