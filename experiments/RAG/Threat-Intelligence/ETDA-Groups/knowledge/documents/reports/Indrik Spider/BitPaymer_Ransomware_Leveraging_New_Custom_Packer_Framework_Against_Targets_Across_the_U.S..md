# Reference for threat actor for "Indrik Spider"

**Title**: BitPaymer Ransomware Leveraging New Custom Packer Framework Against Targets Across the U.S.

**Source**: https://blog.morphisec.com/bitpaymer-ransomware-with-new-custom-packer-framework

## Content






BitPaymer Ransomware Leveraging New Custom Packer Framework Against Targets Across the U.S.
















































































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






















BitPaymer Ransomware Leveraging New Custom Packer Framework Against Targets Across the U.S.

Posted by
Arnold Osipov on July 18, 2019

Find me on:

LinkedIn
Twitter 










Tweet
















Morphisec Labs recently investigated an ongoing BitPaymer ransomware campaign that has been attacking companies across the U.S., both public and private, over the last 3 months. We are aware of at least 15 organizations targeted by the threat group during this latest campaign, spanning multiple industries, including finance, agriculture and technology. Especially interesting is their targeting of a supply chain solution provider, which may be part of a deliberate propagation strategy.
The attacks all follow a similar pattern. Initial infiltration is usually obtained via phishing emails delivering Dridex. Once attackers have a foothold in the system, they perform a full recon stage and steal AD credentials. Then, during the weekend (usually Saturdays), they deploy the ransomware onto the already compromised network. This carefully planned timing allows them to propagate the ransomware to 24/7 running servers and then spread as the first employees returning to work from the weekend login to the compromised network.
Our investigation revealed that, in many cases, organizations had advanced EDR solutions installed in place that the ransomware was able to bypass.
Upon analysis of the ransomware and the loader that executes the payload, we identified several interesting characteristics of a new packer framework the attackers are using to obfuscate and compile a fully custom loader on the day of the attack –  usually just 2-3 hours before the ransomware’s deployment. This makes it unlikely to be detected by antivirus and EDR tools until it’s too late. The ransomware payload itself appears to be a variant compiled 3-4 months ago, which is being reused by the loader wrapper in various campaigns, including the one that knocked out Arizona Beverages earlier this year.
This BitPaymer ransomware variant also has an interesting, innovative approach to bypass Windows Defender Emulator, as shown in the Technical Analysis below. This technique was first introduced at the 2018 Black Hat conference by researcher Alexei Bulazel and we predict that more malware will start incorporating similar approaches.
Morphisec prevents the execution of the ransomware and its propagation, including the initial vectors of Dridex and the backdoors used by the attackers that lead to this compromise.
Technical Analysis
BitPaymer Loader
The loader is compiled and customized for the target and includes redundant instructions, logic and assignments. After analyzing differences between samples, we believe that a new advanced obfuscation framework has been developed by the attackers, one which is highly effective at evading behavior and static analysis.
Example of delusive function from two different BitPaymer packed samples. One of them with lots of junk code while the other is thinner. In both cases it just returns False.
Figure 1: Thinner function that returns False

Figure 2: Same functionality as the function from Figure 1, wrapped with junk code
Before executing the function that decrypts the BitPaymer second stage payload, the loader performs OS version checks. It will run on any OS later than Vista, with some exceptions, such as older versions of Windows Server (Servers are definitely the preferred target of the group).

Figure 3: Deception OS version checks
BitPaymer
Upon loading, BitPaymer checks if the file “C:\\aaa_TouchMeNot_.txt” exists. If so, BitPaymer will terminate the execution, as it is an indicator of a “goat file” in Windows Defender AV Emulator. This is an easy way to bypass Windows Defender Emulator as it always emulates the existence of the file.

Figure 4: Check if running in Windows Defender Emulator
Next, the malware initializes its configuration settings, such as process integrity level and decryption type. It also decrypts all of its strings (ransom note, public key, file extension, etc.) using the RC4 algorithm with a 40 byte key that resides in the beginning of ‘.rdata’ section.
Figure 5: Set process integrity level
Figure 6: Marked is the reversed RC4 key in .rdata section
After the Windows Defender AV Emulator check and the initialization of BitPaymer configuration, BitPaymer tries to execute itself as a service. This will be described in more detail later.
Figure 7: Unpacked BitPaymer entry point
Next, BitPaymer checks if it is running as an alternate data stream. It does that by checking if the name of the file on disk ends with ‘:’.
Figure 8: Check if running from alternate data stream
If not, it will copy itself to a hidden alternate data stream under %APPDATA%\<random_name>:BIN and create a new process with the old file path as a parameter.
The BitPaymer alternate data stream process then performs the following:

Deletes the original file
Copies itself from :BIN alternate data stream to a hidden directory in %APPDATA%\<random>.exe.
Creates a temporary ‘.cmd’ file in %temp% directory and writes the following (Figure 3)


Figure 9: cmd file that will be executed from registry
The .cmd file is not deleted and so has the registry pointing to it (described in the next section)
Elevate Privileges
In order to elevate privileges, BitPaymer uses a technique introduced by @enigma0x3, which is Fileless UAC bypass. It changes the registry key - ‘HKCR\mscfile\shell\open\command’ default value to point at the ‘.cmd’ file which will cause BitPaymer to run with high privileges without a UAC prompt. If it does not succeed in elevating its privileges, BitPaymer will exit without encrypting the filesystem.
The abuse of eventvwr.exe  and similar types of registry hijack elevation techniques are a serious architecture weakness and are very popular among malware. It is also easy to tweak the technique to bypass any existing detection solution.

Figure 10: compromised Registry key
When running with high privileges, BitPaymer deletes shadow copy files from the host. It does this by running the command ‘vssadmin.exe Delete Shadows /All /Quiet’ and ‘diskshadow.exe /s %TEMP%\<tempfile>.tmp’ (<tempfile>.tmp = "delete shadows all\r\nexit\r\n") for Windows Server versions.
Next, it tries to take ownership of a random service by using ‘takeown.exe /F <service_name>’ and ‘icacls.exe <service_name> /reset’. If it succeeds, it saves a copy of the service in ‘:0’ alternate data stream for restoration purposes. It then replaces the service with a copy of its own and executes BitPaymer as a service.
After successfully hijacking and running from a service, BitPaymer begins to encrypt the filesystem. First  it does iterates logical drivers, including network drivers, by mapping the network using the commands ‘arp.exe -a’ and respectively ‘nslookup.exe <IP>’. After gathering all applicable drivers, it recursively iterates each file in each driver. From each driver, it collects all the files that are not: ‘.exe’, ‘.dll’, ‘.<company_name>’, ‘.<company_name>_readme’.
BitPaymer adds its file extension to the encrypted files – ‘.<company_name>’, alongside a ransom note with the same file name and - ‘.<company_name>_readme’ extension.

Figure 11: Ransom note
Conclusion
The threat group behind BitPaymer has successfully hit numerous targets and shows no sign of slowing down. The Customer Packer framework it is now using allows it to create what are essentially new variants hours before the ransomware is deployed, which are extremely difficult for detection-dependent security systems to catch.
Morphisec is powered by Moving Target Defense, which blocks such attacks deterministically, without any prior knowledge or required updates.
Artifacts
NOTE: Morphisec prevented this attack immediately, without using rules, signatures or any other type of prior knowledge. The rules and hash below are provided as a service to the community and to other security solutions who do need and use prior knowledge to detect attacks.
PDB path:
Unlike old BitPaymer samples which had PDB path resemblance to Dridex samples. Some of the newer samples, which are packed with a new custom packer have - ‘RWKGGE.PDB’ pdb path.
YARA Rule:
rule BitPaymer {
meta:
description = "Rule to detect newer Bitpaymer samples. Rule is based on BitPaymer custompacker"author = "Morphisec labs" 
strings:
$opcodes1 = {B9 ?? 00 00 00 FF 14 0F B8 FF 00 00 00 C3 89 45 FC}$opcodes2 = {61 55 FF 54 B7 01 B0 FF C9 C3 CC 89 45 FC}
condition:
(uint16(0) == 0x5a4d) and ($opcodes1 or $opcodes2)
}
SHA1:
47ff3a11ca6f1c088799afaaafadcd46b89f44ac94b37a49c91f8bae7817be8892520c8e50ce62d5fea875bee31434f43bba4384cade7bba83af640466bb444ea7e54b7f6b6a1305bed3556191ceeaf2babcc902eb4fda6824a9f63fea9267e21eb256ae3752eaae8633c361a26aa763e2688ecf62c1a61fbc2b35e453a31cda3b430ff25391c66899981d2aadf3580cc8115d206ed15a881bb8144dec068b188abc0909a346553236e05f2fa8c12da7925440d084b1513647a3c15614741724e4cbec32e7b4af69195157993bffdd51e4bd2fe2ac5fcc0971033db7233aa2f1d460d9588607933b8cab1844efeff5db
















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































































