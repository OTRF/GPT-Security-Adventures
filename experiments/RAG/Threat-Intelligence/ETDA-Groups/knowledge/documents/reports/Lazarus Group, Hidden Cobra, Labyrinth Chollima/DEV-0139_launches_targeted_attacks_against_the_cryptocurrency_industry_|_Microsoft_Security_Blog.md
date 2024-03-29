# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: DEV-0139 launches targeted attacks against the cryptocurrency industry | Microsoft Security Blog

**Source**: https://www.microsoft.com/en-us/security/blog/2022/12/06/dev-0139-launches-targeted-attacks-against-the-cryptocurrency-industry/

## Content


























DEV-0139 launches targeted attacks against the cryptocurrency industry | Microsoft Security Blog





























































 

 



















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



													Attacker techniques, tools, and infrastructure												




									18 min read								

DEV-0139 launches targeted attacks against the cryptocurrency industry




											By										
Microsoft Threat Intelligence












					December 6, 2022				




 





 





 







											Attacker techniques, tools, and infrastructure										



											Threat actors										



											Cryptocurrency mining										



											MITRE ATT&CK										



											Sleet										






April 2023 update – Microsoft Threat Intelligence has shifted to a new threat actor naming taxonomy aligned around the theme of weather. DEV-0139 is now tracked as Citrine Sleet.
To learn about how the new taxonomy represents the origin, unique traits, and impact of threat actors, and to get a complete mapping of threat actor names, read this blog: Microsoft shifts to a new threat actor naming taxonomy.

Over the past several years, the cryptocurrency market has considerably expanded, gaining the interest of investors and threat actors. Cryptocurrency itself has been used by cybercriminals for their operations, notably for ransom payment in ransomware attacks, but we have also observed threat actors directly targeting organizations within the cryptocurrency industry for financial gain. Attacks targeting this market have taken many forms, including fraud, vulnerability exploitation, fake applications, and usage of info stealers, as attackers attempt to get their hands on cryptocurrency funds.
We are also seeing more complex attacks wherein the threat actor shows great knowledge and preparation, taking steps to gain their target’s trust before deploying payloads. For example, Microsoft recently investigated an attack where the threat actor, tracked as DEV-0139, took advantage of Telegram chat groups to target cryptocurrency investment companies. DEV-0139 joined Telegram groups used to facilitate communication between VIP clients and cryptocurrency exchange platforms and identified their target from among the members. The threat actor posed as representatives of another cryptocurrency investment company, and in October 2022 invited the target to a different chat group and pretended to ask for feedback on the fee structure used by cryptocurrency exchange platforms. The threat actor had a broader knowledge of this specific part of the industry, indicating that they were well prepared and aware of the current challenge the targeted companies may have.
After gaining the target’s trust, DEV-0139 then sent a weaponized Excel file with the name OKX Binance & Huobi VIP fee comparision.xls which contained several tables about fee structures among cryptocurrency exchange companies. The data in the document was likely accurate to increase their credibility. This weaponized Excel file initiates the following series of activities:

A malicious macro in the weaponized Excel file abuses UserForm of VBA to obfuscate the code and retrieve some data.
The malicious macro drops another Excel sheet embedded in the form and executes it in invisible mode. The said Excel sheet is encoded in base64, and dropped into C:\ProgramData\Microsoft Media\ with the name VSDB688.tmp
The file VSDB688.tmp downloads a PNG file containing three executables: a legitimate Windows file named logagent.exe, a malicious version of the DLL wsock32.dll, and an XOR encoded backdoor.
The file logagent.exe is used to sideload the malicious wsock32.dll, which acts as a DLL proxy to the legitimate wsock32.dll. The malicious DLL file is used to load and decrypt the XOR encoded backdoor that lets the threat actor remotely access the infected system.

