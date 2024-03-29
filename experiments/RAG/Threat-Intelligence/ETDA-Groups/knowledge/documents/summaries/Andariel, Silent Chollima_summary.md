
Report 1

Summary: The Andariel threat group, affiliated with Lazarus, targets Korean corporations related to national security since 2008, using spear phishing, watering hole, and supply chain attacks. They create and use various malware types, including backdoors like Andardoor and 1th Troy Reverse Shell. Recent attacks in 2023 show a trend of using malware strains developed in Go, such as Goat RAT and DurianBeacon. The threat actor abuses Innorix Agent and exploits vulnerabilities like Log4Shell. The group's tactics and tools show a high level of sophistication and continuous monitoring by AhnLab's ASEC. The attacks target various industries in Korea, emphasizing the need for advanced security measures.





Report 2

Andariel, also known as Silent Chollima, is a subgroup of the Lazarus Group operating out of North Korea with a motivation for information theft and espionage. They have targeted various sectors and countries, including South Korean organizations, defense industries, and foreign defense industries. Their operations date back to 2014 with attacks like "BLACKMINE" and "GHOSTRAT" focusing on information theft. In recent years, Andariel has evolved their tactics, using novel techniques such as concealing malicious code within BMP images and deploying ransomware like DTrack and Maui. They have also been observed using Telegram-based malware written in DLang in Operation "Blacksmith." Additionally, Andariel has been linked to exploiting vulnerabilities like TeamCity CVE-2023-42793 and Apache ActiveMQ CVE-2023-46604. Their activities demonstrate a continuous threat to high-value targets worldwide.





Report 3

Summary:
The threat actor Andariel, also known as Silent Chollima, deployed DTrack and Maui ransomware in a global operation targeting victims in Japan, India, Vietnam, and Russia. The Maui ransomware incident occurred on April 15, 2021, with evidence suggesting it was the first-ever involving Maui ransomware. The actor used a variant of the DTrack malware prior to deploying Maui, indicating a connection to the Korean-speaking APT Andariel with low to medium confidence. The actor's TTPs included using legitimate proxy and tunneling tools, exploiting vulnerabilities in public services like WebLogic and HFS, and deploying ransomware for financial gain on a global scale. The attribution was supported by code similarities with previously known DTrack malware and the use of specific tools associated with the Andariel group. The actor demonstrated an opportunistic approach, targeting companies regardless of industry as long as they had good financial standing. The operation showcased the actor's ongoing financial motivations and scale of interest in deploying ransomware.





Report 4

Summary:
The threat actor Andariel targeted South Korea with ransomware in April 2021, evolving their infection scheme and payload. The group was identified as a sub-group of Lazarus by the Korean Financial Security Institute. Evidence of the threat actor's capability was found in the code overlaps between the second stage payload and previous Andariel malware. The threat actor leveraged malicious Word documents and files mimicking PDF documents for infection. Additionally, a victim was targeted with custom ransomware, indicating a financial motivation. The Andariel group has historically targeted entities in South Korea, including victims in manufacturing, home network service, media, and construction sectors. The attack revealed connections to the Lazarus group but was ultimately attributed to Andariel. The group's tools and techniques have evolved, showcasing a financially motivated state-sponsored actor.





Report 5

Summary:
The report details an attack by the Andariel group, a subsidiary of the Lazarus group, targeting South Korean communications companies and semiconductor manufacturers. The threat actor exploited vulnerabilities in asset management programs and MS-SQL servers, using malware strains like TigerRat, Black RAT, NukeSped variants, and Lilith RAT. Novel techniques included using a Golang downloader and adding concealed user accounts for persistence. The attack involved spear phishing, watering hole, and supply chain tactics, with the threat actor using PowerShell and mshta.exe for malware installation. The report provides IOCs and emphasizes the need for patching and monitoring to prevent future attacks. Date: November 20, 2023.





Report 6

Summary: The Andariel threat group, known for targeting South Korean companies and institutions, has been exploiting the Apache ActiveMQ vulnerability (CVE-2023-46604) to install malware. The group is suspected to be a subsidiary of the Lazarus threat group and has been using spear phishing, watering hole, and supply chain attacks. Evidence suggests that the threat actor has been using novel techniques such as exploiting the Log4Shell vulnerability and abusing legitimate software. The group has been installing NukeSped and TigerRat backdoors through the vulnerability, with logs showing the use of malicious Java class files and tools like CobaltStrike and Metasploit Meterpreter. The attacks have been ongoing since late October, targeting various sectors including national defense, political organizations, and telecommunications in South Korea. The threat actor's capability and use of advanced tools indicate a sophisticated and persistent threat.





Report 7

Malformed report.





Report 8

Malformed report





Report 9

Andariel, Silent Chollima, two North Korean threat actors, have been observed exploiting the TeamCity CVE-2023-42793 vulnerability since early October 2023. The threat actors, Diamond Sleet and Onyx Sleet, have targeted organizations using TeamCity, a CI/CD application for DevOps and software development. Diamond Sleet and Onyx Sleet have utilized unique sets of tools and techniques following successful exploitation of the vulnerability. Diamond Sleet has deployed the ForestTiger backdoor and conducted DLL search-order hijacking attacks, while Onyx Sleet has focused on user account creation, system discovery, and payload deployment. The threat actors have targeted victim organizations in various sectors, including media, IT services, defense, and government. Microsoft has provided mitigation recommendations, including applying updates, investigating indicators of compromise, and using Microsoft Defender Antivirus for protection. The threat actors have demonstrated advanced capabilities and novel techniques, posing a high risk to affected organizations. Date: October 18, 2023.





Report 10

Summary:
The threat actor Andariel, a branch of the Lazarus Group, has been using new reconnaissance tactics mainly against South Korean targets. They have been active in injecting scripts into compromised websites to collect information on visitors' browsers, ActiveX objects, and software versions. The group has targeted specific ActiveX objects related to DRM and voice conversion software used by local governments and public institutions. The reconnaissance tactics have evolved to include websocket connections and expanded to target browsers other than Internet Explorer. The Andariel group's activities have been ongoing since at least 2007, with recent operations in May and June 2018. The threat actor's capabilities and novel techniques indicate a sophisticated and evolving threat landscape. The report provides indicators of compromise and recommendations for layered security protection to mitigate similar threats.





Report 11

Summary:
- Threat actor: Andariel, linked to North Korea's Reconnaissance General Bureau and Lazarus Group.
- Date: December 6th, 2023.
- Region: South Korea.
- Operating sector: Defense industry, research institutes, and pharmaceutical companies.
- Evidence: Stole 1.2 terabytes of data on anti-aircraft systems, conducted ransomware attacks, extorted victims for $357,000 in Bitcoin.
- Novelty: Used a South Korean server rental company as a base for hacking, tracked ransoms on cryptocurrency platforms, and laundered funds through a Chinese bank.
- Collaboration: Investigation conducted alongside the FBI.
- Impact: Joint advisory issued by the UK and South Korea on supply-chain attacks by North Korean hackers.
- Quarterly consultative body established by the US, Japan, and South Korea to block cyber activities funding North Korea's weapons development.
- Tools and techniques: Utilized sophisticated hacking methods and targeted specific sectors for data theft and financial gain.


