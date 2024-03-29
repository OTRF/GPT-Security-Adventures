
Report 1

APT 32, also known as OceanLotus or SeaLotus, is a state-sponsored threat actor originating from Vietnam. Since at least 2013, they have targeted foreign corporations with interests in Vietnam's manufacturing, consumer products, and hospitality sectors, as well as peripheral network security and technology infrastructure companies. They have also targeted foreign governments, Vietnamese dissidents, and journalists. APT 32 has used a variety of tools and techniques, including 0-day exploits in MS Office, Cobalt Strike, Mimikatz, and steganography to shroud payloads. Notable operations include "PhantomLance" in 2014, a mass digital surveillance campaign in 2017, and breaches of ASEAN websites. They have also targeted high-profile organizations like Toyota, BMW, and Hyundai. Counter operations against APT 32 have been reported, such as actions taken by Facebook in Bangladesh and Vietnam in 2020. Their activities have been observed in various sectors and countries, including ASEAN, Australia, China, the USA, and the UK.





Report 2

Summary: A report claims that Vietnamese hackers, specifically APT 32, also known as OceanLotus or SeaLotus, targeted BMW and Hyundai. The threat actor has demonstrated capability in targeting companies in the automotive sector. The attacks were reported in 2024, indicating recent activity. The tools and techniques used by the threat actor are considered novel and sophisticated. The victims targeted were companies in the automotive industry, specifically BMW and Hyundai. The threat actor's activities pose a significant risk to organizations in the region.





Report 3

Summary: A report from Bitdefender Labs highlights a recent Android campaign by the threat actor APT 32, also known as OceanLotus or SeaLotus. The campaign involved the abuse of a legitimate certificate and targeted users in the region. The threat actor's capability is evidenced by the use of novel techniques and tools, potentially older than previously estimated. The victims targeted were in the operating sector of consumer electronics, specifically Amazon Fire TV Stick, Insignia FireOS TV Series, and 2K Indoor Camera. The report was published in May 2020.





Report 4

Summary:
APT 32, also known as OceanLotus or SeaLotus, is a threat actor group operating in China. They have been selling access to compromised computers within Fortune 500 companies to perpetrate future breaches. The group uses Chinese-language VPN services marketed to evade censorship but are also used as a platform for launching attacks on non-Chinese corporations. The group, known as "Terracotta VPN," has over 1,500 nodes globally, with compromised Windows servers being used without the victims' knowledge. The group, also known as "Shell_Crew" or "Deep Panda," has been tied to major data breaches in the U.S., including the U.S. Office of Personnel Management and healthcare insurers Anthem and Premera. The group leverages at least 52 Terracotta VPN nodes to exploit sensitive targets among Western government and commercial organizations. The group's use of VPN services allows their espionage-related network traffic to blend in with legitimate VPN traffic. The group's novel approach involves using compromised servers to launch attacks and maintain anonymity. The report highlights the need for improved network security practices to prevent such compromises.





Report 5

Summary:
- Threat actor: APT32, also known as OceanLotus, SeaLotus.
- Region: Southeast Asia, specifically targeting private sector companies in Vietnam.
- Operating sector: Private sector companies in various industries, including manufacturing, consumer products, hospitality, banking, media, and technology infrastructure.
- Date: Activities observed since at least 2014.
- Evidence of capability: APT32 leverages a unique suite of fully-featured malware, commercially-available tools, and novel techniques.
- Novelty of tools and techniques: APT32 uses ActiveMime files with social engineering methods, cloud-based email analytics software for tracking, and multilingual lure documents. They also employ sophisticated persistence mechanisms, obfuscation techniques, and stealthy tactics to blend in with legitimate user activity.
- Tools used: Malware families include WINDSHIELD, KOMPROGO, SOUNDBITE, PHOREAL, and Cobalt Strike BEACON.
- Infrastructure: APT32 uses a large set of domains and IP addresses for command and control operations.
- Implications: APT32 poses a significant risk to companies operating in or investing in Vietnam, threatens political activism and free speech in Southeast Asia, and targets foreign governments, journalists, and the Vietnam diaspora.
- Overall, APT32 demonstrates a dynamic cyber espionage capability aligned with Vietnamese state interests, utilizing advanced tools and techniques to conduct targeted operations.





