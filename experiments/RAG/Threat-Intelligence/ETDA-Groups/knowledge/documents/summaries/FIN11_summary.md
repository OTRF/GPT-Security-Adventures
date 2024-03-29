
Report 1

Malformed report.





Report 2

Summary:
- Threat actor: FIN11
- Region: Australia
- Operating sector: Financial services
- Type of company: Australian Securities and Investments Commission (ASIC)
- Date: January 15th, 2021
- Evidence of capability: Accessed ASIC server through Accellion software, potentially viewed limited information from recent Australian credit license applications
- Novelty of tools and techniques: Exploited Accellion FTA vulnerability, similar to New Zealand Reserve Bank breach
- Response: ASIC disabled server access, working on forensic investigation with cybersecurity experts
- Impact: No evidence of other systems being reached or impacted
- Accellion customers affected: Dozens potentially compromised by exploiting the same vulnerability.





Report 3

AutoZone, a leading retailer and distributor of automotive spare parts and accessories in the U.S., was targeted in a data breach by the Clop ransomware gang as part of the MOVEit file transfer attacks. The breach occurred on May 28, 2023, compromising data of 184,995 individuals. The threat actor exploited a zero-day vulnerability in the MOVEit application to exfiltrate data, including employee names, email addresses, parts supply details, tax information, and payroll documents. The leaked data did not include customer information. AutoZone informed U.S. authorities about the breach and provided identity theft protection services to affected individuals. The Clop ransomware gang is expected to receive over $75 million in extortion payments from companies impacted by the MOVEit data theft attacks. The threat actor's use of novel techniques and tools, such as exploiting a zero-day vulnerability in MOVEit, demonstrates their advanced capabilities in carrying out cyber attacks.





Report 4

Summary:
On July 19th, 2023, the U.S. cosmetics manufacturer Estée Lauder was targeted in a ransomware attack by the threat actors BlackCat and Clop. The attackers gained unauthorized access to the company's systems and stole data, causing disruptions to its business operations. BlackCat claimed to have stolen over 130 gigabytes of data without encrypting the network, operating independently from Clop. The attack coincided with Estée Lauder's forecasted drop in sales and profits due to the slow recovery from the COVID-19 pandemic. The company, known for brands like Clinique and MAC, is one of the world's largest cosmetics manufacturers. The threat actors may have exploited vulnerabilities in the MOVEit file transfer software to target the company.





Report 5

Summary:
- Threat actor: CL0P ransomware group
- Region: Global, with specific IP addresses located in Moscow, Russia and St. Petersburg, Russia
- Operating sector: Various companies targeted by ransomware attacks
- Type of company: Not specified
- Date: September 29, 2023
- Evidence of capability: CL0P ransomware group shifted to using torrents to distribute victim data after exploiting the MOVEit transfer vulnerability, demonstrating adaptability and persistence in targeting victims.
- Novelty of tools and techniques: CL0P utilized torrents for data distribution, providing faster download speeds for victims and leveraging peer-to-peer file exchange. The threat actor used unique methods to seed data initially, allowing for insights into their operations and infrastructure.
- Tools and techniques used: Transmission 3.00, qBittorrent, FTP, SSH, self-signed TLS certificates
- Impact: CL0P ransomware group stole and leaked terabytes of data, with a significant amount expected to continue to be released. The threat actor remained consistent in releasing data, making good on threats to victims.
- Mitigations: Palo Alto Networks customers can leverage Cortex XDR, XSIAM, and Xpanse for protection against CL0P ransomware and post-exploitation activities associated with the MOVEit vulnerability. Customers can also engage the Unit 42 Incident Response team for specific assistance with this threat and others.





Report 6

Summary: The threat actor "FIN11" targeted the City of Toronto, UK's Virgin Red, and the Pension Protection Fund using the Clop ransomware gang's ongoing GoAnywhere hacking spree. By exploiting a remote code execution flaw in Fortra's GoAnywhere secure file transfer tool, the threat actor breached over 130 organizations. The City of Toronto confirmed data theft through a third-party vendor. The Clop ransomware gang claimed to have breached 130+ organizations and stolen data over ten days using the CVE-2023-0669 vulnerability. The threat actor's novel technique involved exploiting unpatched GoAnywhere MFT instances with an exposed administrative console. The victims impacted by the threat actor's attacks included Hitachi Energy, Saks Fifth Avenue, and Rubrik. The threat actor's capability to breach high-profile organizations highlights the severity of the attacks. (Date: March 23, 2023)





Report 7

Summary:
- Threat actor: FIN11
- Region: Global
- Operating sector: Crimeware
- Type of company targeted: University in Colombia
- Date of operation: 26th of December 2022
- Capability: First Linux variant of Cl0p ransomware observed, flawed encryption algorithm allowing decryption without ransom payment, free decryptor available
- Novelty of tools and techniques: Linux variant lacks some functionalities present in Windows version, uses flawed encryption logic allowing file decryption without payment
- Future expectations: Linux variant expected to eliminate differences with Windows version
- Indicators of Compromise: SHA1 hashes provided for ELF and Windows Cl0p variants, ransom note details, contact emails, onion leak page, YARA rule for detection

Overall, the report highlights the discovery of the first Linux variant of Cl0p ransomware targeting Linux systems with flawed encryption, providing insights into the capabilities and flaws of the threat actor.





Report 8

