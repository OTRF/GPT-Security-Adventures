
Report 1

Summary:
- Threat actor known as "Scattered Spider" conducted a cyberattack on MGM Resorts on September 10, impacting over 30 hotels and casinos globally.
- The group is believed to consist of young adults from the US and UK, utilizing social engineering tactics to obtain login credentials.
- Scattered Spider is associated with the BlackCat/ALPHV ransomware and recently targeted Caesars Entertainment, receiving tens of millions in ransom.
- The group employs credential phishing and social engineering to bypass multifactor authentication and gain access to systems.
- Instead of using unique malware, Scattered Spider relies on legitimate remote management tools for persistent access.
- MGM Resorts' websites are still offline as the investigation continues.
- The attack on MGM Resorts follows a similar pattern to the one on Caesars Entertainment in late August.
- The threat actor's capability lies in their ability to manipulate users into providing access credentials and bypassing security measures.
- The tools and techniques used by Scattered Spider are not novel but effective in breaching high-profile targets in the casino industry.
- The report does not specify a specific date for the operation but highlights ongoing investigations into the cyberattack.

Date: September 14, 2023

Region: Global
Operating Sector: Casinos
Type of Company: MGM Resorts, Caesars Entertainment

Source: https://www.darkreading.com/attacks-breaches/-scattered-spider-mgm-cyberattack-casinos





Report 2

Summary:
The threat actor Octo Tempest, operating globally, has been engaging in financially motivated activities targeting organizations across various industries. Known for their social engineering campaigns, SIM swapping capabilities, and affiliation with ransomware groups, Octo Tempest has evolved their tactics to include extortion, encryption, and destruction of data. They have targeted industries such as telecommunications, technology, and financial services, expanding their operations to include ransomware deployment on VMWare ESXi servers. Utilizing advanced social engineering techniques, SMS phishing, and SIM swapping, Octo Tempest has demonstrated a high level of technical depth and persistence in their attacks. Their use of diverse tools and techniques, such as Azure Data Factory for data exfiltration, showcases their evolving capabilities. Organizations are advised to implement robust security measures, align privileges in Microsoft Entra ID and Azure, and educate users to defend against Octo Tempest's sophisticated attacks. The threat actor's activities have been detected and mitigated through various Microsoft security solutions, providing insights and recommendations for organizations to enhance their defenses against Octo Tempest. The report was last updated on November 1, 2023.





Report 3

Scattered Spider, also known as UNC3944, is a financially motivated threat actor that has been active since 2022. They have been using phone-based social engineering and SMS phishing campaigns to obtain credentials and escalate access to victim organizations. In mid-2023, they shifted to deploying ransomware in victim environments, expanding their monetization strategies. The group has targeted a wide range of industries including telecommunication, business process outsourcers, hospitality, retail, media and entertainment, and financial services. Their tools and techniques include ADRecon, Mimikatz, PingCastle, and others. Some of their reported hacking operations include cyberattacks on MGM Resorts and Caesars Entertainment, leading to ransom payments and customer data theft. Scattered Spider has also targeted luxury hotels in ongoing social engineering attacks. The threat actor operates worldwide and has been observed in underground communities such as Telegram and underground forums. Their capabilities and evolving tactics indicate a persistent and expanding threat to various sectors and industries.





Report 4

Scattered Spider threat actors have been targeting commercial facilities sectors and subsectors, engaging in data theft for extortion and utilizing BlackCat/ALPHV ransomware. They are experts in social engineering, using techniques like phishing, push bombing, and SIM swap attacks to gain access to networks. Scattered Spider actors have been observed using legitimate remote access tunneling tools and malware like AveMaria, Raccoon Stealer, and VIDAR Stealer. They have recently started encrypting victim files after exfiltration and communicate with victims via TOR, Tox, email, or encrypted applications. The threat actors conduct SIM swapping attacks, perform account takeovers in SSO environments, and exfiltrate data to multiple sites including U.S.-based data centers and MEGA[.]NZ. Scattered Spider threat actors have been observed deploying BlackCat/ALPHV ransomware onto victim networks, encrypting VMware ESXi servers. The FBI and CISA recommend implementing various mitigations to improve cybersecurity posture and reduce the risk of compromise by Scattered Spider threat actors. The report was released on November 16, 2023.