Report 6

APT 32, also known as OceanLotus or SeaLotus, has been active in South East Asian countries, targeting victims in the region's operating sector. The threat actor has demonstrated advanced capabilities by leveraging publicly available exploits, such as CVE-2017-11882, to deliver its backdoor while maintaining persistence on compromised systems without leaving traces. OceanLotus has been using novel techniques, including self-extracting archives and decoy documents, to deceive victims and evade detection by security products. The threat actor's tools and techniques have evolved over time, with recent activities involving the use of SFX archives that drop and execute DLL files with a final payload of a backdoor. OceanLotus continues to adapt and improve its tactics to stay under the radar, showcasing a high level of sophistication and persistence in its operations. The threat actor's activities have been observed since mid-2018, with changes in configuration data and C&C servers to avoid detection. Overall, OceanLotus remains a significant threat actor with a diverse toolset and a focus on targeting specific victims through deceptive tactics.





Report 7

Malformed report





Report 8

Summary:
APT32, also known as OceanLotus, targeted the Cambodian government in a new malware campaign using an ASEAN-themed spearphish. The Vietnamese state-sponsored threat group used Recorded Future RAT controller detections and Network Traffic Analysis to identify new operational infrastructure. This campaign involved the delivery of malicious documents containing self-extracting archives with encrypted shellcode to execute the final payload. The threat actor's capability was evidenced by the use of sophisticated loading processes and communication with identified command-and-control domains. The tools and techniques used by APT32 showed a level of sophistication and novelty, with overlaps in tactics, techniques, and procedures seen in historical samples. The campaign targeted Cambodian government organizations, indicating a focus on specific regions and sectors. The report was published on November 10, 2020, by Recorded Future's Insikt Group.





Report 9

Summary:
APT 32, also known as OceanLotus or SeaLotus, has recently surfaced with a new MacOS backdoor variant. The threat actor has targeted organizations in industries such as media, research, and construction, with a focus on users in Vietnam. The new variant exhibits novel behavior and domain names, remaining undetected by most antimalware solutions. The threat actor uses deceptive techniques to evade detection, such as disguising the backdoor as a Word document file. The backdoor's capabilities include collecting system information, receiving commands from C&C servers, and executing malicious actions on infected systems. The threat actor's use of custom encryption and base64 encoding for strings adds to the sophistication of their tools and techniques. The C&C servers associated with the threat actor include mihannevis[.]com, mykessef[.]com, and idtpl[.]org. The report provides indicators of compromise, MITRE TTP mappings, and recommendations for defending against such threats. The report was published on Trend Micro's website by Threats Analysts Luis Magisa and Steven Du.





Report 10

Summary:
APT 32, also known as OceanLotus, SeaLotus, and Cobalt Kitty, has been identified as the threat actor behind a new MacOS backdoor. The threat actor targets human rights organizations, media organizations, research institutes, and maritime construction firms in the region of Vietnam. The backdoor is distributed via a malicious Word document in phishing emails, exploiting the Perl programming language on MacOS computers. The backdoor establishes persistence by installing itself in specific directories based on user privileges and creates hidden persistence files. The backdoor collects system information, encrypts it using AES256, and communicates with malicious C&C servers. The threat actor uses advanced scrambling and encryption techniques to obfuscate data sent to and received from the C&C servers. Mitigation strategies include adopting best practices for phishing attacks and using security solutions like Trend Micro Antivirus for Mac. Indicators of compromise include C&C servers and SHA256 hashes for the delivery document, dropper, and backdoor. The threat actor's novel techniques and tools demonstrate a high level of sophistication and capability.





Report 11

OceanLotus, a threat actor known as APT 32, has been extending cyber espionage operations through fake websites targeting individuals in Vietnam and Southeast Asia. The threat actor has set up multiple fake news websites and Facebook pages to profile users, redirect to phishing pages, and distribute malware payloads for Windows and OSX. These websites appear legitimate and contain benign content, with only specific articles containing malicious content. OceanLotus has been observed using sophisticated techniques to target visitors, including social engineering tactics to prompt users to download fake software updates or documents. The threat actor has been leveraging tools like Cobalt Strike for red teams and nation-state actors, using malleable command-and-control profiles to impersonate legitimate services. The operation time window for these new attack campaigns was within the last year, with evidence of continued evolution in the threat actor's tactics. The report was published on November 6, 2020, by Volexity Threat Research.





