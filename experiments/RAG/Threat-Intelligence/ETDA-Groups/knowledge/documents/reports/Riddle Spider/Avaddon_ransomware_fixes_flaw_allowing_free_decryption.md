# Reference for threat actor for "Riddle Spider"

**Title**: Avaddon ransomware fixes flaw allowing free decryption

**Source**: https://www.bleepingcomputer.com/news/security/avaddon-ransomware-fixes-flaw-allowing-free-decryption/

## Content






















Avaddon ransomware fixes flaw allowing free decryption
































































































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




























HomeNewsSecurityAvaddon ransomware fixes flaw allowing free decryption







 














Avaddon ransomware fixes flaw allowing free decryption


By Lawrence Abrams


February 11, 2021
06:30 PM
3




The Avaddon ransomware gang has fixed a bug that let victims recover their files without paying the ransom. The flaw came to light after a security researcher exploited it to create a decryptor.
On Tuesday, Javier Yuste, a Ph.D. student at Rey Juan Carlos University, published a decryptor for the Avaddon Ransomware on his GitHub page and released a report describing the flaw through ArXiv.
According to Yuste's research, when the Avaddon ransomware encrypts a device, it creates a unique AES256 encryption session key used to encrypt and decrypt the files.
A flaw in how the ransomware clears this key, though, allowed Yuste to create a decryptor that retrieves the key from memory as long as the computer has not been shut down since being encrypted.
Ransomware dev fixes encryption flaw
As first reported by ZDnet, one day after the decryptor was released, the Avaddon ransomware developer posted to a hacker forum that they had fixed the flaw.
"Only neither the decryptor, nor such close atention will stop us. On the contrary, we analyzed the situation, identified weaknesses and found a solution."
"We have already implemented a solution to the problem that will make decryption by third-party means impossible," the Avaddon developer wrote in a forum post.

Post by the ransomware dev on a hacker forum
To compensate the operation's affiliates whose victims may have received free decryption, the ransomware developer increased affiliates' revenue share to 80%. The normal revenue share for Avaddon affiliates is 65-75%, depending on how many victims they generate.
Threat actors read the same security news as you
It is important to remember that ransomware and threat actors follow the same Twitter and news feeds that you do.
In the past, ransomware operations such as GandCrab and Maze routinely taunted antivirus companies, researchers, and even BleepingComputer after news or research was published.
One threat actor went as far as creating a ransomware called 'Fabiansomware' after the ransomware expert Fabian Wosar.

Fabiansomeware Ransomware
BleepingComputer has also been contacted numerous times by threat actors who wanted to clarify a point in an article or tell us further information.
Thus, it is always essential to assume that any ransomware flaws openly disclosed will also be seen by a threat actor.
We have seen this historically with CryptoDefense, DarkSide, and now Avaddon.
For this reason, most ransomware experts do not think security companies and researchers should publish encryption flaws or decryptors as it allows the threat actors to fix the bugs in their malware.
Instead, it is suggested that those who create a decryptor reach out to antivirus companies, incident response firms, law enforcement, and communities like BleepingComputer who commonly help ransomware victims.
These decryptors can then be used by these organizations to privately help victims, while at the same time not publicly revealing to the ransomware developers how to fix their flaws.

Related Articles:
New Black Basta decryptor exploits ransomware flaw to recover filesFree Rhysida ransomware decryptor for Windows exploits RNG flawOnline ransomware decryptor helps recover partially encrypted filesKasseika ransomware uses antivirus driver to kill other antivirusesDecryptor for Babuk ransomware variant released after hacker arrested








Avaddon
Decryptor
Encryption
Flaw
Ransomware



















Lawrence Abrams   
Lawrence Abrams is the owner and Editor in Chief of BleepingComputer.com. Lawrence's area of expertise includes Windows, malware removal, and computer forensics. Lawrence Abrams is a co-author of the Winternals Defragmentation, Recovery, and Administration Field Guide and the technical editor for Rootkits for Dummies.



 Previous Article 
Next Article 


Comments


 




dogsofhellfire2600  - 3 years ago 

 
 


Your recommendation about using communities like BC and other entities to privately help these victims is a good idea. I wonder how well it would work, knowing that many of the victims are not willing to disclose this kind of breach. Good idea !!





 




Lawrence Abrams  - 3 years ago 

 
 


We have been doing this exact process at BC for a very long time. Works well.
We do not ask for company names to help them.





 




doriel  - 3 years ago 

 
 


Thanks for the article. Seems like ransomware vendors suufer from "unpatched security flaws" too :) imagine that! patch for ransomware!
"Please install this patch for your ransomware to improve your overall experience. we fixed following issues: "
:) :)





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











