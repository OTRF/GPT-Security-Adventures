
Report 1

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Russia-based operator (Wizard Spider), Eastern European-based operator (Lunar Spider)
- Operating sector: Banking malware distribution
- Victims: Not specified
- Date: February 7, 2019
- Evidence of capability: Custom TrickBot module associated with Lunar Spider, distribution of TrickBot by BokBot, modified TrickBot lateral movement module
- Novelty of tools and techniques: Custom loader, Base64-encoded PE file, encrypted strings with 256-bit AES, renamed TrickBot modules
- Relationship between Wizard Spider and Lunar Spider established through historical connections with Dyre and Neverquest malware operations.





Report 2

Summary:
- Threat actor: Conti Group
- Region: Global (targeted organizations and governments across the globe)
- Operating sector: Various, including critical infrastructures, chip manufacturers, environmental agencies, and banks
- Type of company: Taiwanese chip manufacturer Advantech, Scotland’s Environmental Protection Agency, Bank Indonesia, among others
- Evidence of capability: Responsible for over a thousand attacks against critical infrastructures, with estimated earnings in the billions
- Novelty of tools and techniques: Utilized semi-automated ransomware, gained access through malware operated by other groups, targeted individuals with elevated privileges, and had a robust organizational structure with various teams
- Operation time window: Early builds observed in late 2019, first public report of ransomware in mid-2020, leaks in February 2022, dissolution in August 2022
- Lessons learned: Former members and affiliates formed new threat groups with improved security policies, emphasizing the continuous evolution and proliferation of sophisticated threat actors.





Report 3

Summary:
The threat actor known as "Wizard Spider, Gold Blackburn" is a highly sophisticated cybercrime group that evolved from the GameOver Zeus era to become the elite "TrickBot" group. Operating since 2013, they have pioneered the cybercrime-as-a-service (CaaS) model and developed the TrickBot malware into a flexible, universal, module-based crimeware solution targeting corporations. By 2019, they introduced the Anchor project, a new addition to their arsenal, which integrates APT capabilities into their model, allowing for targeted data extraction and long-term persistency. The Anchor project combines various tools and methods, including the use of Lazarus Group's PowerRatankba toolkit, indicating a collaboration between TrickBot and nation-state actors. This integration marks a significant evolution in cybercrime, blurring the lines between crimeware and APT, and creating a holistic ecosystem of cybercrime. The Anchor project represents the culmination of years of cybercrime evolution and establishes TrickBot as a groundbreaking force in the cyber threat landscape. (Date: December 10, 2019)





Report 4

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Global
- Operating sector: Entertainment
- Type of company: Movie streaming service
- Date: May 26, 2021
- Evidence of capability: BazaLoader malware distribution requiring significant victim interaction, use of call centers, creation of fake movie streaming service "BravoMovies"
- Novelty of tools and techniques: Leveraging phone-based customer service representatives, intricate attack chain involving fake movie titles, use of fake movie posters from open-source resources
- Campaign details: BazaLoader downloader used in campaign, emails directing victims to call customer service line, website with malicious content, Excel sheet with macros downloading BazaLoader
- Indicators of Compromise: Domains, IPs, URLs, and SHA256 hash associated with the campaign
- Conclusion: Threat actors taking advantage of human behavior trends related to online streaming service subscriptions during the COVID-19 pandemic, using entertainment subscription themes to lure victims.





Report 5

Summary: The threat actor "Wizard Spider, Gold Blackburn" has been identified as the developer of a new stealthy network-hacking malware called BazarBackdoor, linked to the TrickBot gang. The malware is used in phishing campaigns targeting corporate networks, with lures such as customer complaints and COVID-19 themed documents. The threat actor utilizes the Sendgrid email marketing platform for distribution. BazarBackdoor is capable of deploying a network-compromising toolkit and is injected into the svchost.exe process using advanced techniques like Process Hollowing and Process Doppelgänging. The malware communicates with command and control servers using Emercoin decentralized DNS resolution service, making it difficult for law enforcement to seize control. Additionally, the threat actor deploys the Cobalt Strike penetration testing and post-exploitation toolkit on victim machines to gain footholds in corporate networks. The strong ties between BazarBackdoor and TrickBot suggest that the same core team is behind both malware, posing a significant threat to corporate networks. Businesses are advised to be vigilant and educate employees to prevent infection through malicious email links. Date: April 24, 2020.





Report 6

Malformed report.





Report 7

Summary: The threat actor "Wizard Spider, Gold Blackburn" has been identified by Bitdefender Labs for targeting select telecommunication services in the US and Hong Kong. The threat actor utilizes a new Trickbot module that bruteforces RDP connections. The targets of the attacks are in the telecommunication sector. The capability of the threat actor is evidenced by the use of novel tools and techniques, such as the Trickbot module. The report does not specify a specific date or operation time window for the attacks.





Report 8

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Date: November 1, 2021
- Region: Global
- Operating sector: Jewelry industry
- Victims: Celebrity jewelry house Graff
- Evidence of capability: Conti ransomware variant used to compromise systems and steal data of celebrities like Oprah Winfrey, Tom Hanks, and others.
- Novelty of tools and techniques: Conti gang exfiltrates data, threatens to publish if ransom not paid, and sells access to compromised networks.
- Response: Graff swiftly shut down network, informed affected individuals, and worked with law enforcement.
- Investigation: UK's Information Commissioner's Office involved, but attribution and apprehension of cybercriminals challenging.
- Future implications: Graff unlikely to pay ransom, leading to potential publication of more stolen data by threat actor.





Report 9

Summary:
On June 22nd, 2021, the City of Liege, Belgium, experienced a ransomware attack that disrupted its IT network and online services. The attack affected civil status and population services, leading to the cancellation of appointments for town halls, birth registration, weddings, and burial services. Online forms for event permits and paid parking were also impacted. While officials did not specify the type of attack, Belgian media outlets reported it was the work of the Ryuk ransomware gang. The incident highlights the vulnerability of local city networks to ransomware attacks due to limited resources for top-tier security measures. This attack on Liege is part of a trend where major municipalities worldwide have fallen victim to similar cyber threats. The EU is considering creating a joint rapid response force to assist member countries and cities in dealing with cyber-attacks.





Report 10

Summary: Wizard Spider, specifically the Conti (Ryuk) group, has been identified as a threat actor operating data leak sites, joining other ransomware gangs in this tactic. The group has targeted victims in various regions and sectors, including companies in the operating sector. Evidence suggests that the threat actor has advanced capabilities in deploying ransomware attacks and utilizing data leak sites to pressure victims into paying ransom. The tools and techniques used by Conti (Ryuk) demonstrate a level of sophistication and novelty in the cybercriminal landscape. The report does not specify a specific date or operation time window for the activities of Wizard Spider.





Report 11

Summary:
The Conti ransomware gang, affiliated with the Wizard Spider and Gold Blackburn threat actors, has shifted its business model to selling access to organizations it has hacked. This change was noted in the victim shaming blog, where stolen data may be published or sold if ransom negotiations fail. The move to sell access is seen as a novel tactic, possibly to bring victims to the negotiating table. The threat actor's capability is evidenced by their ability to conduct ransomware attacks in less than 3 days. The Conti gang's shift aligns with other ransomware groups focusing on extorting companies for not publishing or selling stolen data. The report also highlights the challenges faced by ransomware groups in managing data-leak sites and the potential for investigators to infiltrate these groups. The operation time window for these activities is not specified in the report.





Report 12

Summary:
The threat actor known as Conti Ransomware, operated by Russia-based threat actors, emerged around February 2020 and quickly became one of the most active ransomware groups. Conti operates using a Ransomware-as-a-Service (RaaS) model, paying affiliates for deploying the malware. Evidence suggests a connection between Conti and the "Wizard Spider" group, known for operating Ryuk ransomware. Conti's aggressive tactics include spearphishing, RDP exploitation, and purchasing network access. The group exfiltrates data, encrypts files, and demands ransom, with a history of targeting high-profile victims like JVCKenwood, Ireland's Health Service, and the Costa Rican government. Conti faced internal divisions and financial challenges, leading to its decline after declaring support for Russia during the Ukraine war. The future of Conti remains uncertain, with the emergence of potential successors like Diavol ransomware. Flashpoint has not definitively confirmed the dual attribution of Conti and Ryuk to Wizard Spider. The report was published on October 4, 2022, by Flashpoint.





