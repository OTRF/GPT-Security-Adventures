
Report 1

Summary:
The threat actor known as ALPHV, also operating under the alias BlackCat Gang, is a ransomware family that emerged in mid-November 2021, utilizing a ransomware-as-a-service (RaaS) business model. The threat actor gained notoriety for its sophistication and innovation, offering affiliates the opportunity to leverage the ransomware in exchange for a percentage of the ransom payment. The BlackCat gang employs various tactics common in the ransomware space, including data exfiltration, threats to release data, and DDoS attacks. The threat actor has targeted victims worldwide across various sectors, including IT services providers, fashion giants, oil companies, universities, natural gas suppliers, betting platforms, healthcare providers, and government agencies. The threat actor has been linked to attacks on organizations in multiple countries, including Germany, Switzerland, Austria, Italy, the US, India, Japan, and Bangladesh. The threat actor has been observed using a range of tools and techniques, such as BlackCat ransomware, GO Simple Tunnel, Impacket, LaZagne, Mimikatz, PsExec, and WebBrowserPassView. The threat actor has also been involved in data breaches, extortion, and leaking stolen data to pressure victims into paying ransom demands. The ALPHV gang has been active in the cybercrime landscape, with reported attacks on a wide range of high-profile targets, including healthcare providers, financial institutions, government agencies, and critical infrastructure. The threat actor has demonstrated a capability to adapt and evolve its tactics, as seen in the use of new tools and techniques to carry out attacks. The threat actor has been the subject of counter operations by law enforcement agencies, with efforts made to disrupt their activities and hold them accountable for their criminal actions.





Report 2

ALPHV Ransomware Affiliate, tracked as UNC4466, targeted vulnerable Veritas Backup Exec installations exposed to the internet, exploiting CVE-2021-27876, CVE-2021-27877, and CVE-2021-27878 vulnerabilities. The threat actor shifted from credential theft to opportunistic targeting of known vulnerabilities. ALPHV emerged in November 2021 as a ransomware-as-a-service, successor to BLACKMATTER and DARKSIDE, targeting critical infrastructure and health entities. In March 2021, Veritas reported critical vulnerabilities in Backup Exec. A METASPLOIT module exploiting these vulnerabilities was released in September 2022, with Mandiant observing exploitation in October 2022.

UNC4466 gained access to a Windows server running Veritas Backup Exec using Metasploit, conducted internal reconnaissance using tools like Advanced IP Scanner and ADRecon, and transferred tools like LAZAGNE and ALPHV ransomware using BITS. The threat actor used SOCKS5 tunneling for command and control, credential access tools like Mimikatz, and evasion techniques like disabling Microsoft Defender. UNC4466 deployed the ALPHV ransomware in late 2022, targeting over 8,500 exposed IP addresses advertising Veritas Backup Exec services.

Defenders are advised to monitor Veritas Backup Exec installations, forward log files to SIEM for detection, and look for suspicious activities like BITS transfers, registry modifications, and file creations in staging directories. UNC4466's techniques align with MITRE ATT&CK framework categories like Data Encrypted for Impact, Defense Evasion, and Command and Control. Mandiant recommends implementing secure access controls, network segmentation, multi-factor authentication, and backup strategies to mitigate ransomware impact. The report provides indicators of compromise and detection opportunities for organizations to enhance their cybersecurity posture.





Report 3

ALPHV gang, also known as BlackCat, claimed responsibility for a ransomware attack on Constellation Software, a Canadian diversified software company. The attack targeted internal financial reporting systems and data storage, impacting a limited amount of personal information and business data. Constellation Software operates through six groups and has over 25,000 employees worldwide. The ALPHV gang threatened to leak over 1 TB of stolen data if ransom demands were not met. The gang has been active since November 2021 and is considered a significant ransomware threat to enterprises globally. The FBI warned about their extensive experience in ransomware operations. The tools and techniques used by the ALPHV gang are believed to be a rebrand of the DarkSide/BlackMatter gang, with a history of targeting high-profile entities. The attack on Constellation Software showcases the ongoing threat posed by ransomware groups like ALPHV. (End of Summary)





Report 4

ALPHV ransomware, also known as BlackCat Gang, has implemented a new extortion strategy by adding a data leak API to increase pressure on victims to pay ransom. The gang recently breached Estée Lauder, a beauty company, which refused to engage in negotiations for ransom payment. The API allows for timely updates about new victims on the leak site and has been partially available for months. The gang provided API calls and a Python crawler to retrieve information from the leak site. The release of the API may be due to a decrease in paying victims, as reported by Coveware, with only 34% of victims paying in the second quarter of the year. Ransomware gangs like Clop continue to target supply chains to make significant profits. ALPHV/BlackCat also compromised Estée Lauder, which refused to pay for the stolen files, leading to a mocking response from the gang. With fewer paying victims, ransomware gangs are exploring new methods to pressure victims for payment, such as making leaks easily accessible to a larger audience. The use of the data leak API is a novel approach in the ransomware landscape and reflects the evolving tactics of threat actors. The report was published on July 26, 2023.





Report 5

Summary: The ALPHV (BlackCat) ransomware gang claimed an attack on the Florida circuit court, affecting state courts across Northwest Florida. The attack involved the acquisition of personal details such as Social Security numbers and CVs of employees, including judges. ALPHV claimed to have a comprehensive network map of the court's systems and local and remote service credentials. The presence of a data leak page on ALPHV's website suggested that negotiations with the ransomware operation had not taken place or had been firmly declined by the court. The attack disrupted court operations in Escambia, Okaloosa, Santa Rosa, and Walton counties for an extended period. The ALPHV ransomware operation, believed to be a rebranding of DarkSide/BlackMatter, is known for targeting global enterprises and continuously adapting tactics. An affiliate of ALPHV claimed responsibility for an attack on MGM Resorts, resulting in losses of approximately $100 million and theft of customer information. The FBI issued a warning about the group's involvement in successful breaches of over 60 entities worldwide between November 2021 and March 2022. The report was published on October 9, 2023.





Report 6

Summary:
The AlphV group, also known as BlackCat Gang, claimed responsibility for a ransomware attack on Forsyth County, Georgia in June 2023. The attack targeted a large county near Atlanta, threatening to expose 350GB of stolen data. County officials confirmed the attack and stated that Social Security numbers and driver's license numbers were accessed. The group claimed to have a variety of sensitive information including financial reports, insurance details, and business agreements. The county is working with law enforcement, cybersecurity firms, and data forensics consultants to respond to the incident. This attack is part of a trend of ransomware incidents targeting local governments across the United States, with at least 31 incidents involving data theft. The AlphV group's use of ransomware and data theft tactics demonstrates their advanced capabilities in cybercrime. The attack on Forsyth County is a significant example of the group's activities in the region.





Report 7

Malformed report





Report 8