Summary:
The threat actor "FIN11" known as Clop ransomware gang has adopted a new tactic of leaking data stolen during MOVEit Transfer attacks on clearweb sites, following the ALPHV ransomware gang's strategy. This tactic involves creating clearweb websites to make it easier for victims to access leaked data, potentially increasing the spread of information. The threat actor targeted companies like PWC, Aon, EY, Kirkland, and TD Ameritrade, leaking stolen data through clearweb sites. While this method aims to pressure companies into paying ransom, the sites were easily taken offline, raising doubts about the effectiveness of this extortion tactic. The threat actor's capability to adapt and use novel techniques in data theft attacks was demonstrated through the creation of clearweb sites for leaking stolen data. The report was published on July 23, 2023, by BleepingComputer.





Report 9

Summary: The threat actor FIN11, specifically the Clop ransomware gang, targeted Saks Fifth Avenue, a luxury brand retailer, claiming to have stolen mock data. The attack was part of ongoing exploits against vulnerable GoAnywhere MFT servers of established enterprises. The threat actor exploited a zero-day vulnerability (CVE-2023-0669) to gain remote code execution on unpatched servers. Clop disclosed breaching 130+ organizations and stealing data over ten days using this vulnerability. Saks confirmed the incident was linked to Fortra, a vendor, and stated that no real customer data or payment information was stolen. The incident highlights the threat actor's capability to exploit novel vulnerabilities and target high-profile companies in the retail sector. Date: March 21, 2023.





Report 10

Summary:
- Threat actor: Clop ransomware gang
- Region: Global
- Operating sector: Various organizations, including energy, supermarket, cybersecurity, and universities
- Type of company: Not specified
- Evidence of capability: Exploited zero-day vulnerability (CVE-2023-0669) in GoAnywhere MFT tool to breach over 130 organizations, stole data, and had the ability to move laterally through networks
- Novelty of tools and techniques: Used zero-day vulnerability in GoAnywhere MFT tool, refused to deploy ransomware but only stole data, linked to TA505 threat group known for deploying Clop ransomware
- Date: Attacks occurred over a ten-day period starting in February 2023
- Operation time window: Not specified
- Malware used: Clop ransomware
- Tools used: GoAnywhere MFT secure file transfer tool
- Source: BleepingComputer, February 10, 2023.





Report 11

Summary: The Clop ransomware gang exploited a zero-day vulnerability in the Fortra GoAnywhere MFT secure file-sharing solution to extort companies, with evidence of data theft from 130 companies. The victims included companies like Community Health Systems (CHS) and Hatch Bank. The threat actor contacted BleepingComputer claiming responsibility for the attacks and began publicly exploiting victims by adding them to their data leak site. Ransom demands have been reported, with similarities to previous attacks using different zero-day vulnerabilities. The threat actor's capability to exploit novel vulnerabilities and extort victims demonstrates their advanced tactics. Operation time window: February to March 2023.





Report 12

Summary: The Clop ransomware gang, known as FIN11, resurfaced in April 2022 after a period of inactivity, targeting 21 victims primarily in the industrial and tech sectors. The surge in activity was noted by NCC Group researchers, with the group being the fourth most active threat actor in April. Despite leaking data from nearly two dozen victims, the group's activity level remains relatively low. The Clop gang's infrastructure was previously disrupted in June 2021 by Operation Cyclone, resulting in minor impact. The threat actor has been linked to ransomware attacks since 2019 and was involved in the Accellion data breaches, leading to increased ransom payments. The group's tactics include exfiltrating data from high-profile companies and using it to extort ransom payments. The recent increase in targeting suggests a potential shutdown process, similar to what the Conti group is undergoing. The threat actor's capability and use of novel techniques indicate a persistent and evolving threat. 

Date: May 28, 2022

Region: Global

Operating Sector: Industrial and Tech

Type of Company: Industrial organizations, tech companies

Evidence of Capability: Resurfaced after period of inactivity, targeted 21 victims, linked to previous ransomware attacks and data breaches

Novelty of Tools and Techniques: Exfiltration of data for extortion, involvement in Accellion data breaches

Malformed report





Report 13

Malformed report.





Report 14

Summary:
The threat actor known as FIN11, associated with the Clop ransomware gang, leaked stolen Bombardier blueprints of the GlobalEye radar snoop jet, potentially compromising sensitive military information. The leak was attributed to a vulnerability in Accellion file-transfer software, affecting multiple organizations, including Bombardier. The leaked CAD drawings included detailed images of military radar antennas and aircraft, raising concerns about the extent of the breach. The threat actor has a history of targeting high-profile companies for ransomware extortion, indicating a sophisticated and persistent threat. The incident occurred on February 23, 2021, and involved around 130 Bombardier employees in Costa Rica. The use of novel tools and techniques, such as exploiting vulnerabilities in third-party software, demonstrates the evolving capabilities of the threat actor.





Report 15

Summary: The threat actor "FIN11," identified as the Clop ransomware gang, has been extorting companies impacted by the MOVEit data theft attacks. The threat actors exploited a zero-day vulnerability in the MOVEit Transfer platform to steal files stored on the server. The Clop gang claimed responsibility for breaching "hundreds of companies" and threatened to leak stolen data if extortion demands were not met. Victims targeted include companies like Shell, UnitedHealthcare Student Resources, and the University of Georgia. The threat actor's capability is evidenced by their successful exploitation of zero-day vulnerabilities and their use of extortion tactics. The novelty lies in the targeting of specific sectors and the use of data theft as leverage for ransom demands. The operation time window for leaking stolen data was set for June 21st.





Report 16

