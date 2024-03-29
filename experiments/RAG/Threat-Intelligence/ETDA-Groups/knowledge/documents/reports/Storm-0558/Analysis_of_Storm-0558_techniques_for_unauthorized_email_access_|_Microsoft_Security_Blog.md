# Reference for threat actor for "Storm-0558"

**Title**: Analysis of Storm-0558 techniques for unauthorized email access | Microsoft Security Blog

**Source**: https://www.microsoft.com/en-us/security/blog/2023/07/14/analysis-of-storm-0558-techniques-for-unauthorized-email-access/

## Content

























Analysis of Storm-0558 techniques for unauthorized email access | Microsoft Security Blog




























































 

 



















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




									10 min read								

Analysis of Storm-0558 techniques for unauthorized email access




											By										
Microsoft Threat Intelligence












					July 14, 2023				




 





 





 







											Threat actors										



											Storm										



											Token theft										



											Typhoon										






Executive summary 
On July 11, 2023, Microsoft published two blogs detailing a malicious campaign by a threat actor tracked as Storm-0558 that targeted customer email that we’ve detected and mitigated: Microsoft Security Response Center and Microsoft on the Issues. As we continue our investigation into this incident and deploy defense in depth measures to harden all systems involved, we’re providing this deeper analysis of the observed actor techniques for obtaining unauthorized access to email data, tools, and unique infrastructure characteristics.
September 6, 2023 update – Microsoft has completed a comprehensive technical investigation into Storm-0558’s acquisition of the Microsoft account consumer signing key. Investigation findings are released on the Microsoft Security Response Center blog: Results of major technical investigations for Storm-0558 key acquisition. 

