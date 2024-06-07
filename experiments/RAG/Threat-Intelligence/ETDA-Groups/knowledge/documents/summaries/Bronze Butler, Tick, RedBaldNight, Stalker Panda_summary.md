
Report 1

Summary:
The threat actor known as Tick, identified by Symantec, has been conducting cyberespionage campaigns primarily targeting Japanese organizations for at least 10 years. Tick utilizes custom-developed malware called Daserf for information stealing purposes, focusing on sectors such as technology, aquatic engineering, and broadcasting in Japan. The group employs spear-phishing emails, watering hole attacks, and a range of hacktools to map victim networks and escalate privileges. Tick's malware, Daserf, uses tactics to avoid detection, such as hiding stolen data in password-protected archives and using file and folder names related to legitimate programs. The threat actor also uses compromised web servers and its own infrastructure for command and control purposes. Tick has been observed using stolen digital certificates in some cases and has targeted large Japanese technology, engineering, and media firms. The group's activity dates back to 2006, indicating a well-organized and advanced cyberespionage group with a narrow focus on specific industries in Japan. Protection against Tick's threats is provided by Symantec and Norton products.





Report 2

The Tick group, operating mainly in Korea and Japan since 2014, has targeted sectors such as aerospace, military, defense industries, heavy industries, electronics, telecommunications, government agencies, and diplomacy. They have been active for over a decade and are suspected to still be operating covertly. The group used a modified Q-Dir variant to drop a ReVBSHell backdoor and created an FTP server file in August 2022. Additionally, they utilized a ShadowPY variant in their attacks. The Tick group's ties to Operation Triple Tiang, a cyber attack campaign targeting political and diplomatic sectors in Korea, were revealed, indicating a high possibility of their involvement. The group's capabilities include sophisticated malware and techniques, posing a significant threat to various industries and government agencies in the region. (Report date: April 17, 2023)





Report 3

Summary:
The threat actor known as BRONZE BUTLER, also referred to as Tick, has been targeting Japanese enterprises, with operations originating in the People's Republic of China. The threat group focuses on exfiltrating intellectual property and confidential data from organizations involved in critical infrastructure, heavy industry, manufacturing, and international relations. They employ spearphishing, strategic web compromises, and zero-day vulnerabilities to compromise systems, with a capability to develop proprietary malware tools and encrypted command and control protocols. BRONZE BUTLER has demonstrated a long-standing presence in compromised networks, with the ability to remain undetected for up to five years. The threat actor utilizes a variety of proprietary and publicly available tools for reconnaissance, lateral movement, and exfiltration, showcasing a high level of sophistication and resourcefulness. The group's tactics include leveraging compromised websites, exploiting vulnerabilities in popular Japanese software, and utilizing unique malware tools for exfiltration. The report provides detailed insights into the tools, techniques, and procedures employed by BRONZE BUTLER, highlighting the group's advanced capabilities and persistent targeting of Japanese organizations. The threat actor's operational infrastructure complexity and evasion tactics pose significant challenges for network defenders and incident responders. (Source: Secureworks, Date: Not specified)





Report 4

Summary:
The threat actor known as Bronze Butler, also operating under aliases Tick, RedBaldNight, and Stalker Panda, has been active since 2006 and primarily targets organizations in Japan. The threat group, sponsored by the National University of Defense and Technology in China, engages in information theft and espionage, focusing on critical infrastructure, defense, engineering, government, high-tech, manufacturing, and international relations sectors. They use a variety of tools such as Gh0st RAT, Mimikatz, and ShadowPad Winnti, with novel techniques like weaponizing secure USB drives and exploiting vulnerabilities in software widely used in Japan. Notable operations include the 2015 Tick attacks compromising Japanese websites, the 2019 Operation "ENDTRADE" targeting specific industries in Japan, and the 2021 breach of Mitsubishi Electric. Counter operations have been initiated, with a Chinese man linked to the cyberattacks being referred to prosecutors by Tokyo police in April 2021.





Report 5

Summary:
- Threat actors including LuckyMouse, Tick, Winnti Group, Calypso, and others exploited Microsoft Exchange vulnerabilities (CVE-2021-26855, CVE-2021-26857, CVE-2021-26858, and CVE-2021-27065) to compromise email servers globally.
- Evidence of at least 10 APT groups leveraging the vulnerabilities to install implants on victims' email servers was found.
- Novel techniques included the use of webshells in Offline Address Book configuration files and DLL search-order hijacking against legitimate executables.
- Threat actors like Tick targeted companies in East Asia providing IT services, while LuckyMouse targeted a governmental entity in the Middle East.
- Calypso compromised email servers of governmental entities in the Middle East, South America, Africa, Asia, and Europe.
- Websiic targeted private companies in Asia and a governmental body in Eastern Europe.
- Winnti Group compromised email servers of an oil company and a construction equipment company in East Asia.
- Mikroceen targeted a utility company in Central Asia.
- DLTMiner deployed PowerShell downloaders on multiple email servers.
- The "Opera" Cobalt Strike threat actor targeted servers in the US, Germany, and the UK.
- Multiple APT groups had access to the exploit before the patch release, indicating widespread exploitation.
- Recommendations include patching Exchange servers, removing webshells, changing credentials, and monitoring for malicious activity.





