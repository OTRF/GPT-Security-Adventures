
Report 1

Summary:
A threat actor, identified as the LuckyMouse APT group, targeted government agencies and a National Data Center in Mongolia in a cyber-espionage campaign discovered by Avast in the summer of 2020. The attack involved planting backdoors and keyloggers to gain access to government networks, with the main aim being the exfiltration of sensitive data. The attack was carried out through a vulnerable company providing services to the agencies and spear-phishing emails with malicious attachments. The threat actor utilized novel tactics such as the Polpo and LuckyBack backdoors, along with known tools like HyperBro RAT and Mimikatz. The attack also involved the use of encryption methods to hide IP addresses in C&C responses. The campaign showed evidence of updated toolsets and sophisticated techniques by the threat actor. The operation time window was not specified in the report.





Report 2

Summary:
The APT trends report for Q1 2019 by Kaspersky highlights the activities of threat actors such as Emissary Panda, APT 27, LuckyMouse, and Bronze Union. The report focuses on the capability of threat actors in targeting supply chains, with a notable example being the "Operation ShadowHammer" attack on ASUS Live Update Utility. Russian-speaking groups showed interest in political activities, while Chinese-speaking actors targeted South East Asia. LuckyMouse APT group targeted Vietnamese government and diplomatic entities using penetration testing frameworks. Chinese state-sponsored threat actor APT40 targeted engineering, transportation, and defense industries. The report also mentions the use of ransomware by APT actors for cyber-sabotage. The findings suggest a growing trend of geopolitical influence on APT activities, with South East Asia being the most active region. The report also highlights the discovery of new malware variants and zero-day vulnerabilities. Overall, the report provides insights into evolving tactics and techniques used by threat actors in the first quarter of 2019.





Report 3

BRONZE UNION, also known as Emissary Panda, APT 27, and LuckyMouse, is a threat group located in the People's Republic of China. They have been active since 2013 and have targeted networks for political and military intelligence-collection objectives. In 2018, evidence showed BRONZE UNION using updated versions of publicly available tools like ZxShell and Gh0st RAT, with novel properties indicating evolving capabilities. They have also developed proprietary tools like SysUpdate and HyperBro since 2016, with SysUpdate being a multi-stage malware used exclusively by the group. BRONZE UNION's tools allow for remote access, persistence, and communication with C2 servers, showcasing their flexibility and ability to adapt to intrusion challenges. The threat actors are skilled at circumventing security controls, escalating privileges, and maintaining access to high-value systems over extended periods. The group's preference for widely available tools and web shells indicates a strategy of maintaining long-term network access. The threat indicators associated with BRONZE UNION activity are provided for monitoring and detection purposes. (Source: https://www.secureworks.com/research/a-peek-into-bronze-unions-toolbox)





Report 4

BRONZE UNION, a threat group based in the People's Republic of China, has been active since 2015 targeting organizations in aerospace, government, defense, technology, energy, and manufacturing sectors. They have been observed using strategic web compromises and exploiting vulnerable Internet-facing services to gain access to networks. The threat actor has demonstrated the capability to conduct successful large-scale intrusions against high-profile networks, using a range of proprietary, publicly available, and native tools to search for and acquire data. They have also shown discipline in avoiding detection by disabling logging processes and manipulating native Windows features. The threat actor's tactics include using tools like OwaAuth, China Chopper web shell, Rcmd, Wrapikatz, Netview, and Kekeo for credential theft, lateral movement, and exfiltration. BRONZE UNION remains a formidable threat group that targets intellectual property and executes operations swiftly, with a preference for leveraging SWCs and scan-and-exploit techniques. The threat indicators associated with BRONZE UNION activity include IP addresses, MD5 and SHA hashes, and filenames. The report provides recommendations for mitigating these threats, including conducting regular internal vulnerability scanning, patching, and upgrading of priority systems. (Source: Secureworks, Date: Ongoing)





Report 5

Malformed report.





Report 6

Malformed report.





Report 7

