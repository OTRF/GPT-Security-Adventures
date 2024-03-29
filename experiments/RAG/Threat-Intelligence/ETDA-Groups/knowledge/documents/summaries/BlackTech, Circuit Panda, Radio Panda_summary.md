
Report 1

Summary:
- Threat actor: BlackTech
- Region: East Asia
- Operating sector: Government organizations
- Type of company: Not specified
- Date: August 2020
- Evidence of capability: BendyBear shellcode linked to WaterBear malware family, associated with BlackTech cyber espionage group, sophisticated features, anti-analysis techniques, polymorphic code, modified RC4 encryption, advanced network communication methods, unique session keys, evasion tactics, in-memory loading of payloads.
- Novelty of tools and techniques: BendyBear shellcode stands out for its advanced features, including encryption methods, network communication protocols, anti-analysis techniques, and in-memory loading capabilities. The use of custom cryptographic routines, byte manipulations, and polymorphic code indicate a high level of technical sophistication.





Report 2

BlackTech, also known as Circuit Panda and Radio Panda, is a state-sponsored threat actor originating from China. They have been active since 2010 and primarily target victims in East Asia, particularly Taiwan, Japan, and Hong Kong. The group's campaigns, such as PLEAD, Shrouded Crossbow, and Waterbear, focus on information theft and espionage in sectors like construction, financial, government, healthcare, media, and technology. BlackTech has been observed using a variety of tools like BendyBear, BIFROST, Bluether, and Flagpro, showcasing their evolving tactics and techniques. The threat actor has been linked to novel operations, such as misusing stolen digital certificates and using API hooking techniques to evade security product detection. Their capability to hide network behaviors and target a wider range of victims, including in the USA, demonstrates their advanced cyber capabilities. The group's use of unique tools like BendyBear and Flagpro highlights their sophistication in cyber espionage activities.





Report 3

Summary:
- Threat actor: BlackTech group
- Region: Asia, specifically Taiwan
- Operating sector: Cyberespionage
- Type of company: ASUS Cloud Corporation
- Date: July 2018 and April 2019
- Capability: Distributing Plead malware via compromised routers and man-in-the-middle attacks against ASUS WebStorage software
- Novelty: Misusing legitimate software for malware distribution, using supply chain and man-in-the-middle attack techniques
- Evidence: Digital signatures, file names, communication interception, and malware behavior analysis
- Tools and techniques: Plead backdoor, first-stage downloader, second-stage loader, third-stage DLL, RC4 encryption, C&C servers, and MITRE ATT&CK techniques.





Report 4

Summary:
A threat actor, likely the cyberespionage group BlackTech, misused stolen digital certificates from Taiwanese tech companies D-Link and Changing Information Technologies in a Plead malware campaign. The certificates were used to sign the Plead malware, a backdoor and password stealer component. Despite the certificates being revoked, the threat actor continued to use them in their attacks. The ability to compromise and reuse code-signing certificates from Taiwan-based companies demonstrates the threat actor's high skill level and focus on the region. The malware samples were highly obfuscated with junk code, making detection challenging. The threat actor's use of stolen digital certificates is a tactic to mask malicious intentions and bypass security measures. The operation was discovered on July 9, 2018.





Report 5

Summary: The threat actors known as BlackTech, Circuit Panda, and Radio Panda have been identified as spending months undetected in company networks. The victims targeted were in the technology and manufacturing sectors in the Asia-Pacific region. The threat actors demonstrated advanced capabilities in evading detection and using novel tools and techniques. The operation time window was not specified in the report. For more information, refer to the source provided.





Report 6

Waterbear, associated with the BlackTech cyberespionage group, has been using modular malware for several years targeting technology companies and government agencies in East Asia. In a recent campaign, Waterbear was found to be using API hooking techniques to evade detection by a specific security product, indicating a novel approach by the threat actor. The attackers demonstrated knowledge of the victim's environment and security products, as well as familiarity with how security products gather information. The API hooking shellcode used by Waterbear is generic, suggesting it could be used to target other products in the future. This activity was consistent with BlackTech's previous campaigns in the APAC region, particularly Taiwan, Japan, and Hong Kong. The report provides detailed technical analysis of Waterbear's capabilities and techniques, highlighting the threat actor's sophistication and adaptability.


