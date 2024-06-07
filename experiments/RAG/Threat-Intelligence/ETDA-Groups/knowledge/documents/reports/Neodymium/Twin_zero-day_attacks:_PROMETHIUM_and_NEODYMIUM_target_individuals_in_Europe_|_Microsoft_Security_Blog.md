# Reference for threat actor for "Neodymium"

**Title**: Twin zero-day attacks: PROMETHIUM and NEODYMIUM target individuals in Europe | Microsoft Security Blog

**Source**: https://www.microsoft.com/security/blog/2016/12/14/twin-zero-day-attacks-promethium-and-neodymium-target-individuals-in-europe/

## Content

























Twin zero-day attacks: PROMETHIUM and NEODYMIUM target individuals in Europe | Microsoft Security Blog


























































 

 



















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



													Attacker techniques, tools, and infrastructure												




									3 min read								

Twin zero-day attacks: PROMETHIUM and NEODYMIUM target individuals in Europe




											By										
Microsoft Defender Security Research Team












					December 14, 2016				




 





 





 







											Attacker techniques, tools, and infrastructure										



											Windows										





Targeted attacks are typically carried out against individuals to obtain intellectual property and other valuable data from target organizations. These individuals are either directly in possession of the targeted information or are able to connect to networks where the information resides. Microsoft researchers have encountered twin threat activity groups that appear to target individuals for reasons that are quite uncommon.
Unlike many activity groups, which typically gather information for monetary gain or economic espionage, PROMETHIUM and NEODYMIUM appear to launch campaigns simply to gather information about certain individuals. These activity groups are also unusual in that they use the same zero-day exploit to launch attacks at around the same time in the same region. Their targets, however, appear to be individuals that do not share common affiliations.
Activity group profiles
PROMETHIUM is an activity group that has been active as early as 2012. The group primarily uses Truvasys, a first-stage malware that has been in circulation for several years. Truvasys has been involved in several attack campaigns, where it has masqueraded as one of server common computer utilities, including WinUtils, TrueCrypt, WinRAR, or SanDisk. In each of the campaigns, Truvasys malware evolved with additional features—this shows a close relationship between the activity groups behind the campaigns and the developers of the malware.
NEODYMIUM is an activity group that is known to use a backdoor malware detected by Microsoft as Wingbird. This backdoor’s characteristics closely match FinFisher, a government-grade commercial surveillance package. Data about Wingbird activity indicate that it is typically used to attack individual computers instead of networks.
Similarly timed attacks
In early May 2016, both PROMETHIUM and NEODYMIUM started conducting attack campaigns against specific individuals in Europe. They both used an exploit for CVE-2016-4117, a vulnerability in Adobe Flash Player that, at the time, was both unknown and unpatched.
PROMETHIUM distributed links through instant messengers, pointing recipients to malicious documents that invoked the exploit code to launch Truvasys on victim computers. Meanwhile, NEODYMIUM used well-tailored spear-phishing emails with attachments that delivered the exploit code, ultimately leading to Wingbird’s installation on victim computers.
While the use of the same exploit code could be attributed to coincidence, the timing of the campaigns and the geographic location of victims lend credence to the theory that the campaigns are somehow related.
Stopping exploits in Windows 10
PROMETHIUM and NEODYMIUM both used a zero-day exploit that executed code to download a malicious payload. Protected view, a security feature introduced in Microsoft Office 2010, can prevent the malicious Flash code from loading when the document is opened. Control Flow Guard, a security feature that is turned on by default in Windows 10 and Microsoft Office 365 64-bit, can stop attempts to exploit memory corruption vulnerabilities. In addition, Credential Guard, an optional feature introduced in Windows 10, can stop Wingbird’s use of the system file, lsass.exe, to load a malicious DLL.
Detecting suspicious behaviors with Windows Defender Advanced Threat Protection
Windows Defender Advanced Threat Protection (Windows Defender ATP) is a new built-in service that ships natively with Windows 10 and helps enterprises to detect, investigate and respond to advanced targeted attacks. When activated, it captures behavioral signals from endpoints and then uses cloud-based machine learning analytics and threat intelligence to flag attack-related activities.
Wingbird, the advanced malware used by NEODYMIUM, has several behaviors that trigger alerts in Windows Defender ATP. Windows Defender ATP has multiple behavioral and machine learning detection rules that can catch various elements of the malware kill chain. As a result, it can generically detect, without any signature, a NEODYMIUM attack in the following stages:

Zero-day exploits causing Microsoft Office to generate and execute malicious files
Zero-day exploits attempting to grant malicious executables higher privileges
Malicious files trying to delete themselves
Malicious files attempting the DLL side-loading technique, in which legitimate DLLs in non-standard folders are replaced by malicious ones so that malicious files are loaded by the operating system or by installed applications
Malicious files injecting code into legitimate processes

In the example below, Windows Defender ATP alerts administrators that something is amiss. It notifies them that an Office document has dropped an executable file in one of their computers—activity that is very likely part of an attack.

Additionally, Windows Defender ATP and Office 365 ATP leverage rules based on IOCs and threat intelligence specific to PROMETHIUM and NEODYMIUM. Alerts from these rules work alongside concise briefs and in-depth profiles provided in the Windows Defender ATP console to help administrators address breach attempts by these activity groups.
For more information about Windows Defender ATP service in Windows 10, check out its features and capabilities and read more about why a post-breach detection approach is a key component of any enterprise security stack.
Details about PROMETHIUM and NEODYMIUM along with indicators of compromise can be found in the Microsoft Security Intelligence Report volume 21.
To test how Windows Defender ATP can help your organization detect, investigate, and respond to advanced attacks, sign up for a free trial.
Windows Defender ATP team

Talk to us
Questions, concerns, or insights on this story? Join discussions at the Microsoft community and Windows Defender Security Intelligence.
Follow us on Twitter @WDSecurity.




							Related Posts						






 








									News								



									Endpoint security								



									Microsoft Intune								

 

Published Feb 1				

						8 min read					




3 new ways the Microsoft Intune Suite offers security, simplification, and savings 



			The main components of the Microsoft Intune Suite are now generally available. Read about how consolidated endpoint management adds value and functionality for security teams.		








 








									Industry trends								



									Microsoft Intune								

 

Published Jan 29				

						<1 minute read					




Best practices in moving to cloud native endpoint management 



			This blog is the second of three that details our recommendation to adopt cloud native device management. Understand the lessons from various Intune customers in their journeys and how they achieved greater security, cost savings, and readiness for the future through their cloud transformations.		








 








									News								



									AI and machine learning								



									Microsoft Intune								

 

Published Sep 26				

						6 min read					




New security features in Windows 11 protect users and empower IT 



			Windows 11 is designed to simplify security with features from the chip to the cloud that are on by default. Since its launch, we’ve seen a 58 percent reduction in security. Learn more about the new features. 		








 








									Best practices								



									IoT security								



									Microsoft Defender for IoT								

 

Published Aug 7				

						9 min read					




Adopting guidance from the US National Cybersecurity Strategy to secure the Internet of Things 



			Microsoft is invested in helping partners create Internet of Things solutions with strong security products that support the March 2023 United States National Cybersecurity Strategy.		














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

































