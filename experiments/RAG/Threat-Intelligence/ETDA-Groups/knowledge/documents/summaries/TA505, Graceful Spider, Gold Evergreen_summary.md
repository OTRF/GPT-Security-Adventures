
Report 1

Summary: The threat actor TA505, also known as Graceful Spider or Gold Evergreen, has been utilizing Excel 4.0 macro to target financial institutions recently. The report does not specify a particular region or operating sector of the victims targeted. The evidence of the threat actor's capability lies in their use of novel techniques such as Excel 4.0 macro, which is a less common method in cyber attacks. The report does not provide a specific date or operation time window for the attacks. 

################## 

Malformed report.





Report 2

The threat actor known as GOLD EVERGREEN, formerly part of the Rock Phish and Avalanche threat groups, is an Eastern European group involved in financially motivated electronic crime. They have shown a high level of organization and sophistication, with the ability to steal significant amounts of money. The threat actors have been active for over 15 years and have used various malware families to achieve their goals. They have demonstrated adaptability to enhanced fraud controls and infrastructure takedowns, showcasing resourcefulness and resilience. The threat actor has been involved in large-scale phishing campaigns, ACH fraud, and the use of malware such as Zeus, Jabberzeus, Gameover Zeus, Dyre, and Bugat v5/Dridex. They have also been involved in operations such as Operation Trident breACH and Operation Tovar. The threat actor has targeted financial institutions, business banking, wealth management, and payroll systems, focusing on areas with large amounts of money protected by less sophisticated fraud controls. Despite multiple arrests and indictments, the threat actor continues to pose a major threat to global economies. The group is likely operating in a limited capacity as of the latest publication.





Report 3

Summary:
TA505, also known as Graceful Spider or Gold Evergreen, conducted an explosive MirrorBlast campaign targeting financial companies. The campaign involved phishing emails with weaponized Excel documents that had low detections on VirusTotal due to lightweight macros. The attack chain targeted financial organizations in regions like Canada, the United States, Hong Kong, and Europe. The threat actor used novel techniques like Google feedproxy URLs with SharePoint and OneDrive lures to evade detection. The campaign showed similarities to TA505's tactics, techniques, and procedures, indicating a financial motivation. The threat actor utilized JScript, MSI packages, and Rebol/KiXtart variants to exfiltrate data and establish persistence. The attack chain was attributed to TA505 based on infection chain, domain names, and previous intrusion details. The campaign highlights the need for organizations to remain vigilant and adapt security procedures to combat evolving threats. The report was published on October 14, 2021, by Morphisec Labs.





Report 4

Summary:
TA505, a threat actor, has been distributing a new SDBbot Remote Access Trojan with the Get2 downloader since September 2019. The campaigns have targeted financial institutions in Greece, Singapore, United Arab Emirates, Georgia, Sweden, Lithuania, and other countries. TA505 has been observed using new Microsoft Office macros specifically with the Get2 downloader. The Get2 downloader, written in C++, collects system information and communicates with a hardcoded command and control server. The SDBbot RAT, also written in C++, has an installer, loader, and RAT component, utilizing application shimming for persistence. The SDBbot communicates with a C&C server over TCP port 443. The campaigns have shown innovation in targeting, volume of emails distributed, and use of new malware. The latest campaign observed on October 7, 2019, saw the Get2 downloader downloading the SDBbot RAT for the first time. TA505 remains a significant threat actor in the cybersecurity landscape.





Report 5

Summary:
The threat actor known as "Evil Corp" orchestrated a cybercrime network that stole approximately $100 million from businesses and consumers. The primary suspect, Maksim V. Yakubets, led an elite cybercrime ring using advanced malware strains like "JabberZeus" and "Bugat" to steal banking credentials. The threat actor recruited money mules to launder stolen funds and transfer them to accomplices in Eastern Europe. Evidence suggests Yakubets was associated with Russian cybercriminals and had ties to the Russian FSB. The U.S. Treasury Department imposed economic sanctions on Yakubets and his associates. The Justice Department disrupted money mule networks linked to cybercrime activities. The threat actor's operations spanned from Hawaii to Florida and from Alaska to Maine. Despite the identification of the threat actor, extradition challenges and Russian government involvement hinder law enforcement efforts. The threat actor's activities were closely monitored by security researchers, leading to warnings to victim companies and interactions with law enforcement agencies. The threat actor's use of sophisticated tools and techniques, along with their association with Russian intelligence, highlight the complexity and challenges in combating cybercrime.