Emissary Panda, also known as APT 27, LuckyMouse, and Bronze Union, is a Chinese threat group that has been active since at least 2010. The group has targeted organizations in sectors such as aerospace, government, defense, technology, energy, and manufacturing. They have used strategic web compromises and watering hole attacks to infiltrate victims' networks. Emissary Panda's motivation is information theft and espionage, with observed attacked countries including the USA, China, Germany, and the Middle East. The threat actor has been linked to various tools such as Gh0st RAT, Mimikatz, and PlugX, and has been involved in operations like "Iron Tiger" in 2010 and "PZChao" in 2017. They have also been observed targeting government organizations in the Middle East in 2019 and using ransomware in 2020. Emissary Panda's evolving tactics, such as using COVID-19 as a lure in 2020, and targeting Exchange servers in 2021, demonstrate their ongoing threat to cybersecurity. Their use of novel techniques like backdoored Electron apps and Linux targeting in 2022 shows their adaptability and persistence in carrying out cyber-attacks.





Report 8

Summary:
- Threat actor: Emissary Panda (APT27, LuckyMouse, Bronze Union)
- Region: Middle East
- Operating sector: Government Organizations
- Date: April 1, 2019 to April 16, 2019
- Evidence of capability: Exploited CVE-2019-0604 in Microsoft SharePoint, installed webshells, uploaded tools for credential dumping, lateral movement, and exploitation of vulnerabilities like EternalBlue (CVE-2017-0144)
- Novelty of tools and techniques: Use of China Chopper webshell, DLL sideloading with legitimate applications like Sublime Text and Microsoft's Create Media, custom backdoor HyperBro, and unique payloads with code overlaps with known Emissary Panda attacks
- Tools uploaded: Mimikatz, cURL, Impacket psexec, HyperBro backdoor, various hack tools for reconnaissance and exploitation
- IOCs: Webshells SHA256, Malicious HackTools and Payloads SHA256, HyperBro C2 domain

Malformed report.





Report 9

Summary:
- Region: Global
- Operating Sector: Various, including governmental entities, private companies, and utility companies
- Type of Company: IT services, oil company, construction equipment company, procurement company, consulting company, software development company, real estate company, utility company
- Date: Ongoing as of March 2021

Multiple APT groups, including LuckyMouse, Tick, Calypso, Winnti Group, Tonto Team, Mikroceen, and DLTMiner, have been exploiting recent Microsoft Exchange vulnerabilities (CVE-2021-26855, CVE-2021-26857, CVE-2021-26858, and CVE-2021-27065) to compromise email servers globally. Evidence suggests that some threat actors had access to the exploit before the patch release. Novel techniques include the use of webshells, backdoors, and RATs to install implants on victims' email servers. The threat actors targeted various organizations, primarily in Asia, the Middle East, and Central Asia, with a focus on espionage activities. The exploitation of these vulnerabilities has led to the installation of malware, including Mimikatz, Cobalt Strike, and ShadowPad, among others. The threat landscape continues to evolve, with an increasing number of threat actors gaining access to these vulnerabilities, emphasizing the importance of promptly patching all Exchange servers.





Report 10

Summary:
The German government has warned of APT27, a Chinese cyberespionage group, targeting local companies since at least March 2021. The threat actor has been exploiting vulnerabilities in software like Microsoft Exchange and Zoho SelfService to install the HyperBro malware for intelligence collection. APT27 has targeted German companies, aiming to steal business secrets and intellectual property, with the possibility of infiltrating networks of customers or service providers. The group has used well-known exploits like CVE-2021-40539 and CVE-2021-26855 to gain access to corporate networks. The use of HyperBro malware, a strain seen since 2018, demonstrates the capability of APT27 to maintain control over infected systems. German authorities have provided indicators of compromise to help organizations set up protective measures against these attacks. Chinese hackers have a history of targeting large German companies for intellectual property theft, with past victims including TeamViewer, ThyssenKrupp, and Bayer. The warning about Chinese cyber-espionage targeting the local business sector dates back to at least 2018.





Report 11

