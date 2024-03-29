# Reference for threat actor for "ALPHV, BlackCat Gang"

**Title**: BlackCat ransomware hits Azure Storage with Sphynx encryptor

**Source**: https://www.bleepingcomputer.com/news/security/blackcat-ransomware-hits-azure-storage-with-sphynx-encryptor/

## Content






















BlackCat ransomware hits Azure Storage with Sphynx encryptor
































































































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




























HomeNewsSecurityBlackCat ransomware hits Azure Storage with Sphynx encryptor







 















BlackCat ransomware hits Azure Storage with Sphynx encryptor


By Sergiu Gatlan




September 16, 2023
10:11 AM
0





Image: Midjourney
The BlackCat (ALPHV) ransomware gang now uses stolen Microsoft accounts and the recently spotted Sphynx encryptor to encrypt targets' Azure cloud storage.
While investigating a recent breach, Sophos X-Ops incident responders discovered that the attackers used a new Sphynx variant with added support for using custom credentials. 
After gaining access to the Sophos Central account using a stolen One-Time Password (OTP), they disabled Tamper Protection and modified the security policies. These actions were possible after stealing the OTP from the victim's LastPass vault using the LastPass Chrome extension.
Subsequently, they encrypted the Sophos customer's systems and remote Azure cloud storage and appended the .zk09cvt extension to all locked files. In total, the ransomware operators could encrypt 39 Azure Storage accounts successfully.
They infiltrated the victim's Azure portal using a stolen Azure key that provided them access to the targeted storage accounts. The keys used in the attack were injected within the ransomware binary after being encoded using Base64.
The attackers also used multiple Remote Monitoring and Management (RMM) tools like AnyDesk, Splashtop, and Atera throughout the intrusion. 
Sophos discovered the Sphynx variant in March 2023 during an investigation into a data breach that shared similarities with another attack described in an IBM-Xforce report published in May (the ExMatter tool was used to extract the stolen data in both instances).
Microsoft also found last month that the new Sphynx encryptor is embedding the Remcom hacking tool and the Impacket networking framework for lateral movement across compromised networks.

BlackCat ransom note sample
​As a ransomware operation that emerged in November 2021, BlackCat/ALPHV is suspected to be a DarkSide/BlackMatter rebrand.
Known initially as DarkSide, this group garnered global attention after breaching Colonial Pipeline, drawing immediate scrutiny from international law enforcement agencies.
Although they rebranded as BlackMatter in July 2021, operations were abruptly halted in November when authorities seized their servers and security firm Emsisoft developed a decryption tool exploiting a vulnerability in the ransomware.
This gang has consistently been recognized as one of the most sophisticated and high-profile ransomware outfits that targets enterprises on a global scale, continuously adapting and refining its tactics.
For instance, in a new extortion approach last summer, the ransomware gang used a dedicated clear web website to leak the stolen data of a specific victim, providing the victim's customers and employees with the means to determine whether their data had been exposed.
More recently, BlackCat introduced a data leak API in July designed to streamline the dissemination of stolen data.
This week, one of the gang's affiliates gang (tracked as Scattered Spider) claimed the attack on MGM Resorts, saying they encrypted over 100 ESXi hypervisors after the company took down its internal infrastructure and refused to negotiate a ransom payment. 
Last April, the FBI issued a warning highlighting that the group was behind the successful breaches of more than 60 entities worldwide between November 2021 and March 2022.

Related Articles:
Trans-Northern Pipelines investigating ALPHV ransomware attack claimsNew RustDoor macOS malware impersonates Visual Studio updateMGM Resorts ransomware attack led to $100 million loss, data theftFidelity National Financial: Hackers stole data of 1.3 million peopleMGM casino's ESXi servers allegedly encrypted in ransomware attack











ALPHV
Azure
Azure Storage
BlackCat
Ransomware
Sphynx
























Sergiu Gatlan   
Sergiu is a news reporter who has covered the latest cybersecurity and technology developments for over a decade. Email or Twitter DMs for tips.




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