Report 6

Summary: Microsoft detected a new TA505 malware campaign in January 2020, marking the threat actor's return after a short break. TA505, also known as SectorJ04, is a financially motivated cybercrime group targeting retail companies and financial institutions. The threat actor used HTML redirectors in phishing emails to deliver malicious Excel documents containing a macro-laden payload. This technique was a novelty for TA505. The malware distributed by TA505 included remote access Trojans and banking Trojans as secondary payloads. The attackers used localized HTML files in different languages and an IP traceback service to track victims globally. The malware dropped a remote access trojan known as GraceWire or FlawedGrace. The campaign also included indicators of compromise (IOCs) provided by Microsoft Security Intelligence. The report did not specify the region, operating sector, or type of company targeted by the threat actor.





Report 7

Malformed report





Report 8

Summary: TA505, also known as Graceful Spider or Gold Evergreen, has been identified as a threat actor exploiting the ZeroLogon vulnerability in attacks. The threat actor has a history dating back to 2014, initially distributing the Dridex banking trojan. TA505 has evolved to deploy a variety of malware, including ransomware like Clop. Recently, the group has been using fake software updates to gain increased privileges on target systems and run malicious scripts. They have also been observed using the Mimikatz post-exploitation tool with exploit code for ZeroLogon. The ZeroLogon vulnerability allows attackers to escalate permissions to administrator level without authentication. Microsoft has issued warnings about the severity of the vulnerability and urged organizations to apply security patches. The threat actor's adoption of ZeroLogon indicates a shift towards targeting organizations in both public and private sectors with increased frequency. The report was published on October 9, 2020.





Report 9

Malformed report





Report 10

Summary:
During January 2020, FireEye observed targeted phishing campaigns by threat actor TA505, also known as Graceful Spider or Gold Evergreen, primarily targeting financial services organizations in the United States, with some campaigns targeting South Korean organizations, including a marketing agency. The phishing documents used uncommon and misunderstood techniques to decrease detection, such as VBA stomping and hiding macros from the Office GUI. The threat actor leveraged a self-hosted email marketing solution called Acelle across multiple campaigns. The payload delivered in these campaigns was a backdoor known as MINEBRIDGE, a C++ backdoor designed to be loaded by an older, unpatched instance of TeamViewer by DLL load-order hijacking. The threat actor's unique tradecraft, targeting financial sectors exclusively, and the novelty of the tools and techniques used, such as VBA stomping, indicate a high level of sophistication. The report also suggests a potential connection to another intrusion set, but the limited overlap in tactics and procedures between campaigns delivering MINEBRIDGE and those delivering FRIENDSPEAK may suggest that MINEDOOR is not exclusive to TA505. FireEye has not observed any instances of successful compromise by MINEBRIDGE, but the threat actor's capabilities and novel techniques pose a significant risk to targeted organizations. The report provides detailed indicators of compromise (IOCs) and insights into the threat actor's operations. The operation time window for these campaigns was from January 7, 2020, to January 28, 2020.





Report 11

TA505, a threat actor known as Graceful Spider or Gold Evergreen, has been observed distributing new malware named ServHelper and FlawedGrace. The ServHelper malware has two variants, one focused on remote desktop functions and the other primarily functioning as a downloader. FlawedGrace, a full-featured RAT, was observed being downloaded by the ServHelper malware. TA505 has been actively targeting banks, retail businesses, and restaurants with these malware families. The ServHelper malware uses HTTP C&C protocol on ports 443 and 80, with newer versions supporting ".bit" C&C domains. FlawedGrace, written in C++, uses a complicated binary protocol for C&C communication on port 443. The threat actor TA505's distribution of these malware variants indicates a long-term investment in malicious activities. The campaigns were observed in November and December 2018, targeting financial institutions, retail, and financial services customers. The evidence of the capability of the threat actor lies in the development and distribution of these new malware variants, showcasing novel tools and techniques. The report provides indicators of compromise and Suricata/Snort signatures for detection. The information was published on January 9, 2019, by Proofpoint US.