Figure 1. Overview of the attack
Further investigation through our telemetry led to the discovery of another file that uses the same DLL proxying technique. But instead of a malicious Excel file, it is delivered in an MSI package for a CryptoDashboardV2 application, dated June 2022. This may suggest other related campaigns are also run by the same threat actor, using the same techniques.
In this blog post, we will present the details uncovered from our investigation of the attack against a cryptocurrency investment company, as well as analysis of related files, to help similar organizations understand this kind of threat, and prepare for possible attacks. Researchers at Volexity recently published their findings on this attack as well. 
As with any observed nation state actor activity, Microsoft directly notifies customers that have been targeted or compromised, providing them with the information they need to secure their accounts. Microsoft uses DEV-#### designations as a temporary name given to an unknown, emerging, or a developing cluster of threat activity, allowing Microsoft Threat Intelligence Center (MSTIC) to track it as a unique set of information until we reach a high confidence about the origin or identity of the actor behind the activity. Once it meets the criteria, a DEV is converted to a named actor.
Initial compromise
To identify the targets, the threat actor sought out members of cryptocurrency investment groups on Telegram. In the specific attack, DEV-0139 got in touch with their target on October 19, 2022 by creating a secondary Telegram group with the name <NameOfTheTargetedCompany> <> OKX Fee Adjustment and inviting three employees. The threat actor created fake profiles using details from employees of the company OKX. The screenshot below shows the real accounts and the malicious ones for two of the users present in the group.
Figure 2. Legitimate profiles of cryptocurrency exchange employees (left) and fake profiles created by the threat actor (right)
It’s worth noting that the threat actor appears to have a broad knowledge of the cryptocurrency industry and the challenges the targeted company may face. The threat actor asked questions about fee structures, which are the fees used by crypto exchange platforms for trading. The fees are a big challenge for investment funds as they represent a cost and must be optimized to minimize impact on margin and profits. Like many other companies in this industry, the largest costs come from fees charged by exchanges. This is a very specific topic that demonstrates how the threat actor was advanced and well prepared before contacting their target.
After gaining the trust of the target, the threat actor sent a weaponized Excel document to the target containing further details on the fees to appear legitimate. The threat actor used the fee structure discussion as an opportunity to ask the target to open the weaponized Excel file and fill in their information.
Weaponized Excel file analysis
The weaponized Excel file, which has the file name OKX Binance & Huobi VIP fee comparision.xls (Sha256: abca3253c003af67113f83df2242a7078d5224870b619489015e4fde060acad0), is well crafted and contains legitimate information about the current fees used by some crypto exchanges. The metadata extracted showed that the file was created by the user Wolf:

