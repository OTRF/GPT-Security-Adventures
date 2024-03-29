
Report 1

Summary:

The threat actor Storm-0558, based in China, acquired a Microsoft account consumer key to forge tokens and access OWA and Outlook.com. Microsoft conducted a technical investigation and found that a crash dump in April 2021 contained the key, allowing the threat actor to compromise a Microsoft engineer's corporate account. The key was leaked due to a race condition and moved to the debugging environment, where it was accessed by the threat actor. Microsoft introduced a common key metadata publishing endpoint in 2018, but developers did not update libraries to perform scope validation automatically, leading to the acceptance of requests for enterprise email using a consumer key. Microsoft has since made improvements to prevent similar incidents in the future. The report was published on July 11, 2023, detailing the findings of the investigation.

Region: China
Operating Sector: Technology
Type of Company: Microsoft
Novelty of Tools and Techniques: Use of acquired consumer key to access enterprise email, race condition exploitation, lack of key scope validation in libraries.





Report 2

Summary:
- Threat actor Storm-0558 targeted customer email data from approximately 25 organizations, including government agencies and public cloud consumer accounts in China.
- Storm-0558 used forged authentication tokens to access email accounts through credential harvesting, phishing campaigns, and OAuth token attacks.
- The threat actor displayed a high degree of technical tradecraft and operational security, targeting US and European diplomatic, economic, and legislative governing bodies.
- Storm-0558 utilized a shared malware tool called Cigril and deployed web shells like China Chopper on compromised servers.
- The threat actor acquired an inactive Microsoft account consumer signing key to forge authentication tokens for accessing Exchange Online and Outlook.com.
- Storm-0558 used PowerShell and Python scripts to extract email data, accessed dedicated infrastructure running SoftEther proxy software, and utilized a token web panel for interaction with Microsoft services.
- Microsoft mitigated the threat actor's activities by blocking the usage of acquired keys, revoking all MSA signing keys, and implementing defense in depth measures.
- Post-compromise activity was limited to email access and exfiltration for targeted users.
- No customer action is required to prevent threat actors from using the described techniques to access Exchange Online and Outlook.com.
- Indicators of compromise include IP addresses associated with Storm-0558's infrastructure and the thumbprint of the acquired signing key.





Report 3

Threat actor Storm-0558, attributed to China, compromised a Microsoft private encryption key (MSA key) allowing them to forge access tokens for Outlook Web Access (OWA) and Outlook.com. The incident, disclosed by Microsoft and CISA on July 21, 2023, was more extensive than initially thought, affecting Azure Active Directory applications beyond Outlook.com and Exchange Online. Storm-0558 exploited two security issues in Microsoft's token verification process. The compromised key could forge tokens for various Azure Active Directory applications, including personal account authentication for SharePoint, Teams, and OneDrive. Microsoft mitigated the risk by revoking the key and publishing attacker IOCs. The threat actor's capability to forge tokens posed a significant risk to applications trusting Microsoft's OpenID v2.0 certificates. The incident highlighted the importance of securing identity provider keys. The report detailed the technical aspects of the incident and provided recommendations for Azure users to detect and mitigate the threat.





Report 4

Summary: In September 2023, Chinese threat actor Storm-0558 breached Microsoft's cloud-based Exchange email platform, leading to the theft of at least 60,000 US State Department emails. The compromised State Department officials were primarily focused on Indo-Pacific diplomacy efforts. Storm-0558 exploited a zero-day validation vulnerability to generate counterfeit access tokens, allowing them to impersonate accounts within targeted organizations. Microsoft revoked the stolen signing key and expanded cloud logging data access to help detect similar breach attempts. The threat actor's capability to breach high-profile government accounts and use novel techniques like access token forgery demonstrates their advanced cyber-espionage tactics.





Report 5

Summary:
The threat actor Storm-0558, believed to be based in China, has been targeting media companies, think tanks, and telecommunications providers since at least 2021. Their main objective is to gain unauthorized access to email accounts through credential harvesting, phishing campaigns, and OAuth token attacks. Storm-0558 demonstrates a high level of technical expertise and operational security, with a focus on OAuth applications and token theft. They have been observed targeting individuals connected to Taiwan and Uyghur geopolitical interests in sectors such as government, media, and telecommunications in the USA and Europe. The threat actor's tooling and reconnaissance activities indicate a sophisticated and well-resourced operation. The group operates independently from other Chinese threat groups, with a motivation for information theft and espionage. The report does not specify a specific date or operation time window for their activities.