As described in more detail in our July 11 blogs, Storm-0558 is a China-based threat actor with espionage objectives. Beginning May 15, 2023, Storm-0558 used forged authentication tokens to access user email from approximately 25 organizations, including government agencies and related consumer accounts in the public cloud. No other environment was impacted. Microsoft has successfully blocked this campaign from Storm-0558. As with any observed nation-state actor activity, Microsoft has directly notified targeted or compromised customers, providing them with important information needed to secure their environments.
Since identification of this malicious campaign on June 16, 2023, Microsoft has identified the root cause, established durable tracking of the campaign, disrupted malicious activities, hardened the environment, notified every impacted customer, and coordinated with multiple government entities. We continue to investigate and monitor the situation and will take additional steps to protect customers.
Actor overview
Microsoft Threat Intelligence assesses with moderate confidence that Storm-0558 is a China-based threat actor with activities and methods consistent with espionage objectives. While we have discovered some minimal overlaps with other Chinese groups such as Violet Typhoon (ZIRCONIUM, APT31), we maintain high confidence that Storm-0558 operates as its own distinct group.
Figure 1 shows Storm-0558 working patterns from April to July 2023; the actor’s core working hours are consistent with working hours in China, Monday through Friday from 12:00 AM UTC (8:00 AM China Standard time) through 09:00 AM UTC (5:00 PM China Standard Time).
Figure 1. Heatmap of observed Stom-0558 activity by day of week and hour (UTC).
In past activity observed by Microsoft, Storm-0558 has primarily targeted US and European diplomatic, economic, and legislative governing bodies, and individuals connected to Taiwan and Uyghur geopolitical interests. 
Historically, this threat actor has displayed an interest in targeting media companies, think tanks, and telecommunications equipment and service providers. The objective of most Storm-0558 campaigns is to obtain unauthorized access to email accounts belonging to employees of targeted organizations. Storm-0558 pursues this objective through credential harvesting, phishing campaigns, and OAuth token attacks. This threat actor has displayed an interest in OAuth applications, token theft, and token replay against Microsoft accounts since at least August 2021. Storm-0558 operates with a high degree of technical tradecraft and operational security. The actors are keenly aware of the target’s environment, logging policies, authentication requirements, policies, and procedures. Storm-0558’s tooling and reconnaissance activity suggests the actor is technically adept, well resourced, and has an in-depth understanding of many authentication techniques and applications.
In the past, Microsoft has observed Storm-0558 obtain credentials for initial access through phishing campaigns. The actor has also exploited vulnerabilities in public-facing applications to gain initial access to victim networks. These exploits typically result in web shells, including China Chopper, being deployed on compromised servers. One of the most prevalent malware families used by Storm-0558 is a shared tool tracked by Microsoft as Cigril. This family exists in several variants and is launched using dynamic-link library (DLL) search order hijacking.
After gaining access to a compromised system, Storm-0558 accesses credentials from a variety of sources, including the LSASS process memory and Security Account Manager (SAM) registry hive. Microsoft assesses that once Storm-0558 has access to the desired user credentials, the actor signs into the compromised user’s cloud email account with the valid account credentials. The actor then collects information from the email account over the web service.
Initial discovery and analysis of current activity
On June 16, 2023, Microsoft was notified by a customer of anomalous Exchange Online data access. Microsoft analysis attributed the activity to Storm-0558 based on established prior TTPs. We determined that Storm-0558 was accessing the customer’s Exchange Online data using Outlook Web Access (OWA). Microsoft’s investigative workflow initially assumed the actor was stealing correctly issued Azure Active Directory (Azure AD) tokens, most probably using malware on infected customer devices. Microsoft analysts later determined that the actor’s access was utilizing Exchange Online authentication artifacts, which are typically derived from Azure AD authentication tokens (Azure AD tokens). Further in-depth analysis over the next several days led Microsoft analysts to assess that the internal Exchange Online authentication artifacts did not correspond to Azure AD tokens in Microsoft logs.
Microsoft analysts began investigating the possibility that the actor was forging authentication tokens using an acquired Azure AD enterprise signing key. In-depth analysis of the Exchange Online activity discovered that in fact the actor was forging Azure AD tokens using an acquired Microsoft account (MSA) consumer signing key. This was made possible by a validation error in Microsoft code. The use of an incorrect key to sign the requests allowed our investigation teams to see all actor access requests which followed this pattern across both our enterprise and consumer systems. Use of the incorrect key to sign this scope of assertions was an obvious indicator of the actor activity as no Microsoft system signs tokens in this way. Use of acquired signing material to forge authentication tokens to access customer Exchange Online data differs from previously observed Storm-0558 activity. Microsoft’s investigations have not detected any other use of this pattern by other actors and Microsoft has taken steps to block related abuse.
Actor techniques
Token forgery
Authentication tokens are used to validate the identity of entities requesting access to resources – in this case, email. These tokens are issued to the requesting entity (such as a user’s browser) by identity providers like Azure AD. To prove authenticity, the identity provider signs the token using a private signing key. The relying party validates the token presented by the requesting entity by using a public validation key. Any request whose signature is correctly validated by the published public validation key will be trusted by the relying party. An actor that can acquire a private signing key can then create falsified tokens with valid signatures that will be accepted by relying parties. This is called token forgery.
Storm-0558 acquired an inactive MSA consumer signing key and used it to forge authentication tokens for Azure AD enterprise and MSA consumer to access OWA and Outlook.com. All MSA keys active prior to the incident – including the actor-acquired MSA signing key – have been invalidated. Azure AD keys were not impacted. The method by which the actor acquired the key is a matter of ongoing investigation. Though the key was intended only for MSA accounts, a validation issue allowed this key to be trusted for signing Azure AD tokens. This issue has been corrected.
As part of defense in depth, we continuously update our systems. We have substantially hardened key issuance systems since the acquired MSA key was initially issued. This includes increased isolation of the systems, refined monitoring of system activity, and moving to the hardened key store used for our enterprise systems. We have revoked all previously active keys and issued new keys using these updated systems. Our active investigation indicates these hardening and isolation improvements disrupt the mechanisms we believe the actor could have used to acquire MSA signing keys. No key-related actor activity has been observed since Microsoft invalidated the actor-acquired MSA signing key. Further, we have seen Storm-0558 transition to other techniques, which indicates that the actor is not able to utilize or access any signing keys. We continue to explore other ways the key may have been acquired and add additional defense in depth measures.
Identity techniques for access
Once authenticated through a legitimate client flow leveraging the forged token, the threat actor accessed the OWA API to retrieve a token for Exchange Online from the GetAccessTokenForResource API used by OWA. The actor was able to obtain new access tokens by presenting one previously issued from this API due to a design flaw. This flaw in the GetAccessTokenForResourceAPI has since been fixed to only accept tokens issued from Azure AD or MSA respectively. The actor used these tokens to retrieve mail messages from the OWA API. 
Actor tooling
Microsoft Threat Intelligence routinely identifies threat actor capabilities and leverages file intelligence to facilitate our protection of Microsoft customers. During this investigation, we identified several distinct Storm-0558 capabilities that facilitate the threat actor’s intrusion techniques. The capabilities described in this section are not expected to be present in the victim environment.
Storm-0558 uses a collection of PowerShell and Python scripts to perform REST API calls against the OWA Exchange Store service. For example, Storm-0558 has the capability to use minted access tokens to extract email data such as:

