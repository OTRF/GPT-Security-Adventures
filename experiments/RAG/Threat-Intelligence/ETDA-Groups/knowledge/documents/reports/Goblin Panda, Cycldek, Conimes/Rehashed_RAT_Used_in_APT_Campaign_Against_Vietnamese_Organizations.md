# Reference for threat actor for "Goblin Panda, Cycldek, Conimes"

**Title**: Rehashed RAT Used in APT Campaign Against Vietnamese Organizations

**Source**: https://www.fortinet.com/blog/threat-research/rehashed-rat-used-in-apt-campaign-against-vietnamese-organizations

## Content








Rehashed RAT Used in APT Campaign Against Vietnamese Organizations










































Blog




Categories



Business & Technology 




FortiGuard Labs Threat Research




Industry Trends




Partners




Customer Stories




PSIRT Blogs






Business & Technology 




FortiGuard Labs Threat Research




Industry Trends




Partners




Customer Stories




PSIRT Blogs




CISO Collective






































FortiGuard Labs Threat Research
Rehashed RAT Used in APT Campaign Against Vietnamese Organizations





By 

Jasper Manuel and
                                          
                                           
                                      
                                  
                          

                                  
                                      
                                            
                                               Artem Semenchenko



 | September 05, 2017







Recently, FortiGuard Labs came across several malicious documents that exploit the vulnerability CVE-2012-0158. To evade suspicion from the victim, these RTF files drop decoy documents containing politically themed texts about a variety of Vietnamese government-related information. It was believed in a recent report that the hacking campaign where these documents were used was led by the Chinese hacking group 1937CN. The link to the group was found through malicious domains used as command and control servers by the attacker. In this blog, we will delve into the malware used in this campaign and will try to provide more clues as to the instigator of this campaign.

Sample decoy documents
When the documents are opened, they drop several files in one of the following folders:
 %AppData%\Microsoft\Credentials
%AppData%\Microsoft\SystemCertificates
%AppData%\Microsoft\Windows\Templates
Some samples drop the following files: 
Taskeng.exe – signed legitimate GoogleUpdate.exe version 1.3.33.5
Psisrndrx.ebd – encrypted blob containing malware file
Goopdate.dll – decrypter and loader of malware file
Some drop the following files:
SC&Cfg.exe – signed legitimate McAfee AV application
Vsodscpl.dll – contains the malware file
Others drop the following files:
Systemm.exe - signed legitimate GoogleUpdate.exe version 1.3.30.3
Systemsfb.ebd - encrypted blob containing malware file
Goopdate.dll – decrypter and loader of malware file
Similar to other APT attacks, such as MONSOON APT, this APT uses DLL hijacking to evade the behavior monitoring technologies of security programs.
DLL Hijacking
DLL hijacking is a technique used by some APT malware in which instead of the legitimate application (.exe) loading the benign DLL, the application is tricked into loading a DLL containing malicious code. This technique is employed to evade Host Intrusion Prevention System (HIPS) of security programs that monitor the behaviors of executed files. Most HIPS tools whitelist signed or trusted files, thereby excluding malware loaded using DLL hijacking by signed files from behavior monitoring.
In the context of this attack, taskeng.exe and SC&Cfg.exe are signed legitimate applications; however, they are tricked into loading malware that are disguised as the legitimate Goopdate.dll and Vsodscpl.dll files.

Taskeng.exe and SC&Cfg.exe file information
Next, Taskeng.exe needs to load and import some functions from the original Goopdate.dll file; however, the Goopdate.dll was hijacked to contain malicious code, effectively changing the original code execution to execution of the malicious code.
 

Snippet from taskenge.exe that loads goopdate.dll
In the same fashion, SC&Cfg.exe imports the “dll_wWinMain” function from the original vsodscpl.dll, but this DLL was hijacked as well, and also contains malicious code.

SC&Cfg.exe import table containing import from vsodscpl.dll
Once the malicious DLLs are loaded, the DLLs decrypt (from psisrndrx.ebd (1st case) or from its body (2nd case)) and load a Trojan downloader. The Trojan downloader is a DLL file. It is not dropped on disk but is only executed in memory. Also, the actual Trojan downloader in memory when dumped will not run. This is because the ‘MZ’ in the IMAGE_DOS_HEADER, the DOS stub, and the ‘PE’ signature were deliberately removed. This was done to prevent the dumped file from being analyzed properly in a debugger and decompiler. However, we can easily fix the dump by adding the ‘MZ’, a DOS stub, and the ‘PE’ signature.

Missing header items as anti-analysis
This Trojan downloader downloads a RAT (Remote Access Trojan), which we will call “NewCore” RAT, from the following domains:
web.thoitietvietnam.org
dalat.dulichovietnam.net
halong.dulichculao.com
Trojan Downloader
The Trojan downloader first creates an autostart registry entry so it runs whenever the machine is rebooted:
HKLM/HKCU\Software\Microsoft\Windows\CurrentVersion\Run
Microsoft Windows Media = “%AppData%\Microsoft\Credentials\.exe”
As an anti-VM, it checks whether the environment has the registry key:
HKCR\Applications\VMwareHostOpen.exe
Before it can download the NewCore RAT, it needs to send the following information to the C&C server:

OS version
Processor speed
Number of processors
Physical memory size
Computer name
User name
User privilege
Computer IP address
Volume serial number

The above information is converted to its hex string representation, and then sent to the C&C server via HTTP GET:

GET request to the C&C server
The response is an XOR encrypted data that includes the encrypted NewCore RAT.

Response from the server

XOR decryption of response from the C&C server
NewCore Remote Access Trojan
We named this RAT ‘NewCore’ after we found the project name used by the author, which is indicated on the following PDB file string:

Malware project name
According to its compilation time stamp, this malware was compiled on March 16, 2017.

