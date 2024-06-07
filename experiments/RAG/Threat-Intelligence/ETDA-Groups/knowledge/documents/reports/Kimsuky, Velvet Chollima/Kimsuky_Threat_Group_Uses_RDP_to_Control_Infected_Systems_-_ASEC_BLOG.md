# Reference for threat actor for "Kimsuky, Velvet Chollima"

**Title**: Kimsuky Threat Group Uses RDP to Control Infected Systems - ASEC BLOG

**Source**: https://asec.ahnlab.com/en/57873/

## Content















Kimsuky Threat Group Uses RDP to Control Infected Systems - ASEC BLOG



































































 

Malware Information
AhnLab Detection
Statistics
Response Guide
AhnLab
 














Posted By Sanseo  , October 17, 2023 

Kimsuky Threat Group Uses RDP to Control Infected Systems 
Kimsuky, a threat group known to be supported by North Korea, has been active since 2013. At first, they attacked North Korea-related research institutes in South Korea before attacking a South Korean energy agency in 2014. Other countries have also become targets of their attack since 2017. [1] The group usually launches spear phishing attacks on the national defense, diplomatic, and academic sectors, defense and media industries, as well as national organizations. Their goal is to exfiltrate internal information and technology from the targets. [2]
After initial access, the Kimsuky threat group usually installs backdoors to control the infected systems or Infostealers to exfiltrate sensitive information within the infected systems. While open-source-based malware such as xRAT (Quasar RAT) or malware developed by the group itself are used in attacks, the group also uses legitimate tools to control the infected system.
It is a characteristic of the Kimsuky group to use these malware alongside various tools that support remote control in their attack process. The most commonly used method for remote control is Remote Desktop Protocol (RDP). In environments without RDP, the open-source tool RDP Wrapper is installed. Once RDP is installed, a user account is added for RDP access, or additional pieces of malware are used to conceal the added account and configure multiple RDP sessions. [3] [4]
Aside from RDP, there have been cases where TinyNuke (public malware) or TightVNC (open-source VNC tool) were customized and used in attacks. VNC, also known as Virtual Network Computing, is a screen-sharing system that remotely controls other computers like RDP. [5] Besides these, there are also cases where Chrome Remote Desktop, supported by the Google Chrome web browser, was used to control the infected system. [6]

Figure 1. Malware that installs Chrome Remote Desktop
In this post, we will cover the latest cases where the Kimsuky group installed BabyShark through presumed spear phishing attacks before installing various RDP-related malware strains. Tools used in the attacks have similar features to those in past cases, but from their PDB information, it is deemed that they have been created recently to be used in attacks.

Figure 2. PDB information of the injector malware
Besides these, another new malware was discovered; the name used by the threat actor upon creating the malware was “RevClient”. This malware operates by receiving commands from the threat actor through the C&C server. Depending on the command, it can add user accounts or enable the port forwarding feature.
1. Initial Access
While the initial distribution method has not been confirmed, it is presumed that spear phishing attacks would have been used. There was a history of the file “hwp.bat” being used in the infected system, like the case covered in the ASEC Blog post, “Malicious Batch File (*.bat) Disguised as a Document Viewer Being Distributed (Kimsuky)”. [7] The BAT malware checks for antivirus products using WMIC commands and additionally installs script-type malware.

Figure 3. The hwp.bat file used in attacks
After the initial infection, the threat actor continuously exfiltrated information from the infected system by changing malware and the C&C server address. Main examples of the malware that were installed include “k.ps1”, a keylogger, and the file “OneNote.vbs” which executes “k.ps1”. The file “k.ps1” saves the logged data in the file “%APPDATA%\k.log”.

Figure 4. Addresses used for uploading the exfiltrated information

Figure 5. Kimsuky group’s keylogger malware
Besides these, “pow.ps1”, a loader malware, and “desktop.r7u”, an encoded data file, were also identified. “pow.ps1” decrypts the file in the path “%APPDATA%\Microsoft\desktop.r7u” and executes it in the memory area. The decrypted file “desktop.r7u” is an injector. If the file “desktop.r3u” exists in the same path, the injector is responsible for decrypting this file and injecting it into “MSBuild.exe”, a legitimate program. While the file could not be procured, in similar attack cases in the past, a decrypted “desktop.r3u” file was xRAT, and the report by Huntress stated that KimJongRAT was used. [8]

