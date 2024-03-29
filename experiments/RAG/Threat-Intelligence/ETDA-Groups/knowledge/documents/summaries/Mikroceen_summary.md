
Report 1

Malformed report.





Report 2

Summary:
- Threat actor "Mikroceen" targeted high-profile companies in Central Asia, including a telecommunications company, a gas company, and a governmental institution.
- The threat actor, possibly from China, used backdoors like sqllauncher.dll and logon.dll to gain long-term access to networks and evade AV detection.
- The group also utilized tools like Mimikatz and Gh0st RAT for lateral movement within networks.
- The backdoors allowed for file manipulation, screenshot capture, process manipulation, and data exfiltration to a C&C server.
- The threat actor showed capability in recompiling custom tools and using encryption techniques to make analysis difficult.
- The group's activities were linked to previous campaigns like Microcin, BYEBY, and Vicious Panda, with C&C servers registered to Choopa, LLC.
- Avast and ESET collaborated on the analysis, with indicators of compromise shared on GitHub.
- The threat actor's use of known tools and techniques, along with similarities in code, pointed to Chinese APT group involvement.
- Avast notified the targeted company and local CERT team, but no response was received, indicating ongoing threat activity in the region.





Report 3

Summary:
Between March 2nd and March 5th, multiple Advanced Persistent Threat (APT) groups, including LuckyMouse, Tick, Winnti Group, Calypso, Tonto Team, and Mikroceen, exploited Microsoft Exchange vulnerabilities (CVE-2021-26855, CVE-2021-26857, CVE-2021-26858, and CVE-2021-27065) to compromise email servers globally. The threat actors used webshells to install implants on victims' email servers, with evidence of backdoors, RATs, and password dumping tools being deployed. The Winnti Group, known for supply-chain attacks, compromised servers in East Asia, while Mikroceen targeted a utility company in Central Asia. The novel tools and techniques used, such as the Mikroceen RAT and IIS backdoors, demonstrate the evolving capabilities of these threat actors. The widespread exploitation of these vulnerabilities highlights the urgency for organizations to patch their Exchange servers. The operation timeframe ranged from March 2nd to March 5th, with over 5,000 unique servers in 115 countries affected.





Report 4

Summary:
- Threat actor named "Microcin" targeted a diplomatic entity in February 2020.
- The actor, also known as SixLittleMonkeys, used an enterprise-grade API-like programming style, uncommon in malware.
- The campaign involved steganography in images from cloudinary.com to deliver configuration data and modules.
- The threat actor showed a novel approach with asynchronous work with sockets and an API-like architecture.
- The network module used custom encryption and HTTP POST-based C2 communication.
- Commands included file operations, execution, and data transfer.
- Infrastructure included domains like apps.uzdarakchi.com and forum.mediaok.info.
- The campaign marked an advancement in software architecture for the threat actor.
- Indicators of compromise include downloader and network module MD5 hashes and associated domains and IPs.
- The report was published on June 19, 2020, by Denis Legezo from Kaspersky's GReAT team.





Report 5

Summary:
The threat actor Mikroceen, also known as SixLittleMonkeys, has been active since 2017, targeting companies in the telecommunications and gas industries, as well as governmental entities in Central Asia. The actor has been linked to various malware campaigns, including Microcin against Russian military personnel and BYEBY against the Belarussian government. Mikroceen's motivation is information theft and espionage, with observed tool usage including Gh0st RAT and Mimikatz. The threat actor originates from China and has targeted victims in Belarus, Mongolia, Russia, and Central Asia. The latest reported hacking operation involved attacks on Exchange servers by at least 10 APT groups in March 2021.


