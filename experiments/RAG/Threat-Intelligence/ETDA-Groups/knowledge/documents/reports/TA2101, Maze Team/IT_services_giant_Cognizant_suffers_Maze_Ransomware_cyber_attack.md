# Reference for threat actor for "TA2101, Maze Team"

**Title**: IT services giant Cognizant suffers Maze Ransomware cyber attack

**Source**: https://www.bleepingcomputer.com/news/security/it-services-giant-cognizant-suffers-maze-ransomware-cyber-attack/

## Content






















IT services giant Cognizant suffers Maze Ransomware cyber attack































































































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




























HomeNewsSecurityIT services giant Cognizant suffers Maze Ransomware cyber attack







 














IT services giant Cognizant suffers Maze Ransomware cyber attack


By Lawrence Abrams


April 18, 2020
01:45 PM
1




Information technologies services giant Cognizant suffered a cyber attack Friday night allegedly by the operators of the Maze Ransomware, BleepingComputer has learned.
Cognizant is one of the largest IT managed services company in the world with close to 300,000 employees and over $15 billion in revenue.
As part of its operations, Cognizant remotely manages its clients through end-point clients, or agents, that are installed on customer's workstations to push out patches, software updates, and perform remote support services.
On Friday, Cognizant began emailing their clients, stating that they had been compromised and included a "preliminary list of indicators of compromise identified through our investigation." Clients could then use this information to monitor their systems and further secure them.
The listed IOCs included IP addresses of servers and file hashes for the kepstl32.dll, memes.tmp, and maze.dll files. These IP addresses and files are known to be used in previous attacks by the Maze ransomware actors.
There was also a hash for a new unnamed file, but there is no further information about it.
Security research Vitali Kremez has released a Yara rule that can be used to detect the Maze Ransomware DLL.

When we contacted the Maze operators about this attack, they deny being responsible.
In the past, Maze has been reticent to discuss attacks or victims until negotiations stall. As this attack is very recent, Maze is likely not discussing it to avoid complications in what they hope would be potential ransom payment.
After reporting on this attack, Cognizant posted a statement to their web site that confirms the cyber attack was by Maze Ransomware:

Cognizant can confirm that a security incident involving our internal systems, and causing service disruptions for some of our clients, is the result of a Maze ransomware attack.
Our internal security teams, supplemented by leading cyber defense firms, are actively taking steps to contain this incident.  Cognizant has also engaged with the appropriate law enforcement authorities.
We are in ongoing communication with our clients and have provided them with Indicators of Compromise (IOCs) and other technical information of a defensive nature. 

Threat actors were likely on the network for weeks
If the Maze operators conducted this attack, they were likely present in Cognizant's network for weeks, if not longer.
When enterprise-targeting ransomware operators breach a network, they will slowly and stealthily spread laterally throughout the system as they steal files and steal credentials.
Once the attackers gain administrator credentials on the network, they will then deploy the ransomware using tools like PowerShell Empire.
If it was Maze, it must be treated as a data breach
Before deploying ransomware, the Maze operators always steal unencrypted files before encrypting them.
These files are then used as further leverage to have the victim pay the ransom as Maze will threaten to release the data if a victim does not pay.

Chubb info on Maze news site
These are not idle threats as Maze has created a "News' site that is used to publish stolen data from non-paying victims.
If Maze was not behind the attack as they claim, there is still a good chance that data was stolen as that has become a standard tactic used by ransomware operators.
For this reason, all ransomware attacks must be treated as data breaches.
This is a developing story.

Related Articles:
Johnson Controls says ransomware attack cost $27 million, data stolenFidelity National Financial: Hackers stole data of 1.3 million peopleUS mortgage lender loanDepot confirms ransomware attackOnline museum collections down after cyberattack on service providerXerox says subsidiary XBS U.S. breached after ransomware gang leaks data








Cognizant
Cyberattack
Maze
Ransomware



















Lawrence Abrams   
Lawrence Abrams is the owner and Editor in Chief of BleepingComputer.com. Lawrence's area of expertise includes Windows, malware removal, and computer forensics. Lawrence Abrams is a co-author of the Winternals Defragmentation, Recovery, and Administration Field Guide and the technical editor for Rootkits for Dummies.



 Previous Article 
Next Article 


Comments


 




anothertester  - 3 years ago 

 
 


I don’t believe backups are sufficient anymore, definitely not when ransomware groups are stealing data before encrypting them. Backups are definitely important and the only way a business could recover from such an attack but that doesn’t stop a data breach. 





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