Figure 6. The routine of decrypting and injecting desktop.r3u
2. Installing Additional Payloads
Seeing from the fact that the BabyShark C&C server address has been changed after a certain period of time, it could be seen that the threat actor continuously updated BabyShark even after its initial installation. Although information can be collected from the infected system using BabyShark alone, the threat actor additionally installed RDP-related malware afterward.
2.1. Injector
Among the installed malware, “process.exe” is almost identical to the decrypted “desktop.r7u” covered above, which is the injector. Similarities can be seen when comparing the PDB information of the two malware strains.

PDB information of the decrypted desktop.r7u: H:\Hollow\csharp process hollowing_complete_offset\csharp process hollowing_complete_offset\process\process\obj\x86\Release\process.pdb
PDB information of process.exe: G:\0726_Rev_hollowing\csharp process hollowing_complete_offset\process\process\obj\x86\Release\process.pdb

A difference is that the decryption target is the file “CustomVerification.DIC” in the %APPDATA% path and that the target process for injection is “powershell_ise.exe”. Although the file “CustomVerification.DIC” could not be identified, it is likely one of the malware that the Kimsuky group frequently uses because there are cases where xRAT was used in attacks around the same time period.
2.2. Changing the RDP Service
Aside from these, the threat actor installed a piece of malware with the name “multiple.exe”. This malware adds user accounts, enables RDP, and also supports multiple sessions. The malware first terminates the RDP service and grants permission to modify “termsrv.dll” which manages said service. Afterward, it changes the file name of “termsrv.dll” to “termsrv.pdb” and then copies the file “termsrv.dll” which already exists in the %APPDATA% path into %SystemDirectory%.

Figure 7. The routine of changing to the patched termsrv.dll to support multiple sessions
Ordinarily in Windows desktop environments, only one session is supported when connecting via RDP, unlike servers. As only one session is supported for one system, even if the user accounts are different, when the threat actor remotely connects to a system, the existing user’s session is terminated. Mimikatz and other malware of the Kimsuky group patch the memory of the currently running RDP service process to bypass this phenomenon.
However, the malware currently being used in attacks used the method of directly swapping out the legitimate “termsrv.dll” file for the patched “termsrv.dll” file. Comparing the “termsrv.dll” file that the threat actor created in advance in the %APPDATA% path with the legitimate “termsrv.dll” file shows that the CDefPolicy::Query() function has been patched.

CDefPolicy::Query() function routine of the legitimate termsrv.dll file: 39 81 3C 06 00 00 0F 84 E7 43 01 00
CDefPolicy::Query() function routine of the patched termsrv.dll file: B8 00 01 00 00 89 81 38 06 00 00 90

At this stage, an account named “IIS_USER” is created and added to the admin group to be used as the account to control the infected system. Additionally, when an account is added, it is visible when the user logs in; so, the system user can be aware of the new account. To prevent this, the malware registers the newly created “IIS_USER” to SpecialAccounts, preventing it from being visible even when the user logs in.

Figure 8. Commands to register and conceal a user account

PDB information of multiple.exe – 1: Z:\5-program\multiple\multisession_complete\multisession_complete\Release\x64\Multisession.pdb
PDB information of multiple.exe – 2: G:\0711_uac_multiple_work\multisession_complete\multisession_complete\x64\Release\Multisession.pdb

2.3. RevClient
RevClient is an RDP-related malware that runs by receiving commands from the C&C server. Depending on the command, it can perform user account-related tasks or port forwarding. The following is the configuration data of RevClient used in attacks. It can be seen that the malware version is “1.0”. Characteristically, it uses the string “ZhengReversePC” as the mutex name. The actual configuration data is included in the string “AllSettings” encrypted in Base64.

Figure 9. Configuration data of RevClient
It is possible to check other configuration data by decrypting the Base64 string. 
SettingsDataVersion“1.0”Mutex“ZhengReversePC”Host IP5.61.59[.]53Host port0MSTSC (RDP) IP127.0.0.2MSTSC (RDP) port3389Main (C&C) port2086Table 1. Configuration data of RevClient
The C&C address is made by combining the host IP address and the main port, then a connection is made. Afterward, basic information on the infected system is collected and transferred. Then, settings or commands are received as a response.