Report 6

Summary:

- Threat actor: Bronze Butler, Tick, RedBaldNight, Stalker Panda
- Region: China is the main suspect
- Operating sector: Mitsubishi Electric
- Evidence of capability: Sophisticated tools and techniques used
- Novelty of tools: Not specified
- Date: Not specified

Overall, the threat actor group, including Bronze Butler, Tick, RedBaldNight, and Stalker Panda, targeted Mitsubishi Electric in a security breach, with China being the main suspect. The group demonstrated sophisticated capabilities in their attack, using advanced tools and techniques. The specific novelty of the tools used was not mentioned in the report. The date of the operation was not provided.





Report 7

Summary:
The threat actor known as REDBALDKNIGHT, also identified as BRONZE BUTLER and Tick, has been targeting Japanese organizations such as government agencies, biotechnology, electronics manufacturing, and industrial chemistry sectors. They utilize the Daserf backdoor with capabilities including executing shell commands, data download/upload, screenshots, and keystroke logging. Recent telemetry indicates that REDBALDKNIGHT has expanded its targets to include Russian, Singaporean, and Chinese enterprises. The threat actor has been active since at least 2008, using social engineering tactics with Japanese-language decoy documents. They have integrated steganography into their operations to conceal second-stage backdoors and C&C communication, enhancing their ability to evade detection. The use of steganography is not limited to Daserf, as other toolkits employed by REDBALDKNIGHT also utilize this technique. Mitigation strategies include enforcing least privilege, network segmentation, access control, intrusion detection, and keeping systems up-to-date. Trend Micro's Deep Discovery and Deep Security solutions provide defense against such targeted attacks. The report provides detailed insights into the threat actor's tactics, techniques, and procedures, emphasizing the need for proactive cybersecurity measures.





Report 8

Summary:
The threat actor known as "Bronze Butler, Tick, RedBaldNight, Stalker Panda" has been identified as the creator of the ShadowWali backdoor, a new variant of the xxmm family of backdoors targeting Japanese businesses. The threat actor has been active since 2015 and has developed multiple malware tools, including Wali and ShadowWali. Evidence suggests that the threat actor has been customizing and adapting tools and techniques, such as reflective loader and Metasploit modules. The backdoors use large inflated executables to evade traditional security products and employ process injection techniques, with ShadowWali injecting into LSASS.exe and explorer.exe. The threat actor utilizes legitimate and fake Japanese websites for C2 infrastructure, with compromised sites hosted by GMO Internet Group. The xxmm builder, used to generate the backdoors, indicates a connection to the ShadowWalker rootkit, although rootkit functionality was not observed in the backdoors. The threat actor remains unidentified, but evidence suggests an Asian origin. The backdoors have been effective in infecting endpoints and evading detection, with ShadowWali showing variations and improvements compared to Wali. The threat actor's capability lies in the customization and adaptation of tools, as well as the use of inflated file sizes to evade detection. The backdoors continue to target Japanese organizations actively.





Report 9

Tick, a cyberespionage group targeting organizations in Japan and the Republic of Korea, was found to have weaponized secure USB drives to target air-gapped critical systems. The group used custom malware such as Minzen, Datper, Nioupale, and HomamDownloader in their attack campaigns. Tick specifically targeted a secure USB drive created by a South Korean defense company, likely in an effort to compromise air-gapped systems. The malware used in these attacks only targeted systems running Microsoft Windows XP or Windows Server 2003, indicating intentional targeting of older, out-of-support versions of Windows. The attack scenario involved compromising the USB drive, loading a malicious file named SymonLoader, and attempting to infect specific systems. The novel technique of weaponizing a secure USB drive is uncommon and likely aimed at compromising systems that do not connect to the public internet. The attack was hypothesized to have occurred multiple years ago, and the full attack sequence remains incomplete. The report provides detailed technical information on the attack methodology and indicators of compromise.





Report 10

The threat actor known as "Tick" group has been conducting cyber espionage attacks against organizations in the Republic of Korea and Japan, focusing on companies in the Defense and High-Tech industries. They use custom malware called Daserf along with multiple commodity and custom tools, exploit vulnerabilities, and employ social engineering techniques. Tick has been observed attacking high-profile targets in Japan for the last three years. They have also been linked to other threats like Invader and 9002, with shared infrastructure dating back to 2012-2013. Tick has also been associated with the Minzen malware, which includes a backdoor module called NamelessHdoor, based on the Nameless Backdoor code from 2005. Additionally, Tick has been found using a custom variant of the Gh0st RAT, with shared infrastructure and cipher code. The threat actor has been observed using spearphishing emails with a patched file encryption program called HomamDownloader to target victims. The report provides indicators of compromise and ways for Palo Alto Networks customers to protect themselves from these threats. The report was published on July 24, 2017.


