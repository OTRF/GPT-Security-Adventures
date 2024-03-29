# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: Lazarus hackers target researchers with trojanized IDA Pro

**Source**: https://www.bleepingcomputer.com/news/security/lazarus-hackers-target-researchers-with-trojanized-ida-pro/

## Content






















Lazarus hackers target researchers with trojanized IDA Pro
































































































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




























HomeNewsSecurityLazarus hackers target researchers with trojanized IDA Pro







 














Lazarus hackers target researchers with trojanized IDA Pro


By Lawrence Abrams


November 10, 2021
12:08 PM
0




A North Korean state-sponsored hacking group known as Lazarus is again trying to hack security researchers, this time with a trojanized pirated version of the popular IDA Pro reverse engineering application.
IDA Pro is an application that converts an executable into assembly language, allowing security researchers and programmers to analyze how a program works and discover potential bugs.
Security researchers commonly use IDA to analyze legitimate software for vulnerabilities and malware to determine what malicious behavior it performs.
However, as IDA Pro is an expensive application, some researchers download a pirated cracked version instead of purchasing it.
As with any pirated software, there is always the risk of it being tampered modified to include malicious executables, which is precisely what ESET researcher Anton Cherepanov discovered in a pirated version of IDA Pro distributed by the Lazarus hacking group.
Trojanized IDA Pro targets security researchers
Today, ESET tweeted about a malicious version of IDA Pro 7.5 discovered by Cherepanov that is being distributed online to target security researchers.
This IDA installer has been modified to include two malicious DLLs named idahelp.dll and win_fw.dll that will be executed when the program is installed.

Malicious DLLs added to pirated IDA ProSource: ESET
The win_fw.dll file will create a new task in the Windows Task Scheduler that launches the idahelper.dll program.

New SRCheck scheduled task created by win_fw.dllSource: ESET
The idahelper.dll will then connect to the devguardmap[.]org site and download payloads believed to be the NukeSped remote access trojan. The installed RAT will allow the threat actors to gain access to the security researcher's device to steal files, take screenshots, log keystrokes, or execute further commands.
"Based on the domain and trojanized application, we attribute this malware to known Lazarus activity, previously reported by Google's Threat Analysis Group and Microsoft," ESET tweeted regarding connection to Lazarus.
Cherepanov told BleepingComputer that while he does not know how the installer is being distributed, it was discovered recently and appears to have been distributed since Q1 2020
Lazarus has a history of targeting researchers
The Lazarus hacking group, also known as Zinc by Microsoft, has a long history of targeting security researchers with backdoors and remote access trojans.
In January, Google disclosed that Lazarus conducted a social media campaign to create fake personas pretending to be vulnerability researchers.

Fake online security researcher personas
Using these personas, the hacking group would contact other security researchers about potential collaboration in vulnerability research.
After establishing contact with a researcher, the hackers would send Visual Studio projects related to an alleged 'vulnerability,' which contained a malicious hidden DLL named 'vcxproj.suo.'
When the researcher attempted to build the project, a pre-build event would execute the DLL, which acted as a custom backdoor installed on the researcher's device.
Other Lazarus attacks also used an Internet Explorer zero-day to deploy malware on security researcher's devices when they visited links sent by the attackers.

Exploiting the Lazarus zero-day in Internet Explorer
While it was never determined what the ultimate goal was for these attacks, it was likely to steal undisclosed security vulnerabilities and exploits that the hacking group could use in their own attacks.

Related Articles:
Hackers used new Windows Defender zero-day to drop DarkMe malwareFBI seizes Warzone RAT infrastructure, arrests malware vendorNew Qbot malware variant uses fake Adobe installer popup for evasionNew ‘Gold Pickaxe’ Android, iOS malware steals your face for fraudUbuntu 'command-not-found' tool can be abused to spread malware








IDA Pro
Lazarus Group
Malware
North Korea
RAT
Security Researcher
Vulnerability Researcher



















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











