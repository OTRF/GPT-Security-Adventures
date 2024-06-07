
Report 1

Malformed report





Report 2

The threat actor known as Reaper, APT 37, Ricochet Chollima, ScarCruft, conducted a series of attacks named 'Operation Battle Cruiser' targeting specific users in South Korea using spear phishing techniques. The attacks utilized vulnerabilities in HWP document files and Flash Player Zero-Day (CVE-2018-4878) to deliver malicious payloads. The threat actor employed fileless malware and DLL-based files disguised as video files (battle32.avi, battle64.avi) to evade detection. The tools and techniques used by the threat actor showed similarities to previous Lazarus group campaigns and were linked to state-sponsored actors. The attacks were ongoing as of April 11, 2018, and targeted various sectors including defense, finance, and cryptocurrency exchanges. The threat actor's activities demonstrated advanced capabilities and a high level of sophistication in their operations.





Report 3

Malformed report.





Report 4

Summary:
- Threat actor: ScarCruft APT group
- Date: June 17, 2016
- Region: Russia and Asia
- Operating sector: High-profile targets including an Asian law enforcement agency, a large Asian trading company, an American mobile advertising company, and individuals affiliated with the International Association of Athletics Federations (IAAF)
- Evidence of capability: ScarCruft APT group used a Flash zero-day vulnerability in targeted attacks against more than two dozen victims, implementing read/write operations for full remote code execution and bypassing antivirus detection using Windows DDE.
- Novelty of tools and techniques: ScarCruft APT group's tools and techniques are described as professional and focused, with the use of Flash exploits, watering hole attacks, and exploit kits to redirect victims' browsers to a server controlled by the attackers.
- Adobe patched the zero-day vulnerability in Flash Player, with the update addressing 36 vulnerabilities in total, including memory corruption flaws, type-confusion, use-after-free, buffer overflow, and directory search path vulnerabilities.
- ScarCruft APT group's deployment of zero-day exploits against high-profile targets indicates their resourcefulness and persistence in exploiting vulnerabilities.
- Adobe's efforts to introduce new exploit mitigations into Flash Player have made it more difficult for researchers to find bugs, reducing the frequency of in-the-wild Flash Player exploits.
- ScarCruft APT group's operations, including Operation Daybreak and Operation Erebus, demonstrate their advanced capabilities and ongoing threat to high-profile targets in the region.





Report 5

Summary: The threat actor known as RedEyes (also identified as APT37, ScarCruft) has been distributing CHM malware disguised as security emails from a Korean financial company to Korean users. The malware, identified by AhnLab Security Emergency response Center, utilizes a steganography technique to deceive users. The malicious script within the CHM file is activated upon execution, leading to potential damage to infected systems. The malware is capable of downloading files and extracting information based on the threat actor's commands. The attack process involves the execution of encoded PowerShell commands and the establishment of persistence through the registry. The threat actor's server is used to transmit command execution results. The malware targets specific users in Korea by incorporating content of interest to lure them into executing the malware. Users are advised to refrain from opening emails from unknown sources and regularly update security products. The report was posted on March 9, 2023, by ASEC.





Report 6

Summary:
In August 2023, SentinelOne identified an intrusion into the Russian defense industrial base, specifically a missile engineering organization NPO Mashinostroyeniya, by North Korean threat actors. The threat actors compromised the organization's internal IT infrastructure, including an email server, using a Windows backdoor named OpenCarrot. The email server compromise was attributed to the ScarCruft threat actor, while a Lazarus Group backdoor was also used for network compromise. The intrusion, discovered in mid-May 2022, provided insights into North Korean cyber espionage campaigns targeting high-value organizations globally. The threat actors demonstrated advanced technical capabilities and utilized novel tools and techniques, such as the OpenCarrot backdoor with over 25 commands for reconnaissance, filesystem manipulation, and C2 communication. The infrastructure analysis revealed connections to known North Korean threat actors and highlighted the potential sharing of resources and infrastructure among them. The incident underscores the proactive measures taken by North Korea to advance their missile development objectives through covert cyber operations.