Report 12

Summary:
The threat actor known as TA505, also referred to as Graceful Spider and Gold Evergreen, has been active since 2006 and is primarily motivated by financial gain. Operating out of Russia, TA505 has targeted victims in various sectors worldwide, including education, financial, healthcare, hospitality, and retail. The group is known for distributing a wide range of malware, including Dridex, Locky ransomware, and Jaff ransomware, through massive spam campaigns. TA505 has been observed using novel tools and techniques such as embedding SettingContent-ms files in PDFs, introducing new downloader malware like Get2, and targeting specific industries with personalized attachments. The threat actor has also been linked to other groups like Buhtrap and Ratopak Spider, indicating a complex network of cybercriminal activity. TA505's continuous evolution and experimentation with different malware tools demonstrate their adaptability and persistence in carrying out cyber attacks. The group has been the target of various counter operations over the years, including arrests related to cyber-theft and efforts to disrupt their activities. TA505's recent exploits include leveraging the SolarWinds Serv-U vulnerability for initial access, showcasing their ongoing threat to organizations globally.





Report 13

Summary:
The threat actor TA505, also known as Graceful Spider or Gold Evergreen, is a sophisticated and versatile cybercrime group that targets multiple sectors and geographies for financial gain. They have evolved from relying on third-party services to operating independently in their fraudulent activities. TA505 primarily uses the Clop ransomware strain to encrypt corporate networks and demand ransom in Bitcoin. They heavily rely on malware like Get2/GetandGo and SDBbot to gain access to targeted networks. TA505 has been involved in high-profile incidents, such as the Maastricht University attack in the Netherlands in December 2019. The threat actor employs novel techniques, including a custom packer and multiple layers of encryption, to evade detection and protect their malicious code. Their working schedule suggests a well-organized group operating in Eastern Europe, possibly Ukraine. TA505 poses a significant threat to organizations worldwide, demonstrating high capability and motivation in their criminal activities. The report covers activities from March to June 2020, highlighting the group's evolving tactics and targets.





Report 14

Summary:
- Threat actor: TA505, also known as Graceful Spider and Gold Evergreen.
- Region: Global, with specific targeting of German-speaking countries like Germany and Austria.
- Operating sector: Various industries targeted by malicious email campaigns.
- Capability: TA505 has returned with new tools including KiXtart Loader, MirrorBlast loader, and an updated FlawedGrace variant.
- Novelty: The threat actor has evolved its tactics by using Rebol and KiXtart scripting languages for intermediate loaders, moving away from the previously popular Get2 downloader.
- Date: Campaigns observed since early September 2021, with a significant increase in activity in late September and October 2021.
- Evidence: Similarities in domain naming conventions, email lures, and delivery of FlawedGrace RAT indicate a high confidence attribution to TA505.
- Outlook: TA505 is financially motivated and adaptable, posing a continued threat with the potential for further adjustments in operations and methods.
- Indicators of Compromise: Various URLs and domains associated with MirrorBlast C&C, MSI downloads, and FlawedGrace RAT payloads.
- Detection rules: EmergingThreats and ETPRO rules for detecting MirrorBlast and FlawedGrace activity.





Report 15

Summary:
TA505, also known as Graceful Spider or Gold Evergreen, has been actively targeting various countries and entities with a combination of techniques using ServHelper and FlawedAmmyy payloads. The threat actor has been observed targeting different regions, including Turkey, Serbia, Romania, Korea, Canada, the Czech Republic, and Hungary, with novel techniques such as using .ISO image attachments for entry. TA505 has also been using a newer version of ServHelper, a .NET downloader, and a .DLL variant of FlawedAmmyy downloader in their campaigns. The threat actor has shown capability in evading detection and continuously upgrading their malware to maximize profits. The group has been experimenting with different delivery methods and obfuscation techniques to bypass security measures. Enterprises are advised to strengthen their defenses against phishing and social engineering attacks, as TA505 continues to pose a threat to businesses across various sectors.





Report 16