File nameOKX Binance & Huobi VIP fee comparision.xlsCompObjUserTypeLen31CompObjUserTypeMicrosoft Excel 2003 WorksheetModifyDate2022:10:14 02:34:33TitleOfPartsComparison_Oct 2022SharedDocNoAuthorWolfCodePageWindows Latin 1 (Western European)AppVersion16LinksUpToDateNoScaleCropNoLastModifiedByWolfHeadingPairsWorksheets, 1FileTypeXLSFileTypeExtensionxlsHyperlinksChangedNoSecurityNoneCreateDate2022:10:14 02:34:31SoftwareMicrosoft ExcelMIMETypeapplication/vnd.ms-excel
Figure 3. The information in the malicious Excel file
The macro is obfuscated and abuses UserForm (a feature used to create windows) to store data and variables. In this case, the name of the UserForm is IFUZYDTTOP, and the macro retrieves the information with the following code IFUZYDTTOP.MgQnQVGb.Caption where MgQnQVGb is the name of the label in the UserForm and .caption allows to retrieve the information stored into the UserForm.
The table below shows the data retrieved from the UserForm:
Obfuscated dataOriginal dataIFUZYDTTOP.nPuyGkKr.Caption & IFUZYDTTOP.jpqKCxUd.CaptionMSXML2.DOMDocumentIFUZYDTTOP.QevjtDZF.Captionb64IFUZYDTTOP.MgQnQVGb.Captionbin.base64IFUZYDTTOP.iuiITrLG.CaptionBase64 encoded Second WorksheetIFUZYDTTOP.hMcZvwhq.CaptionC:\ProgramData\Microsoft MediaIFUZYDTTOP.DDFyQLPa.Caption\VSDB688.tmpIFUZYDTTOP.PwXgwErw.Caption & IFUZYDTTOP.ePGMifdW.CaptionExcel.Application
The macro retrieves some parameters from the UserForm as well as another XLS file stored in base64. The XLS file is dropped into the directory C:\ProgramData\Microsoft Media as VSDB688.tmp and runs in invisible mode.
Figure 4. The deobfuscated code to load the extracted worksheet in invisible mode.
Additionally, the main sheet in the Excel file is protected with the password dragon to encourage the target to enable the macros. The sheet is then unprotected after installing and running the other Excel file stored in Base64. This is likely used to trick the user to enable macros and not raise suspicion.
Extracted worksheet
The second Excel file, VSDB688.tmp (Sha256: a2d3c41e6812044573a939a51a22d659ec32aea00c26c1a2fdf7466f5c7e1ee9), is used to retrieve a PNG file that is parsed later by the macro to extract two executable files and the encrypted backdoor. Below is the metadata for the second worksheet:
File NameVSDB688.tmpCompObjUserTypeMicrosoft Excel 2003 WorksheetModifyDate2022:08:29 08:07:24TitleOfPartsSheet1SharedDocNoCodePageWindows Latin 1 (Western European)AppVersion16LinksUpToDateNoScaleCropNoCompObjUserTypeLen31HeadingPairsWorksheets, 1FileTypeXLSFileTypeExtensionxlsHyperlinksChangedNoSecurityNoneCreateDate2006:09:16 00:00:00SoftwareMicrosoft ExcelMIMETypeapplication/vnd.ms-excel
Figure 5. The second file is completely empty but contains the same UserForm abuse technique as the first stage.
The table below shows the deobfuscated data retrieved from the UserForm:
Obfuscated dataOriginal dataGGPJPPVOJB.GbEtQGZe.Caption & GGPJPPVOJB.ECufizoN.CaptionMSXML2.DOMDocumentGGPJPPVOJB.BkxQNjsP.Captionb64GGPJPPVOJB.slgGbwvS.Captionbin.base64GGPJPPVOJB.kiTajKHg.CaptionC:\ProgramData\SoftwareCache\GGPJPPVOJB.fXSPzIWf.Captionlogagent.exeGGPJPPVOJB.JzrHMGPQ.Captionwsock32.dllGGPJPPVOJB.pKLagNSW.Caption56762eb9-411c-4842-9530-9922c46ba2daGGPJPPVOJB.grzjNBbk.Caption/shadowGGPJPPVOJB.aJmXcCtW.Caption & GGPJPPVOJB.zpxMSdzi.CaptionMSXML2.ServerXMLHTTP.6.0GGPJPPVOJB.rDHwJTxL.CaptionGet
The macro retrieves some parameters from the UserForm then downloads a PNG file from hxxps://od.lk/d/d021d412be456a6f78a0052a1f0e3557dcfa14bf25f9d0f1d0d2d7dcdac86c73/Background.png. The file was no longer available at the time of analysis, indicating that the threat actor likely deployed it only for this specific attack.
Figure 6. Deobfuscated code that shows the download of the file Background.png
The PNG is then split into three parts and written in three different files: the legitimate file logagent.exe, a malicious version of wsock32.dll, and the XOR encrypted backdoor with the GUID (56762eb9-411c-4842-9530-9922c46ba2da). The three files are used to load the main payload to the target system.
Figure 7. The three files are written into C:\\ProgramData\SoftwareCache\ and run using the CreateProcess API
Loader analysis
Two of the three files extracted from the PNG file, logagent.exe and wsock32.dll, are used to load the XOR encrypted backdoor. The following sections present our in-depth analysis of both files.
Logagent.exe
Logagent.exe (Hash: 8400f2674892cdfff27b0dfe98a2a77673ce5e76b06438ac6110f0d768459942) is a legitimate system application used to log errors from Windows Media Player and send the information for troubleshooting.
The file contains the following metadata, but it is not signed:
Description ValuelanguageEnglish-UScode-pageUnicode UTF-16 little endianCompanyNameMicrosoft CorporationFileDescriptionWindows Media Player LogagentFileVersion12.0.19041.746InternalNamelogagent.exeLegalCopyright© Microsoft Corporation. All rights reserved.OriginalFilenamelogagent.exeProductNameMicrosoft® Windows® Operating SystemProductVersion12.0.19041.746
The logagent.exe imports function from the wsock32.dll which is abused by the threat actor to load malicious code into the targeted system. To trigger and run the malicious wsock32.dll, logagent.exe is run with the following arguments previously retrieved by the macro: 56762eb9-411c-4842-9530-9922c46ba2da /shadow. Both arguments are then retrieved by wsock32.dll. The GUID 56762eb9-411c-4842-9530-9922c46ba2da is the filename for the malicious wsock32.dll to load and /shadow is used as an XOR key to decrypt it. Both parameters are needed for the malware to function, potentially hindering isolated analysis.
Figure 8. Command line execution from the running process logagent.exe
Wsock32.dll
The legitimate wsock32.dll is the Windows Socket API used by applications to handle network connections. In this attack, the threat actor used a malicious version of wsock32.dll to evade detection. The malicious wsock32.dll is loaded by logagent.exe through DLL side-loading and uses DLL proxying to call the legitimate functions from the real wsock32.dll and avoid detection. DLL proxying is a hijacking technique where a malicious DLL sits in between the application calling the exported function and a legitimate DLL that implements that exported function. In this attack, the malicious wsock32.dll acts as a proxy between logagent.exe and the legitimate wsock32.dll.
It is possible to notice that the DLL is forwarding the call to the legitimate functions by looking at the import address table:
Figure 9. Import Address Table from wsock32.dll
Figure 10. Retrieving data with PeStudio revealed the original file name for the malicious wsock32.dll.
When the malicious wsock32.dll is loaded, it first retrieves the command line, and checks if the file with the GUID as a filename is present in the same directory using the CreateFile API to retrieve a file handle.
Figure 11. Verification of the presence of the file 56762eb9-411c-4842-9530-9922c46ba2da for decryption
The malicious wsock32.dll loads and decodes the final implant into the memory with the GUID name which is used to remote access the infected machine.
SHA2562e8d2525a523b0a47a22a1e9cc9219d6526840d8b819d40d24046b17db8ea3fbImphash52ff8adb6e941e2ce41fd038063c5e0eRich PE Hashff102ff1ac1c891d1f5be7294035d19eFiletypePE32+ DLLCompile Timestamp2022-08-29 06:33:10 UTC
Once the file is loaded into the memory, it gives remote access to the threat actor. At the time of the analysis, we could not retrieve the final payload. However, we identified another variant of this attack and retrieved the payload, which is discussed in the next section. Identified implants were connecting back to the same command-and-control (C2) server.
Related attack
We identified another file using a similar mechanism as logagent.exe and delivering the same payload. The loader is packaged as an MSI package and as posed an application called CryptoDashboardV2 (Hash: e5980e18319027f0c28cd2f581e75e755a0dace72f10748852ba5f63a0c99487). After installing the MSI, it uses a legitimate application called tplink.exe to sideload the malicious DLL called DUser.dll and uses  DLL proxying as well.
creation datetime11/12/2009 11:47author168 TradingtitleInstallation Databasepage count200word count2keywordsInstaller, MSI, Databaselast saved11/12/2009 11:47revision number{30CD8B94-5D3C-4B55-A5A3-3FC9C7CCE6D5}last printed11/12/2009 11:47application nameAdvanced Installer 14.5.2 build 83143subjectCryptoDashboardV2templatex64;1033code pageLatin IcommentsThis installer database contains the logic and data required to install CryptoDashboardV2.
Figure 12. Installation details of the MSI file
Once the package is installed, it runs and side-loads the DLL using the following command: C:\Users\user\AppData\Roaming\Dashboard_v2\TPLink.exe” 27E57D84-4310-4825-AB22-743C78B8F3AA /sven, where it noticeably uses a different GUID.
Further analysis of the malicious DUser.dll showed that its original name is also HijackingLib.dll, same as the malicious wsock32.dll. This could indicate the usage of the same tool to create these malicious DLL proxies. Below are the file details of DUser.dll:
SHA25690b0a4c9fe8fd0084a5d50ed781c7c8908f6ade44e5654acffea922e281c6b33Imphash52ff8adb6e941e2ce41fd038063c5e0eRich PE Hashff102ff1ac1c891d1f5be7294035d19eFiletypeWin32 DLLCompile Timestamp2022-06-20 07:47:07 UTC
Once the DLL is running, it loads and decodes the implant in the memory and starts beaconing the same domain. In that case, the implant is using the GUID name 27E57D84-4310-4825-AB22-743C78B8F3AA and the XOR key /sven.
Implant analysis
The payload decoded in the memory by the malicious DLL is an implant used by the threat actor to remotely access the compromised machine. We were able to get the one from the second variant we uncovered. Below are the details of the payload:
SHA256ea31e626368b923419e8966747ca33473e583376095c48e815916ff90382dda5Imphash96321fa09a450119a8f0418ec86c3e08Rich PE Hash8c4fb0cb671dbf8d859b875244c4730cFiletypeWin32 DLLCompile Timestamp2022-06-20 00:51:33 UTC
First, the sample retrieves some information from the targeted system. It can connect back to a remote server and receive commands from it.
Figure 13. Details about the connection to the C2.
Figure 14. The sample is connecting back to the domain name strainservice[.]com.
Infrastructure
It is interesting to notice that the threat actor abused OpenDrive in one of the variants to deliver the payload. The OpenDrive account has been set up quickly for a one shot, indicating that it was created for only one target.
We identified one domain used as C2 server, strainservice[.]com and connected back to the two implants. This domain was registered on June 26 on Namecheap, just before the distribution of the first variant. At the time of the attack, the server had port 80, 443, and 2083. The implants were communicated on port 443.
Defending against targeted attacks
In this report we analyzed a targeted attack on cryptocurrency investment fund startups. Such companies are relatively new, but manage hundreds of millions of dollars, raising interest by threat actors.   
In this attack we identified that the threat actor has broad knowledge of the cryptocurrency industry as well as the challenges their targets may face, increasing the sophistication of the attack and their chance of success. The threat actor used Telegram, an app widely used in the field, to identify the profile of interest, gained the target’s trust by discussing relevant topics, and finally sent a weaponized document that delivered a backdoor through multiple mechanisms. Additionally, the second attack identified was luring a fake crypto dashboard application.
The cryptocurrency market remains a field of interest for threat actors. Targeted users are identified through trusted channels to increase the chance of success. While the biggest companies can be targeted, smaller companies can also be targets of interest. The techniques used by the actor covered in this blog can be mitigated by adopting the security considerations provided below:

Use the included indicators of compromise to investigate whether they exist in your environment and assess for potential intrusion.
Educate end users about protecting personal and business information in social media, filtering unsolicited communication (in this case, Telegram chat groups), identifying lures in spear-phishing email and watering holes, and reporting of reconnaissance attempts and other suspicious activity.
Educate end users about preventing malware infections, such as ignoring or deleting unsolicited and unexpected emails or attachments sent via instant messaging applications or social networks. Encourage end users to practice good credential hygiene and make sure the Microsoft Defender Firewall (which is enabled by default) is always on to prevent malware infection and stifle propagation.
Change Excel macro security settings to control which macros run and under what circumstances when you open a workbook. Customers can also stop malicious XLM or VBA macros by ensuring runtime macro scanning by Antimalware Scan Interface (AMSI) is on. This feature—enabled by default—is on if the Group Policy setting for Macro Run Time Scan Scope is set to “Enable for All Files” or “Enable for Low Trust Files”.
Turn on attack surface reduction rules to prevent common attack techniques observed in this threat:

Block Office applications from creating executable content
Block Office communication application from creating child processes
Block Win32 API calls from Office macros


Ensure that Microsoft Defender Antivirus is up to date and that real-time behavior monitoring is enabled.


Detection details
Microsoft Defender Antivirus
Microsoft Defender Antivirus detects threat components as the following malware:

