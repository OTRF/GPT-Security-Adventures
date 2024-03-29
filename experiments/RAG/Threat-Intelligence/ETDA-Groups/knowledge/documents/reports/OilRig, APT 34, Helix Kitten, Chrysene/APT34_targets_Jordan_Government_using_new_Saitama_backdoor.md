# Reference for threat actor for "OilRig, APT 34, Helix Kitten, Chrysene"

**Title**: APT34 targets Jordan Government using new Saitama backdoor

**Source**: https://blog.malwarebytes.com/threat-intelligence/2022/05/apt34-targets-jordan-government-using-new-saitama-backdoor/

## Content











APT34 targets Jordan Government using new Saitama backdoor








































 




 








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

































 


News
						 | 						Threat Intelligence

APT34 targets Jordan Government using new Saitama backdoor 
Posted: May 10, 2022
 by Threat Intelligence Team 


On April 26th, we identified a suspicious email that targeted a government official from Jordan’s foreign ministry. The email contained a malicious Excel document that drops a new backdoor named Saitama. Following our investigation, we were able to attribute this attack to the known Iranian Actor APT34. Also known as OilRig/COBALT GYPSY/IRN2/HELIX KITTEN, APT34 is an Iranian threat group that has targeted Middle Eastern countries and victims worldwide since at least 2014. The group is known to focus on the financial, governmental, energy, chemical, and telecommunication sectors. In this blog post, we describe the attack flow and share details about the Saitama backdoor. Malicious email file The malicious email was sent to the victim via a Microsoft Outlook account with the subject “Confirmation Receive Document” with an Excel file called “Confirmation Receive Document.xls”. The sender pretends to be a person from the Government of Jordan by using its coat of arms as a signature.  Excel document The Excel attachment contains a macro that performs malicious activities. The document has an image that tries to convince the victim to enable a macro.  After enabling the macro, the image is replaced with the Jordan government’s the coat of the arms:  The macro has been executed on WorkBook_Open(). Here are the main functionalities of this macro:   Hides the current sheet and shows the new sheet that contains the coat of arms image. Calls the “eNotif’ function which is used to send a notification of each steps of macro execution to its server using the DNS protocol. To send a notification it builds the server domain for that step that contains the following parts: “qw” + identification of the step (in this step “zbabz”) + random number + domain name (joexpediagroup.com)=qwzbabz7055.joexpediagroup.com. Then it uses the following WMI query to get the IP address of the request: Select * From Win32_PingStatus Where Address='” & p_sHostName & “‘” which performs the DNS communication the the created subdomain. Creates a TaskService object and Gets the task folder that contains the list of the current tasks Calls ENotif function Checks if there is a mouse connected to PC and if that is the case performs the following steps  Creates %APPDATA%/MicrosoftUpdatedirectory Creates “Update.exe”, “Update.exe.config” and “Microsoft.Exchange.WenServices.dll” Reads the content of the UserForm1.label1, UserForm2.label1 and UserForm3.label1 that are in base64 format, decodes them and finally writes them into the created files in the previous step Calls a ENotif function for each writes function   Checks the existence of theUpdate.exefile and if for some reason it has not been written to disk, it writes it using a technique that loads a DotNet assembly directly using mscorlib and Assembly.Load by manually accessing the VTable of the IUnknown. This technique was taken from Github (link). Even though, this technique was not used in this macro since the file was already written, the function name (“Test”) suggests that the threat actor is trying to implement this technique in future attacks. Finally, it calls the ENotif function.    Defines a xml schema for a scheduled task and registers it using the RegisterTask function. The name of the scheduled task is MicrosoftUpdate and is used to make update.exepersistent.   Saitama Backdoor – A finite state machine The dropped payload is a small backdoor that is written in .Net. It has the following interesting pdb path: E:SaitamaSaitama.AgentobjReleaseSaitama.Agent.pdb. Saitama backdoor abuses the DNS protocol for its command and control communications. This is stealthier than other communication methods, such as HTTP. Also, the actor cleverly uses techniques such as compression and long random sleep times. They employed these tricks to disguise malicious traffic in between legitimate traffic.  Another element that we found interesting about this backdoor is the way that it is implemented. The whole flow of the program is defined explicitly as a finite-state machine, as shown in the Figure 7. In short, the machine will change its state depending on the command sent to every state. Graphically, the program flow can be seen as this:  The finite-machine state can be: BEGIN It is the initial state of the machine. It just accepts the start command that puts the machine into the ALIVE state. ALIVE This state fetches the C&C server, expecting to receive a command from the attackers. These servers are generated by using the PRNG algorithm that involves transformations like the Mersenne Twister. These transformations will generate subdomains of the hard coded domains in the Config class (Figure 8).  Figure 9 shows an example of the generated subdomain:  This state has two possible next stages. If the performed DNS request fails, the next stage is SLEEP. Otherwise, the next stage is RECEIVE. SLEEP and SECOND SLEEP These states put the backdoor in sleep mode. The amount of time that the program will sleep is determined by the previous stage. It is clear that one of the main motivations of the actor is to be as stealthy as possible. For example, unsuccessful DNS requests puts the backdoor in sleep mode for a time between 6 and 8 hours! There are different sleep times depending on the situations (values are expressed in milliseconds):  There is also a “Second Sleep” state that puts the program on sleep mode a different amount of time. RECEIVE This state is used to receiving commands from the C&C servers. Commands are sent using the IP address field that is returned by the DNS requests. Further details about the communication protocol are provided later in this report. In a nutshell, every DNS request is capable of receiving 4 bytes. The backdoor will concatenate responses, building buffers in that way. These buffers will contain the commands that the backdoor will execute. DO (DoTask) That state will execute commands received from the server. The backdoor has capabilities like executing remote pre-established commands, custom commands or dropping files. The communication supports compression, also. The following figure shows the list of possible commands that can be executed by the backdoor.     ID Type Command     1 PS Get-NetIPAddress -AddressFamily IPv4 | Select-Object IPAddress   2 PS Get-NetNeighbor -AddressFamily IPv4 | Select-Object “IPADDress”   3 CMD whoami   4 PS [System.Environment]::OSVersion.VersionString   5 CMD net user   6 — ———[NOT USED]———   7 PS Get-ChildItem -Path “C:Program Files” | Select-Object Name   8 PS Get-ChildItem -Path ‘C:Program Files (x86)’ | Select-Object Name   9 PS Get-ChildItem -Path ‘C:’ | Select-Object Name   10 CMD hostname   11 PS Get-NetTCPConnection | Where-Object{$_.State -eq “Established”} | Select-Object “LocalAddress”, “LocalPort”, “RemoteAddress”, “RemotePort”   12 PS $(ping -n 1 10.65.4.50 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.4.51 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.65.65 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.53.53 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.21.200 | findstr /i ttl) -eq $null   13 PS nslookup ise-posture.mofagov.gover.local | findstr /i Address;nslookup webmail.gov.jo | findstr /i Address   14 PS $(ping -n 1 10.10.21.201 | findstr /i ttl) -eq $null;$(ping -n 1 10.10.19.201 | findstr /i ttl) -eq $null;$(ping -n 1 10.10.19.202 | findstr /i ttl) -eq $null;$(ping -n 1 10.10.24.200 | findstr /i ttl) -eq $null   15 PS $(ping -n 1 10.10.10.4 | findstr /i ttl) -eq $null;$(ping -n 1 10.10.50.10 | findstr /i ttl) -eq $null;$(ping -n 1 10.10.22.50 | findstr /i ttl) -eq $null;$(ping -n 1 10.10.45.19 | findstr /i ttl) -eq $null   16 PS $(ping -n 1 10.65.51.11 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.6.1 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.52.200 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.6.3 | findstr /i ttl) -eq $null   17 PS $(ping -n 1 10.65.45.18 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.28.41 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.36.13 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.51.10 | findstr /i ttl) -eq $null   18 PS $(ping -n 1 10.10.22.42 | findstr /i ttl) -eq $null;$(ping -n 1 10.10.23.200 | findstr /i ttl) -eq $null;$(ping -n 1 10.10.45.19 | findstr /i ttl) -eq $null;$(ping -n 1 10.10.19.50 | findstr /i ttl) -eq $null   19 PS $(ping -n 1 10.65.45.3 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.4.52 | findstr /i ttl) -eq $null;$(ping -n 1 10.65.31.155 | findstr /i ttl) -eq $null;$(ping -n 1 ise-posture.mofagov.gover.local | findstr /i ttl) -eq $null   20 PS Get-NetIPConfiguration | Foreach IPv4DefaultGateway | Select-Object NextHop   21 PS Get-DnsClientServerAddress -AddressFamily IPv4 | Select-Object SERVERAddresses   22 CMD systeminfo | findstr /i “Domain”    Figure 12: List of predefined commands  It is pretty shocking to see that even when attackers have the possibility of sending any command, they choose to add that predefined list in the backdoor in Base64 format. As we can see, some of them are common reconnaissance snippets, but some of them are not that common. In fact, some of the commands contain internal IPsand also internal domain names(like ise-posture.mofagov.gover.local). That shows that this malware was clearly targeted and also indicates that the actor has some previous knowledge about the internal infrastructure of the victim. SEND – SEND AND RECEIVE The Send state is used to send the results generated by commands to the actor’s server. In this case, the name of the subdomain will contain the data. As domain names are used to exfiltrate unknown amounts of data, attackers had to split this data in different buffers. Every buffer is then sent through a different DNS request. As it can be seen in the Figure 12, all the required information in order to reconstruct original data is sent to the attackers. The size of the buffer is only sent in the first packet.  Attribution There are several indicators that suggest that this campaign has been operated by APT34.  Maldoc similarity: The madoc used in this campaign shared some similarities with maldocs used in previous campaigns of this actor. More specifically similar to what was mentioned in CheckPoint’s reportthis maldoc registers a scheduled task that would launch the executable every X minutes, also it uses the same anti sandboxing technique (checking if there is a mouse connected to the PC or not). Finally, we see a similar pattern to beacon back to the attacker server and inform the attacker about the current stage of execution. Victims similarity: The group is known to target the government of Jordan and this is the case in this campaign. Payload similarity: DNS is the most common method used byAPT34 for its C&C communications. The group is also known to use uncommon encodings such as Base32 and Base36 in its previous campaigns. The Saitama backdoor uses a similar Base32 encoding for sending data to the servers that is used by DNSpionage. Also, to build subdomains it uses Base32 encoding that is similar to what was reported by Mandiant.   Malwarebytes customers are protected from this attack via our Anti-Exploit layer.  IOCs Maldoc:Confirmation Receive Document.xls26884f872f4fae13da21fa2a24c24e963ee1eb66da47e270246d6d9dc7204c2b Saitama backdoor:update.exee0872958b8d3824089e5e1cfab03d9d98d22b9bcb294463818d721380075a52dC2s:uber-asia.comasiaworldremit.com joexpediagroup.com




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








































