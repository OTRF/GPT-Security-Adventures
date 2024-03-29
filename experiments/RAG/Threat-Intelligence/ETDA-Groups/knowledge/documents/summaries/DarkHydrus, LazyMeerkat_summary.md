
Report 1

DarkHydrus, also known as LazyMeerkat, is a state-sponsored threat actor originating from Iran that has been targeting government agencies and educational institutions in the Middle East since at least 2016. The group is known for using open-source tools and custom payloads in their attacks, with reported usage of tools such as Cobalt Strike, Mimikatz, Phishery, and RogueRobin. They have been linked to other threat groups such as APT 19 and APT 26, but it is unclear if they are the same. DarkHydrus has been involved in various hacking operations, including credential harvesting attacks on educational institutions and spear-phishing campaigns targeting government organizations. Their attacks have involved malicious attachments in spear-phishing emails and the use of backdoors dropped by macros in lure documents. The group's capability and novel techniques, such as using Google Drive for command and control communications, demonstrate their advanced tactics in carrying out information theft and espionage. The latest observed attacks by DarkHydrus were reported in January 2019, indicating ongoing malicious activities in the region.





Report 2

DarkHydrus, a threat actor, has been targeting government entities and educational institutions in the Middle East since at least Fall 2017. They have been carrying out ongoing credential harvesting attacks using spear-phishing emails containing malicious Microsoft Office documents that leverage the "attachedTemplate" technique to steal login credentials. DarkHydrus has been using the open-source Phishery tool to create these malicious Word documents and host the C2 server to gather credentials. The use of Phishery is novel, as it allows DarkHydrus to conduct targeted attacks against entities in the Middle East. The threat actor's reliance on open-source tools and consistent targeting of specific sectors indicate a high level of capability and persistence. The latest observed attack occurred on June 24, 2018, targeting an educational institution in the Middle East. The infrastructure used in these attacks includes the domain 0utl00k[.]net, which resolves to specific IP addresses. Overall, DarkHydrus poses a significant threat to organizations in the Middle East, and their use of novel tools and techniques makes them a formidable adversary.





Report 3

Summary:
- Threat actor: DarkHydrus
- Date: January 18, 2019
- Region: Middle East
- Operating sector: Not specified
- Type of company of victims: Security or technology vendors
- Evidence of capability: DarkHydrus observed using tactics like typosquatting domains, abusing open-source tools, and leveraging novel file types for anti-analysis.
- Novelty of tools and techniques: DarkHydrus delivered a new variant of the RogueRobin trojan that uses Google Drive API for C2 communications, enabling an alternative command and control channel.
- Tools and techniques used: AppLocker bypass technique, PowerShell and C# variants of RogueRobin, DNS tunneling, sandbox evasion checks, and Google Drive for C2 communications.
- Infrastructure: DarkHydrus used consistent naming schema and structure in their infrastructure, registering domains visually similar to well-known technology vendors.
- Conclusion: DarkHydrus continues operations with new techniques, porting PowerShell-based code to an executable variant, and using Google Drive for C2, suggesting a shift towards abusing legitimate cloud services for infrastructure.





Report 4

Summary:
- Threat actor group DarkHydrus targeted at least one government agency in the Middle East in July 2018.
- The attack involved spear-phishing emails with password-protected RAR archive attachments containing malicious Excel Web Query files (.iqy).
- DarkHydrus used a custom PowerShell-based payload named RogueRobin, a departure from their previous attacks using open-source legitimate tools.
- The payload checked for sandbox environments before attempting to persistently execute on the system.
- DarkHydrus communicated with its command and control (C2) servers using a custom DNS tunneling protocol.
- The C2 domains used by DarkHydrus spoofed legitimate domains of security vendors.
- The payload provided remote administration capabilities through various commands.
- DarkHydrus leveraged weaponized Microsoft Office documents in previous attacks.
- The attack campaign showed evidence of DarkHydrus using novel techniques and tools, possibly custom-developed.
- Palo Alto Networks customers were protected against the attack through various security measures.

Date: July 27, 2018

Region: Middle East
Operating Sector: Government
Type of Company: Government agency

Evidence of Capability: Custom PowerShell-based payload, DNS tunneling protocol, sandbox evasion techniques, remote administration capabilities through commands.

Novelty of Tools and Techniques: Use of .iqy files, custom PowerShell payload, DNS tunneling protocol, and spoofing legitimate domains of security vendors.

Malformed report