Summary:
The threat actor known as Clop ransomware has resumed its operations after recent arrests of some of its members. The arrests, conducted by the National Police of Ukraine, the Korean National Police Agency, and the USA, targeted the money laundering aspect of the operation, leading to the seizure of assets and disruption of infrastructure. Despite the arrests, Clop has continued its ransomware activities by listing new victims on their data leak site. The threat actor has been active since March 2019, targeting enterprises with a variant of the CryptoMix ransomware. Clop is known for large-scale ransomware attacks and data theft, with estimated damages reaching $500 million. The threat actor has also been involved in stealing data from Accellion FTA file transfer devices using zero-day vulnerabilities. The core members of Clop are believed to be residing in Russia, indicating the international nature of the threat actor. Law enforcement actions have had some impact on ransomware groups this year, targeting affiliates and infrastructure to disrupt criminal activities. The novelty of Clop's tools and techniques lies in their ability to spread throughout networks, steal data, and deploy ransomware effectively. The threat actor's resilience and adaptability in the face of law enforcement actions demonstrate their capability to continue operations despite setbacks. The report was published on June 23, 2021.





Report 17

Summary: The threat actor FIN11, known for the Clop ransomware, has evolved its extortion tactics by using torrents to leak data stolen in MOVEit attacks, starting on May 27th. This new method aims to evade takedowns and increase data distribution speed. Victims targeted include organizations worldwide, such as Aon, K & L Gates, and Zurich Brazil. The use of torrents allows for faster data transfer speeds and decentralized distribution, making it harder for law enforcement to shut down. This novel approach showcases the threat actor's adaptability and sophistication, potentially leading to increased extortion payments estimated at $75-$100 million.





Report 18

Summary: The threat actor FIN11 targeted the Colorado Department of Health Care Policy & Financing (HCPF) through a data breach involving the IBM MOVEit software, impacting over four million individuals. The breach was facilitated by Clop ransomware exploiting a zero-day vulnerability (CVE-2023-34362). The threat actors accessed and likely exfiltrated sensitive information, including personal and health data of HCPF members. This incident demonstrates the threat actor's capability to conduct large-scale data breaches and utilize novel techniques such as zero-day exploits. The victims, in this case, were individuals enrolled in Health First Colorado (Medicaid) and Child Health Plan Plus programs. The operation time window was around May 28, 2023, when the unauthorized access occurred.





Report 19

Summary: Crown Resorts, a gambling and entertainment company in Australia, confirmed a ransom demand after a data breach on their GoAnywhere server by the Clop ransomware gang, utilizing a zero-day vulnerability. The threat actor has shifted from file encryption to data extortion attacks, claiming to have stolen data from 130 organizations over ten days. The company stated that no customer data was compromised, and they are working with law enforcement to investigate the incident. Clop has a history of exploiting zero-day flaws for data theft and extortion, with previous attacks on companies like Shell and Kroger. The vendor of GoAnywhere software, Fortra, is facing a potential class action lawsuit for inadequate cybersecurity measures. The threat actor's novel use of zero-day vulnerabilities and data extortion tactics demonstrates their capability and evolving techniques. (Date: March 28, 2023)





Report 20

Summary: Cybersecurity firm Qualys was targeted by the threat actor FIN11 in a data breach using a zero-day vulnerability in the Accellion FTA server. The attack resulted in the theft of sensitive data such as purchase orders, invoices, and tax documents. The threat actor, known for using the Clop ransomware, has been extorting victims by posting stolen data on their ransomware data leak site. Qualys confirmed the breach and stated that a limited number of customers were affected, with no impact on their production environments. The threat actor's capability to exploit zero-day vulnerabilities and extort victims using ransomware demonstrates their advanced tactics and techniques. The attack occurred in December 2020, and Qualys has since shut down the affected Accellion FTA servers and hired Mandiant for further investigation.

Date: December 2020
Region: Global
Operating Sector: Cybersecurity
Type of Company: Cybersecurity firm

Evidence of Capability: Exploitation of zero-day vulnerability, data exfiltration, extortion using ransomware
Novelty of Tools and Techniques: Use of Clop ransomware, targeting Accellion FTA servers, public extortion of stolen data





Report 21

Summary:
- Threat actor "FIN11" targeted the Washington State Auditor office, exposing 1.6 million unemployment claims in February 2021.
- The threat actor exploited a vulnerability in Accellion's file transfer service, affecting various organizations, including banks and government agencies.
- The exposed data files contained sensitive personal information, such as social security numbers, bank account details, and employment information.
- Accellion acknowledged a zero-day vulnerability in their legacy FTA solution in mid-December, leading to multiple breaches before a patch was deployed.
- Organizations like the Reserve Bank of New Zealand, the Australian Securities and Investments Commission, and the Harvard Business School were also impacted.
- The threat actor's use of novel techniques and tools, such as exploiting the Accellion vulnerability, demonstrates their advanced capabilities.
- The incident highlights the ongoing threat posed by threat actors like FIN11 targeting organizations with valuable data.
- The victims of the data breach included Washington residents, local governments, and state agencies, emphasizing the widespread impact of the attack.





Report 22

Summary: The threat actor FIN11 targeted Delta Dental of California, a dental insurance provider covering 45 million people across 15 states. The threat actors exploited a zero-day SQL injection flaw in the MOVEit Transfer software application, leading to remote code execution. The Clop ransomware gang leveraged this vulnerability to breach thousands of organizations worldwide. The breach occurred between May 27 and May 30, 2023, impacting 6,928,932 customers who had their personal data exposed, including names, financial account numbers, and credit/debit card numbers. Delta Dental of California provided free credit monitoring and identity theft protection services to mitigate the risk for affected individuals. This incident marks the third largest MOVEit data breach. Date of breach discovery: June 1, 2023. Date of completion of investigation: November 27, 2023.





Report 23

