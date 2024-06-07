# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: Diamond Sleet supply chain compromise distributes a modified CyberLink installer | Microsoft Security Blog

**Source**: https://www.microsoft.com/en-us/security/blog/2023/11/22/diamond-sleet-supply-chain-compromise-distributes-a-modified-cyberlink-installer/

## Content

























Diamond Sleet supply chain compromise distributes a modified CyberLink installer | Microsoft Security Blog





























































 

 



















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



													Microsoft Defender XDR												



													Supply chain attacks												




									7 min read								

Diamond Sleet supply chain compromise distributes a modified CyberLink installer




											By										
Microsoft Threat Intelligence












					November 22, 2023				




 





 





 







											Microsoft Defender										



											Microsoft Defender for Endpoint										



											Attacker techniques, tools, and infrastructure										



											Threat actors										





Microsoft Threat Intelligence has uncovered a supply chain attack by the North Korea-based threat actor Diamond Sleet (ZINC) involving a malicious variant of an application developed by CyberLink Corp., a software company that develops multimedia software products. This malicious file is a legitimate CyberLink application installer that has been modified to include malicious code that downloads, decrypts, and loads a second-stage payload. The file, which was signed using a valid certificate issued to CyberLink Corp., is hosted on legitimate update infrastructure owned by CyberLink and includes checks to limit the time window for execution and evade detection by security products. Thus far, the malicious activity has impacted over 100 devices in multiple countries, including Japan, Taiwan, Canada, and the United States.
Microsoft attributes this activity with high confidence to Diamond Sleet, a North Korean threat actor. The second-stage payload observed in this campaign communicates with infrastructure that has been previously compromised by Diamond Sleet. More recently, Microsoft has observed Diamond Sleet utilizing trojanized open-source and proprietary software to target organizations in information technology, defense, and media.
To address the potential risk of further attacks against our customers, Microsoft has taken the following steps to protect customers in response to this malicious activity:

Microsoft has communicated this supply chain compromise to CyberLink 
Microsoft is notifying Microsoft Defender for Endpoint customers that have been targeted or compromised in this campaign
Microsoft reported the attack to GitHub, which removed the second-stage payload in accordance with its Acceptable Use Policies
Microsoft has added the CyberLink Corp. certificate used to sign the malicious file to its disallowed certificate list
Microsoft Defender for Endpoint detects this activity as Diamond Sleet activity group.
Microsoft Defender Antivirus detects the malware as Trojan:Win32/LambLoad.

Microsoft may update this blog as additional insight is gained into the tactics, techniques, and procedures (TTPs) used by the threat actor in this active and ongoing campaign.
Who is Diamond Sleet?
The actor that Microsoft tracks as Diamond Sleet (formerly ZINC) is a North Korea-based activity group known to target media, defense, and information technology (IT) industries globally. Diamond Sleet focuses on espionage, theft of personal and corporate data, financial gain, and corporate network destruction. Diamond Sleet is known to use a variety of custom malware that is exclusive to the group. Recent Diamond Sleet malware is described in Microsoft’s reporting of the group’s weaponization of open source software and exploitation of N-day vulnerabilities. Diamond Sleet overlaps with activity tracked by other security companies as Temp.Hermit and Labyrinth Chollima.



			DIAMOND SLEET (ZINC)		

Learn about other recent activity 



Activity overview
Microsoft has observed suspicious activity associated with the modified CyberLink installer file as early as October 20, 2023. The malicious file has been seen on over 100 devices in multiple countries, including Japan, Taiwan, Canada, and the United States. While Microsoft has not yet identified hands-on-keyboard activity carried out after compromise via this malware, the group has historically:

Exfiltrated sensitive data from victim environments
Compromised software build environments
Moved downstream to additional victims for further exploitation
Used techniques to establish persistent access to victim environments