Report 7

Summary:
The threat actor known as STARK#MULE has been identified by Securonix Threat Research targeting Korean-speaking victims using US military document lures. The campaign is suspected to originate from North Korea and is reminiscent of past attacks by groups like APT37. The attack chain involves phishing emails with zip file attachments containing malicious PowerShell scripts. The malware is staged from compromised Korean e-commerce websites, allowing the threat actor to evade detection. The final stage involves a persistent malware embedded in the victim's machine that communicates over HTTP. The threat actor's infrastructure is based on two compromised Korean websites. The malware establishes persistence through scheduled tasks and communicates with a C2 server to exfiltrate system details. The attack utilizes novel techniques such as using Thumbs.db to execute PowerShell code and leveraging legitimate binaries for malicious activities. The campaign poses a significant threat to organizations, especially those in the South Korean region. (Report date: Jul 28, 2023, updated August 1, 2023)





Report 8

Malformed report.





Report 9

Malformed report.





Report 10

The FreeMilk spear phishing campaign, identified by Palo Alto Networks Unit 42 in May 2017, targeted various individuals worldwide using the CVE-2017-0199 Microsoft Word Office/WordPad Remote Code Execution Vulnerability. The threat actor hijacked legitimate email conversations to send malicious spear phishing emails from compromised accounts tied to a legitimate domain in North East Asia. The campaign delivered two malware payloads, PoohMilk and Freenki, to victims, including a bank in the Middle East, trademark and intellectual property service companies in Europe, an international sporting organization, and individuals with ties to North East Asia. PoohMilk acted as the first stage loader, setting up persistence in the registry and executing the second stage payload, Freenki. Freenki collected host information and served as a second stage downloader, communicating with its C2 server and executing various functions based on arguments passed. The threat actor used novel techniques, such as hijacking email conversations and delivering multiple malware payloads, to evade detection. The campaign is still ongoing, with the threat actor attempting to stay under the radar by carefully crafting decoy documents and leveraging existing conversations. The threat actor has been linked to previous campaigns involving N1stAgent RAT and a watering hole attack targeting visitors to an anti-government media website. The campaign demonstrates the threat actor's capability to conduct highly targeted attacks using sophisticated tools and techniques.





Report 11

Summary:
The threat actor known as RedEyes (ScarCruft) targeted individuals in Korea by exploiting the HWP EPS vulnerability using steganography to distribute malware. The group has a history of using steganography and Powershell for remote control. In a recent attack, a new malware strain named M2RAT was identified, utilizing shared memory for C&C commands. The threat actor's persistence techniques included autorun registration and registry key manipulation. M2RAT's exfiltration capabilities involved keylogging, data leakage, and screenshots sent to the threat actor's server. The group's focus on individual targets and advanced techniques make them a significant threat. The attack was discovered in January 2023.





Report 12

Malformed report.





Report 13

Summary:
The threat actor ITG10, also known as Reaper, APT 37, Ricochet Chollima, and ScarCruft, has been targeting South Korean entities related to the Democratic People's Republic of Korea (DPRK) since late April 2023. The threat actor employs phishing campaigns to deliver RokRAT malware, which allows for remote command execution, data exfiltration, and keylogging. ITG10's tactics overlap with APT37 and ScarCruft, using decoy documents to target South Korean government, universities, think tanks, and dissidents. The threat actor's novel techniques include using ISO files with modified PowerShell scripts and Hangul Word Processor decoy documents to deliver malware. The campaign suggests a focus on individuals and organizations involved in foreign policy related to the Korean peninsula. The threat actor's activities pose a significant risk to targeted organizations, requiring heightened vigilance and endpoint detection measures. The report provides indicators of compromise and recommendations for organizations to mitigate the threat. 

