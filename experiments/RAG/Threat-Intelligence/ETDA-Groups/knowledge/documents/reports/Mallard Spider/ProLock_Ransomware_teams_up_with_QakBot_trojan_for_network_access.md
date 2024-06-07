# Reference for threat actor for "Mallard Spider"

**Title**: ProLock Ransomware teams up with QakBot trojan for network access

**Source**: https://www.bleepingcomputer.com/news/security/prolock-ransomware-teams-up-with-qakbot-trojan-for-network-access/

## Content






















ProLock Ransomware teams up with QakBot trojan for network access































































































News



Featured
Latest







Microsoft: New critical Exchange bug exploited as zero-day





LockBit claims ransomware attack on Fulton County, Georgia





Trans-Northern Pipelines investigating ALPHV ransomware attack claims





Microsoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flaws









Three critical application security flaws scanners can’t detect





Turla hackers backdoor NGOs with new TinyTurla-NG malware





New Qbot malware variant uses fake Adobe installer popup for evasion





Take an extra $5 off this ad-blocking DNS for Presidents' Day








Tutorials



Latest
Popular







How to enable Kernel-mode Hardware-enforced Stack Protection in Windows 11





How to use the Windows Registry Editor





How to backup and restore the Windows Registry





How to open a Windows 11 Command Prompt as Administrator









How to start Windows in Safe Mode





How to remove a Trojan, Virus, Worm, or other Malware





How to show hidden files in Windows 7





How to see hidden files in Windows








Virus Removal Guides



Latest
Most Viewed
Ransomware







Remove the Theonlinesearch.com Search Redirect





Remove the Smartwebfinder.com Search Redirect





How to remove the PBlock+ adware browser extension





Remove the Toksearches.xyz Search Redirect









Remove Security Tool and SecurityTool (Uninstall Guide)





How to Remove WinFixer / Virtumonde / Msevents / Trojan.vundo





How to remove Antivirus 2009 (Uninstall Instructions)





How to remove Google Redirects or the TDSS, TDL3, or Alureon rootkit using TDSSKiller









Locky Ransomware Information, Help Guide, and FAQ





CryptoLocker Ransomware Information Guide and FAQ





CryptorBit and HowDecrypt Information Guide and FAQ





CryptoDefense and How_Decrypt Ransomware Information Guide and FAQ








Downloads



Latest
Most Downloaded







Qualys BrowserCheck





STOPDecrypter





AuroraDecrypter





FilesLockerDecrypter









AdwCleaner





ComboFix





RKill





Junkware Removal Tool








Deals



Categories







eLearning





IT Certification Courses





Gear + Gadgets





Security








VPNs



Popular







Best VPNs





How to change IP address





Access the dark web safely





Best VPN for YouTube








Forums
More

Startup Database
Uninstall Database
Glossary
Chat on Discord
Send us a Tip!
Welcome Guide




























HomeNewsSecurityProLock Ransomware teams up with QakBot trojan for network access







 















ProLock Ransomware teams up with QakBot trojan for network access


By Ionut Ilascu




May 14, 2020
12:02 PM
0





ProLock is a relatively new malware on the ransomware  scene but has quickly attracted attention by targeting businesses and local governments and demanding huge ransoms for file decryption.
Its most recent victim is Diebold Nixdorf, mostly known for providing automated teller machines (ATMs).
This attack was caught before the encryption stage and did not impact these systems; it did cause some disruptions as it affected the corporate network.
Average prices
This ransomware family started as PwndLocker but it was rebranded to ProLocker in March after the developers fixed a bug that allowed free decryption of the files.
According to research conducted by BleepingComputer, ProLock demands ransoms ranging between $175,000 to over $660,000 depending on the size of the network.
However, the skills and techniques seen with ProLock operators are similar to those of high-profile ransomware groups such as Sodinokibi and Maze, BleepingComputer learned from Oleg Skulkin, Senior Digital Forensics Analyst at Group-IB. a Singapore-based cybersecurity company.
Victims breached via QakBot and RDP
The researcher says that these groups may intersect through third-party individuals providing operational support (distribution, initial breach, lateral movement).
Skulkin presented in a report today ProLock’s tactics, techniques, and procedures (TTP), in the hope of better understanding and defending against this threat actor.
To breach victims, ProLock relies on two main vectors: distribution via QakBot (QBot) - previously affiliated with MegaCortex ransomware, and access via public-facing remote desktop (RDP) servers.

