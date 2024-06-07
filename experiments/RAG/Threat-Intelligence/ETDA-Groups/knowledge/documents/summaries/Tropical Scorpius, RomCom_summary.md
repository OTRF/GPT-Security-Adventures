
Report 1

Summary:
- Threat actor named Tropical Scorpius observed deploying Cuba Ransomware using novel tools and techniques since early May 2022.
- Victims targeted across various sectors including Professional and Legal Services, State and Local Government, Manufacturing, Transportation and Logistics, Wholesale and Retail, Real Estate, Financial Services, Health Care, High Technology, Utilities and Energy, Construction, and Education.
- Novel tools and techniques used include ROMCOM RAT, weaponized local privilege escalation exploit, KerberCache tool, kernel driver for targeting security products, and ZeroLogon hacktool.
- Evidence of capability includes ransom payments totaling $43.9 million and demands of at least $74 million.
- Operating sector of victims targeted includes multiple industries in the United States.
- Tools used for local privilege escalation and lateral movement include CVE-2022-24521 exploit, Kerberoasting, Mimikatz, and custom Kerberos tool named KerberCache.
- Command and control infrastructure includes ROMCOM RAT with unique C2 protocol and ICMP capabilities.
- Recommendations for mitigation include advanced logging, patching systems, deploying XDR/EDR solutions, and performing threat hunting.
- Indicators of compromise include hashes for driver dropper, ZeroLogon hacktool, Cuba Ransomware, privilege escalation tool, KerberCache hacktool, and ROMCOM RAT.
- Infrastructure associated with the threat actor includes CombinedResidency[.]org and optasko[.]com.
- Report updated on August 10, 2022, and November 8, 2022, to remove erroneous IoC for ROMCOM RAT.





Report 2

The RomCom threat actor has been targeting Ukraine and potentially the United Kingdom through new attack campaigns utilizing SolarWinds, KeePass, and PDF Technologies. The threat actor impersonated legitimate products like SolarWinds Network Performance Monitor, KeePass Open-Source Password Manager, and PDF Reader Pro. The threat actor's capabilities include spoofing legitimate websites, Trojanizing applications, and deploying targeted phishing emails. The RomCom threat actor's novel techniques involve creating fake websites to mimic real ones and dropping malicious bundles onto victims' machines. The threat actor's motivation is unclear, but the campaigns show a connection to other threat actors like Cuba Ransomware and Industrial Spy. The RomCom threat actor's activities have been ongoing, with indicators of compromise identified in the report. The report was published on November 2, 2022, by the BlackBerry Research & Intelligence Team.





Report 3

Summary:
The RomCom threat actor targeted Ukraine's NATO membership talks at the NATO Summit by sending malicious documents as lures to organizations supporting Ukraine abroad and guests of the upcoming NATO Summit. The threat actor utilized RTF exploitation in the documents to initiate outbound connections from victims' machines. The threat actor used spear-phishing techniques, typosquatting, and cloned websites to deceive victims. The threat actor leveraged a zero-day vulnerability (CVE-2022-30190) affecting Microsoft's Support Diagnostic Tool to conduct remote code execution attacks. The RomCom threat actor employed a downloader to establish connections to remote servers and collect system information. The network infrastructure used by the threat actor overlapped with known RomCom infrastructure, indicating a high likelihood of the same threat actor. The campaign targeted representatives of Ukraine, foreign organizations, and individuals supporting Ukraine. The threat actor demonstrated a medium to high level of confidence in being associated with the RomCom threat group based on geopolitical context, domain registration, code similarities, and network infrastructure. The report was published on July 8, 2023, by the BlackBerry Research & Intelligence Team.





Report 4