Diamond Sleet utilized a legitimate code signing certificate issued to CyberLink Corp. to sign the malicious executable. This certificate has been added to Microsoft’s disallowed certificate list to protect customers from future malicious use of the certificate:
Signer: CyberLink Corp. Issuer: DigiCert SHA2 Assured ID Code Signing CA SignerHash: 8aa3877ab68ba56dabc2f2802e813dc36678aef4 CertificateSerialNumber: 0a08d3601636378f0a7d64fd09e4a13b
Microsoft currently tracks the malicious application and associated payloads as LambLoad.
LambLoad
LambLoad is a weaponized downloader and loader containing malicious code added to a legitimate CyberLink application. The primary LambLoad loader/downloader sample Microsoft identified has the SHA-256 hash 166d1a6ddcde4e859a89c2c825cd3c8c953a86bfa92b343de7e5bfbfb5afb8be.
Before launching any malicious code, the LambLoad executable ensures that the date and time of the local host align with a preconfigured execution period.
Figure 1. Code for checking date and time of local host
The loader then targets environments that are not using security software affiliated with FireEye, CrowdStrike, or Tanium by checking for the following process names:

csfalconservice.exe (CrowdStrike Falcon)
xagt.exe (FireEye agent)
taniumclient.exe (Tanium EDR solution)

If these criteria are not met, the executable continues running the CyberLink software and abandons further execution of malicious code. Otherwise, the software attempts to contact one of three URLs to download the second-stage payload embedded inside a file masquerading as a PNG file using the static User-Agent ‘Microsoft Internet Explorer’:

hxxps[:]//i.stack.imgur[.]com/NDTUM.png
hxxps[:]//www.webville[.]net/images/CL202966126.png
hxxps[:]//cldownloader.github[.]io/logo.png

The PNG file contains an embedded payload inside a fake outer PNG header that is, carved, decrypted, and launched in memory.
Figure 2. Payload embedded in PNG file
When invoked, the in-memory executable attempts to contact the following callbacks for further instruction. Both domains are legitimate but have been compromised by Diamond Sleet:

hxxps[:]//mantis.jancom[.]pl/bluemantis/image/addon/addin.php
hxxps[:]//zeduzeventos.busqueabuse[.]com/wp-admin/js/widgets/sub/wids.php

The crypted contents of the PNG file (SHA-256: 089573b3a1167f387dcdad5e014a5132e998b2c89bff29bcf8b06dd497d4e63d) may be manually carved using the following command:

To restore the in-memory payload statically for independent analysis, the following Python script can be used to decrypt the carved contents.

To crypt and verify:

Both the fake PNG and decrypted PE payload have been made available on VirusTotal.
Recommendations
Microsoft recommends the following mitigations to reduce the impact of this threat. Check the recommendations card for the deployment status of monitored mitigations.

Use Microsoft Defender Antivirus to protect from this threat. Turn on cloud-delivered protection and automatic sample submission on Microsoft Defender Antivirus. These capabilities use artificial intelligence and machine learning to quickly identify and stop new and unknown threats.
Enable network protection to prevent applications or users from accessing malicious domains and other malicious content on the internet.
Enable investigation and remediation in full automated mode to allow Microsoft Defender for Endpoint to take immediate action on alerts to resolve breaches, significantly reducing alert volume.
Take immediate action to address malicious activity on the impacted device. If malicious code has been launched, the attacker has likely taken complete control of the device. Immediately isolate the system and perform a reset of credentials and tokens.
Investigate the device timeline for indications of lateral movement activities using one of the compromised accounts. Check for additional tools that attackers might have dropped to enable credential access, lateral movement, and other attack activities. Ensure data integrity with hash codes.
Turn on the following attack surface reduction rule: Block executable files from running unless they meet a prevalence, age, or trusted list criterion.

Detection details
Microsoft Defender Antivirus
Microsoft Defender Antivirus detects threat components as the following malware:

Trojan:Win32/LambLoad.A!dha
Trojan:Win32/LambLoad.B!dha
Trojan:Win32/LambLoad.C!dha
Trojan:Win64/LambLoad.D!dha
Trojan:Win64/LambLoad.E!dha

Microsoft Defender for Endpoint
Alerts with the following title in the security center can indicate threat activity on your network:

Diamond Sleet activity group

The following alert might also indicate threat activity related to this threat. Note, however, that this alert can be also triggered by unrelated threat activity.

An executable loaded an unexpected dll

Threat intelligence reports
Microsoft customers can use the following reports in Microsoft products to get the most up-to-date information about the threat actor, malicious activity, and techniques discussed in this blog. These reports provide the intelligence, protection information, and recommended actions to prevent, mitigate, or respond to associated threats found in customer environments.
Microsoft Defender Threat Intelligence

