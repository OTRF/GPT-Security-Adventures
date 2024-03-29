# Reference for threat actor for "DarkHotel"

**Title**: New DarkHotel APT attack chain identified | Zscaler

**Source**: https://www.zscaler.com/blogs/security-research/new-darkhotel-apt-attack-chain-identified

## Content
New DarkHotel APT attack chain identified | ZscalerThis site uses JavaScript to provide a number of functions, to use this site please enable JavaScript in your browser.Concerned about VPN vulnerabilities? Learn how you can benefit from our VPN migration offer including 60 days free service.Talk to an expertCloseOpenSearchCXO REvolutionariesCareersPartnersSupportShowContact UsOptionsGet in touch1-408-533-0288Chat with usShowSign InOptionsZscaler Cloud Portal | AdminZscaler Cloud Portal One | AdminZscaler Cloud Portal Two | AdminZscaler Cloud Portal Three | AdminZscaler Cloud Portal Beta | Adminadmin.zscloud.netZscaler Private Access Sign-InHomeThe Zscaler ExperienceProducts & SolutionsPlatformResourcesCompanyRequest a demoopen searchopen navigationThe Zscaler ExperienceZscaler: A Leader in the 2023 Gartner® Magic Quadrant™ for Security Service Edge (SSE)Get the full reportYour world, securedExperience the transformative power of zero trust.The Zscaler DifferenceThe Zscaler DifferenceExperience the World’s Largest Security CloudCustomer Success StoriesAnalyst RecognitionMachine Learning and AI at ZscalerReduce Your Carbon FootprintZero Trust FundamentalsZero Trust FundamentalsWhat Is Zero Trust?What Is Security Service Edge (SSE)?What Is Secure Access Service Edge (SASE)?What Is Zero Trust Network Access (ZTNA)?What Is Secure Web Gateway (SWG)?What Is Cloud Access Security Broker (CASB)?What Is Cloud Native Application Protection Platform (CNAPP)?Zero Trust ResourcesProducts & SolutionsSecure Your UsersProvide users with seamless, secure, reliable access to applications and data.Secure Your WorkloadsBuild and run secure cloud apps, enable zero trust cloud connectivity, and protect workloads from data center to cloud.Secure Your IoT and OTProvide zero trust connectivity for IoT and OT devices and secure remote access to OT systems.ProductsProductsTransform your organization with 100% cloud native servicesSecure Internet Access (ZIA)Secure Private Access (ZPA)Digital Experience (ZDX)Data Protection (CASB/DLP)Posture ControlSolution AreasSolution AreasPropel your business with zero trust solutions that secure and connect your resourcesCyberthreat ProtectionData ProtectionZero Trust NetworkingBusiness AnalyticsVPN AlternativeZero Trust SASEAccelerate M&A IntegrationOptimize Digital ExperiencesZero Trust SD-WANZero Trust Cloud ConnectivityZero Trust for IoT/OTFind a Product or SolutionPartner IntegrationsIndustry and Market SolutionsPlatformZero Trust Exchange PlatformLearn how Zscaler delivers zero trust with a cloud native platform that is the world’s largest security cloudZero Trust Exchange PlatformTitle LinkTransform with Zero Trust ArchitectureTransform with Zero Trust ArchitecturePropel your transformation journeySecure Digital TransformationNetwork TransformationApplication TransformationSecurity TransformationSecure Your Business GoalsSecure Your Business GoalsAchieve your business and IT initiativesEnsure Secure Business ContinuityAccelerate M&A and DivestituresRecession-Proof Your EnterpriseSecure Your Hybrid WorkforceDownload Zscaler Client ConnectorResourcesLearn, connect, and get support.Explore tools and resources to accelerate your transformation and secure your worldLearn, connect, and get support.Title LinkAmplifying the voices of real-world digital and zero trust pioneersVisit nowResource CenterResource CenterStay up to date on best practicesResource LibraryBlogCustomer Success StoriesWebinarsZpediaEvents & TrainingsEvents & TrainingsFind programs, certifications, and eventsUpcoming EventsZenith LiveZscaler AcademyInteractive Zscaler Whiteboard WorkshopSecurity Research & ServicesSecurity Research & ServicesGet research and insights at your fingertipsThreatLabz AnalyticsToolsToolsTools designed for youSecurity PreviewSecurity and Risk AssessmentSecurity Advisory UpdatesDisclose a VulnerabilityExecutive Insights AppRansomware Protection ROI CalculatorCommunity & SupportCommunity & SupportConnect and find supportCustomer Success CenterZenith CommunityCXO REvolutionariesZscaler Help PortalExplore the latest Zscaler InnovationsIndustry & Market SolutionsIndustry & Market SolutionsSee solutions for your industry and countryPublic SectorHealthcareFinancial ServicesEducationSee allResource CenterResource CenterStay up to date on best practicesResource LibraryBlogCustomer Success StoriesWebinarsZpediaEvents & TrainingsEvents & TrainingsFind programs, certifications, and eventsUpcoming EventsZenith LiveZscaler AcademyInteractive Zscaler Whiteboard WorkshopSecurity Research & ServicesSecurity Research & ServicesGet research and insights at your fingertipsThreatLabz AnalyticsToolsToolsTools designed for youSecurity PreviewSecurity and Risk AssessmentSecurity Advisory UpdatesDisclose a VulnerabilityExecutive Insights AppRansomware Protection ROI CalculatorCommunity & SupportCommunity & SupportConnect and find supportCustomer Success CenterZenith CommunityCXO REvolutionariesZscaler Help PortalExplore the latest Zscaler InnovationsIndustry & Market SolutionsIndustry & Market SolutionsSee solutions for your industry and countryPublic SectorHealthcareFinancial ServicesEducationSee allCompanyAbout ZscalerDiscover how it began and where it’s goingPartnersMeet our partners and explore system integrators and technology alliancesNews & AnnouncementsStay up to date with the latest newsLeadership TeamMeet our management teamPartner IntegrationsExplore best-in-class partner integrations to help you accelerate digital transformationInvestor RelationsSee news, stock information, and quarterly reportsEnvironmental, Social & GovernanceLearn about our ESG approachCareersJoin our missionPress CenterFind everything you need to cover ZscalerComplianceUnderstand our adherence to rigorous standardsZenith VenturesUnderstand our adherence to rigorous standardsZscaler BlogGet the latest Zscaler blog updates in your inboxSubscribeSecurity ResearchNew DarkHotel APT attack chain identifiedSAHIL ANTIL, SUDEEP SINGHDecember 16, 2021 - 8 min read Security InsightsContentsArticleMore blogsCopy URLCopy URLSummary
In November 2021, ThreatLabz identified a previously undocumented variant of an attack chain used by the South Korea-based Dark Hotel APT group. We also discovered new activity on the command-and-control (C2) infrastructure previously associated with this APT group. The new activity on their infrastructure aligns with the type of targets chosen by this threat actor in the past.
In this blog, we describe our new findings in detail, including technical analysis of the attack chain and its components as well as the C2 infrastructure analysis.