Date: June 6, 2023
Region: South Korea
Operating Sector: Government, Universities, Think Tanks, Energy, Manufacturing, Supply Chain
Type of Company: N/A





Report 14

Summary:
In late October 2022, Google's Threat Analysis Group (TAG) discovered a 0-day vulnerability in Internet Explorer exploited by North Korean actor APT37 to target users in South Korea. The vulnerability, CVE-2022-41128, was embedded in malicious documents, including one referencing a tragic incident in Seoul. APT37 historically targets South Korean users, North Korean defectors, policy makers, journalists, and human rights activists. The exploit used a unique delivery scenario involving remote RTF templates and HTML content to distribute IE exploits. The threat actor utilized a custom hashing algorithm in the shellcode to erase traces of exploitation. While the final payload was not recovered, APT37 is known to deploy implants like ROKRAT, BLUELIGHT, and DOLPHIN. Microsoft patched the vulnerability (CVE-2022-41128) on November 8, 2022. The threat actor's use of novel techniques and tools underscores their advanced capabilities in cyber operations.

Date: Late October 2022
Region: South Korea
Operating Sector: Various, including South Korean users, North Korean defectors, policy makers, journalists, and human rights activists
Type of Company: N/A
Novelty: Exploitation of Internet Explorer 0-day vulnerability, unique delivery scenario, custom hashing algorithm in shellcode, use of implants like ROKRAT, BLUELIGHT, and DOLPHIN
Capability: Advanced cyber capabilities demonstrated by APT37 in exploiting vulnerabilities and deploying sophisticated techniques.





Report 15

Summary:
The threat actor known as KONNI, previously associated with the North Korean group Kimsuky, has evolved its Remote Administration Tool (RAT) into a stealthier version. The group has been active for at least 8 years, targeting political institutions in Russia and South Korea. The latest attack involving the KONNI Rat showcased significant updates, including a simplified attack chain, removal of rundll support, and the use of AES encryption to protect strings and files. The threat actor has also employed obfuscation techniques, such as an unidentified packer, to evade detection. Recent attacks have moved away from using the packer. The constant code improvements by the threat actor aim to bypass sandbox detection and make traditional signature-based detection more challenging. Malwarebytes users are protected against this evolving threat. Date: January 26, 2022.





Report 16

Summary:
- Threat actor identified as APT 37 (aka: Ricochet Chollima, InkySquid, ScarCruft, Reaper, and Group123).
- Operating in the region of Russia and targeting Russian government addresses.
- Targeting victims in the Windows platform.
- Utilizing phishing emails written in Russian to deploy malware.
- Novel technique of including previous email threads to appear credible.
- Malicious attachment "Donbass.zip" containing PowerPoint files with decoy and malicious macros.
- Malicious macro in "Donbass.ppam" executes base 64-encoded PowerShell command.
- Attempted connection to C2 server at gg1593[.]c1[.]biz.
- Persistence mechanisms used to ensure continued access.
- Fortinet provides protections against this threat through various services.
- Date of report: September 19, 2022.





Report 17

Summary:
- Threat actor identified as Reaper, APT 37, Ricochet Chollima, ScarCruft targeted the Russian Ministry of Foreign Affairs (MID) in a new Konni campaign.
- The campaign involved leveraging the Konni malware associated with the Democratic People’s Republic of Korea for espionage purposes.
- The threat actor used phishing tactics to harvest credentials, deployed Covid-related lures, and targeted MID entities via malicious emails.
- Novel techniques included impersonating government software for Covid mandates and sending trojanized files from compromised accounts.
- The campaign spanned from October 2021 to December 2021, demonstrating patient and persistent nature of advanced actors.
- Black Lotus Labs, the threat research team of Lumen Technologies, uncovered the targeted actions.
- The threat actor's capability was evidenced by the use of malicious URLs, loaders, screensavers, and evasion techniques.
- Defensive measures advised include full network monitoring, multifactor authentication, and phishing awareness.
- Black Lotus Labs blocked the threat actor infrastructure and added indicators to their security portfolio.
- The analysis was performed by Danny Adamitis and Steve Rudd, emphasizing the evolving capabilities of advanced threat actors.





