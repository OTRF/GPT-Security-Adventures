# Reference for threat actor for "Pinchy Spider, Gold Southfield"

**Title**: Threat Profile: GandCrab Ransomware

**Source**: https://blog.morphisec.com/threat-profile-gandcrab-ransomware

## Content






Threat Profile: GandCrab Ransomware
















































































ON-DEMAND WEBINAR: Morphisec's Top 10 Security Predictions - Outlook into 2024























Support
Partners
Contact Us













Products

Product Overview
Morphisec for Windows Endpoints
Morphisec for Windows Servers & Workloads
Morphisec for Linux Server Protection
Morphisec Vulnerability Visibility & Prioritization
Incident Response Services
About Moving Target Defense

Solutions

By Industry

Finance
Hedge Funds
Healthcare
Technology
Manufacturing
Legal
K-12 Education
SMB

By Use Case

Microsoft Defender AV
Microsoft Defender for Endpoint
Virtual Desktop Protection
Cloud Workload Protection
Remote Employee Security
Ransomware Prevention
Virtual Patching and Compliance
Supply Chain Attack Protection
Browser Attack Protection


Company

About Us
News & Events
Careers

Resources

Blog
Learning Center
Customer Stories 




































Products

Products
Product Overview
Morphisec for Windows Endpoints
Morphisec for Windows Servers & Workloads
Morphisec for Linux Server Protection
Morphisec Vulnerability Visibility & Prioritization
Incident Response Services
About Moving Target Defense

Solutions

Solutions
By Industry

Finance
Hedge Funds
Healthcare
Technology
Manufacturing
Legal
K-12 Education
SMB

By Use Case

Microsoft Defender AV
Microsoft Defender for Endpoint
Virtual Desktop Protection
Cloud Workload Protection
Remote Employee Security
Ransomware Prevention
Virtual Patching and Compliance
Supply Chain Attack Protection
Browser Attack Protection


Company

Company
About Us
News & Events
Careers

Resources

Resources
Learning Center
Customer Stories 

Blog
Support
Partners
Contact Us



































Cybersecurity Blog
Cybersecurity News, Threat Research, and more from the Team Spearheading the Evolution of Endpoint Security






















Threat Profile: GandCrab Ransomware

Posted by
Roy Moshailov on February 23, 2018

Find me on:

Twitter 










Tweet
















GandCrab Ransomware
Here is a look at GandCrab ransomware and some techniques it uses to evade detection and analysis. These days, most malware employs long-chain attack and anti-analysis techniques to make it more difficult to detect the payload and harder to analyze by security researchers. Such is the case with GandCrab, a new ransomware strain that entered the scene late last month and is currently active.
Organizations with Morphisec as a memory defense layer were protected from GandCrab from the moment it emerged.
GandCrab is being distributed as Ransomware-as-a-service by a Russian cybercrime group through a profit-sharing “partner program.” Interestingly, according to Australian firm LMNTRIX Labs, the “partner program” prohibits the targeting of Russia and countries in the Commonwealth of Independent States including Azerbaijan, Armenia, Belarus, Kazakhstan, Kyrgyzstan, Moldova, Tajikistan, Turkmenistan, Uzbekistan, and Ukraine. GandCrab malware is delivered primarily via the RIG and GrandSoft exploit kit. Other distribution mechanisms include the EiTest Hoefler Text Pop-up campaign (compromised websites), and a Necurs botnet-powered malspam campaign.
Gandcrab ransomware is backed by a custom packer and uses multiple techniques to make it difficult for security researchers to analyze. Packer-based malware is malware that is modified in the runtime memory using various sophisticated compression techniques. It is an easy method for hackers to create new signatures for the same malware on the fly, simply by changing the encryption/packing method.
How Does Grandcrab Work?
RIG exploit kit leading to GandCrab ransomware:
Image credit: Malwarebytes Lab
 EiTest campaign leading to GandCrab ransomware via Hoefler Text Pop-up:
Image credit: Broad Analysis
The GandCrab Sample and Packing Technique
The GandCrab ransomware sample is a packed Windows executable. GandCrab is not identified as packed by standard tools, i.e., it uses a custom packer (for more about custom packers, see this analysis of another custom packer). We start by noticing an interesting, relatively high entropy in one of the sections (e.g. entropy of .rsrc is 7.79), which gives us the first indication that it is a packer.
As shown in the image below, GlobalAlloc and VirutalProctect API are used to allocate memory and then modify the protection to RWE (read write execute) access rights. These are some of the indicators for the unpacked executable shellcode (the code will write and execute from the same location).

As part of the evasive techniques, GandCrab malware iterates over the PEB to find useful functions (locate GetProcAddress and LoadLibrary), build the IAT (Import Address Table), and jump to the unpacked sample:

Find Kernel32.dll and then get the GetProcAddress and LoadLibrary from EAT(Export Address Table):

