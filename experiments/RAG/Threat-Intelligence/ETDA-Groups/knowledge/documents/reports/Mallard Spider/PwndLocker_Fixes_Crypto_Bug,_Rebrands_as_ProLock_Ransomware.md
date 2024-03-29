# Reference for threat actor for "Mallard Spider"

**Title**: PwndLocker Fixes Crypto Bug, Rebrands as ProLock Ransomware

**Source**: https://www.bleepingcomputer.com/news/security/pwndlocker-fixes-crypto-bug-rebrands-as-prolock-ransomware/

## Content






















PwndLocker Fixes Crypto Bug, Rebrands as ProLock Ransomware































































































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




























HomeNewsSecurityPwndLocker Fixes Crypto Bug, Rebrands as ProLock Ransomware







 














PwndLocker Fixes Crypto Bug, Rebrands as ProLock Ransomware


By Lawrence Abrams


March 20, 2020
05:01 PM
0




PwndLocker has rebranded as the ProLock Ransomware after fixing a crypto bug that allowed a free decryptor to be created.
At the beginning of March, we reported on a new ransomware called PwndLocker that was targeting enterprise networks and demanding ransoms ranging between $175,000 to over $660,000 depending on the size of the network. 
Soon after, Michael Gillespie of ID Ransomware and Fabian Wosar of Emsisoft were able to discover a weakness in the ransomware that allowed them to create a free decryptor for victims to get their files back without paying the ransom.
Rebranded as ProLock Ransomware
After their initial failure, the developers rebranded their infection as ProLock Ransomware and have started to target corporate networks once again.
According to Sophos researcher PeterM, the new ProLock Ransomware is being distributed through a BMP image file being stored in C:\ProgramData named WinMgr.bmp. Embedded in this image is the ransomware executable.
This BMP file renders properly in an image viewer, as shown below, with only a few dots appearing in the upper right corner.

WinMgr.bmp
If you view it through a hex editor, though, you can see that it includes binary data embedded in it as well.

Hex Edit of WinMgr.bmp
This binary data is then reassembled by a PowerShell script that injects it directly into memory

PowerShell Script
Peter stated that this attack has been seen against a few servers, but it is not quite known how they got access. It is suspected that the attackers gained access through exposed Remote Desktop services.
"They targeted a handful of servers. Not sure how they got in (yet) but I can see quite a few keygens and cracking tools on the network, probably just end up being an exposed RDP though :-)," Peter stated in a Tweet.
As the attackers have full access to the network, it is unsure why they are hiding the ransomware executable in a BMP image file.
It is most likely being done to evade detection by security software as it deployed throughout the network using tools like PowerShell Empire or PSExec.
ProLock encryption method
Otherwise, a ProLock encryption attack will be the same as the methods used by PwndLocker.
When launched it will clear the shadow volume copies on the machine so that they cannot be used to recover files

vssadmin.exe delete shadows /all /quiet
vssadmin.exe resize shadowstorage /for=D: /on=D: /maxsize=401MB
vssadmin.exe resize shadowstorage /for=D: /on=D: /maxsize=unbounded

It will then start encrypting files on the computer, while skipping any with the following extensions and files in operating system and common application folders.

.exe, .dll, .lnk, .ico, .ini, .msi, .chm, .sys, .hlf, .lng, .inf, .ttf, .cmd, .bat, .vhd, .bac, .bak, .wbc, .bkf, .set, .win, .dsk
When encrypting files it will append the extension .proLock to an encrypted file's name. For example. 1.doc will be encrypted and named 1.doc.proLock.

ProLock encrypted files
In each folder that has been scanned for files, ProLock will create a ransom note named [HOW TO RECOVER FILES].TXT that contain instructions on how to connect to a Tor for payment information.

ProLock Ransom Note
As each ProLock ransomware executable is hard coded with a ransom amount assigned to a particular victim, from the sample we analyzed the ransom amounts continue to be high. This one was for 80 bitcoins or approximately $470,000.

ProLock Ransomware Tor Payment Site
Unfortunately, with this release the ransomware operators fixed their encryption flaw that made free decryption possible.
Victims will need to recover from backups instead or rebuild their files.
IOCS
Hashes:

WinMgr.bmp: a6ded68af5a6e5cc8c1adee029347ec72da3b10a439d98f79f4b15801abd7af0

Associated Files:

[HOW TO RECOVER FILES].TXT
C:\Programdata\WinMgr.xml
C:\Programdata\WinMgr.bmp
C:\Programdata\clean.bat
C:\Programdata\run.bat

ProLock Ransom Note:

Your files have been encrypted by ProLock Ransomware using RSA-2048 algorithm.

   [.:Nothing personal just business:.]

No one can help you to restore files without our special decryption tool.

To get your files back you have to pay the decryption fee in BTC.
The final price depends on how fast you write to us.

   1. Download TOR browser: https://www.torproject.org/
   2. Install the TOR Browser.
   3. Open the TOR Browser.
   4. Open our website in the TOR browser: msaoyrayohnp32tcgwcanhjouetb5k54aekgnwg7dcvtgtecpumrxpqd.onion
   5. Login using your ID xxx

   ***If you have any problems connecting or using TOR network:
   contact our support by email chec1kyourf1les@protonmail.com.

   [You'll receive instructions and price inside]

The decryption keys will be stored for 1 month.

We also have gathered your sensitive data.
We would share it in case you refuse to pay.

Decryption using third party software is impossible.
Attempts to self-decrypting files will result in the loss of your data.
 







ProLock
PwndLocker
Ransomware
Steganography



















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











