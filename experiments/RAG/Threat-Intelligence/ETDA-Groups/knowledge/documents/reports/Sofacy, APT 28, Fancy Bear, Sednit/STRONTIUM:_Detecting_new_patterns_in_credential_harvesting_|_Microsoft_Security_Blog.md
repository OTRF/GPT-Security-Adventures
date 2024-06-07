# Reference for threat actor for "Sofacy, APT 28, Fancy Bear, Sednit"

**Title**: STRONTIUM: Detecting new patterns in credential harvesting | Microsoft Security Blog

**Source**: https://www.microsoft.com/security/blog/2020/09/10/strontium-detecting-new-patters-credential-harvesting/

## Content

























STRONTIUM: Detecting new patterns in credential harvesting | Microsoft Security Blog






























































 

 



















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



													Social engineering / phishing												




									5 min read								

STRONTIUM: Detecting new patterns in credential harvesting




											By										
Microsoft Threat Intelligence












					September 10, 2020				




 





 





 







											Forest Blizzard (STRONTIUM)										





Microsoft has tied STRONTIUM to a newly uncovered pattern of Office365 credential harvesting activity aimed at US and UK organizations directly involved in political elections. Analysts from Microsoft Threat Intelligence Center (MSTIC) and Microsoft Identity Security have been tracking this new activity since April 2020. Credential harvesting is a known tactic used by STRONTIUM to obtain valid credentials that enable future surveillance or intrusion operations. Subsequent analysis revealed that between September 2019 and June 2020, STRONTIUM launched credential harvesting attacks against tens of thousands of accounts at more than 200 organizations. In the two weeks between August 18 and September 3, the same attacks targeted 6,912 accounts belonging to 28 organizations. None of these accounts were successfully compromised.
Not all the targeted organizations were election-related. However, we felt it important to highlight a potential emerging threat to the 2020 US Presidential Election and future electoral contests in the UK.
Microsoft CVP Customer Security and Trust, Tom Burt provided some additional details on this campaign in his recent On The Issues blog post. The purpose of this post is to provide defenders in any organization, but especially those directly or indirectly affiliated with electoral systems, insight into the technical nature of this activity. By providing these details, we hope to enable better defense against future attacks and share best practices for securing cloud environments against this type of activity.
Tactical Details
STRONTIUM relied heavily upon spear phishing in its credential harvesting efforts leading up to the 2016 US presidential election. In 2016, spear-phishing was the most common tactic for stealing credentials from targeted accounts. This time around, STRONTIUM appears to be taking a different approach, namely, brute-force/password-spray tooling. This shift in tactics, also made by several other nation-state actors, allows them to execute large-scale credential harvesting operations in a more anonymized manner. The tooling STRONTIUM is using routes its authentication attempts through a pool of approximately 1,100 IPs, the majority associated with the Tor anonymizing service. This pool of infrastructure has evolved over time, with an average of approximately 20 IPs added and removed from it per day. STRONTIUM’s tooling alternates its authentication attempts amongst this pool of IPs approximately once per second. Considering the breadth and speed of this technique, it seems likely that STRONTIUM has adapted its tooling to use an anonymizer service to obfuscate its activity, evade tracking, and avoid attribution.
During the two-week period, August 19 – September 3, STRONTIUM’s credential harvesting tooling utilized a daily average of 1,294 IPs associated with 536 netblocks and 273 ASNs. Of these netblocks, some were much more heavily utilized by the tooling than others, both in terms of the total number of authentications attempted from them and the total number of IPs utilized within them. Figure 1 below represents the 5 netblocks from which the highest number of total auth attempts were observed. As highlighted in the table, several of these netblocks had much higher IP utilization rates than the rest. This observed behavior indicates that the underlying anonymization services providing the infrastructure backbone for STRONTIUM auth attempts are, in a sense, over-serving IPs in these specific netblocks.

Figure 1: Highest volume netblocks used in STRONTIUM auth attempts.
The fact that the anonymization service is over-serving specific netblocks gives defenders an opportunity to hunt for activity associated both with this STRONTIUM activity or other malicious tooling that is utilizing the same anonymization service. The following Azure Sentinel query (GitHub link) is designed to identify failed authentication attempts from the three highest-signal, highest-utilization netblocks highlighted above, and group the results by UserAgent.