Summary:
TA505, also known as Hive0065, a financially motivated cybercrime group, continues to target various industries, including finance, retail, and restaurants, since at least 2014. They primarily conduct malicious spam campaigns delivering a wide range of custom and open-source malware, including banking Trojans, ransomware, and extortion schemes. The group has been observed spreading the SDBbot remote-access Trojan (RAT) since at least September 2019, using it primarily as a secondary payload. The threat actor employs sophisticated tactics, techniques, and procedures (TTPs) such as spear phishing emails impersonating legitimate cloud-based applications to deliver malware. They have also exploited the COVID-19 pandemic to deliver ransomware and banking Trojans. The group's arsenal includes tools like VSPUB DLLs with CobaltStrike code similarities, Meterpreter reverse shells, and SDBbot RAT components. The threat actor's continued malicious activity and evolving TTPs indicate a persistent threat to a wide range of industries, with a focus on social engineering and malware delivery. The report provides indicators of compromise (IoCs) to help organizations detect and respond to TA505's activities. The information is based on research conducted by IBM X-Force Incident Response and Intelligence Services (IRIS) and was published on April 14, 2020, by Melissa Frydrych.





Report 17

Summary:
TA505, also known as Graceful Spider or Gold Evergreen, has recently debuted a new backdoor named ServHelper targeting banks, retailers, and restaurants in the U.S. The threat actor has developed two variants of ServHelper, one focusing on remote desktop functions and the other as a downloader for a RAT called FlawedGrace. Evidence suggests that TA505 is actively targeting financial institutions and retail businesses with these malware families. The novelty of the tools and techniques used by TA505 includes the development of ServHelper with new commands and functionality in almost every new campaign, indicating ongoing development and long-term investment by the threat actor. The capability of TA505 to distribute new malware variants consistently and prolifically, as well as their history of distributing hundreds of millions of malicious messages worldwide, highlights the persistent threat posed by this organized cybercrime ring. The report was published on January 11, 2019, by Threatpost.





Report 18

Summary:
TA505, also known as Graceful Spider or Gold Evergreen, has been targeting financial institutions and retail companies in Latin America, East Asia, and Europe. They have been using HTML attachments to deliver malicious .XLS files leading to downloader and backdoor FlawedAmmyy, primarily targeting users in South Korea. TA505 has been updating their tactics by using legitimate or compromised RATs like FlawedAmmyy, FlawedGrace, and Remote Manipulator System (RMS). They have been using novel techniques like abusing Excel 4.0 macros, MSI Installer payloads, and legitimate software to evade detection. The group has also been observed using EmailStealer, VBA macros, and HTML links in emails to distribute malware. Suspicious activity resembling TA505's TTPs has been detected, involving Kronos and SmokeLoader, but with differences in infrastructure and techniques. Defending against TA505's activities requires regular system updates, multilayered security mechanisms, and secure email gateways. Trend Micro endpoint solutions and Hosted Email Security can help protect against TA505's threats. The report provides indicators of compromise related to this threat.





Report 19

TA505, a threat actor also known as Graceful Spider or Gold Evergreen, initiated summer campaigns in June 2019 targeting victims in the UAE, South Korea, Singapore, and the United States. The threat actor introduced a new downloader malware named AndroMut, which exhibits similarities to the Andromeda malware family. AndroMut is written in C++ and employs advanced techniques such as Windows API hashing, string encryption, and anti-analysis measures to evade detection. TA505 used AndroMut to download the FlawedAmmyy Remote Access Trojan (RAT) in campaigns targeting recipients in South Korea and financial institutions in Singapore, UAE, and the USA. The malware establishes communication with its command and control server using HTTP POST requests and is capable of executing various commands, including self-removal and updating. The AndroMut malware, along with the FlawedAmmyy RAT payload, represents TA505's latest toolset for their malicious activities. The report was published on July 2, 2019, by Proofpoint.





Report 20

Summary:
- Threat actor: TA505, Graceful Spider, Gold Evergreen
- Region: South Korea
- Operating sector: Financial sector, manufacturing, and medical services
- Evidence of capability: TA505 used malicious attachments, ransomware, and a remote access trojan (FlawedAmmyy) to target victims in South Korea. They have been active since at least 2014 and share tools with FIN7.
- Novelty of tools and techniques: TA505 used a ransomware strain called Rapid, a new technique for the group, and targeted victims with phishing emails containing malicious Microsoft Excel documents.
- Operation time window: Throughout 2019
- Source: https://www.cyberscoop.com/ta505-south-korea-bank-phishing/





