
Report 1

APT10, also known as MenuPass Group, is a Chinese cyber espionage group that has been tracked since 2009. They have historically targeted construction and engineering, aerospace, and telecom firms, as well as governments in the United States, Europe, and Japan. In June 2016, APT10 expanded their operations, targeting a Japanese university and later expanding to more widespread targeting in Japan. They have targeted manufacturing companies in India, Japan, and Northern Europe, a mining company in South America, and multiple IT service providers worldwide. APT10 unveiled new tools in 2016/2017, including backdoors like HAYMAKER, SNUGRIDE, and BUGJUICE, as well as a customized version of the open-source QUASARRAT RAT. These new tools show APT10's capability development and innovation. The threat actor has used traditional spear phishing methods as well as accessed victims through global service providers, demonstrating a mix of traditional and novel techniques. The report indicates that APT10 is a threat to organizations worldwide, and while their pace of operations may slow following public disclosure, they are likely to return with new tactics, techniques, and procedures. The report was last updated on Nov 29, 2023.





Report 2

APT10, also known as Stone Panda, targeted Japanese corporations in July 2018 using the UPPERCUT backdoor. The threat actor, a Chinese cyber espionage group, sent spear phishing emails containing malicious documents related to maritime, diplomatic, and North Korean issues. The UPPERCUT backdoor, previously known as ANEL, was updated with new features and techniques, including the use of Windows certutil.exe for payload decoding. The malware dropped files, decoded them, and executed shellcode to load an updated variant of UPPERCUT. A unique feature in the latest version was the use of unique Blowfish encryption keys for each C2 address. APT10's capability to update and maintain their malware indicates a high level of sophistication. To mitigate the threat, users are advised to disable Office macros and avoid opening documents from unknown sources. The FireEye Multi-Vector Execution (MVX) engine can detect and block this threat. The report was last updated on August 10, 2023, providing detailed insights into the evolving tactics of the threat actor.





Report 3

Summary:
APT10, managed by the Tianjin bureau of the Chinese Ministry of State Security, was responsible for the Cloud Hopper attacks on global clients of Managed Service Providers in 2016. Three actors, Zheng Yanbin, Gao Qiang, and Zhang Shilong, were identified as being associated with the attacks. Evidence suggests that Gao Qiang has been working with the Chinese state, with Uber receipts showing his travel between work at Huaying Haitai and the Tianjin State Security Bureau headquarters. This connection indicates a link between APT10 and the Chinese Ministry of State Security, similar to the APT3 model. The report provides insight into the capabilities and novel techniques used by APT10, highlighting their infiltration of western infrastructure and ties to Chinese intelligence services. Date: August 15, 2018. Targeted victims: Global clients of Managed Service Providers.





Report 4

Summary:
- Threat actor: Stone Panda, APT 10, menuPass
- Region: China
- Operating sector: Aerospace (Airbus)
- Date: January 2019
- Evidence of capability: Hackers in China targeted Airbus' information systems, gaining access to personal data of employees in Europe, specifically professional contact and IT identification details. The attack was believed to be conducted by the APT 10 group, showing a high level of complexity and sophistication in their techniques. The hackers were attempting to access technical documents related to European aircraft, prompting Airbus to reinforce security measures and investigate the breach. The attack was reported by French publication Challenges, indicating the novelty and advanced nature of the tools and techniques used by the threat actor.





Report 5

Summary:
The threat actor known as ChessMaster, linked to APT 10 and menuPass, targeted Japanese academe, technology enterprises, media outfits, managed service providers, and government agencies. The campaign utilized malware-laden spear-phishing emails with decoy documents. The threat actor's arsenal included novel tools and techniques such as malicious shortcuts, PowerShell, self-extracting archives, runtime packers, second-stage payloads, hacking tools, TinyX, and RedLeaves. The campaign showed similarities to APT 10's Operation Cloud Hopper, indicating a shared cyberespionage game. The report was presented at the RSA Conference 2017 Asia Pacific & Japan on July 27, 2017, in Marina Bay Sands, Singapore. The report was updated on August 14, 2017, to include Indicators of Compromise related to ChessMaster's campaigns.





Report 6

Summary:
- Threat actor: APT10, also known as Stone Panda, menuPass
- Region: Taiwan
- Operating sector: Financial sector
- Date: Attacks started in November 2021 and were ongoing in February 2022
- Evidence of capability: Exploited vulnerability in security software used by 80% of local financial organizations, used advanced obfuscation techniques, leveraged reflective code loading, planted ASPXCSharp web shell, used Impacket tool, installed Quasar RAT for persistent remote access
- Novelty of tools and techniques: Advanced obfuscation techniques, reflective code loading, ASPXCSharp web shell, Impacket tool, Quasar RAT
- Objective: Exfiltration of brokerage information, PII data, disruption of investment during economic growth period
- Motivation: Not financial gain, but espionage and disruption
- Previous targeting: Chinese cyberespionage groups have targeted various sectors in Taiwan for years.





Report 7

Summary:
- Threat actor: Chinese state-backed hacking group APT10, also known as Stone Panda
- Region: India
- Operating sector: Healthcare (vaccine makers)
- Victims: Serum Institute of India (SII) and Bharat Biotech
- Date: March 1, 2021
- Evidence of capability: Identified gaps and vulnerabilities in IT infrastructure and supply chain software
- Novelty of tools and techniques: Targeting weak web servers and content-management systems
- Motivation: Exfiltrating intellectual property for competitive advantage
- Connection to Chinese Ministry of State Security
- Previous cyber-attacks targeting COVID-19 vaccine companies in multiple countries