Diamond Sleet
Diamond Sleet supply chain compromise at distributes a modified CyberLink installer

Microsoft Defender XDR Threat analytics 

Actor profile: Diamond Sleet
Activity profile: Diamond Sleet supply chain compromise at distributes a modified CyberLink installer

Hunting queries
Microsoft Defender XDR  
Microsoft Defender XDR (formerly Microsoft 365 Defender) customers can run the following query to find related activity in their networks:

let iocs = dynamic(["166d1a6ddcde4e859a89c2c825cd3c8c953a86bfa92b343de7e5bfbfb5afb8be",
"089573b3a1167f387dcdad5e014a5132e998b2c89bff29bcf8b06dd497d4e63d",
"915c2495e03ff7408f11a2a197f23344004c533ff87db4b807cc937f80c217a1"]);
DeviceFileEvents
| where ActionType == "FileCreated"
| where SHA256 in (iocs)
| project Timestamp, DeviceName, FileName, FolderPath, SHA256

Microsoft Defender XDR and Microsoft Sentinel
This query can be used in both Microsoft Defender XDR advanced hunting and Microsoft Sentinel Log Analytics. It surfaces devices where the modified CyberLink installer can be found.

DeviceFileCertificateInfo
| where Signer contains "CyberLink Corp"
| where CertificateSerialNumber == "0a08d3601636378f0a7d64fd09e4a13b"
| where SignerHash == "8aa3877ab68ba56dabc2f2802e813dc36678aef4"
| join DeviceFileEvents on SHA1
| distinct DeviceName, FileName, FolderPath, SHA1, SHA256, IsTrusted, IsRootSignerMicrosoft, SignerHash

Microsoft Sentinel
Microsoft Sentinel customers can use the TI Mapping analytics (a series of analytics all prefixed with ‘TI map’) to automatically match the malicious domain indicators mentioned in this blog post with data in their workspace. If the TI Map analytics are not currently deployed, customers can install the Threat Intelligence solution from the Microsoft Sentinel Content Hub to have the analytics rule deployed in their Sentinel workspace.
The following YAMLs contain queries that surface activities related to this attack:

Uncommon processes
Windows installer packages
Process entropy
Rare process path
Device network events with low-count FQDN

Indicators of compromise
The list below provides IOCs observed during our investigation. We encourage our customers to investigate these indicators in their environments and implement detections and protections to identify past related activity and prevent future attacks against their systems.
IndicatorTypeDescription166d1a6ddcde4e859a89c2c825cd3c8c953a86bfa92b343de7e5bfbfb5afb8beSHA-256Trojanized CyberLink installer (LambLoad)089573b3a1167f387dcdad5e014a5132e998b2c89bff29bcf8b06dd497d4e63dSHA-256Second-stage PNG payload915c2495e03ff7408f11a2a197f23344004c533ff87db4b807cc937f80c217a1 SHA-256Decrypted PE from second-stage PNGhxxps[:]//update.cyberlink[.]com/Retail/Promeo/RDZCMSFY1ELY/CyberLink_Pr omeo_Downloader.exeURLCyberLink update URL used to deliver malicious installerhxxps[:]//update.cyberlink[.]com/Retail/Patch/Promeo/DL/RDZCMSFY1ELY/Cyb erLink_Promeo_Downloader.exeURLCyberLink update URL used to deliver malicious installerhxxps[:]//cldownloader.github[.]io/logo.pngURLStage 2 staging URLhxxps[:]//i.stack.imgur[.]com/NDTUM.pngURLStage 2 staging URLhxxps[:]//www.webville[.]net/images/CL202966126.pngURLStage 2 staging URLhxxps[:]//mantis.jancom[.]pl/bluemantis/image/addon/addin.phpURLStage 2 callback URLhxxps[:]//zeduzeventos.busqueabuse[.]com/wpadmin/js/widgets/sub/wids.phpURLStage 2 callback url
Further reading
For the latest security research from the Microsoft Threat Intelligence community, check out the Microsoft Threat Intelligence Blog: https://aka.ms/threatintelblog.
To get notified about new publications and to join discussions on social media, follow us on X (formerly Twitter) at https://twitter.com/MsftSecIntel.









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




































