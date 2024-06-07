
Report 1

Summary:
- Threat actor named BackdoorDiplomacy, also known as Ke3chang, Vixen Panda, APT 15, GREF, Playful Dragon, has been targeting Ministries of Foreign Affairs and telecommunication companies in Africa and the Middle East since at least 2017.
- They exploit vulnerable internet-exposed devices like web servers and networking equipment interfaces for initial infection.
- They use open-source tools for scanning and lateral movement, with a custom backdoor called Turian derived from Quarian.
- The group has targeted Ministries of Foreign Affairs in African countries, Europe, Middle East, and Asia, as well as telecommunication companies and a Middle Eastern charity.
- They have been observed using DLL Search-Order Hijacking and targeting removable media for data collection and exfiltration.
- The threat actor operates on both Windows and Linux systems, with a focus on obfuscation and persistence techniques.
- Turian, the backdoor used, shares similarities with Quarian and employs unique network encryption schemes.
- The group also uses open-source remote access tools like Quasar for more interactive access.
- The report provides IoCs, MITRE ATT&CK techniques used, and details on the network encryption protocols used by the threat actor.
- The report was published on June 10, 2021, by ESET Research.





Report 2

Summary: The threat actor known as Ke3chang, Vixen Panda, APT 15, GREF, Playful Dragon has been identified conducting a new campaign in the Middle East region. The victims targeted were companies in the Middle East operating in the diplomatic sector. The threat actor demonstrated advanced capabilities with the use of novel tools and techniques in this campaign. The operation time window was not specified in the report. For more information, refer to the source provided.





Report 3

Summary:
- Threat actor: Playful Taurus, also known as APT15, BackdoorDiplomacy, Vixen Panda, KeChang, and NICKEL.
- Region: Iran
- Operating sector: Government
- Date: January 18, 2023
- The threat actor, a Chinese advanced persistent threat group, has been active since at least 2010 and targets government and diplomatic entities across North and South America, Africa, and the Middle East.
- In June 2021, the group upgraded their toolkit to include a new backdoor called Turian, exclusively used by Playful Taurus actors.
- Evidence suggests that several Iranian government networks have likely been compromised by Playful Taurus.
- The threat actor's infrastructure includes domains targeting diplomatic entities and telecommunications companies across Africa and the Middle East.
- The threat actor uses unique XOR decryption functions and network protocols, with recent upgrades indicating evolving tactics and tooling.
- Palo Alto Networks provides protections against the threats described, including Advanced URL Filtering, DNS Security, Cortex XDR, and WildFire malware analysis.





Report 4

Malformed report





Report 5

The report provides information on the threat actor "Ke3chang, Vixen Panda, APT 15, GREF, Playful Dragon" targeting victims in the region of unknown. The threat actor has been identified as APT15 and has demonstrated capabilities in developing tools such as a .net tool to enumerate the victim's SharePoint database. Additionally, decoder scripts for BS2005 and RoyalCLI samples were found, along with Yara signatures and Suricata signatures for various samples. The report does not specify the operating sector or type of company targeted by the threat actor. The tools and techniques used by the threat actor show a level of sophistication and novelty. The report does not include a specific date or operation time window.





Report 6

Malformed report





Report 7

Ke3chang, also known as Vixen Panda, APT 15, GREF, and Playful Dragon, is a threat group operating out of China since at least 2010. They have targeted various industries, including oil, government, military, and more, in countries worldwide. The threat actor is state-sponsored, motivated by information theft and espionage. Ke3chang has used a wide range of tools and techniques, including BS2005, Cobalt Strike, Mimikatz, and more, demonstrating a high level of capability. They have been involved in multiple hacking operations, such as Operation "Ke3chang" in 2010 targeting European MFAs during the Syrian crisis. The threat actor has evolved their custom malware arsenal over the years, with new tools like TidePool in 2016 and MirageFox in 2018. Ke3chang has continued to be active, with new samples like Ketrum in 2020 and ongoing campaigns like BackdoorDiplomacy targeting government organizations. Their novel tools and techniques, along with their extensive target list, make Ke3chang a persistent and evolving threat actor in the cybersecurity landscape.





Report 8

Summary:
- Threat actor NICKEL, associated with China-based APT15, APT25, and KeChang, targeted government organizations, diplomatic entities, and NGOs across Latin America, Europe, and North America.
- Microsoft Digital Crimes Unit seized NICKEL-operated websites and disrupted ongoing attacks in 29 countries.
- NICKEL used exploits against unpatched systems, credential dumpers, custom malware for persistence, and routine data exfiltration.
- Novel tools and techniques included using malware families like Leeson, Neoichor, and NumbIdea for command and control, deploying keyloggers, and using Mimikatz for credential theft.
- NICKEL compromised networks through attacks on web applications and VPN appliances, and used compromised credentials for routine email collection.
- Evidence of routine host data collection and exfiltration was observed, with specific examples of archiving data using rar.exe and 7z.exe.
- Microsoft provided recommended defenses, IOCs, detections in Microsoft 365 Defender, and advanced hunting queries in Microsoft Sentinel.
- The operation time window was from September 2019 to the present, with ongoing monitoring and protection efforts by Microsoft.





Report 9

The threat actor known as Ke3chang, also referred to as APT15, has been targeting diplomatic missions primarily in Europe, with activities dating back to 2010. ESET researchers have identified a previously undocumented malware family named Okrum, linked to the Ke3chang group, which was first detected in December 2016. The victims targeted by Okrum included diplomatic missions in Slovakia, Belgium, Chile, Guatemala, and Brazil. Additionally, new versions of known malware families attributed to Ke3chang, such as BS2005 backdoors and RoyalDNS malware, were detected from 2015 to 2019. The threat actor's capability is evidenced by the use of advanced techniques, including steganography to hide malicious payloads in PNG files, and the use of external tools for malicious activities. The threat actor's persistence and evasion techniques, as well as the evolution of their code over time, indicate a high level of sophistication. The report provides detailed technical information on the tools and techniques used by the threat actor, showcasing their advanced capabilities.





Report 10

Summary:
- Threat actor: Ke3chang, Vixen Panda, APT 15, GREF, Playful Dragon
- Region: Global, with a focus on Indian embassy personnel worldwide
- Operating sector: Indian embassies in different countries
- Type of company: Indian embassies
- Date: May 22, 2016
- Evidence of capability: Continued evolution of custom malware arsenal, targeting Indian embassy personnel, exploiting CVE-2015-2545, reuse of code responsible for registry changes and command and control traffic, behavioral ties to Ke3chang
- Novelty of tools and techniques: New malware family named TidePool, strong behavioral ties to Ke3chang, exploitation of relatively new vulnerability, reuse of code from BS2005 malware family, modification of registry keys, URL beacon creation, C2 obfuscation routine
- Conclusion: Operation Ke3chang has continued operations and developed new malware, with a focus on Indian embassies, indicating a high priority target.





Report 11

Summary:
The threat actor known as Ke3chang, APT15, targeted high-profile entities across multiple continents, including European ministries, Indian embassies, and British military contractors. The group has been active since 2010 and is backed by the Chinese government. In mid-May, new samples named "Ketrum" were identified, merging features from older APT15 implants. The operation was recent, with samples connecting to the same C2 server in two different time periods. The new samples show the evolution of APT15's codebase, with differences in backdoor functionalities and communication techniques. The threat actor continues to use basic backdoors to gain control over victims' devices, with a focus on manual command execution. The tools used by APT15, such as Ketrum, show a mix of old and new techniques, indicating the group's persistence in adapting their TTPs. The report provides technical analysis and IOCs for tracking APT15's activities. (Date: May 2020)


