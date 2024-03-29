
Report 1

Malformed report





Report 2

Summary:

- Threat actor known as SectorM04 targeted Singapore's SingHealth database in June 27, 2018, exfiltrating personal data of 1.5 million people.
- Multiple malware pieces were used in the attack over a year, with evidence linking the attack to a threat group known as SectorM04.
- Novelty in the tools and techniques used include a decoy document with a malicious executable disguised as a benign Word document.
- The malware used DLL side loading to load a malicious DLL file abusing the DLL search order, along with a shellcode file.
- Persistence mechanisms involved creating a service named "WanServer" and using the run registry key to run the malware.
- The malware beaconed using HTTPS POST on port 443 and set inline hooks on certain DLL functions for defense evasion.
- Information collected included OS versions, NetBIOS name, MAC address, and logged-on username.
- The malware exhibited reverse shell capabilities and had additional modules for further actions.
- IoCs included hashes for the PlugX Trinity components and network information for domains and IP addresses.
- References to COI report, Symantec blog, and other sources provided additional context to the threat actor's capabilities.

Date: June 27, 2018 (SingHealth breach)
Operation Time Window: Almost a year

Source: https://redalert.nshc.net/2019/03/19/sectorm04-targeting-singapore-custom-malware-analysis/





Report 3

Summary:
The threat actor known as Whitefly/Mofang, likely operating out of China and possibly government-affiliated, has been targeting organizations involved in investments or technological advances perceived as a threat to Chinese interests. They have conducted campaigns in Myanmar, focusing on government and critical infrastructure, as well as attacking various sectors in multiple countries including automotive, defense, and government. Their motivation is information theft and espionage. The threat actor has been observed using tools such as Mimikatz, Nibatad, and ShimRAT, indicating advanced capabilities. The novelty of their techniques includes the use of custom malware like SectorM04. The first sighting of this threat actor was in 2012, with reported hacking operations including the breach of SingHealth in 2018. The threat actor has targeted victims in countries like Canada, Germany, and the USA.