Compilation time
However, as of this writing, only a few Antivirus engines, including Fortinet detect this malware according to VirusTotal.

VirusTotal positives
This RAT is a DLL file. Its malicious routines are contained in its imported function “ProcessTrans”. However, executing the DLL without using the downloader will not work as the C&C server string is not embedded in its body. When the downloader calls the function “ProcessTrans”, it supplies to the function the C&C server string and a handle to the C&C server internet session. In this case, Heuristic detection based on behavior will not work on the DLL alone.
This RAT is capable of the following:

Shutdown the machine
Restart the machine
Get disk list
Get directory list
Get file information
Get disk information
Rename files
Copy files
Delete files
Execute files
Search files
Download files
Upload files
Screen monitoring
Start command shell

 

Shutdown and restart machine commands

File manager, monitor screen, command shell commands

File manager subcommands
Based on the strings found in its body, this malware may have been derived from the PcClient and PcCortr backdoors whose source codes are publicly available, especially on Chinese language coding forums. PcClient detections usually include PcCortr.

Strings related to PcCortr modules

PcClient and PcCortr source codes can be downloaded from Chinese coding forums
PcClient was used in the past by some APT groups such as Nitro, which were also linked to a China-based hacker.
According to the PDB file string embedded in the NewCore RAT body, the creator of the project is someone using the handle “hoogle168”.

We have little clue as to who this individual is, so we tried to look for information about this handle. Our investigation led us to several Chinese language forum pages. Looking at these forums, it seems like a user using the handle “hoogle168” is very active on a certain coding forums, and is proficient in C and VC++. This user even replied to a thread and gave advice on what to learn to develop remote control software. We don’t know for sure if this person is the NewCore author.
Solution:
To prevent triggering this RTF exploit, it is important to apply the patches released by Microsoft that cover CVE-2012-0158 vulnerability.
Fortinet also covers detection for these threats as MSOffice/Dropper!exploit.CVE20120158 for the malicious RTF files, and W32/NewCore.A!tr.bdr for the payload.
C&C URLs were also blocked using Fortinet's FortiGuard Web Filtering.
Conclusion:
NewCore RAT may just be a rehashed PcClient RAT, but it proves to be effective in evading AV detection by using a combination of simple techniques such as DLL-hijacking, file-less execution of downloaded malware, and passing C&C information as parameter from downloader to the downloaded file.
As always, Fortiguard Labs will keep an eye on threats like NewCore to protect our customers against these threats.
Thank you to Tien Phan for additional insights.
 
-= FortiGuard Lion Team =-
 
IOCs:
Lure:
2a4e8ae006be3a5ed2327b6422c4c6f8f274cfa9385c4a540bc617bff6a0f060
3faacef20002f9deb1305c43ea75b8422fd29a1559c0cf01cf1cee6a1b94fc0e
5bdbf536e12c9150d15ae4af2d825ff2ec432d5147b0c3404c5d24655d9ebe52
14b4d8f787d11c7d72f66231e80997ef6ffa1d868d9d8f964bea36871e1c2ff2
637c156508949c881763c019d2dca7c912da9ec63f01e3d3ba604f31b36e52ab
5573f6ec22026b0c00945eec177f04212492bb05c33b4b80f73c65ce7fe5119a
00466938836129a634b573d2b57311200ab04aba7252cfbf6b77f435612ca6c6
c375946ba8abee48948f79a89ea5b4f823d8287c2feb3515755b22ba5bd8849d
f6a4bab7d5664d7802f1007daa04ae71e0e2b829cd06faa9b93a465546837eb4
fabf4debacb7950d403a84f4af25c084d0b576783006d334052ebf7ea432196e
 
Loader:
9cebae97a067cd7c2be50d7fd8afe5e9cf935c11914a1ab5ff59e91c1e7e5fc4
ea5b3320c5bbe2331fa3c0bd0adb3ec91f0aed97709e1b869b79f6a604ba002f
 
Trojan Downloader:
edbcc384b8ae0a2f52f239e2e599c3d2053f98cc1f4bc91548ec420bec063be6
49efab1dedc6fffe5a8f980688a5ebefce1be3d0d180d5dd035f02ce396c9966
df8475669a14a335c46c802f642dd5569c52f915093a680175c30cc9f28aacdb
 
NewCore RAT:
37bd97779e854ea2fc43486ddb831a5acfd19cf89f06823c9fd3b20134cb1c35
 
Command and Control Servers:
web.thoitietvietnam.org
dalat.dulichovietnam.net
halong.dulichculao.com
Sign up for weekly Fortinet FortiGuard Labs Threat Intelligence Briefs and stay on top of the newest emerging threats.






Tags:

exploit, 
    
      Vietnamese government, 
    
      APT Campaign, 
    
      RTF file





Related Posts







                    FortiGuard Labs Threat Research
                
Cobalt Malware Strikes Using CVE-2017-11882 RTF Vulnerability








                    FortiGuard Labs Threat Research
                
CVE-2017-11826 Exploited in the Wild with Politically Themed RTF Document








                    FortiGuard Labs Threat Research
                
FortiGuard Labs Discovers Multiple Use-After-Free Vulnerabilities in Microsoft Word




































































News & Articles


News Releases


News Articles




Security Research


Threat Research


FortiGuard Labs


Threat Map


Ransomware Prevention




Connect With Us


Fortinet Community


Partner Portal


Investor Relations


Product Certifications




Company


About Us


Exec Mgmt


Careers


Training


Events


Industry Awards


Social Responsibility


CyberGlossary


Sitemap


Blog Sitemap




Contact Us

(866) 868-3678





Copyright © 2024 Fortinet, Inc. All Rights Reserved
Terms of Services
Privacy Policy
 | Cookie Settings