Summary: The report details an investigation into an accidental APT attack by threat actor Emissary Panda, also known as APT 27, LuckyMouse, and Bronze Union. The attack involved the Polar ransomware, which encrypted files on victim computers. The threat actor demanded payment for a decryption key, threatening irreversible data loss if the computers were restarted or shut down. The report includes MITRE TTPs used by the threat actor, such as exploiting public-facing applications, scheduled tasks, and data exfiltration. Novel tools and techniques included the use of legitimate components like GDFInstall.exe signed by Ubisoft and an encrypted copy of the ransomware. The report provides IOCs related to the attack. The incident was published on November 27, 2020, by Positive Technologies. 

Malformed report.





Report 12

Iron Tiger APT, also known as LuckyMouse, EmissaryPanda, and APT27, has updated its toolkit with an evolved SysUpdate malware variant that now uses five files in its infection routine instead of the usual three. The threat actor has been targeting gambling and betting companies in Southeast Asia, with evidence suggesting a continued interest in the gambling industry. Iron Tiger has possible connections to other threat actors based on similar tactics, techniques, and procedures (TTPs) observed. The threat actor has also been using rootkits, such as the Pandora backdoor, to hide files at the kernel level. Novel tools and techniques, such as the use of a modified FRP tool and the exploitation of the Microsoft Exchange vulnerability CVE-2020-0688, have been observed. The threat actor has targeted governments, banks, telecommunication providers, and the energy sector in the Middle East and Southeast Asia. The timeline of the attacks spans from July 2019 to January 2021, with various malware samples and tools being deployed. The indicators of compromise (IoCs) can be found in the report.





Report 13

Iron Tiger, also known as Emissary Panda, APT 27, LuckyMouse, Bronze Union, compromised the chat application Mimi in a supply chain attack targeting Windows, Mac, and Linux users. The threat actor, an advanced persistent threat (APT) group, has been active for almost a decade and is known for cyberespionage. Iron Tiger used a new malware family targeting the Mac OS platform, along with samples compiled for the Linux platform. The group controlled servers hosting the legitimate installers of the MiMi chat application, indicating a supply chain attack. Iron Tiger's interest in compromising victims across Windows, Linux, and macOS platforms was evident in this campaign. The campaign timeline dates back to June 2021, with modifications made to Windows and Mac OS MiMi chat installers in November 2021 and May 2022, respectively. The threat actor targeted victims in Taiwan and the Philippines, with one identified victim being a Taiwanese gaming development company. The campaign was attributed to Iron Tiger based on similarities with previous samples and indicators linking to the threat actor. The report provides detailed analysis of the malware used, infection vectors, and indicators of compromise.





Report 14

Iron Tiger, an advanced persistent threat (APT) group, updated their custom malware family SysUpdate in 2022 to include new features and Linux platform support. The oldest sample of this updated version was found in July 2022, with subsequent samples identified in late October 2022. Iron Tiger's complex loading logic aims to evade security solutions. The new version uses the ASIO C++ asynchronous library and removes C++ run-time type information classes observed in the 2021 version. The threat actor added DNS TXT communication for C&C, a novel technique. The malware retrieves machine information and sends it to the C&C encrypted with DES. Iron Tiger also targeted a gambling company in the Philippines, using a domain name similar to the victim's for C&C. The threat actor signed malicious files with a stolen certificate from VMProtect, indicating a common practice. The campaign demonstrates Iron Tiger's interest in the gambling industry and South East Asia, using chat applications as infection vectors. The threat actor regularly updates tools to add new features and target other platforms, indicating ongoing development and potential future campaigns. Organizations are advised to enhance security measures and remain vigilant for possible infection vectors used by Iron Tiger.





Report 15

Summary:
APT27, also known as Emissary Panda, LuckyMouse, or Bronze Union, has been observed exploiting the COVID-19 pandemic to target individuals working from home. The threat actor has been using thematic email campaigns and malicious attachments to lure victims. The attack chain involves the use of fake PDF files that are actually .lnk files, which execute a series of commands to drop and execute malware. The threat actor leverages obfuscation techniques and old Microsoft Office components to establish persistence on the target system. The final stage of the attack involves the deployment of a backdoor beaconing to a command and control server. The tools and techniques used by APT27 demonstrate a high level of sophistication and the capability to exploit current events for malicious purposes. The report was published on March 19, 2020, highlighting the ongoing threat posed by APT27 during the COVID-19 crisis.