TrojanDownloader:O97M/Wolfic.A
TrojanDownloader:O97M/Wolfic.B
TrojanDownloader:O97M/Wolfic.C
TrojanDownloader:Win32/Wolfic.D
TrojanDownloader:Win32/Wolfic.E
Behavior:Win32/WolficDownloader.A
Behavior:Win32/WolficDownloader.B

Microsoft Defender for Endpoint
Alerts with the following titles in the security center can indicate threat activity on your network:

An executable loaded an unexpected dll
DLL search order hijack
‘Wolfic’ malware was prevented

Advanced hunting queries
The following hunting queries locate relevant activity.
Query that looks for Office apps that create a file within one of the known bad directories:
DeviceFileEvents
| where InitiatingProcessFileName has_any ("word", "excel", "access", "outlook" "powerpnt")
| where ActionType == "FileCreated"
| where parse_path( FolderPath ).DirectoryPath has_any(
    @"C:\ProgramData\Microsoft Media",
    @"C:\ProgramData\SoftwareCache",
    @"Roaming\Dashboard_v2"
    )
| project Timestamp, DeviceName, FolderPath, InitiatingProcessFileName, SHA256, InitiatingProcessAccountName, InitiatingProcessAccountDomain

Query that looks for Office apps that create a file within an uncommon directory (less that five occurrences), makes a set of each machine this is seen on, and each user that has executed it to help look for how many users/hosts are compromised:
DeviceFileEvents
| where InitiatingProcessFileName has_any ("word", "excel", "access", "outlook", "powerpnt")
| where ActionType == "FileCreated"
| extend Path = tostring(parse_path(FolderPath).DirectoryPath)
| summarize PathCount=count(), DeviceList=make_set(DeviceName), AccountList=make_set(InitiatingProcessAccountName) by FileName, Path, InitiatingProcessFileName, SHA256
| where PathCount < 5

