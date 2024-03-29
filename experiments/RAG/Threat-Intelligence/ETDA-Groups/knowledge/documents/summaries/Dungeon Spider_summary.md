
Report 1

Summary:
- Threat actor "Dungeon Spider" targeted Methodist Hospital in Henderson, Kentucky, leading to an "internal state of emergency" due to a Locky ransomware attack on March 24, 2016.
- The ransomware encrypted valuable files on the hospital's systems, demanding four bitcoins (USD $1,600) for decryption.
- Evidence of the threat actor's capability was shown through the use of malicious macros in Word documents to deliver the ransomware.
- The attack disrupted hospital operations, forcing them to process everything on paper temporarily.
- Similar attacks on the healthcare industry, like the Hollywood Presbyterian Medical Center, indicate a trend of targeting vulnerable sectors.
- The incident highlighted the vulnerability of the healthcare industry to cyberattacks due to the valuable information it holds.
- The hospital's response included shutting down systems and gradually bringing them back online to check for infections.
- No ransom was paid, and patient information was not compromised, with the hospital's internal systems now operational.
- The incident underscores the ongoing threat of ransomware attacks on critical infrastructure and the importance of cybersecurity measures in the healthcare sector.





Report 2

Malformed report





Report 3

DUNGEON SPIDER, a criminal group operating the Locky ransomware since February 2016, targets victims with a combination of RSA and AES encryption algorithms. The ransomware deletes Shadow Volume Copies to prevent file recovery and communicates with hard-coded IP addresses or uses a domain generation algorithm for C2 communications. Each victim receives a personal identification number for decryption key retrieval upon ransom payment. Locky's notoriety led to the emergence of PyLocky in September 2018, targeting entities in France and Germany. PyLocky masquerades as a version of Locky, indicating active development of ransomware by threat actors. DUNGEON SPIDER primarily relies on broad spam campaigns for distribution, with Locky being the associated name in the industry. The last observed activity of Locky was in late 2017, with no evidence linking PyLocky to DUNGEON SPIDER or Locky. The threat actor continues to pose a dominant and viable threat vector in the cybersecurity landscape.





Report 4

Summary:
The threat actor known as Dungeon Spider, operating the Locky ransomware, has been active since 2016 and primarily targets victims through broad spam campaigns with malicious attachments. The ransomware encrypts files using RSA and AES algorithms, targeting a wide range of file extensions and deleting Shadow Volume Copies to prevent recovery. Dungeon Spider has been linked to the Necurs distribution network. The threat actor's motivation is financial gain, with reported attacks on various sectors worldwide. The latest observed activity was in 2017, with the actor evolving techniques such as using PDFs instead of Word documents for distribution. The threat actor originates from Russia and has been involved in high-profile attacks on organizations like Hollywood Presbyterian Medical Center and Methodist Hospital in Henderson, Kentucky. The Locky ransomware has shown resilience and adaptability, making it a persistent threat in the cybersecurity landscape.





Report 5

Summary: The threat actor known as "Dungeon Spider" targeted a Hollywood hospital, infecting their systems with ransomware. The attack occurred in 2024, as reported by ZDNET. The victims were in the healthcare sector, specifically a hospital in the Hollywood region. The threat actor demonstrated capability in deploying ransomware and demanding payment for decryption. The tools and techniques used by "Dungeon Spider" were novel and effective in compromising the hospital's systems. The attack highlights the ongoing threat posed by ransomware actors to critical infrastructure and sensitive sectors.





Report 6

Summary:
The threat actor known as "Dungeon Spider" has been actively targeting victims in Japan with the Locky ransomware since February 2016. The Locky ransomware has quickly become a major threat in Japan, ranking tenth in Botnet observations. The malware uses downloaders like W97M/TrojanDownloader.34B7!tr and JS/Nemucod.GY!tr.dldr to infect victims, with a focus on Japan. The ransomware note is even served in Japanese to Japanese victims. The threat actor's use of new ransomware techniques and tools, along with the rapid expansion of infection activity, indicate a high level of capability and sophistication. The threat actor's activities have been detected by FortiGuard Labs, urging the need for protective measures and backups to prevent data loss. The report was published on April 5, 2016, by Kenichi Terashita from FortiGuard Labs.





Report 7

Summary:
The report discusses the threat actor known as "Dungeon Spider" and their ransomware Trojan called Locky. The Locky Trojan, active since February 2016, spreads through malicious spam messages containing attachments with macros or obfuscated scripts in JavaScript. The Trojan encrypts files using AES-128 in CTR mode and demands ransom in bitcoins. It communicates with Command and Control servers using HTTP protocol and generates new C&C addresses daily. Kaspersky Lab products offer protection against Locky at all stages of the attack. The report provides insights into the propagation, geography of attacks, encryption methods, ransom demands, and countermeasures against Locky. The threat actor targets victims globally, with infections reported in 114 countries. The report also highlights the novelty of Locky as a new ransomware threat written from scratch.





Report 8