The Alphv group, also known as the BlackCat Gang, claimed responsibility for hacking Clarion, a global manufacturer of audio and video equipment for cars. Clarion Japan, the Japanese subsidiary of Clarion Co., Ltd., was targeted by the ransomware group, which threatened to leak sensitive data, including engineering information and partner documents. The group announced the hack on September 23, 2023, and threatened to sell the stolen data to interested parties by September 25, 2023. Clarion's car navigation systems are widely used in Japan and by various automakers globally. The Alphv group has a history of targeting organizations in various sectors, including industrial explosives, defense contractors, and fashion giants, with ransom demands ranging from tens of thousands to tens of millions of dollars. The group has been active since November 2021 and has a track record of successful cyberattacks. The ransomware attack on Clarion could have significant implications for the automotive industry and other players in the sector.





Report 9

Summary:
The threat actor known as ALPHV, also referred to as BlackCat, listed Amazon-owned Ring on their darknet site, threatening to leak data. Ring denied experiencing a ransomware attack. The group has a history of compromising customer cameras through credential theft. The company has updated its security practices. The FBI issued a Flash report linking ALPHV to Darkside/Blackmatter, indicating extensive networks and experience in ransomware operations. ALPHV previously listed data stolen from Munster Technological University. The company spokesperson stated there were no indications of a ransomware incident. GDPR requires companies to confirm breaches within 72 hours to avoid fines. The threat actor's capabilities include data theft and extortion. The tools and techniques used by ALPHV are novel and sophisticated. The operation time window for the threat actor's activities is ongoing.





Report 10

ALPHV, also known as BlackCat, is a ransomware group that has gained attention for its sophisticated ransomware coded in the Rust programming language. The group has publicly posted details about roughly two dozen victims on its extortion site over the last two months. German cybersecurity officials suspect ALPHV of being responsible for an attack on two German logistics companies, leading to oil supply disruptions across gas stations. The group claims to have ties to REvil, DarkSide, and other ransomware groups, but states they are not a rebrand or mix of talents. ALPHV believes they have no competitors in the market due to their high-quality software and range of services related to ransom. They work only with Russian-speaking partners and do not plan to expand geographically. ALPHV uses the Rust programming language for its ransomware, aiming to create a new product that meets modern requirements. They have unique features like access tokens and unique domains for every victim to prevent decryption by other entities. The group works with recovery companies to simplify the process, offering discounts and quick recovery times. ALPHV does not target government, healthcare, or educational institutions, except for pharmaceutical companies and private clinics. They offer special features like calls, DDoS attacks, brute force capabilities, and a distributed onion storage for negotiation processes. ALPHV aims to create a RaaS meta-universe that includes a full range of services related to their business. The group remains apolitical and controls affiliates preventively at registration. They have a spiritual and technical leader known as the "super admin." ALPHV dismisses investigations linking them to developers and states they are beyond what analysts can imagine. The group hints at future changes in the ransomware scene and encourages following their updates for more information. The report was published on February 4th, 2022.





Report 11

Malformed report.





Report 12

Summary: The threat actor known as ALPHV, also referred to as BlackCat Gang, targeted an Australian law firm in an April ransomware attack that impacted 65 Australian government agencies. The attack was attributed to the Russian-speaking Alphv hacking group, which published stolen data from the law firm. The attack affected a large number of private sector clients of the law firm as well. The national cybersecurity coordinator, Air Marshal Darren Goldie, revealed that data from multiple Australian government entities was compromised in the attack. Notably, the Australian federal police and the Department of Home Affairs were among the victims of the hack. Alphv is known for targeting high-profile organizations with sensitive data and had previously been flagged by the Australian Cyber Security Center in 2022. The law firm, HWL Ebsworth, received an extortion demand of AU$4.6 million from Alphv. The incident was reported to the Office of the Australian Information Commissioner on May 8. The attack highlights the threat actor's capability to target government agencies and high-profile organizations, using ransomware as a tool for extortion. The use of novel techniques and tools by the threat actor underscores the evolving nature of cyber threats faced by organizations. The incident serves as a reminder of the importance of robust cybersecurity measures to protect sensitive data and prevent ransomware attacks.





Report 13

Bandai Namco, a Japanese game publishing company, confirmed a cyberattack by the ALPHV ransomware group on July 3, 2022. The attack targeted Bandai Namco's offices in Asian regions, excluding Japan, resulting in unauthorized access to internal systems. The hackers claimed to have stolen corporate data during the breach. Bandai Namco is known for popular video games like Elden Ring and Dark Souls. The ransomware group ALPHV, also known as BlackCat, is believed to be a rebrand of the DarkSide/BlackMatter gang. ALPHV has targeted various enterprises globally, including the Moncler fashion group and Swissport airline cargo handling services. The group has evolved its extortion tactics by launching a searchable database of stolen data, increasing the threat to victims. The FBI warned that ALPHV had breached at least 60 entities worldwide, showcasing their extensive network and experience in ransomware operations. Bandai Namco has not provided technical details of the attack, but the confirmation and entry on the ransomware group's data leak site suggest a ransomware incident. The company is investigating the extent of the damage and potential leakage of customer information. ALPHV's capability and use of novel tools and techniques make them a significant threat to enterprises in various sectors.





Report 14

Summary:
On July 19th, 2023, the U.S. cosmetics manufacturer Estée Lauder was targeted in a ransomware attack by the threat actors BlackCat and Clop. The hackers gained unauthorized access to the company's systems and stole data, causing disruptions to its business operations. Estée Lauder, known for brands like Clinique and MAC, shut down some systems and launched an investigation with law enforcement and cybersecurity experts. BlackCat claimed to have stolen over 130 gigabytes of data without encrypting the network, while Clop may have exploited vulnerabilities in the MOVEit file transfer software. This incident occurred amidst a forecasted drop in sales and profits for Estée Lauder due to slow recovery from the COVID-19 pandemic in duty-free and travel destinations. The company's products are sold in approximately 150 countries, making it one of the world's largest cosmetics manufacturers. The threat actors' capability and novel techniques include data theft without encryption and exploiting software vulnerabilities. The attack highlights the ongoing cyber threats faced by companies in the manufacturing sector.





Report 15

Summary:
The threat actor known as BlackCat (ALPHV) ransomware has been observed leveling up for stealth, speed, and exfiltration, targeting organizations globally in sectors such as healthcare, government, education, manufacturing, and hospitality. The group has been active since November 2021 and has shown continuous evolution in their tactics and tools. BlackCat affiliates have automated data exfiltration using a custom malware called ExMatter and released a new version of their ransomware named Sphynx with upgraded capabilities to evade defensive measures. The group has demonstrated a nuanced understanding of Active Directory and Group Policy Objects to deploy tools and interfere with security measures swiftly. BlackCat has been linked to attempted extortion in various sectors globally and has shown no signs of slowing down. The threat actor has been observed using PowerShell, RDP, and modifying default domain GPOs to disable security controls and deploy ransomware tools. The group exfiltrates data using ExMatter before executing ransomware, impacting both Windows and Linux systems. BlackCat's toolkit contains functionalities beyond ransomware, acting as a "toolkit" based on tools from Impacket. The threat actor is likely to continue enhancing their operations using novel means to increase speed and stealth. Recommendations include monitoring GPO administration and controlling software execution to prevent malicious tools from running. The report was last updated on June 13, 2023, to correct an analysis of ExMatter's persistence behavior.