Report 21

Summary:
- Threat actor: TA505, also known as Graceful Spider or Gold Evergreen
- Region: Italy
- Operating sector: Banking and Retail, potential expansion to other industries
- Date: 05/29/2019
- Evidence of capability: Highly obfuscated macro code, use of SFX archives, remote administration tool for complete access
- Novelty of tools and techniques: Use of junk instructions in macro code, self-extracting archives, remote administration tool for control
- Targeted victims: Italian organization, unspecified US retail company
- Tools used: "rtegre.exe", "wprgxyeqd79.exe", "uninstall.exe", "winserv.exe"
- C2 server: Hosted in Bulgaria, part of AS-21100 operated by ITL LLC
- Indicators of Compromise: Dropurl, C2, Persistence, Hash values
- Yara rules for detection: Excel dropper, SFX archives, backdoor, trojan
- Conclusion: TA505 group expanding operations beyond traditional sectors, active since 2014
- Ongoing campaign: "veter1605_MAPS_10cr0.exe" with changing variations
- Comparison with previous attack campaigns: Similarities in deployment of remote administration tool, reuse of code components, introduction of new components
- Threat actor's history: Active since 2014, targeting high profile companies globally
- Indicators of compromise: Dropurl, C2, Persistence, Hash values
- Yara rules for detection: Excel dropper, SFX archives, backdoor, trojan
- Conclusion: TA505 group expanding operations beyond traditional sectors, active since 2014
- Ongoing campaign: "veter1605_MAPS_10cr0.exe" with changing variations
- Comparison with previous attack campaigns: Similarities in deployment of remote administration tool, reuse of code components, introduction of new components
- Threat actor's history: Active since 2014, targeting high profile companies globally.





Report 22

Summary:
The threat actor TA505, also known as Graceful Spider or Gold Evergreen, has been active since at least 2016, primarily targeting organizations with financially motivated malicious spam campaigns. They have distributed a variety of payloads, including Locky ransomware, The Trick banking Trojan, GlobeImposter ransomware, and FlawedAmmyy remote access Trojan. TA505 has shown adaptability by exploring new malicious attachments and techniques, such as using VBScript files compressed in 7-Zip archives, abusing Dynamic Data Exchange (DDE) in Microsoft Word attachments, and distributing malware via BlackTDS. They have also geo-targeted campaigns and experimented with new vectors like .iqy attachments to download malware. Despite fluctuations in campaign frequency and volume, TA505 remains a significant threat actor in the email threat landscape, constantly evolving to bypass defenses and deliver various payloads at scale. The latest activity from TA505 includes the distribution of FlawedAmmyy RAT through Zip archives containing ".url" files. Their willingness to explore new techniques and payloads, even without access to the Necurs spam cannon, demonstrates their adaptability and persistence in the cyber threat landscape. The report covers TA505's activities from September 2017 to June 2018, showcasing their history of introducing major malware strains and their ongoing evolution in tactics and techniques. The threat actor's capability to distribute a wide range of malware and their experimentation with new delivery methods highlight the need for organizations to remain vigilant against their evolving threats.





Report 23

TA505, also known as Graceful Spider or Gold Evergreen, targeted the US retail industry with personalized attachments starting from November 15, 2018. The threat actor aimed at large retail chains, restaurant chains, and grocery chains, as well as other organizations in the food and beverage industries. The use of personalized attachments in moderately large campaigns combined with retail industry targeting was observed just in time for the holiday shopping season. TA505 utilized various malware families, including Remote Manipulator System (RMS) and FlawedAmmyy, among others, in their campaigns. The actor employed a new tactic of personalizing attachments for each target, a technique not previously used by TA505. The malicious attachments contained the targeted company's logo to make the messages more believable. The document attached to the emails contained macros that, if enabled, downloaded and executed an MSI file leading to the installation of RMS with a custom command and control (C&C) address. The threat actor's change in tactics to focus on downloaders, RATs, information stealers, and banking Trojans in smaller, more targeted campaigns indicates a shift in the threat landscape. TA505 appears poised to take advantage of increased activity in the US retail and grocery sector through the end of the year. The report was published on December 6, 2018, by Proofpoint.





