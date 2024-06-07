# Reference for threat actor for "TA505, Graceful Spider, Gold Evergreen"

**Title**: Ransomware gang now using critical Windows flaw in attacks

**Source**: https://www.bleepingcomputer.com/news/security/ransomware-gang-now-using-critical-windows-flaw-in-attacks/

## Content






















Ransomware gang now using critical Windows flaw in attacks
































































































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




























HomeNewsSecurityRansomware gang now using critical Windows flaw in attacks







 















Ransomware gang now using critical Windows flaw in attacks


By Ionut Ilascu




October 9, 2020
03:33 AM
0





Microsoft is warning that cybercriminals have started to incorporate exploit code for the ZeroLogon vulnerability in their attacks. The alert comes after the company noticed ongoing attacks from cyber-espionage group MuddyWater (SeedWorm) in the second half of September.
This time, the threat actor is TA505, an adversary who is indiscriminate about the victims it attacks, with a history starting with the distribution of Dridex banking trojan in 2014.
Over the years, the actor has been in attacks delivering a wide variety of malware, from backdoors to ransomware.
Recently, intrusions from this group are followed by the deployment of Clop ransomware, as in the attack on Maastricht University last year that resulted in paying a 30 bitcoin (about $220,000) ransom.
Fake updates and legit tools
Microsoft says that TA505, which it tracks as Chimborazo, deployed a campaign with fake software updates that connect to the threat actor’s command and control (C2) infrastructure.
The purpose of the malicious updates is to give hackers increased privileges (User Account Control bypass) on the target system and run malicious scripts.

source: Microsoft
For the second part, TA505 uses Windows Script Host (WScript.Exe), which allows executing scripts in various programming languages, including VBScript, Python, Ruby, PHP, JavaScript, and Perl.
Microsoft says that the attackers compile a version of the Mimikatz post-exploitation tool using the Microsoft Build Engine (MSBuild.Exe)n for building applications.
The version of Mimikatz obtained this way includes exploit code for the ZeroLogon vulnerability (CVE-2020-1472). Over the past month, numerous researchers released proof–of–concept exploits for this flaw.
What Microsoft described in a short thread is a classic domain takeover attack, where ZeroLogon is a perfect fit. It offers direct access to the domain controller, so the attacker no longer needs to spend time getting the admin credentials.
With TA505 involved in big-money ransomware business, organizations should prioritize applying security patches for this vulnerability as attacks similar to what Microsoft described are likely to occur with increased frequency.
ZeroLogon details available
Discovered by Tom Tervoort of Secura, ZeroLogon allows intruders on a domain network to increase permissions to administrator level without needing to authenticate.
Tervoort found that he could force the connection to a domain controller through the Netlogon Remote Protocol in an unencrypted state (non-secure RPC communication).
Next, by leveraging a flaw in the Netlogon crypto algorithm, it is possible to spoof a domain administrator login. A technical write-up is available from Secura.
Microsoft addressed this vulnerability partially for now, by preventing Windows Active Domain controller communication over non-secure RPC. This update is available since August 11.
On February 9, though, a new update will enforce the same secure communication to all devices on the network.
Warnings released
Network admins received repeated warnings about the severity of the ZeroLogon vulnerability (maximum critical score 10/10) and urged to apply the current patch.
With exploit code that (domain admin privilege obtained in seconds) released since mid-September, threat actors moved quickly to incorporating it in their attacks.
The U.S. Cybersecurity and Infrastructure Security Agency (CISA) on September 18 required the Federal Civilian Executive Branch to treat fixing the flaw as an emergency.
Microsoft first sounded the alarm on September 23, when it saw ZeroLogon actively exploited in attacks. Next came the alert about MuddyWater leveraging the exploit.
Now it’s cybercriminals wielding it, a clear sign that ZeroLogon is on the way of being adopted by a wide range of threat groups targeting organizations in both the public and private sectors.

Related Articles:
Microsoft: New critical Exchange bug exploited as zero-dayZoom patches critical privilege elevation flaw in Windows appsMicrosoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flawsMicrosoft unveils new 'Sudo for Windows' feature in Windows 11New Linux glibc flaw lets attackers get root on major distros











Domain Controller
Privilege Escalation
TA505
Windows
Zerologon
























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