Report 18

Summary:
A new variant of the Konni malware was used in a spear phishing campaign targeting Russia in late July 2021. The malware was potentially linked to the North Korean APT group APT37. The threat actor used two different UAC bypass techniques and obfuscation tricks to evade detection. The campaign involved weaponized documents with malicious macros, JavaScript files executing batch and PowerShell scripts, and a heavily obfuscated final payload named Xmlprov.dll (Konni Rat). The malware collected victim machine information and exfiltrated it to attacker-controlled servers. The campaign targeted political organizations in Russia and South Korea, with past operations reported in 2019 and 2020. The new campaign showed differences in macro usage, obfuscation techniques, UAC bypass methods, and payload encryption compared to previous campaigns. Malwarebytes customers were protected against this campaign. The report did not specify the operation time window.





Report 19

Summary:
- Threat actor: InkySquid, associated with North Korean APT37
- Date: August 24, 2021
- Victims: Individual targeted by North Korean threat actors
- Evidence of capability: Deployed custom malware family BLUELIGHT alongside RokRAT (ScarCruft/APT37)
- Novelty of tools: BLUELIGHT used custom Google Web App for command and control, RokRAT used cloud services for communication
- Techniques: Malware loaded using convoluted mechanisms involving Python and Ruby scripts
- Recommendations: Block cloud storage resources, monitor for unusual scheduled tasks, use provided YARA rules for detection
- Conclusion: InkySquid linked to APT37, effective evasion of detection by antivirus programs
- Source: Volexity report titled "North Korean BLUELIGHT Special: InkySquid Deploys RokRAT" dated August 24, 2021.





Report 20

Reaper, also known as APT 37, Ricochet Chollima, and ScarCruft, is a state-sponsored threat actor originating from North Korea. The threat actor primarily targets victims in South Korea, Japan, Vietnam, and the Middle East across various sectors such as aerospace, automotive, manufacturing, and healthcare. Reaper has been active since 2012 and has demonstrated the capability to exploit zero-day vulnerabilities, particularly in Hangul Word Processor and Adobe Flash. The threat actor employs a diverse suite of malware for intrusion and exfiltration, including custom and destructive malware. Reaper's operations involve sophisticated social engineering tactics, strategic web compromises, and the use of torrent file-sharing sites to distribute malware. The group has shown an evolution in their operational security over time, utilizing compromised servers, messaging platforms, and cloud service providers for command and control infrastructure. The threat actor has been observed using a wide range of tools and techniques, including several 0-day Flash and MS Office exploits, as well as custom malware like Erebus, NavRAT, and RokRAT. The latest activity report from 2023 highlights ongoing operations such as "STARK#MULE" and "Distribution of Backdoor via Malicious LNK," indicating a continuous effort by Reaper to refine their attack tools and techniques.





Report 21

Summary:
The threat actor known as RedEyes (ScarCruft) has been distributing CHM malware related to the Fukushima wastewater release, targeting users in Korea. The malware uses a spotlight issue to lure users into opening malicious files, with commands similar to those used in previous attacks by the RedEyes group. The malware registers commands to the RUN key for persistence and executes additional scripts from a URL containing JavaScript code. This backdoor malware can download/upload files, edit the registry, and perform other malicious activities based on commands from the threat actor's server. Users are advised to avoid opening emails from unknown sources and regularly update security products. The operation was reported on September 8, 2023, by the AhnLab Security Emergency response Center (ASEC).





Report 22

