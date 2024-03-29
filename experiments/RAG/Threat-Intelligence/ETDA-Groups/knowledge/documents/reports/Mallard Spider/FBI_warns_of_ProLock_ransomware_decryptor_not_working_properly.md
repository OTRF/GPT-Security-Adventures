# Reference for threat actor for "Mallard Spider"

**Title**: FBI warns of ProLock ransomware decryptor not working properly

**Source**: https://www.bleepingcomputer.com/news/security/fbi-warns-of-prolock-ransomware-decryptor-not-working-properly/

## Content






















FBI warns of ProLock ransomware decryptor not working properly































































































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




























HomeNewsSecurityFBI warns of ProLock ransomware decryptor not working properly







 














FBI warns of ProLock ransomware decryptor not working properly


By Ionut Ilascu


May 18, 2020
03:36 AM
1




Multiple actors in the ransomware business saw the new coronavirus pandemic as the perfect opportunity to focus on an already overburdened healthcare sector. ProLock is yet another threat to the list.
The FBI‌ issued a flash alert at the beginning of the month to alert organizations of the new threat actor, saying that its targets in the US include entities in the following sectors: healthcare, government, financial, and retail.
Decryptor malfunction
The FBI does not encourage giving in to the demands of any ransomware actor. Doing so would only increase their confidence to continue such attacks.
With ProLock, the decryptor is not working properly and data will be lost. Files larger than 64MB may become corrupted during the decryption process.
Integrity loss of 1 byte per 1KB is possible with files over 100MB and additional work may be needed to make the decryptor work properly. This issue will increase the downtime of an organization even they agree to the actor's demands.
The malware started as PwndLocker in late 2019 but made a reputation by targeting businesses and local governments, adjusting its ransom demands to the size of the compromised network.
After fixing a bug that allowed free decryption, PwndLocker emerged as ProLocker in March and its activity started to escalate.
Getting in the network
As cybersecurity company Group-IB‌ points out in a recent report, ProLock has partnered with QakBot banking trojan to obtain access to victims’ networks; this likely contributed to this ransomware's ascension.
The trojan does not install this ransomware family but runs a set of scripts to let its operators on the victim network so they can map it and move laterally. The payload is extracted from a BMP or JPG file named WinMgr, and is loaded into memory.

source: Group-IB
Like other ransomware operators, ProLock’s spend some time on the victim network looking for high-value systems and important data to steal. The information is siphoned out using the Rclone a command-line tool for syncing with various cloud storage services.
The ransom demand following the encryption comes with the threat that victim data would be released on public websites and social media unless payment for decryption is not received.
Other methods include misconfigured remote desktop protocol (RDP). For networks with single-factor authentication, the actor uses stolen logins.
Once inside, ProLock operators make sure that they leave no option for recovering the files without paying. If backups and volume shadow copies are found, they are either deleted or encrypted.

source: Group-IB
With ransom demands between $175,000 to over $660,000, ProLock is as serious a threat as other, more infamous ransomware families like Maze, Sodinokibi, Ryuk, or LockerGoga, which are considered top earners in the ransomware business.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBank of America warns customers of data breach after vendor hackFree Rhysida ransomware decryptor for Windows exploits RNG flaw








ProLock
Ransomware



















Ionut Ilascu   
Ionut Ilascu is a technology writer with a focus on all things cybersecurity. The topics he writes about include malware, vulnerabilities, exploits and security defenses, as well as research and innovation in information security. His work has been published by Bitdefender, Netgear, The Security Ledger and Softpedia.



 Previous Article 
Next Article 


Comments


 




Demonslay335  - 3 years ago 

 
 


Emsisoft offers a custom decryptor for businesses who have received a tool from the criminals that fixes the bug. It is a bug with their decryptor, *not* the malware, so files *are* recoverable as long as you have not run their tool on them (which deletes the encrypted files). We discovered this bug quite awhile ago.





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