Threat attribution
DarkHotel is an advanced persistent threat (APT) group based out of South Korea that has been active since at least 2007. They are known to target senior business executives by uploading malicious code to their computers through infiltrated hotel WiFi networks, as well as through spear-phishing and P2P attacks.
We attribute this attack chain to the Dark Hotel APT group with a high level of confidence due to the below reasons:
1. The multi-layer malicious document which drops a scriptlet post-exploitation.
2. Filename of the dropped file system artifacts such as the scriptlet file - googleofficechk.sct
3. The command-and-control (C2) commands are the same as earlier payloads used by Dark Hotel.
4. Timestamps of the dropped payloads are around the same timeframe when previously documented Dark Hotel APT activity was observed.

Attack flow
Figure 1 below illustrates the full attack chain.

Figure 1: Attack chain
 
Technical analysis
For the purpose of technical analysis we will consider the document with MD5 hash: 89ec1f32e1bbf794c41fa5f5bc6869c0
[+] Stage 1: Malicious document
The first stage of this attack is a multi-layered malicious document which defines an AltChunk element to load an embedded DOCX file. The embedded DOCX file defines another AltChunk element which loads an embedded malicious RTF file. Figure 2 below shows one of the defined AltChunk elements and its corresponding relationship.

Figure 2: AltChunk element and its corresponding relationship
The malicious RTF file contains three OLE objects as shown in Figure 3

Figure 3: OLE objects present inside malicious RTF
When the RTF file is loaded, the three OLE objects are dropped in the %temp% directory with the names “p”, “b” and “googleofficechk.sct”. Out of these three dropped files, the scriptlet file (googleofficechk.sct) is executed which is described in detail in the next section.
[+] Stage-2: Scriptlet file
Similar to what has been described previously by Antiy Labs, the first operation performed by the scriptlet file is to send a Base64 encoded list of running processes to the configured C2 server. It sends a POST request to the URL “http://signing-config[.]com/cta/key.php” with DATA “L=G641giQQOWUiXE&q={Base64 encoded list of running processes}”
The subsequent operations performed by this scriptlet file differ from what has been observed in past attacks.
The scriptlet file in our case performs the following operations:
1. Checks if the directory “%LOCALAPPDATA%\PeerDistRepub\” exists else creates it.
2. Checks for the presence of file “%LOCALAPPDATA%\PeerDistRepub\msrvcd32.exe”. If the file exists, then it doesn't perform further operations.
Note: This file check is likely performed to detect if the machine is already infected, which also indicates that the threat actor used multiple variations while performing the attack.
 