C&C address: 5.61.59[.]53:2086

ItemDataSignature string“NAT”Information about the infected systemString obtained by encrypting [User Name]@[PC Name] in Base64OS informationOS informationVersion“1.0”Host portFirst, the value is 0, then this can be received from the C&C server.Table 2. Data transferred to C&C server
The response is separated into four with “;” as the separator, and set items are used for each command. It is estimated that the first response will be the host port number, which is the fourth item, and in subsequent responses, the command number, which is the third item, will be transmitted along with additional data.
ResponseDataUser account nameUsed for adding or deleting user accounts (encrypted in Base64)User account passwordUsed for adding user accounts (encrypted in Base64)CommandCommand numberHost portPort number for port forwardingTable 3. Command structure

Figure 10. The routine of executing commands
CommandData100Start port forwarding200Delete user account300Add and conceal user account400Terminate port forwarding and initialize host port500Terminate port forwardingTable 4. List of commands
When the command “100” is transmitted, the previously received host port numbers are combined. A connection is made to the address 5.61.59[.]53:(Host Port), then this and 127.0.0.2:3389 are linked. Generally, RDP-related port forwarding tools are used to overcome the fact that threat actors cannot directly access NAT environments from the outside. Thus, a connection is first established to the threat actor’s address through the reverse connection method. Then, a connection is made to the RDP port of the infected system, relaying the two communication lines.

Figure 11. Port forwarding routine
Additionally, RevClient has the NewConcurrentRDPatcher() function implemented, which has features similar to “multiple.exe” above. The difference is that unlike “multiple.exe” which changes the previously patched “termsrv.dll” file, the NewConcurrentRDPatcher() function directly patches and modifies said file according to the Windows version. While there is no routine to execute the NewConcurrentRDPatcher() function, it is deemed that other versions of RevClient would perform this task through a command from the C&C server or in the initialization routine.

Figure 12. RevClient’s RDP patch routine
3. Conclusion
The Kimsuky threat group is continuously abusing RDP to obtain control over infected systems and exfiltrate information. RDP can also be used in the initial access process using brute force and dictionary attacks, or during lateral movement. Because RDP is one of the services that come pre-installed in Windows systems, adequate management is needed to detect or prevent such incidents.
Users must refrain from opening attachments on suspicious emails, and when installing external software, it is recommended to purchase or download them from their official websites. Additionally, users must set complex passwords for their accounts and change them periodically.
Also, V3 must be updated to the latest version to block malware infection in advance. In addition to endpoint security products (V3), sandbox-based APT solutions such as MDS must be implemented to prevent harm from cyberattacks.
AhnLab MDS sandbox detects the malware that patches RDP and activates multiple sessions under the detection name “Execution/MDP.Command.M10645”.

Figure 13. Malware detected by AhnLab MDS

Figure 14. Changes to file ownership detected
File Detection– Trojan/Win.Agent.C5502241 (2023.10.08.03)– Trojan/Win.Injector.C5502245 (2023.10.08.03)– Backdoor/Win.RevClient.R609964 (2023.10.08.03)– Trojan/Win.Agent.R5502241 (2023.10.08.03)– Backdoor/PowerShell.XRatLoader.SC192386 (2023.09.13.00)– Trojan/VBS.KeylogLoader.SC192383 (2023.09.13.00)– Keylogger/PowerShell.Agent (2023.09.13.00)– Data/BIN.Encoded (2023.09.13.00)
Behavior Detection– Execution/MDP.Command.M10645
AMSI Detection– Trojan/Win.Injector.C5485760
IOCMD5– ad9a3e893abdac7549a7d66ca32142e8 : Keylogger 런쳐 – BabyShark (OneNote.vbs)– 116a71365b83cc38211ccfc8059b363e : Keylogger – BabyShark (k.ps1)– c8d589ac5c872b12e502ec1fc2fee0c7 : Loader – BabyShark (pow.ps1)– 0d6717c3fa713c5f5f5cb0539b94b84f : Injector – BabyShark (desktop.r7u)– 0d691673af913dc0942e55548f6e2e4e : Injector (process.exe)– 2dbe8e89310b42e295bfdf3aad955ba9 : RDP Pacher (multiple.exe)– 7313dc4d9d6228e442fc6ef9ba5a1b9a : RDP Pacher (multiple.exe)– be2f73a637258aa872bdf548daf55336 : RevClient (RevClient.exe)– 02804d632675b2a3711e19ef217a2877 : RevClient (RevClient_x86.exe)
C&C– hxxps://onessearth[.]online/up/upload_dotm.php : BabyShark– hxxps://powsecme[.]co/up/upload_dotm.php : BabyShark– 5.61.59[.]53:2086 : RevClient
AhnLab MDS detects and responds to unknown threats by performing sandbox-based dynamic analysis. For more information about the product, please visit our official website.

 