Download emails
Download attachments
Locate and download conversations
Get email folder information

The generated web requests can be routed through a Tor proxy or several hardcoded SOCKS5 proxy servers. The threat actor was observed using several User-Agents when issuing web requests, for example:

Client=REST;Client=RESTSystem;;
Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.159 Safari/537.36
Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/106.0.0.0 Safari/537.36 Edg/106.0.1370.52
“Microsoft Edge”;v=”113″, “Chromium”;v=”113″, “Not-A.Brand”;v=”24″

The scripts contain highly sensitive hardcoded information such as bearer access tokens and email data, which the threat actor uses to perform the OWA API calls. The threat actor has the capability to refresh the access token for use in subsequent OWA commands.
Figure 2. Python code snippet of the token refresh functionality used by the threat actor.
Figure 3. PowerShell code snippet of OWA REST API call to GetConversationItems.
Actor infrastructure
During significant portions of Storm-0558’s malicious activities, the threat actor leveraged dedicated infrastructure running the SoftEther proxy software. Proxy infrastructure complicates detection and attribution of Storm-0558 activities. During our response, Microsoft Threat Intelligence identified a unique method of profiling this proxy infrastructure and correlated with behavioral characteristics of the actor intrusion techniques. Our profile was based on the following facets:

Hosts operating as part of this network present a JARM fingerprint consistent with SoftEther VPN: 06d06d07d06d06d06c42d42d000000cdb95e27fd8f9fee4a2bec829b889b8b.
Presented x509 certificate has expiration date of December 31, 2037.
Subject information within the x509 certificate does not contain “softether”.

Over the course of the campaign, the IPs listed in the table below were used during the corresponding timeframes.
IP addressFirst seenLast seenDescription51.89.156[.]1533/9/20237/10/2023SoftEther proxy176.31.90[.]1293/28/20236/29/2023SoftEther proxy137.74.181[.]1003/31/20237/11/2023SoftEther proxy193.36.119[.]454/19/20237/7/2023SoftEther proxy185.158.248[.]1594/24/20237/6/2023SoftEther proxy131.153.78[.]1885/6/20236/29/2023SoftEther proxy37.143.130[.]1465/12/20235/19/2023SoftEther proxy146.70.157[.]455/12/20236/8/2023SoftEther proxy185.195.200[.]395/15/20236/29/2023SoftEther proxy185.38.142[.]2295/15/20237/12/2023SoftEther proxy146.70.121[.]445/17/20236/29/2023SoftEther proxy31.42.177[.]1815/22/20235/23/2023SoftEther proxy185.51.134[.]526/7/20237/11/2023SoftEther proxy173.44.226[.]706/9/20237/11/2023SoftEther proxy45.14.227[.]2336/12/20236/26/2023SoftEther proxy185.236.231[.]1096/12/20237/3/2023SoftEther proxy178.73.220[.]1496/16/20237/12/2023SoftEther proxy45.14.227[.]2126/19/20236/29/2023SoftEther proxy91.222.173[.]2256/20/20237/1/2023SoftEther proxy146.70.35[.]1686/22/20236/29/2023SoftEther proxy146.70.157[.]2136/26/20236/30/2023SoftEther proxy31.42.177[.]2016/27/20236/29/2023SoftEther proxy5.252.176[.]87/1/20237/1/2023SoftEther proxy80.85.158[.]2157/1/20237/9/2023SoftEther proxy193.149.129[.]887/2/20237/12/2023SoftEther proxy5.252.178[.]687/3/20237/11/2023SoftEther proxy116.202.251[.]87/4/20237/7/2023SoftEther proxy185.158.248[.]936/25/202306/26/2023SoftEther proxy20.108.240[.]2526/25/20237/5/2023SoftEther proxy146.70.135[.]1825/18/20236/22/2023SoftEther proxy

