# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: North Korea's Lazarus APT leverages Windows Update client, GitHub in latest campaign

**Source**: https://blog.malwarebytes.com/threat-intelligence/2022/01/north-koreas-lazarus-apt-leverages-windows-update-client-github-in-latest-campaign/

## Content











North Korea's Lazarus APT leverages Windows Update client, GitHub in latest campaign













































 




 








Skip to content





Search

Search Malwarebytes.com



Search for:








Contact Us

Personal Support
Business Support
Talk to Sales
Contact Press
Partner Programs
Submit Vulnerability


Company

About Malwarebytes
Careers
News & Press


Sign In

MyAccount sign in: manage your personal or Teams subscription >
Cloud Console sign in: manage your cloud business products >
Partner Portal sign in: management for Resellers and MSPs >


 














Personal


< Personal

ProductsMalwarebytes Premium >Malwarebytes Privacy VPN >Malwarebytes Identity Theft Protection >Malwarebytes Browser Guard >Malwarebytes for Teams/small offices >AdwCleaner for Windows >

Find the right productSee our plansInfected already?Clean your device now




SolutionsFree antivirus >Free virus scan & removal >Windows antivirus >Mac antivirus >Android antivirus >iOS security >Chromebook antivirus >
See personal pricingManage your subscriptionVisit our support page 





Business


< Business
BUNDLESCorePrevent and remediate threats and identify vulnerabilitiesAdvancedUtilize threat guidance and patch management plus everything in CoreEliteDeploy Managed Detection and Response plus everything in AdvancedUltimateProtect against categories of malicious websites plus everything in Elite


TECHNOLOGY HIGHLIGHTSManaged Detection & Response (MDR) Deploy fully-managed threat monitoring, investigation, and remediationEndpoint Detection & Response (EDR)Prevent more attacks with security that catches what others missSecurity AdvisorVisualize and optimize your security posture in just minutesFor EducationSecure your students and institution against cyberattacks







Learn more about Security Advisor (available in every bundle) and see the full list of our products and services.
Full technology list >




Pricing



< Pricing
Personal pricingProtect your personal devices and dataSmall office/home office pricingProtect your team’s devices and dataBusiness pricingExplore our award-winning endpoint security products, from EP to EDR to MDR




Partners



< Partners
Explore PartnershipsPartner SolutionsResellersManaged Service ProvidersComputer RepairTechnology PartnersAffiliate PartnersContact Us




Resources


< Resources
Learn About CybersecurityAntivirusMalwareRansomwareMalwarebytes Labs – BlogGlossaryThreat Center


Business ResourcesReviewsAnalyst ReportsCase StudiesPress & News


ReportsThe State of Malware 2023 ReportRead report



Support



< Support
Technical SupportPersonal SupportBusiness SupportPremium ServicesForumsVulnerability DisclosureReport a False Positive


Featured ContentActivate Malwarebytes Privacy on Windows device.See Content Product Videos



 

Free Download




Search
Search

Search Malwarebytes.com



Search for:









































SUBSCRIBE


rss

































 


Threat Intelligence

North Korea’s Lazarus APT leverages Windows Update client, GitHub in latest campaign 
Posted: January 27, 2022
 by Threat Intelligence Team 