Report 12

OceanLotus, also known as APT 32, conducted a new watering hole attack in Southeast Asia targeting 21 compromised websites, including government and media sites in Cambodia and Vietnam. The attack, active since September 2018, is believed to be run by OceanLotus, an espionage group interested in foreign governments and dissidents since 2012. The threat actor evolved their tactics by using public key cryptography and switching to WebSocket to hide malicious communications. The attack involved compromising websites visited by potential targets and using unique domains for each compromised site. The attackers used sophisticated techniques to evade detection, including obfuscation and encryption of communications. The campaign involved a first stage delivering decoy or malicious scripts based on visitor location, and a second stage reconnaissance script communicating through WebSocket over SSL. The attackers registered multiple domains and servers to remain stealthy, mimicking legitimate websites. The report generated by the reconnaissance script contained detailed information about victim browsers and websites visited. The threat actor's sophistication and continuous improvement of their toolset highlight the need for close monitoring of OceanLotus activities. The report includes indicators of compromise for network infrastructure and files used in the attack. The campaign is a significant threat to organizations in Southeast Asia and underscores the importance of proactive cybersecurity measures.





Report 13

OceanLotus, also known as APT 32 or SeaLotus, has recently updated its macOS malware targeting Mac users. The threat actor employs a wide range of techniques to gain code execution, achieve persistence, and evade detection on Windows systems. The malware sample analyzed in April 2019 was packed with UPX, making static detection more difficult. The backdoor executable creates an anti-debugging watchdog thread to check for the presence of a debugger. The C&C servers used by this sample were created in 2018, indicating recent activity. The malware no longer uses the libcurl library for network exfiltration, opting for an external library instead. Strings are encrypted using AES-256-CBC, with a script released to automate decryption using the Hex-Rays API. The OceanLotus group continues to update its toolset, targeting Mac users with improved capabilities. The exact network protocol used by the malware remains unknown due to encryption. The IoCs and MITRE ATT&CK techniques associated with this threat actor are available for further analysis.





Report 14

Summary:
The threat actor APT 32, also known as OceanLotus or SeaLotus, has been using steganography to hide encrypted payloads within .png image files since September 2018. This tactic was discovered by researchers who found that the group targets private sector industries and foreign governments, primarily in Southeast Asian countries like Vietnam and the Philippines. The threat actor has been active since at least 2014 and is known for delivering malicious attachments via spear phishing emails. The use of steganography to conceal malware is a novel approach, with the threat actor employing bespoke tools that make detection challenging for standard analysis tools. The threat actor has been observed deploying two new obfuscated loaders that deploy APT32-specific backdoors, with one loader using a custom .png steganography method to hide the payload. This technique allows the payload to be hidden in plain sight, making it virtually indistinguishable from an original image. The threat actor's capability to use steganography to obfuscate payloads demonstrates their evolving tactics and sophistication in cyber-espionage activities.





Report 15

APT 32, also known as OceanLotus or SeaLotus, conducted a sophisticated and widespread mass digital surveillance and attack campaign targeting Asian nations, the ASEAN organization, media, human rights groups, and civil society organizations. The attacks were carried out through compromised websites during high-profile ASEAN summits. OceanLotus, believed to be a Vietnam-based APT group, utilized advanced tactics, techniques, and procedures (TTPs) to target specific individuals and organizations. The threat actor used custom Google Apps to gain access to victim Gmail accounts, modified compromised websites with JavaScript for social engineering, and employed multiple backdoors like Cobalt Strike. The attack infrastructure included numerous attacker-created domains mimicking legitimate services and heavy use of Let's Encrypt SSL/TLS certificates. The threat group's capability and scale were compared to the Russian APT group Turla. The report detailed the operating pattern of OceanLotus, compromised websites, JavaScript tracking and profiling frameworks, and methods of maintaining persistent access. The threat actor also targeted Google accounts through OAuth authorization prompts on compromised websites. Volexity recommended defense measures for users and website administrators to mitigate the threat. The report provided network signatures for detecting OceanLotus activity and concluded that the threat group has evolved into a highly skilled and organized APT actor. The report was published on November 6, 2017, by Volexity.





