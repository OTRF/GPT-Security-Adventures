
Report 1

The threat actor known as Nefilim targeted MAS Holdings, a Sri Lankan clothing manufacturer that produces lingerie for brands like Beyonce's Ivy Park, Nike, and Victoria's Secret. The cyber extortionists claimed to have stolen 300 GB of private files from MAS Holdings' network and demanded a ransom. They posted some allegedly stolen documents online as evidence, including audit documents featuring worker payroll summaries. The group, Nefilim, specializes in stealing documents from victims and using the threat of posting them online to extort payment. This tactic of weaponizing stolen data is a novel approach, with threats to sell it on the dark web, use it for identity theft, or spear phish customers and business partners. MAS Holdings declined to confirm if their commercial partners were alerted to the breach. The incident was flagged by a senior researcher at cyber security firm Emsisoft, highlighting the risk posed by such ransomware groups. The date of the operation was not specified in the report.





Report 2

Summary: The threat actor "Traveling Spider," identified as the Nefilim ransomware operation, targeted the Dussmann Group, a business giant in Germany, specifically their subsidiary Dresdner Kühlanlagenbau GmbH (DKA). The attack resulted in data being stolen and published on ransomware data leak sites as leverage for ransom payment. The Nefilim operators claimed to have encrypted four domains and stolen approximately 200GB of archives. The attack showcased the threat actor's capability to breach networks and steal sensitive data, with evidence of novel techniques such as leveraging stolen files for extortion. The attack occurred on July 28, 2020, and highlighted the importance of securing remote desktop services and implementing multi-factor authentication to prevent ransomware attacks.





Report 3

Malformed report.





Report 4

Summary:
The threat actor known as "Traveling Spider" has been spreading Nemty ransomware through a fake PayPal site, targeting unsuspecting users. The ransomware was observed as a payload from the RIG exploit kit, indicating a varied distribution strategy. The malicious executable, named 'cashback.exe,' encrypts files on victim hosts, with the ransomware taking approximately seven minutes to complete encryption. The threat actor used homograph domain name spoofing to deceive users, making the fake page appear genuine. Security researcher Vitali Kremez noted that the Nemty ransomware variant is at version 1.4 with minor bug fixes. The ransomware targets computers outside specific countries, encrypting files and deleting shadow copies. The ransom demand is approximately $1,000 in BTC, with the payment portal hosted on the Tor network for anonymity. The threat actor's use of novel techniques, such as homograph attacks and distribution via fake PayPal sites, demonstrates their evolving capabilities. The report was published on September 8, 2019, highlighting the ongoing threat posed by the Traveling Spider threat actor.





Report 5

Summary: Whirlpool, a home appliance giant, was targeted in a Nefilim ransomware attack, with data stolen before encryption. The attack occurred in the first weekend of December, with leaked data including employee-related documents. Whirlpool confirmed the attack and stated that their systems have been fully restored. Nefilim has targeted other large victims in the past, including Orange S.A., Dussman Group, Luxottica, and Toll Group. The threat actor's capability is evidenced by the successful attack on Whirlpool, a company generating approximately $20 billion in revenue for 2019. The use of Nefilim ransomware and data exfiltration techniques demonstrates the novelty of tools and techniques employed by the threat actor. 

Date: December 28, 2020

Region: Global

Operating Sector: Home Appliance Industry

Type of Company: Home Appliance Giant (Whirlpool)





Report 6

Luxottica, the world's largest eyewear company, experienced a data breach on August 5th, 2020, exposing the personal and protected health information of 820K patients at LensCrafters, Target Optical, EyeMed, and other eye care practices. The breach affected patients' personal data, medical conditions, and history, with some having credit card numbers and social security numbers exposed. Luxottica detected the breach on August 9th and confirmed the attacker's access to patient information on August 28th. The threat actor used novel techniques to breach the appointment scheduling application, leading to the exposure of sensitive data. Luxottica is offering identity monitoring services to affected individuals and advising them to monitor their credit statements for fraudulent activity. The breach was classified as a "Hacking/IT Incident" and affected a significant number of patients in the healthcare sector.





Report 7

Summary:
- Threat actor: Nefilim Hackers
- Region: Global (specifically targeting energy companies in India and Australia)
- Operating sector: Energy, logistics
- Date: June 9, 2020
- Evidence of capability: Nefilim ransomware used to target energy companies, including Aban Offshore and Toll Group, with data breaches and publication of sensitive information online.
- Novelty of tools and techniques: Nefilim ransomware uses AES-128 encryption, marks files with 'Nefilim' string, and manages payments via email communication instead of Tor payment site. The ransomware has similarities with Nemty 2.5 ransomware but does not have a Ransomware-as-a-Service component.
- Toll Group refused to engage with hackers' ransom demands, leading to publication of data on the dark web.
- Ransomware threat is evolving and becoming more sophisticated, requiring stringent precautions to prevent permanent damage to networks.





Report 8