Report 5

Summary:
The threat actor known as Muddled Libra, operating in the software automation, BPO, telecommunications, and technology industries, poses a significant risk to organizations with well-developed legacy cyber defenses. They have been active from mid-2022 through early 2023, targeting large outsourcing firms serving high-value cryptocurrency institutions and individuals. Muddled Libra utilizes social engineering as their primary modus operandi, targeting IT help support desks and using anonymizing proxy services to obscure their IP addresses. They have been observed using various tools and techniques, such as NSOCKs and TrueSocks proxy services, creating email rules to monitor communications, deploying custom virtual machines, and using open-source rootkits to target VMware vCenter servers. The threat actor has a strong understanding of the modern incident response framework and has been associated with the BlackCat ransomware group. Muddled Libra's capabilities include a wide attack toolkit, proficiency in social engineering, and flexibility in attack strategies, making them difficult to eradicate once established in an environment. The threat actor has clear goals for their breaches and targets downstream customers using stolen data. The report provides indicators of compromise and mitigation recommendations for organizations to defend against Muddled Libra. The report was updated on September 15, 2023, to include new tactics, techniques, and procedures observed in incident response cases involving Muddled Libra.





Report 6

UNC3944, a financially motivated threat cluster known as "Scattered Spider," has been leveraging SMS phishing campaigns for SIM swapping, ransomware, extortion, and notoriety since 2022. The threat actor has been observed targeting a wide range of industries, including telecommunication, business process outsourcer (BPO) companies, hospitality, retail, media and entertainment, and financial services. UNC3944 has demonstrated a strong focus on stealing sensitive data for extortion purposes and has shown an understanding of Western business practices. The threat actor has been using publicly available tools and legitimate software in combination with malware available for purchase on underground forums. UNC3944 has been observed using social engineering tactics, commercial residential proxy services, legitimate software, and high operational tempo to access critical systems and exfiltrate large volumes of data. The threat actor has also been creating unmanaged virtual machines inside victims' environments and targeting business-critical systems when deploying ransomware. UNC3944 has been expanding its monetization strategies, shifting from SIM swapping attacks to ransomware, and is expected to continue diversifying its tactics and skills over time. The threat actor has been using phishing kits, credential theft tools, and cloud resources to establish persistent access to victim environments and maximize impact. The report provides recommendations for organizations to mitigate against common UNC3944 tactics, such as MFA abuse and unauthorized use of privileged accounts within Microsoft cloud environments. The threat actor is expected to continue evolving and leveraging underground communities for support to enhance the effectiveness of their operations. (Source: Mandiant, Sep 14, 2023)





Report 7

Summary:
The threat actor known as "Scattered Spider," also referred to as "0ktapus" and UNC3944, has expanded its targets from telecommunication and tech companies to include hospitality, retail, media, and financial services. Operating since 2022, the group has evolved from data theft to sophisticated ransomware attacks, using phone-based social engineering and SMS phishing campaigns to gain access to victim organizations. They have shown skill in social engineering techniques and have a focus on stealing sensitive data for extortion purposes. The threat actor relies on publicly available tools, legitimate software, and malware purchased on underground forums. They have been observed using phishing kits, infostealers, and data miners to move laterally within victim networks. The group's evolution into ransomware attacks and extortion signals a shift in their monetization strategies, with potential collaboration with other ransomware gangs like BlackCat/AlphV. The threat actor's use of creative and persistent targeting of victims' cloud resources poses a significant challenge to defenders. The group's capability to access critical systems, exfiltrate large volumes of data, and overwhelm security response teams highlights the sophistication of their operations. The threat actor's use of novel techniques and tools, along with their continuous evolution, indicates a persistent and growing threat to organizations across various industries. (Date: September 18th, 2023)