Report 13

Summary:
In early December, a healthcare provider in Canada was targeted by two ransomware groups, Karma and Conti, simultaneously. The Karma group exfiltrated data without encryption, while the Conti group deployed ransomware less than a day later. Both groups gained entry through ProxyShell exploits on Microsoft Exchange Server. The attackers used advanced techniques like creating administrative accounts, deploying Cobalt Strike beacons, and exfiltrating data to Mega cloud storage. The Conti group encrypted files and dropped ransom notes, while the Karma group identified the target as a healthcare organization. The attack highlighted the risks of known vulnerabilities and the importance of multiple layers of defense. The attackers were able to achieve their goals despite some malware defenses in place. The report provides detailed technical information and indicators of compromise related to the attack.

Date: December 3, 2022
Region: Canada
Operating Sector: Healthcare
Threat Actor: Wizard Spider, Gold Blackburn

##################





Report 14

Summary:
The Conti ransomware gang, also known as Wizard Spider or Gold Blackburn, has threatened to leak victim data if details of ransom negotiations are shared with journalists. This threat comes after a recent incident involving JVCKenwood. The gang has introduced new rules to penalize victims or security researchers who leak screenshots of negotiations. The Conti gang is trying to control media coverage around its attacks and shift blame onto security researchers and journalists. This tactic is part of a larger trend where ransomware gangs try to control the narrative through press releases. The gang's actions demonstrate a novel approach to intimidation and manipulation in the ransomware landscape. The report was published on October 2nd, 2021, by Catalin Cimpanu.





Report 15

Summary: Wizard Spider, specifically the threat actor Gold Blackburn, targeted Ireland's Department of Health with Conti ransomware. Despite breaching the network, encryption failed due to the deployment of Cobalt Strike beacons. The attack on the Department of Health was part of a campaign targeting the Irish health sector. The Conti gang demanded a $19,999,000 ransom from the Health Service Executive (HSE) after claiming to have stolen 700 GB of data. The ransomware used appends the .FEEDC extension to encrypted files. Conti ransomware, a private Ransomware-as-a-Service operation linked to Russian-based cybercrime group Wizard Spider, shares code with Ryuk Ransomware. The attack on the Department of Health was blocked by antivirus software and investigative tools. The incident led to widespread disruption in Ireland's healthcare services, but the HSE refused to pay the ransom. 

Date: May 17, 2021.





Report 16

Malformed report





Report 17

Summary: The threat actor "Wizard Spider, Gold Blackburn" targeted Ireland's health service, HSE, with Conti ransomware, offering a free decryptor while still threatening to sell or release stolen data if a ransom is not paid. The attack led to widespread disruption in the healthcare system, forcing HSE to shut down IT systems. The decryptor provided by the threat actor can recover encrypted files, but the government of Ireland is cautious and will conduct a technical review before using it. Cybersecurity firm Emsisoft has also created a faster universal decryptor for assistance. The threat actor's capability is evidenced by the release of a 700 GB data dump, showcasing novel tactics in ransomware operations. (Date: May 20, 2021)





Report 18

Summary:
The threat actor known as Conti ransomware group, also referred to as Wizard Spider, has seemingly disappeared, leading to speculation of faking its own death. The group's dark web leak site used for negotiating ransoms with victims has vanished, impacting its ability to operate. Conti, believed to be based in Russia, has been involved in high-profile attacks, including one on Ireland's Health Service executive in May 2021. Evidence suggests that Conti executed a plan to transition to new ransomware "brands" and disperse its workforce to other affiliated gangs. The group's activity was notably reduced in May, with a shift towards other gangs allegedly linked to Conti. The novelty lies in Conti's attempt to retire under new names and disperse its members, showcasing a strategic evolution in response to potential sanctions and operational challenges. The report was published on June 23, 2022.





Report 19

Summary:
On January 21, 2022, the Conti ransomware gang targeted Delta Electronics, a Taiwanese electronics manufacturing company that supplies power components to Apple and Tesla. Over 1,500 servers and 12,000 computers were encrypted in the attack. The attackers demanded a $15 million ransom from Delta. The company is working with Trend Micro and Microsoft to contain the damage. The ransomware used was identified as a version of Conti. Delta's official websites remain offline, and the company is using an alternative web server to communicate with customers. The attack showcases the threat actor's capability to target high-profile companies in the technology sector and the use of novel tools and techniques to encrypt a significant portion of the victim's network.





Report 20

Summary: The threat actor "Wizard Spider, Gold Blackburn" associated with Conti ransomware has been observed prioritizing revenue and cyberinsurance data theft. Evidence suggests that the threat actor utilizes leaked training material to conduct ransomware attacks, including using legitimate software like Atera for backdoor access. The threat actor targets victims in the insurance and banking sectors, focusing on exfiltrating financial and cybersecurity policy documents. Novel techniques include using Atera for remote access and rclone for data synchronization to Mega cloud storage. The threat actor's operations were observed in August 2021. 

Date: August 17, 2021

Region: Global

Operating Sector: Insurance, Banking

Type of Company: Not specified

Capability of Threat Actor: Utilizes leaked training material, deploys legitimate software for persistence, targets specific data for exfiltration, employs novel techniques for data synchronization.





Report 21

Wizard Spider, Gold Blackburn, a threat actor, targeted victims in the U.S. operating in the accounting, tax, and payroll sectors during tax season. The threat actor utilized sophisticated tax-themed spam campaigns to deliver the TrickBot banking Trojan, a highly effective financial malware. The campaigns spoofed major accounting and payroll firms like Paychex and ADP, increasing the likelihood of success in deceiving recipients. The threat actor demonstrated capability in crafting convincing emails with malicious attachments, leveraging typosquatting and professional deception techniques. The campaigns were active from January to March 2019, targeting both personal and business email accounts. The malware used obfuscated macros in Excel documents to drop files that executed TrickBot, allowing for data theft and wire fraud. TrickBot's operators continuously enhance the malware's capabilities, including stealing RDP, VNC, and PuTTY credentials, showcasing their sophistication and resources. The threat actor's use of novel techniques and tools, combined with the targeting of high-profile sectors during a specific operational window, highlights the advanced nature of their operations.





Report 22

Malformed report.





Report 23

Summary: In a recent incident, a DOD contractor fell victim to a ransomware infection perpetrated by the threat actor known as Wizard Spider, Gold Blackburn. The attack targeted a company operating in the defense sector, highlighting the threat actor's focus on high-value targets. The incident demonstrates the capability of Wizard Spider to successfully compromise well-protected networks and deploy ransomware. The tools and techniques used by the threat actor are sophisticated and novel, posing a significant challenge to traditional cybersecurity defenses. The operation time window of the attack was not specified in the report.





Report 24

Summary: Wizard Spider, Gold Blackburn targeted the South Australian government employees, compromising sensitive personal information of up to 80,000 individuals through a ransomware attack on Frontier Software on November 13, 2021. The threat actor, identified as Conti ransomware, exfiltrated data including names, dates of birth, tax file numbers, and bank account details. The attack demonstrated the threat actor's capability to evade detection and exfiltrate data from segmented environments. Conti ransomware, known for its Ransomware as a Service operation, has been linked to high-profile incidents and continues to pose a significant threat, as seen in the attack against Nordic Choice Hotels. The incident highlights the importance of reviewing cybersecurity measures to prevent future breaches. The victims, mainly government employees, were advised to monitor their accounts closely and take necessary precautions. The attack showcases the novel use of ransomware tactics by threat actors, emphasizing the need for enhanced cybersecurity measures.





Report 25

