# Reference for threat actor for "Tropical Scorpius, RomCom"

**Title**: Storm-0978 attacks reveal financial and espionage motives | Microsoft Security Blog

**Source**: https://www.microsoft.com/en-us/security/blog/2023/07/11/storm-0978-attacks-reveal-financial-and-espionage-motives/

## Content


























Storm-0978 attacks reveal financial and espionage motives | Microsoft Security Blog




























































 

 



















Skip to main content







Microsoft



Microsoft Security




Microsoft Security




                            Microsoft Security
                        




 Home 



Solutions


Cloud security


Cloud workload protection


Data security


Frontline workers


Identity & network access


Identity threat detection & response


Industrial & critical infrastructure


Information protection & governance


IoT security


Passwordless authentication


Phishing


Ransomware


Risk management


Secure remote work


XDR


XDR + SIEM


Zero Trust



 

Products


Product families
Product families


Microsoft Defender


Microsoft Entra


Microsoft Intune


Microsoft Priva


Microsoft Purview


Microsoft Sentinel




Security AI
Security AI


Microsoft Security Copilot




Identity & access
Identity & access


Microsoft Entra ID (Azure Active Directory)


Microsoft Entra External ID


Microsoft Entra ID Governance


Microsoft Entra ID Protection


Microsoft Entra Internet Access


Microsoft Entra Private Access


Microsoft Entra Permissions Management


Microsoft Entra Verified ID


Microsoft Entra Workload ID


Microsoft Entra Domain Services


Azure Key Vault




SIEM & XDR
SIEM & XDR


Microsoft Sentinel


Microsoft Defender for Cloud


Microsoft Defender XDR


Microsoft Defender for Endpoint


Microsoft Defender for Office 365


Microsoft Defender for Identity


Microsoft Defender for Cloud Apps


Microsoft Defender Vulnerability Management


Microsoft Defender Threat Intelligence




Cloud security
Cloud security


Microsoft Defender for Cloud


Microsoft Defender Cloud Security Posture Mgmt


Microsoft Defender External Attack Surface Management


Azure Firewall


Azure Web App Firewall


Azure DDoS Protection


GitHub Advanced Security




Endpoint security & management
Endpoint security & management


Microsoft Defender for Endpoint


Microsoft Defender XDR


Microsoft Defender for Business


Microsoft Intune core capabilities


Microsoft Defender for IoT


Microsoft Defender Vulnerability Management


Microsoft Intune Advanced Analytics


Microsoft Intune Endpoint Privilege Management​


Microsoft Intune Enterprise Application Management


Microsoft Intune Remote Help


Microsoft Cloud PKI




Risk management & privacy
Risk management & privacy


Microsoft Purview Insider Risk Management


Microsoft Purview Communication Compliance


Microsoft Purview eDiscovery


Microsoft Purview Compliance Manager


Microsoft Purview Audit


Microsoft Priva Risk Management


Microsoft Priva Subject Rights Requests




Information protection
Information protection


Microsoft Purview Information Protection


Microsoft Purview Data Lifecycle Management


Microsoft Purview Data Loss Prevention





 

Services


Microsoft Security Experts


Microsoft Defender Experts for XDR


Microsoft Defender Experts for Hunting


Microsoft Incident Response


Microsoft Security Enterprise Services



 
Partners



Resources


Get started
Get started


Cybersecurity awareness


Customer stories


Security 101


Product trials


How we protect Microsoft




Reports and analysis
Reports and analysis


Industry recognition


Microsoft Security Insider


Microsoft Digital Defense Report


Security Response Center




Community
Community


Microsoft Security Blog


Microsoft Security Events


Microsoft Tech Community




Documentation and training
Documentation and training


Documentation


Technical Content Library


Training & certifications




Additional sites
Additional sites


Compliance Program for Microsoft Cloud


Microsoft Trust Center


Security Engineering Portal


Service Trust Portal


Microsoft built in security





 
Contact Sales



More





Start free trial




 



 All Microsoft


Global


Microsoft Security


Azure


Dynamics 365


Microsoft 365


Microsoft Teams


Windows 365




Tech & innovation
Tech & innovation


Microsoft Cloud


AI


Azure Space


Mixed reality


Microsoft HoloLens


Microsoft Viva


Quantum computing


Sustainability




Industries
Industries


Education


Automotive


Financial services


Government


Healthcare


Manufacturing


Retail


All industries




Partners
Partners


Find a partner


Become a partner


Partner Network


Find an advertising partner


Become an advertising partner


Azure Marketplace


AppSource




Resources
Resources


Blog


Microsoft Advertising


Developer Center


Documentation


Events


Licensing


Microsoft Learn


Microsoft Research




View Sitemap










Search
Search Microsoft Security




 No results




Cancel







 













					Blog home				