RedEyes Group, also known as APT37, ScarCruft, and Reaper, is a state-sponsored threat actor targeting individuals such as North Korean defectors, human rights activists, and university professors in South Korea. In May 2023, they were found distributing an Infostealer with wiretapping capabilities and using a backdoor developed in GoLang that exploits the Ably platform for command and control. The threat actor's commands were sent through the GoLang backdoor using an API key value saved in a GitHub repository, allowing anyone with the key to subscribe and receive commands. This novel technique of using Ably for command communication was identified by AhnLab Security Emergency Response Center (ASEC) during their analysis. The RedEyes group employed spear phishing emails with CHM files disguised as password-protected documents to gain initial access to target systems. The malware used PowerShell scripts for persistence and backdoor functionality, with features like file exfiltration, registry editing, and task scheduling. The threat actor also utilized a known privilege escalation technique and executed an Infostealer named FadeStealer for data exfiltration, including wiretapping of microphones. The unique aspect of this attack was the use of AblyGo backdoor and GitHub repository for dynamic authentication key retrieval, showcasing the threat actor's advanced capabilities and evasion techniques. The attack flow, from initial access to exfiltration, was meticulously planned and executed by the RedEyes group, highlighting the need for vigilance and proactive defense measures against such sophisticated threats.





Report 23

Summary: APT37, also known as RedEyes or ScarCruft, a North Korean cyber espionage group, has been using a new malware strain called M2RAT to target individuals for intelligence collection. The group utilizes steganography and exploits an EPS vulnerability to deliver the malware, which acts as a remote access trojan capable of keylogging, data theft, command execution, and taking screenshots. The malware can scan for portable devices connected to Windows computers, such as smartphones, and exfiltrate data from them. The use of a shared memory section for command and control communication makes analysis challenging. ASEC observed these attacks starting in January 2023. The threat actor's capability to develop evasive malware highlights their sophistication and ongoing threat to targeted entities. 

Date: February 14, 2023

Region: North Korea

Operating Sector: Cyber espionage

Type of Company of Victims: Not specified

Novelty of Tools and Techniques: Use of steganography, exploitation of EPS vulnerability, shared memory section for C2 communication, data exfiltration, and direct transfer of stolen data.





Report 24

The threat actor known as APT37, also referred to as ScarCruft, Reaper, and Group123, has been identified using a VBA self-decode technique to inject the RokRat malware. The attack targeted the government of South Korea, with the document compilation date aligning with an attack almost a year ago. APT37 has been active since at least 2012, primarily targeting victims in South Korea. This attack marks a novel approach for the threat actor, using self-decoding VBA Office files, which is a first for this APT group. The final payload used by the threat actor is a known custom RAT (RokRat) that has been used in previous campaigns. The malware is capable of capturing screenshots, gathering system information, data exfiltration to cloud services, stealing credentials, and file and directory management. The sample compilation date for this attack was 29 Oct 2019. The threat actor used several anti-analysis techniques to avoid detection, including checking for specific DLLs and debugger presence. The attack vector used was spear phishing, with the malicious document weaponized with the RokRat malware injected into Notepad.exe. The threat actor's use of a self-decoding technique showcases their evolving capabilities and persistence in targeting victims.





Report 25

The threat actor known as RedEyes (ScarCruft), also identified as APT37, distributed the RokRAT malware through LNK files in April 2023. The malware is capable of collecting user credentials and downloading additional malware. The LNK files contained PowerShell commands to execute malicious behavior by creating and executing script files. The threat actor disguised the LNK files as legitimate PDF files to deceive victims. The malware was distributed to victims in the Korean financial sector. The threat actor used cloud services like pcloud and yandex to send collected information. The threat actor's capabilities include injecting malware into the PowerShell process to perform malicious activities. The threat actor's use of novel techniques, such as distributing malware through LNK files, demonstrates their evolving tactics.





Report 26