Summary:
- Threat actor: Wizard Spider
- Date: July 01, 2021
- Region: Not specified
- Operating sector: Not specified
- Type of company of victims: Not specified
- Evidence of capability: Diavol ransomware used by Wizard Spider, unique encryption procedure using user-mode Asynchronous Procedure Calls (APCs) without symmetric encryption algorithm, anti-analysis techniques, termination of services and processes, encryption method using RSA only, deletion of shadow copies, changes to desktop wallpaper.
- Novelty of tools and techniques: Diavol ransomware is a new family, uses unique encryption procedures, anti-analysis techniques, and asynchronous I/O operations, no symmetric encryption used, errors in hardcoded configuration, potential link to Conti and Egregor ransomware.
- Malware samples: Diavol (locker.exe), Conti v3 (locker64.dll), Conti (locker.exe)
- IOCs: File hashes, file names, file paths, IPs, URLs, domains.
- MITRE ATT&CK Techniques: Obfuscated Files or Information, System Information Discovery, Application Layer Protocol: Web Protocols, Service Stop, Impair Defenses: Disable or Modify Tools, Network Share Discovery, Inhibit System Recovery, Inter-Process Communication: Component Object Model, Data Encrypted for Impact, Data Destruction.





Report 26

Malformed report





Report 27

Summary: The threat actor "Wizard Spider, Gold Blackburn" targeted the engineering firm Parker-Hannifin Corporation based in Ohio, specializing in aerospace hydraulic equipment. The data breach occurred between March 11 and March 14, 2022, with the Conti ransomware gang claiming responsibility. The stolen data included personal information of employees, such as Social Security Numbers, financial account information, and health insurance details. The threat actor's capability is evidenced by the exfiltration of specific files from the firm's computers. The novelty of the tools and techniques used by the threat actor is demonstrated by the ransomware attack and subsequent data publication. The attack potentially compromised technical details and schematics valuable in engineering circles. The incident highlights the risk of phishing attacks, social engineering, identity theft, and bank fraud. The threat actor's actions pose a significant threat to the aerospace and industrial components sector.





Report 28

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Date: March 2, 2020
- Region: Global
- Operating sector: E-discovery and managed services
- Company targeted: Epiq Global
- Evidence of capability: Unauthorized activity detected, systems taken offline globally, third-party forensics firm conducting investigation
- Novelty of tools and techniques: Industry best practices in encrypting and protecting data, no evidence of data transfer or misuse
- Impact: Relativity e-discovery software instances offline, customers unable to work on review projects
- Restoration timeline: Days, not hours, before systems are restored.





Report 29

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Date: May 2021
- Victim: Exagrid, a backup appliance supplier
- Region: Global
- Operating sector: Data center hardware
- Evidence of capability: Conti ransomware attack, $2.6m ransom paid in bitcoins
- Novelty of tools and techniques: Cyber criminals downloaded employee and customer data, confidential contracts, and source code; negotiations involved sharing files via Sendspace, providing decryption tool via Mega.nz
- Embarrassing for Exagrid as they had previously emphasized strengths against ransomware
- ExaGrid's website claims to offer unique approach to protect backup data from compromise
- ExaGrid accidentally deleted decryption tool and had to request it again.





Report 30

Summary:
The threat actor "Wizard Spider, Gold Blackburn" targeted the British clothing brand FatFace in a ransomware attack on January 17th, 2021. The attack, attributed to the Conti ransomware group, resulted in the compromise of customer data including names, email addresses, mailing addresses, and partial credit card information. The threat actors demanded $8.5 million initially but settled for a $2 million payment for a decryption key and a promise not to leak the stolen 200GB of data. The attackers gained access to FatFace's network through a phishing attack and provided recommendations for improving network security to the victim. FatFace confirmed the ransomware attack and reported it to law enforcement and the Information Commissioner’s Office. The incident highlighted the need for businesses to enhance email filtering, phishing awareness, password policies, EDR technology, and offline backup strategies to mitigate such threats.





Report 31

Malformed report





Report 32

Summary: French IT giant Sopra Steria was targeted by the threat actor Wizard Spider, Gold Blackburn on October 20th, 2020, using Ryuk ransomware. Sopra Steria, a European IT company with 46,000 employees, was affected by the attack. Evidence suggests that the threat actor used BazarLoader to gain access to the network and deploy Ryuk ransomware, a technique increasingly used for high-value targets. The attack flow involved compromising a Windows domain controller to encrypt all devices on the network. The threat actor's capability and novel techniques indicate a sophisticated and evolving cyber threat.





Report 33

Summary:
- Threat Actor: GOLD ULRICK (Wizard Spider, Gold Blackburn)
- Region: Global
- Operating Sector: Various industries
- Type of Company: Not specified
- Evidence of Capability: Despite public disclosures of communications and operational details, GOLD ULRICK, operating the Conti ransomware scheme, has maintained and even increased its activity levels.
- Novelty of Tools and Techniques: GOLD ULRICK has continued to evolve its ransomware, intrusion methods, and data handling approaches, with a reported 50% payment success rate and an average payout of $700k.
- Operation Time Window: Ongoing, with a surge in new victims added to the Conti leak site in March 2022.
- Date of Report: April 21, 2022
- Source: Secureworks
- Malformed report





Report 34

Summary:
- Threat actor: GOLD ULRICK and GOLD BLACKBURN
- Region: Global
- Operating sector: Financially motivated cybercrime
- Victims: Hundreds of high-profile victims, including organizations targeted for ransomware attacks
- Date: Since mid-2018
- Evidence of capability: Leaked messages reveal collaboration and support among multiple threat groups, with a mature cybercrime ecosystem and interconnectivity
- Novelty of tools and techniques: Use of TrickBot, BazarLoader, Ryuk, Conti ransomware, PowerShell Empire, Cobalt Strike Beacon C2 servers
- Leaked data includes dossiers of threat actors with personal information
- Threat actor's leaks could be in response to pro-Russian statements
- Impact: Hundreds of victims affected, potential disruption of operations due to exposure of leaked data.





Report 35

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Global
- Operating sector: Malware distribution
- Victims: Companies in Active Directory (AD) environments with Domain Controllers (DC)
- Date: April 2020
- Evidence of capability: TrickBot, an information stealer, updated its propagation module from "mworm" to "nworm" to evade detection.
- Novel tools and techniques: Nworm retrieves an encrypted binary over network traffic, runs from system RAM, leaves no artifacts on infected DC, and disappears after reboot.
- Notable evolution: TrickBot's use of modules for propagation, with nworm being a significant change in tactics.
- Impact: TrickBot caused by nworm is not persistent on DCs, making it harder to detect and remove.
- Conclusion: TrickBot developers are adapting to avoid detection, emphasizing the importance of security practices and up-to-date systems to prevent infections.





Report 36

Summary: Bank Indonesia, the central bank of Indonesia, confirmed a ransomware attack by the Conti group, leaking non-critical data. The attack occurred last month, with no disruption to operations. Conti, linked to the Wizard Spider group, claimed responsibility and threatened to leak more data if a ransom is not paid. The group is known for using BazarLoader and TrickBot malware to gain access to networks and deploy ransomware. Conti has targeted high-profile organizations globally, including Ireland's Department of Health and marketing giant RR Donnelly. The FBI, CISA, and NSA issued a warning about increased Conti ransomware activity. Date: January 20, 2022. Region: Indonesia. Operating Sector: Banking. Type of Company: Central Bank.





Report 37

Summary: JVCKenwood, a multinational electronics company based in Japan, was targeted by the Conti ransomware group, claiming to have stolen 1.5TB of data and demanding a $7 million ransom. The attack occurred on September 22nd, with servers in Europe being breached. Evidence of data theft was provided by the threat actors, including a scanned passport of a JVCKenwood employee. Conti ransomware is believed to be operated by the TrickBot group and has been involved in high-profile attacks against various organizations, including healthcare providers. The ransomware gang has faced controversy after a leaked attack playbook. JVCKenwood has not indicated whether they will pay the ransom. The attack highlights the capability of the threat actor and the novel techniques used in the operation.

Date: September 30, 2021

Region: Europe

Operating Sector: Electronics

Type of Company: Multinational electronics company





Report 38

Summary: K12 Inc., an online schooling giant, was targeted by the Ryuk ransomware in mid-November, leading to a data leak threat. The threat actor, identified as Wizard Spider or Gold Blackburn, gained access to student data and other information. K12 paid the ransom to prevent the data leak, utilizing their cyber insurance for the payment. The threat actor is known for stealing unencrypted data before encrypting devices, engaging in 'double-extortion' tactics. The incident did not impact K12's online Learning Management System or affiliated charter schools. The ransomware negotiation firm Coveware advises against paying ransoms due to the uncertainty of threat actors keeping their promises regarding stolen data. Date: December 2, 2020. Region: Global. Operating Sector: Education. Type of Company: Online schooling.