“Access via public-facing RDP-server is a very common technique used by many ransomware operators. Commonly this kind of access is bought from the third party, but may be obtained by some of group members as well” - Oleg Skulkin

Similar to how Ryuk works with TrickBot and DoppelPaymer/BitPaymer work with Dridex for access to networks, ProLock is working with QakBot to gain access.
QakBot is a banking trojan that spreads via phishing campaigns that deliver malicious Microsoft Word documents, usually to businesses. Emotet botnet was seen distributing this malware.
The researcher points out that both QakBot and ProLock rely on PowerShell to get the payload running. For the banking malware, malicious macros are employed for the task, while for the ransomware the code is extracted from a JPG or BMP image file.

image with ProLock binary
If ProLock operators use RDP access to reach their victim, persistence is established using valid accounts. With QakBot, multiple methods are used but popular ones rely on Run keys and scheduled tasks.
According to data from Group-IB, it takes about a week before QakBot makes room for ProLock. Skulkin told us that the trojan does not install the ransomware but downloads batch scripts from cloud storage repositories and executes them.
Lateral movement and file exfiltration
Lateral movement activity begins after the operators obtain credentials to some servers. Usually, RDP access for reconnaissance is enabled through the scripts, which are executed with PsExec.
The ransomware is later deployed using the command line interface for Windows Management Instrumentation (WMI).
Aligning to the current trend, ProLock operators steal data from a compromised network. The files are archived with 7-zip and uploaded to various cloud storage spaces (OneDrive, Google Drive, Mega) using Rclone, a command line program that syncs data with an impressive number of cloud storage services.
After exfiltration, the operators execute a PowerShell script to extract the ProLock binary embedded in an image file and unleash it across the enterprise network to encrypt data on reachable systems.
Each encrypted file has the ransomware mark (extensions .proLock, .pr0Lock, .proL0ck, .key, or .pwnd) and recovery instructions are provided in a text file dropped in every folder.

Skulkin says that ProLock does not have a “leak site” at the moment, although this may change in the near future.
Group-IB's report is available here and includes MITRE ATT&CK (Adversarial Tactics, Techniques & Common Knowledge) knowledge.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBank of America warns customers of data breach after vendor hackFree Rhysida ransomware decryptor for Windows exploits RNG flaw











ProLock
Ransomware
























Ionut Ilascu   
Ionut Ilascu is a technology writer with a focus on all things cybersecurity. The topics he writes about include malware, vulnerabilities, exploits and security defenses, as well as research and innovation in information security. His work has been published by Bitdefender, Netgear, The Security Ledger and Softpedia.




 Previous Article 
Next Article 



Post a Comment Community Rules

You need to login in order to post a comment

Not a member yet? Register Now



You may also like:













Popular Stories






Hackers used new Windows Defender zero-day to drop DarkMe malware







Microsoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flaws

































Follow us:









Main Sections

News
VPN Buyer Guides
Downloads
Virus Removal Guides
Tutorials
Startup Database
Uninstall Database
Glossary



Community

Forums
Forum Rules
Chat



Useful Resources

Welcome Guide
Sitemap



Company

About BleepingComputer
Contact Us
Send us a Tip!
Advertising
Write for BleepingComputer
Social & Feeds
Changelog








Terms of Use -  Privacy Policy - Ethics Statement - Affiliate Disclosure


Copyright @ 2003 - 2024  Bleeping Computer® LLC  - All Rights Reserved












Login


Username



Password





Remember Me



Sign in anonymously





 Sign in with Twitter

Not a member yet? Register Now
















  
Reporter

Help us understand the problem. What is going on with this comment?




Spam


Abusive or Harmful


Inappropriate content


Strong language


Other





Read our posting guidelinese to learn what content is prohibited.



Submitting...
SUBMIT











