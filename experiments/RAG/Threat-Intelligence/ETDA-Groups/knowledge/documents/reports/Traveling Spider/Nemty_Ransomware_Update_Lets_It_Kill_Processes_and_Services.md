# Reference for threat actor for "Traveling Spider"

**Title**: Nemty Ransomware Update Lets It Kill Processes and Services

**Source**: https://www.bleepingcomputer.com/news/security/nemty-ransomware-update-lets-it-kill-processes-and-services/

## Content






















Nemty Ransomware Update Lets It Kill Processes and Services































































































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




























HomeNewsSecurityNemty Ransomware Update Lets It Kill Processes and Services







 














Nemty Ransomware Update Lets It Kill Processes and Services


By Ionut Ilascu


September 14, 2019
03:11 PM
0




Nemty ransomware is under active development, although its version number may not show it. Its authors are clearly making efforts to make it a more efficient and sophisticated malware and it begins wider distribution.
The malware is new in the business and its cold reception in the ransomware underground community did not help it take off the way its administrators wanted.
Process and service killer
Despite making changes to the code, Nemty authors kept the same version number, shows an analysis from security researcher Vitali Kremez. The code, however, shows modifications that make the ransomware more aggressive in its actions.
The researcher noticed that the latest version of the malware includes code for killing processes and services in order to encrypt files that are currently in use.

Process and service killer 
(Source: Vitali Kremez)
A look at Nemty's new code reveals a set of nine targeted processes, which include WordPad, Microsoft Word, Excel, Outlook Thunderbird email clients, SQL, and the VirtualBox software for running virtual machines.
With SQL and VirtualBox on the list, it gives us a clue that Nemty is targeting corporate victims.

List of terminated processes
More countries on the "no-no" list
Kremez also observed that the 'isRu' check has now extended to more countries. The full list now including Russia, Belarus, Kazakhstan, Tajikistan, Ukraine, Azerbaijan, Armenia, Kyrgyzstan, and Moldova, with the last four being the latest additions.
With an earlier version of the malware, 'isRU' did not make any difference for the encryption job and just marked those hosts to send system information to the command and control server. An update changed this and aborted encryption on computers positive for this check.

Blacklisted countries
New distribution pipeline
One of the first versions of Nemty was seen distributed by RIG EK (exploit kit), while a more recent release, 1.4, spread through a fake PayPal page.
At the beginning of this week, a new release was observed by security researchers where they observed changes in the way victims are chosen and how the encryption process works.
The malware operators have a new distributor on their list, Radio EK, as found by nao_sec at the beginning of the week.
This is not a top-quality distributor, though, as the EK exploits a vulnerability in JScript and VBScript for Internet Explorer that Microsoft patched three years ago, the researcher told BleepingComputer.

RadioEK in a malvertising campaign
Nemty may not enjoy much success at the moment but its authors seem to be putting in the energy to earn the respect of cybercriminals on ransomware forums and turn their malware into a lucrative business.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBank of America warns customers of data breach after vendor hackFree Rhysida ransomware decryptor for Windows exploits RNG flaw








Nemty Ransomware
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











