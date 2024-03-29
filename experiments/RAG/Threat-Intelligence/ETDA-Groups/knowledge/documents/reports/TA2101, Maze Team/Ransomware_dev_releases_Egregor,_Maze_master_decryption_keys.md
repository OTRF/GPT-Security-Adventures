# Reference for threat actor for "TA2101, Maze Team"

**Title**: Ransomware dev releases Egregor, Maze master decryption keys

**Source**: https://www.bleepingcomputer.com/news/security/ransomware-dev-releases-egregor-maze-master-decryption-keys/

## Content






















Ransomware dev releases Egregor, Maze master decryption keys
































































































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




























HomeNewsSecurityRansomware dev releases Egregor, Maze master decryption keys







 














Ransomware dev releases Egregor, Maze master decryption keys


By Lawrence Abrams


February 9, 2022
10:26 AM
4




The master decryption keys for the Maze, Egregor, and Sekhmet ransomware operations were released last night on the BleepingComputer forums by the alleged malware developer.
The Maze ransomware began operating in May 2019 and quickly rose to fame as they were responsible for the use of data theft and double-extortion tactics now used by many ransomware operations.
After Maze announced its shutdown in October 2020, they rebranded in September as Egregor, who later disappeared after members were arrested in Ukraine.
The Sekhmet operation was somewhat of an outlier as it launched in March 2020, while Maze was still active.
Master decryption keys released
Fast forward 14 months later, and the decryption keys for these operations have now been leaked in the BleepingComputer forums by a user named 'Topleak' who claims to be the developer for all three operations.
The poster said that this was a planned leak and is not related to recent law enforcement operations that have led to the seizing of servers and the arrests of ransomware affiliates.
"Since it will raise too much clues and most of them will be false, it is necessary to emphasize that it is planned leak, and have no any connections to recent arrests and takedowns," explained the alleged ransomware developer.
They further stated that none of their team members will ever return to ransomware and that they destroyed all of the source code for their ransomware.

Forum post leaking Maze, Egregor, and Sekhmet decryption keysSource: BleepingComputer
The post includes a download link for a 7zip file with four archives containing the Maze, Egregor, and Sekhmet decryption keys, and the source code for a 'M0yv' malware used by the ransomware gang.

Archive containing the leaked decryption keysSource: BleepingComputer
Each of these archives contains the public master encryption key and the private master decryption key associated with a specific "advert", or affiliate of the ransomware operation.
In total, the following are the number of RSA-2048 master decryption keys released per ransomware operation:
Maze: 9 master decryption keys for the original malware that targeted non-corporate users.
Maze: 30 master decryption keys.
Egregor: 19 master decryption keys.
Sekhmet: 1 master decryption key.
Emsisoft's Michael Gillespie and Fabian Wosar has reviewed the decryption keys and confirmed to BleepingComputer that they are legitimate and can be used to decrypt files encrypted by the three ransomware families.
Gillespie told us that the keys are used to decrypt a victim's encrypted keys that are embedded in a ransom note.

Encrypted key in Maze ransom noteSource: BleepingComputer
Emsisoft has released a decryptor to allow any Maze, Egregor, and Sekhmet victims who have been waiting to recover their files for free.

Emsisoft decryptor for Maze, Egregor, and Sekhmet
To use the decryptor, victims will need ransom note created during the attack as it contains the encrypted decryption key.
Bonus M0yv malware source code
The archive also includes the source code for the M0yv 'modular x86/x64 file infector' developed by the Maze ransomware operation and used previously in attacks.
"Also there is a little bit harmless source code of polymorphic x86/x64 modular EPO file infector m0yv detected in the wild as Win64/Expiro virus, but it is not expiro actually, but AV engines detect it like this, so no single thing in common with gazavat," the ransomware developer said in the forum post.
"M0yv source is a bonus, because there was no any major source code of resident software for years now, so here we go," the developer later explained.
This source code come in the form of a Microsoft Visual Studio project and includes some already compiled DLLs.

Source code snippet for the M0yv malwareSource: BleepingComputer
The todo.txt file indicates the source code for this malware was last updated on January 19th, 2022.

Related Articles:
The Week in Ransomware - December 22nd 2023 - BlackCat hackedLockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBank of America warns customers of data breach after vendor hack








Decryption Key
Developer
Egregor
Maze
Ransomware
Sekhmet



















Lawrence Abrams   
Lawrence Abrams is the owner and Editor in Chief of BleepingComputer.com. Lawrence's area of expertise includes Windows, malware removal, and computer forensics. Lawrence Abrams is a co-author of the Winternals Defragmentation, Recovery, and Administration Field Guide and the technical editor for Rootkits for Dummies.



 Previous Article 
Next Article 


Comments


 




mynameisgod  - 2 years ago 

 
 


Awww bless his heart. What a kind and caring criminal he is.





 




TsVk!  - 2 years ago 

 
 


A smart criminal knows when it's time to cash in and walk away. Releasing the keys wasn't necessary, I'm glad that many will be able to get their files back now. 





 




DG1991  - 2 years ago 

 
 


I hope the guys from STOP/DJVU Ransomware gang will do the same thing in the future, *praying.





 




vnabc  - 2 years ago 

 
 


Hopefully, Phobos group would do the same soon!





Post a Comment Community Rules

You need to login in order to post a comment
Not a member yet? Register Now



You may also like:











Popular Stories






Hackers used new Windows Defender zero-day to drop DarkMe malware







Microsoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flaws










Latest Downloads




Malwarebytes Anti-Malware
Version: 4.6.8.311
5M+ Downloads




Windows Repair (All In One)
Version: 4.14.1
2M+ Downloads




McAfee Consumer Products Removal tool
Version: NA
441,649 Downloads




AdwCleaner
Version: 8.4.0.0
56M+ Downloads




Everything Desktop Search
Version: 1.4.1.1017
24,866 Downloads



























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











