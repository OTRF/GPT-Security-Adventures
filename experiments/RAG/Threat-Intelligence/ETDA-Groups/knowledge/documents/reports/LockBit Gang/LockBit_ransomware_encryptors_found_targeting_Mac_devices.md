# Reference for threat actor for "LockBit Gang"

**Title**: LockBit ransomware encryptors found targeting Mac devices

**Source**: https://www.bleepingcomputer.com/news/security/lockbit-ransomware-encryptors-found-targeting-mac-devices/

## Content






















LockBit ransomware encryptors found targeting Mac devices
































































































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




























HomeNewsSecurityLockBit ransomware encryptors found targeting Mac devices







 














LockBit ransomware encryptors found targeting Mac devices


By Lawrence Abrams


April 16, 2023
01:31 PM
7




Image: Norebbo
The LockBit ransomware gang has created encryptors targeting Macs for the first time, likely becoming the first major ransomware operation to ever specifically target macOS.
The new ransomware encryptors were discovered by cybersecurity researcher MalwareHunterTeam who found a ZIP archive on VirusTotal that contained what appears to be most of the available LockBit encryptors.
Historically, the LockBit operation uses encryptors designed for attacks on Windows, Linux, and VMware ESXi servers. However, as shown below, this archive [VirusTotal] also contained previously unknown encryptors for macOS, ARM, FreeBSD, MIPS, and SPARC CPUs.

Archive of available LockBit encryptorsSource: BleepingComputer
These encryptors also include one named 'locker_Apple_M1_64' [VirusTotal] that targets the newer Macs running on Apple Silicon. The archive also contains lockers for PowerPC CPUs, which older Macs use.
Further research by cybersecurity researcher Florian Roth found an Apple M1 encryptor uploaded to VirusTotal in December 2022, indicating that these samples have been floating around for some time.
Likely test builds
BleepingComputer analyzed the strings in the LockBit encryptor for Apple M1 and found strings that are out of place in a macOS encryptor, indicating that these were likely haphazardly thrown together in a test.
For example, there are numerous references to VMware ESXi, which is out of place in an Apple M1 encryptor, as VMare announced they would not be supporting the CPU architecture.

_check_esxi
esxi_
_Esxi
_kill_esxi_1
_kill_esxi_2
_kill_esxi_3
_kill_processes
_kill_processes_Esxi
_killed_force_vm_id
_listvms
_esxcfg_scsidevs1
_esxcfg_scsidevs2
_esxcfg_scsidevs3
_esxi_disable
_esxi_enable

Furthermore, the encryptor contains a list of sixty-five file extensions and filenames that will be excluded from encryption, all of them being Windows file extensions and folders.
A small snippet of the Windows files the Apple M1 encryptor will not encrypt is listed below, all out of place on a macOS device.

.exe
.bat
.dll
msstyles
gadget
winmd
ntldr
ntuser.dat.log
bootsect.bak
autorun.inf
thumbs.db
iconcache.db
Almost all of the ESXi and Windows strings are also present in the MIPs and FreeBSD encryptors, indicating that they use a shared codebase.
The good news is that these encryptors are likely not ready for deployment in actual attacks against macOS devices.
Cisco Talos researcher Azim Khodjibaev told BleepingComputer that based on their research, the encryptors were meant as a test and were never intended for deployment in live cyberattacks.
macOS cybersecurity expert Patrick Wardle further confirmed BleepingComputer's and Cisco's theory that these are in-development/test builds, stating that the encryptor is far from complete as it is missing the required functionality to encrypt Macs properly.
Instead, Wardle told BleepingComputer that he believes the macOS encryptor is based on the Linux version and compiled for macOS with some basic configuration settings.
Furthermore, Wardle told us that when the macOS encryptor is launched, it crashes due to a buffer overflow bug in its code.

"It seems that macOS is now on their radar ... but other than compiling it for macOS, and adding a basic config (which are just basic flags ...not specific to macOS per se) this is far from ready for deployment," Wardle told BleepingComputer.
Wardle further shared that the LockBit developer must first "figure out how to bypass TCC, get notarized" before becoming a functional encryptor.
A detailed technical analysis conducted by Wardle on the new Mac encryptor can be found on Objective See.
While Windows has been the most targeted operating system in ransomware attacks, nothing prevents developers from creating ransomware that targets Macs.
However, as the LockBit operation is known for pushing the envelope in ransomware development, it would not be surprising to see more advanced and optimized encryptors for these CPU architectures released in the future.
Therefore, all computer users, including Mac owners, should practice good online safety habits, including keeping the operating system updated, avoiding opening unknown attachments and executables, generate offline backups, and using strong and unique passwords at every site you visit.
Update 4/16/23: In response to questions from BleepingComputer, the public-facing representative of LockBit, known as LockBitSupp, said that the Mac encryptor is "actively being developed."
While LockBit has a history of toying with security researchers and the media, if true, we will likely see more production-quality versions in the future.
Furthermore, while it's not clear how useful a macOS encryptor would be in the enterprise, some LockBit affiliates target consumers and small businesses, where an encryptor like this could be more useful.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaBank of America warns customers of data breach after vendor hackNew RustDoor macOS malware impersonates Visual Studio updateThe Week in Ransomware - February 2nd 2024 - No honor among thievesCISA warns of patched iPhone kernel bug now exploited in attacks








Apple
Apple M1
Encryptor
LockBit
macOS
PowerPC
Ransomware



















Lawrence Abrams   
Lawrence Abrams is the owner and Editor in Chief of BleepingComputer.com. Lawrence's area of expertise includes Windows, malware removal, and computer forensics. Lawrence Abrams is a co-author of the Winternals Defragmentation, Recovery, and Administration Field Guide and the technical editor for Rootkits for Dummies.



 Previous Article 
Next Article 


Comments


 




Mjaggard  - 9 months ago 

 
 


Clearly a good idea but how are strong and unique passwords going to help against a ransomware attack? A reliable backup is what you need.





 




Lawrence Abrams  - 9 months ago 

 
 


Using employees credentials are a common vector used to gain access to corporate networks.
Every little bit of good cyber practices helps, including not using weak passwords and different ones for each account.
Added offline backup recommendation. Thx.





 




TimMcP  - 9 months ago 

 
 


Say you sign up to some web site, and use your corporate email address to register, and also use your corporate password, so you don't have to remember two, if there's no 2FA on your webmail, and those creds get breached, you've given away access to your email. If you picked a unique password for that new site, you haven't. 





 




BrechtMo  - 9 months ago 

 
 


"Furthermore, while it's not clear how useful a macOS encryptor would be in the enterprise, some LockBit affiliates target consumers and small businesses, where an encryptor like this could be more useful."
I'm not sure what this means. Do you mean a MacOs installation in an enterprise managed environment would be less vulnerable somehow?





 




Lawrence Abrams  - 9 months ago 

 
 


No, just that macOS is not as widely used in the enterprise compared to Windows servers and workstations.





 




TimMcP  - 9 months ago 

 
 


Indeed, we got rid of our last few Macs last year. Out of ~5000 devices we had about 5 Macs, because someone convinced someone they could so something a PC couldn't back in the day.





 




h_b_s  - 9 months ago 

 
 


Macs are more likely to be a personal device around corporate environments, especially with executives and technical support. There is a high(er) percentage of Macs in universities in the US that may be either personal/student owned or university property, however. Universities tend to be very mixed environments. You'll find Microsoft, Apple, IBM in both mainframe and POWER systems, and various Linux systems that may or may not be PCs in nearly any given university. Administration is usually Microsoft with IBM mainframe support depending on the uni.





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