Threat intelligence











			Search the Microsoft security blog		



Submit

 

















 









													Research												



													Threat intelligence												



													Microsoft Defender												



													Threat actors												




									7 min read								

Storm-0978 attacks reveal financial and espionage motives




											By										
Microsoft Threat Intelligence












					July 11, 2023				




 





 





 







											Microsoft Defender for Endpoint										



											Microsoft Defender XDR										



											Microsoft Sentinel										



											Attacker techniques, tools, and infrastructure										



											Ransomware										



											Vulnerabilities and exploits										



											Extortion										



											Ransomware										



											Remote code execution										



											Storm										






August 8, 2023 update: Microsoft released security updates to address CVE-2023-36884. Customers are advised to apply patches, which supersede the mitigations listed in this blog, as soon as possible.

Microsoft has identified a phishing campaign conducted by the threat actor tracked as Storm-0978 targeting defense and government entities in Europe and North America. The campaign involved the abuse of CVE-2023-36884, which included a remote code execution vulnerability exploited before disclosure to Microsoft via Word documents, using lures related to the Ukrainian World Congress.
Storm-0978 (DEV-0978; also referred to as RomCom, the name of their backdoor, by other vendors) is a cybercriminal group based out of Russia, known to conduct opportunistic ransomware and extortion-only operations, as well as targeted credential-gathering campaigns likely in support of intelligence operations. Storm-0978 operates, develops, and distributes the RomCom backdoor. The actor also deploys the Underground ransomware, which is closely related to the Industrial Spy ransomware first observed in the wild in May 2022. The actor’s latest campaign detected in June 2023 involved abuse of CVE-2023-36884 to deliver a backdoor with similarities to RomCom.
Storm-0978 is known to target organizations with trojanized versions of popular legitimate software, leading to the installation of RomCom. Storm-0978’s targeted operations have impacted government and military organizations primarily in Ukraine, as well as organizations in Europe and North America potentially involved in Ukrainian affairs. Identified ransomware attacks have impacted the telecommunications and finance industries, among others.
Microsoft 365 Defender detects multiple stages of Storm-0978 activity. Customers who use Microsoft Defender for Office 365 are protected from attachments that attempt to exploit CVE-2023-36884. In addition, customers who use Microsoft 365 Apps (Versions 2302 and later) are protected from exploitation of the vulnerability via Office. Organizations who cannot take advantage of these protections can set the FEATURE_BLOCK_CROSS_PROTOCOL_FILE_NAVIGATION registry key to avoid exploitation. More mitigation recommendations are outlined in this blog.

Microsoft 365 Defender is becoming Microsoft Defender XDR. Learn more.

Targeting
Storm-0978 has conducted phishing operations with lures related to Ukrainian political affairs and targeting military and government bodies primarily in Europe. Based on the post-compromise activity identified by Microsoft, Storm-0978 distributes backdoors to target organizations and may steal credentials to be used in later targeted operations.
The actor’s ransomware activity, in contrast, has been largely opportunistic in nature and entirely separate from espionage-focused targets. Identified attacks have impacted the telecommunications and finance industries.
Tools and TTPs
Tools
Storm-0978 uses trojanized versions of popular, legitimate software, leading to the installation of RomCom, which Microsoft assesses is developed by Storm-0978. Observed examples of trojanized software include Adobe products, Advanced IP Scanner, Solarwinds Network Performance Monitor, Solarwinds Orion, KeePass, and Signal. To host the trojanized installers for delivery, Storm-0978 typically registers malicious domains mimicking the legitimate software (for example, the malicious domain advanced-ip-scaner[.]com).
In financially motivated attacks involving ransomware, Storm-0978 uses the Industrial Spy ransomware, a ransomware strain first observed in the wild in May 2022, and the Underground ransomware. The actor has also used the Trigona ransomware in at least one identified attack.
Additionally, based on attributed phishing activity, Storm-0978 has acquired exploits targeting zero-day vulnerabilities. Identified exploit activity includes abuse of CVE-2023-36884, including a remote code execution vulnerability exploited via Microsoft Word documents in June 2023, as well as abuse of vulnerabilities contributing to a security feature bypass.
Ransomware activity
In known ransomware intrusions, Storm-0978 has accessed credentials by dumping password hashes from the Security Account Manager (SAM) using the Windows registry. To access SAM, attackers must acquire SYSTEM-level privileges. Microsoft Defender for Endpoint detects this type of activity with alerts such as Export of SAM registry hive.
Storm-0978 has then used the Impacket framework’s SMBExec and WMIExec functionalities for lateral movement.
Microsoft has linked Storm-0978 to previous management of the Industrial Spy ransomware market and crypter. However, since as early as July 2023, Storm-0978 began to use a ransomware variant called Underground, which contains significant code overlaps with the Industrial Spy ransomware.
Figure 1. Storm-0978 ransom note references the “Underground team” and contains target-specific details of exfiltrated information
The code similarity between the two ransomware variants, as well as Storm-0978’s previous involvement in Industrial Spy operations, may indicate that Underground is a rebranding of the Industrial Spy ransomware.
Figure 2. Underground ransomware .onion site
Espionage activity
Since late 2022, Microsoft has identified the following campaigns attributable to Storm-0978. Based on the post-compromise activity and the nature of the targets, these operations were likely driven by espionage-related motivations:
June 2023 – Storm-0978 conducted a phishing campaign containing a fake OneDrive loader to deliver a backdoor with similarities to RomCom. The phishing emails were directed to defense and government entities in Europe and North America, with lures related to the Ukrainian World Congress. These emails led to exploitation via the CVE-2023-36884 vulnerability.Microsoft Defender for Office 365 detected Storm-0978’s initial use of the exploit targeting CVE-2023-36884 in this phishing activity. Additional recommendations specific to this vulnerability are detailed below.
Figure 3. Storm-0978 email uses Ukrainian World Congress and NATO themes
Figure 4. Storm-0978 lure document with Ukrainian World Congress and NATO content
Notably, during this campaign, Microsoft identified concurrent, separate Storm-0978 ransomware activity against an unrelated target using the same initial payloads. The subsequent ransomware activity against a different victim profile further emphasizes the distinct motivations observed in Storm-0978 attacks.
December 2022 – According to CERT-UA, Storm-0978 compromised a Ukrainian Ministry of Defense email account to send phishing emails. Identified lure PDFs attached to emails contained links to a threat actor-controlled website hosting information-stealing malware.
October 2022 – Storm-0978 created fake installer websites mimicking legitimate software and used them in phishing campaigns. The actor targeted users at Ukrainian government and military organizations to deliver RomCom and likely to obtain credentials of high-value targets.
Recommendations
Microsoft recommends the following mitigations to reduce the impact of activity associated with Storm-0978’s operations.