Report 24

Summary:
- Threat actor: TA505, Graceful Spider, Gold Evergreen
- Region: Global targeting, with specific focus on Banking sector
- Operating sector: Banking and Retail companies
- Date: 05/16/2019
- Evidence of capability: TA505 group used evasive techniques like LOLBins and cryptographically signed payloads to penetrate corporate perimeters
- Novelty of tools and techniques: Deployed a credential stealing software as part of their arsenal, with a high level of protection against antivirus detection and no encryption in data communication
- Malware analysis: Email stealer malware aimed at retrieving email and password accounts, with a focus on Outlook and Thunderbird clients
- Indicators of Compromise: Dropurl, C2 servers, and hash values provided for identification
- Conclusion: Email accounts can be a source of revenue for cybercriminals, with potential for spreading malware, BEC attacks, and credential stuffing
- Yara Rules and Searched Extensions provided for further analysis and detection of the threat actor's activities.





Report 25

Summary:
The threat actor TA505, also known as Graceful Spider or Gold Evergreen, has been tracked by Proofpoint researchers for their involvement in financially motivated cybercrime. They are responsible for distributing a wide range of malware, including Dridex, Locky ransomware, Jaff ransomware, The Trick banking Trojan, and GlobeImposter ransomware. TA505 is known for conducting massive spam campaigns using the Necurs botnet, with disruptions to Necurs leading to quiet periods in their activities. They have shown adaptability by shifting techniques and malware frequently, while consistently operating at a massive scale. TA505's history and operations provide insights into the framework employed by modern threat actors, focusing on the actor, vector, hoster, payload, and C&C elements. Despite occasional disruptions, TA505 is expected to continue driving malicious email campaigns in the future. The report covers the period from 2014 to September 2017 and provides detailed information on the malware strains distributed by TA505, their distribution methods, and campaign attributes.

Region: Global
Operating Sector: Cybersecurity
Type of Company of Victims: Various industries targeted through email campaigns

Date: September 27, 2017





Report 26

Summary:
Threat actor TA505, also known as Graceful Spider or Gold Evergreen, targeted financial enterprises in April 2019 using LOLBins and a new backdoor malware called ServHelper. The operation involved a highly targeted phishing campaign, signed and verified malicious code, deliberate timing, selective persistence mechanisms, and extensive use of LOLBins. TA505, known for campaigns like Dridex and Locky ransomware, targeted financial institutions globally, focusing on large organizations to extract valuable data. The ServHelper backdoor, discovered in late 2018, used legitimate Windows OS processes for malicious activities and was signed by Sectigo RSA Code Signing CA for legitimacy. The attack was detected and contained by Cybereason, showcasing the threat actor's advanced capabilities and evasion techniques. The operation highlighted the increasing use of LOLBins and the sophistication of threat actors in evading detection. The attack was thwarted before any damage was done, but the use of signed and verified files increases the likelihood of future undetected attacks.





Report 27

Malformed report





Report 28

Summary:
TA505, a threat actor known for its operations in the financial sector, has been tracked by NCC Group, revealing the development of a P2P network related to the group. The identified binary files, attributed to the developer(s) of 'Grace' (FlawedGrace), include a remote administration tool (RAT) used exclusively by TA505. These binaries are capable of P2P communication via UDP, indicating a connection to the developer(s) of 'Grace'. The threat actor has a history of evolving from banking fraud to ransomware operations, with 'Grace' being repurposed as a tool for fraudulent wire transactions and card data theft. TA505's shift to ransomware operations, including the use of tools like 'Clop' and 'SDBBot', showcases their capability to extort large sums of money from victims. The technical analysis of the identified tool reveals a downloader, signed drivers, and a node tool used for communication and data transfer within the network. The use of unique identifiers, encryption methods, and network communication protocols demonstrate the sophistication and novelty of TA505's tools and techniques. The report provides IoCs including nodes' IPs and binary hashes for detection and mitigation purposes. The operation time window for this report is December 2, 2021.