Microsoft Threat Protection (MTP) also provides a platform for users to identify failed authentication attempts. The following query will give MTP users the ability to hunt and address these threats as well:
MSTIC has observed that the STRONTIUM tooling operates in two modes when targeting accounts: brute-force and password-spray.
In password-spray mode, the tooling attempts username: password combinations in a ‘low-‘n-slow’ manner. Organizations targeted by the tooling running in this mode typically see approximately four authentication attempts per hour per targeted account over the course of several days or weeks, with nearly every attempt originating from a different IP address.
In brute-force mode, the tooling attempts many username: password attempts very rapidly for a much shorter time period. Organizations targeted by the tooling running in this mode typically see over 300 authentication attempts per hour per targeted account over the course of several hours or days.
Tooling Operating ModeAvg ## of Attempts Per Account Per HourAvg # Of IPs Utilized for Auth Attempts Per Account Per Hour Avg Length of AttackPassword-Spray44Days-WeeksBrute-Force335200Hours-Days
Organizations targeted by STRONTIUM using this tooling saw auth attempts against an average of 20% of their total accounts. In some instances, MSTIC assesses the tooling may have discovered these accounts simply by attempting authentications against a large number of possible account names until it found ones that were valid.
Guidance: Proactive defense 
There are some very simple steps businesses and targeted individuals can take to significantly improve the security of their accounts and make these types of attacks much more difficult.
1. Enable multi-factor authentication
We have seen clear proof that enabling multi-factor authentication (MFA) across both business and personal email accounts successfully thwarts the majority of credential harvesting attacks. Our colleagues in Azure Active Directory put it more precisely—

“… doing any form of MFA takes you out of reach of most attacks. MFA (using any mechanism) is just too costly to break – unless a highly motivated attacker is after that high-value account or asset.”

Blog: Your password doesn’t matter—but MFA does!


However, most enterprise accounts have not implemented this simple protection:

“When we evaluate all the tokens issued with MFA claims, we see that less than 10% of users use MFA per month in our enterprise accounts (and that includes on-premises and third-party MFA). Until MFA is more broadly adopted, there is little reason for attackers to evolve.”

Blog: All your creds are belong to us!


2. Actively monitor failed authentications
When monitoring login activity in your accounts, look for any type of discernable patterns in these failed authentications and track them over time. Password spray is an increasingly common tactic of nation-state actors.
You can also maintain broader visibility into behavioral anomalies like failed login attempts by running detections and monitoring using Microsoft Cloud App Security (MCAS) which monitors user sessions for third-party cloud apps, including G-Suite, AWS, and Salesforce. The MCAS detection engine looks for anomalous user activity for indicators of compromise. One indicator, “multiple failed login attempts,” can be used to create a dynamic baseline per user, across the tenant, and alert on anomalous login behavior that may represent an active brute force or password spray attack.
Microsoft Threat Protection (MTP) can help to automatically track and rebuild the Incident view of all the compromised identities by password-spray leveraged later by the attacker to expand the breach to endpoint or cloud assets.
3. Test your organization’s resilience
Attack Simulator in Office 365 ATP lets you run realistic, but simulated phishing and password attack campaigns in your organization. Pick a password and then run the campaign against as many users as you want. The results will let you know how many people are using that password. Use the data to train users and build your custom list of banned passwords.




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



									Incident response								



									Microsoft Incident Response								



									Attacker techniques, tools, and infrastructure								

 

Published Mar 24				

						19 min read					




Guidance for investigating attacks using CVE-2023-23397 



			This guide provides steps organizations can take to assess whether users have been targeted or compromised by threat actors exploiting CVE-2023-23397. 		











									News								



									Incident response								



									Microsoft Entra								

 

Published Sep 24				

						6 min read					




Delivering security innovation that puts Microsoft’s experience to work for you 



			Cybersecurity is the central challenge of our digital age. Without it, everything from our personal email accounts and privacy to the way we do business, and all types of critical infrastructure, are under threat. As attackers evolve, staying ahead of these threats is getting harder. Microsoft can help. We focus on three areas: running security operations that work for you, building enterprise-class technology, and driving partnerships for a heterogeneous world. We can tip the scales in favor of the good guys and make the world a safer place.		











									Research								



									Threat intelligence								



									Business email compromise								

 

Published Nov 16				

						2 min read					




Microsoft Security Intelligence Report: Strontium 



			The Microsoft Security Intelligence Report (SIR) provides a regular snapshot of the current threat landscape, using data from more than 600 million computers worldwide. The latest report (SIRv19) was released this week and includes a detailed analysis of the actor group STRONTIUM – a group that uses zero-day exploits to collect the sensitive information of […]		














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

