Locky is a ransomware malware operated by Necurs, released in 2016. It is delivered via email with a malicious Microsoft Word document containing macros. The user is prompted to enable macros, leading to the encryption of files with specific extensions. The encrypted files display a message instructing the victim to pay a ransom in bitcoin. Locky uses RSA-2048 + AES-128 cipher for encryption, making manual decryption impossible. It has been distributed through various methods, including exploit kits and malicious attachments. Notable incidents include the Hollywood Presbyterian Medical Center paying a ransom in bitcoins. Locky has targeted a wide range of victims, including hospitals and educational institutions. The threat actor behind Locky has shown capability in evolving the ransomware with new variants and distribution techniques. The operation of Locky has been ongoing since its release in 2016, with updates and changes in distribution methods.





Report 9

Summary:
The threat actor known as "Dungeon Spider" has been observed spreading Locky ransomware through spam campaigns, targeting victims in the Asia Pacific region. The ransomware is hidden under multiple obfuscated layers of JavaScript, with new evasion techniques being constantly developed. The threat actor uses XOR obfuscation, XOR and reverse obfuscation, and JavaScript obfuscation to avoid detection by security measures. The Locky payload is disguised as junk files and downloaded through compromised websites. McAfee Labs has detected this malicious JavaScript and Locky payload as JS/Nemucod and Ransomware-Locky.a!enc respectively. The cat-and-mouse game between ransomware developers and security vendors continues, with new evasion techniques expected to emerge. Users are advised to keep their antimalware signatures up to date to protect against such threats. The operation time window for these campaigns is ongoing, with new variants and techniques being developed regularly.





Report 10

Summary:
The threat actor known as "Dungeon Spider" was identified for distributing the Locky Ransomware Virus, which was delivered by the same actor behind the Dridex malware campaigns. The Locky ransomware was distributed through spam emails containing malicious macros in MS Word documents, with the first observation made on February 16, 2016. The threat actor utilized a botnet previously associated with Dridex campaigns to distribute the ransomware. The Locky ransomware encrypts files based on their extension and displays a ransom message, instructing victims to buy Bitcoins and send them to a specific Bitcoin address for decryption. The threat actor behind the Locky ransomware attack demonstrated a novel approach by leveraging the same infrastructure used for distributing other malware variants. The ransomware also generated DGA traffic for command and control purposes. The Locky ransomware targeted a wide range of file formats on local disk drives, including mapped shared drives. The threat actor's capability was evidenced by the use of sophisticated techniques and infrastructure for distribution. The report provides detailed IOCs and technical information related to the Locky ransomware campaign. The operation time window for this threat actor's activity was not specified in the report.





Report 11

Locky Ransomware has switched to the Lukitus extension for encrypted files in a new variant discovered on August 16, 2017. The ransomware is distributed via spam emails with specific subject lines and attachments containing JS files that download the Locky executable. Once executed, Locky encrypts files and appends the .lukitus extension to them. The ransom note displayed after encryption instructs victims on how to pay the ransom, set at 0.49 BTC or approximately $2,000 USD. Currently, there is no free decryption method available for files encrypted by this Locky variant. To protect against Locky Ransomware, users are advised to maintain backups, use security software, and practice good online security habits.





Report 12

Malformed report





Report 13

The threat actor known as "Dungeon Spider" has been identified as the operator behind the recent Locky ransomware phishing attacks that have successfully evaded machine learning tools. The attacks targeted businesses in multiple regions including North America, Europe, and Southeast Asia in late September. The threat actor demonstrated a high level of capability by using social engineering tactics to distribute phishing emails that appeared legitimate and bypassed malware detection tools. The phishing emails contained attachments disguised as printer outputs with malicious scripts, making detection challenging even for machine learning algorithms. Security researchers at Comodo detected and analyzed over 110,000 Locky-related emails sent from a vast number of IP addresses across the globe. The threat actor's ability to continuously launch attacks using compromised servers and infected systems belonging to individual consumers and ISPs highlights the persistent nature of the threat. The Locky ransomware has been widely distributed since 2016 and continues to be a significant threat in the cybersecurity landscape. The attacks coincide with Europol's warning of ransomware being a prevalent cyber threat, with Locky being a notable example. The threat actor's use of novel techniques and tools underscores the evolving nature of cyber threats in the digital landscape.





Report 14

The report discusses the threat actor known as "Dungeon Spider" targeting victims with Locky ransomware, particularly Hollywood Presbyterian Medical Center and Methodist Hospital in February 2016. The threat actor has evolved the ransomware with variants like zepto, thor, osiris, and Diablo6. The report highlights the threat actor's capability to adapt and evade detection by making small changes in the code. The threat actor uses spear phishing emails with VBS files to deliver the ransomware payload. The report provides a technical teardown of the attack, showing the connection to the command-and-control server and the encryption process. The report also includes indicators of compromise (IoCs) such as domain names and hash values associated with the threat actor. The threat actor's capability to create multiple domains for distributing ransomware is evident. The report emphasizes the importance of user education to prevent such attacks and recommends using endpoint protection products like CylancePROTECT. The threat actor's use of novel techniques like VBS files and malicious URLs in spam emails showcases their advanced capabilities. The report was published on November 7, 2017, by the BlackBerry Cylance Threat Research Team.