Report 16

Summary:
The threat actor known as BlackCat (ALPHV) claimed responsibility for a ransomware attack on Swissport, a €3 billion revenue firm with a global presence in 50 countries providing cargo handling and other services. The attack caused flight delays and service disruptions. BlackCat leaked a small set of data obtained from the attack, including passports, internal memos, and job candidate details. The threat actor offered to sell the entire 1.6 TB data dump. Swissport, with 66,000 employees worldwide, handles millions of passengers and tons of cargo annually. BlackCat emerged after the shutdown of BlackMatter and is linked to the BlackMatter/DarkSide operation. The ransom demands range from $400,000 to $3 million payable in Bitcoin or Monero, with an additional 15% fee for Bitcoin payments. The threat actors threaten DDoS attacks until the ransom is paid. The operation is considered highly sophisticated, targeting victims globally since November 2021. The threat actor uses novel techniques and tools, posing a significant risk to organizations in various sectors. The report was published on February 15, 2022.





Report 17

Summary: The BlackCat/ALPHV ransomware gang targeted the Austrian federal state of Carinthia, demanding $5 million to unlock encrypted computer systems, causing severe operational disruption. The attack affected government services, including passport issuance and COVID-19 testing. The threat actor offered a decryption tool for the ransom, but the state refused to pay. There is no evidence of data theft, and the state plans to restore systems from backups. The ALPHV/BlackCat gang emerged in November 2021 as a sophisticated ransomware operation, targeting high-profile entities like Moncler and Swissport. The FBI warned of at least 60 breaches by BlackCat, making it one of the most active ransomware projects. The attack on Carinthia indicates a focus on organizations capable of paying large ransoms to avoid financial losses. The threat actor's tools and techniques are considered novel and dangerous, with a history of targeting high-value victims. The report was published on May 27, 2022, detailing the recent attack on Carinthia by the BlackCat/ALPHV ransomware gang.





Report 18

Summary: The threat actor known as BlackCat, also referred to as ALPHV, targeted an Indian missile fuel maker, Solar Industries, adding them to their list of victims. The attack involved the theft of sensitive data, including specifications for propellant used in Indian military missile and rocket systems, warhead data, and personal information of employees and customers. The ransomware group, suspected to be linked to former REvil members, claimed to have over 2 terabytes of data for sale. The attack led to the shutdown of Solar Industries' website and attracted the attention of Indian authorities, with the Central Bureau of Investigation poised to investigate. The stolen data also included security camera footage, audits, reports of flaws in products, and information about supply chain vendors. Solar Industries, a publicly traded company with a significant market share in India, faced a sophisticated malware program from BlackCat capable of infecting various operating systems and employing encryption routines and cryptographic algorithms. The attack is considered a cyber terrorist attack due to the sensitive nature of the stolen data. The incident highlights the importance of appropriate security measures for companies, as per Indian law. The attack demonstrates the threat actor's capability and the novelty of their tools and techniques, posing a significant risk to organizations in the region.





Report 19

Summary:
The threat actor known as BlackCat, also referred to as ALPHV, targeted the University of Pisa in Europe, demanding a $4.5 million ransom. The attack occurred on June 14, 2022. BlackCat has been focusing on the education sector in Europe and beyond, with evidence of attacks on academic institutions in France, North America, and Asia. The group is known for using Rust programming language for its ransomware products, offering affiliates a 90% share of victims' payouts. BlackCat has been recruiting operators actively. The group leverages unpatched Microsoft Exchange server vulnerabilities as an attack vector, with a focus on remote desktop applications and compromised credentials for network access. The ransomware family is known for its cross-platform capabilities, operating on Windows, Linux, and VMWare instances. The attack on the University of Pisa is part of a series of attacks on educational institutions globally, showcasing the threat actor's capability and reach. The group's use of novel tools and techniques, along with its recruitment strategies, indicate a sophisticated and evolving threat landscape.





Report 20

Summary:
The threat actor known as BlackCat, associated with ALPHV, has recently introduced a new utility called Munchkin to propagate their ransomware payload to remote machines and shares on victim organization networks. The BlackCat ransomware operators have been evolving their tooling over the past two years as part of their ransomware-as-a-service (RaaS) business model. Unit 42 researchers acquired a unique instance of Munchkin loaded in a customized Alpine virtual machine (VM), showcasing a novel tactic of using VMs to deploy malware and bypass security solutions. BlackCat historically targeted victims in the United States but has expanded globally across various industries. The BlackCat tool set has evolved, with recent updates including obfuscation mechanisms and the release of Munchkin, a Linux-based utility to run BlackCat on remote machines or encrypt SMB/CIFS shares. The use of VMs to run malware is a growing trend among ransomware actors to evade security controls. The Munchkin utility is delivered as an ISO file and executes commands to change the root password, run the malware binary, and power off the VM. The controller malware within the VM decrypts strings, parses configuration files, and creates customized BlackCat samples for encryption. The malware iterates through configurations to infect specified SMB/CIFS drives. Palo Alto Networks customers are protected from these threats through their security services. Indicators of compromise include hashes of Munchkin and BlackCat samples, along with YARA rules for detection. The BlackCat threat continues to evolve, with the introduction of Munchkin showcasing their innovative tactics in deploying ransomware.





Report 21

Malformed report





Report 22

Summary:
The threat actor known as ALPHV, operating under the name BlackCat Gang, has targeted the Beverly Hills Plastic Surgery clinic, stealing sensitive medical records and threatening to leak patients' photos if a ransom is not paid. The gang has been active in extorting various organizations, including Reddit data, Australian federal agencies, and banks. They have also targeted healthcare providers like Lehigh Valley Health Network, stealing patient images and health records. The threat actor's capability is evidenced by their ability to breach and exfiltrate data from critical infrastructure sectors like healthcare. The novelty of their techniques lies in the personal nature of their threats, such as leaking cosmetic surgery photos, which has been seen before but is still impactful. The report does not specify a specific date or operation time window for these incidents.





Report 23

Summary:
- Threat actor: ALPHV, BlackCat Gang
- Date: August 1, 2022
- Target: Creos Luxembourg S.A., a natural gas pipeline and electricity network operator in Europe
- Owner: Encevo, an energy supplier in five EU countries
- Attack: Cyberattack resulted in customer portals becoming unavailable, data exfiltration
- Tools: BlackCat ransomware used to threaten publication of stolen data
- Tactics: Extortion platform used to pressure victims to pay ransom
- Novelty: Threat actor continues to target high-profile companies despite law enforcement pressure
- Recent targets: Austrian states, Italian fashion chains, Swiss airport service provider, German petrol supply firm, and now Creos Luxembourg.





Report 24