Categories:AhnLab Detection 
Tagged as:Kimsuky,RDP,RevClient 




Lazarus Group’s Operation Dream Magic 

Where Has the MS Office Document Malware Gone? 







5
1
vote
Article Rating

 





 Subscribe




 Login 




Notify of 


new follow-up comments
new replies to my comments








 







 


Label












{}
[+]

 















Name*





Email





Website






[Important] Consent to Collection and Use of Personal Information


Purpose: Identify the contact information of user who left a comment and respond to inquiries on our blog posts.
Personal Information We Collect: Name of user and organization, Email address
Period of Retention: We store personal information for 3 months. Then, we delete and destroy personal information without delay.

 



I agree to AhnLab’s collection and use of personal information.




















Δ 










 


Label












{}
[+]

 















Name*





Email





Website






[Important] Consent to Collection and Use of Personal Information


Purpose: Identify the contact information of user who left a comment and respond to inquiries on our blog posts.
Personal Information We Collect: Name of user and organization, Email address
Period of Retention: We store personal information for 3 months. Then, we delete and destroy personal information without delay.

 



I agree to AhnLab’s collection and use of personal information.




















Δ 






18 Comments                    









 Inline Feedbacks                    
View all comments











Kimsuky Threat Group Uses RDP to Control Infected Systems - Ciberdefensa



    3 months ago













[…] post Kimsuky Threat Group Uses RDP to Control Infected Systems appeared first on ASEC […]






0






Reply













Kimsuky: Their Use of RDP in Controlling Systems - Invaders



    3 months ago













[…] systems, extracting sensitive information, and acquiring advanced technologies. Our colleagues at Ahnlab have shed light on the latest developments in Kimsuky’s tactics, which we will explore in […]






0






Reply













North Korea's Kimsuky Doubles Down on Remote Desktop Control - n-cryptech



    3 months ago













[…] to an environment if RDP is not present, researchers from South Korea’s AhnLab revealed in a blog post Oct. […]






0






Reply













North Korea's Kimsuky Doubles Down on Distant Desktop Management - artificialintelligence360



    3 months ago













[…] to an surroundings if RDP isn’t current, researchers from South Korea’s AhnLab revealed in a weblog submit Oct. […]






0






Reply













North Korea's Kimsuky Doubles Down on Remote Desktop Control - IT LinesIT Lines



    3 months ago













[…] to an environment if RDP is not present, researchers from South Korea’s AhnLab revealed in a blog post Oct. […]






0






Reply













North Korea’s Kimsuky Doubles Down on Remote Desktop Control - Kilguard | News, Reviews, & AI



    3 months ago













[…] to an surroundings if RDP is not current, researchers from South Korea’s AhnLab uncovered in a blog post Oct. […]






0






Reply













North Korea’s Kimsuky Doubles Down on Remote Desktop Control – Cyber Social Hub



    3 months ago













[…] to an environment if RDP is not present, researchers from South Korea’s AhnLab revealed in a blog post Oct. […]






0






Reply













North Korea's Kimsuky Doubles Down on Distant Desktop Management - Sale & Buy Vehicles



    3 months ago













[…] to an setting if RDP isn’t current, researchers from South Korea’s AhnLab revealed in a weblog publish Oct. […]






0






Reply













North Korea’s Kimsuky Doubles Down on Remote Desktop Control – Cerebral LY InfoSec



    3 months ago













[…] to an environment if RDP is not present, researchers from South Korea’s AhnLab revealed in a blog post Oct. […]