This blog was authored by Ankur Saini and Hossein Jazi  Lazarus Group is one of the most sophisticated North Korean APTs that has been active since 2009. The group is responsible for many high profile attacks in the past and has gained worldwide attention. The Malwarebytes Threat Intelligence team is actively monitoring its activities and was able to spot a new campaign on Jan 18th 2022.  In this campaign, Lazarus conducted spear phishing attacks weaponized with malicious documents that use their known job opportunities theme. We identified two decoy documents masquerading as American global security and aerospace giant Lockheed Martin.  In this blog post, we provide technical analysis of this latest attack including a clever use of Windows Update to execute the malicious payload and GitHub as a command and control server. We have reported the rogue GitHub account for harmful content.  Analysis   The two macro-embedded documents seem to be luring the targets about new job opportunities at Lockheed Martin:   Lockheed_Martin_JobOpportunities.docx Salary_Lockheed_Martin_job_opportunities_confidential.doc  The compilation time for both of these documents is 2020-04-24, but we have enough indicators that confirm that they have been used in a campaign around late December 2021 and early 2022. Some of the indicators that shows this attack operated recently are the domains used by the threat actor.  Both of the documents use the same attack theme and have some common things like embedded macros but the full attack chain seems to be totally different. The analysis provided in the blog is mainly based on the “Lockheed_Martin_JobOpportunities.docx” document but we also provide brief analysis for the second document (Salary_Lockheed_Martin_job_opportunities_confidential.doc) at the end of this blog.     Attack Process   The below image shows the full attack process which we will discuss in detail in this article. The attack starts by executing the malicious macros that are embedded in the Word document. The malware performs a series of injections and achieves startup persistence in the target system. In the next section we will provide technical details about various stages of this attack and its payload capabilities.   Macros: Control flow hijacking through KernelCallbackTable     The above code uses a very unusual and lesser known technique to hijack the control flow and execute malicious code. The malware retrieves the address of the “WMIsAvailableOffline” function from “wmvcore.dll”, then it changes the memory protection permissions for code in “WMIsAvailableOffline” and proceeds to overwrite the code in memory with the malicious base64 decoded shell-code.  Another interesting thing happening in the above code is the control flow hijacking through the KernelCallbackTable member of the PEB. A call to NtQueryInformationProcess is made with ProcessBasicInformation class as the parameter which helps the malware to retrieve the address of PEB and thus retrieving the KernelCallbackTable pointer.     KernelCallbackTable is initialized to an array of callback functions when user32.dll is loaded into memory, which are used whenever a graphical call (GDI) is made by the process. To hijack the control flow, malware replaces the USER32!_fnDWORD callback in the table with the malicious WMIsAvailableOffline function. Once the flow is hijacked and malicious code is executed the rest of the code takes care of restoring the KernelCallbackTable to its original state.  Shellcode Analysis   The shellcode loaded by the macro contains an encrypted DLL which is decrypted at runtime and then manually mapped into memory by the shellcode. After mapping the DLL, the shellcode jumps to the entry point of that DLL. The shellcode uses some kind of custom hashing method to resolve the APIs. We used hollows_hunter to dump the DLL and reconstruct the IAT once it is fully mapped into memory.     The hashing function accepts two parameters: the hash of the DLL and the hash of the function we are looking for in that DLL. A very simple algorithm is used for hashing APIs. The following code block shows this algorithm:   def string_hashing(name):     hash = 0     for i in range(0, len(name)):         hash = 2 * (hash + (ord(name[i]) | 0x60))     return hash  The shellcode and all the subsequent inter-process Code/DLL injections in the attack chain use the same injection method as described below.  Code Injection   The injection function is responsible for resolving all the required API calls. It then opens a handle to the target process by using the OpenProcess API. It uses the SizeOfImage field in the NT header of the DLL to be injected into allocated space into the target process along with a separate space for the init_dll function. The purpose of the init_dll function is to initialize the injected DLL and then pass the control flow to the entry point of the DLL. One thing to note here is a simple CreateRemoteThread method is used to start a thread inside the target process unlike the KernelCallbackTable technique used in our macro.     Malware Components    stage1_winword.dll – This is the DLL which is mapped inside the Word process. This DLL is responsible for restoring the original state of KernelCallbackTable and then injecting stage2_explorer.dll into the explorer.exe process.      stage2_explorer.dll – The winword.exe process injects this DLL into the explorer.exe process. With brief analysis we find out that the .data section contains two additional DLLs. We refer to them as drops_lnk.dll and stage3_runtimebroker.dll. By analyzing stage2_explorer.dll a bit further we can easily understand the purpose of this DLL.     The above code snippet shows the main routine of stage2_explorer.dll. As you can see it checks for the existence of “C:Wíndowssystem32wuaueng.dll” and then if it doesn’t exist it takes its path to drop additional files. It executes the drops_lnk.dll in the current process and then tries to create the RuntimeBroker process and if successful in creating RuntimeBroker, it injects stage3_runtimebroker.dll into the newly created process. If for some reason process creation fails, it just executes stage3_runtimebroker.dll in the current explorer.exe process.   drops_lnk.dll – This DLL is loaded and executed inside the explorer.exe process, it mainly drops the lnk file (WindowsUpdateConf.lnk) into the startup folder and then it checks for the existence of wuaueng.dll in the malicious directory and manually loads and executes it from the disk if it exists. The lnk file (WindowsUpdateConf.lnk) executes “C:Windowssystem32wuauclt.exe” /UpdateDeploymentProvider C:Wíndowssystem32wuaueng.dll /RunHandlerComServer. This is an interesting technique used by Lazarus to run its malicious DLL using the Windows Update Client to bypass security detection mechanisms. With this method, the threat actor can execute its malicious code through the Microsoft Windows Update client by passing the following arguments: /UpdateDeploymentProvider, Path to malicious dll and /RunHandlerComServer argument after the dll.         stage3_runtimebroker.dll – This DLL is responsible for creating the malicious directory (“C:Wíndowssystem32”) and then drops the wuaueng.dll in that directory, furthermore it sets the attributes of the directory to make it hidden.      wuaueng.dll – This is one of the most important DLLs in the attack chain. This malicious DLL is signed with a certificate which seems to belong to “SAMOYAJ LIMITED”, Till 20 January 2022, the DLL had (0/65) AV detections and presently only 5/65 detect it as malicious. This DLL has embedded inside another DLL which contains the core module (core_module.dll) of this malware responsible for communicating with the Command and Control (C2) server. This DLL can be loaded into memory in two ways: – If drops_lnk.dll loads this DLL into explorer.exe then it loads the core_module.dll and then executes it– If it is being executed from wuauclt.exe, then it retrieves the PID of explorer.exe and injects the core_module.dll into that process.     The Core module and GitHub as a C2   Rarely do we see malware using GitHub as C2 and this is the first time we’ve observed Lazarus leveraging it. Using Github as a C2 has its own drawbacks but it is a clever choice for targeted and short term attacks as it makes it harder for security products to differentiate between legitimate and malicious connections. While analyzing the core module we were able to get the required details to access the C2 but unfortunately it was already cleaned and we were not able to get much except one of the additional modules loaded by the core_module.dll remotely (thanks to @jaydinbas who shared the module with us).     There seems to be no type of string encoding used so we can clearly see the strings which makes the analysis easy. get_module_from_repo uses the hardcoded username, repo_name, directory, token to make a http request to GitHub and retrieves the files present in the “images” directory of the repository.     The HTTP request retrieves contents of the files present in the repository with an interesting validation which checks that the retrieved file is a PNG. The file that was earlier retrieved was named “readme.png”; this PNG file has one of the malicious modules embedded in it. The strings in the module reveal that the module’s original name is “GetBaseInfo.dll”. Once the malware retrieves the module it uses the map_module function to map the DLL and then looks for an exported function named “GetNumberOfMethods” in the malicious module. It then executes GetNumberOfMethods and saves the result obtained by the module. This result is committed to the remote repo under the metafiles directory with a filename denoting the time at which the module was executed. This file committed to the repo contains the result of the commands executed by the module on the target system. To commit the file the malware makes a PUT HTTP request to Github.  Additional Modules (GetBaseInfo.dll)   This was the only module which we were able to get our hands on. Only a single module does limit us in finding all the capabilities this malware has. Also its a bit difficult to hunt for these modules as they never really touch the disk which makes them harder to detect by AVs. The only way to get the modules would be to access the C2 and download the modules while they are live. Coming back to this module, it has very limited capabilities. It retrieves the Username, ComputerName and a list of all the running processes on the system and then returns the result so it can be committed to the C2.     GitHub Account   The account with the username “DanielManwarningRep” is used to operate the malware. The account was created on January 17th, 2022 and other than this we were not able to find any information related to the account.     Second Malicious Document used in the campaign   Malicious Document – Salary_Lockheed_Martin_job_opportunities_confidential.doc (0160375e19e606d06f672be6e43f70fa70093d2a30031affd2929a5c446d07c1)  The initial attack vector used in this document is similar to the first document but the malware dropped by the macro is totally different. Sadly, the C2 for this malware was down by the time we started analyzing it.  This document uses KernelCallbackTable as well to hijack the control flow just like our first module, the injection technique used by the shellcode also resembles the first document. The major difference in this document is that it tries to retrieve a remote HTML page and then executes it using mshta.exe. The remote HTML page is located at https[:]//markettrendingcenter[.]com/member.htm and throws a 404 Not Found which makes it difficult for us to analyze this document any further.     Attribution   There are multiple indicators that suggest that this campaign has been operated by the Lazarus threat actor. In this section we provide some of the indicators that confirm the actor behind this attack is Lazarus:   Using job opportunities as template is the known method used by Lazarus to target its victims. The documents created by this actor are well designed and contain a large icon for a known company such as LockHeed Martin, BAE Systems, Boeing and Northrop Grumman in the template. In this campaign the actor has targeted people that are looking for job opportunities at Lockheed Martin. Targeting the defense industry and specifically Lockheed Martin is a known target for this actor. The document’s metadata used in this campaign links them to several other documents used by this actor in the past.      Using Frame1_Layout for macro execution and using lesser known API calls for shellcode execution is known to be used by Lazarus. We also were able to find infrastructure overlap between this campaign and past campaigns of Lazarus (Figure 19).     Conclusion   Lazarus APT is one of the advanced APT groups that is known to target the defense industry. The group keeps updating its toolset to evade security mechanisms. In this blog post we provided a detailed analysis about the new campaign operated by this actor. Even though they have used their old job theme method, they employed several new techniques to bypass detections:   Use of KernelCallbackTable to hijack the control flow and shellcode execution Use of the Windows Update client for malicious code execution Use of GitHub for C2 communication     IOCs:   Maldocs:0d01b24f7666f9bccf0f16ea97e41e0bc26f4c49cdfb7a4dabcc0a494b44ec9b Lockheed_Martin_JobOpportunities.docx0160375e19e606d06f672be6e43f70fa70093d2a30031affd2929a5c446d07c1Salary_Lockheed_Martin_job_opportunities_confidential.docDomains:markettrendingcenter.comlm-career.comPayloads:       Name Sha256   readme.png 4216f63870e2cdfe499d09fce9caa301f9546f60a69c4032cb5fb6d5ceb9af32   wuaueng.dll 829eceee720b0a3e505efbd3262c387b92abdf46183d51a50489e2b157dac3b1   stage1_winword.dll f14b1a91ed1ecd365088ba6de5846788f86689c6c2f2182855d5e0954d62af3b   stage2_explorer.dll 660e60cc1fd3e155017848a1f6befc4a335825a6ae04f3416b9b148ff156d143   drops_lnk.dll 11b5944715da95e4a57ea54968439d955114088222fd2032d4e0282d12a58abb   stage3_runtimebroker.dll 9d18defe7390c59a1473f79a2407d072a3f365de9834b8d8be25f7e35a76d818   core_module.dll c677a79b853d3858f8c8b86ccd8c76ebbd1508cc9550f1da2d30be491625b744   GetBaseInfo.dll 5098ec21c88e14d9039d232106560b3c87487b51b40d6fef28254c37e4865182       