Build IAT (VirtualAlloc,VirtualProtect,VirtualFree,GerVersionExA,TerminateProcess):

Allocation of the new memory region:

Copy the Image:
 
Use VirtualProtect to change the protection of the Imagebase and then map new sections and build the IAT for unpacked PE (while zeroing the original memory):

It is worthwhile to examine and analyze the new mapped executable Import functions:
(CrypteImportkey, CryptGenKey, ShellExecuteW, Process32FirstW, OpenProcess, CreateMutexW, RegCreatekeyExW)

Jump to unpacked PE – Now we can dump the unpacked sample and analyze it:
 
 
The unpacked GandCrab uses several techniques designed to avoid detection, including identifying tools used by analysts or sandbox environments (read more on this unpacked sample):

Queries information about victim OS user. For example, keyboard type, computer name, presence of security solutions, localname, processor type, IP, OS version, disk space, system language, active drives, current Windows version, and processor architecture (validates that the keyboard layout is not Russian).




Create a mutex with some system info



Check against a set of running security solutions processes
 Kill list of hardcoded process (to free up handles for files that will be encrypted)

 

 If it does not find the C2 server, it does not continue to the main encryption function

GandCrab malware uses the standard Microsoft crypto API from Advapi32.dll. It calls CryptGenKey with the RSA algorithm. 
 
The encrypted files use .GDCB as the file extension. Additionally, victims receive a GDCB-DECRYPT.txt file which serves as the ransom note.
 
Surprisingly, the developers are asking for DASH cryptocurrency (lesser-known but more anonymous than Bitcoin) for a decryption key and to get back the original files.
The “customer” support service is similar to Spora ransomware in that it provides a public communication to all its victims, with a 24/7 support chat service.
How Does Morphisec Protect You from GandCrab?
Morphisec stops GandCrab ransomware across its attack chain, both during the exploit delivery stage (exploit kits), and the ransomware payload stage (if downloaded directly).  Morphisec customers are and have always been protected from GandCrab out of the box, no updates needed, back to the very first production version of Morphisec Endpoint Threat Prevention released 2 years ago and it was always useful each and every time.
Resources

http://www.broadanalysis.com/2018/02/06/eitest-campaign-hoefler-text-pop-up-delivers-gandcrab-ransomware-and-fake-av-alert/ 
https://blog.malwarebytes.com/threat-analysis/2018/01/gandcrab-ransomware-distributed-by-rig-and-grandsoft-exploit-kits/ 

Hashes: 

3c60a9af0f5538f3bca64a1df5c604a6d194495d8d5a66bcd1a4f09b84015ebb (EITest campaign payload, Executable file)
69f55139df165bea1fcada0b0174d01240bc40bc21aac4b42992f2e0a0c2ea1d (Seamless-campaign Rig EK payload, Executable file)
496a5f41e206b552c93690926d6678b2f2550fe14db8dbdc42e6532353735c13(Flash exploit, SWF file)
6a19146eb0ae8a352b166454f69bf95b4152f43b9692b4c014f9258f43be8d02(Flash exploit, SWF file)

 
 















Subscribe to our blog
Stay in the loop with industry insight, cyber security trends, and cyber attack information and company updates.






























Search Our Site





























Recent Posts














Posts by Tag



Moving Target Defense (127)


Cyber Security News (123)


Morphisec Labs (111)


Threat Research (60)


Threat Post (59)


Morphisec News (52)


Automated Moving Target Defense (8)


Defense-in-Depth (6)


in-memory attacks (6)


Gartner (4)


runtime attacks (4)


Legacy security (3)


Linux cyber security (3)


advanced threat defense (3)


threat and vulnerability management (3)


ChatGPT (2)


Gartner endpoint protection (2)


Ransomware (2)


financial cybersecurity (2)


patch management (2)


Anti-tampering (1)


Evasive loader (1)


Fileless malware (1)


Gartner Emerging Tech (1)


Healthcare cybersecurity (1)


IoT security (1)


Securing IoT devices (1)


Server security (1)


See all



























Products

Product Overview
Morphisec for Windows Endpoints
Morphisec for Windows Servers & Workloads
Morphisec for Linux Server Protection
Morphisec Vulnerability Visibility & Prioritization
Incident Response Services
About Moving Target Defense

Solutions By Industry

Banking & Finance
Hedge Funds
Healthcare
Technology
Manufacturing
Legal
K-12 Education
SMB

Solutions by Use Case

Microsoft Defender for Endpoint
Microsoft Defender AV
Virtual Desktop Protection
Ransomware Protection
Supply Chain Attack Protection
Cloud Workload Protection
Remote Employee Security
Virtual Patching & Compliance
Browser Attack Protection







Company

About Us
News & Events
Careers

Blog
Support
Partners
Contact Us
Privacy & Legal
Contact Sales
Inquire via Azure














© 2023 Morphisec Ltd. | All rights reserved































































