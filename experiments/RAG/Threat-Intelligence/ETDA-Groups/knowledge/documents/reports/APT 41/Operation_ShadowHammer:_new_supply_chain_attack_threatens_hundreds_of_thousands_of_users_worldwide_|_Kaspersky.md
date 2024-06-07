# Reference for threat actor for "APT 41"

**Title**: Operation ShadowHammer: new supply chain attack threatens hundreds of thousands of users worldwide | Kaspersky

**Source**: https://www.kaspersky.com/about/press-releases/2019_operation-shadowhammer-new-supply-chain-attack

## Content
Operation ShadowHammer: new supply chain attack threatens hundreds of thousands of users worldwide | KasperskySkip to main contentSolutions for:Home ProductsSmall Business 1-50 employeesMedium Business 51-999 employeesEnterprise 1000+ employeesSolutions for:Home ProductsSmall Business 1-50 employeesMedium Business 51-999 employeesEnterprise 1000+ employeesKaspersky logoAbout UsAbout UsCompanyTeamTransparencyCorporate NewsPress CenterCareersSponsorshipsPolicy BlogPolicy BlogGeneral CybersecurityIndustrial CybersecurityPrivacyCyber InsuranceDigital SkillsHomeAboutCorporate NewsMarch 25, 2019Operation ShadowHammer: new supply chain attack threatens hundreds of thousands of users worldwideKaspersky Lab has uncovered a new advanced persistent threat (APT) campaign that has affected a large number of users through what is known as a supply chain attack. Our research found that threat actors behind Operation ShadowHammer have targeted users of the ASUS Live Update Utility, by injecting a backdoor into it at least between June and November 2018. Kaspersky Lab experts estimate that the attack may have affected more than a million users worldwide.A supply chain attack is one of the most dangerous and effective infection vectors, increasingly exploited in advanced operations over the last few years – as we have seen with ShadowPad or CCleaner. It targets specific weaknesses in the interconnected systems of human, organizational, material, and intellectual resources involved in the product life cycle: from initial development stage through to the end user. While a vendor’s infrastructure can be secure, there could be vulnerabilities in its providers’ facilities that would sabotage the supply chain, leading to a devastating and unexpected data breach.The actors behind ShadowHammer targeted the ASUS Live Update Utility as the initial source of infection. This is a pre-installed utility in most new ASUS computers, for automatic BIOS, UEFI, drivers and applications updates. Using stolen digital certificates used by ASUS to sign legitimate binaries, the attackers have tampered older versions of ASUS software, injecting their own malicious code. Trojanized versions of the utility were signed with legitimate certificates and were hosted on and distributed from official ASUS update servers – which made them mostly invisible to the vast majority of protection solutions.While this means that potentially every user of the affected software could have become a victim, actors behind ShadowHammer were focused on gaining access to several hundreds of users, which they had prior knowledge about. As Kaspersky Lab’s researchers discovered, each backdoor code contained a table of hardcoded MAC addresses – the unique identifier of network adapters used to connect a computer to a network. Once running on a victim’s device, the backdoor verified its MAC address against this table. If the MAC address matched one of the entries, the malware downloaded the next stage of malicious code. Otherwise, the infiltrated updater did not show any network activity, which is why it remained undiscovered for such a long time. In total, security experts were able to identify more than 600 MAC addresses. These were targeted by over 230 unique backdoored samples with different shellcodes.The modular approach and extra precautions taken when executing code, to prevent accidental code or data leakage indicates that it was very important for the actors behind this sophisticated attack to remain undetected, while hitting some very specific targets with surgical precision. Deep technical analysis shows that the arsenal of the attackers is very advanced and reflects a very high level of development within the group.The search for similar malware has revealed software from three other vendors in Asia, all backdoored with very similar methods and techniques. Kaspersky Lab has reported the issue to Asus and other vendors.“The selected vendors are extremely attractive targets for APT groups that might want to take advantage of their vast customer base. It is not yet very clear what the ultimate goal of the attackers was and we are still researching who was behind the attack. However, techniques used to achieve unauthorized code execution, as well as other discovered artefacts suggest that ShadowHammer is probably related to the BARIUM APT, which was previously linked to the ShadowPad and CCleaner incidents, among others. This new campaign is yet another example of how sophisticated and dangerous a smart supply chain attack can be nowadays,” said Vitaly Kamluk, Director of Global Research and Analysis Team, APAC, at Kaspersky Lab.All Kaspersky Lab products successfully detect and block the malware used in Operation ShadowHammer.In order to avoid falling victim to a targeted attack by a known or unknown threat actor, Kaspersky Lab researchers recommend implementing the following measures:In addition to adopting must-have endpoint protection, implement a corporate grade security solution which detects advanced threats on the network level at an early stage, such as Kaspersky Anti Targeted Attack Platform;For endpoint level detection, investigation and timely remediation of incidents, we recommend implementing EDR solutions such as Kaspersky Endpoint Detection and Response or contacting a professional incident response team;Integrate Threat Intelligence feeds into your SIEM and other security controls in order to get access to the most relevant and up-to-date threat data and prepare for future attacks.Kaspersky Lab will present full findings on Operation ShadowHammer at Security Analyst Summit 2019, in Singapore, 9-11 April.A full report on the ShadowHammer campaign is already available to customers of Kaspersky Intelligence Reporting Service.A blog summarizing the attack as well as a special tool designed to validate whether users’ devices were a target can also be found on Securelist. The validation is also available on a separate website.About Kaspersky LabKaspersky Lab is a global cybersecurity company, which has been operating in the market for over 21 years. Kaspersky Lab’s deep threat intelligence and security expertise is constantly transforming into next generation security solutions and services to protect businesses, critical infrastructure, governments and consumers around the globe. The company’s comprehensive security portfolio includes leading endpoint protection and a number of specialized security solutions and services to fight sophisticated and evolving digital threats. Over 400 million users are protected by Kaspersky Lab technologies and we help 270,000 corporate clients protect what matters most to them.Operation ShadowHammer: new supply chain attack threatens hundreds of thousands of users worldwideKasperskyKaspersky Lab has uncovered a new advanced persistent threat (APT) campaign that has affected a large number of users through what is known as a supply chain attack. Our research found that threat actors behind Operation ShadowHammer have targeted users of the ASUS Live Update Utility, by injecting a backdoor into it at least between June and November 2018. Kaspersky Lab experts estimate that the attack may have affected more than a million users worldwide.Related Articles Press ReleasesLaser-focus on business: Kaspersky transforms the United partner programKaspersky has introduced a major update to its United partner program. As the number of its global partners increases, Kaspersky has defined four new specified approaches for those selling, deploying, providing managed services or building solutions with Kaspersky products. To drive this new approach, the partner program, benefits, and motivation have been revised to better align with its partners’ business models.Read More > Updated Antidrone solution from Kaspersky: smarter detection, scaling and customizationAmid a constantly growing civilian drone market, Kaspersky has given its anti-drone solution a major new update. The latest version features improved system scalability, an interface that operates 12 times more quickly, and optimized incident visualization. Kaspersky Antidrone Solution is a comprehensive system that detects, identifies, and neutralizes civil drones that pose a security or physical threat to various settings, including critical infrastructure, public events, and commercial facilities.Read More > Nearly a quarter of online daters experience digital stalkingA new survey, commissioned by Kaspersky of 21000 people worldwide, reveals shocking data about the extent of digital abuse. Read More > Stay in Touch