Summary: Energy giant Shell disclosed a data breach after attackers compromised the company's secure file-sharing system powered by Accellion's File Transfer Appliance (FTA). The attack did not affect Shell's core IT systems. The attackers were linked to the FIN11 cybercrime group and the Clop ransomware gang. Less than 100 out of 300 customers using the legacy FTA software were breached, with less than 25 victims suffering significant data theft. Multiple organizations, including cybersecurity firm Qualys and the Reserve Bank of New Zealand, were affected by breaches targeting Accellion FTA. The attacks were part of ongoing extortion attempts targeting organizations using unpatched Accellion FTA versions. The report was published on March 22, 2021.





Report 24

Summary:
The threat actor FIN11, also known as Lace Tempest, has been active since 2016 and has targeted various sectors globally, including defense, education, energy, financial, hospitality, retail, telecommunications, technology, and transportation. FIN11 has evolved its monetization methods over the years, shifting from POS malware to ransomware and hybrid extortion. The group has used a variety of tools such as Amadey, AZORult, Clop ransomware, and Meterpreter, among others. Notably, FIN11 has been linked to criminal service providers for domain registration, hosting, and malware services, enhancing the scale and sophistication of their operations. The threat actor has been involved in numerous high-profile attacks, including ransomware incidents targeting universities, healthcare organizations, government agencies, and major corporations. Counter operations against FIN11 have included arrests of group members and the offering of bounties for information on the group.





Report 25

FIN11, a financially motivated threat group, has been conducting widespread phishing campaigns since at least 2016. They have targeted organizations in the financial, retail, and hospitality sectors from 2017 through 2018, expanding to include a diverse set of sectors and geographic regions in 2019. The threat group conducts up to five high-volume campaigns a week, showing significant gaps in their phishing operations. While Mandiant has responded to numerous FIN11 intrusions, the group has only successfully monetized access in a few instances. Recently, FIN11 has shifted to deploying CLOP ransomware and threatening to publish exfiltrated data to pressure victims into paying ransom demands. The group's evolving monetization methods, from POS malware in 2018 to ransomware in 2019, indicate a trend towards post-compromise ransomware deployment and data theft extortion. FIN11's use of criminal service providers complicates attribution, and they have utilized services for anonymous domain registration, bulletproof hosting, code signing certificates, and private or semi-private malware. The group's activities are not attributed to TA505, although they share some similarities. The full report on FIN11 is available through the FireEye Intelligence Portal.





Report 26

Summary:
- Threat actor FIN11 has been observed impersonating popular video conference application Zoom to distribute malware.
- The campaign was detected on 2022-09-21 by CYFIRMA research team.
- FIN11 is known for conducting large-scale campaigns using impersonated web applications.
- The threat actor used Zoom download pages to install Information Stealer (Vidar) targeting a large attack surface.
- The threat actor has been associated with CLOP ransomware for post-compromise ransomware deployment and data theft extortion.
- Fake Zoom download pages were discovered, all registered in the Russian Federation.
- FIN11 has a history of conducting phishing campaigns targeting various sectors and geographic regions.
- The threat actor used novel techniques like embedding malicious files in legitimate Zoom applications to compromise systems.
- Malicious URLs pointed to .exe, .rar, .apk, .lnk, and .pdf files indicating a well-planned campaign targeting all operating systems.
- The threat actor leveraged PowerShell, MSBuild.exe, and DLL files related to information stealers like Vidar in the attack.





Report 27

Summary:
The threat actor FIN11, in collaboration with the Clop ransomware gang, targeted up to 100 companies globally using Accellion's legacy File Transfer Appliance in mid-December 2020. The attacks involved multiple zero-day vulnerabilities and a new web shell named DEWMODE. The threat actors stole sensitive data and threatened victims with public exposure unless a ransom was paid. Victims included supermarket giant Kroger, Singtel, QIMR Berghofer Medical Research Institute, and others. The attackers used SQL injection, OS command execution, and SSRF vulnerabilities to gain access. Mandiant tracked the attacks as UNC2546 and UNC2582, highlighting the collaboration between Clop and FIN11. The use of novel techniques like the DEWMODE web shell and the exploitation of zero-day vulnerabilities demonstrate the evolving capabilities of the threat actor. The attacks represent a significant shift in FIN11's tactics, as they traditionally relied on phishing campaigns. The relationship between FIN11 and UNC2546 is still under assessment due to differences in infection vectors and tactics. The attacks underscore the increasing sophistication and collaboration among threat actors in the cyber landscape.





Report 28

Summary: The threat actor FIN11 targeted the New York City Department of Education (NYC DOE) in a data breach affecting 45,000 students using the MOVEit Transfer server. The breach exploited a zero-day vulnerability (CVE-2023-34362) before security updates were available. The Clop ransomware gang claimed responsibility for the attack and has a history of targeting managed file transfer (MFT) platforms. Evidence suggests that Clop had been testing exploits for the vulnerability since 2021. The attack resulted in data theft from multiple organizations, including universities, healthcare providers, and government entities. The FBI is investigating the breach, and impacted organizations are being extorted by the threat actor. The threat actor's use of novel techniques and tools, along with the scale of the attack, demonstrate the capability and persistence of FIN11. (Date: June 26, 2023)





Report 29

Summary:
The threat actor known as Clop targeted hundreds of companies in a mass extortion campaign using a zero-day vulnerability in the MOVEit file transfer software. The Russian-speaking cyber gang exfiltrated sensitive data for use in extortion campaigns, with ongoing victim additions. Clop's use of zero-day bugs in ransomware campaigns is rare but not unheard of, showcasing a novel approach in the cybercrime landscape. The group likely acquired the zero-day bug through underground forums or internal discovery. Clop's strategy of exfiltrating data for extortion rather than encrypting files is a unique tactic that has been successful, leading to a potential trend in ransomware operations. The focus on exploiting middleware programs like MOVEit highlights a new avenue for threat actors to target vulnerabilities in less scrutinized software. The threat actor's maturity and success in targeting companies with middleware vulnerabilities indicate a shift in ransomware tactics towards data exfiltration and extortion. The operation time window for Clop's campaign was during the summer of 2023.





