# Reference for threat actor for "Pinchy Spider, Gold Southfield"

**Title**: REvil ransomware now changes password to auto-login in Safe Mode

**Source**: https://www.bleepingcomputer.com/news/security/revil-ransomware-now-changes-password-to-auto-login-in-safe-mode/

## Content






















REvil ransomware now changes password to auto-login in Safe Mode
































































































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




























HomeNewsSecurityREvil ransomware now changes password to auto-login in Safe Mode







 















REvil ransomware now changes password to auto-login in Safe Mode


By Lawrence Abrams




April 7, 2021
04:06 PM
0





A recent change to the REvil ransomware allows the threat actors to automate file encryption via Safe Mode after changing Windows passwords.
In March, we reported on a new Windows Safe Mode encryption mode added to the REvil/Sodinokibi ransomware. This mode can be enabled using the -smode command-line argument, which would reboot the device into Safe Mode, where it would perform the encryption of files.
It is believed that this mode was added as a way to evade detection by security software and to shut down backup software, database servers, or mail servers to have greater success when encrypting files.
However, at the time of our reporting, the ransomware required someone to manually login to Windows Safe mode before the encryption would start, which could raise red flags.
New version automatically logs Windows into Safe Mode
At the end of March, a new sample of the REvil ransomware was discovered by security researcher R3MRUM that refines the new Safe Mode encryption method by changing the logged-on user's password and configuring Windows to automatically login on reboot.
With this new sample, when the -smode argument is used, the ransomware will change the user's password to 'DTrump4ever.'
The ransomware then configures the following Registry values so that Windows will automatically login with the new account information.
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon]
"AutoAdminLogon"="1"
"DefaultUserName"="[account_name]"
"DefaultPassword"="DTrump4ever"
While it unknown if new samples of the REvil ransomware encryptor continue to use the 'DTrump4ever' password, at least two samples uploaded to VirusTotal in the past two days continue to do so.
These changes illustrate how ransomware gangs continuously evolve their tactics to successfully encrypt victims' devices and force a ransom payment.
REvil also recently warned that they would perform DDoS attacks on victims and email victims' business partners about stolen data if a ransom is not paid.

Related Articles:
New Mimic ransomware abuses ‘Everything’ Windows search toolLockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsMicrosoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flawsRansomware attack forces 100 Romanian hospitals to go offline











Passwords
Ransomware
REvil
Safe Mode
Sodinokibi
Windows
























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