Report 39

Summary: On January 28, 2022, KP Snacks, a major British snack producer, was targeted by the Conti ransomware group, leading to disruptions in deliveries to supermarkets. The attack resulted in supply chain disruptions affecting leading superstores in the UK, with delays expected until the end of March. The threat actor gained access to sensitive files, including employee records and financial documents, and threatened to leak proprietary data if a ransom was not paid. Conti, linked to the Wizard Spider Russian cybercrime group, is known for targeting high-profile organizations and has been associated with other malware such as Ryuk and TrickBot. The FBI, CISA, and NSA have issued warnings about the increased activity of Conti ransomware attacks.





Report 40

Summary: In July 2020, leading toy maker Mattel was hit by a ransomware attack, impacting some business functions but not leading to data theft. The attack was discovered on July 28, 2020, and Mattel took measures to contain it and restore critical operations. The company, known for brands like Barbie and Hot Wheels, disclosed the attack in a filing with the SEC, stating that no sensitive data was exfiltrated. While the filing did not specify the ransomware operation responsible, a source indicated it was linked to TrickBot. TrickBot infections often lead to network-wide compromises followed by Ryuk or Conti ransomware encryption. Mattel has not provided further details about the attack. 

Date: July 28, 2020
Region: Global
Operating Sector: Toy Industry
Type of Company: Leading toy maker
Threat Actor: Wizard Spider, Gold Blackburn





Report 41

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Not specified
- Operating sector: Not specified
- Type of company: Not specified
- Date: November 20, 2020
- Evidence of capability: TrickBot group released LightBot, a reconnaissance tool for high-value targets, used in phishing campaigns to gather network information for potential attacks.
- Novelty of tools and techniques: LightBot is a lightweight PowerShell script focused on reconnaissance, similar to FIN7 profiler script, used to handpick Ryuk ransomware targets.
- Tools collect data like computer name, hardware info, Windows version, IP address, and create scheduled tasks for persistence.
- Adaptability and resiliency shown by the hacking group despite previous takedown efforts.
- Warning for admins to be vigilant against LightBot phishing campaigns leading to potential Ryuk or Conti ransomware attacks.





Report 42

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Louisiana, France, Canada, Mexico
- Operating sector: State agencies, hospital, oil company
- Date: November 2019
- Evidence of capability: Targeted ransomware attacks using Ryuk and DoppelPaymer variants
- Novelty of tools and techniques: Use of Tor "hidden service" Web portal for communication with victims
- Louisiana's Office of Technology Services, Charles-Nicolle University Hospital, Nunavut government, and PEMEX were targeted
- Attackers did not receive ransom payments due to victims having backup systems in place
- FBI emphasized the importance of cyber hygiene, including backups and software updates, to prevent ransomware attacks
- State and local agencies, as well as hospitals, are vulnerable targets due to reliance on legacy systems and lack of information security skills.





Report 43

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Global
- Operating sector: Marketing
- Type of company targeted: Marketing giant RRD (RR Donnelly)
- Date: December 27, 2021
- Evidence of capability: Stole data in Conti ransomware attack, leaked 2.5GB of data, targeted a leading integrated services company with a revenue of $4.93 billion in 2021
- Novelty of tools and techniques: Used Conti ransomware, exfiltrated data, timed attack to coincide with significant financial event (merger agreement)
- RRD confirmed data theft, took measures to protect information
- FBI warning about ransomware attacks coinciding with financial events
- RRD did not respond to further questions about the attack.





Report 44

Summary: McMenamins breweries, a popular chain in Oregon and Washington, was targeted by a Conti ransomware attack on December 12th, disrupting operations. The attack encrypted servers, workstations, and point-of-sale systems, leading to the shutdown of IT systems and credit card processing. While customer payment data was not impacted, internal employee data may have been compromised. The threat actor, Conti, is known for high-profile attacks and is believed to gain access through phishing or exploiting vulnerabilities. The attack highlights the threat actor's capability to steal data and deploy ransomware, with potential impacts on customer data security. The use of Conti ransomware in this attack showcases the group's advanced techniques and the need for heightened cybersecurity measures.





Report 45

Summary:
- Threat actor: WIZARD SPIDER, LUNAR SPIDER
- Date: March 17, 2019
- Evidence of collaboration: New BokBot proxy module used by WIZARD SPIDER in conjunction with TrickBot operated by LUNAR SPIDER.
- Capability: Ability to steal sensitive information and conduct fraudulent wire transfers.
- Novelty: Proxy module contains potent BokBot features within TrickBot malware framework.
- Technique: Man-in-the-Middle attacks against web browsers on infected hosts.
- Victims: Not specified.
- Region: Not specified.
- Operating sector: Not specified.
- Company type: Not specified.





Report 46

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: New Orleans, Louisiana
- Operating sector: Municipal government
- Date: December 16, 2019
- Evidence of capability: Utilized Ryuk ransomware, affected over 4,000 computers and servers, shut down official websites and services, compromised city workers' credentials
- Novelty of tools and techniques: Ryuk ransomware used in conjunction with banking trojans, known for large ransomware payouts
- Investigation ongoing by state and federal law enforcement agencies
- Potential data loss minimized due to quick response and offline backups
- Recent research warns against paying ransom for decryption key due to potential data corruption
- Attack linked to previous Ryuk incidents in other municipal governments.





Report 47

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Global
- Operating sector: Online banking users
- Type of company: Not specified
- Date: March 09, 2020
- Capability: Wizard Spider, Gold Blackburn, known for TrickBot malware, spreading new variant via Word document, collecting sensitive information, controlling victim's computers, delivering other malware like Emotet.
- Novelty: New variant of TrickBot spreads via Word document, heavily obfuscated JavaScript code, bypasses auto-analysis tools, downloads payload from server, maintains persistence by copying files to startup folder, communicates with C&C server for commands and module downloads.
- Tools and techniques: Malicious Word document, obfuscated JavaScript code, base64 encoded payload, DLL files executed in rundll32.exe, modular Trojan behavior, communication with C&C server for commands and module downloads.





Report 48

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: New Zealand
- Operating sector: Healthcare
- Victims: Waikato District Health Board and affiliate hospitals
- Date: May 19, 2021
- Evidence of capability: Ransomware attack led to IT services shutdown, surgeries postponed, and patient notes inaccessible
- Novelty of tools and techniques: Initial incursion believed to be via email attachment, ransom not paid
- Threat actor's history: Linked to previous attacks on Scottish Environmental Protection Agency and Irish hospital
- Response: Working on system restoration and remediation, investigation ongoing
- Impact: Disruption of clinical services, surgeries, and outpatient activities.





Report 49

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: United States
- Operating sector: Telecommunications
- Type of company: Nokia subsidiary, SAC Wireless
- Date: June 16, 2021
- Evidence of capability: Conti ransomware attack breached SAC Wireless network, stole data, and encrypted systems. Personal information of employees and dependents stolen.
- Novelty of tools and techniques: Conti ransomware gang demanded ransom, threatened to leak stolen data online. Conti shares code with Ryuk Ransomware. Gang breached Ireland's Health Service Executive and Department of Health.
- Countermeasures taken by SAC Wireless: Changed firewall rules, disconnected VPN connections, activated geo-location policies, provided employee training, deployed monitoring tools, expanded multi-factor authentication.
- Additional information: Conti operators attempted to breach US healthcare and first responder organizations. Disgruntled affiliate leaked gang's training materials.





Report 50

Summary: Nordic Choice Hotels was targeted by the Conti ransomware group, impacting guest reservation and room key card systems. The incident occurred on December 2nd, leaving staff without access to reservation systems. The attack potentially leaked guest booking information, affecting Nordic Choice Club members and current hotel guests. The threat actor, Conti ransomware, is associated with the Russian-based cybercrime group Wizard Spider and has targeted healthcare and first responder organizations in the past. No ransom demand has been made yet, and law enforcement agencies have been engaged. The attack is still in early stages, and negotiations with the threat actors have not begun. The hotel group is working to restore normal operations and advises customers to be cautious of suspicious communications.