Report 30

Summary: Johnson & Johnson disclosed a data breach impacting patients due to a third-party breach involving IBM, affecting CarePath users. The breach exposed sensitive information such as full names, contact information, and medical details of users enrolled before July 2nd, 2023. The incident, discovered on August 2nd, 2023, revealed a previously undocumented method that allowed unauthorized access to the CarePath database. The compromised data could be used for phishing and social engineering attacks. IBM, the technology service provider, fixed the security gap and offered free credit monitoring to impacted individuals. This incident is separate from the Clop ransomware attack on IBM earlier this year.





Report 31

Summary: Kroger, a supermarket giant, experienced a data breach due to a vulnerability in the Accellion FTA software, exposing pharmacy and employee data. The breach was disclosed on February 20, 2021, with no impact on grocery store data or payment information. Kroger is offering free credit monitoring to affected individuals. The threat actor exploited a zero-day vulnerability in the Accellion FTA service, affecting multiple companies. The breach highlights the wide-reaching impact of Accellion attacks on various sectors. The threat actor's capability to exploit novel vulnerabilities and target sensitive data demonstrates a sophisticated approach. The incident underscores the ongoing threat posed by cybercriminals targeting organizations using secure file-transfer services.





Report 32

Summary:
The threat actor FIN11 conducted a data breach impacting Genworth Financial, CalPERS, and other companies, exposing data for 3.2 million individuals. The attacks began on May 27, 2023, exploiting a MOVEit Transfer zero-day vulnerability. The Clop ransomware gang extorted companies by listing impacted organizations on a data leak site. Genworth Financial estimated 2.5-2.7 million individuals affected, with exposed data including sensitive information like social security numbers. CalPERS, the largest public pension fund in the US, reported approximately 769,000 members impacted. The threat actor demonstrated capability in exploiting zero-day vulnerabilities and using ransomware for extortion. The novel use of MOVEit Transfer zero-day vulnerability and data theft tactics indicate evolving techniques by the threat actor. Date of operation: May 27, 2023 onwards.





Report 33

The threat actor known as FIN11 targeted the State of Maine government, resulting in a data breach affecting 1.3 million individuals. The breach exploited a vulnerability in the MOVEit file transfer tool, with evidence pointing to the Clop ransomware gang as the perpetrators. The attack occurred between May 28, 2023, and May 29, 2023, with various Maine state agencies affected, including the Department of Health and Human Services and the Department of Education. Personal information such as Social Security numbers, driver's licenses, and health insurance details were exposed. The State of Maine delayed notifying the public to conduct a thorough investigation and is offering free credit monitoring and identity theft protection services to affected individuals. The threat actor's use of a zero-day vulnerability in a widely used software product demonstrates their advanced capabilities and novel techniques.





Report 34

Summary:
- Threat actor: FIN11
- Date: November 26, 2021
- Region: Singapore
- Operating sector: Maritime services provider
- Victims: Swire Pacific Offshore
- Evidence of capability: Clop ransomware attack, unauthorized network infiltration, theft of company data including passports, payroll information, ID numbers, bank account details, email addresses, and internal correspondence messages.
- Novelty of tools and techniques: Clop ransomware group claimed responsibility, leaked data indicates theft of personal data of employees, potential impact on 2,500 individuals.
- Targeting the shipping industry: Ransomware actors targeting costly disruptions in the industry due to post-pandemic challenges.
- Conclusion: Swire Pacific Offshore investigating the incident, no material impact on global operations reported, incident reported to relevant authorities.





Report 35

Summary: Microsoft has identified the Clop and LockBit ransomware gangs as the threat actors behind recent attacks on PaperCut servers, exploiting vulnerabilities to steal corporate data. The vulnerabilities, allowing remote code execution and information disclosure, were actively exploited in the wild, with a PoC exploit released shortly after. The threat actor, tracked as Lace Tempest and overlapping with FIN11 and TA505, has been exploiting the vulnerabilities since April 13th. They deploy TrueBot malware, linked to the Clop ransomware operation, and use Cobalt Strike beacon for lateral movement and data theft. The attacks on PaperCut servers fit the pattern of Clop's preference for data exfiltration over file encryption, making organizations urged to upgrade to patched versions immediately. The threat actor's capability and use of novel techniques indicate a sophisticated and evolving threat landscape. 

Date: April 26, 2023

Region: Global

Operating Sector: Printing management software

Type of Company: Large companies, state organizations, education institutes

Evidence of Capability: Exploitation of vulnerabilities, deployment of TrueBot malware, use of Cobalt Strike beacon, data exfiltration

Novelty of Tools and Techniques: Exploitation of vulnerabilities for initial access, preference for data exfiltration over file encryption, use of MegaSync file-sharing application

Operation Time Window: Since April 13th

Source: https://www.bleepingcomputer.com/news/security/microsoft-clop-and-lockbit-ransomware-behind-papercut-server-hacks/





Report 36

Summary: The threat actor known as FIN11 exploited a zero-day vulnerability in the SysAid service management software to deploy Clop ransomware, targeting corporate servers for data theft. The vulnerability, identified as CVE-2023-47246, was used to upload a webshell and execute PowerShell scripts to load the GraceWire malware. The threat actor, tracked as Lace Tempest by Microsoft, deployed additional scripts to erase activity logs and fetch a Cobalt Strike listener on compromised hosts. SysAid quickly developed a patch for the vulnerability and advised users to update to version 23.3.36 or later. The report provides indicators of compromise to detect or prevent the intrusion, including filenames, hashes, IP addresses, and attacker commands. The operation took place on November 2, 2023.





