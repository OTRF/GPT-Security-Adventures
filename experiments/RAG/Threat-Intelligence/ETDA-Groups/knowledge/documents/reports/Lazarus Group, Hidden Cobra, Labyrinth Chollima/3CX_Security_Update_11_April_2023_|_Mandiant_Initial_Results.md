# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: 3CX Security Update 11 April 2023 | Mandiant Initial Results

**Source**: https://www.3cx.com/blog/news/mandiant-initial-results/

## Content
﻿





















3CX Security Update 11 April 2023 | Mandiant Initial Results






























 





 Skip to content













    Search for:          WHICH 3CX 



PBX / PHONE SYSTEM


Free
Small Business
Enterprise

Hosted
On Premise
Self Hosted / Private Cloud

Call Center Solution
Live Chat

Need help? Find a Partner 



WHY 3CX 



SUBSTANTIAL SAVINGS



Self managed phone system 
No monthly user pricing


FREEDOM OF CHOICE


On premise |
Hosted |
Self-hosted


Bring your own trunk & numbers




REMOTE WORKING READY


World class mobile & web apps
Video Conferencing 



BOOST PRODUCTIVITY



Microsoft 365 Integration 
KYC - CRM Integrations





CONTACT CENTER



Integrated Call Center
Live Chat |
WhatsApp |
SMS





TRIED AND TESTED



Testimonials 
Global Partner Network


PRICINGTRYBLOGFORUMHELP 



GETTING STARTED



Install 3CX
Setup your team
Office hours



DESKPHONES


Configure deskphones
Supported IP Phones
Using your deskphone





VOICE CALLING


Configure SIP Trunks
Supported SIP Trunks
Call Queues & Ring Groups



MESSAGING


Setting up Live Chat
Configuring WhatsApp / Facebook
Team answering chat 





ADVANCED


Call Routing: IVR/Digital Receptionist
MS 365 Integration
MS Teams Integration



USING 3CX



The Web Client
iOS  /
Android / Windows Apps

Video conferencing 


  DE ES FR IT NL BR RUGlobal OfficesLogin LoginWHICH 3CX PBX / PHONE SYSTEMFreeSmall BusinessEnterpriseHostedOn PremiseSelf Hosted / Private CloudCall Center SolutionLive ChatNeed help? Find a PartnerWHY 3CX SUBSTANTIAL SAVINGSSelf managed phone systemNo monthly user pricingFREEDOM OF CHOICEOn premiseHostedSelf-hostedBring your own trunk & numbersREMOTE WORKING READYWorld class mobile & web appsVideo ConferencingBOOST PRODUCTIVITYMicrosoft 365 IntegrationKYC - CRM IntegrationsCONTACT CENTERIntegrated Call CenterLive ChatWhatsAppTRIED AND TESTEDTestimonialsGlobal Partner NetworkPRICINGTRYBLOGFORUMHELP GETTING STARTEDInstall 3CXSetup your teamOffice hoursDESKPHONESConfigure deskphonesSupported IP PhonesUsing your deskphoneVOICE CALLINGConfigure SIP TrunksSupported SIP TrunksCall Queues & Ring GroupsMESSAGINGSetting up Live ChatConfiguring WhatsAppConfiguring FacebookTeam answering chatADVANCEDCall Routing: IVR/Digital ReceptionistMS 365 IntegrationMS Teams IntegrationUSING 3CXThe Web ClientiOS AppAndroid AppWindows AppVideo conferencing  DE ES FR IT NL BR RUGlobal OfficesLogin Login 















PHONE SYSTEM | VIDEO | LIVE CHAT 
CONNECT YOUR TEAM & CUSTOMERS

Try it FREE





























Security Update Tuesday 11 April 2023 - Interim Assessment Concluded 

 Posted on April 11th, 2023 by Pierre Jourdan, Security Pentesting, 3CX


