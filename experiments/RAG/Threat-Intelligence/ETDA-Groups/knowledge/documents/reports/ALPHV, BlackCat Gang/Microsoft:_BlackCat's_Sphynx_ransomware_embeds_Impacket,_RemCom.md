# Reference for threat actor for "ALPHV, BlackCat Gang"

**Title**: Microsoft: BlackCat's Sphynx ransomware embeds Impacket, RemCom

**Source**: https://www.bleepingcomputer.com/news/microsoft/microsoft-blackcats-sphynx-ransomware-embeds-impacket-remcom/

## Content






















Microsoft: BlackCat's Sphynx ransomware embeds Impacket, RemCom
































































































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




























HomeNewsMicrosoftMicrosoft: BlackCat's Sphynx ransomware embeds Impacket, RemCom







 















Microsoft: BlackCat's Sphynx ransomware embeds Impacket, RemCom


By Lawrence Abrams




August 17, 2023
06:05 PM
0





Microsoft has discovered a new version of the BlackCat ransomware that embeds the Impacket networking framework and the Remcom hacking tool, both enabling spreading laterally across a breached network.
In April, cybersecurity researcher VX-Underground tweeted about a new BlackCat/ALPHV encryptor version called Sphynx.
"We are pleased to inform you that testing of basic features ALPHV/BlackCat 2.0: Sphynx is completed," said the BlackCat operators in a message to their affiliates.
"The code, including encryption, has been completely rewritten from scratch. By default all files are frozen. The main priority of this update was to optimize detection by AV/EDR," further explained the ransomware operations.
Soon after, IBM Security X-Force performed a deep dive into the new BlackCat encryptor, warning that the encryptor evolved into a toolkit.
This was based on strings in the executable that indicated it contained impacket, used for post-exploitation functions such as remote execution and dumping secrets from processes.

Impacket strings found by IBM X-ForceSource: IBM
The BlackCat Sphynx encryptor
In a series of posts today, the Microsoft's Threat Intelligence team says they have also analyzed the new Sphynx version and found that it used the Impacket framework to spread laterally on compromised networks.
"Microsoft has observed a new version of the BlackCat ransomware being used in recent campaigns," posted Microsoft.
"This version includes the open-source communication framework tool Impacket, which threat actors use to facilitate lateral movement in target environments."
Impacket is described as an open-source collection of Python classes for working with network protocols.
However, it is more commonly used as a post-exploitation toolkit by penetration testers, red teamers, and threat actors to spread laterally on a network, dump credentials from processes, perform NTLM relay attacks, and much more.
Impacket has become very popular among threat actors who breach a device on a network and then use the framework to obtain elevated credentials and gain access to other devices.
According to Microsoft, the BlackCat operation is using the Impacket framework for credential duping and remote service execution to deploy the encryptor across an entire network.
In addition to Impacket, Microsoft says that the encryptor embeds the Remcom hacking tool, which is a small remote shell that allows the encryptor to remotely execute commands on other devices on a network.
In a private Microsoft 365 Defender Threat Analytics advisory seen by BleepingComputer, Microsoft says they saw this new encrypted used by BlackCat affiliate 'Storm-0875' since July 2023.
Microsoft is identifying this new version as BlackCat 3.0, even though, as we previously said, the ransomware operation calls it 'Sphynx' or 'BlackCat/ALPHV 2.0' in communications with affiliates.

Sample of a BlackCat ransom note
An ever-evolving ransomware gang
BlackCat, aka ALPHV, launched its operation in November 2021 and is believed to be a rebrand of the DarkSide/BlackMatter gang, which was responsible for the attack on Colonial Pipeline.
The ransomware gang has always been considered one of the most advanced and top-tier ransomware operations, constantly evolving its operation with new tactics.
For example, as a new extortion tactic last summer, the ransomware gang created a clearweb website dedicated to leaking data for a particular victim, so customers and employees could check if their data was exposed.
More recently, the threat actors created a data leak API, allowing for easier dissemination of stolen data.
With the BlackCat encryptor evolving from a decryptor to a full-fledged post-exploitation toolkit, it allows the ransomware affiliates to more quickly deploy file encryption across the network
As it is vital to detect ransomware attacks as soon as they occur, adding these tools only makes it harder for defenders.

Related Articles:
Trans-Northern Pipelines investigating ALPHV ransomware attack claimsNew RustDoor macOS malware impersonates Visual Studio updateMGM Resorts ransomware attack led to $100 million loss, data theftFidelity National Financial: Hackers stole data of 1.3 million peopleMGM casino's ESXi servers allegedly encrypted in ransomware attack











ALPHV
BlackCat
Encryptor
Impacket
Post-Exploitation
Ransomware
Remcom
Sphynx
























Lawrence Abrams   
Lawrence Abrams is the owner and Editor in Chief of BleepingComputer.com. Lawrence's area of expertise includes Windows, malware removal, and computer forensics. Lawrence Abrams is a co-author of the Winternals Defragmentation, Recovery, and Administration Field Guide and the technical editor for Rootkits for Dummies.




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