3. Releases the IP addresses bound to all DHCP-enabled network adapters
4. Copies the executable from “%temp%\p” to “%LOCALAPPDATA%\PeerDistRepub\qq3104.exe”
5. Copies the executable from “%temp%\b” to “%LOCALAPPDATA%\PeerDistRepub\qq2688.exe”
6. Creates a ZoneIdentifier ADS (Alternate Data Stream) corresponding to the files copied above with the following content:
ZoneTransfer
ZoneId=1
Note: The ZoneID=1 is written to create the false evidence that the file was downloaded from the Intranet
7. Execute the binary “qq3104.exe” whose functionality is described in detail in the next section
8. Renew the IPv4 address for the network adapters
Figure 4 below shows the relevant scriptlet code

Figure 4: Scriptlet code
[+] Stage-3: Dropped binaries
# qq3104.exe
As mentioned in the previous section, the binary qq3104.exe gets executed as part of the operations performed by the scriptlet file. This binary mainly performs three operations:
1. Spoofs the process related information in the PEB structure to pretend as explorer.exe

Figure 5: Code snippet responsible for PEB modification
2. Perform UAC bypass using elevation moniker against the vulnerable COM interfaces {3E5FC7F9-9A51-4367-9063-A120244FBEC7} and {D2E7041B-2927-42fb-8E9F-7CE93B6DC937}

3. Execute the binary qq2688.exe
# qq2688.exe
This binary on execution checks if there is any running process with the name “360Tray.exe” or “QQPCTray.exe” and does some firewall checks. These process names correspond to security software popularly used in China.
The main operation performed by the binary is to register a Windows service which also serves as a persistence mechanism. 
To register the Windows service, the binary creates the registry key “HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\services\\X” and populates the service related registry values. Along with the service related registry values, two additional registry values are defined with the name “s” and “x” under the same registry key. 
Based on the service registry values, it is an auto start service which executes VBScript code using mshta.exe.

Figure 6: Code snippet responsible for registering the Windows service
The VBScript code in turn executes an encoded PowerShell command which is shown in Figure 8 below

Figure 7: Decoded PowerShell command executed by VBScript code
[+] Stage-4: PowerShell scripts
The PowerShell command which is executed as part of the service execution reads, decodes and executes the data stored under registry value “HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\services\\X\\s”.
The decoded data is a PowerShell script which executes another PowerShell command. The command is shown in Figure 9 below.

Figure 8: Decoded PowerShell command executed by PowerShell script
Similar to the first PowerShell command it also reads, decodes and executes the data stored under registry value “HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\services\\X\\x”.
The decoded data is an obfuscated PowerShell script which embeds an encoded .NET dll. The .NET dll is loaded and executed in-memory from within the PowerShell script.
[+] Stage-5: .NET dll
The .NET dll on analysis turns out to be the same downloader which is described in Antiy blog. The only changes are in the configured C2 servers and the parameters which are used as part of network requests.
Information about the C2 servers is provided in Indicators of compromise section while the format for network requests is described below:
Request format for data exfiltration:
{C2 server URL}?im={MAC address}&mk=u&ltc={victim information}
                OR
{C2 server URL}?xt={MAC address}&mk=u&ltc={victim information}
Request format for payload download:
{C2 server URL}?im={MAC address}&mk=d
            OR
{C2 server URL}?xt={MAC address}&mk=d

[+] C2 infrastructure analysis
We analyzed the C2 infrastructure related to the IP address of the server hosting the domain - signing-config[.]com. This domain was configured in the stage-2 scriptlet file and used to exfiltrate system information to the C2 server.
IP address = 23.111.184[.]119
Leveraging passive DNS data, we identified several domains hosted on the server with the above IP address and noticed a pattern in the domain names. A lot of domains were created to spoof the names of organizations in China related to the government, education, and political think tanks.
Below are a few examples summarized in a table:
 
Domain nameTarget spoofedwww.onlinesurvey.register.moe.edu.cn[.]serviceneteasse.comMinistry of Education, Chinawww.preview.maiil.caict.ac.cn.coremailxt[.]serviceneteasse.comPolitical think tanks of Chinawww.prevwdoc.mofcom.gov.cn.loginwebbauthh[.]serviceneteasse.comBeihang University in Chinawww.compliance.maill.buaa.edu.cn.coremailxt[.]serviceneteasse.comMinistry of commerce, Chinawww.compliance.maill.hit.edu.cn[.]coremailxt.serviceneteasse.comHarbin Institute of Technologysecureattch.nudt.edu.cn[.]coremailxt.serviceneteasse.comNational University of Defence and Technology

