
Report 1

Summary: FIN6, also known as Skeleton Spider, was responsible for a web skimmer incident involving card data from Volusion that surfaced on the dark web. The threat actor targeted companies in the retail sector, specifically those using Volusion's e-commerce platform. The incident occurred in 2024, showcasing the ongoing activity of FIN6. The capability of the threat actor is evidenced by their ability to deploy web skimmers and exfiltrate sensitive card data. The use of the dark web to sell stolen information highlights the sophistication of FIN6's operations. The tools and techniques used by FIN6 demonstrate a level of novelty and adaptability in their cyber attacks.





Report 2

FIN6, also known as Skeleton Spider, is a cybercrime group that targets the hospitality and retail sectors, stealing payment card data for profit. The group has been active since 2015 and has used a variety of aliases to evade detection. They have been observed using a range of tools and techniques, including Cobalt Strike, Mimikatz, and LockerGoga ransomware. Victims of their attacks operate in sectors such as Chemical, Energy, Manufacturing, and Retail. Notably, in 2020, they partnered with the TrickBot gang to use the new malware framework "Anchor" for financial gain. Europol detained suspects behind their attacks in 2021, showing efforts to counter their operations.





Report 3

Summary:
The threat actor ITG08, also known as FIN6, has partnered with the TrickBot gang to use the Anchor malware framework for financial profit. The Anchor framework, dating back to 2018, is connected to TrickBot and includes a new PowerShell-based backdoor called PowerTrick. ITG08/FIN6 primarily targets point-of-sale machines in the U.S. and Europe. Evidence suggests that ITG08 has used PowerTrick and Anchor in targeted attacks on enterprise networks, including POS systems. The use of TerraLoader, More_eggs backdoor, and Metasploit shellcode loaders in combination is unique to ITG08. The partnership with TrickBot reveals ITG08's strategy to adapt to new malware and collaborate with other threat actors. The group has also targeted e-commerce environments and maintains relationships with underground malware suppliers. ITG08 is financially motivated, adaptable, sophisticated, and persistent, making it a potent cybercriminal group. The report was published on April 7, 2020, by Ole Villadsen.





Report 4

Summary: The threat actor FIN6, also known as Skeleton Spider, targeted Norsk Hydro, one of the largest aluminum producers in the world, with LockerGoga ransomware, forcing the company into partial manual operations. The attack was noticed by IT staff late Monday, affecting computer systems in most business areas. LockerGoga ransomware, although relatively new, gained public attention in January after an attack on Altran Technologies. NorCERT warned companies about the attack, indicating that Norsk Hydro was one of its victims. The attack involved Active Directory, used for authenticating and authorizing users and systems on a Windows domain network. Norsk Hydro confirmed the ransomware infection and is working to contain and neutralize the attack with external help. The company is prioritizing safe operations, limiting financial impact, and restoring operations from backups. The incident did not endanger people but impacted operations globally. The company is currently running in manual mode, with production losses minimal. The main focus is on ensuring safe operations and cleaning infected servers. No power plants outside Norway were affected. The report was updated with new information from Norsk Hydro's CFO and the director of the Norwegian cybersecurity authority. 

Date: March 19, 2019

Region: Global

Operating Sector: Aluminum Production

Type of Company: Norsk Hydro, Aluminum Production Company





Report 5

Summary:
The threat actor ITG08, also known as FIN6, has been active since 2015, targeting point-of-sale machines in brick-and-mortar retailers and companies in the hospitality sector in the U.S. and Europe. Recently, they have been observed targeting e-commerce environments using online skimming techniques to steal payment card data. ITG08 has been actively attacking multinational organizations by spear phishing specific employees with fake job advertisements and deploying the More_eggs JScript backdoor malware. This backdoor, sold on the dark web, allows attackers to establish and maintain a foothold in compromised environments. The threat actor also uses Windows Management Instrumentation (WMI) and PowerShell techniques for lateral movement and deploying malware. The use of Comodo code-signing certificates further strengthens the link to ITG08. The report provides detailed analysis of the threat actor's tactics, techniques, and procedures, as well as mitigation tips for defenders. The campaign investigated by IBM X-Force Incident Response and Intelligence Services (IRIS) occurred in August 2019.





Report 6

Summary:
Between February 27, 2019, and the past 8-10 weeks, Morphisec tracked a global cyber attack targeting Point of Sale thin clients, with evidence pointing to the threat actor FIN6. The attack involved the use of FrameworkPOS scraping malware and Cobalt Strike backdoor execution, with PowerShell/WMI stages used for lateral movement and privilege escalation. Victims in the United States, Japan, and India from the finance, insurance, and healthcare sectors were targeted. The threat actor demonstrated advanced capabilities by utilizing memory evasion techniques and injecting code into processes. The attack involved the use of multiple servers delivering the Cobalt Strike beacon and the installation of a FrameworkPOS scraper for exfiltrating credit card information. Morphisec Labs is still analyzing the infiltration methods, but immediate prevention of such attacks is crucial due to the evolving nature of the threat actor's techniques.





Report 7

Summary: 
On January 24, 2019, Altran Technologies, a French engineering consultancy, was targeted by a ransomware attack using the LockerGoga strain. The attack affected operations in some European countries, leading Altran to shut down its network and applications. Evidence suggests that the ransomware was slow and inefficient, with the capability to encrypt various file types. The ransom note included contact information for payment instructions, indicating a focus on targeting companies. The ransomware was signed with a valid certificate, potentially aiding in its deployment without detection. The attack timeline and spread of the ransomware were hypothesized based on available information. The threat actor behind the attack remains unidentified.





Report 8

Summary:
- Threat actor: FIN6, Skeleton Spider
- Region: Not specified
- Operating sector: Engineering industry
- Type of company: Not specified
- Date: April 5, 2019
- Evidence of capability: FIN6 expanded criminal enterprise to deploy ransomware (Ryuk, LockerGoga) for monetization, used stolen credentials, Cobalt Strike, Metasploit, Adfind, 7-Zip for reconnaissance and lateral movement, created Windows services for PowerShell commands, used named pipe impersonation for privilege escalation, automated deployment of ransomware using batch scripts
- Novelty of tools and techniques: Use of Cobalt Strike, Metasploit, PowerShell commands, Adfind, 7-Zip, encoded commands, ransomware families Ryuk and LockerGoga, creation of distribution servers, anti-forensics commands, use of domain administrator credentials
- Malformed report





Report 9

Summary:
The Securonix Threat Research Team has been monitoring the LockerGoga targeted cyber sabotage/ransomware attacks impacting companies like Norsk Hydro and Hexion/Momentive, causing over $40 million in damages. The attacks are attributed to the FIN6 threat actor, known for targeting industrial, manufacturing, healthcare, and insurance companies in the US and Asia. The threat actor uses signed digital certificates to evade detection and employs techniques like disabling antivirus processes and deleting event logs. The attacks involve file encryption, cyber sabotage, lateral movement, and defense evasion. Securonix provides recommendations for detection and prevention, including monitoring process activity and implementing security training programs. The report was updated on April 30, 2019, and includes references to various sources detailing the impact and analysis of the LockerGoga attacks. The threat actor's capabilities and novel techniques demonstrate a high level of sophistication in targeting IT and OT infrastructure. 

Region: Global
Operating Sector: Industrial, Manufacturing, Healthcare, Insurance
Type of Company: Norsk Hydro, Hexion/Momentive
Date: Updated April 30, 2019


