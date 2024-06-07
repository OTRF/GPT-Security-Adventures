# Reference for threat actor for "Hexane"

**Title**: Lyceum .NET DNS Backdoor | Zscaler

**Source**: https://www.zscaler.com/blogs/security-research/lyceum-net-dns-backdoor

## Content
Lyceum .NET DNS Backdoor | ZscalerThis site uses JavaScript to provide a number of functions, to use this site please enable JavaScript in your browser.Concerned about VPN vulnerabilities? Learn how you can benefit from our VPN migration offer including 60 days free service.Talk to an expertCloseOpenSearchCXO REvolutionariesCareersPartnersSupportShowContact UsOptionsGet in touch1-408-533-0288Chat with usShowSign InOptionsZscaler Cloud Portal | AdminZscaler Cloud Portal One | AdminZscaler Cloud Portal Two | AdminZscaler Cloud Portal Three | AdminZscaler Cloud Portal Beta | Adminadmin.zscloud.netZscaler Private Access Sign-InHomeThe Zscaler ExperienceProducts & SolutionsPlatformResourcesCompanyRequest a demoopen searchopen navigationThe Zscaler ExperienceZscaler: A Leader in the 2023 Gartner® Magic Quadrant™ for Security Service Edge (SSE)Get the full reportYour world, securedExperience the transformative power of zero trust.The Zscaler DifferenceThe Zscaler DifferenceExperience the World’s Largest Security CloudCustomer Success StoriesAnalyst RecognitionMachine Learning and AI at ZscalerReduce Your Carbon FootprintZero Trust FundamentalsZero Trust FundamentalsWhat Is Zero Trust?What Is Security Service Edge (SSE)?What Is Secure Access Service Edge (SASE)?What Is Zero Trust Network Access (ZTNA)?What Is Secure Web Gateway (SWG)?What Is Cloud Access Security Broker (CASB)?What Is Cloud Native Application Protection Platform (CNAPP)?Zero Trust ResourcesProducts & SolutionsSecure Your UsersProvide users with seamless, secure, reliable access to applications and data.Secure Your WorkloadsBuild and run secure cloud apps, enable zero trust cloud connectivity, and protect workloads from data center to cloud.Secure Your IoT and OTProvide zero trust connectivity for IoT and OT devices and secure remote access to OT systems.ProductsProductsTransform your organization with 100% cloud native servicesSecure Internet Access (ZIA)Secure Private Access (ZPA)Digital Experience (ZDX)Data Protection (CASB/DLP)Posture ControlSolution AreasSolution AreasPropel your business with zero trust solutions that secure and connect your resourcesCyberthreat ProtectionData ProtectionZero Trust NetworkingBusiness AnalyticsVPN AlternativeZero Trust SASEAccelerate M&A IntegrationOptimize Digital ExperiencesZero Trust SD-WANZero Trust Cloud ConnectivityZero Trust for IoT/OTFind a Product or SolutionPartner IntegrationsIndustry and Market SolutionsPlatformZero Trust Exchange PlatformLearn how Zscaler delivers zero trust with a cloud native platform that is the world’s largest security cloudZero Trust Exchange PlatformTitle LinkTransform with Zero Trust ArchitectureTransform with Zero Trust ArchitecturePropel your transformation journeySecure Digital TransformationNetwork TransformationApplication TransformationSecurity TransformationSecure Your Business GoalsSecure Your Business GoalsAchieve your business and IT initiativesEnsure Secure Business ContinuityAccelerate M&A and DivestituresRecession-Proof Your EnterpriseSecure Your Hybrid WorkforceDownload Zscaler Client ConnectorResourcesLearn, connect, and get support.Explore tools and resources to accelerate your transformation and secure your worldLearn, connect, and get support.Title LinkAmplifying the voices of real-world digital and zero trust pioneersVisit nowResource CenterResource CenterStay up to date on best practicesResource LibraryBlogCustomer Success StoriesWebinarsZpediaEvents & TrainingsEvents & TrainingsFind programs, certifications, and eventsUpcoming EventsZenith LiveZscaler AcademyInteractive Zscaler Whiteboard WorkshopSecurity Research & ServicesSecurity Research & ServicesGet research and insights at your fingertipsThreatLabz AnalyticsToolsToolsTools designed for youSecurity PreviewSecurity and Risk AssessmentSecurity Advisory UpdatesDisclose a VulnerabilityExecutive Insights AppRansomware Protection ROI CalculatorCommunity & SupportCommunity & SupportConnect and find supportCustomer Success CenterZenith CommunityCXO REvolutionariesZscaler Help PortalExplore the latest Zscaler InnovationsIndustry & Market SolutionsIndustry & Market SolutionsSee solutions for your industry and countryPublic SectorHealthcareFinancial ServicesEducationSee allResource CenterResource CenterStay up to date on best practicesResource LibraryBlogCustomer Success StoriesWebinarsZpediaEvents & TrainingsEvents & TrainingsFind programs, certifications, and eventsUpcoming EventsZenith LiveZscaler AcademyInteractive Zscaler Whiteboard WorkshopSecurity Research & ServicesSecurity Research & ServicesGet research and insights at your fingertipsThreatLabz AnalyticsToolsToolsTools designed for youSecurity PreviewSecurity and Risk AssessmentSecurity Advisory UpdatesDisclose a VulnerabilityExecutive Insights AppRansomware Protection ROI CalculatorCommunity & SupportCommunity & SupportConnect and find supportCustomer Success CenterZenith CommunityCXO REvolutionariesZscaler Help PortalExplore the latest Zscaler InnovationsIndustry & Market SolutionsIndustry & Market SolutionsSee solutions for your industry and countryPublic SectorHealthcareFinancial ServicesEducationSee allCompanyAbout ZscalerDiscover how it began and where it’s goingPartnersMeet our partners and explore system integrators and technology alliancesNews & AnnouncementsStay up to date with the latest newsLeadership TeamMeet our management teamPartner IntegrationsExplore best-in-class partner integrations to help you accelerate digital transformationInvestor RelationsSee news, stock information, and quarterly reportsEnvironmental, Social & GovernanceLearn about our ESG approachCareersJoin our missionPress CenterFind everything you need to cover ZscalerComplianceUnderstand our adherence to rigorous standardsZenith VenturesUnderstand our adherence to rigorous standardsZscaler BlogGet the latest Zscaler blog updates in your inboxSubscribeSecurity ResearchLyceum .NET DNS BackdoorNIRAJ SHIVTARKAR, AVINASH KUMARJune 09, 2022 - 10 min read Security InsightsContentsArticleMore blogsCopy URLCopy URLActive since 2017, Lyceum group is a state-sponsored Iranian APT group that is known for targeting Middle Eastern organizations in the energy and telecommunication sectors and mostly relying on .NET based malwares. 
Zscaler ThreatLabz recently observed a new campaign where the Lyceum Group was utilizing a newly developed and customized .NET based malware targeting the Middle East by copying the underlying code from an open source tool.
 