Report 51

Summary: Wizard Spider, specifically the Gold Blackburn subgroup, targeted one of Roman Abramovich's companies with ransomware. The incident was reported in 2024 by ZDNET. This threat actor has demonstrated the capability to target high-profile individuals and companies, indicating a high level of sophistication. The use of ransomware as a tool for financial gain is a common tactic employed by Wizard Spider. The targeting of a company owned by a prominent figure like Roman Abramovich highlights the audacity and boldness of the threat actor. The tools and techniques used by Wizard Spider, such as ransomware, are not novel but effective in causing disruption and financial loss to the victims. The incident serves as a reminder of the ongoing threat posed by sophisticated threat actors like Wizard Spider in the cybersecurity landscape.





Report 52

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Canada
- Operating sector: Technology
- Type of company: Global tech manufacturer (Panasonic)
- Date: February 2022
- Evidence of capability: Ransomware attack affected systems, processes, and networks, requiring extensive actions to address the issue.
- Novelty of tools and techniques: Embattled ransomware group Conti added Panasonic Canada to its list of victims despite previous security breach in November.
- Tools and techniques used: Malware, access to internal network, data exfiltration.
- Ongoing investigation to fully mitigate impacts from the incident.
- No mention of specific tools or techniques used by the threat actor.





Report 53

Summary:
The threat actor known as Conti, operated by Wizard Spider and Gold Blackburn, has shown resilience and adaptability despite leaks of internal chats in late February. The Russia-based ransomware gang quickly replaced exposed infrastructure and continued targeting new victims, including U.S.-based companies, with ransom demands. Evidence of their capability was seen in successfully completing two new data breaches post-leaks. Conti's network activity has increased, with attempts at breaches and phishing emails observed. The threat actor's ability to pivot and maintain operations showcases their expertise and determination. The gang's potential rebranding and adaptation in response to leaks indicate a continued threat to victims in the future. The report does not specify the operating sector or type of company targeted by Conti. Date: March 7, 2022.





Report 54

Summary: In April 2021, the threat actor known as Conti targeted the Broward County Public Schools in Florida, demanding a $40 million ransom, which was later lowered to $10 million. The attack affected the sixth-largest school system in the USA, with nearly 261,000 students. The threat actor's capability was demonstrated through the negotiation process and the use of ransomware. The novelty of the attack lies in the high ransom demand, showcasing the evolving tactics of ransomware gangs. The attack highlighted the financial constraints of public school systems and the impact of such demands on students and taxpayers. The incident serves as a reminder of the increasing threat of cybercrime to organizations in various sectors.





Report 55

Summary: The threat actor "Wizard Spider, Gold Blackburn" deployed Ryuk Ransomware in a cyberattack on the City of Durham, North Carolina, leading to the shutdown of its network. The attack was initiated through a phishing email, with the ransomware spreading through network servers. The attack caused disruptions in the city's emergency services, including the 911 call center and the Fire Department's phone service. The threat actor likely had access to the network for weeks before deploying the ransomware. Ryuk Ransomware is known to be associated with TrickBot Trojan, which steals data and spreads laterally through networks. The attack on Durham is part of a pattern of Ryuk Ransomware attacks targeting various sectors, including legal services and government entities. The attack demonstrates the threat actor's capability to disrupt critical services and highlights the ongoing risk posed by ransomware attacks. Date: March 8, 2020. Region: North Carolina. Operating Sector: Government. Type of Company: City services.





Report 56

Summary: The threat actor "Wizard Spider, Gold Blackburn" conducted a Ryuk ransomware campaign targeting Port Lavaca City Hall, affecting the local government's server, billing, and auto-pay systems. The attack demanded a ransom of US$200,000, with the city officials refusing to pay and working on system restoration. The incident incurred nearly US$50,000 in costs to the city. The threat actor demonstrated capability in encrypting files and disrupting operations, with evidence of targeting government entities in the region. The use of Ryuk ransomware and email system entry point indicate familiarity with advanced tools and techniques. The attack was reported to the FBI for investigation. Date: February 18, 2020.





Report 57

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Florida, United States
- Operating sector: Public sector (Florida Library System)
- Date: January 9, 2020
- Evidence of capability: Ryuk ransomware used in attack on Volusia County libraries, encrypted 20 servers and 600 computers, demanded ransom
- Novelty of tools and techniques: Ryuk ransomware used, no flaws in encryption, demands high ransom payments, attributed to "Wizard Spider" criminal group
- Impact: Cost of attacks estimated at $7.5 billion in 2019, multiple Florida municipalities victimized
- Response: Involvement of cybersecurity firms, law enforcement, and Department of Homeland Security
- Attribution challenges: Speculation on Russian ties of threat actor, difficulty in attribution due to tactics used
- Recovery options: Limited to restoring from backups or paying ransom, no flaws in encryption
- Conclusion: Ryuk ransomware poses significant threat to public and private sector organizations, demands high ransom payments for data release.





Report 58

Summary:
In March 2021, the Spanish government labor agency SEPE was targeted by the Ryuk ransomware, affecting over 700 agency offices across Spain. The attack encrypted the agency's network systems, causing delays in appointments but not affecting personal data, payroll, or unemployment benefits. Ryuk is a ransomware-as-a-service group known for its private affiliate program and high activity levels, with affiliates responsible for one in three ransomware attacks in the past year. The attack on SEPE is part of a trend of high-profile ransomware incidents in Spain, including attacks on Everis, Cadena SER, and Telefonica. The threat actor's capability is evidenced by the widespread impact of their attacks and the use of novel techniques to target high-profile organizations.





Report 59

Summary: The threat actor known as Wizard Spider, Gold Blackburn targeted the Fortune 500 company EMCOR with Ryuk ransomware. The attack was reported in 2024 by ZDNET. This incident demonstrates the capability of the threat actor to target high-profile companies in the industrial sector. The use of Ryuk ransomware indicates a sophisticated and financially motivated attack. The tools and techniques used by Wizard Spider, Gold Blackburn are considered novel and advanced, posing a significant threat to organizations. The attack highlights the need for enhanced cybersecurity measures to protect against such threats.





Report 60

Summary: Sandhills Global, a US-based trade publication and hosting company catering to various industries, suffered a ransomware attack by the Conti ransomware gang on October 2, 2021. The attack caused their websites to go offline and disrupted business operations, affecting well-known publications like Truck Paper and Machinery Trader. The Conti gang is known for stealing files before encrypting devices and demanding multi-million ransom demands. Sandhills Global has temporarily shut down operations to protect data and is working with cybersecurity experts to investigate and restore operations. The extent of data access or compromise is still under investigation. The attack demonstrates the capability of the threat actor in targeting specific sectors and using ransomware as a tool for extortion. The use of Conti ransomware and the targeting of a company in the machinery marketplace sector highlight the novelty and evolving tactics of the threat actor.





Report 61

Summary:
In late December 2020, the Scottish Environment Protection Agency (SEPA) was hit by a ransomware attack by the threat actor known as "Wizard Spider, Gold Blackburn." The attack resulted in the theft of 1.2GB of data, including sensitive information related to SEPA's business areas. The attack was likely orchestrated by international cyber-criminal groups aiming to disrupt public services and extort funds. SEPA refused to pay the ransom demanded by the attackers and is working with security experts, the Scottish government, Police Scotland, and the National Cyber Security Centre to investigate the incident. The threat actor used novel ransomware tools, possibly linked to the Conti ransomware gang, indicating a high level of sophistication. Recovery efforts are ongoing, and SEPA anticipates a significant period for full system restoration. The attack highlights the vulnerability of critical infrastructure to ransomware threats.





Report 62

Summary: Shutterfly, an online retail and photography manufacturing platform, disclosed a data breach after a Conti ransomware attack on December 3, 2021. The threat actor, identified as Conti, accessed personal information of employees, including names, salary details, and leave claims. The attack involved encrypting over 4,000 devices and 120 VMware ESXi servers belonging to Shutterfly. The Conti ransomware operation released 7.02 GB of stolen data, including finance, legal, customer service, and payroll information. Shutterfly is working with cybersecurity experts to investigate the attack and is offering two years of free credit monitoring to affected individuals. The incident highlights the capability of the threat actor in data exfiltration and the use of ransomware for financial gain.