0






Reply













Microsoft Warns of North Korean Assaults Exploiting JetBrains TeamCity Flaw - superpcparts.com



    3 months ago













[…] an extra signal of North Korea’s evolving offensive applications, ASEC has attributed one other menace actor generally known as Kimsuky (aka APT43) to a contemporary set of […]






0






Reply













Kimsuky Threat Group Uses RDP to Control Infected Systems - Net Tech, Inc.



    3 months ago













[…] Click here for the full alert. […]






0






Reply













Microsoft Warns of North Korean Attacks Exploiting JetBrains TeamCity Flaw – Cloud Karamchari



    3 months ago













[…] a further sign of North Korea’s evolving offensive programs, ASEC has attributed another threat actor known as Kimsuky (aka APT43) to a fresh set of spear-phishing attacks that […]






0






Reply













North Korea's Kimsuky Doubles Down on Distant Desktop Management - superpcparts.com



    3 months ago













[…] to an setting if RDP is just not current, researchers from South Korea’s AhnLab revealed in a weblog put up Oct. […]






0






Reply













North Korea’s Kimsuky Doubles Down on Remote Desktop Control – CyberSigna



    3 months ago













[…] to an environment if RDP is not present, researchers from South Korea’s AhnLab revealed in a blog post Oct. […]






0






Reply













North Korea's Kimsuky Doubles Down on Distant Desktop Management #Imaginations Hub - Imaginations Hub



    3 months ago













[…] to an surroundings if RDP will not be current, researchers from South Korea’s AhnLab revealed in a weblog publish Oct. […]






0






Reply













Eagle Eye 437 – Eagle Eye Intelligence



    3 months ago













[…] NORTH KOREA: Kimusky Threat Actors Likely to Increase Attacks on Foreign Targets […]






0






Reply













Microsoft Warns of North Korean Attacks Exploiting JetBrains TeamCity Flaw



    3 months ago













[…] a further sign of North Korea’s evolving offensive programs, ASEC has attributed another threat actor known as Kimsuky (aka APT43) to a fresh set of spear-phishing attacks that […]






0






Reply













Threat Actors Installing Linux Backdoor Accounts - ASEC BLOG



    13 days ago













[…] For example, while the Kimsuky threat group uses RATs to control the infected system when attacking Windows systems, it also uses RDP to remotely control the target system in a GUI environment. Accordingly, the Kimsuky threat group installs RDP Wrapper or activates the RDP service in the infected system, then patches the RDP service afterward to allow multiple RDP sessions. Then it adds and conceals a new account so that the account can be used to control the target system thereon [1]. […]






0






Reply




 













Archives Archives

Select Month
 February 2024 
 January 2024 
 December 2023 
 November 2023 
 October 2023 
 September 2023 
 August 2023 
 July 2023 
 June 2023 
 May 2023 
 April 2023 
 March 2023 
 February 2023 
 January 2023 
 December 2022 
 November 2022 
 October 2022 
 September 2022 
 August 2022 
 July 2022 
 June 2022 
 May 2022 
 April 2022 
 March 2022 
 February 2022 
 January 2022 
 December 2021 
 November 2021 
 October 2021 
 September 2021 
 August 2021 
 July 2021 
 June 2021 
 May 2021 
 April 2021 
 March 2021 
 February 2021 
 January 2021 
 December 2020 
 November 2020 
 September 2020 
 August 2020 
 July 2020 
 June 2020 
 May 2020 
 April 2020 
 March 2020 
 February 2020 
 December 2019 
 November 2019 
 October 2019 
 September 2019 
 August 2019 
 June 2019 
 May 2019 
 April 2019 
 March 2019 
 February 2019 
 January 2019 
 November 2018 
 July 2018 
 April 2018 
 February 2018 


FOLLOW US


LinkedIn   


X   


RSS Feed   









footer(en) 220, Pangyoyeok-ro, Bundang-gu, Seongnam-si, Gyeonggi-do, Korea | Privacy & Security© AhnLab, Inc. All rights reserved.family site


한국 (한국어)
Global (English)
日本 (日本語)
 




wpDiscuzInsert 









 




















































































Loading Comments...



 


Write a Comment...




Email



Name



Website
















































































































































































































