Summary:
- Threat actor: Nefilim Ransomware group, also known as Nemty.
- Date: January 26, 2021.
- Region: Global.
- Operating sector: Not specified.
- Type of company of victims: Not specified.
- Evidence of capability: Compromised admin account with high-level access, exfiltrated hundreds of GB of data, deployed ransomware.
- Novelty of tools and techniques: Exploited Citrix vulnerabilities, used Mimikatz to steal credentials, deployed ransomware via compromised domain admin account, used Cobalt Strike for lateral movement.
- Recommendations: Grant minimal access permissions, disable unnecessary accounts, implement service accounts, conduct regular Active Directory audits, use anti-ransomware technologies like Intercept X.
- Source: Sophos News.





Report 9

Summary: Traveling Spider threat actor, operating in the security sector, released Nemty 1.6 ransomware via the RIG exploit kit targeting enterprise users using Internet Explorer and Flash Player. The ransom note of Nemty 1.6 shows version 1.6, and the encryption algorithm was modified to use Windows cryptographic libraries. The threat actor attempted to evade decryption tools by security firm Tesorion but was unsuccessful. The operation was first spotted on October 11, 2019. The threat actor's capability includes exploiting vulnerabilities in outdated software to distribute ransomware, showcasing a novel approach in utilizing exploit kits for malware distribution.





Report 10

Summary:
The threat actor "Traveling Spider" has been actively distributing Nemty Ransomware via 'Love Letter' spam emails. The spam campaign, identified by Malwarebytes and X-Force IRIS researchers, started on February 27, 2020, targeting potential victims with emails disguised as messages from secret lovers. The emails contain a ZIP archive with a highly obfuscated JavaScript file named LOVE_YOU.js, which downloads and executes the Nemty ransomware on victims' computers. Nemty ransomware, first spotted in August 2019, is known for deleting shadow copies of encrypted files and demanding payment for decryption. The threat actor's use of a 'secret lover' bait in the spam emails is a novel technique to lure victims into downloading the ransomware. The operators behind Nemty ransomware have also announced plans to create a leak blog for publishing information stolen from ransomware victims who refuse to pay. The threat actor's capability to continuously evolve their tactics and tools poses a significant risk to organizations, particularly in the region and operating sectors targeted by the campaign.





Report 11

Summary: The threat actor "Traveling Spider" has been distributing Nemty ransomware through the RIG exploit kit targeting systems with outdated technology. Nemty ransomware operators struck a distribution deal to exploit vulnerabilities in Internet Explorer and Flash Player. The malware administrators made Nemty known on cybercriminal forums, drawing attention through its code referencing the Russian president and antivirus software. Nemty ransomware demands around $1,000 in bitcoin for decryption, with no free decryption tool available. Security researcher Mol69 observed Nemty as a payload in malvertising campaigns from RIG exploit kit, using a new variant with the '.NEMTY_Lct5F3C' extension for encrypted files. The ransom note provides instructions on payment for data recovery, with the decryption key controlled by the malware administrators. Nemty is a new threat in the ransomware scene, met with skepticism in the underground community. The entire activity of Nemty encryption process takes over 10 minutes to finish, and the threat actor is not as selective in partnerships compared to other ransomware operators. 

Date: September 3, 2019

Region: Global

Operating Sector: Various

Type of Company: Various





Report 12

Summary: The threat actor "Traveling Spider," identified as Nemty Ransomware operators, has been targeting victims by stealing and posting their data if ransoms are not paid. The tactic of stealing and publishing data, including sensitive company information, has escalated ransomware attacks into data breaches. The threat actor has been using a data leak site to extort non-paying victims, with evidence of targeting an American footwear company. This novel approach by Nemty Ransomware operators aims to increase costs and reputation damage to push victims into paying ransoms. The report was published on March 2, 2020, by BleepingComputer.





Report 13

Summary: The threat actor "Traveling Spider" has been identified as the group behind the Nemty Ransomware update that allows it to kill processes and services, making it more aggressive and sophisticated. The malware targets corporate victims, as evidenced by its ability to terminate processes like WordPad, Microsoft Word, Excel, and SQL. The threat actor has expanded its target countries list to include Russia, Belarus, and others. The distribution pipeline for the ransomware has evolved, with recent versions being spread through fake PayPal pages and malvertising campaigns. Despite facing challenges, the threat actor is actively developing the malware to establish a lucrative business in the ransomware underground community. Operation time window: September 14, 2019. Region: Global. Operating sector: Various. Company type: Not specified.





Report 14

Summary: The threat actor "Traveling Spider," also known as Nemty Ransomware, has announced plans to leak data of non-paying victims through a blog. This tactic, previously used by other ransomware groups, aims to pressure companies into paying the ransom to avoid data leaks. Nemty Ransomware is capable of network attacks targeting entire corporations, with a builder mode for creating executables. The threat actor plans to create a website for leaking stolen data if ransoms are not paid. This evolution in ransomware tactics indicates a shift towards data exfiltration and further extortion methods. The threat actor's capability to target corporate networks and the novelty of leaking data for extortion purposes pose a significant risk to victims. The report was published on January 13, 2020.