Report 16

OceanLotus, also known as APT 32, targeted high-profile corporate and government entities in Southeast Asia, particularly in Vietnam, the Philippines, Laos, and Cambodia. The threat actor is known for using custom-built backdoors and techniques to gain remote access to compromised machines. They employ a two-stage attack involving a dropper package to smuggle the backdoor onto systems, using trickery commonly associated with targeted operations. OceanLotus utilizes spearphishing emails with malicious attachments disguised as documents or spreadsheets to lure victims into running the dropper. They also employ watering hole attacks to compromise websites likely to be visited by victims. The threat actor uses DLL side-loading to remain undetected, co-opting legitimate applications' library-loading processes with malicious DLLs. The group's persistence and use of encryption for communication with command-and-control servers demonstrate their advanced capabilities. The report was published on March 13, 2018, by ESET Research.





Report 17

Summary:
The threat actor known as APT 32, OceanLotus, SeaLotus conducted a large-scale APT operation in Asia targeting a global corporation based in Asia to steal proprietary business information. The operation, named Operation Cobalt Kitty, involved spear-phishing attacks on top-level management, compromising over 40 PCs and servers. The threat actor demonstrated adaptability by changing tools and techniques, using modified publicly-available tools and six custom-built tools, including backdoors exploiting DLL sideloading attacks. A novel and stealthy backdoor targeting Microsoft Outlook for command-and-control and data exfiltration was developed. The operation persisted for at least a year before being detected. Cybereason attributes this APT to the OceanLotus Group, also known as APT-C-00, SeaLotus, and APT32. The threat actor's arsenal included DNS tunneling for C2 communication and a rare Outlook macro backdoor for data exfiltration. The attackers showed persistence and resourcefulness in adapting their tactics, even after being exposed and shut down. The operation showcased the OceanLotus Group's capabilities and motivation in conducting sophisticated cyber espionage APTs. The report provides detailed insights into the attack lifecycle, tools used, and the threat actor's profile. Date: Not specified. Region: Asia. Operating Sector: Global corporation based in Asia. Type of Company: Not specified.





Report 18

Summary:
In the final quarter of 2017, the threat actor OceanLotus Group (also known as APT32, Cobalt Kitty) was discovered using bespoke backdoors and obfuscated CobaltStrike Beacon payloads for C2 operations. They utilized PowerShell for malware deployment, obfuscators, and reflective PE/shellcode loaders from exploit kits like MSFvenom and Veil to operate malware in-memory with no on-disk footprint. The remote access trojans developed by OceanLotus Group, named Roland, Remy, and Splinter, showed code similarities with known malware like "Backdoor.Win32.Denis" and "WINDSHIELD." Roland was designed to mimic legitimate software DLLs of victim organizations. The threat actor tailored C2 protocols for each target, supporting various communication methods. The malware showed high-standard design and development, indicating a well-funded and equipped team capable of repurposing custom library code for future attacks. The report provides in-depth technical analysis of the malware, C2 protocols, TTPs, and observations. The threat actor's capabilities and novel techniques suggest a sophisticated and well-resourced operation.





Report 19

Summary:
The threat actor APT 32, also known as OceanLotus, has been using a suite of remote access trojans called "Ratsnif" to enhance their network attack capabilities. The trojans, actively developed since 2016, combine various attack techniques like packet sniffing, ARP poisoning, DNS spoofing, HTTP injection, and MAC spoofing. The threat actor has targeted victims in the Automotive & IOT sector, with victims being companies in various regions. The Ratsnif samples analyzed show evidence of the threat actor's capability to conduct sophisticated network attacks. The tools and techniques used by the threat actor, such as HTTP injection, protocol parsing, and SSL hijacking, demonstrate a level of novelty and sophistication in their operations. The latest sample of Ratsnif, discovered in the latter half of 2018, introduced new features and did not rely on C2 for operation, showcasing the threat actor's evolving tactics. The threat actor's use of open-source libraries and poor development quality in the malware indicate a lack of adherence to high standards typically observed in OceanLotus malware. The report provides detailed technical analysis of the Ratsnif samples, including indicators of compromise and insights into the threat actor's modus operandi. The report was published on July 1, 2019, by the BlackBerry Cylance Threat Research Team.





