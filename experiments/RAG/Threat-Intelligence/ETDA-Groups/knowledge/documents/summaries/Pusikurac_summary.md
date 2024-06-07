
Report 1

Summary:
A threat actor named "Pusikurac" has been identified in a new campaign delivering the Orcus Remote Access Trojan (RAT) in ongoing, targeted attacks. The campaign uses advanced evasive techniques to bypass security tools, with the Orcus RAT capable of stealing browser cookies and passwords, launching DDoS attacks, disabling webcam activity lights, recording microphone input, and more. The threat actor focuses on information stealing and .NET evasion, registering domains through FreeDns services and utilizing legitimate free text storage services like paste. The attacker heavily misuses commercial .NET packers and embeds payloads within video files and images. The attack flow involves a persistent VBscript executing a PowerShell script to download a .NET executable obfuscated and encrypted by ConfuserEx, which then performs a UAC bypass through event viewer registry hijacking. The Orcus RAT is delivered through a legitimate Ramadan-themed Coca-Cola advertising video, with the attacker using AES encryption for settings. The threat actor behind the campaign has been linked to multiple campaigns, showcasing a high level of sophistication in their techniques. The campaign demonstrates the use of novel tools and techniques, indicating the threat actor's capability and expertise in conducting targeted attacks. The report was published on January 30, 2019, by Morphisec Labs.





Report 2

Summary:

The threat actor Pusikurac, also known as Morphisec, has been identified in a highly sophisticated campaign delivering the Orcus Remote Access Trojan in targeted attacks since 2019. The campaign utilizes advanced evasive techniques to bypass security tools and can steal sensitive information, launch DDoS attacks, disable webcams, record audio, log keystrokes, and more. Forensic data indicates a single threat actor is behind multiple campaigns. Pusikurac focuses on information stealing and .NET evasion, registering domains through FreeDns services and embedding payloads within video files and images. The threat actor's motivation is information theft and espionage. The campaign has been observed targeting victims in various sectors and countries. The tools used include the Orcus RAT. The report does not specify the country of origin of the threat actor. 

Date of last modification: 2020-04-29


