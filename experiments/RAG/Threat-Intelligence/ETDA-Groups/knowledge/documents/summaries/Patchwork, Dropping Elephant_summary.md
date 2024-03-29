
Report 1

The threat actor known as Patchwork, also referred to as Dropping Elephant, has expanded its targets beyond government-associated organizations to include industries such as aviation, broadcasting, finance, and more. The group uses Chinese-themed content to lure targets into compromising their networks. The attacks have been observed targeting organizations in regions including the US, China, Japan, Southeast Asia, and the United Kingdom. The threat actor utilizes malicious PowerPoint and rich text files to exploit vulnerabilities such as CVE-2014-4114 and CVE-2015-1641. The malware dropped includes Backdoor.Enfourks and Backdoor.Steladok, which can search for files and upload them to specified servers. The threat actor's use of Baidu in their routines suggests a connection to Chinese software vendors. Mitigation strategies include deleting suspicious emails, keeping software updated, and using security software. Symantec and Norton products detect Patchwork's malware, with indicators of compromise including suspicious domains, IP addresses, and file names associated with the campaign. The threat actor's use of novel techniques and tools underscores their capability to target a wide range of industries and regions.





Report 2

Patchwork, also known as Dropping Elephant, is an APT group that has been active since December 2015, targeting diplomats and economists through spear phishing campaigns and watering hole attacks. The group is believed to be affiliated with a South Asian country and focuses on countries like Pakistan, Sri Lanka, Nepal, and others. Recently, the Knownsec 404 Advanced Threat Intelligence Team discovered a new backdoor tool called EyeShell used by Patchwork, which is a streamlined backdoor program designed for Windows systems. EyeShell has three functional modules, including initialization, online detection, and interaction, supporting various commands for file enumeration, upload, download, execution, and more. The tool uses AES-128 encryption for network interactions and is speculated to be used in conjunction with the BADNEWS Trojan. The report was published on July 26, 2023, providing detailed insights into the capabilities and techniques of the threat actor.





Report 3

Patchwork, also known as Dropping Elephant, is a threat actor that has been active since at least 2013, with a focus on targeting personnel working on military and political assignments, particularly in Southeast Asia and the South China Sea region. The threat actor has infected an estimated 2,500 machines, primarily targeting governments and government-related organizations worldwide. Patchwork's code is pieced together from various online sources, resembling a patchwork quilt. The group is associated with Confucius and operates out of India, targeting sectors such as aviation, defense, energy, finance, government, IT, media, NGOs, pharmaceuticals, and think tanks in countries like Bangladesh, China, Japan, the USA, and others in the Middle East and Southeast Asia. Patchwork's tools include AndroRAT, LokiBot, PowerSploit, and others, with reported hacking operations dating back to 2015, targeting government organizations in Europe, Pakistan, and US think tanks. The threat actor's novel techniques were highlighted in a 2023 report titled "Patchwork's new assault Weapons report — EyeShell Weapons Disclosure."





Report 4

Summary:
The Patchwork APT Group, also known as Dropping Elephant, targeted US-based think tanks in spear phishing campaigns in March and April 2018. The threat actors used unique tracking links in emails to identify recipients who opened the messages. They mimicked domains and themes of well-known US think tank organizations like CFR and CSIS to deliver malicious RTF documents exploiting CVE-2017-8570 to drop and execute QuasarRAT. The QuasarRAT, a freely available remote access tool, provided various functionalities for attackers. The threat actors leveraged the "packager trick" and exploited CVE-2017-8570 to execute the malware. The malware communicated with a command and control server at tautiaos.com. The attacks showed an evolution in Patchwork's targeting strategy and tracking capabilities, using open-source tools for flexibility in compromising systems. The campaign demonstrated the threat actor's capability to target specific sectors and regions with novel techniques.





Report 5

Patchwork APT, an Indian threat actor active since December 2015, targeted Pakistan through spear phishing attacks in late November to early December 2021. The threat actor used a new variant of the BADNEWS Remote Administration Trojan (RAT) called Ragnatela, capable of executing commands, capturing screenshots, logging keystrokes, and more. The RAT was distributed via malicious RTF files impersonating Pakistani authorities. Victims included Ministry of Defense-Government of Pakistan, National Defense University of Islamabad, and faculty members focusing on molecular medicine and biological science. Interestingly, the threat actor infected their own development machine with the RAT, revealing their use of virtual machines and VPNs. The campaign showed Patchwork's interest in new targets, although their sophistication level is not as high as other APT groups. The operation window was from late November to early December 2021.





Report 6

Patchwork, also known as Dropping Elephant and Monsoon, has been targeting victims in the Indian subcontinent, specifically focusing on organizations related to the Pakistan Army, Pakistan Atomic Energy Commission, and Pakistan’s Ministry of the Interior. The threat actors have been using EPS exploits embedded in legitimate documents to deliver their updated BADNEWS payload, which acts as a backdoor for full control over victim machines. The group has been actively updating their toolsets, including modifications to how the malware obtains its C2 server information and communicates with remote servers. The use of weaponized legitimate documents is a common tactic for this threat actor group. The most recent activity was observed in March 2018, with the threat actor group actively updating their tools and techniques to stay ahead of the security community. The victims targeted are primarily in the Indian subcontinent region, with a focus on organizations related to the military and government sectors. The threat actor group continues to evolve their malware toolset, with recent changes to how the BADNEWS malware family uses dead drop resolvers and communicates with C2 servers. The report provides indicators of compromise, including malicious document SHA256 hashes, BADNEWS SHA256 hashes, C2 servers, and dead drop resolvers. The report also includes a script to decrypt data from dead drop resolvers used by the threat actor group.





Report 7

Patchwork, also known as Dropping Elephant, is an advanced persistent threat (APT) group that has been active since at least 2014. The threat actor primarily targets government and military entities in the South Asian region, with a focus on India and Pakistan. The victims of Patchwork/Dropping Elephant have been predominantly in the telecommunications, government, and defense sectors. The threat actor has demonstrated a high level of sophistication in their operations, utilizing custom malware and novel techniques to evade detection. Patchwork/Dropping Elephant has been known to use spear-phishing emails with malicious attachments to gain initial access to their targets. The group has also been observed using living-off-the-land techniques and leveraging legitimate tools to carry out their attacks. The latest activity attributed to Patchwork/Dropping Elephant was reported in January 2021, indicating that the threat actor remains active and continues to pose a significant risk to organizations in the region.





Report 8

Summary:
The Dropping Elephant threat actor, also known as "Chinastrats" and "Patchwork," is an aggressive cyber-espionage group targeting high-profile diplomatic and economic entities in the Asian region. The threat actor uses spear-phishing and watering hole attacks to infect victims, primarily focusing on those involved in China's foreign relations. The group utilizes custom attack tools and social engineering tactics to steal sensitive documents and data since at least November 2015. Notably, Dropping Elephant's backdoor malware downloads additional encrypted payloads and communicates with a C2 server, exhibiting advanced capabilities. The threat actor's activities have been detected in China, indicating a specific interest in Chinese-related targets. Despite not using advanced techniques, Dropping Elephant's successful operations highlight the importance of patching vulnerabilities and basic security measures. Kaspersky Lab has provided indicators of compromise and actively collaborates with CERTs and LEAs to mitigate the threat.


