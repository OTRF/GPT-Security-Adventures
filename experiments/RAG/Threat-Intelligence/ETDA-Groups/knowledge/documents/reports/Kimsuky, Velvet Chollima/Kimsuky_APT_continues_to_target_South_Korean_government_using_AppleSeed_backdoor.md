# Reference for threat actor for "Kimsuky, Velvet Chollima"

**Title**: Kimsuky APT continues to target South Korean government using AppleSeed backdoor

**Source**: https://blog.malwarebytes.com/threat-analysis/2021/06/kimsuky-apt-continues-to-target-south-korean-government-using-appleseed-backdoor/

## Content











Kimsuky APT continues to target South Korean government using AppleSeed backdoor













































 




 








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

Kimsuky APT continues to target South Korean government using AppleSeed backdoor 
Posted: June 1, 2021
 by Threat Intelligence Team 


This blog post was authored by Hossein Jazi.  The Kimsuky APT—also known as Thallium, Black Banshee, and Velvet Chollima—is a North Korean threat actor that has been active since 2012. The group conducts cyber espionage operations to target government entities mainly in South Korea. On December 2020, KISA (Korean Internet & Security Agency) provided a detailed analysis about the phishing infrastructure and TTPs used by Kimsuky to target South Korea.  The Malwarebytes Threat Intelligence team is actively monitoring this actor and has been able to spot phishing websites, malicious documents, and scripts that have been used to target high profile people within the government of South Korea. The structure and TTPs used in these recent activities align with what has been reported in KISA’s report.  Targets   One of the lures used by Kimsuky named “외교부 가판 2021-05-07” in Korean language translates to “Ministry of Foreign Affairs Edition 2021-05-07” which indicates that it has been designed to target the Ministry of Foreign Affairs of South Korea. According to our collected data, we have identified that it is one entity of high interest for Kimsuky. Other targets associated with the Korean government include:   Ministry of Foreign Affairs, Republic of Korea 1st Secretary Ministry of Foreign Affairs, Republic of Korea 2nd Secretary Trade Minister Deputy Consul General at Korean Consulate General in Hong Kong International Atomic Energy Agency (IAEA) Nuclear Security Officer Ambassador of the Embassy of Sri Lanka to the State Ministry of Foreign Affairs and Trade counselor  Beside targeting government, we also have observed that Kimsuky collected information about universities and companies in South Korea including the Seoul National University and Daishin financial security company as well as KISA. This does not mean the threat actors actively targeted them yet nor that they were compromised.  Phishing Infrastructure   The group has the capability to set up phishing infrastructure to mimic well known websites and trick victims to enter their credentials. This is one of the main methods used by this actor to collect email addresses that later will be used to send spearphishing emails. The group is still using similar phishing models previously mentioned in the KISA report with some small changes.  As an example, they have added the Mobile_detect and Anti_IPs modules from type B to type C (KISA report) in order to be able to detect mobile devices and adjust the view based on that. This phishing model has the capability to show phishing pages in English or Korean based on the parameter value received from the phishing email. This model has been deployed by Kimsuky to target not only Korean speaking victims but also English speaking people, as well.     We have observed that they developed different phishing techniques to mimic the following web services and steal credentials:   Gmail Hotmail Microsoft Outlook Nate Daum Naver Telegram KISA     We have identified several URLs used by Kimsuky to host their phishing infrastructure:  http://accounts[.]goggle[.]hol[.]es/MyAccounthttps://myaccount[.]google[.]newkda[.]com/signinhttp://myaccount[.]google[.]newkda[.]com/signinhttp://myaccount[.]google[.]nkaac[.]net/signinhttps://myaccounts-gmail[.]autho[.]co/signinhttp://myaccounts-gmail[.]kr-infos[.]com/signinhttp://myaccount[.]cgmail[.]pe[.]hu/signinhttps://accounts[.]google-manager[.]ga/signinhttps://accounts[.]google-signin[.]ga/v2https://myaccount[.]google-signin[.]ga/signinhttps://account[.]grnail-signin[.]ga/v2https://myaccount[.]grnail-signin[.]ga/v2https://myaccounts[.]grnail-signin[.]ga/v2https://accounts[.]grnail-signin[.]ga/v2https://protect[.]grnail-signin[.]ga/v2https://accounts[.]grnail-signing[.]work/v2https://myaccount[.]grnail-signing[.]work/v2https://myaccount[.]grnail-security[.]work/v2https://signin[.]grnail-login[.]mlhttps://login[.]gmail-account[.]gqhttps://signin[.]gmrail[.]mlhttps://login[.]gmeil[.]kro[.]krhttps://account[.]googgle[.]kro[.]kr  The group has used Twitter accounts to find and monitor its targets to prepare well crafted spear phishing emails. The group also is using Gmail accounts to use for phishing attacks or registering domains. One of the Gmail accounts used by this actor is ” tjkim1991@gmail[.]com” which was used to register the following sub-domains:  ns1.microsoft-office[.]usns2.microsoft-office[.]us  They were registered on April 3 and we believe have been reserved to be used for future campaigns. Pivoting from these sub-domains, we were able to uncover the infrastructure used by this actor. Some of it has overlap with previously reported campaigns operated by Kimsuky.     Command and Control infrastructure   Kimsuky reuses some of its phishing infrastructure for its command and control communications. In their most recent attack against South Korea’s government they reused the infrastructure that has been used to host their phishing websites for AppleSeed backdoor C&C communications. Besides using the AppleSeed backdoor to target Windows users, the actor also has used an Android backdoor to target Android users. The Android backdoor can be considered as the mobile variant of the AppleSeed backdoor. It uses the same command patterns as the Windows one. Also, both Android and Windows backdoors have used the same infrastructure. It is also interesting to mention that this actor calls themselves Thallium.     Here are some of IPs and domains used by the actor for C2 communications:   210.16.120[.]34 216.189.157[.]89 45.58.55[.]73 45.13.135[.]103 27.102.114[.]89 210.16.121[.]137 58.229.208[.]146  27.102.107[.]63 download.riseknite[.]life onedrive-upload.ikpoo[.]cf alps.travelmountain[.]ml texts.letterpaper[.]press  Analysis of the most recent AppleSeed attack   In this section we provide an analysis of the AppleSeed backdoor that has been used to target the Ministry of the Foreign Affairs of South Korea.  Initial Access   The actor has distributed its dropper embedded in an archive file (외교부 가판 2021-05-07.zip) as an attachment through spearphishing emails. The target email addresses have been collected using the actor email phishing campaigns we described in the previous section. The actor conducted this spearphishing attack on May 7, 2021. The archive file contains a JavaScript file (외교부 가판 2021-05-07.pdf.jse) which pretends to be a PDF file that contains two Base64 encoded blobs. The first one is the content of the decoy PDF file in Base64 format and the other one contains the AppleSeed payload also in Base64 format (encoded twice).  At first it uses the MSXML Base64 decoding functionality to decode the first layer and then uses certutil.exe to decode the second layer and get the final ApppleSeed payload. The decoy PDF file has been decoded using the MSXML Base64 decoding function.     After decoding the PDF and AppleSeed payload, the content gets written into the ProgramData directory. At the end, the decoy PDF file is opened by calling Wscript.Shell.Run and the AppleSeed payload executed through PowerShell by calling regsvr32.exe. Calling regsvr32.exe to run a DLL registers it as a server that automatically calls the DLL export function that has been named DllRegisterServer.   powershell.exe -windowstyle hidden regsvr32.exe /s AppleSeed_Payload   Wscript_Shell.Run(Pdf_Name);  AppleSeed Backdoor   The dropped payload is a DLL file that has been packed using the UPX packer. The unpacked sample is highly obfuscated and important API calls and strings have been encrypted using a custom encryption algorithm. The encrypted version of the strings and API calls are in hex ASCII format. Whenever in the code the malware needs to use a string, it takes the encrypted string and passes it into two functions to decrypt it.  The first function “string_decryptor_prep” gets the encrypted string and then prepares a custom data structure that has four elements:   typedef struct _UNICODESTR { 	wchar_t *Buffer; // Encrypted string  	DWORD padding; 	uint64_t Length; // Length of the string 	uint64_t MaxLength; // Max length for the string which has been calculated based on the lenght } UNICODESTR;   The second function “string_decryptor” gets the created data structure in the previous function and then decrypts the string and puts it in the same data structure.     The decryptor function first convert the input string in hex ascii format to binary by calling the hexascii_to_binary function on each two ascii characters (i.e. c3, 42, b1, 1d… in example 1). The first 16 bytes of in the input is then used as the key and the remainder is the actual value that gets decrypted in 16 byte chunks (i.e. ed, d5, 0d, 60). Decryption is a simple xor operation of key[i] ^ string[i-1] ^ string[i] (For the first character string_to_be_decrypted[i-1] is set to zero).     Most of the important API calls resolve dynamically during the run time using “string_decryptor” function. (288 API calls have been resolved dynamically.)     The AppleSeed payload has an export function named “DllRegisterServer” which will be called when the DLL is executed using RegSvr32.exe. DllRegisterServer has a function that is responsible for performing the DLL initialization and setup that includes the following steps:   Copy itself into “C:ProgramDataSoftwareESTsoftCommon” and rename itself as ESTCommon.dll to pretend it is a DLL that belongs to ESTsecurity company. Make itself persistent by creating the following registry key:   Registry key name: EstsoftAutoUpdate Registry key value: Regsvr32.exe /s C:ProgramDataSoftwareESTsoftCommonESTCommon.dll Registry location: HKLUSoftwareMicrosoftWindowsCurrentVersionRunOnce      Functionality activation by creating the following files into “C:ProgramDataSoftwareESTsoftCommonflags” directory and writes “flag” into them: FolderMonitor, KeyboardMonitor, ScreenMonitor, UsbMonitor.  In the next step it creates a Mutex to make sure it only infects a victim once.     After creating that mutex, it checks if the current process has the right access privilege by calling GetTokenInformation API call and if it does not have the right privilege, it tries to escalate its privilege using AdjustTokenPrivilege by passing SeDebugPrivilege to it to gain system level privilege.     At the end it performs its main functionalities in separate threads. All the the collected data in each thread is being zipped and encrypted and is being sent to the command and control server using HTTP POST requests in a separate thread. After sending the data to the server, the data is deleted from the victim’s machine. The ApppleSeed payload is using RC4 for encryption and decryption of the data. To generate RC4 key, it creates a Random buffer of 117 bytes by Calling CryptGenRandom and then uses CryptCreateHash and CryptHashData to adds the buffer into a MD5 hash object. Then it calls CryptDeriveKey to generate the RC4 key. The created 117 bytes buffer is encrypted using RSA algorithm and is sent to the sever along with RC4 encrypted data. The RSA key is in hex ASCII format and has been decrypted using “string_decryptor” function.  Input Capture (KeyLogger)   The keylogger function uses GetKeyState and GetKeyboardState to capture the pressed keys on the victim’s machine and logs all keys per process into the log.txt file.     Screen Capture   This module takes screenshots by calling the following sequence of API calls and writes them to files: GetDesktopWindow, GetDC, CreateCompstibleDC, CreateCompatibleBitmap, Bitblt and GetDIBits and then writes them into a file using CreateFileW and WriteFile.     Collect removable media data   This module finds the removable media devices connected to the machine and collects its data before sending it to the command and control server. To identify a USB drive it calls CM_Get_Device_IDW to retrieve the device instance ID that would be in format “” and then checks if it contains USB string value.     Collect files   This thread looks for txt, ppt, hwp, pdf, and doc files in the Desktop, Documents, Downloads and AppDataLocalMicrosoftWindowsINetCacheIE directories and archives them to be ready to be exfiltrated to the server.     Command structure   The AppleSeed backdoor is using a two layer command structure to communicate to its command and control server. Here is the URL pattern used for C&C communications:   entity:url url:?m=[command layer one]&p1=[volume serial number]&p2=[command layer two]   Command layer one defines the type of command that server expected to be executed on the victim and it can have one of the following values:       Command Description   a ping mode (Collect victim info including IP, Time stamp, victim OS version)   b upload data mode   c Download command (Waiting for command)   d Delete command   e Upload command mode   f List directories mode   g Delete file mode   h Check existence of a file mode    Command Layer one   Command layer 2 is only for when the command layer 1 is in upload data mode (c) and defines the type of upload. It can have one of the following values:       Command Description   a Upload command execution results   b Upload files and removable media data   c Upload screenshots   d Upload input capture data (Keylogger data)    Command layer 2   Conclusion   Kimsuky is one of North Korea’s threat actors that has mainly targeted South Korean government entities. In this blog post we took a look at this group’s activities including its phishing infrastructure and command and control mechanisms. Our research has shown that the group is still using a similar infrastructure and TTPs as reported on December 2020 by KISA. Its most recent campaign targeted the ministry of foreign affairs using the Apple Seed backdoor.     MITRE ATT&CK Techniques       Tactic ID Name Details   Reconnaissance T1598 Phishing for Information Use phishing to collect email addresses for targeted attack   Resource Development T1583.00 Acquire Infrastructure: Domains Purchase and register domains a few month before the attack   Resource Development T1587.001 Develop Capabilities: Malware Develop AppleSeed backdoor for the attack   Resource Development T1585.002 Establish Accounts: Email Accounts Create email accounts to register domains and use in phishing attacks   Resource Development T1585.001 Establish Accounts: Social Media Accounts Use Twitter to collect info about victims   Initial Access T1566.001 Phishing: Spearphishing Attachment Distributing archive files that contains JS dropper through phishing emails   Execution T1059.001 Command and Scripting Interpreter: PowerShell Use PowerShell to execute commands   Execution T1059.007 Command and Scripting Interpreter: JavaScript Use JS to execute PowerShell   Persistence T1547.001 Boot or Logon Autostart Execution: Registry Run Keys / Startup Folder Create Registry RunOnce key   Privilege Escalation T1134 Access Token Manipulation Adjust its token privileges to have the SeDebugPrivilege   Defense Evasion  T1134 Access Token Manipulation Adjust its token privileges to have the SeDebugPrivilege   Defense Evasion T1140 Deobfuscate/Decode Files or Information – Use the command certutil to decode base64 contents– Decrypt data coming from Server   Defense Evasion T1070.004 Indicator Removal on Host: File Deletion Delete its exfiltrated data to cover its tracks   Defense Evasion T1112 Modify Registry  modify the Run registry key   Defense Evasion T1027 Obfuscated Files or Information – All the strings and API calls are obfuscated using custom encryption– The dropped payload is packed with UPX   Defense Evasion T1218.010 Signed Binary Proxy Execution: Regsvr32 Load payload through Regsvr32   Credential Access T1056.001 Input Capture: Keylogging Log keystrokes on the victim’s machine   Discovery T1083 File and Directory Discovery Obtain file and directory listings   Discovery T1082 System Information Discovery Collect OS type and volume serial number   Collection T1560 Archive Collected Data Compress and encrypt collected data prior to exfiltration   Collection T1005 Data from Local System Collect data from local system   Collection T1025 Data from Removable Media Collect data from removable media   Collection T1056.001 Input Capture: Keylogging Log keystrokes on the victim’s machine   Collection T1113 Screen Capture Capture screenshots   Command and Control T1001 Data Obfuscation Encrypt data for exfiltration   Command and Control T1071.001 Application Layer Protocol: Web Protocols Use HTTP for command and control communication   Exfiltration T1041 Exfiltration Over C2 Channel Exfiltrate data over the same channel used for C2      




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








