Summary:
The threat actor known as ScarCruft, also referred to as APT 37, Ricochet Chollima, and ScarCruft, has been tracked since 2016 and is believed to be a Korean-speaking, state-sponsored group targeting organizations with ties to the Korean peninsula. ScarCruft is highly skilled and resourceful, constantly evolving its attack tools. The threat actor utilizes multi-stage binary infection procedures to update modules effectively and evade detection. ScarCruft has been observed using public exploit code and a cloud-based backdoor known as ROKRAT to steal information from infected hosts. Additionally, ScarCruft has developed a Bluetooth device harvester to collect information on connected Bluetooth devices. Victims of ScarCruft include investment and trading companies in Vietnam and Russia, as well as diplomatic agencies in Hong Kong and North Korea. The threat actor has shown interest in political and diplomatic intelligence. ScarCruft's activities have overlapped with other threat actors like DarkHotel, indicating a complex threat landscape. The group is likely to continue evolving and expanding its exfiltration targets. The report provides indicators of compromise for ScarCruft tools and related malware. For more information, contact intelreports@kaspersky.com.





Report 27

Summary:
The threat actor known as ScarCruft, also referred to as APT37 or Temp.Reaper, has been surveilling North Korean defectors, journalists covering North Korea-related news, and government organizations related to the Korean Peninsula. The actor has been targeting victims in South Korea, utilizing spear-phishing emails and stolen login credentials to deliver malware. The actor has demonstrated a high level of sophistication by utilizing PowerShell malware, Windows executables, and Android applications with similar command and control schemes based on HTTP communication. The actor has been surveilling victims for several months, exfiltrating sensitive data, and attempting to infect additional hosts. The campaign has been ongoing since at least mid-2020, with infrastructure primarily based on compromised web servers in South Korea. The threat actor has shown a history of targeting individuals related to North Korea, indicating a likely connection to the ScarCruft group with medium confidence. The actor's TTPs include various techniques for initial access, execution, persistence, defense evasion, discovery, collection, command and control, and exfiltration. The campaign targets individuals rather than specific companies or organizations, with a focus on human rights activists and defectors.





Report 28

Summary:
The Securonix Threat Research team has observed a new attack campaign, STIFF#BIZON, possibly linked to Konni/APT37 (North Korea), targeting high-value victims in Czech Republic, Poland, and other countries. The attack involves phishing emails with malicious attachments containing Konni-based malware. The threat actor's capabilities include capturing screenshots, extracting state keys for offline decryption of cookies, and extracting browser logins and passwords. The attacker establishes C2 communication and uses various modules for data collection and command execution. The attack involves sophisticated techniques such as creating scheduled tasks for persistence and using PowerShell for execution. The threat actor's modus operandi includes reconnaissance activities and service installations for persistence. The report highlights the importance of securing credentials and implementing security measures to mitigate the risk of such attacks. The ongoing campaign is being tracked by the Securonix Threat Research team, with a focus on detecting and preventing similar attacks. The report provides indicators of compromise, MITRE ATT&CK techniques used by the threat actor, and hunting queries for detection. The report also emphasizes the need for up-to-date AV definitions, patching systems, and implementing security measures to prevent similar attacks.





Report 29

Summary:
- Threat actor: Reaper, APT 37, Ricochet Chollima, ScarCruft
- Region: Southeast Asia, primarily South Korea and North Korea
- Operating sector: Government agencies, cryptocurrency exchanges, political events
- Evidence of capability: Customized dropper CARROTBAT used to deliver malware, 29 unique CARROTBAT samples identified, overlaps with SYSCON and OceanSalt malware families
- Novelty of tools and techniques: CARROTBAT dropper allows for dropping and opening decoy files, rudimentary command obfuscation, use of DDE exploit, use of certutil utility for downloading and executing remote files
- Operation time window: March 2018 to September 2018
- Victims targeted: British government agency, individuals in Korea related to cryptocurrencies and political events
- Tools and techniques used: DDE exploit, certutil utility, decoy documents in various formats
- Infrastructure: Various domains and FTP servers used for C2 communication
- Conclusion: Suspected threat actor behind Fractured Block campaign, overlaps with KONNI and SYSCON activities, not enough evidence to attribute to a specific group with certainty.





