# Reference for threat actor for "8220 Gang"

**Title**: Imperva Detects Undocumented 8220 Gang Activities | Imperva

**Source**: https://www.imperva.com/blog/imperva-detects-undocumented-8220-gang-activities/

## Content











WP 

 























































Imperva Detects Undocumented 8220 Gang Activities | Imperva












































































































Under DDoS Attack?
 
1-866-777-9980
 












Login




LoginCloud Security ConsoleRASP Console
English




EnglishENDeutschDEEspañolESFrançaisFRPortuguêsPT-BR日本語日本語한국어KR中文CN 




Under DDoS Attack?
 
1-866-777-9980
 
Contact UsContact Us 


Why ImpervaProducts
Products

Application PerformanceApplication SecurityData SecurityNetwork SecurityImperva PlansApplication PerformanceApplication Performance OverviewOptimize content delivery and user experienceContent Delivery NetworkBoost website performance with caching and compressionWaiting RoomVirtual queuing to control visitor trafficThe importance of a resilient CDN for digital performanceGet featured reportApplication SecurityApplication Security OverviewIndustry-leading application and API protectionWeb Application FirewallInstantly secure applications from the latest threatsAdvanced Bot ProtectionIdentify and mitigate the most sophisticated bad botAPI SecurityDiscover shadow APIs and the sensitive data they handleDDoS ProtectionSecure all assets at the edge with guaranteed uptimeClient-Side ProtectionVisibility and control over third-party JavaScript codeRuntime ProtectionSecure workloads from unknown threats and vulnerabilitiesServerless ProtectionUncover security weaknesses on serverless environmentsAttack AnalyticsComplete visibility into your latest attacks and threatsImperva named a security leader in the SecureIQlab CyberRisk ReportGet featured reportData SecurityData Security OverviewProtect all data and ensure compliance at any scaleData Security FabricMulticloud, hybrid security platform protecting all data typesBusiness CapabilitiesData security at scaleData security for multicloudRisk analytics & insightsData compliance at scaleData discovery & classificationCloud Data SecuritySaaS-based data posture management and protectionThe Imperva AdvantageBroadest coverageProtect any data sourceEcosystem integrationUnified visibilityIDC Spotlight: Effective Multicloud Data SecurityGet featured reportNetwork SecurityNetwork Security OverviewProtection and control over your network infrastructureDDoS ProtectionSecure all assets at the edge with guaranteed uptimeGlobal DDoS Threat Landscape ReportGet featured reportImperva PlansSolutions
Solutions

By Use CaseBy IndustryImperva PlansBy Use CaseApplication SecurityStop software supply chain attacksMitigate account takeover attacksProtect modern web applicationsSecure API inventoriesProtect against online fraudEmbed security into DevOpsProtect applications from business logic abuseData SecuritySafeguard sensitive and personal dataAdvance data governanceAssure data compliance and privacySecurely move data to the cloudObserve data risk managementMonitor user behavior analyticsData encryption and cryptographic solutionsNetwork SecurityDefend DDoS attacks at scaleSecure business continuity in the event of an outageApplication PerformanceEnsure consistent application performanceBy IndustrySolutions by IndustryDefense-in-depth security for every industryGovernmentHealthcareFinancial ServicesTelecom & ISPsRetailThe State of Security within eCommerce 2022Get free reportImperva PlansSupport
Support

SupportSupportLooking for technical support or services, please review our various channels belowTechnical SupportServicesImperva UniversityCommunitySupport Portal LoginDocumentationEOL PolicyPartners
Partners

Channel PartnersTechnology Alliance PartnersChannel PartnersChannel Partners ProgramLooking for an Imperva partner? Find an approved one with the expertise to help youChannel PartnersFind a PartnerPartner Portal LoginImperva reimagines partner program: Imperva AccelerateLearn howTechnology Alliance PartnersTechnology Alliance PartnersImperva collaborates with the top technology companiesTechnology Alliance Partners (TAP)Become a TAPFind a TAPProtect your Cloudera data with ImpervaLearn more Customers
Customers

Application Security Customer StoriesData Security Customer StoriesSee all Customer StoriesApplication Security Customer StoriesApplication Security Customer StoriesLearn how Imperva enables and protects industry leadersTower ensures website visibility and uninterrupted business operationsSmallpdf protects its customers and ensures availabilityQuálitas continues its quality services using Imperva Application SecurityLearn howData Security Customer StoriesData Security Customer StoriesLearn how Imperva enables and protects industry leadersBanco Popular streamlines operations and lowers operational costsDiscovery Inc. tackles data compliance in public cloud with Imperva Data Security FabricDiscovery Inc. tackles data compliance in public cloudLearn howSee all Customer StoriesResources
Resources