Initial Results from Mandiant Incident Response
Following the appointment of Mandiant as our security incident response team, forensic analysis on our network and product is in progress. In a nutshell, the interim assessment concluded:
Attribution
Based on the Mandiant investigation into the 3CX intrusion and supply chain attack thus far, they attribute the activity to a cluster named UNC4736. Mandiant assesses with high confidence that UNC4736 has a North Korean nexus.
Windows-based Malware
Mandiant determined that the attacker infected targeted 3CX systems with TAXHAUL (AKA “TxRLoader”) malware. When executed on Windows systems, TAXHAUL decrypts and executes shellcode located in a file named <machine hardware profile GUID>.TxR.0.regtrans-ms located in the directory C:\Windows\System32\config\TxR\. The attacker likely chose this file name and location to attempt to blend into standard Windows installations. The malware uses the Windows CryptUnprotectData API to decrypt the shellcode with a cryptographic key that is unique to each compromised host, which means the data can only be decrypted on the infected system. The attacker likely made this design decision to increase the cost and effort of successful analysis by security researchers and incident responders.
In this case, after decrypting and loading the shellcode contained within the file <machine hardware profile GUID>.TxR.0.regtrans-ms was a complex downloader which Mandiant named COLDCAT. It is worth noting, however, this malware differs from GOPURAM referenced in Kaspersky’s report.
The following YARA rule can be used to hunt for TAXHAUL (TxRLoader):
rule TAXHAUL
{
meta:
author = "Mandiant"
created = "04/03/2023"
modified = "04/03/2023"
version = "1.0"
strings:
$p00_0 = {410f45fe4c8d3d[4]eb??4533f64c8d3d[4]eb??4533f64c8d3d[4]eb}
$p00_1 = {4d3926488b01400f94c6ff90[4]41b9[4]eb??8bde4885c074}
condition:
uint16(0) == 0x5A4D and any of them
}
Please note that in a similar way to any YARA rule, this should be properly assessed within a test environment first before usage in production. This also comes with no guarantees regarding false positive rates, as well as coverage for this entire malware family and eventual variants.
MacOS-based Malware
Mandiant also identified a MacOS backdoor, currently named SIMPLESEA, located at /Library/Graphics/Quartz (MD5: d9d19abffc2c7dac11a16745f4aea44f). Mandiant is still analysing SIMPLESEA to determine if it overlaps with another known malware family.*
The backdoor written in C communicates via HTTP. Supported backdoor commands include shell command execution, file transfer, file execution, file management, and configuration updating. It can also be tasked to test the connectivity of a provided IP and port number.
The backdoor checks for the existence of its configuration file at /private/etc/apdl.cf. If it does not exist, it creates it with hard-coded values. The config file is single-byte XOR encoded with the key 0x5e. C2 comms are sent over HTTP requests. A bot id is generated randomly seeded with the PID of the malware upon initial execution. The id is sent with C2 communications. A brief host survey report is included in beacon requests. Message contents are encrypted with the A5 stream cipher according to the function names in the binary.
* Previous reporting mentioned the macOS build server was compromised with SIMPLESEA. Mandiant Intelligence analyzed the sample and determined it to have a high degree of code overlap with POOLRAT, deprecating SIMPLESEA in favor of POOLRAT.
Persistence
On Windows, the attacker used DLL side-loading to achieve persistence for TAXHAUL malware. DLL side-loading triggered infected systems to execute the attacker's malware within the context of legitimate Microsoft Windows binaries, reducing the likelihood of malware detection. The persistence mechanism also ensures the attacker malware is loaded at system start-up, enabling the attacker to retain remote access to the infected system over the internet.
The malware was named C:\Windows\system32\wlbsctrl.dll to mimic the legitimate Windows binary of the same name. The DLL was loaded by the legitimate Windows service IKEEXT through the legitimate Windows binary svchost.exe.
Command and Control
Mandiant identified that malware within the 3CX environment made use of the following command and control infrastructure:

azureonlinecloud[.]com
akamaicontainer[.]com
journalide[.]org
msboxonline[.]com


By Pierre Jourdan|April 11th, 2023|Comments Off on Security Update Tuesday 11 April 2023 - Interim Assessment Concluded 
 Discuss this article 



Related Posts 







 


3CX Among G2’s Best Software in 2024


February 9th, 2024







 


3CX Wins ‘Leader’ Award from SourceForge


January 18th, 2024







 


3CX’s Top Forum Contributors for Q4 2023


January 16th, 2024







 


Bringing 2023 to a Close with G2 Winter Report


December 22nd, 2023







 


3CX Holiday Season - Opening Hours


December 19th, 2023







 


Update on SQL Injection Vulnerability for SQL Server Integration


December 17th, 2023







 


Security Advisory: Disable your SQL Database Integrations


December 15th, 2023







 


Update on 4SC Free Subscriptions


December 1st, 2023




 




Product Newsletter

Subscribe to our Product News:



Subscribe

Browse Categories
Product ReleasesNewsDocs and FAQVlogEventsLatest Tech ArticlesFinal Stop to V20: Release Candidate 33CX Windows Softphone RC: Easy ProvisioningImproved Chat Control in 3CX Video ConferencingImproved Chat & Contact Filtering in Latest iOS App BetaNew Beta Update for the 3CX Android AppGet Started - Admin


Install 3CX
Setup your team
Easy SIP trunk setup
Call routing, IVR, office hours
Call queues, ring groups
Configure IP Phones
Install website Live Chat
Integrate WhatsApp & Facebook

Get Started - Users


Get to know the Web Client
Get the apps: iOS or Android
How to use your deskphone
Schedule a video call / conference
Manage Live Chat & SMS

Upcoming Webinars




 Подготовка и обновление до версии 20 


View all trainings 


Get 3CX - Absolutely Free!Link up your team and customers  Phone System  Live Chat  Video ConferencingHosted or Self-managed. Up to 10 users free forever. No credit card. Try risk free.






A 3CX Account with that email already exists. You will be redirected to the Customer Portal to sign in or reset your password if you've forgotten it.






 Sign up with Google




OR




 Sign up with email






 Please enter a valid Name.



 Please enter a valid Email Address.









 

This site is protected by reCAPTCHA and the Google
Privacy Policy and
Terms of Service apply.




 Go Back






Trusted by 350,000+ companies
The #1 Communications System!
12,000,000+ users everyday
 About 3CX Careers Awards Case Studies Contact Us Contact Center Build Voice Apps Hotel PBX Virtual PBX Small Business Phone System VoIP FAQs SIP Server Softphone 3CX as Alternative Global Sites 3CX Academy Call Reporting Free Linux PBX Free WordPress Chat Plugin Configuration GuidesSitemap Privacy




Page load link


































































3CX uses cookies to enhance your experience. By continuing to use our site, you agree to our use of cookies. OK
 