Summary:
- Threat actor: Storm-0978, also known as RomCom
- Region: Europe and North America
- Operating sector: Defense, government, telecommunications, finance
- Storm-0978 is a Russian cybercriminal group involved in ransomware, extortion, and espionage operations targeting defense and government entities.
- They exploit vulnerabilities like CVE-2023-36884 to deliver backdoors like RomCom and conduct phishing campaigns related to Ukrainian political affairs.
- Storm-0978 uses trojanized versions of legitimate software, deploys ransomware like Industrial Spy and Underground, and acquires exploits targeting zero-day vulnerabilities.
- The actor has targeted organizations primarily in Ukraine, Europe, and North America, impacting government, military, and financial sectors.
- Microsoft Defender detects Storm-0978's activities and provides mitigation recommendations.
- Storm-0978's ransomware and espionage activities are distinct, with espionage operations driven by financial and intelligence motives.
- Microsoft has linked Storm-0978 to previous ransomware operations and identified espionage campaigns since late 2022.





Report 5

Summary:
The threat actor known as Tropical Scorpius, also operating under the alias RomCom, has been active since 2019, with recent reports indicating the use of Cuba Ransomware to target organizations across various sectors such as Professional Services, Government, Healthcare, and Education. The group has impacted a total of 60 organizations, with a focus on information theft, espionage, and financial gain. The threat actor is believed to originate from Russia and has been observed using tools like Cuba, Industrial Spy, ROMCOM RAT, and Underground. Recent hacking operations include spoofing popular apps to target Ukrainian militaries, abusing KeePass and SolarWinds to target Ukraine and potentially the United Kingdom, and targeting female political leaders with new ROMCOM variants. The threat actor's capabilities and novel techniques have been highlighted in reports from various cybersecurity firms like Palo Alto, Trend Micro, and Microsoft. The threat actor's activities pose a significant risk to organizations in sectors such as Construction, Education, Energy, Financial, Government, Healthcare, High-Tech, Manufacturing, Shipping and Logistics, and Transportation.





Report 6

The RomCom threat actor, previously unknown, has been targeting Ukrainian military institutions by deploying spoofed versions of popular software such as "Advanced IP Scanner" and "PDF Filler." The threat actor has shown the capability to actively develop new capabilities, as seen in the switch from one application to another. The initial campaign occurred on July 23, 2022, with improvements in evasion techniques observed on October 10, 2022. The threat actor has been distributing the RomCom RAT through fake websites spoofing legitimate applications, with the latest campaign targeting military institutions in Ukraine on October 21. The threat actor has also targeted IT companies, food brokers, and food manufacturing in the U.S., Brazil, and the Philippines. The RomCom RAT threat actor is actively developing new techniques and campaigns, with no apparent link to any attributed threat actor at the time of publication. The threat actor's tools and techniques show a level of sophistication and novelty, posing a significant threat to victims worldwide.





Report 7

Summary:
The threat actor "Void Rabisu" targeted female political leaders with a new variant of the ROMCOM backdoor. Operating in the region of Ukraine and countries supporting Ukraine, the threat actor has targeted government and military entities, energy and water utility sectors, EU politicians, and security conference participants. Void Rabisu has shown capabilities of signing malware with certificates, employing malicious advertisements on search engines, and exploiting vulnerabilities like CVE-2023-36884. The threat actor used a new variant of the ROMCOM backdoor, dubbed "ROMCOM 4.0" or "PEAPOD," in campaigns targeting attendees of the Women Political Leaders Summit in August 2023. Void Rabisu's novel technique involves TLS-enforcing by the ROMCOM C&C servers to evade detection. The threat actor's activities suggest a shift towards cyberespionage, possibly influenced by the geopolitical circumstances surrounding the war in Ukraine.





Report 8

Summary:
The threat actor Void Rabisu, also known as Tropical Scorpius, has been using the RomCom backdoor in attacks since at least October 2022, showing a shift in motives from financial gain to geopolitical goals. The RomCom backdoor has been used in attacks against the Ukrainian government and military, targeting organizations in Ukraine's energy and water utility sectors, as well as entities in Europe and the US. The threat actor employs novel techniques such as binary padding, obfuscation with VMProtect, and COM hijacking for persistence. The use of fake companies and websites to sign malware binaries adds a layer of sophistication to the attacks. The evolving capabilities of the threat actor and the tools used indicate a growing alignment between financially motivated cybercriminals and APT actors in the current geopolitical landscape. The report provides detailed insights into the tactics, techniques, and procedures employed by Void Rabisu, highlighting the need for enhanced endpoint security solutions to mitigate the risks posed by such threat actors.