ResourcesThreat ResearchLearning AssetsResourcesResourcesGet all the information you need about Imperva products and solutionsResource LibraryBlogWebinarsCase StudiesPrivacy, Compliance & Trust CenterImperva CertificationsNew Vulnerability in Popular Widget Shows Risks of Third-Party CodeRead moreThreat ResearchThreat ResearchStay informed on the latest threats and vulnerabilitiesThreat Research OverviewCyber Threat IndexCyber Attack MapFree ToolsNetwork MapCyber Threat IndexLatest threat analysisLearning AssetsLearning AssetsExpand and share your knowledgeLearning CenterApplication Security GuideData Security GuideImperva CommunityDocumentation PortalBrowse the Imperva Learning Center for the latest cybersecurity topicsExplore nowCompany
Company

CompanyCompanyGet to know us, beyond our products and servicesAbout UsEventsCareersPress & AwardsContact InformationImperva ESG ReportsRead more 












Home > Blog > Imperva Detects Undocumented 8220 Gang Activities 












Imperva Detects Undocumented 8220 Gang Activities

Imperva Threat Research 















 
 Daniel Johnston Dec 14, 2023  3 min read










 


Imperva Threat Research has detected previously undocumented activity from the 8220 gang, which is known for the mass deployment of malware using a variety of continuously evolving TTPs. This threat actor has been known to target both Windows and Linux web servers with cryptojacking malware. 
In this blog, we will detail recent activity, attack vectors used by the group, and share the indicators of compromise (IoCs) from the group’s most recent and previously unknown campaigns. Imperva customers are protected against this group’s known activities. All organizations should maintain up-to-date patches and security.
History
The 8220 gang, widely believed to be of Chinese origin, was first identified by Cisco Talos in 2017 targeting Drupal, Hadoop YARN, and Apache Struts2 applications to propagate cryptojacking malware. Since then, various other researchers have provided updates on the evolving tactics, techniques and procedures (TTPs) leveraged by the group, including exploitation of Confluence and Log4j vulnerabilities. Most recently, Trend Micro disclosed evidence of the group leveraging the Oracle WebLogic vulnerability CVE-2017-3506 to infect targeted systems. 
Evolving TTPs
As well as the recently disclosed use of CVE-2021-44228 and CVE-2017-3506, Imperva Threat Research observed the group’s attempted exploitation of CVE-2020-14883, a Remote Code Execution vulnerability in Oracle WebLogic Server, to propagate malware.
This vulnerability allows remote authenticated attackers to execute code using a gadget chain and is commonly chained with CVE-2020-14882 (an authentication bypass vulnerability also affecting Oracle Weblogic Server) or the use of leaked, stolen, or weak credentials. Exploitation of these vulnerabilities is well documented. Therefore, it is easy to modify for the purposes of malware deployment. The 8220 gang uses two different gadget chains: one enables the loading of an XML file, which then contains a call to the other and enables execution of commands on the OS.

The group uses different variations of the supplied XML depending on the target OS:

The command used to target Linux hosts attempts to download one of a set of second phase files using a variety of different methods: cURL, wget, lwp-download and python urllib (base64 encoded), as well as a custom bash function that is also base64 encoded.

Decoded base64: calls to python 2 and 3 urllib:

Custom bash download function:

On Windows a simple PowerShell WebClient command is used to execute a downloaded PowerShell script:

In another variation of the attack, the group uses a different gadget chain to execute Java code without the requirement of an externally hosted XML file.

The injected Java code first evaluates whether the OS is Windows or Linux, and then executes the appropriate command strings, which are identical to the ones already outlined above.

From here, the downloaded files are executed, infecting the exploited hosts with known AgentTesla, rhajk and nasqa malware variants, shown in the VirusTotal screenshots below.



The chain of infection using CVE-2020-14883:

Activity Trends
The following graph shows recent activity attributed to the 8220 gang, all of which was mitigated by Imperva Cloud WAF. The group appears to be opportunistic when selecting their targets, with no clear trend in country or industry. Imperva Threat Research observed the group attacking healthcare, telecommunications, and financial services targets in the United States, South Africa, Spain, Columbia, and Mexico. The 8220 gang appears to use custom tools written in Python to launch their attack campaigns, and the attacking IPs—located in the US, Mexico and Russia—are associated with known hosting companies.

Imperva Mitigation
At the time of writing, Imperva Cloud WAF and on-prem WAF mitigates all of the web vulnerabilities known to be leveraged by the 8220 gang for their malicious activities. Recent vulnerabilities detected by Imperva and leveraged by the group include:

CVE-2017-3506 – Oracle WebLogic Server RCE
CVE-2019-2725 – Oracle WebLogic Server Authenticated Deserialization
CVE-2020-14883 – Oracle WebLogic Server Authenticated RCE
CVE-2021-26084 – Atlassian Confluence Server OGNL Injection RCE
CVE-2021-44228 – Apache Log4j JNDI RCE
CVE-2022-26134 – Atlassian Confluence Server RCE

Conclusion
The 8220 gang, a widely recognized threat actor driven by financial motives, has been under scrutiny by various research teams since 2017. The group relies on simple, publicly available exploits to target well-known vulnerabilities and exploit easy targets to achieve their objectives. While considered unsophisticated, they are constantly evolving their tactics and techniques to evade detection. 
Throughout our investigation, we observed that attributing attacks to this group was relatively straightforward due to their consistent use of easily traceable IoCs and TTPs, frequently reusing the same IP addresses, web servers, payloads, and attack tools. 
Despite the group’s lack of sophistication, it remains critical for enterprises to promptly patch their applications and implement multiple layers of security measures to safeguard against falling victim to such groups. Imperva Threat Research will maintain its vigilance in monitoring the activities of this and other threat actors, and ensuring security for our customers.
Latest 8220 gang IoCs
URLs

Source IPs

Malicious file hashes




Try Imperva for Free
Protect your business for 30 days on Imperva.

Start Now








Try Imperva for Free
Protect your business for 30 days on Imperva.
Start Now 

Suggested  Report
2023 Imperva Bad Bot Report Read more 











Trending





 


Imperva Threat Research 
CVE-2023-22524: RCE Vulnerability in Atlassian Companion for macOS 





 
 Ron Masas Dec 14, 2023  5 min read










 


Application Security 
...



Imperva Threat Research 




Online Retailers: Five Threats Targeting Your Business This Holiday Shopping Season 










 
 Erez Hasson,  Gabi Stapel Nov 8, 2023  13 min read










 


Imperva Threat Research 
Analysis: A Ransomware Attack on a PostgreSQL Database 


 
 Omri Cohen Oct 24, 2023  3 min read










 


Imperva Threat Research 
Database Ransomware: From Attack to Recovery 


 
 Omri Cohen Oct 19, 2023  7 min read










 


Imperva Threat Research 
DDoS Attacks Leveraged by Attackers in Israel Conflict 





 
 Gabi Stapel Oct 12, 2023  2 min read










 


Application Security 
...



Imperva Threat Research 




Protecting Against HTTP/2 Rapid Reset: CVE-2023-44487 










 
 Kunal Anand,  Nadav Avital Oct 10, 2023  1 min read












 






×

Subscribe to our blog





Thank you!

Keep an eye on that inbox for the latest news and industry updates.









 







+1 866 926 4678


Partners Imperva Partner Ecosystem
Channel Partners
Technology Alliances
Find a Partner
Partner Portal Login
 

Resources Imperva Blog
Resource Library
Case Studies
Learning Center
 

About Us Why Imperva
Who We Are
Events
Careers
Press & Awards
Contact Information
 

Network Network Map
System Status
 

Support Emergency DDoS Protection
Support Portal
Imperva Community
Documentation Portal
API Integration
Trust Center
 

Cookie Preferences Trust Center Modern Slavery Statement Privacy Legal



English




EnglishDeutschEspañolFrançaisPortuguês日本語中文 





+1 866 926 4678




English




EnglishDeutschEspañolFrançaisPortuguês日本語中文 


































































Cookie Preferences Trust Center Modern Slavery Statement Privacy Legal








Copyright © 2023 Imperva. All rights reserved








 



 






×


Protect Against Business Logic Abuse
Identify key capabilities to prevent attacks targeting your business logic
Download Now







 






×


The 10th Annual Bad Bot Report
The evolution of malicious automation over the last decade
Download Now







 






×


The State of Security Within eCommerce in 2022
Learn how automated threats and API attacks on retailers are increasing
Free Report







 






×

Prevoty is now part of the Imperva Runtime Protection


Protection against zero-day attacks
No tuning, highly-accurate out-of-the-box
Effective against OWASP top 10 vulnerabilities


Learn more here







 






×

Want to see Imperva in action?
Fill out the form and our experts will be in touch shortly to book your personal demo.





Thank you!

An Imperva security specialist will contact you shortly.




×



“Imperva prevented 10,000 attacks in the first 4 hours of Black Friday weekend with no latency to our online customers.”
Top 3 US Retailer