Report 20

Summary:

APT 32, also known as OceanLotus or SeaLotus, targeted Toyota with a second security breach within five weeks. The incidents affected Toyota Japan, Toyota Vietnam, and Toyota Thailand, with details of the hacks undisclosed. The threat actor's capability is evidenced by the coordinated attacks across multiple regions and sectors within the automotive industry. The novelty lies in the rapid succession of breaches targeting the same company, indicating a persistent and evolving threat. The operation time window spans five weeks, showcasing a sustained effort by the threat actor.





Report 21

OceanLotus, also known as APT32, is a threat actor group originating from Southeast Asia, known for its sophisticated operations. The group primarily targets private sectors across multiple industries, foreign governments, activists, and dissidents connected to Vietnam in the APAC region. They have been actively using a new custom downloader malware family named "KerrDown" since early 2018. The delivery methods for KerrDown include malicious Microsoft Office documents with macros and RAR archives containing legitimate programs with DLL side-loading. The group has been observed using the Cobalt Strike Beacon payload in their campaigns, delivered through KerrDown. The compile timestamps of KerrDown samples suggest that OceanLotus operates during weekdays with a typical 9 AM to 6 PM working pattern. The group likely operates out of Vietnam or nearby countries and continues to evolve their tools and techniques. The report provides indicators of compromise and insights into the group's operations.





Report 22

Summary:
APT32, also known as OceanLotus or SeaLotus, a Vietnamese threat actor, targeted the Wuhan Government and Chinese Ministry of Emergency Management from January to April 2020 to collect intelligence on the COVID-19 crisis. The threat actor used spear phishing emails with tracking links to target Chinese government entities. A novel technique involved using a METALJACK loader displaying a Chinese-language titled COVID-19 decoy document to launch its payload. The malware also loaded shellcode to collect victim's computer information and communicated with command and control servers. The threat actor's activities indicate a global increase in cyber espionage related to the COVID-19 crisis, targeting governments and organizations seeking nonpublic information. The report provides indicators and MITRE ATT&CK technique mapping for detection and defense against APT32's tactics. The operation window was from January to April 2020. 

Date: January to April 2020
Region: East Asia (China)
Operating Sector: Government (Wuhan Government, Chinese Ministry of Emergency Management)
Type of Company: Government agencies, non-government organizations, and international organizations.





Report 23

Summary:
APT 32, a Vietnamese state-linked hacking group, targeted a Cambodian newspaper website to attack a local human rights organization, Licadho, after the Australian sale of the newspaper to a Malaysian spin doctor specializing in "covert PR." The attack involved a "watering hole" technique redirecting visitors to a fake Google page and a malicious site called GTransfer. The threat actor, APT32, has been active for at least five years, targeting foreign governments, Vietnamese dissidents, journalists, and corporations with interests in Vietnam's manufacturing, consumer products, and hospitality sectors. The malware campaign by APT32 started in late 2016 and is the first state-linked hacking outfit identified by FireEye that is not Chinese or Russian. The attack was detected in November 2017, with evidence of the malicious code added to the website around May 8. The attack coincided with the lead-up to a national election in Cambodia on July 29, highlighting the threat actor's capability and selective targeting techniques.





Report 24

Malformed report.





Report 25

Malformed report.





Report 26

Summary:
The threat actor APT 32, also known as OceanLotus, is an APT group with alleged Vietnamese background that has been active since April 2012. They have targeted various sectors including maritime institutions, scientific research institutes, real estate companies, and banks in countries like China, Cambodia, Thailand, and Laos. The group has shown a high level of sophistication and capability in their attacks, using novel techniques such as bait compression files, phishing attacks exploiting WinRAR vulnerabilities, and MAC backdoors. They have also exploited vulnerabilities like Eternal Blue and used template injection techniques in their attacks. The group constantly evolves their tactics, techniques, and procedures, showcasing a strong ability to conduct targeted and persistent attacks. The report provides detailed information on the group's activities, tools, and techniques used in their attacks, as well as indicators of compromise for tracking their malicious activities.