Query that summarizes child process of Office apps, looking for less than five occurrences:
DeviceProcessEvents
| where InitiatingProcessFileName has_any ("word", "excel", "access", "powerpnt")
| summarize ProcessCount=count(), DeviceList=make_set(DeviceName), AccountList=make_set(InitiatingProcessAccountName) by FileName, FolderPath, SHA256, InitiatingProcessFileName
| where ProcessCount < 5

Query that lists of all executables with Microsoft as ProcessVersionInfoCompanyName, groups them together by path, then looks for uncommon paths, with less than five occurrences:
DeviceProcessEvents
| where ProcessVersionInfoCompanyName has "Microsoft"
| extend Path = tostring(parse_path(FolderPath).DirectoryPath)
| summarize ProcessList=make_set(FileName) by Path
| where array_length( ProcessList ) < 5

Query that searches for connections to malicious domains and IP addresses:
DeviceNetworkEvents
| where (RemoteUrl has_any ("strainservice.com")) 
     or (RemoteIP has_any ("198.54.115.248"))

Query that searches for files downloaded from malicious domains and IP addresses.
DeviceFileEvents
| where (FileOriginUrl  has_any ("strainservice.com")) 
     or (FileOriginIP  has_any ("198.54.115.248"))

Query that searchers for Office apps downloading files from uncommon domains, groups users, filenames, and devices together:
DeviceFileEvents
| where InitiatingProcessFileName has_any ("word", "excel", "access", "powerpnt")
| where ActionType == "FileCreated"
| where isnotempty( FileOriginUrl ) or isnotempty( FileOriginIP )
| summarize DomainCount=count(), UserList=make_set(InitiatingProcessAccountName), DeviceList=make_set(DeviceName),
    FileList=make_set(FileName) by FileOriginUrl, FileOriginIP, InitiatingProcessFileName