Summary:
- Threat actor: BlackCat/ALPHV ransomware gang
- Date: September 2, 2022
- Target: Italian energy agency Gestore dei Servizi Energetici SpA (GSE)
- GSE is a publicly-owned company promoting renewable energy sources in Italy
- Attack involved data theft of 700GB of files containing confidential information
- Previous attacks by the same threat actor targeted Eni SpA, Creos Luxembourg S.A., and Oiltanking
- BlackCat/ALPHV ransomware operation believed to be a rebrand of DarkSide/BlackMatter gang
- Notable for attacking Colonial Pipeline and other enterprises worldwide
- Known for evolving extortion tactics, including double-extortion attacks and searchable database of stolen data
- FBI warned of extensive networks and experience with ransomware operations
- Novelty in tools and techniques includes double-extortion tactics and searchable database of stolen data

Malformed report.





Report 25

Summary: The BlackCat ransomware gang, also known as ALPHV, claimed to have breached the network of healthcare giant Henry Schein, stealing 35 TB of data including payroll and shareholder information. Henry Schein, a Fortune 500 company with operations in 32 countries, disclosed the cyberattack on October 15, 2023, leading to temporary disruptions in its manufacturing and distribution businesses. The company took systems offline to contain the incident and notified law enforcement authorities. BlackCat/ALPHV ransomware group added Henry Schein to its dark web leak site, threatening to release more data daily. The gang encrypted the company's devices again after failed negotiations. The BlackCat ransomware operation emerged in November 2021 and is believed to be a rebrand of the DarkSide/BlackMatter group. The FBI linked the group to attacks on over 60 organizations worldwide between November 2021 and March 2022. The threat actor's capability is evidenced by the successful breach of a healthcare giant and the theft of sensitive data, showcasing novel tools and techniques in ransomware attacks. The report provides details on the timeline of events, the response of the victim company, and the ongoing negotiations with the threat actor.





Report 26

The report discusses the failed attempt by the threat actor known as ALPHV or BlackCat to extort an Australian commercial law giant, HWL Ebsworth. The law firm's network was hacked, and the threat actor leaked 1.45 terabytes of data containing over a million documents stolen from the company's systems in April 2023. HWL Ebsworth, with an annual revenue of hundreds of millions of dollars and employing over 2,000 people, refused to meet the extortion demands of the cybercriminals. The leaked documents on BlackCat's site are easily accessible, raising concerns about the exposure of sensitive information. The law firm's clients, including the ANZ banking group and various government entities, may be impacted by the incident. The threat actor's indexed database allows visitors to filter search results by filename or file type, making the leaked documents easily exploitable. The report does not mention the specific region targeted by the threat actor, but it highlights the operating sector as the legal industry in Australia. The report does not provide details on the novelty of tools and techniques used by the threat actor. The operation time window is mentioned as April 2023 when the data was stolen from the law firm's systems.





Report 27

Summary:
The threat actor known as BlackCat (ALPHV) ransomware gang targeted Azure Storage using the Sphynx encryptor. They used stolen Microsoft accounts and a new Sphynx variant with custom credentials support to encrypt targets' cloud storage. The attackers gained access to a Sophos Central account using a stolen OTP and encrypted systems and Azure cloud storage, successfully encrypting 39 accounts. They infiltrated the victim's Azure portal using a stolen Azure key encoded with Base64. The threat actor used RMM tools like AnyDesk, Splashtop, and Atera during the intrusion. The Sphynx variant was discovered in March 2023 and was found embedding the Remcom hacking tool and Impacket networking framework for lateral movement. BlackCat/ALPHV is suspected to be a DarkSide/BlackMatter rebrand and has targeted enterprises globally with sophisticated tactics. The gang has been involved in high-profile attacks, including the breach of Colonial Pipeline. They have continuously adapted their tactics, introducing new extortion approaches and a data leak API. Affiliates of the gang, such as Scattered Spider, have claimed attacks on companies like MGM Resorts. The FBI issued a warning about the group's successful breaches of over 60 entities worldwide between November 2021 and March 2022. The report was published on September 16, 2023.





Report 28

Summary:
The threat actor known as "ALPHV, BlackCat Gang" has been implicated in an attack on German oil companies. The attack involved the use of BlackCat ransomware. The victims targeted were companies in the oil sector in Germany. The attack was reported in 2024 by ZDNET. The threat actor demonstrated capability in deploying ransomware against critical infrastructure companies. The tools and techniques used by the threat actor were novel and sophisticated, indicating a high level of expertise. The attack highlights the ongoing threat posed by ransomware groups targeting key industries.





Report 29

Summary:
- Threat actor: ALPHV, BlackCat Gang
- Date: December 16, 2022
- Target: Colombian energy supplier EPM (Empresas Públicas de Medellín)
- Sector: Energy, water, and gas provider
- Evidence: Ransomware attack disrupted operations, encrypted devices, and stole data
- Novelty: BlackCat ransomware operation used ExMatter data-theft tool to steal data before encryption
- Tools: ExMatter tool uploaded data to unsecured remote server, matching EPM computer naming formats
- Impact: Approximately 4,000 employees instructed to work from home, IT infrastructure down
- Previous attacks: Enel Group targeted in 2020, healthcare system disrupted by RansomHouse attack
- Region: Colombia
- Ownership: EPM owned by the Colombian Municipality of Medellin
- Revenue: EPM generated over $25 billion in revenue in 2022
- Response: EPM provided alternative payment methods for customers, investigation ongoing

Malformed report.





Report 30

Summary:
The threat actor known as BlackCat (AlphaV) is a relatively new ransomware group that has targeted over 60 organizations in various sectors such as government, healthcare, and public utilities. The group is associated with other advanced-persistent threat (APT) groups like Conti, DarkSide, Revil, and BlackMatter. BlackCat is known for exploiting vulnerabilities in Windows operating systems, Exchange servers, and Secure Mobile Access products. The group has the capability to exploit critical vulnerabilities such as CVE-2021-34473 and CVE-2021-34523 found in Microsoft Exchange Server. BlackCat uses stolen access credentials to gain initial access to networks and then proceeds to map the entire network, manipulate accounts, disable security systems, and execute ransomware attacks. The group stands out for its use of the Rust programming language to develop highly tailored executables for targeted attacks. BlackCat also engages in ransomware-as-a-service and is known for its speedy data encryption and public leak site for stolen information. Organizations can defend against BlackCat attacks by patching known vulnerabilities, deploying multifactor authentication, conducting regular attack surface management scans, performing penetration tests, and maintaining separate backup data. The FBI has issued an advisory warning about the potential danger posed by BlackCat. Organizations must monitor their networks consistently and patch vulnerabilities to prevent ransomware attacks. The report was published on September 8, 2022, and provides insights into the tactics and characteristics of the BlackCat threat actor.





Report 31

Summary: The FBI reported that the ALPHV/BlackCat ransomware gang has made over $300 million in ransom payments from more than 1,000 victims worldwide as of September 2023. The threat actor has compromised over 1,000 entities, with nearly 75% in the United States and approximately 250 outside the United States. The FBI provided mitigation measures and indicators of compromise to help organizations defend against ALPHV attacks. The threat actor is suspected to be a rebrand of the DarkSide and BlackMatter ransomware operations. The FBI disrupted the ALPHV operation, obtained decryption keys, and helped over 500 victims recover their files for free. The FBI seized the domain for the ransomware operation's data leak site. The ALPHV gang claimed to have breached at least 3,400 victims. The threat actor's tools and techniques are considered novel, and the FBI's actions have been seen as a significant disruption in the cybercrime landscape. Date: December 19, 2023.