Key Features of this attack:
 

The new malware is a .NET based DNS Backdoor which is a customized version of the open source tool “DIG.net”
The malware leverages a DNS attack technique called "DNS Hijacking" in which an attacker- controlled DNS server manipulates the response of DNS queries and resolve them as per their malicious requirements.
The malware employs the DNS protocol for command and control (C2) communication which increases stealth and keeps the malware communication probes under the radar to evade detection.
Comprises functionalities like Upload/Download Files and execution of system commands on the infected machine by abusing DNS records, including TXT records for incoming commands and A records for data exfiltration. 

 
Delivery mechanism
 
During this campaign, the macro-enabled Word document (File name: ir_drones.docm) shown below is downloaded from the domain “http[:]//news-spot.live” disguising itself as a news report related to military affairs in Iran. The text of the document is copied from the following original report here: https[:]//www[.]rferl[.]org/a/iran-drone-program-threats-interests/31660048.html
 

Fig 1. Attached Macro-enabled Word Document
 
Once the user enables the macro content, the following AutoOpen() function is executed which increases picture brightness using “PictureFormat.Brightness = 0.5” revealing content with the headline, “Iran Deploys Drones To Target Internal Threat, Protect External Interests.”
 
Fig 2. AutoOpen() function revealing content to lure the victims
 
