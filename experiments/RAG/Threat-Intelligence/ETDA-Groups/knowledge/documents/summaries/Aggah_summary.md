
Report 1

Summary:
The Aggah campaign, discovered on 09/24/2019, involved a multi-stage infection chain starting with a weaponized Office document containing VBA macro code. The attackers used obfuscation techniques and a bit.ly link to deliver payloads associated with the Gorgon Group APT. The final payload varied, with a variant of the AzoRult infostealer being used at one point. This variant, named "Mana Tools," targeted browsers to exfiltrate credentials and navigation data. The campaign raised questions about the identity of the threat actor behind it, with possibilities ranging from Gorgon Group to minor cyber criminals. The attackers used Pastebin for hosting malicious payloads and employed persistence mechanisms to ensure continued access to infected systems. The campaign showcased novel techniques and tools, including customized versions of known malware like AzoRult.





Report 2

Summary:
The threat actor known as Aggah has been active since at least 2018, targeting organizations primarily in the Middle East but also in the United States, Europe, and Asia. The actor's tools and techniques include the use of RevengeRAT configured with a duckdns[.]org domain for C2, as well as other RATs like Agent Tesla, NanoCore RAT, and njRAT. The Aggah Campaign has targeted various sectors such as Automotive, Education, Government, Healthcare, Hospitality, Manufacturing, Media, Retail, and Technology in countries including the USA, UK, Germany, Japan, and others. The actor's motivation includes information theft, espionage, and financial gain. Notably, the Aggah Campaign has evolved over time, with operations like "Roma225" in 2018 targeting the Italian automotive sector and more recent activities targeting businesses in the manufacturing and retail sectors. The threat actor has also been observed using novel techniques such as hijacking clipboards to replace cryptocurrency addresses. The Aggah Campaign continues to pose a significant threat to organizations globally.





Report 3

Summary:
The threat actor known as Aggah has been running a botnet without renting a server for over a year, targeting Italian companies in the Retail sector. The actor utilizes malicious PPA files with macros to download web pages from BlogSpot, hiding malicious code within them. The actor, now identified as YAKKA3, uses Pastebin to download additional code, including a PowerShell loader and a .NET process injection utility. The actor also employs a UAC Bypass Tool to elevate privileges stealthily. The delivered malware includes a LokiBot variant, and previous payloads included AZOrult infostealer. The actor remains active and dangerous, utilizing legitimate third-party services to manage infected hosts and run the botnet. The actor's activities have been tracked for over a year, with potential connections to the Gorgon APT group. The threat actor's tools and techniques demonstrate a high level of sophistication and adaptability.





Report 4

Summary:
The Aggah Campaign, active in March 2019, targeted organizations in the Middle East, the United States, Europe, and Asia. The threat actor used Template Injection to deliver RevengeRAT via Bit.ly, BlogSpot, and Pastebin. The actor employed various techniques to disable security mechanisms in Microsoft Office products and used Pastebin for C2 support. The RevengeRAT payload was configured with a duckdns[.]org domain for C2, and the actor used the alias "hagga" in the campaign. The threat actor's capability was demonstrated through the use of sophisticated techniques and tools like RevengeRAT. The campaign targeted organizations in various sectors, including education, media/marketing, government, technology, retail, manufacturing, and more. The campaign's reach extended to multiple countries, indicating a large-scale operation.





Report 5

Summary:
- Threat actor: Aggah
- Region: Asia, with a focus on Taiwan and South Korea
- Operating sector: Manufacturing industry
- Date: Campaign began in early July 2021
- Evidence of capability: Spearphishing emails targeting manufacturing companies, use of compromised websites to host malicious scripts delivering Warzone RAT
- Novelty of tools and techniques: Aggah's evolution to using compromised sites, obfuscated payloads in PowerShell files, use of AMSI bypass, reuse of class names, and spoofed B2B email addresses
- Attribution: TTPs align with previous Aggah activity
- Conclusion: Aggah shows adaptability and evolution in tactics, moving towards using compromised sites to evade detection

Malformed report.





Report 6

Summary:
The threat actor known as "Aggah" has been observed in a new variant of a unique malware loader that utilizes fileless multi-stage techniques, dual-use tools, and free web hosting services like Bitly and Pastebin. The malware loader drops spyware strains such as Agent Tesla, Remcos RAT, and NanoCore RAT as final payloads. The threat actor has shown a level of sophistication by using advanced evasion techniques and leaving traces of the malware author in the code. The campaign involves distributing malware through Microsoft Office documents with malicious VBA macros and utilizing Pastebin URLs to store resources. The threat actor's capability to adapt and update the malware, as well as the use of novel techniques like CMSTP.exe for privilege escalation, poses a serious threat to organizations. The evidence suggests a team behind the development of Aggah, with attempts to gain recognition in hacker forums and social media platforms. The attack was detected and prevented by Deep Instinct's advanced Deep Learning-based static analysis and behavioral capabilities. The operation time window for this threat actor is not specified in the report.





Report 7

Summary:
The threat actor "Aggah" targeted Italian companies in the manufacturing sector, including those in the automotive production chain, as reported on 05/22/2020. The actor has been previously identified in malicious operations targeting various industries in the US, Europe, and Asia. The actor utilized an intricate infection chain involving malicious office documents with macros, PowerShell stages, and CMSTP bypass exploit, showcasing advanced techniques. The actor's campaigns evolved over time, using obfuscation methods and leveraging legitimate services like Pastebin for C2 communication. The final payload used was AgentTesla, a commodity malware for stealing sensitive information. The threat actor demonstrated persistence and flexibility in bypassing traditional security defenses, posing a significant cyber threat to organizations. The report provides indicators of compromise and Yara rules for detection.





Report 8

Malformed report





Report 9

Summary:
The threat actor known as "Aggah" conducted the "Roma225" campaign targeting companies in the Italian automotive sector. The attack involved a phishing email impersonating a senior partner of a Brazilian law firm, distributing a malware-laden PowerPoint add-in document. The malware utilized VBA macro code to download and execute a dropper from a malicious Blogspot page. The malware, identified as a RevengeRAT variant, stored payloads in registry keys, executed malicious scripts, and established connections with command and control servers in Canada and Brazil. The attack also involved the deployment of a njRAT variant and an Outlook.exe payload. The threat actor's infrastructure was geolocated in different countries. The attack showed similarities with tactics used by APT groups like The Gorgon Group. The malware used unique techniques and tools, indicating a high level of sophistication. The attack was detected on 12/27/2018.





Report 10

Summary:
The threat actor "Aggah" has been observed targeting private companies in various sectors, including automotive, luxury, education, and media/marketing, as reported by Unit42. The attacks involve the use of a Remote Access Trojan named "RevengeRat" and show similarities to the Gorgon Group's tactics. The infection chain is sophisticated, with multiple stages to deliver the payload. The threat actor leverages platforms like Blogger and Pastebin for obfuscation and persistence. The malware implants, including RevengeRAT, are obfuscated using tools like ConfuserEx and .Net Reactor. The threat actor shows an evolution in their techniques, such as process hollowing, while maintaining some TTPs. The campaign, internally referenced as TH-173, may involve up to 1600 victims. The threat actor's persistence mechanisms include registry key manipulation and scheduled tasks. The campaign is ongoing, with evidence of continued activity and refinement in tactics. The report provides indicators of compromise and Yara rules for detection. The threat actor's activities are being monitored by Cybaze-Yoroi Z-LAB.