Looks for downloaded files with uncommon file extensions, groups remote IPs, URLs, filenames, users, and devices:
DeviceFileEvents
| where InitiatingProcessFileName has_any ("word", "excel", "access", "powerpnt", "outlook")
| where ActionType == "FileCreated"
| where isnotempty( FileOriginUrl ) or isnotempty( FileOriginIP )
| extend Extension=tostring(parse_path(FolderPath).Extension)
| extend  Path=tostring(parse_path(FolderPath).DirectoryPath)
| summarize ExtensionCount=count(), IpList=make_set(FileOriginIP), UrlList=make_set(FileOriginUrl), FileList=make_set(FileName),
    UserList=make_set(InitiatingProcessAccountName), DeviceList=make_set(DeviceName) by Extension, InitiatingProcessFileName

Looks for Office apps that have child processes that match the GUID command line, with a check for Microsoft binaries to reduce the results before the regex:
DeviceProcessEvents
| where InitiatingProcessFileName has_any ("word", "excel", "access", "powerpnt")
| where ProcessVersionInfoCompanyName has "Microsoft"
| where ProcessCommandLine matches regex 
    @"[A-Za-z0-9]+\.exe [A-Za-z0-9]{8}-[A-Za-z0-9]{4}-[A-Za-z0-9]{4}-[A-Za-z0-9]{4}-[A-Za-z0-9]{12} /[A-Za-z0-9]$"

Microsoft Sentinel
Microsoft Sentinel customers can use the TI Mapping analytic to automatically match the malicious IP and domain indicators mentioned in this blog post with data in their workspace. If the TI Map analytics are not currently deployed, customers can install the Threat Intelligence solution from the Microsoft Sentinel Content Hub to have the analytics rule deployed in their Sentinel workspace. More details on the Content Hub can be found here:  https://learn.microsoft.com/azure/sentinel/sentinel-solutions-deploy 
To supplement this indicator matching customers can use the Advanced Hunting queries listed above against Microsoft 365 Defender data ingested into their workspaces as well as the following Microsoft Sentinel queries:

Least common parent and child process pairs: https://github.com/Azure/Azure-Sentinel/blob/master/Solutions/Windows%20Security%20Events/Hunting%20Queries/Least_Common_Parent_Child_Process.yaml 


Detect anomalous process trees: https://github.com/Azure/Azure-Sentinel/blob/46906229919827bffa14211341f52dd68e27ad81/Hunting%20Queries/Microsoft%20365%20Defender/Execution/detect-anomalous-process-trees.yaml