The threat actor then leverages the AutoClose() function to drop the DNS backdoor onto the system. Upon closing the document the AutoClose() function is executed, reading a PE file from the text box present on the 7th page of the word document and parsing it further into the required format as shown below with the “MZ” header as the initial two bytes of the byte stream.
 

Fig 3. AutoClose() function reading the PE File
This PE file is then further written into the Startup folder in order to maintain persistence via the macro code as shown below in the screenshot. With this tactic, whenever the system is restarted, the DNS Backdoor is executed. 

Fig 4. DNS Backdoor dropped in the Startup folder

The dropped binary is a .NET based DNS Backdoor named “DnsSystem” which allows the threat actors to execute system commands remotely and upload/download data on the infected machine.
Below, we analyze the dropped .NET based DNS Backdoor and its inner workings.

 
Lyceum .NET DNS backdoor
The Lyceum Group has developed a .NET based DNS Backdoor which has been widely used in the wild in their recent campaigns. As discussed earlier, the backdoor was dropped in the Startup folder of the infected system from a Macro Enabled Word document.
md5: 8199f14502e80581000bd5b3bda250ee
Filename: DnsSystem.exe
 
Attack Chain Analysis
The .NET based DNS Backdoor is a customized version of the Open source tool DIG.net (DnsDig) found here: DNS.NET Resolver (C#) - CodeProject. DIG.net is an open source DNS Resolver which can be leveraged to perform DNS queries onto the DNS Server and then parse the response. The threat actors have customized and appended code that allows them to perform DNS queries for various records onto the custom DNS Server, parse the response of the query in order to execute system commands remotely, and upload/download files from the Command & Control server by leveraging the DNS protocol.
Initially the malware sets up an attacker controlled DNS server by acquiring the IP Address of the domain name “cyberclub[.]one” = 85[.]206[.]175[.]199 using Dns.GetHostAddresses() for the DIG Resolver function, which in turn triggers an DNS request to cyberclub[.]one for resolving the IP address. Now this IP is associated as the custom attacker controlled DNS Server for all the further DNS queries initiated by the malware. 
Fig 5. Initialize Attacker-Controlled DNS Server
 
Next, the Form Load function generates a unique BotID depending on the current Windows username. It converts the username into its MD5 equivalent using the CreateMD5() function, and parses the first 8 bytes of the MD5 as the BotID for the identification of the user and system infected by the malware.

Fig 6. Generation of BotID using the Windows username

Now, the backdoor needs to receive commands from the C2 server in order to perform tasks.  The backdoor sends across an initial DNS query to “trailers.apple.com” wherein the domain name “trailers.apple.com” is concatenated with the previously generated BotID before initiation of the DNS request. The DNS query is then sent to the DNS server in order to fetch the “TXT” records for the provided domain name by passing three arguments to the BeginDigIt() function: 

Name: Target Domain name - EF58DF5Ftrailers.apple.com 
qType: Records to be queried - TXT
qClass: Dns class value - IN (default)


Fig 7. Setup of DNS Query parameters before execution of BeginDigIt() Function
The BeginDigIt function then executes the main DNS resolver function “DigIt.” This sends across the DNS query in order to fetch the DNS record for the provided target domain name to the DNS server, and parses the response as seen in the code snippet below.

Fig 8. DNS Query DigIt Function 
 
Comparing the Digit Resolver Code DigIt() function strings with the Dig.Net tool output from the screenshot shown below provides us further assurance that the Dig.Net tool has been customized by the Lyceum Group to develop the following .Net based DNS backdoor.    .

Fig 9. Original Dig.net GUI Output 
The malware utilizes a DNS attack technique known as “DNS Hijacking” where in the DNS server is being controlled by the attackers which would allow them to manipulate the response to the DNS queries. Now let's analyze the DNS Hijacking routine below.
As discussed earlier, the backdoor performs initial DNS queries in order to fetch the TXT records for the domain EF58DF5trailers.apple.com. EF58DF5 is the BotID generated based on the Windows user to receive commands from the C2 server.
 
Fig 10. DNS query to attacker-controlled DNS server to fetch TXT records.
 
As can be seen in the above screenshot, a DNS query is performed to fetch the TXT records for the domain name: EF58DF5trailers.apple.com to the DNS Server: 85[.]206[.]175[.]199 which is the attacker-controlled DNS server previously initialized.
Here’s where the DNS hijacking happens: As the malware sends across a DNS query to fetch the TXT records to the attacker-controlled DNS server, the attacker controlled DNS server responds with an incorrect response consisting of the commands to be executed by the backdoor such as ipconfig,whoami,uploaddd etc as shown in the screenshot below.

Fig 11. Ipconfig command returned as the TXT record from the attacker controlled DNS server
 
Following is the DIG.Net DNS response received by the backdoor and then further parsed in order to execute commands on the infected machine.

Fig 12. DIG.net output received by the backdoor
The above screenshot consists of the DNS query performed to the attacker controlled DNS server along with the target domain name EF58DF5trailers.apple.com. The Answer section consists of the query response, which includes the target Domain name and the response to the TXT record with two values, “ipconfig” - command to be executed and “1291” - Communication ID
Next, the Dig.net response is parsed using multiple pattern regex code routines which parse out the TXT record values—the aforementioned command and communication ID—from the complete response received by the malware. 

Fig 13. Parsing of TXT Records

Next, depending on the command received in the TXT record from the C2 server, there are three functions which can be performed by the Lyceum backdoor:

Download Files - If the command received from the DNS query consists of a string: “downloaddd” it initiates the download routine and downloads the file from the URL using DownloadFileAsync(). The URL would be the first 11 bytes of the TXT record response value, and stores that downloaded file in the Downloads folder as shown below in the code snippet. This functionality can be leveraged to drop additional malware on the infected machine.


Fig 14. Backdoor Download Routine

Upload Files - If the command received from the DNS query consists of a string: “uploaddd”, it uploads the local file on the disk using UploadFileAsync() function to an External URL after parsing the TXT record response value into two variables: uriString (external URL) and filename (Local File). This functionality can be leveraged to exfiltrate data.


Fig 14.  Backdoor Upload Routine
 

Command Execution - If none of the above strings match the TXT record response then the response is passed on to the Command execution routine. There, the response to the txt record is executed as a command on the infected machine using “cmd.exe /c <txt_record_response_command>” and the command output is sent across to the C2 server in the form of DNS A Records.


Fig 15. Backdoor Command Execution Routine
 
In this case, the TXT record response we received for the DNS query performed against the attacker controlled DNS server is “ipconfig”. This response initiates the Command execution routine of the backdoor and thus the command “ipconfig” would be executed on the infected machine - cmd.exe /c ipconfig
Further, the command output is exfiltrated to the C2 server, encoded in Base64 and then concatenated with the Communication ID and the previously generated BotUID using “$” as the separator.
 

Fig 16. Command Output exfiltration Pattern setup 
        
  Data Exfil Pattern: [base64encoded_command_output]$[communication_id]$[Bot_ID]

Once the command output is encoded in the above mentioned pattern, the DNS backdoor then sends across the output to the C2 server via DNS query in the form of A records in multiple blocks of queries, where the A record values consists of the encoded command output. Once the command output is transmitted completely, an “Enddd” command is sent across in a Base64-encoded data exfil pattern to notify the end of the command output as shown below in the screenshot.

Fig 17. Exfiltration of Encoded Command Output via A records queries on the attacker controlled DNS server
 
Decoded A Records:

IPConfig Command Output - 
 
Encoded A record = ICAgSVB2NCBBZGRyZXNzLiAuIC4gLiAuIC4gLiAuIC4gLiAuIDogMTkyLjE2OC4.yLjEw$929$5686BB2F
Decoded A record =
IPv4 Address. . . . . . . . . . . : 192.168.2.10 $ ComID: 929 $ UID: 5686BB2F

End Command - 
Encoded A record = RW5kZGQ=$1291$$EF58DF5F 
Decoded A record = Enddd $ ComID: 1291 $ UID: EF58DF5F

Cloud Sandbox detection

Fig 18: The Zscaler Cloud Sandbox successfully detected the malware.
 
Conclusion
APT threat actors are continuously evolving their tactics and malware to successfully carry out attacks against their targets. Attackers continuously embrace new anti-analysis tricks to evade security solutions; re-packaging of malware makes static analysis even more challenging. The Zscaler ThreatLabz team will continue to monitor these attacks to help keep our customers safe.
 
MITRE ATT&CK mapping:
 
T1059Command and Scripting InterpreterT1055Process InjectionT1562Disable or Modify ToolsT1010Application Window DiscoveryT1018Remote System DiscoveryT1057Process DiscoveryT1518Security Software DiscoveryT1071Application Layer Protocol
 
IOC:
Docm Hash:
13814a190f61b36aff24d6aa1de56fe2
 
Exe Hash:
8199f14502e80581000bd5b3bda250ee
 
Domain and URL's:

cyberclub[.]one
hxxp://news-spot[.]live/Reports/1/?id=1111&pid=a52
hxxp://news-spot[.]live/Reports/1/?id=1111&pid=a28
hxxp://news-spot[.]live/Reports/1/?id=1111&pid=a40
hxxp://news-spot[.]live/Reports/1/45/DnsSystem[.]exe
 
About ThreatLabz
ThreatLabz is the security research arm of Zscaler. This world-class team is responsible for hunting new threats and ensuring that the thousands of organizations using the global Zscaler platform are always protected. In addition to malware research and behavioral analysis, team members are involved in the research and development of new prototype modules for advanced threat protection on the Zscaler platform, and regularly conduct internal security audits to ensure that Zscaler products and infrastructure meet security compliance standards. ThreatLabz regularly publishes in-depth analyses of new and emerging threats on its portal, research.zscaler.com.
Stay updated on ThreatLabz research by subscribing to our Trust Issues newsletter today.
 
 Thank you for readingWas this post useful?Yes, very!Not reallyExplore more Zscaler blogsAgniane Stealer: Dark Web’s Crypto ThreatRead postThe Impact of the SEC’s New Cybersecurity PoliciesRead postSecurity Advisory: Remote Code Execution Vulnerability (CVE-2023-3519)Read postThe TOITOIN Trojan: Analyzing a New Multi-Stage Attack Targeting LATAM RegionRead post01
                /
                02Go to next slideGo to previous slideGet the latest Zscaler blog updates in your inboxBy submitting the form, you are agreeing to our privacy policy. THE ZSCALER EXPERIENCELearn about:Your world, securedZero TrustSecure Access Service Edge (SASE)Security Service Edge (SSE)Zero Trust Network Access (ZTNA)Secure Web Gateway (SWG)Cloud Access Security Broker (CASB)Cloud Native Application Protection Platform (CNAPP)PRODUCTS & SOLUTIONSSecure Your UsersSecure Your WorkloadsSecure Your IoT and OTSecure Internet Access (ZIA)Data Protection (CASB/DLP)Digital Experience (ZDX)Posture ControlIndustry & Market SolutionsPartner IntegrationsZscaler Client ConnectorPLATFORMZero Trust Exchange PlatformSecure Digital TransformationNetwork TransformationApplication TransformationSecurity TransformationRESOURCESResource LibrarySecurity PreviewSecurity & Risk AssessmentThreatLabz Analytics & InsightsUpcoming EventsBlogZscaler AcademyCXO RevolutionariesZpediaRansomware Protection ROI CalculatorPOPULAR LINKSPricing & PlansAbout ZscalerLeadership TeamCareer OpportunitiesFind or Become a PartnerCustomer Success CenterInvestor RelationsPress CenterNews & AnnouncementsESGComplianceContact ZscalerHomeEnglishFrançaisDeutschItaliano日本Castellano - MexicoCastellano - EspañaPortugues - BrasilZscaler is universally recognized as the leader in zero trust. Leveraging the largest security cloud on the planet, Zscaler anticipates, secures, and simplifies the experience of doing business for the world's most established companies. EnglishFrançaisDeutschItaliano日本Castellano - MexicoCastellano - EspañaPortugues - BrasilVisit us on FacebookLinkedinFollow us on TwitterSubscribe our Youtube ChannelSitemapPrivacyLegalSecurity© 2024 Zscaler, Inc. All rights reserved. Zscaler™ and other trademarks listed at zscaler.com/legal/trademarks are either (i) registered trademarks or service marks or (ii) trademarks or service marks of Zscaler, Inc. in the United States and/or other countries. Any other trademarks are the properties of their respective owners.