Report 32

Summary:
- Threat actor: ALPHV, BlackCat Gang
- Target: Fashion giant Moncler
- Date: December 2021
- Region: Italy
- Operating sector: Luxury fashion
- Evidence of capability: Stolen data published on dark web, ransom demand of $3 million
- Novelty of tools and techniques: ALPHV categorized as sophisticated RaaS, robust operational structure
- Data leaked: Employees, former employees, suppliers, consultants, business partners, customers
- No credit card data stolen
- ALPHV gang attempting to sell data of "rich customers"
- Moncler rejected ransom demand, informed stakeholders and Italian Data Protection Authority

Malformed report.





Report 33

Summary: On December 19, 2021, French IT services company Inetum Group was targeted by a ransomware attack using the BlackCat ransomware, also known as ALPHV and Noberus. Inetum operates in over 26 countries, providing digital services to companies in sectors such as aerospace, defense, banking, automotive, energy, healthcare, insurance, retail, public sector, transportation, telecom, and media. The attack had a limited impact on Inetum's operations in France and did not affect its main infrastructures or client operations. The ransomware strain used in the attack was written in Rust, a unique feature for ransomware operations, and had advanced capabilities such as spreading to other computers, terminating virtual machines, and wiping them. Inetum Group quickly responded to the attack by isolating affected servers and terminating client VPN connections. The company notified authorities and engaged with specialized cybercrime units for incident response. Delivery operations to customers remained safe, and messaging and collaboration systems were unaffected. The attack did not exploit the recent critical Log4j vulnerability. The threat actor behind the attack demonstrated advanced capabilities and used novel techniques, making them a significant concern for organizations in the IT services sector.





Report 34

Summary:
- Threat actor: ALPHV, BlackCat Gang
- Date: December 5, 2023
- Target: HTC Global Services, a managed service provider offering technology and business services to healthcare, automotive, manufacturing, and financial industries.
- Evidence of capability: ALPHV ransomware gang leaked screenshots of stolen data, including passports, contact lists, emails, and confidential documents.
- Novelty of tools and techniques: ALPHV believed to have exploited the Citrix Bleed vulnerability to breach HTC's network.
- Operating sector of victims: Global enterprises, critical infrastructure like publicly owned electricity provider and hospital network in the United States.
- Recent attacks: ALPHV affiliate claimed data theft from Tipalti and extortion of impacted companies individually.
- Evolution of threat actor: ALPHV is a rebrand of DarkSide and BlackMatter ransomware operations, known for targeting global enterprises and continuously adapting tactics.
- Recent surge in attacks by ALPHV, including collaboration with English-speaking threat actors for extortion attacks.





Report 35

Summary:
- Date: March 29th, 2023
- Region: India
- Threat Actor: Black Cat/AlphV ransomware group
- Victims: Sun Pharmaceuticals, the fourth-largest specialty generic pharmaceutical company in the world
- Type of Company: Pharmaceutical
- Evidence of Capability: Theft of company data and personal information, impact on IT systems, breach of file systems, theft of data, revenue loss, hiring of cybersecurity firm for response
- Novelty of Tools and Techniques: Use of ransomware, targeting of healthcare and pharmaceutical companies, evolution from money theft to ransomware-as-a-service operation
- Operation Time Window: Ongoing containment and eradication efforts
- Other Targets: Healthcare network in Pennsylvania, hospital technology giant NextGen Healthcare, colleges and universities in the U.S., Japanese video game giant Bandai Namco, toy production company Jakks Pacific, German oil companies, Italian fashion brand Moncler.





Report 36

Summary:
The threat actor known as BlackCat ransomware gang targeted the Japanese watchmaker Seiko, breaching their IT infrastructure and accessing or exfiltrating data. Seiko, a large watchmaker with over 12,000 employees and annual revenue exceeding $1.6 billion, disclosed the breach on August 10, 2023. BlackCat claimed responsibility for the attack and posted samples of stolen data on their extortion site, including production plans, employee passport scans, and technical schematics. The threat actor demonstrated advanced capabilities by leaking confidential information and using novel tactics such as creating a data leak API for easier distribution of stolen data. Researchers also identified an initial access broker selling access to a Japanese manufacturing company, matching Seiko's profile, one day before the breach. The incident highlights the evolving tactics of ransomware gangs targeting high-profile companies in the manufacturing sector.





Report 37

Summary:
On September 29th, 2023, a large healthcare provider in Michigan, McLaren HealthCare, confirmed a ransomware attack by the Black Cat/AlphV gang. The attack affected 13 hospitals, infusion centers, cancer centers, and other medical services operated by McLaren. The gang claimed to have stolen 6 TB of data, including personal information and videos of hospital work. McLaren had to shut down its computer network at 14 facilities, causing outages in billing and electronic health record systems. The company has engaged global cybersecurity specialists and law enforcement to investigate the incident. The attack is part of a trend where healthcare institutions are targeted by ransomware actors, with previous attacks on hospitals in four states and a major U.S. healthcare network. The Black Cat/AlphV gang has a history of targeting healthcare institutions and was also responsible for an attack on MGM Resorts in Las Vegas. The incident highlights the increasing sophistication of cybercriminals and the ongoing challenge of protecting systems against such attacks.





Report 38

Summary:
On June 2nd, 2023, a legal services platform called Casepoint, used by the SEC, Pentagon, and other U.S. government agencies, is investigating claims by the BlackCat/AlphV ransomware group that they have been attacked. The ransomware group shared sensitive documents allegedly related to the FBI and claimed to have access to Casepoint's network. Casepoint's vice president initially denied any breach but later activated incident response protocols and hired a forensic firm to investigate. The company stated that its services have not been disrupted, and clients can continue using the platform. The ransomware group claimed to have 2 terabytes of data from Casepoint, but the legitimacy of the leaked documents is unclear. Experts believe the BlackCat/AlphV group may be associated with the Darkside ransomware group, known for the Colonial Pipeline cyberattack. The threat actor's capability to target a legal services platform used by government agencies and major companies like Marriott demonstrates their sophistication. The use of ransomware and leaking sensitive documents shows the novelty of their tools and techniques. The threat actor's targeting of high-profile organizations in the legal and government sectors poses a significant risk to national security.





Report 39

Summary:
In May 2022, an automotive supplier was targeted in a triple ransomware attack by threat actors identified as Lockbit, Hive, and an ALPHV/BlackCat affiliate. The attacks exploited a misconfiguration involving Remote Desktop Protocol (RDP) on a management server. Lockbit exfiltrated data to Mega cloud storage, used Mimikatz for password extraction, and distributed ransomware using PsExec. Hive used RDP for lateral movement and dropped ransomware shortly after Lockbit. The ALPHV/BlackCat affiliate established persistence with Atera Agent, exfiltrated data, and distributed ransomware two weeks after Lockbit and Hive attacks. The threat actors used novel techniques such as multiple encryption of files and log wiping. The BlackCat ransomware binaries had unique functionalities like UUID collection and symbolic link evaluations. The investigation was complicated by system restoration, log wiping, and lack of DHCP logging. Sophos' Rapid Response team found evidence of files encrypted by all three ransomware groups. Proactive defense measures include patching, securing accessible services, segmentation, strong passwords, and layered protection. IOCs related to the attacks were posted on Sophos' Github repository. The report was published on August 10, 2022, by Sophos News.





