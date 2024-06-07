
Report 1

Summary:
- Threat actor "RedDelta" conducted an espionage campaign targeting telecommunication companies in Asia Pacific, Europe, and the US.
- The attack, dubbed Operation Diànxùn, used malware masquerading as Flash applications and a phishing website impersonating Huawei's career page.
- Evidence suggests a medium to high level of confidence that RedDelta was behind the campaign, with a focus on stealing 5G technology-related information.
- The threat actor utilized novel techniques such as using a Cobalt Strike backdoor instead of the usual PlugX backdoor.
- McAfee's telemetry identified targets in the telecommunication sector, particularly in Southeast Asia, Europe, and the US, with a strong interest in German, Vietnamese, and Indian companies.
- The campaign was linked to RedDelta's previous activities targeting the Vatican and religious organizations, with similarities to the threat actor Mustang Panda.
- McAfee recommends a multi-layered security approach including MVISION Insights, Web Gateway, UCE, EDR, and NSP for protection against such attacks.
- The threat actor's motivation is believed to be related to the ban of Chinese technology in the global 5G roll-out.
- McAfee is actively monitoring the threat and providing updates on the situation.





Report 2

RedDelta, a Chinese-state sponsored threat activity group, targeted the Vatican, the Catholic Diocese of Hong Kong, the Hong Kong Study Mission to China, and the Pontifical Institute for Foreign Missions in a series of network intrusions starting in May 2020. These intrusions aimed to gather intelligence ahead of the renewal of the China-Vatican provisional agreement in September 2020. RedDelta's novel use of PlugX with different encryption methods and malware infection chains set them apart from other threat groups like Mustang Panda. In addition to Catholic Church-related entities, RedDelta also targeted law enforcement, government entities in India, and a government organization in Indonesia. The threat actor's motivation is information theft and espionage, operating primarily in government, law enforcement, and telecommunications sectors across various countries. The latest reported operation by RedDelta involved targeting diplomatic offices using a compromised email address of a diplomat from a European NATO country. The threat actor's activities have been ongoing since 2020, with multiple hacking operations reported.





Report 3

Summary:
- Threat actor "RedDelta" (also known as TA416) has been observed resuming activity post-Chinese National Day holiday targeting entities associated with diplomatic relations between the Vatican and the Chinese Communist Party, as well as organizations in Myanmar and Africa.
- Proofpoint researchers identified a new Golang variant of TA416's PlugX malware loader, indicating an update to the actor's toolset for delivering malware payloads.
- The Golang loader, used alongside consistent PlugX malware, demonstrates the threat actor's persistence in modifying tools to evade detection and frustrate analysis.
- The threat actor's phishing activity, using social engineering lures related to Vatican-CCP relations, resumed after a period of dormancy following disclosures by threat researchers.
- Command and control infrastructure, including IP addresses and communication URLs, were identified, with the malware communicating with a server hosted by a Chinese ISP.
- The threat actor's adaptation to detection efforts and continued targeting of diplomatic and religious organizations suggest a persistent threat that will likely continue its activities in the future.

Date: November 23, 2020

Region: Global
Operating Sector: Diplomatic, Religious
Type of Company: Not specified





Report 4

Summary:
The threat actor "RedDelta" identified as TA416, aligned with the Chinese state, has been targeting European diplomatic entities, particularly those involved in refugee and migrant services, amidst the conflict between Russia and Ukraine. The group utilizes web bugs for reconnaissance before delivering PlugX malware payloads via malicious URLs. TA416 has updated its PlugX variant, changing its encoding method and expanding its configuration capabilities. The threat actor has been observed using legitimate PE files for DLL search order hijacking to install the PlugX malware payload. Recent campaigns show a rapid pace of malware development with evolving encryption methods and configuration capabilities. TA416 has been consistent in targeting European diplomatic entities and has shown a lack of innovation but compensates with a high tempo of variation in their malware delivery methods. The group's persistent targeting and phishing tactics have led to periodic discovery by threat researchers. The latest campaign on February 28, 2022, targeted a diplomat from a European NATO country working in refugee and migrant services. The threat actor used a compromised email address to deliver a compressed archive containing a PE dropper and components of an updated Trident Loader PlugX malware payload. The PlugX malware payload has shown obfuscation and anti-analysis techniques, indicating ongoing development by TA416. The group's consistent victimology and tactics suggest a high level of confidence in attributing the recent campaigns to TA416. The report provides indicators of compromise (IOCs) for tracking and monitoring TA416's activities.