Report 63

Summary: Shutterfly, a photography and personalized photo company, was targeted by the Conti ransomware gang approximately two weeks ago. The attack resulted in the encryption of over 4,000 devices and 120 VMware ESXi servers. Conti is known for its "double-extortion" tactic of stealing corporate data and threatening to release it if a ransom is not paid. The threat actor has a history of targeting high-profile organizations and is believed to be operated by a Russian hacking group. The attack on Shutterfly disrupted services for their corporate network, Lifetouch, BorrowLenses, and Groovebook. The ransomware gang is demanding millions of dollars as ransom. The attack highlights the capability of the threat actor to breach networks, steal data, and deploy ransomware. The incident was confirmed by Shutterfly, who stated that no financial information of customers was impacted. The US government recently issued an advisory on Conti ransomware attacks due to increased activity by the cybercrime gang.





Report 64

Summary:
- Threat actor: Conti ransomware gang, specifically Wizard Spider, Gold Blackburn
- Date: March 1st to March 3rd, 2022
- Region: United States
- Operating sector: Transportation industry
- Company type: Snap-on, a leading manufacturer of automotive tools
- Evidence of capability: Stole personal data including names, Social Security Numbers, dates of birth, and employee identification numbers
- Novelty of tools and techniques: Used Conti ransomware, known for attacks on high-profile organizations
- Snap-on disclosed data breach after detecting unusual activity in their network and shutting down all systems
- Conti ransomware gang claimed responsibility for the attack and leaked stolen data
- Snap-on offered free identity theft protection service to affected individuals.





Report 65

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Global
- Operating sector: Cybercrime
- Type of company of victims: Not specified
- Date: February 24, 2022
- Evidence of capability: Trickbot malware has been inactive since December 2021, indicating a shift in operations. Trickbot operators are suspected to be collaborating with Emotet operators, with evidence of joint activities. The threat actor group is transitioning from Trickbot to newer platforms like Emotet and Bazar, leveraging multiple malware families. The decrease in Trickbot campaigns and the continued deployment of ransomware linked to Trickbot suggest a strategic shift in operations.
- Novelty of tools and techniques: Trickbot operators are observed to be using Emotet and Bazar malware, indicating a shift towards more advanced and stealthy tools. The use of multiple malware families and the collaboration between threat actor groups demonstrate a sophisticated and evolving approach to cybercrime. The threat actor group is adapting to avoid detection and maintain operational effectiveness.





Report 66

Summary:
- Threat actor: Son of Conti, a Russian-speaking ransomware group
- Region: Costa Rica
- Operating sector: Government agencies, health services
- Date: April 2022 (attack on government agencies), May 2022 (attack on health services)
- Evidence of capability: Encrypting key servers, erasing medical records, causing national state of emergency
- Novelty of tools and techniques: Shift towards targeting politics, potential country extortion instead of traditional ransomware attacks
- Concerns about future attacks and lack of resources for cybersecurity in Costa Rica
- Threat actor's determination to continue operations under a different name
- Source: The Record from Recorded Future News

Overall, the Son of Conti threat actor group demonstrated advanced capabilities in targeting government agencies and health services in Costa Rica, signaling a shift towards political motivations in ransomware attacks. The attacks raised concerns about future incidents and highlighted the need for increased cybersecurity measures and international collaboration.





Report 67

Summary:
In October 2020, the threat actor "Wizard Spider, Gold Blackburn" targeted the Steelcase furniture giant, a leading office furniture manufacturer globally, with a Ryuk ransomware attack. The attack forced Steelcase to shut down its network to contain the spread. The threat actor utilized BazarLoader or TrickBot infections to gain remote access and deploy Ryuk ransomware. The attack was disclosed in an 8-K form filed with the Securities and Exchange Commission (SEC). The incident did not result in any data loss or loss of assets, and Steelcase is actively restoring its systems. The attack is part of a series of recent attacks by the same threat actor targeting organizations like Sopra Steria and Universal Health Services. The novelty of the attack lies in the use of advanced tools and techniques like BazarLoader and Ryuk ransomware.





Report 68

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Adelaide, Australia
- Operating sector: Local government (City of Onkaparinga council)
- Date: December 14, 2019
- Evidence of capability: Utilized Ryuk ransomware to lock down IT systems, affecting phones, emails, and public computers at libraries.
- Novelty of tools and techniques: Ryuk ransomware used to demand ransom, causing losses of $3.7 million globally since 2018.
- No personal information compromised in the attack.
- City of Onkaparinga council was the first Adelaide organization affected.
- Forensic investigations ongoing to determine the source of the attack.
- No ransom requested from the council, potential insurance coverage if needed.





Report 69

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: United States (Tampa Bay Times)
- Operating sector: Media (Tampa Bay Times)
- Date: January 27, 2020
- Evidence of capability: Ryuk ransomware attack on Tampa Bay Times, new variant of Ryuk stealer targeting government, financial, and law enforcement entities.
- Novel tools and techniques: Ryuk malware evolved to target specific sectors with a variety of malicious software, including Emotet and TrickBot in multi-stage attacks.
- New variant of Ryuk Stealer aimed at stealing large volumes of sensitive data.
- Focus on data exfiltration and encryption of valuable files to minimize detection.
- Use of FTP protocol for data exfiltration highlighted as a concern.
- Recommendations to filter incoming internet traffic and monitor outbound traffic to limit data exfiltration.





Report 70

Malformed report.





Report 71

Malformed report.





Report 72

Wizard Spider, also known as Gold Blackburn, has been identified as the threat actor behind a fileless TrickBot infection targeting Windows 10 64-bit operating systems. TrickBot is a sophisticated and modular Trojan horse that has evolved over the years to evade security controls. The threat actor's capability is evidenced by the use of novel techniques such as fileless deployment, injection into svchost processes, and encryption of communication with command-and-control servers. The change in TrickBot's deployment routine, specifically for Windows 10 devices, indicates a strategic adaptation to avoid detection. The report, dated August 8, 2019, highlights the continued evolution of banking Trojans like TrickBot, emphasizing the need for defenders to stay vigilant against evolving threats. The victims targeted by Wizard Spider are primarily in the banking and finance sector, demonstrating the threat actor's focus on financial gain.





Report 73

Summary:
The threat actor known as "Wizard Spider, Gold Blackburn" is behind the Ryuk ransomware, which has targeted various enterprise organizations worldwide, including the Tribune Publishing newspapers. The ransomware, discovered in mid-August 2018, is notable for its big game hunting tactics, targeting large organizations with critical assets for high ransom payments. Evidence suggests that Ryuk is linked to criminal groups Wizard Spider and CryptoTech, with Wizard Spider recently upgrading Ryuk with Wake-on-LAN and ARP ping scanner capabilities. The threat actor behind Ryuk has netted significant sums through ransom payments, with indications of ties to Russian cybercriminal groups. The infection vectors of Ryuk involve multi-attack campaigns with Emotet and TrickBot. Systems infected with Ryuk display ransom notes and encrypted files with the .ryk extension. Malwarebytes continues to track Ryuk campaigns and recommends security measures to mitigate attacks. Indicators of Compromise (IOCs) include specific file hashes associated with Ryuk variants. The threat actor's novel techniques and capabilities demonstrate a persistent focus on monetizing victims' data. The report was published on December 12, 2019, by Malwarebytes Labs.





Report 74

Top-Tier Russian Organized Cybercrime Group, Wizard Spider, operating in the crimeware sector, unveiled a fileless stealthy "PowerTrick" backdoor for high-value targets such as financial institutions. The threat actor, TrickBot, actively develops offensive tools like PowerTrick for stealthiness and reconnaissance, remaining undetected for targeted post-exploitation purposes. The PowerTrick backdoor is designed to bypass security controls and exploit secure networks, with the capability to execute commands and return results in Base64 format. TrickBot actors also utilize PowerShell utilities like 'letmein.ps1' for lateral movement and network profiling. The threat actor leverages various techniques and malware deliveries, including TrickBot Anchor Malware and TerraLoader with the "more_eggs" backdoor. The PowerTrick backdoor execution flow involves downloading a larger backdoor and performing actions on objectives, such as checking filesystem, downloading payloads, and executing commands. The threat actor's novel techniques include direct shellcode execution and modifying delivery systems to bypass security controls. The report provides indicators of compromise and IOCs associated with the threat actor. (Source: SentinelLabs, January 9, 2020)





