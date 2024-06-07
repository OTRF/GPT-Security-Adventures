
Report 1

Summary:
The threat actor known as Confucius, first seen in 2013, is believed to be from South Asia, specifically India, and is associated with Patchwork and Dropping Elephant groups. Their operations involve deploying bespoke backdoors and stealing files from victims' systems, targeting USB devices to overcome air-gapped environments. Confucius has targeted victims in various sectors and countries, including Azerbaijan, Bangladesh, France, India, Indonesia, Iran, Italy, Mongolia, Pakistan, and others. They have used tools like ApacheStealer, Hornbill, and SunBird, and have been involved in hacking operations exploiting programs like InPage and using fake romance websites to distribute malicious Android applications. In 2021, Confucius used Pegasus Spyware-related lures to target the Pakistani military. The threat actor's activities show a capability for information theft and espionage, with a focus on novel tools and techniques to compromise targets.





Report 2

Summary:
The threat actor known as "Confucius" has been observed utilizing malware families that abuse legitimate websites for command and control communication, evading traditional DNS lookups. The malware families, CONFUCIUS_A and CONFUCIUS_B, have been linked to cyber espionage campaigns targeting primarily the Middle East and parts of Asia, with a focus on Pakistan. CONFUCIUS_A was observed using Yahoo and Quora for DNS resolution, while CONFUCIUS_B exhibited similar behavior but with custom obfuscation techniques. The use of legitimate web services for communication and the substitution of words for components of IP addresses are novel techniques employed by the threat actor. The malware families are believed to have a single developer or development company behind them, with links to known espionage campaigns such as SNEEPY and Operation Patchwork. The threat actor's infrastructure and techniques suggest a sophisticated and persistent cyber threat. (Date: September 28, 2016)





Report 3

Summary:
The threat actor known as Confucius has been identified using new techniques and establishing connections with the Patchwork group. The threat actor primarily targets victims in South Asia, specifically in Pakistan. Confucius has been using fake romance websites to distribute malicious Android applications, with new websites and payloads being set up for this purpose. The threat actor has also been using adult content and chat applications as lures to compromise targets. The tools and techniques used by Confucius show an evolution in their modus operandi, including the use of malicious Android and Windows applications. The threat actor has demonstrated capability in stealing sensitive information and files from victims, with a focus on specific file types. The threat actor has shown links to other groups, such as Patchwork, through shared code and infrastructure. Confucius has been active in ongoing campaigns, utilizing weaponized documents and modified versions of Remote Administration Tools. Organizations are advised to implement proactive security measures to defend against threats from actors like Confucius and Patchwork. Trend Micro offers solutions to protect against email-based attacks and endpoint security to mitigate the impact of these threats. The report was last updated on August 30, 2018, and provides indicators of compromise related to the threat actor groups.





Report 4

Confucius, a threat actor, targeted the Pakistani military through a spear phishing campaign using Pegasus spyware-related lures. The campaign involved sending emails impersonating the Pakistani Armed Forces and warning about Pegasus spyware, leading to the download of a malicious document. The document contained macros that, when enabled, loaded a series of .NET DLL files for downloading and executing malicious payloads. The final payload was a file stealer designed to exfiltrate specific file types from the victim's system. The threat actor used innovative techniques like hiding malicious code in the comments section and encrypted documents to evade detection. The campaign showed an interest in military personnel and employed various social engineering lures. Best security practices and solutions like Trend Micro™ Cloud App Security and Deep Discovery™ Email Inspector can help defend against such attacks. The report provided indicators of compromise, including hashes of malicious documents and URLs/IP addresses associated with the campaign. Date of operation: Early August.





Report 5

Summary:
The threat actor "Confucius" engages in cyberespionage operations targeting individuals in South Asian countries, such as military personnel and businessmen. The group uses social engineering tactics, including online romance scams, to lure victims into installing malware on their devices. Confucius utilizes custom backdoors and file stealers, with some tools resembling those used by the Patchwork group. The threat actor exploits vulnerabilities in Office files for malware delivery and exfiltrates stolen data through a cloud storage service. Confucius' operations demonstrate a focus on tailored attacks and novel techniques, with evidence of targeting a specific set of victims. The report provides insights into the group's infrastructure, tools, and tactics, highlighting the need for organizations to adopt countermeasures to mitigate the threat. The operation time window is not specified in the report.





Report 6

Summary:
- Threat actor "Confucius" discovered by Unit 42 on November 2, 2017, exploited InPage program with three documents dropping malware families: CONFUCIUS_B, BioData, and MY24.
- InPage exploit uncommon, previously noted by Kaspersky in late 2016, targets politically or militarily motivated victims in regions like India and Kashmir.
- Novelty in tools and techniques include unique shellcode with custom hashing algorithm, use of InPage as attack vector, and malware families with advanced capabilities.
- Malware payloads dropped suggest well-resourced attackers behind the attacks, with continued development observed by Unit 42.
- Palo Alto Networks customers protected against threats with malicious domain flags, WildFire platform categorization, and AutoFocus tracking of Confucius_B, MY24, and BioData.