Report 40

Summary:
- Date: June 3rd, 2022
- Location: Alexandria, Louisiana
- Target: City of Alexandria, a 50,000-person city
- Threat Actor: AlphV ransomware gang, also known as BlackCat
- Evidence of Capability: AlphV has attacked at least three U.S. colleges and universities this year, including Florida International University and North Carolina A&T University. The FBI has tracked at least 60 ransomware attacks by the AlphV group as of March.
- Novelty of Tools and Techniques: AlphV has aggressively posted details about its victims publicly and has threatened media outlets like KALB for reporting on their activities.
- Operation Time Window: Ongoing investigation with more information expected to be available over the weekend.
- Previous Attacks: AlphV has targeted state agencies in Louisiana in 2019 and has a history of attacking local governments in the U.S.
- Response: Louisiana state officials have deployed cybersecurity resources to assist with the response and investigation of the attack.
- Impact: The ransomware attack has affected the city's operations, with data leakage threats and network disruptions reported by the threat actor.

Overall, the AlphV ransomware gang, also known as BlackCat, has demonstrated a high level of capability and aggressiveness in targeting various sectors, including local governments and educational institutions in the U.S. The threat actor's use of novel techniques and threats against media outlets indicate a brazen approach to cybercrime.





Report 41

Summary:
On August 23rd, 2022, major airline technology provider Accelya was attacked by the ransomware group AlphV/Black Cat, leading to the exposure of company data on a ransomware leak site. The attack targeted a technology firm that provides services to numerous airlines, including Delta, British Airways, JetBlue, United, Virgin Atlantic, and American Airlines. Accelya managed to quarantine the ransomware before it could spread further, with no evidence of lateral movement to customers' environments. The group claimed to have stolen emails, worker contracts, and more from Accelya. AlphV/Black Cat has been active in targeting various sectors, including the airline industry, city governments, universities, energy companies, and video game companies. The group is believed to be a rebrand of the BlackMatter ransomware group, which was allegedly connected to the DarkSide ransomware group responsible for the Colonial Pipeline attack. The FBI has tracked at least 60 ransomware attacks by the AlphV/Black Cat group as of March. The threat actor's capabilities include targeting high-profile companies and utilizing novel techniques to breach their systems.





Report 42

Summary:
The report details a threat actor known as BlackCat Gang, also referred to as ALPHV, who used malvertising as an entry vector to distribute malware via cloned webpages of legitimate organizations. The threat actor leveraged the SpyBoy Terminator tool to tamper with protection provided by agents. The report highlights an incident where a targeted organization's network was compromised, leading to unauthorized activities such as stealing administrator privileges, establishing backdoor access, and attempting to steal passwords and access backup servers. The threat actor used various tools and techniques, including AdFind, PowerShell scripts, PowerView, PsExec, and more, to gather information, escalate privileges, and move laterally across the environment. The threat actor also attempted to disable antivirus programs using a KillAV BAT script. The report emphasizes the importance of early detection, response, and remediation to prevent serious damage from such attacks. Recommendations include educating employees about phishing, monitoring and logging activities, defining normal network traffic, improving incident response and communication, and engaging with cybersecurity professionals if needed. The report concludes with indicators of compromise (IOCs) for reference. The report does not specify the region, operating sector, or type of company of the victims targeted by the threat actor. The report was published by Trend Micro on an unspecified date.





Report 43

Summary: McLaren Health Care, a non-profit healthcare system in Michigan, experienced a data breach impacting 2.2 million individuals between late July and August 2023. The breach exposed sensitive personal information such as full names, Social Security numbers, health insurance information, and medical records. McLaren identified the breach on August 22, 2023, and the threat actor responsible was the ALPHV/BlackCat ransomware group, who claimed responsibility on October 4. The threat actors threatened to auction the stolen data set affecting 2.5 million people. McLaren notified impacted individuals and recommended vigilance in monitoring financial accounts. The threat actor's capability was demonstrated through the successful compromise of McLaren's systems and the theft of sensitive data. The tools and techniques used by the threat actor, including ransomware, data theft, and data auctioning, indicate a sophisticated and malicious operation. The incident highlights the vulnerability of healthcare organizations to cyber threats and the need for enhanced cybersecurity measures. Date: August 22, 2023 - October 4, 2023.





Report 44

The report discusses the threat actor known as "ALPHV, BlackCat Gang" and their new version of the Sphynx ransomware that embeds the Impacket networking framework and the Remcom hacking tool. Microsoft discovered this new version in August 17, 2023. The ransomware is used in recent campaigns and includes Impacket for lateral movement in target environments. Impacket is a popular post-exploitation toolkit used by threat actors for various malicious activities. The ransomware also embeds the Remcom hacking tool for remote execution of commands on network devices. Microsoft observed this new version being used by BlackCat affiliate 'Storm-0875' since July 2023. The BlackCat gang is considered one of the most advanced ransomware operations, constantly evolving its tactics. They have rebranded from DarkSide/BlackMatter and have been responsible for attacks on high-profile targets like Colonial Pipeline. The use of Impacket and Remcom in the Sphynx ransomware showcases the threat actor's capability to deploy file encryption across networks quickly. The report provides evidence of the threat actor's sophistication and the novelty of their tools and techniques.





Report 45

Summary: Motel One, a low-budget hotel chain operating in multiple countries, disclosed a data breach following a ransomware attack where customer data, including 150 credit card details, was stolen. The attack was claimed by the BlackCat/ALPHV ransomware gang, who threatened to leak nearly 24.5 million files if a ransom was not paid. The threat actors targeted Motel One's internal systems and stole sensitive information such as customer addresses, credit card data, and internal company documents. The attack was announced on September 30, 2023, and the threat group gave Motel One five days to negotiate the ransom payment. The company engaged IT experts to investigate and remediate the incident, while data protection authorities were notified. The threat actor's capability is evidenced by the large amount of data stolen and the novel technique of adding the victim to an extortion site on the dark web. The attack highlights the ongoing threat posed by ransomware actors to companies in the hospitality sector.





Report 46

Summary: Norton Healthcare, a Kentucky health system, disclosed a data breach after a ransomware attack in May 2023. The attack exposed personal information of patients, employees, and dependents, affecting roughly 2.5 million individuals. The attackers, claimed to be the ALPHV (BlackCat) gang, gained unauthorized access to sensitive data including Social Security Numbers, health information, and financial account numbers. Norton Healthcare did not link the attack to a specific ransomware operation but the ALPHV gang claimed responsibility and leaked proof of the breach on their dark web leak site. The attack targeted a healthcare organization in the United States, adding to a string of ransomware attacks on healthcare institutions nationwide. The victims received breach notification letters and will be provided with two years of free credit protection services. The attack highlights the ongoing threat posed by ransomware groups targeting healthcare organizations, as warned by the U.S. government. The attackers used novel techniques to exfiltrate data and disrupt operations, showcasing their capability to target high-profile organizations in the healthcare sector. The incident underscores the need for enhanced cybersecurity measures to protect sensitive data and prevent future attacks. 