Report 75

Wizard Spider, also known as Gold Blackburn, has been identified as the threat actor behind a recent TrickBot campaign targeting users via Department of Labor FMLA spam emails. The campaign leverages the Family and Medical Leave Act (FMLA) as context around COVID-19 to distribute the malware. TrickBot is a sophisticated banking Trojan operated by an organized cybercrime gang, capable of gaining complete control of infected devices and carrying out bank account takeovers, wire fraud, and ransomware attacks. The threat actor has been seen collaborating with ITG08, known as FIN6, to target the retail sector. The campaign uses malicious document files and macros to deliver the TrickBot payload, with novel techniques such as using cURL to download executables and executing them using zipfldr.dll. The threat actor's use of COVID-19-themed spam to deliver malware highlights their adaptability to current events and their ongoing efforts to target users globally. The campaign shows evidence of TrickBot's continued evolution and sophistication in carrying out financially motivated attacks. The report was published on April 30, 2020, by IBM X-Force.





Report 76

Summary:
- Threat actor identified as "Wizard Spider, Gold Blackburn" conducted operations involving TrickBot malware leading to Ryuk ransomware deployment.
- Operations active since at least December 2017, with a notable increase in the latter half of 2018, targeting victim organizations for large ransom payments.
- Evidence of interactive deployment of ransomware, utilizing EMPIRE and RDP connections for lateral movement within victim environments.
- Operations reportedly netted about $3.7 million in current BTC value.
- No definitive evidence linking Ryuk malware to North Korea, despite code similarities with Hermes ransomware.
- TrickBot administrator group suspected to be based in Eastern Europe, providing malware to cyber criminal actors.
- Evidence of consistent use of "gtags" to identify specific TrickBot users across incidents.
- Operations referred to as GRIM SPIDER, with variations in Ryuk deployment methods observed across engagements.
- Consistency in TrickBot group tags suggests management of implants post-exploitation.
- Implications include the growing popularity of deploying ransomware after gaining access to victim organizations through other methods.
- Operations expected to continue in 2019, emphasizing the need for organizations to prioritize proper remediation of all threats.





Report 77

Summary:
The threat actor "Wizard Spider, Gold Blackburn" has been identified pushing a 2FA bypass app named "TrickMo" to bank customers in Germany. The app is distributed by the TrickBot Trojan and is designed to bypass second-factor authentication for transaction authorization. TrickMo is sophisticated and possesses features to steal transaction authorization codes from victims. It is actively developed and specifically deployed in Germany, targeting the banking sector. The threat actor has been active since at least 2016, with TrickBot being used for bank fraud. TrickMo's novelty lies in its capability to overcome pushTAN app validations used by German banks. The threat actor uses advanced techniques like screen video recording and accessibility services to steal TAN codes. The threat actor also has a kill switch feature to remotely eliminate the malware. The report provides indicators of compromise and insights into the threat actor's evolving capabilities. The operation time window is ongoing, with the report published on March 24, 2020.





Report 78

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Japan
- Operating sector: Banking & Finance
- Type of company: Banks, e-commerce sites, cryptocurrency exchange platforms
- Date: December 3, 2019
- Evidence of capability: TrickBot Trojan, most active banking Trojan family, targeting Japanese banks for the first time, leveraging malicious spam and Emotet botnet for distribution, web injections on banking websites leading to online banking fraud, potential for TrickBot attacks turning into Ryuk ransomware attacks.
- Novelty of tools and techniques: TrickBot evolving with code modifications, targeting Japanese banks, using web injections, potential for Ryuk ransomware attacks, leveraging Emotet and TrickBot infections.
- Malware trends: TrickBot emerged in 2016, evolving rapidly, leading in the global chart of most active banking Trojan families.
- Mitigation tips: Tight control of system updates, layering security controls, role-based training, blacklisting malicious IPs, maintaining backup programs, launching incident response plans promptly.
- Contact for response assistance: X-Force Incident Response and Intelligence Services hotline.

Overall, the threat actor Wizard Spider, Gold Blackburn, operating through the TrickBot Trojan, has widened infection campaigns in Japan targeting banks, e-commerce sites, and cryptocurrency exchange platforms, with the potential for ransomware attacks. The threat actor's capability is evidenced by the use of web injections, Emotet botnet distribution, and the evolution of TrickBot. Mitigation strategies include system updates, security controls, training, blacklisting, backups, and prompt incident response. Contact X-Force for response assistance.





Report 79

Summary: Wizard Spider, Gold Blackburn threat actor, known for TrickBot malware, has evolved to evade analysis by checking screen resolution to detect virtual machines. TrickBot, initially a banking Trojan, now engages in various malicious activities, including lateral network spreading and credential theft. Evidence suggests the threat actor targets victims in the cybersecurity sector. The novelty lies in TrickBot's use of screen resolution as an anti-VM technique, specifically targeting resolutions commonly used in malware analysis virtual machines. This tactic aims to avoid detection by researchers and automated sandbox systems. The report was published on July 1, 2020, highlighting the ongoing threat posed by Wizard Spider, Gold Blackburn.





Report 80

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Global
- Operating sector: Various
- Type of company of victims: Not specified
- Capability evidence: Collaboration between Shatak phishers and TrickBot for Conti ransomware attacks, use of phishing emails with password-protected archives containing malicious documents, deployment of TrickBot and BazarBackdoor malware, network reconnaissance, data exfiltration, encryption of devices with Conti ransomware
- Novelty of tools and techniques: Collaboration between threat actors, use of reply-chain emails, base-64 encoded code, Cobalt Strike beacon deployment, use of 'Rclone' tool for data exfiltration, disabling Windows Defender's real-time monitoring, collaboration with other ransomware groups
- Date/Operation time window: Collaboration started in July 2021 and ongoing
- Source: https://www.bleepingcomputer.com/news/security/trickbot-teams-up-with-shatak-phishers-for-conti-ransomware-attacks/





Report 81

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Global
- Operating sector: Various, including banking & finance, energy & utility, government, healthcare
- Date: February 25, 2022
- IBM Security X-Force discovered a new version of Trickbot Group's AnchorDNS backdoor, now called AnchorMail or Delegatz, used in recent attacks ending with Conti ransomware deployment.
- Trickbot Group, known for Trickbot banking Trojan, has adapted to ransomware attacks using Bazarloader payloads and Conti ransomware-as-a-service.
- AnchorMail communicates with C2 server via email-based SMTP and IMAP protocols over TLS, a novel technique compared to AnchorDNS's DNS protocol.
- AnchorMail creates scheduled tasks for persistence, collects system information, and executes commands received from C2.
- AnchorMail is written in C++ and targets Windows systems, with a potential Linux variant.
- The threat actor's capability is evidenced by the sophisticated C2 communication mechanism and the use of novel techniques in malware development.





Report 82

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Italy
- Operating sector: Healthcare
- Type of company: Not specified
- Date: March 4, 2020
- Capability: Trickbot spam campaign targeting Italian e-mail addresses using Coronavirus fears to spread malware. Utilizes weaponized Word document with VBA script to deliver Trickbot variant. Similar mechanisms used in previous campaigns. 
- Novelty: Twist of using Coronavirus fears in spam message, but delivery mechanisms are not new. 
- Tools and techniques: Enclosed scripted Word document, JavaScript dropper, VBA script, PHP script, obfuscated JavaScript file, Base64-encoded Windows executable, malicious payload. 
- IoCs: hxxps://185[.]234.73.125/wMB03o/Wx9u79.php, 23[.]19.227.235
- Source: https://news.sophos.com/en-us/2020/03/04/trickbot-campaign-targets-coronavirus-fears-in-italy/





Report 83