Report 37

Summary:
The threat actor known as Clop gang targeted multiple organizations, including accounting giant Deloitte, Chuck E. Cheese, government contractor Maximus, and the Hallmark Channel, compromising them via the MOVEit vulnerability. The gang accessed the personal information of 8 to 11 million individuals, including social security numbers and protected health information. The victims' list includes 514 organizations and over 36 million individuals. Progress Software, the maker of MOVEit, faced multiple class-action lawsuits. The threat actor used novel tactics, including exploiting vulnerabilities in the MOVEit file transfer suite. The incident occurred on July 27, 2023, and ongoing investigations are being conducted to assess the full impact and costs of the attack.





Report 38

Summary:
- Threat actor: FIN11
- Region: Missouri, USA
- Operating sector: Healthcare
- Type of company: IBM MOVEit data breach
- Date: May 27, 2023
- Evidence of capability: Clop ransomware gang conducted the attack using a zero-day vulnerability (CVE-2023-34362).
- Novelty of tools and techniques: Stole data from over 600 companies worldwide, including healthcare information related to Medicaid services in Missouri.
- Expected profit: $75-100 million from the attacks.
- Impact: Exposed protected health information for Medicaid participants in Missouri, including names, dates of birth, and medical claims information. Only two social security numbers were exposed.
- Recommendations: Freeze credit and monitor credit reports for unusual activity.





Report 39

Malformed report.





Report 40

Summary: The threat actor FIN11 breached the New Zealand Reserve Bank by exploiting a critical vulnerability in the Accellion FTA file sharing service, which was patched on December 24th, 2020. The breach occurred on December 25th, 2020, indicating a short timeframe between the patch release and the attack. The attackers targeted sensitive information stored on the file sharing service. The use of a zero-day vulnerability and the quick deployment of a patch by the threat actor demonstrate their capability and sophistication. The victims targeted were in the financial sector, specifically the Reserve Bank of New Zealand. The threat actor's use of novel tools and techniques, along with the timing of the attack during the Christmas holiday, added complexity to the incident.





Report 41

Malformed report





Report 42

Summary: Procter & Gamble confirmed a data breach via a zero-day exploit on their GoAnywhere MFT platform in early February 2023. The breach was part of a series of attacks by the Clop ransomware gang targeting Fortra GoAnywhere secure storage servers globally. The threat actors stole data from over 130 organizations using the CVE-2023-0669 vulnerability as a zero-day exploit. The victims included companies like Community Health Systems, Hatch Bank, Rubrik, and Saks Fifth Avenue. Clop threatened to publish stolen documents online if victims did not negotiate ransom payments. This incident is similar to the 2020 Accellion breaches where Clop demanded ransoms from high-profile companies. The threat actor's capability to exploit zero-day vulnerabilities and extort organizations demonstrates their advanced tactics and techniques. The operation time window for the attacks and extortion began in early February and continued through March 2023.





Report 43

Summary:
- Threat actor FIN11 has been exploiting a vulnerability in the MOVEit file transfer tool, affecting over 250 organizations, including Radisson Hotels and major insurance companies.
- Radisson Hotels confirmed that guest records were accessed in the data breach, with an ongoing investigation to identify affected guests.
- American National Insurance Company and Sun Life also confirmed data breaches due to the MOVEit vulnerability.
- The Clop ransomware group has been identified as the primary hacker group exploiting the vulnerability.
- Multiple schools, banks, and companies worldwide have been affected, with at least 17.7 million people's information exposed.
- The University of Illinois and University of Louisville are among the educational institutions impacted by the breach.
- The federal government warned of three new vulnerabilities in the MOVEit software, marking the fourth, fifth, and sixth issues found since the fiasco began in May 2023.
- The threat actor's capability is evidenced by the widespread impact on various sectors, including hospitality, insurance, and education, using novel techniques to exploit vulnerabilities in the software.





Report 44

Summary: The threat actor FIN11, associated with the Clop ransomware gang, targeted Stanford Medicine, University of Maryland Baltimore, and University of California by leaking personal and financial information obtained through hacking the universities' Accellion File Transfer Appliance software. The attack involved exploiting a vulnerability in the file-sharing service to access sensitive data. The threat actor has been leaking stolen files since February, coercing victims to pay ransoms. The attack has also impacted other universities, government agencies, and private companies, with evidence linking the operation to the FIN11 cybercrime group. Multiple data breaches have occurred after the threat actors compromised Accellion FTA servers, leading to a joint security advisory by Five Eyes members. The attack on Brown University resulted in system shutdowns. The threat actor's capability is demonstrated through the novel use of exploiting Accellion FTA vulnerabilities for data exfiltration. 

Date: April 3, 2021

Region: Global

Operating Sector: Education, Healthcare

Type of Company: Universities

Evidence of Capability: Exploiting Accellion FTA vulnerabilities for data exfiltration

Novelty of Tools and Techniques: Exploiting Accellion FTA vulnerabilities for data exfiltration

Malformed report





Report 45

Summary: The threat actor known as FIN11 targeted universities in Colorado and Miami, leaking data stolen from Accellion FTA servers starting in December. The ransomware gang demanded $10 million in bitcoin from the organizations to prevent the publication of the stolen data. The threat actor exploited vulnerabilities in Accellion FTA servers to access sensitive information, including student grades, academic records, and patient data. The University of Colorado and University of Miami were among the victims, with the University of Miami confirming a data security incident involving Accellion. The threat actor, Clop ransomware operation, used novel techniques to extort victims, including leaking screenshots of stolen data to pressure them into paying the ransom. The threat actor has targeted other organizations, including supermarket giant Kroger and the Reserve Bank of New Zealand, using similar tactics. The operation time window for this activity was from December to March 2021.





