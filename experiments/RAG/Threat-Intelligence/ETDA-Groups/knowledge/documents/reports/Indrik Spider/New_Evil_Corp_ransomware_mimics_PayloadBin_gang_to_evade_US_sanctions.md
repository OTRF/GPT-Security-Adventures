# Reference for threat actor for "Indrik Spider"

**Title**: New Evil Corp ransomware mimics PayloadBin gang to evade US sanctions

**Source**: https://www.bleepingcomputer.com/news/security/new-evil-corp-ransomware-mimics-payloadbin-gang-to-evade-us-sanctions/

## Content






















New Evil Corp ransomware mimics PayloadBin gang to evade US sanctions

































































































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




























HomeNewsSecurityNew Evil Corp ransomware mimics PayloadBin gang to evade US sanctions







 














New Evil Corp ransomware mimics PayloadBin gang to evade US sanctions


By Lawrence Abrams


June 6, 2021
04:52 PM
0




The new PayloadBIN ransomware has been attributed to the Evil Corp cybercrime gang, rebranding to evade sanctions imposed by the US Treasury Department's Office of Foreign Assets Control (OFAC).
The Evil Corp gang, also known as Indrik Spider and the Dridex gang, started as an affiliate for the ZeuS botnet. Over time, they formed a group that focused on distributing the banking trojan and downloader called Dridex via phishing emails.
As cybergangs started to transition to highly profitable ransomware attacks, Evil Corp launched a ransomware operation called BitPaymer, which was delivered via the Dridex malware in compromised corporate networks.
After being sanctioned by the US government in 2019, ransomware negotiation firms refused to facilitate ransom payments for Evil Corp ransomware attacks to avoid facing fines or legal action from the Treasury Department.
Evil Corp began renaming their ransomware operations to different names such as WastedLocker, Hades, and Phoenix to bypass these sanctions. 
The threat actors used Phoenix in an attack on insurance firm CNA.
Evil Corp impersonates Payload Bin hacking group
After breaching the Metropolitan Police Department in Washington, DC, and stealing unencrypted data, the Babuk gang said they were quitting ransomware encryption and instead focus on data theft and extortion.
At the end of May, the Babuk data leak site had a design refresh where the ransomware gang rebranded as a new group called 'payload bin,' shown below.

Babuk Tor site turned into Payload Bin siteSource: MalwareHunterTeam
On Thursday, BleepingComputer found a new ransomware sample called PayloadBIN [VirusTotal] that we immediately assumed was related to the rebranding of Babuk Locker.
When installed, the ransomware will append the .PAYLOADBIN extension to encrypted files, as shown below.

Files encrypted by PayloadBIN
Furthermore, the ransom note is named 'PAYLOADBIN-README.txt' and states that the victim's "networks is LOCKED with PAYLOADBIN ransomware."

PayloadBIN ransom note
After finding the sample, BleepingComputer thought Babuk was lying about their intentions to move away from ransomware and rebranded to a new name.
However, after analyzing the new ransomware, both Fabian Wosar of Emsisoft and Michael Gillespie of ID Ransomware confirmed that the ransomware is a rebranding of Evil Corp's previous ransomware operations.

Looks like EvilCorp is trying to pass off as Babuk this time. As Babuk releases their PayloadBin leak portal, EvilCorp rebrands WastedLocker once again as PayloadBin in an attempt to trick victims into violating OFAC regulations. Sample: https://t.co/k669bbaNyV
— Fabian Wosar (@fwosar) June 5, 2021

WastedLocker -> Hades -> Phoenix -> PayloadBin, all same malware/group behind it. Probably a few in-between don't care to recall at the moment.
— Michael Gillespie (@demonslay335) June 5, 2021
While discussing why they would have impersonated another cybercrime group, Wosar felt that they saw and took an opportunity to impersonate a hacking group that is not sanctioned.

"Now they had a gang rebranding and just took the opportunity." - Fabian Wosar.

As the ransomware is now attributed to a sanctioned hacking group, most ransomware negotiation firms will likely not help facilitate payments for victims affected by the PayloadBIN ransomware.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBank of America warns customers of data breach after vendor hackFree Rhysida ransomware decryptor for Windows exploits RNG flaw








Babuk Locker
Dridex
Evil Corp
Hades
PayloadBIN
Ransomware
Sanctions



















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