Malformed report.





Report 47

Summary:
- Date: November 27th, 2023
- Threat actor: AlphV/Black Cat ransomware gang
- Target: Fidelity National Financial, a Fortune 500 provider of title insurance for property sales
- The ransomware gang claimed credit for the cyberattack on Fidelity National Financial, impacting certain company systems and acquiring credentials
- Fidelity National Financial acknowledged the attack in regulatory documents submitted to the U.S. Securities and Exchange Commission
- The attack caused disruptions to the company's services related to title insurance, escrow, mortgage transaction services, and technology to the real estate and mortgage industries
- The attack had downstream effects on the real estate industry, causing delays in home-sale closings
- Cybersecurity expert Kevin Beaumont noted that the company had tools exposed to the internet vulnerable to the CitrixBleed bug
- The attack occurred amidst warnings from top U.S. cybersecurity agencies about the vulnerability
- The attack on Fidelity National Financial followed a similar incident targeting Texas-based mortgage giant Mr. Cooper
- The threat actor demonstrated capability in targeting high-profile companies in the real estate and financial sectors using novel techniques and tools
- The attack highlights the ongoing threat posed by ransomware gangs to critical infrastructure and industries.





Report 48

Summary:
The threat actor known as BlackCat targeted the Pennsylvania Health System, specifically one physician practice located in Lackawanna County. The attack was detected on February 6, 2023, and involved unauthorized activity within the IT system. The attack demanded a ransom payment, but the health system refused to pay. BlackCat is a Russian-based ransomware-as-a-service group known for targeting organizations in the academic and healthcare sectors. The attack on the health system involved sensitive patient information, including clinically appropriate patient images for radiation oncology treatment. The health system is working with cybersecurity experts to investigate the incident and has not experienced disruptions in operations. The incident highlights the importance of healthcare organizations increasing cyber resiliency and monitoring legacy systems. The attack is part of a series of recent healthcare sector victims targeted by BlackCat, following a warning from the U.S. Department of Health and Human Services about threats involving the cybercrime group. The threat actor has demanded ransom payments as high as $1.5 million and frequently updates its tooling.





Report 49

Summary:
- Date: September 25th, 2023
- Threat actor: AlphV/Black Cat ransomware gang
- Target: Progressive Leasing, a product leasing giant based in Salt Lake City
- Sector: Retail
- Evidence: The ransomware gang claimed to have stolen personal information of over 40 million customers
- Novelty: The attack on Progressive Leasing follows a recent attack on MGM Resorts by the same threat actor
- The company reported the cyberattack to regulators at the SEC and is still investigating the incident
- The attack resulted in the theft of sensitive information, including social security numbers
- The company is part of a larger corporation, PROG Holdings, offering "buy now, pay later" options
- The ransomware gang is known for causing international headlines with its attacks
- The company's CFO stated that they do not expect a financial fallout from the attack due to limited operational impact.





Report 50

Summary:
The threat actor known as ALPHV, also referred to as BlackCat ransomware, has been identified for cloning a victim's website to leak stolen data as an extortion tactic. The incident occurred on December 26, 2023, when the threat actor published stolen data from a financial services company on a replica site. The stolen data included various documents such as memos, payment forms, employee information, financial data, and passport scans, totaling 3.5GB. ALPHV shared the data on a file-sharing service and distributed the link on its leak site. This tactic of impersonating the victim's site to leak data is a new trend that may be adopted by other ransomware gangs due to its low cost and potential impact on victims. The threat actor's capability to create a search for specific data stolen from victims sets them apart from other ransomware groups. This incident highlights the evolving threat landscape that victims need to navigate, as ransomware operators continue to test new extortion tactics.





Report 51

Summary:
The threat actor known as ALPHV, also referred to as BlackCat Gang, has escalated their extortion tactics by creating a website for victims to search for their stolen data. This innovative approach involves releasing stolen data from a hotel and spa in Oregon, including sensitive employee information like Social Security Numbers. The threat actor created a dedicated website for victims to check if their data was stolen, increasing the pressure on victims to pay the ransom. This tactic aims to scare employees and guests into demanding the removal of their data from the web, ultimately leading to ransom payment. ALPHV is believed to be a rebrand of the DarkSide/BlackMatter gang responsible for the Colonial Pipeline attack. The threat actor's capability is demonstrated by the time-consuming task of setting up individual employee data packs on the website. The novelty of this approach remains to be seen in terms of its success and potential impact on future ransomware operations. The report was published on June 14, 2022.





Report 52

Summary:
The ALPHV ransomware group, also known as BlackCat, targeted a healthcare network in Pennsylvania by publishing clinical photographs of breast cancer patients. The group, linked to Russia, attempted to extort the network, Lehigh Valley Health Network, by threatening to release sensitive patient data. The attack targeted a computer system used for patient images for radiation oncology treatment. The network's president stated that they would not pay the ransom and were taking the incident seriously to protect patient data. The attack caused the network's website to become inaccessible. Experts and professionals in the cybersecurity field condemned the gang's actions as despicable and barbaric. ALPHV celebrated the attack and threatened to unleash more damage on the network. Similar attacks on healthcare organizations by ransomware gangs have been reported in recent months, highlighting the persistent threat in the industry. The incident involving ALPHV and Lehigh Valley Health Network showcases the increasing severity and audacity of cybercriminals targeting sensitive sectors like healthcare.





Report 53

The threat actor known as ALPHV, BlackCat Gang, was behind a cyberattack on Reddit in February 2023. The attack involved stealing 80GB of data from Reddit, including internal documents, source code, and employee data. The threat actors gained access to Reddit's systems through a phishing attack on an employee. The attack did not impact user passwords, accounts, or credit card information. The BlackCat Gang attempted to extort $4.5 million from Reddit to delete the stolen data but did not receive a response. The threat actors threatened to leak the data if the ransom was not paid. This attack was similar to one on Riot Games, where source code for games was stolen. The BlackCat Gang is also believed to be responsible for an attack on Western Digital in March 2023. The threat actors did not encrypt devices in the Reddit attack. The Western Digital attack caused a massive outage to the company's My Cloud service. The threat actor's capabilities include stealing large amounts of data and using extortion tactics to demand ransom. The tools and techniques used by the threat actor are not specified in the report. The report does not mention the region, operating sector, or type of company of the victims targeted by the threat actor. The report does not provide a specific date or operation time window for the attack.





Report 54