As early as May 15, 2023, Storm-0558 shifted to using a separate series of dedicated infrastructure servers specifically for token replay and interaction with Microsoft services. It is likely that the dedicated infrastructure and supporting services configured on this infrastructure offered a more efficient manner of facilitating the actor’s activities. The dedicated infrastructure would host an actor-developed web panel that presented an authentication page at URI /#/login. The observed sign-in pages had one of two SHA-1 hashes: 80d315c21fc13365bba5b4d56357136e84ecb2d4 and 931e27b6f1a99edb96860f840eb7ef201f6c68ec.
Figure 4. Token web panel sign-in page with SHA-1 hashes.
As part of the intelligence-driven response to this campaign, and in support of tracking, analyzing, and disrupting actor activity, analytics were developed to proactively track the dedicated infrastructure. Through this tracking, we identified the following dedicated infrastructure.
IP addressFirst seenLast seenDescription195.26.87[.]2195/15/20236/25/2023Token web panel185.236.228[.]1835/24/20236/11/2023Token web panel85.239.63[.]1606/7/20236/11/2023Token web panel193.105.134[.]586/24/20236/25/2023Token web panel146.0.74[.]166/28/20237/4/2023Token web panel91.231.186[.]2266/29/20237/4/2023Token web panel91.222.174[.]416/29/20237/3/2023Token web panel185.38.142[.]2496/29/20237/2/2023Token web panel

The last observed dedicated token replay infrastructure associated with this activity was stood down on July 4, 2023, roughly one day following the coordinated mitigation conducted by Microsoft. 
Post-compromise activity
Our telemetry and investigations indicate that post-compromise activity was limited to email access and exfiltration for targeted users.
Mitigation and hardening
No customer action is required to mitigate the token forgery technique or validation error in OWA or Outlook.com. Microsoft has mitigated this issue on customers’ behalf as follows:

On June 26, OWA stopped accepting tokens issued from GetAccessTokensForResource for renewal, which mitigated the token renewal being abused.
On June 27, Microsoft blocked the usage of tokens signed with the acquired MSA key in OWA preventing further threat actor enterprise mail activity.
On June 29, Microsoft completed replacement of the key to prevent the threat actor from using it to forge tokens. Microsoft revoked all MSA signing which were valid at the time of the incident, including the actor-acquired MSA key. The new MSA signing keys are issued in substantially updated systems which benefit from hardening not present at issuance of the actor-acquired MSA key:Microsoft has increased the isolation of these systems from corporate environments, applications, and users.Microsoft has refined monitoring of all systems related to key activity, and increased automated alerting related to this monitoring.

Microsoft has moved the MSA signing keys to the key store used for our enterprise systems.


On July 3, Microsoft blocked usage of the key for all impacted consumer customers to prevent use of previously-issued tokens.