Report 30

The Fractured Statue Campaign targeted a U.S. government agency between July and October 2019, using malware families associated with the Konni Group to lure targets into opening malicious email attachments related to North Korea. The campaign featured a new malware downloader called CARROTBALL, which facilitated the installation of the SYSCON Remote Access Trojan (RAT) via FTP for Command and Control (C2). The threat actor sent six unique malicious document lures to 10 targets, including U.S. government agency personnel and non-U.S. foreign nationals associated with North Korea. The campaign demonstrated evolution in tactics with the use of new downloader family and Word Document macros, but bore resemblance to a previous campaign called Fractured Block. The threat actor's TTPs included targeting individuals interested in North Korea, using phishing lures with North Korea-related content, and increasing payload delivery complexity. The activity is assessed with moderate confidence to be related to the Konni Group. The campaign utilized novel tools and techniques, such as the CARROTBALL downloader and FTP credential pairs for C2 operations. The threat actor's infrastructure included domains like handicap.eu5.org and IP addresses like 185.176.43.94. The report was published on January 23, 2020, by Unit 42 of Palo Alto Networks.





Report 31

Summary:
- Threat actor: GOLDBACKDOOR, associated with APT37, Ricochet Chollima
- Region: Democratic People’s Republic of Korea (DPRK)
- Operating sector: Targeting journalists specializing in DPRK
- Date: Spear-phishing campaign discovered on March 18, 2022
- Evidence: Malicious artifacts shared by NK News, including new malware sample GOLDBACKDOOR
- Capability: Medium-high confidence that GOLDBACKDOOR is successor or parallel to BLUELIGHT malware
- Novelty: Technical overlaps with APT37/Ricochet Chollima malware, impersonation of NK News
- Tools and techniques: Detailed technical process of GOLDBACKDOOR deployment outlined in report
- Source: Stairwell Threat Research team analysis based on shared artifacts and assessment

Malformed report.





Report 32

Malformed report.





Report 33

The threat actor known as 'Operation Star Cruiser' is a state-sponsored APT group that has been targeting South Korea with sophisticated cyber espionage activities. The group is believed to be linked to the Lazarus group and has been active since February 2018, using HWP document vulnerabilities. The threat actor's TTPs show strong similarities to a previous campaign named 'Operation Battle Cruiser'. The threat actor utilizes spear phishing attacks tailored to the South Korean environment, exploiting HWP vulnerabilities. The threat actor's tools and techniques show a high level of sophistication, with the use of implants, attribution, and infrastructure following a consistent pattern. The threat actor's capability is evidenced by the use of novel techniques such as combining CVE-2018-4878 and HWP vulnerabilities in their attacks. The threat actor's activities indicate a persistent and evolving threat to the South Korean cryptocurrency sector. The threat actor's operations demonstrate a high level of coordination and strategic targeting, posing a significant risk to targeted entities. The threat actor's activities highlight the need for enhanced threat intelligence research and security monitoring to mitigate potential risks.





Report 34

The threat actor known as Thallium, associated with North Korea, recently conducted a supply chain attack by tampering with a private stock investment messenger program. Thallium has previously been known to primarily use (spear) phishing attacks, such as 'Blue Estimate.' The messenger program was created in NSIS format and utilized the 'XSL Script Processing' technique to connect to a specific FTP server and download additional command files. The threat actor also created folders and connected to a server to execute additional commands. Thallium targeted stock investment users with the supply chain attack, showing a shift towards exploiting financial gains. The use of the 'XSL Script Processing' technique in both spear phishing and supply chain attacks is a notable aspect of Thallium's capabilities. The report was published on January 3, 2021.