Turn on cloud-delivered protection in Microsoft Defender Antivirus or the equivalent for your antivirus product to cover rapidly evolving attacker tools and techniques. Cloud-based machine learning protections block a majority of new and unknown variants.
Run EDR in block mode so that Microsoft Defender for Endpoint can block malicious artifacts, even when your non-Microsoft antivirus doesn’t detect the threat or when Microsoft Defender Antivirus is running in passive mode. EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post-breach.
Enable investigation and remediation in full automated mode to allow Microsoft Defender for Endpoint to take immediate action on alerts to resolve breaches, significantly reducing alert volume.
Use Microsoft Defender for Office 365 for enhanced phishing protection and coverage against new threats and polymorphic variants. Defender for Office 365 customers should ensure that Safe Attachments and Safe Links protection is enabled for users with  Zero-hour Auto Purge (ZAP) to remove emails when a URL gets weaponized post-delivery.
Microsoft 365 Defender customers can turn on attack surface reduction rules to prevent common attack techniques used in ransomware attacks:

Block process creations originating from PsExec and WMI commands – Some organizations might experience compatibility issues with this rule on certain server systems but should deploy it to other systems to prevent lateral movement originating from PsExec and WMI, including Impacket’s WMIexec.
Block executable files from running unless they meet a prevalence, age, or trusted list criterion
Use advanced protection against ransomware
Block all Office applications from creating child processes



CVE-2023-36884 specific recommendations

 August 8, 2023 update: Microsoft released security updates to address CVE-2023-36884. Customers are advised to apply patches, which supersede the mitigations below, as soon as possible. 


Customers who use Microsoft Defender for Office 365 are protected from attachments that attempt to exploit CVE-2023-36884.
In addition, customers who use Microsoft 365 Apps (Versions 2302 and later) are protected from exploitation of the vulnerability via Office.
In current attack chains, the use of the Block all Office applications from creating child processes attack surface reduction rule prevents the vulnerability from being exploited
Organizations who cannot take advantage of these protections can set the FEATURE_BLOCK_CROSS_PROTOCOL_FILE_NAVIGATION registry key to avoid exploitation. 

No OS restart is required, but restarting the applications that have had the registry key added for them is recommended in case the value was already queried and is cached.
Please note that while these registry settings would mitigate exploitation of this issue, it could affect regular functionality for certain use cases related to these applications. For this reason, we suggest testing. To disable the mitigation, delete the registry key or set it to “0”.



Figure 5. Screenshot of settings for the FEATURE_BLOCK_CROSS_PROTOCOL_FILE_NAVIGATION key to prevent exploitation of CVE-2023-36884
Detection details
Microsoft Defender for Office 365
Microsoft Defender for Office 365 customers are protected from attachments that attempt to exploit CVE-2023-36884.
Microsoft Defender Antivirus
Microsoft Defender Antivirus detects post-compromise components of this threat as the following malware:

Ransom:Win32/IndustrialSpy
Trojan:Win32/RomCom
Trojan:Win64/RomCom
HackTool:Win32/Impacket
HackTool:Python/Impacket
Exploit:Script/Teefey

Microsoft Defender for Endpoint
Alerts with the following titles in the security center can indicate threat activity on your network:

Emerging threat activity group Storm-0978 detected

Microsoft Sentinel
Microsoft Sentinel also has detection and threat hunting content that customers can use to detect the post exploitation activity detailed in this blog in addition to Microsoft 365 Defender detections list above.
The following content can be used to identify activity described in this blog post:

Potential Impacket Execution
Commands executed by WMI on new hosts – potential Impacket

References

Void Rabisu’s Use of RomCom Backdoor Shows a Growing Shift in Threat Actors’ Goals. Trend Micro
Technical Analysis of Industrial Spy Ransomware. ZScaler
CERT-UA#6940. CERT-UA

Further reading
For the latest security research from the Microsoft Threat Intelligence community, check out the Microsoft Threat Intelligence Blog: https://aka.ms/threatintelblog.
To get notified about new publications and to join discussions on social media, follow us on Twitter at https://twitter.com/MsftSecIntel. 




							Related Posts						






 








									Research								



									Threat intelligence								



									Microsoft Defender								



									Threat actors								

 

Published Apr 18				

						7 min read					




Microsoft shifts to a new threat actor naming taxonomy 



			Microsoft is excited to announce that we are shifting to a new threat actor naming taxonomy aligned to the theme of weather. The complexity, scale, and volume of threats is increasing, driving the need to reimagine not only how Microsoft talks about threats but also how we enable customers to understand those threats quickly and with clarity.		








 








									Research								



									Threat intelligence								



									Microsoft Defender								



									Attacker techniques, tools, and infrastructure								

 

Published Jun 14				

						13 min read					




Cadet Blizzard emerges as a novel and distinct Russian threat actor 



			Microsoft attributes several campaigns to a distinct Russian state-sponsored threat actor tracked as Cadet Blizzard (DEV-0586), including the WhisperGate destructive attack, Ukrainian website defacements, and the hack-and-leak front “Free Civilian”. 		








 








									Research								



									Threat intelligence								



									Microsoft Defender								



									Threat actors								

 

Published May 24				

						10 min read					




Volt Typhoon targets US critical infrastructure with living-off-the-land techniques 



			Chinese state-sponsored actor Volt Typhoon is using stealthy techniques to target US critical infrastructure, conduct espionage, and dwell in compromised environments.		








 








									Research								



									Threat intelligence								



									Microsoft Defender								



									Threat actors								

 

Published Apr 18				

						14 min read					




Nation-state threat actor Mint Sandstorm refines tradecraft to attack high-value targets 



			Today, Microsoft is reporting on a distinct subset of Mint Sandstorm (formerly known as PHOSPHORUS), an Iranian threat actor that specializes in hacking into and stealing sensitive information from high-value targets. This subset is technically and operationally mature, capable of developing bespoke tooling and quickly weaponizing recently disclosed vulnerabilities. 		














Get started with Microsoft Security

Microsoft is a leader in cybersecurity, and we embrace our responsibility to make the world a safer place.



							Learn more						






 







		Connect with us on social	




 





 





 













What's new


Surface Laptop Studio 2


Surface Laptop Go 3


Surface Pro 9


Surface Laptop 5


Surface Studio 2+


Copilot in Windows


Microsoft 365


Windows 11 apps




Microsoft Store


Account profile


Download Center


Microsoft Store support


Returns


Order tracking


Certified Refurbished


Microsoft Store Promise


Flexible Payments




Education


Microsoft in education


Devices for education


Microsoft Teams for Education


Microsoft 365 Education


How to buy for your school


Educator training and development


Deals for students and parents


Azure for students






Business


Microsoft Cloud


Microsoft Security


Dynamics 365


Microsoft 365


Microsoft Power Platform


Microsoft Teams


Microsoft Industry


Small Business




Developer & IT


Azure


Developer Center


Documentation


Microsoft Learn


Microsoft Tech Community


Azure Marketplace


AppSource


Visual Studio




Company


Careers


About Microsoft


Company news


Privacy at Microsoft


Investors


Diversity and inclusion


Accessibility


Sustainability






English (United States)


California Consumer Privacy Act (CCPA) Opt-Out Icon





Your Privacy Choices




California Consumer Privacy Act (CCPA) Opt-Out Icon





Your Privacy Choices





Sitemap


Contact Microsoft


Privacy 


Manage cookies


Terms of use


Trademarks


Safety & eco


Recycling


About our ads

© Microsoft 2024

