Report 46

Summary:
The threat actor known as "Clop" is a ransomware gang that is pressuring victims by emailing their customers and asking them to demand a ransom payment to protect their privacy. This tactic involves stealing unencrypted data before encrypting a victim's network and using it in a double-extortion strategy. Clop has targeted various victims, including jet maker Bombardier, Flagstar Bank customers, and an online maternity clothing store. The threat actor sends threatening emails to customers, stating that their personal data will be published if the ransom is not paid. This novel approach of involving customers in the ransom demand process demonstrates the increasing pressure ransomware gangs are applying to victims. The report does not specify the region, operating sector, or type of company targeted by Clop. The report was published on March 26, 2021, by Lawrence Abrams on BleepingComputer.





Report 47

Summary:
In August 2022, the Cl0p ransomware group targeted South Staffordshire Water, a British water company, potentially stealing customer bank details. The incident did not impact water supply but led to disruptions in the corporate network. The stolen data included customer names, addresses, and bank details used for direct debit payments. The company is working with forensic experts to investigate the breach and has notified regulatory bodies. The attack was part of a series of ransomware incidents in the UK, prompting government officials to assess risks to critical services. The Cl0p group demanded an extortion payment to prevent data release and disclosed network access methods. Law firm Hayes Connor is assisting affected employees in potential claims related to the breach.





Report 48

Summary: The threat actor known as FIN11 has targeted universities in Maryland and California in new data leaks. The victims were in the education sector, specifically universities. The attack occurred in 2024. FIN11 demonstrated their capability by using ransomware to target these institutions, indicating a high level of sophistication. The tools and techniques used by FIN11 were novel and effective, leading to successful data leaks. The threat actor's focus on universities suggests a strategic targeting of organizations with valuable data.





Report 49

Summary:
- Threat actor: FIN11
- Date: July 6, 2023
- Region: Global
- Operating sector: Oil and gas
- Type of company: Multinational oil and gas company (Shell)
- Evidence of capability: Cl0p ransomware group targeted Shell using MOVEit managed file transfer (MFT) to steal data, impacting hundreds of organizations and millions of individuals.
- Novelty of tools and techniques: Cl0p cybergang used the MOVEit hack to compromise personal information of Shell employees, with the data being published after Shell refused to negotiate.
- No evidence of impact on other Shell IT systems.
- Cl0p group has targeted US federal government agencies as well.
- Shell confirmed the hack after data was published by the threat actor.





Report 50

Summary: The threat actor known as FIN11 targeted Shutterfly, an online retail and photography manufacturing platform, with Clop ransomware. The attack exploited a vulnerability in the MOVEit File Transfer utility to breach companies and attempt extortion. Shutterfly confirmed the attack but stated that customer and employee data remained safe. The threat actor demanded a ransom, but the company did not disclose the amount. The novel aspect of this attack was the exploitation of the MOVEit vulnerability, impacting multiple organizations, including Shell, Deutsche Bank, and various universities and government entities. The U.S. Cybersecurity and Infrastructure Security Agency also reported breaches in federal agencies. The threat actor's capability was demonstrated through the successful exploitation of vulnerabilities and targeting of high-profile organizations. Date: July 14, 2023.





Report 51

Siemens Energy confirmed a data breach after a MOVEit data-theft attack by the threat actor FIN11 on June 27, 2023. The attack targeted Siemens Energy, a Munich-based energy technology company with a global presence, and Schneider Electric, a French multinational company specializing in digital automation and energy management. The threat actor utilized a zero-day vulnerability in the MOVEit Transfer platform, tracked as CVE-2023-34362. The attack resulted in data theft, with Clop listing both companies on their data leak site. The attacks have impacted various companies, federal government agencies, and local state agencies, leading to widespread data breaches. The threat actor's capability is evidenced by the novel use of zero-day vulnerabilities and the targeting of high-profile companies in the energy and automation sectors.





Report 52

Singtel and QIMR Berghofer Medical Research Institute reported data breaches caused by a vulnerability in Accellion FTA software, impacting government agencies, educational institutions, and companies. Singtel, a telecommunications company in Singapore, and QIMR Berghofer, a medical research institute, were targeted. The threat actor exploited a zero-day vulnerability in Accellion FTA, gaining unauthorized access to data. Singtel is investigating the breach's impact and has taken the FTA system offline. QIMR Berghofer disclosed that de-identified data on clinical trials and employee resumes were accessed. The breach occurred on December 25, 2020, with Accellion notifying them on February 2, 2021. The threat actor's capability to exploit novel vulnerabilities in widely-used software is evident in this incident. Date: December 25, 2020 - February 2, 2021.





Report 53

Summary: The threat actor known as FIN11 targeted the German enterprise software giant Software AG with Clop ransomware, demanding a $23 million ransom after stealing employee information and company documents. Software AG, with over 5,000 employees and operations in 70 countries, serves customers in various sectors including government, banking, transportation, insurance, and retail. Evidence suggests that data was downloaded from Software AG's servers and employee notebooks, with the threat actor threatening to publish stolen information if the ransom is not paid. The attack affected Software AG's internal network, leading to the shutdown of internal systems, while customer cloud services remained unaffected. The use of Clop ransomware and the demand for a significant ransom amount demonstrate the capability and sophistication of the threat actor. The attack occurred on October 3, 2020, with ongoing efforts to restore systems and data for orderly operation.





Report 54