Indicators of compromise
IOCFilename/Type Descriptionabca3253c003af67113f83df2242a7078d5224870b619489015e4fde060acad0OKX Binance & Huobi VIP fee comparision.xlsWeaponized Excel file17e6189c19dedea678969e042c64de2a51dd9fba69ff521571d63fd92e48601bOKX Binance & Huobi VIP fee comparision.xlsWeaponized Excel filea2d3c41e6812044573a939a51a22d659ec32aea00c26c1a2fdf7466f5c7e1ee9VSDB688.tmpSecond worksheet dropped2e8d2525a523b0a47a22a1e9cc9219d6526840d8b819d40d24046b17db8ea3fbwsock32.dll / HijackingLib.dllMalicious dropper that acts as a DLL proxy to legit wsock32.dll82e67114d632795edf29ce1d50a4c1c444846d9e16cd121ce26e63c8dc4a1629Duser.dll 90b0a4c9fe8fd0084a5d50ed781c7c8908f6ade44e5654acffea922e281c6b33Duser.dll / HijackingLib.dllMalicious dropped that acts as a DLL proxy to the legit Duser.dlle5980e18319027f0c28cd2f581e75e755a0dace72f10748852ba5f63a0c994874acbe3.msiFake CryptoDashboard application MSI package  delivering Duser.dlleee4e3612af96b694e28e3794c4ee4af2579768e8ec6b21daf71acfc6e22d52b43d972.msiSecond fake application BloxHolder delviering Duser.dllea31e626368b923419e8966747ca33473e583376095c48e815916ff90382dda5DLLImplant loaded by Duser.dllC:\ProgramData\SoftwareCache\wsock32.dllPathPath of wsock32.dllC:\Users\user\AppData\Roaming\Dashboard_v2\DUser.dllPathPath of Duser.DllC:\Program Files\CryptoDashboardV2\PathPath of the fake appC:\ProgramData\Microsoft Media\VSDB688.tmpPathPath of the second worksheethxxps://od.lk/d/d021d412be456a6f78a0052a1f0e3557dcfa14bf25f9d0f1d0d2d7dcdac86c73/Background.pngBackground.png downloaded from OpenDrivePng file downloaded on the victim machines strainservice.comDomain/C2Command and control server198.54.115.248IP/C2IP of the C256762eb9-411c-4842-9530-9922c46ba2da GUIDGUID used 27E57D84-4310-4825-AB22-743C78B8F3AAGUIDGUID used TPLink.exe” 27E57D84-4310-4825-AB22-743C78B8F3AA /svenCommand lineCommand line runs by the legit exelogagent.exe 56762eb9-411c-4842-9530-9922c46ba2da /shadowCommand lineCommand line runs by the legit file
MITRE ATT&CK techniques
TacticsTechnique IDNameDescriptionReconnaissanceT1591Gather Victim Org InformationThe attackers gathered information about the targets reaching them on Telegram with a clear understanding of their challenges.T1593.001Social MediaAttackers identified the targets on specific crypto currencies group on Telegram.Resource DevelopmentT1583.001Acquire Infrastructure: DomainsAttackers registered the domain “strainservice.com” on June 18Initial Access T1566.001Spearphishing AttachmentAttackers sent a weaponized Excel document.ExecutionExecutionT1204.002User Execution: Malicious FileThe targeted user must open the weaponized Excel document and enable macros.T1059.005Command and Scripting Interpreter: Visual BasicAttackers used VBA in the malicious excel document “OKX Binance & Huobi VIP fee comparision.xls” to deliver the implant.T1106Native APIUsage of CreateProcess API in the excel document to run the executable.Persistence, Privilege Escalation, Defense EvasionT1574.002DLL side-LoadingThe attackers abused the legitimate Logagent.exe to side-load the malicious wsock32.dll and the legitimate TPLink.Exe to side load Duser.dllDefense EvasionT1027Obfuscated file or informationThe malicious VBA is obfuscated using UserForm to hide variable and data.T1036.005Masquerading: Match Legitimate Name or LocationThe attackers are using legitimate DLL name that acts as DLL Proxy to the original one (wsock32.dll and Duser.dll).T1027.009Obfuscated Files or Information: Embedded PayloadsThe malicious DLL are dropping the implant into the machine.Command & ControlT1071.001Application Layer Protocol: Web ProtocolsThe implant is communicating to the remote domain through port 80 or 443.T1132Data EncodingThe implant is encoding the data exchanged with the C2.ExfiltrationT1041Exfiltration over C2 channelThe implant has the ability to exfiltrate information.




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



									Threat intelligence								



									Microsoft Defender XDR								



									Vulnerabilities and exploits								

 

Published Oct 18				

						10 min read					




Multiple North Korean threat actors exploiting the TeamCity CVE-2023-42793 vulnerability 



			 Since early October 2023, Microsoft has observed North Korean nation-state threat actors Diamond Sleet and Onyx Sleet exploiting the Jet Brains TeamCity CVE-2023-42793 remote-code execution vulnerability. Given supply chain attacks carried out by these threat actors in the past, Microsoft assesses that this activity poses a particularly high risk to organizations who are affected.		








 








									Research								



									Threat intelligence								



									Influence operations								

 

Published Mar 2				

						10 min read					




New research, tooling, and partnerships for more secure AI and machine learning 



			At Microsoft, we’ve been working on the challenges and opportunities of AI for years. Today we’re sharing some recent developments so that the community can be better informed and better equipped for a new world of AI exploration.		














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

