SHARE THIS ARTICLE
































RELATED ARTICLES





 



News
																	 | 																	Privacy

Facebook Marketplace users’ stolen data offered for sale


February 15, 2024 - Personal data belonging to 200,000 Facebook Marketplace users has been published online, including email addresses and phone numbers.

CONTINUE READING
 0 Comments






 



Cybercrime
																	 | 																	Ransomware
																	 | 																	Threats

How ransomware changed in 2023


February 14, 2024 - In 2023, the CL0P ransomware gang broke the scalability barrier and shook the security world with a series of short, automated campaigns.

CONTINUE READING
 0 Comments






 



News
																	 | 																	Personal

Malwarebytes crushes malware all the time


February 14, 2024 - The PC Security Channel tested Malwarebytes against 2015 files.  Here's how we did.

CONTINUE READING
 0 Comments






 



Exploits and vulnerabilities
																	 | 																	News

Update now! Microsoft fixes two zero-days on February Patch Tuesday


February 14, 2024 - Microsoft has issued patches for 73 security vulnerabilities in its February 2024 Patch Tuesday.

CONTINUE READING
 0 Comments






 



Android
																	 | 																	News
																	 | 																	Personal

TheTruthSpy stalkerware, still insecure, still leaking data


February 13, 2024 - Stalkerware app TheTruthSpy has been hacked for the fourth time, once again leaking the sensitive data it captures.