Summary: Sony confirmed a data breach impacting thousands in the U.S. due to a zero-day vulnerability in the MOVEit Transfer platform exploited by the Clop ransomware gang. The breach occurred on May 28, 2023, and was discovered in early June. Personal information of 6,791 individuals in the U.S. was compromised. Sony offered credit monitoring and identity restoration services to the affected individuals. The threat actor targeted Sony Group and accessed sensitive information. The breach was limited to the software platform and did not impact other systems. Sony suffered two security breaches in the past four months, with the latest incident involving a server in Japan used for internal testing. The threat actor used novel techniques to exploit the zero-day vulnerability and gain unauthorized access to personal information. 

Date: May 28, 2023

Region: U.S.

Operating Sector: Technology

Type of Company: Sony Interactive Entertainment

Evidence of Capability: Exploitation of zero-day vulnerability, compromise of personal information, targeted attack on specific software platform.





Report 55

Summary:
The threat actor "FIN11," also known as TA505, was behind a ransomware attack on Maastricht University in the Netherlands on December 23, 2019. The university paid a 30 bitcoin ransom to decrypt critical systems affected by the attack. TA505 is a financially motivated hacker group known for targeting retail companies and financial institutions since at least Q3 2014. They used remote access Trojans and malware downloaders to deliver ransomware strains like Locky, BitPaymer, and Clop. The attackers gained access to the university's systems through phishing emails and deployed the Clop ransomware on 267 Windows systems. The university paid the ransom to avoid data loss and downtime, restoring encrypted files. The incident was investigated by security company Fox-IT, and the university continues to assess the impact of the attack on its data. The decision to pay the ransom was made to protect the interests of students and staff, allowing teaching and exams to proceed as planned.





Report 56

Summary:
- Threat actor: Clop ransomware group
- Region: Tasmania, Australia
- Operating sector: Government, Department for Education, Children and Young People
- Date: March 27, 2023
- Evidence: 16,000 sensitive documents leaked, including financial data, names, addresses, and bank account numbers
- Novelty: Exploited vulnerability CVE-2023-0669 affecting Fortra's GoAnywhere managed file transfer product
- Capability: Attacked over 130 organizations, slowly adding victims to their list
- Response: Emergency management arrangements activated, investigation ongoing
- Impact: Local political scandal, opposition criticizing government's handling of the incident
- Additional: Clop spent four days in the government's network, more documents likely to be released, hotline set up for concerned parents

Overall, the Clop ransomware group targeted government officials in Tasmania, leaking sensitive documents and financial data through a third-party file transfer service. The group exploited a vulnerability affecting Fortra's GoAnywhere product, impacting multiple organizations globally. The incident has sparked a local political scandal, with the opposition criticizing the government's response. The threat actor's capability and persistence in targeting organizations indicate a significant threat to data security.





Report 57

Malformed report.





Report 58

Malformed report.





Report 59

Summary: 
In October 2023, the threat actor FIN11 targeted Flagstar Bank, affecting 800,000 customers in the United States. The breach was facilitated through a third-party service provider, Fiserv, which was compromised in the CLOP MOVEit Transfer data theft attacks. The threat actor exploited a zero-day vulnerability in the MOVEit Transfer product to access Fiserv's systems and steal customer data. This incident marks the third breach for Flagstar since 2021, with previous breaches exposing sensitive information such as names and Social Security Numbers. The novelty of the tools and techniques used by the threat actor lies in the exploitation of zero-day vulnerabilities and targeting financial institutions through third-party service providers.





Report 60

Summary:
- Threat actor: FIN11
- Region: UK
- Operating sector: Financial
- Type of company: UK Pension Protection Fund, City of Toronto, British multinational Virgin, Hitachi, Investissement Québec, Rio Tinto, Rubrik, health providers in the U.S., Hatch Bank
- Date: March 24th, 2023
- Evidence of capability: Clop ransomware group accessed data of more than three dozen victims through a vulnerability in GoAnywhere (CVE-2023-0669), affecting various organizations including the UK Pension Protection Fund.
- Novelty of tools and techniques: Clop used the same tactic of exploiting vulnerabilities in third-party software (GoAnywhere) as in previous attacks on Accellion's File Transfer Appliance, showcasing a pattern of mass-hacking using new web shells.
- No negotiations with the criminal group were reported, and affected individuals were offered support and monitoring services.
- The Information Commissioner's Office provided data protection advice and recommendations to the PPF.
- The PPF assured that no data of current members and levy payers was involved in the breach.
- Threat intelligence analyst noted the historical pattern of Clop's mass-hacking activities.





Report 61

Summary:
- Threat actor: Clop ransomware gang
- Region: USA
- Operating sector: Government contractor (Serco Inc)
- Date: May 27th onwards
- Evidence of capability: Exploited zero-day vulnerability in MOVEit Transfer platform
- Novel tools and techniques: Large-scale data-theft campaign, high ransom demands
- Victims: Serco Inc (personal information of over 10,000 individuals compromised), U.S. federal agencies, U.S. Department of Energy entities
- Collaboration with CBIZ for investigation and security measures implementation
- Estimated ransom earnings: $75-100 million
- U.S. Cybersecurity and Infrastructure Security Agency (CISA) involvement in response.





Report 62

Summary: Welltok, a healthcare SaaS provider in the U.S., experienced a data breach exposing the personal data of 8.5 million patients after a file transfer program was hacked by the Clop ransomware gang. The breach occurred on July 26, 2023, impacting various healthcare providers across states like Minnesota, Alabama, and Massachusetts. Patient data including names, addresses, and Social Security Numbers was compromised. This breach is notable for being the second largest MOVEit data breach, showcasing the threat actor's capability to exploit zero-day vulnerabilities and target healthcare organizations. The tools and techniques used by the threat actor demonstrate a level of sophistication in targeting sensitive data in the healthcare sector. Date: July 26, 2023.





Report 63

Malformed report