Ongoing monitoring indicates that all actor activity related to this incident has been blocked. Microsoft will continue to monitor Storm-0558 activity and implement protections for our customers.
Recommendations
Microsoft has mitigated this activity on our customers’ behalf for Microsoft services. No customer action is required to prevent threat actors from using the techniques described above to access Exchange Online and Outlook.com.
Indicators of compromise
IndicatorTypeFirst seenLast seenDescriptiond4b4cccda9228624656bff33d8110955779632aaThumbprint  Thumbprint of acquired signing key195.26.87[.]219IPv45/15/20236/25/2023Token web panel185.236.228[.]183IPv45/24/20236/11/2023Token web panel85.239.63[.]160IPv46/7/20236/11/2023Token web panel193.105.134[.]58IPv46/24/20236/25/2023Token web panel146.0.74[.]16IPv46/28/20237/4/2023Token web panel91.231.186[.]226IPv46/29/20237/4/2023Token web panel91.222.174[.]41IPv46/29/20237/3/2023Token web panel185.38.142[.]249IPv46/29/20237/2/2023Token web panel51.89.156[.]153IPv43/9/20237/10/2023SoftEther proxy176.31.90[.]129IPv43/28/20236/29/2023SoftEther proxy137.74.181[.]100IPv43/31/20237/11/2023SoftEther proxy193.36.119[.]45IPv44/19/20237/7/2023SoftEther proxy185.158.248[.]159IPv44/24/20237/6/2023SoftEther proxy131.153.78[.]188IPv45/6/20236/29/2023SoftEther proxy37.143.130[.]146IPv45/12/20235/19/2023SoftEther proxy146.70.157[.]45IPv45/12/20236/8/2023SoftEther proxy185.195.200[.]39IPv45/15/20236/29/2023SoftEther proxy185.38.142[.]229IPv45/15/20237/12/2023SoftEther proxy146.70.121[.]44IPv45/17/20236/29/2023SoftEther proxy31.42.177[.]181IPv45/22/20235/23/2023SoftEther proxy185.51.134[.]52IPv46/7/20237/11/2023SoftEther proxy173.44.226[.]70IPv46/9/20237/11/2023SoftEther proxy45.14.227[.]233IPv46/12/20236/26/2023SoftEther proxy185.236.231[.]109IPv46/12/20237/3/2023SoftEther proxy178.73.220[.]149IPv46/16/20237/12/2023SoftEther proxy45.14.227[.]212IPv46/19/20236/29/2023SoftEther proxy91.222.173[.]225IPv46/20/20237/1/2023SoftEther proxy146.70.35[.]168IPv46/22/20236/29/2023SoftEther proxy146.70.157[.]213IPv46/26/20236/30/2023SoftEther proxy31.42.177[.]201IPv46/27/20236/29/2023SoftEther proxy5.252.176[.]8IPv47/1/20237/1/2023SoftEther proxy80.85.158[.]215IPv47/1/20237/9/2023SoftEther proxy193.149.129[.]88IPv47/2/20237/12/2023SoftEther proxy5.252.178[.]68IPv47/3/20237/11/2023SoftEther proxy116.202.251[.]8IPv47/4/20237/7/2023SoftEther proxy
Further reading
For the latest security research from the Microsoft Threat Intelligence community, check out the Microsoft Threat Intelligence Blog: https://aka.ms/threatintelblog.
To get notified about new publications and to join discussions on social media, follow us on Twitter at https://twitter.com/MsftSecIntel. 




							Related Posts						






 








									Research								



									Threat intelligence								



									Microsoft Copilot for Security								



									Threat actors								

 

Published Feb 14				

						12 min read					




Staying ahead of threat actors in the age of AI 



			Microsoft, in collaboration with OpenAI, is publishing research on emerging threats in the age of AI, focusing on identified activity associated with known threat actors Forest Blizzard, Emerald Sleet, Crimson Sandstorm, and others. The observed activity includes prompt-injections, attempted misuse of large language models (LLM), and fraud.		








 








									Research								



									Threat intelligence								



									Microsoft Defender								



									Cybercrime								

 

Published Dec 12				

						16 min read					




Threat actors misuse OAuth applications to automate financially driven attacks 



			Microsoft Threat Intelligence presents cases of threat actors misusing OAuth applications as automation tools in financially motivated attacks. 		








 








									Research								



									Incident response								



									Microsoft Entra								



									Cloud threats								

 

Published Dec 5				

						28 min read					




Microsoft Incident Response lessons on preventing cloud identity compromise 



			In real-world customer engagements, Microsoft IR sees combinations of issues and misconfigurations that could lead to attacker access to customers’ Microsoft Entra ID tenants. Reducing risk and exposure of your most privileged accounts plays a critical role in preventing or detecting attempts at tenant-wide compromise.		








 








									Research								



									Threat intelligence								



									Threat actors								

 

Published Nov 9				

						6 min read					




Microsoft shares threat intelligence at CYBERWARCON 2023 



			At the CYBERWARCON 2023 conference, Microsoft and LinkedIn analysts are presenting several sessions detailing analysis across multiple sets of threat actors and related activity, demonstrating Microsoft Threat Intelligence’s ongoing efforts to track threat actors, protect customers, and share information with the wider security community.		














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

