Report 15

Summary: The threat actor known as "Traveling Spider" has been identified as the group behind the Nemty ransomware operation, which recently shut down its public Ransomware-as-a-Service (RaaS) operations. The group has targeted companies in the healthcare and education sectors in the United States and Europe. Evidence suggests that the threat actor has advanced capabilities in deploying ransomware attacks and has been using novel techniques to evade detection. The operation time window for this activity was not specified in the report.





Report 16

Summary:
The threat actor "Traveling Spider" has been identified as the group behind the Nefilim ransomware, which emerged in February 2020. The ransomware threatens to release stolen data if the ransom is not paid within seven days. Nefilim shares code similarities with Nemty 2.5, indicating a potential connection between the two. Unlike Nemty, Nefilim relies on email communications for payments rather than a Tor payment site. The ransomware uses AES-128 encryption and RSA-2048 public key encryption for file encryption. Victims targeted include organizations with exposed Remote Desktop Services. The threat actor's capability is evidenced by the secure nature of the ransomware, making file recovery without payment currently impossible. The novelty lies in the threat to leak data if the ransom is not paid, a tactic increasingly used by ransomware groups. The operation time window is ongoing, with ongoing research to identify potential weaknesses in the ransomware.





Report 17

Summary: The threat actor "Traveling Spider" has been identified spreading a new Nemty ransomware variant via compromised RDP connections. The ransomware, named Nemty, encrypts files and demands a ransom for decryption. The ransom note indicates the attackers hold the decryption key, and victims are instructed to pay in Bitcoin. Security researcher Vitali Kremez discovered unique features in the malware, including references to Russian President Putin and the antivirus industry. Nemty includes a verification process to identify computers in specific countries, and it is distributed through compromised RDP connections, giving the attackers more control. The threat actor's capability is demonstrated through the use of novel techniques and tools, such as the mutex object named "hate" and the encryption key disguised as a message to the antivirus industry. The report does not specify the region, operating sector, or type of company targeted by the threat actor. Date: August 26, 2019.





Report 18

Orange, a French telecommunications company, confirmed a ransomware attack on their Orange Business Services division on July 4th, 2020, exposing data of twenty enterprise customers. The attack was attributed to the Nefilim ransomware operators who leaked customer data on their site. The attack involved a cryptovirus-type computer attack targeting the Neocles IT platform, affecting customers hosted on the "Le Forfait informatique" platform. The leaked data included emails, airplane schematics, and files from ATR Aircraft, a French aircraft manufacturer. This incident highlights the trend of ransomware attacks as data breaches, with stolen files used as leverage for ransom demands. The attack demonstrates the threat actor's capability to breach a telecommunications company's enterprise services division and steal sensitive data, showcasing the novelty of their tools and techniques.





Report 19

The threat actor known as Nefilim Ransomware Group targeted Spirit Airlines, leaking over 33,000 files containing sensitive customer data from 2006 to 2021. The stolen data included credit card lists, transaction records, email addresses, and partial card numbers, violating the privacy of individuals. Despite the breach, Spirit Airlines has not made any public statements or notified customers, indicating a lack of awareness of the incident. The use of specialized dark web intelligence tools by KELA revealed the extent of the data leak. The novelty of the tools and techniques used by the threat actor, such as encryption and system lock-down, highlights their capability to exploit unprotected databases. The report does not specify a specific date or operation time window for the incident.





Report 20

Summary: Toll Group, a leading provider of transportation and logistics services in the Asia Pacific region, was targeted by the Nefilim Ransomware for the second time in three months. The threat actor behind Nefilim is known for stealing unencrypted files and using them as leverage for ransom demands. Toll Group shut down certain IT systems to prevent further encryption of devices, impacting customer-facing applications and deliveries. The threat actor has been actively seeking experienced threat actors to launch network-wide corporate attacks. Toll Group has no intention of engaging with ransom demands and is working with IT security experts and the Australian Cyber Security Centre. The threat actor's use of novel tactics, such as threatening to release stolen data on a "Leaks" site, demonstrates their capability and persistence. The Toll Group was found to be utilizing a vulnerable Citrix ADC Netscaler server during the attacks. The incident highlights the ongoing threat posed by ransomware attacks to companies in the transportation and logistics sector.





Report 21

Traveling Spider, also known as Gold Mansard, is a threat actor that has been active since 2019, with the first version of their ransomware named Nemty. The group's motivation is financial gain, and they have targeted victims in various sectors across multiple countries worldwide. The threat actor has been observed using a variety of tools such as 7-Zip, Mimikatz, and Nemty ransomware. Their operations have included distributing ransomware via exploit kits, spam emails, and targeting high-profile companies like Toll Group and Luxottica. Traveling Spider has also been involved in leaking non-paying victims' data and shutting down public Ransomware as a Service (RaaS) operations. The group's use of novel techniques, such as punishing victims by posting their stolen data online, demonstrates their advanced capabilities in the cyber threat landscape. The latest reported counter operations against Traveling Spider are not specified in the provided report.