Report 16

Summary:
In June 2018, LuckyMouse, also known as APT 27, targeted a national data center in Central Asia, gaining access to government resources for a waterholing campaign. The threat actor used the HyperBro Trojan as their last-stage RAT, with timestamps from December 2017 to January 2018. The tools and tactics used in the campaign were attributed to the Chinese-speaking LuckyMouse actor. The malware spread through unclear initial infection vectors, possibly using a waterhole to infect data center employees. The campaign involved compromising government websites to redirect users to malicious domains. The threat actor's capability was evidenced by the use of Metasploit's shikata_ga_nai encoder and LZNT1 compression. The campaign targeted government entities and utilized a Mikrotik router for malicious HTTP requests processing. LuckyMouse's activity in waterholing government websites indicated a strategic aim to inject JavaScript into web pages. The campaign highlighted the threat actor's ability to target critical infrastructure and conduct sophisticated attacks.





Report 17

Summary:
- Threat actor: LuckyMouse (also known as APT 27, Emissary Panda, Bronze Union)
- Region: China
- Operating sector: Technology and governmental sectors
- Type of company of victims targeted: Not specified
- Date: May 26, 2022
- Evidence of capability: LuckyMouse targeted MacOS using a backdoored Electron app named "MìMì" to download and execute a Mach-O binary dubbed "rshell." This marks the first time LuckyMouse targeted MacOS and potentially involved in domestic surveillance.
- Novelty of tools and techniques: The backdoored Electron app was used to drop the RShell implant, written in C++ and using BJSON over TCP sockets for communication with the C2 server. The implant did not display a persistence mechanism and had specific commands for interacting with the filesystem.
- Conclusion: SEKOIA associates this activity with LuckyMouse with high confidence, indicating a potential expansion of their mandate to include surveillance. The threat actor was mostly observed carrying out espionage activities against the technology and governmental sectors. SEKOIA refrains from making assessments on the motivation of the intrusion set but will continue monitoring their activities.





Report 18

The threat actor identified as Emissary Panda, also known as APT 27, LuckyMouse, and Bronze Union, was discovered targeting industrial espionage targets globally, with a focus on the automotive, electronic, aerospace, energy, and pharmaceutical industries. The group, believed to be based in China, utilized over 100 compromised legitimate websites in "watering hole" attacks to target individuals with access to valuable industrial data. The group did not rely on zero-day vulnerabilities but instead exploited older vulnerabilities like CVE-2011-3544 and CVE-2010-0738. They used unique tools like the PlugX remote access tool and the ASPXTool web shell, with interfaces developed in Standard (Simplified) Chinese. The threat actor targeted Windows network domain controllers and Exchange e-mail servers to steal credentials and move laterally within compromised networks, often compromising other systems within two hours of initial access. The operation was reported by Dell SecureWorks researchers at the Black Hat information security conference on August 5, 2015.





Report 19

Summary:
- Threat actor: Threat Group-3390 (TG-3390), also known as Emissary Panda, APT 27, LuckyMouse, Bronze Union
- Region: People's Republic of China
- Operating sector: Wide range of organizations, including defense manufacturing, aerospace, automotive, technology, energy, pharmaceuticals, education, legal, and international relations
- Date: August 5, 2015
- Evidence of capability:
  - TG-3390 uses long-running strategic web compromises (SWCs) and whitelists to deliver payloads
  - Notable for compromising Microsoft Exchange servers using custom backdoor and credential logger
  - Access to proprietary tools and mature development process
  - Technical proficiency in obfuscation techniques, DLL side loading, and IIS exploitation
  - Tradecraft includes spearphishing emails, web shells, and data exfiltration
- Novelty of tools and techniques:
  - Use of HttpBrowser backdoor with obfuscation techniques
  - Deployment of OwaAuth web shell on Microsoft Exchange servers
  - Parking of domain names to non-routable IP addresses for evasion
- Recommendations for prevention and detection:
  - Search web log files for evidence of scanning and exfiltration
  - Implement two-factor authentication for remote access solutions
  - Audit ISAPI filters and search for web shells on Microsoft Exchange servers.