Summary:
The threat actor known as BlackCat (aka ALPHV) is a ransomware group that has been operating since at least November. They have targeted various victims, including OilTanking GmbH, Swissport, Florida International University, and the University of North Carolina A&T. The group has been demanding ransom payments of up to $2.5 million, with a possible discount for quick resolution. They engage in "quadruple extortion" tactics, including encryption, data theft, denial of service attacks, and harassment. BlackCat uses advanced techniques such as search functionality in leaked data and has been associated with other ransomware groups like DarkSide and BlackMatter. The group has been actively recruiting affiliates and developing new features for their ransomware, such as multiple encryption modes and unique onion domains for each victim. BlackCat's arsenal includes tools like Cobalt Strike, PsExec, and Mimikatz for network intrusions and post-exploitation. The group has been actively publishing new victims almost every 4 days and has been competing with other ransomware syndicates like Lockbit and Conti. Mitigation strategies include regular backups, network segmentation, and implementing multifactor authentication. The threat actor's activities are monitored on the Dark Web, and they have been actively recruiting new members and developing new features for their ransomware operations.





Report 55

Summary:
A string of cyberattacks on European oil and chemical sectors occurred in February 2022, targeting major ports in Belgium, the Netherlands, and Germany. The attacks were ransomware incidents affecting oil port terminals and German oil industry companies, forcing oil suppliers to reroute their products. The attacks are believed to be linked to the BlackCat and Conti families, with the BlackCat group implicated in recent compromises. European prosecutors and cybersecurity officials are investigating the incidents, but there is no evidence suggesting coordination between the attacks. The attacks are likely motivated by criminal intent rather than nation-state involvement. The attacks disrupted operations at companies like Sea-Invest and Oiltanking GmbH, leading to the temporary halt of activities and rerouting of oil supplies. The incidents highlight the ongoing threat to critical infrastructure from cyberattacks, with previous incidents like the Colonial Pipeline ransomware attack serving as a reminder of the potential impact. The report does not mention any specific novel tools or techniques used by the threat actor.





Report 56

Summary:
The threat actor known as BlackCat (aka ALPHV) is a ransomware family that emerged in mid-November 2021, operating on a ransomware-as-a-service (RaaS) model. BlackCat targets organizations in various sectors, including construction, retail, transportation, insurance, and pharmaceuticals, with a significant number of victims in the U.S. and Europe. The ransomware is coded in Rust, making it highly customizable and capable of targeting both Windows and Linux systems. BlackCat employs multiple extortion techniques, such as data exfiltration, threats of DDoS attacks, and releasing data if ransom is not paid. The group uses legitimate tools like Mimikatz and LaZagne for password recovery and anti-forensics tools like fileshredder. Victims are targeted with ransom demands of up to $14 million, with the option to pay in Bitcoin or Monero. BlackCat utilizes a unique onion domain for communication with victims and employs triple extortion tactics. Palo Alto Networks provides detection and prevention capabilities for BlackCat ransomware through products like Cortex XDR and Next-Generation Firewalls. The threat actor's innovative and sophisticated tactics, combined with the use of Rust programming language, make BlackCat a significant threat in the ransomware landscape. The report provides detailed technical information, courses of action, and indicators of compromise related to BlackCat ransomware.





Report 57

Summary:
- Threat actor: ALPHV, BlackCat Gang
- Target: Toy maker Jakks Pacific, a major toy production company with licensing deals with Disney and Nintendo
- Date: Cyberattack reported on December 29, 2022
- Evidence of capability: Ransomware attack encrypted servers, personal information potentially accessed
- Novelty of tools and techniques: Two ransomware groups, Hive and BlackCat, posted stolen data, highlighting the use of initial access brokers and wholesale access markets in the ransomware ecosystem
- Company's response: Hired cybersecurity experts, ongoing investigation, refusal to pay $5 million ransom
- Impact: Minor stir among cybersecurity experts, potential for data leakage and financial impact
- Region: United States
- Operating sector: Toy manufacturing
- Type of company: Large corporation with global reach and high-profile licensing deals
- Source: The Record from Recorded Future News

Overall, the report details a cyberattack on Jakks Pacific by ransomware groups, showcasing the evolving tactics and strategies used by threat actors in the cybercrime landscape.





Report 58

Summary: The report provides an update on the activities of the BlackCat ransomware group, which is believed to be a rebranded version of the BlackMatter or DarkSide ransomware group. The threat actor has targeted several organizations, including a Nigerian betting platform, three universities, and a natural gas supplier in Latin America. The report details the ransomware attacks on these organizations, including Bet9ja, FIU, NCAT State University, AIT-Thailand, and TGS. The threat actor has claimed to have stolen data, including confidential information and personally identifiable information, from these victims. The report also highlights the response of the organizations to the attacks, including investigations and security measures taken. The threat actor has threatened to publish the stolen data if ransom demands are not met. The report also mentions the connection between BlackCat and BlackMatter ransomware groups, as identified by cybersecurity researchers. The threat actor has been using novel tools and techniques, such as a custom exfiltration tool named Fendr, to steal data from corporate networks. The report provides insights into the evolving tactics of the threat actor and the impact of their attacks on various sectors and regions.





Report 59

Summary:
- Threat actor known as ALPHV/BlackCat discovered in December 2021, first professional cybercrime group to use Rust programming language for ransomware.
- ALPHV actively recruiting operators from various ransomware organizations, offering up to 90% of ransom paid by victims.
- Group's leak site named over twenty victim organizations as of late January 2022.
- Concern about malware shifting to Rust for security reasons.
- Evidence suggests ALPHV/BlackCat author previously involved with REvil ransomware cartel.
- U.S. State Department offering $10 million reward for information on REvil leadership.
- Evidence points to Sergey Duckerman as core developer for ALPHV ransomware.
- Sergey Duckerman denies involvement in coding malware but has connections with individuals involved.
- Sergey Duckerman's GitHub account deleted after investigation.
- Binrs, another alias, banned from multiple cybercrime forums.
- Rust programming language gaining popularity in malware development.
- Concerns raised about security of Rust programming language.
- Evidence suggests Russian involvement in ransomware operations.
- Inconsistencies in statements made by individuals involved in threat actor activities.





Report 60

Summary:
The threat actor known as ALPHV/BlackCat Ransomware Gang has been targeting corporations and public entities in the Americas and Europe. They have been using Google ads laced with malware to infect victims with their ransomware. The gang typically gains initial access through valid credentials, exploitation of remote management services, and browser-based attacks. One of their affiliates has expanded into malvertising, using Google ads to distribute the Nitrogen malware, which leads to the ALPHV/BlackCat ransomware infection. The gang has connections to the former BlackMatter ransomware group and has been involved in high-profile attacks on companies like MGM Resorts, McClaren Health Care, and Clarion. They have been known to use malicious tactics, such as publishing sensitive patient data and photos of breast cancer patients, to force victims to pay ransom demands. The gang has been observed using a variety of intrusion tools, including Cobalt Strike, Sliver, and Brute Ratel. Organizations are advised to include browser-based attacks in their user awareness training and implement attack surface reduction rules to protect against such threats. It is recommended to engage with a Managed Detection and Response (MDR) provider to disrupt threats before they impact the business. The eSentire Threat Response Unit (TRU) is actively monitoring and responding to threats posed by the ALPHV/BlackCat Ransomware Gang. The report was published on November 14, 2023, by eSentire.