Home Solutions

Kaspersky Standard
Kaspersky Plus
Kaspersky Premium
Kaspersky Safe Kids
Kaspersky VPN Secure Connection
Kaspersky Password Manager
All Solutions



Small Business Products
(1-50 employees)

Kaspersky Small Office Security
Kaspersky Endpoint Security Cloud
All Products



Medium Business Products
(51-999 employees)

Kaspersky Endpoint Security Cloud
Kaspersky Endpoint Security for Business Select
Kaspersky Endpoint Security for Business Advanced
All Products



Enterprise Solutions
(1000+ employees)

Cybersecurity Services
Threat Management and Defense
Endpoint Security
Hybrid Cloud Security
All Solutions


© 2024 AO Kaspersky LabPrivacy Policy • Online Tracking Opt-Out Guide • Anti-Corruption Policy • License Agreement B2C • License Agreement B2BContact UsAbout UsPartnersBlogResource CenterPress ReleasesSitemapCareersSelect your countryGlobal
Americas

América Latina
Brasil
United States
Canada

Africa

Afrique Francophone
Algérie
Maroc
South Africa
Tunisie

Middle East

Middle East
الشرق الأوسط



Western Europe

Belgique & Luxembourg
Danmark
Deutschland & Schweiz
España
France
Italia & Svizzera
Nederland & België
Norge
Österreich
Portugal
Sverige
Suomi
United Kingdom



Eastern Europe

Česká republika
Magyarország
Polska
România
Srbija
Türkiye
Ελλάδα (Greece)
България (Bulgaria)
Россия и Белару́сь (Russia & Belarus)
Україна (Ukraine)



Asia & Pacific

Australia
India
New Zealand
Việt Nam
ไทย (Thailand)
한국 (Korea)
中国 (China)
香港特別行政區 (Hong Kong SAR)
台灣 (Taiwan)
日本語 (Japan)

For all other countries

Global Website

We use cookies to make your experience of our websites better. By using and further navigating this website you accept this. Detailed information about the use of cookies on this website is available by clicking on more information.Accept and Close