In addition to this, we also identified several newly registered domains on this server which are used to spoof cryptocurrency projects popularly used in China such as the Deeper network.
The domain, deepersbot[.]network was registered by the threat actor to spoof the legitimate domain, deeper[.]network.

Figure 9: Phishing website
The fake domain asks the users to validate their wallet on the main page and presents them an option to choose from a wide variety of popularly used crypto currency wallets.

Figure 10: Wallet options provided on the phishing website
Once the user chooses the wallet type, they will be redirected to a page which prompts them to share their private key.

Figure 11: Page asking for user Private key information
It uses one of the following 3 ways:
Phrase: A 12 or 24 word recovery phrase which can be used to restore the private key and steal the funds.
JSON file: a password-protected JSON file which stores the encrypted private key
Private key: The private key itself
The table below summarizes the list of domains registered which use social engineering to steal the private keys of crypto currency wallets of the users:
 
Date registeredDomain name13th Nov 2021dappconnectmainbott[.]org13th Nov 2021deepersbot[.]network5th Nov 2021www.walletauthenticatorbot[.]net2nd Nov 2021dapp-connect[.]org

Zscaler Cloud Sandbox report

Figure 12: Zscaler Cloud Sandbox detection

Indicators of compromise
[+] Hashes
 
MD5Description89ec1f32e1bbf794c41fa5f5bc6869c0Document

[+] C2 Domains
signing-config[.]com
svcstat[.]com
relay-server[.]com
[+] C2 URLs
 
ComponentURLScriptlet filehttp://signing-config[.]com/cta/key.php.NET backdoor
http://svcstat[.]com/policy/v2.php?im=
			http://relay-server[.]com/mint/mvv.php?xt=


[+] Files system artifacts
# Dropped binaries
%LOCALAPPDATA%\PeerDistRepub\qq3104.exe
%LOCALAPPDATA%\PeerDistRepub\qq2688.exe
%TEMP%\p
%TEMP%\b
# Scriptlet file
%TEMP%\googleofficechk.sct
[+] Registry artifacts
Registry Key: HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\services\\X
Registry Values: 
HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\services\\X\\s
HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\services\\X\\x
 Thank you for readingWas this post useful?Yes, very!Not reallyExplore more Zscaler blogsAgniane Stealer: Dark Web’s Crypto ThreatRead postThe Impact of the SEC’s New Cybersecurity PoliciesRead postSecurity Advisory: Remote Code Execution Vulnerability (CVE-2023-3519)Read postThe TOITOIN Trojan: Analyzing a New Multi-Stage Attack Targeting LATAM RegionRead post01
                /
                02Go to next slideGo to previous slideGet the latest Zscaler blog updates in your inboxBy submitting the form, you are agreeing to our privacy policy. THE ZSCALER EXPERIENCELearn about:Your world, securedZero TrustSecure Access Service Edge (SASE)Security Service Edge (SSE)Zero Trust Network Access (ZTNA)Secure Web Gateway (SWG)Cloud Access Security Broker (CASB)Cloud Native Application Protection Platform (CNAPP)PRODUCTS & SOLUTIONSSecure Your UsersSecure Your WorkloadsSecure Your IoT and OTSecure Internet Access (ZIA)Data Protection (CASB/DLP)Digital Experience (ZDX)Posture ControlIndustry & Market SolutionsPartner IntegrationsZscaler Client ConnectorPLATFORMZero Trust Exchange PlatformSecure Digital TransformationNetwork TransformationApplication TransformationSecurity TransformationRESOURCESResource LibrarySecurity PreviewSecurity & Risk AssessmentThreatLabz Analytics & InsightsUpcoming EventsBlogZscaler AcademyCXO RevolutionariesZpediaRansomware Protection ROI CalculatorPOPULAR LINKSPricing & PlansAbout ZscalerLeadership TeamCareer OpportunitiesFind or Become a PartnerCustomer Success CenterInvestor RelationsPress CenterNews & AnnouncementsESGComplianceContact ZscalerHomeEnglishFrançaisDeutschItaliano日本Castellano - MexicoCastellano - EspañaPortugues - BrasilZscaler is universally recognized as the leader in zero trust. Leveraging the largest security cloud on the planet, Zscaler anticipates, secures, and simplifies the experience of doing business for the world's most established companies. EnglishFrançaisDeutschItaliano日本Castellano - MexicoCastellano - EspañaPortugues - BrasilVisit us on FacebookLinkedinFollow us on TwitterSubscribe our Youtube ChannelSitemapPrivacyLegalSecurity© 2024 Zscaler, Inc. All rights reserved. Zscaler™ and other trademarks listed at zscaler.com/legal/trademarks are either (i) registered trademarks or service marks or (ii) trademarks or service marks of Zscaler, Inc. in the United States and/or other countries. Any other trademarks are the properties of their respective owners.