CONTINUE READING
 0 Comments










ABOUT THE AUTHOR









Threat Intelligence Team













Contributors



Threat Center



Podcast



Glossary



Scams










 

					Cyberprotection for every one.					



FOR PERSONAL
Windows Antivirus
Mac Antivirus
Android Antivirus
Free Antivirus
VPN App (All Devices)
Malwarebytes for iOS
SEE ALL

COMPANY
About Us
Contact Us
Careers
News and Press
Blog
Scholarship
Forums
 

FOR BUSINESS
Small Businesses
Mid-size business
Larger Enterprise
Endpoint Protection
Endpoint Detection & Response
Managed Detection and Response (MDR)

FOR PARTNERS
Managed Service Provider (MSP) Program
Resellers

MY ACCOUNT
Sign In


SOLUTIONS
Rootkit Scanner
Trojan Scanner
Virus Scanner
Spyware Scanner
Password Generator
Anti Ransomware Protection

ADDRESS
One Albert Quay2nd FloorCork T12 X8N6Ireland
3979 Freedom Circle12th FloorSanta Clara, CA 95054


LEARN
Malware
Hacking
Phishing
Ransomware
Computer Virus
Antivirus
What is VPN?
 




 Twitter




 Facebook




 LinkedIn




 Youtube




 Instagram




Cybersecurity info you can’t live without
Want to stay informed on the latest news in cybersecurity? Sign up for our newsletter and learn how to protect your computer from threats.


Email Address



















English


Legal
Privacy
Accessibility
Vulnerability Disclosure
Terms of Service
 
						© 2024 All Rights Reserved						










Select your language








