Summary:
During June and July, F5 researchers observed Trickbot campaigns targeting US financial services institutions, cryptocurrencies, credit card companies, and e-commerce without using redirection attacks, a departure from previous tactics. Trickbot, a prominent banking trojan since 2016, has evolved to focus on dynamic injection attacks, a technique previously unused in such geographically centered campaigns. The threat actor's campaigns are regionally focused, with a new configuration targeting a smaller set of US financial services institutions. The novel use of dynamic injection requires precision and insight into target page infrastructure, indicating a sophisticated and costly attack method. The Trickbot threat remains active and engaged, posing a significant risk to financial services institutions and their users. The report provides recommendations for security controls to mitigate these malware attacks. The operation time window for the analysis spans from June to September 2019.





Report 84

Summary: The threat actor "Wizard Spider, Gold Blackburn" targeted the City of Tulsa, Oklahoma, in early May 2021 with a ransomware attack attributed to the Conti Ransomware gang. The attack led to the exposure of personal data, including police citations, containing personally identifiable information such as name, date of birth, address, and driver's license number. The leaked data was shared via the dark web, prompting the City of Tulsa to issue a warning to affected individuals to be vigilant against potential identity theft. The threat actor's capability was demonstrated through the publication of 18,938 files, disrupting the City's network and online services. The novelty of the tools and techniques used by the threat actor included data exfiltration and data leak tactics. The incident highlights the ongoing threat posed by ransomware gangs and the importance of monitoring personal information for fraudulent activity.





Report 85

Summary: UHS hospitals, a Fortune 500 hospital and healthcare services provider, were targeted by a reported country-wide Ryuk ransomware attack affecting facilities in the US. The attack occurred during the early morning, leading to the shutdown of systems and impacting hospitals in California, Florida, Texas, Arizona, and Washington D.C. Evidence suggests that the attack was carried out by the threat actor "Wizard Spider, Gold Blackburn" using Ryuk ransomware, with files being renamed with the .ryk extension. The attack likely started with a phishing campaign and involved the Emotet and TrickBot Trojans before deploying Ryuk ransomware. The threat actor's capability is demonstrated by the use of novel techniques such as phishing, malware deployment, and ransomware attacks. The attack highlights the vulnerability of healthcare organizations to cyber threats and the potential risks to patient and employee data. Date: September 28, 2020.





Report 86

Summary:
The threat actor "Wizard Spider, Gold Blackburn" targeted a maritime facility in the United States, as disclosed by the US Coast Guard. The victims were in the maritime sector. The attack involved the Ryuk ransomware, indicating the capability of the threat actor to deploy sophisticated malware. The incident was reported in 2024. The use of Ryuk ransomware suggests a high level of expertise and potentially significant financial motivation. The tools and techniques used by the threat actor are not specified in the report.





Report 87

Summary:
- Threat Actor: Wizard Spider, Gold Blackburn
- Region: United States (Alabama) and Australia (Gippsland and south-west Victoria)
- Operating Sector: Healthcare
- Date: Incident first reported on 1 October 2019
- Evidence of Capability: Three US hospitals in Alabama and seven hospitals in Australia were targeted with ransomware, forcing closures and disruptions to patient services.
- Novelty of Tools and Techniques: The ransomware attacks were well-organized, causing disruptions to critical services and patient records.
- Impact: Hospitals had to divert new admissions, cancel elective surgeries, and revert to manual systems for patient management.
- Recommendations: Cyber-security experts advised organizations to review security procedures, ensure backups are in place and regularly tested to restore data in case of ransomware infections.





Report 88

Summary: The threat actor known as "Wizard Spider, Gold Blackburn" targeted the University of Utah, leading to a ransom payment of $457,000. The attack was reported by ZDNET in 2024. The victims were in the education sector, specifically a university. The threat actor demonstrated capability in deploying ransomware attacks, indicating a high level of sophistication. The tools and techniques used by the threat actor were novel and effective, resulting in a successful extortion of funds from the university.





Report 89

Summary:
Between mid-April and mid-June 2022, the Russia-based cybercriminal syndicate "Trickbot group," also known as Wizard Spider, DEV-0193, and the Conti group, conducted at least six campaigns against Ukraine, deploying IcedID, CobaltStrike, AnchorMail, and Meterpreter. This marked an unprecedented shift as the group had not previously targeted Ukraine. The campaigns were financially motivated and aimed at Ukrainian state authorities, individuals, and organizations, potentially leading to data theft or ransomware attacks. The threat actor, ITG23, used new malware and tools during these attacks, including a malicious Excel downloader, a self-extracting archive (SFX), and a malware crypter named "Forest." The use of novel tools and techniques, along with the targeting of Ukraine, signifies a significant capability and shift in operations for the threat actor. The campaigns highlight a trend of aligning targets with Russian state interests amidst the ongoing conflict. The report provides details on the campaigns, IOCs, and recommendations for mitigating risks associated with these attacks. The information was sourced from IBM X-Force research and published on July 7, 2022, by Ole Villadsen, Charlotte Hammond, and Kat Metrick.





Report 90

Summary:
- Threat actor: WIZARD SPIDER, also known as GRIM SPIDER, operating Ryuk ransomware targeting large organizations since August 2018.
- Region: Russia-based criminal group.
- Operating sector: Targeting enterprise environments.
- Novelty of tools and techniques: Ryuk derived from Hermes source code, only used by WIZARD SPIDER, netted over 705.80 BTC across 52 transactions.
- Evidence of capability: Shift in operations to "big game hunting," sophisticated tactics, and high ransom returns.
- Operation time window: Since August 2018.
- Tools and techniques: Initial compromise through TrickBot, distributed via spam email or Emotet.
- Development: Ryuk constantly evolving, with new features added.
- Prevention: Falcon platform can detect and prevent Ryuk by leveraging behavioral patterns.
- Attribution: Medium-high confidence that WIZARD SPIDER operates from Russia.
- Date: January 10, 2019.
- Source: CrowdStrike report.





Report 91

Summary: Nordex, a wind turbine firm, was targeted by the Conti ransomware operation, leading to the shutdown of IT systems and remote access to managed turbines. The attack was detected early in April 2022, with Nordex taking precautionary measures to contain it. The Conti ransomware gang claimed responsibility for the attack but did not leak any data, suggesting negotiations or lack of data theft. Conti is known for double-extortion attacks and has been linked to other malware infections like Ryuk and TrickBot. The attack on Nordex highlights the threat actor's capability to target critical infrastructure companies in the energy sector using sophisticated techniques. The incident underscores the ongoing risk posed by ransomware attacks to companies in the renewable energy industry.





Report 92

Summary:
The threat actor known as Wizard Spider, also operating under the alias Gold Blackburn, is associated with the TrickBot banking malware and is reportedly based in Russia. The group targets various sectors including Defense, Financial, Government, Healthcare, and Telecommunications worldwide. They have been observed using a wide range of tools and techniques such as TrickBot, BokBot, and Ryuk ransomware. The group has been involved in numerous hacking operations targeting organizations globally, with a focus on financial crime and financial gain. Counter operations against the threat actor have been conducted by various entities, including disrupting botnets and arresting members. The threat actor's activities have been ongoing since at least 2014, with reported incidents up to the present day.





Report 93

Summary:
- Threat actor: Wizard Spider, Gold Blackburn
- Region: Russia-based
- Operating sector: eCrime group targeting enterprise environments
- Date: October 16, 2020
- Evidence of capability: Wizard Spider has evolved from TrickBot to Ryuk, Conti, and BazarLoader, demonstrating resilience and dedication to criminal operations. They have developed new tools and modified existing ones, with TrickBot infecting over one million systems worldwide. Wizard Spider has shown the ability to react to disruption attempts swiftly and efficiently.
- Novelty of tools and techniques: BazarLoader is being used as an initial access tool, with spam emails containing links to Google Docs files hosting the payload. The loader component of BazarLoader uses string and code obfuscation, mimicking legitimate software for persistence. Ryuk ransomware has introduced code obfuscation techniques to slow down reverse engineering. Conti ransomware has evolved with compiler-based obfuscation techniques to evade detection and disrupt malware analysis systems.
- Conclusion: Wizard Spider remains a highly capable adversary with a diverse and effective toolset, continuing to run criminal operations despite disruption attempts. The group's resilience and adaptability highlight the importance of ongoing efforts to combat cyber threats.


