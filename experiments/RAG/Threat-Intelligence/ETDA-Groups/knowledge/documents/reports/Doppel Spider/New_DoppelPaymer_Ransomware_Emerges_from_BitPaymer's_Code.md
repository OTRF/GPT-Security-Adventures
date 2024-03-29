# Reference for threat actor for "Doppel Spider"

**Title**: New DoppelPaymer Ransomware Emerges from BitPaymer's Code

**Source**: https://www.bleepingcomputer.com/news/security/new-doppelpaymer-ransomware-emerges-from-bitpaymers-code/

## Content






















New DoppelPaymer Ransomware Emerges from BitPaymer's Code































































































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




























HomeNewsSecurityNew DoppelPaymer Ransomware Emerges from BitPaymer's Code







 















New DoppelPaymer Ransomware Emerges from BitPaymer's Code


By Ionut Ilascu




July 15, 2019
01:36 PM
0





Malware researchers have discovered a new file-encrypting malware they dubbed DoppelPaymer that has been making victims since at least mid-June, asking hundreds of thousands of US dollars in ransom.
The ransomware strain has at least eight variants that extended their feature set gradually, with the earliest one dating since April.
Victims in the public service sector
DoppelPaymer takes its name from BitPaymer, with which it shares more than large portions of code. There are three confirmed victims of this ransomware strain, which priced its decryption keys between 2 BTC and 100 BTC, say researchers from CrowdStrike.

Bitcoin price in late April was around $5,150 and kept rising ever since, with lows well above the $7,000 mark and peaking above $12,000 in late June and early July.
One of the victims is the City of Edcouch, Texas, which was left with a ransom note demanding 8 BTC to decrypt the data on the affected computers.
It is unclear when the Edcouch administration was attacked, but city officials said that the amount converted to about $40,000. This makes it likely that the compromise happened in early May or before when bitcoin price stooped below $5,500.
Another victim was the Chilean Ministry of Agriculture, the researchers said in a report last week. The country's Computer Security Incident Response Team (CSIRT) confirmed on July 1 that a ransomware attack hit servers from a public service connected to the Ministry of Agriculture.
Parallel extortion activity
CrowdStrike researchers observed some striking similarities between DoppelPaymer's payment portal and the original one for BitPaymer. One striking hint linking the two ransomware threats is the "Bit paymer" title at the top of the page but they're similar all over.

Another clue pointing to a connection between the two pieces of malware is that they "share significant amounts of code." However, they have different encryption schemes.
Where DoppelPaymer combines 2048-bit RSA keys with 256-bit AES, the latest BitPaymer versions use 4096-bit RSA with the same specification for symmetric encryption.
Also, there is standard AES encryption padding (PKCS#7) in DoppelPaymer while BitPaymer uses random bytes specified in a field called 'TAIL.'
By analyzing differences and similarities between the two, Brett Stone-Gross, Sergei Frankoff and Bex Hartley of CrowdStrike's research and threat intel team believe that the new ransomware strain may be the work of a BitPaymer group member that started their own ransomware business.

"Both BitPaymer and DoppelPaymer continue to be operated in parallel and new victims of both ransomware families have been identified in June and July 2019. The parallel operations, coupled with the significant code overlap between BitPaymer and DoppelPaymer, indicate not only a fork of the BitPaymer code base, but an entirely separate operation." - CrowdStrike

The new ransomware includes modifications that make it superior to BitPaymer, such as threaded encryption process for a quicker operation.
The operators of BitPaymer are the same individuals behind the Dridex banking trojan, collectively known as the INDRIK SPIDER. They are former affiliates of the cybercriminal gang calling itself "The Business Club."
The group is responsible for using the GameOver Zeus botnet (disrupted in 2014), believed to have infected over one million computers, and causing damages in excess of $100 million from business and financial institutions across the world.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBank of America warns customers of data breach after vendor hackFree Rhysida ransomware decryptor for Windows exploits RNG flaw











BitPaymer
DoppelPaymer
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