(Source: https://www.cnbctv18.com/healthcare/chinese-hackers-target-indian-vaccine-makers-sii-bharat-biotech-says-security-firm-8461981.htm)





Report 8

Summary:
The threat actor known as Stone Panda, APT 10, or menuPass has been observed utilizing compiler-level obfuscations in their malware samples. The malware samples analyzed by the Carbon Black Threat Analysis Unit (TAU) included opaque predicates and control flow flattening techniques. The malware, specifically the ANEL (UpperCut) RAT program used by APT10, was observed in Japan. TAU investigated and modified the HexRaysDeob tool to defeat these obfuscations, achieving a deobfuscation success rate of 89% in tested samples. The modifications included new patterns for opaque predicates, data-flow tracking, analysis in multiple maturity levels, handling multiple control flow dispatchers, and various jump cases for control flow flattening. The tool's effectiveness in deobfuscating the ANEL malware suggests a broader applicability to other threat actors utilizing similar obfuscation techniques. The report was published on February 25, 2019, by Takahiro Haruyama of VMware TAU.





Report 9

Malformed report





Report 10

Malformed report





Report 11

Malformed report.





Report 12

Summary:
The threat actor known as "Stone Panda, APT 10, menuPass" conducted an advanced, persistent attack targeting global telecommunications providers, with evidence suggesting Chinese affiliation. The operation, named "Operation Soft Cell," focused on obtaining high-value data, resulting in a complete network takeover. The threat actor aimed to steal CDR records and compromised sensitive information like usernames, passwords, billing data, and call records. The tools and techniques used, such as modified China Chopper web shell, Mimikatz for credential stealing, and PoisonIvy RAT for maintaining access, were associated with Chinese threat actors like APT10. The attack, active since at least 2012, involved multiple waves of attacks over a 6-month period. The threat actor's infrastructure indicated operations in China, Hong Kong, and Taiwan. The motive behind the attack was likely espionage for sensitive information, with a high probability of state sponsorship from China. The threat actor's behavior and tools pointed towards APT10 or a similar threat actor. The report highlighted the importance of attribution accuracy and ongoing monitoring of the threat actor's activity. The investigation is ongoing, with efforts to track the threat actor's tools and compromised organizations. The report provided security recommendations for organizations to enhance their defenses against similar attacks. The operation demonstrated the threat posed by nation-state actors targeting critical infrastructure like telecommunications providers.





Report 13

Malformed report





Report 14

Stone Panda, also known as APT 10, MenuPass, and Red Apollo, is a Chinese state-sponsored cyberespionage group that has been operating since 2006. They have been attributed to the Tianjin State Security Bureau of the Ministry of State Security by the United States Department of Justice. Stone Panda targets aerospace, engineering, and telecom firms, as well as governments considered rivals of China. They have been tracked since 2009 and are now considered a threat to organizations worldwide. Stone Panda uses tactics such as zero-days, phishing, backdoors, RAT, and keylogging. They have been involved in operations like Operation Cloud Hopper, targeting MSPs in various countries, and have been implicated in attacks on government and private organizations in the Philippines and Japan. In March 2021, they targeted Bharat Biotech and the Serum Institute of India for intellectual property exfiltration. Stone Panda's use of sophisticated tools and techniques, along with their long-standing presence in the cyberespionage landscape, demonstrates their advanced capabilities and persistent threat to global organizations.





Report 15

Stone Panda, also known as APT 10 and menuPass, is a threat group originating from China that has been active since around 2009. The threat actor has targeted various sectors including healthcare, defense, aerospace, and government, with a focus on Japanese victims since at least 2014. Stone Panda has been observed using a wide range of tools and techniques, including Cobalt Strike, Mimikatz, and Poison Ivy, among others. Notable hacking operations include spear-phishing attacks in 2016, the "Cloud Hopper" campaign targeting managed IT service providers, and the "TradeSecret" operation targeting the National Foreign Trade Council in 2017. Stone Panda has also been involved in attacks on telecommunications providers and the aerospace sector, with reported operations continuing into 2022. The threat actor has been linked to state-sponsored activity, specifically the Tianjin bureau of the Chinese Ministry of State Security and Huaying Haitai, with a motivation for information theft and espionage. Stone Panda's global reach has targeted victims in countries such as the USA, Japan, Australia, and the UK. The threat actor has been the subject of counter operations, including indictments against Chinese hackers in 2018 and EU sanctions in 2020.





Report 16

Stone Panda, also known as APT 10 and menuPass, conducted a new APT campaign targeting Japanese academics and organizations from September to November 2016. The victims included Japanese academics, pharmaceutical companies, and a US-based subsidiary of a Japanese manufacturing organization. The threat actor used known malware like PlugX and Poison Ivy, along with a new Trojan called "ChChes," which was unique to this group. The ChChes samples were digitally signed using a certificate leaked from HackingTeam. The threat actor spoofed sender email addresses, including those associated with the Sasakawa Peace Foundation and The White House, to send spear phishing emails. The C2 infrastructure used in the attacks was largely actor-registered. The menuPass group, believed to originate from China, has been active since 2009 and has targeted Japanese organizations since at least 2014. The ChChes malware family used in the attacks had capabilities such as encryption, executing shell commands, uploading and downloading files, loading and executing DLLs, and listing bot commands. The lack of persistence in ChChes suggests it was used as an initial infiltration tool. The attacks highlight the ongoing threat posed by menuPass to Japanese organizations and the need for awareness of spear phishing. Palo Alto Networks customers are protected from these malware families and C2 infrastructure.


