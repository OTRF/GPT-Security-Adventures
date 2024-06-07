# Reference for threat actor for "Mallard Spider"

**Title**: Qbot steals your email threads again to infect other victims

**Source**: https://www.bleepingcomputer.com/news/security/qbot-steals-your-email-threads-again-to-infect-other-victims/

## Content






















Qbot steals your email threads again to infect other victims
































































































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




























HomeNewsSecurityQbot steals your email threads again to infect other victims







 















Qbot steals your email threads again to infect other victims


By Lawrence Abrams




August 27, 2020
03:32 PM
0





The Qbot trojan is again stealing reply-chain emails that can be used to camouflage malware-riddled emails as parts of previous conversations in future malicious spam campaigns.
Qbot (also known as QakBot) is a banking and information-stealing malware that has been actively infecting victims for more than ten years.
When installed, Qbot will attempt to steal its victims' stored passwords, cookies, credit cards, emails, and online banking credentials.
This trojan is also known to download and install other malware onto compromised computers, including ProLock Ransomware payloads.
Since July 2020, Qbot has been a malware of choice for the notorious Emotet botnet and has seen a surge of new infections.
Qbot steals victim's emails for future malspam campaigns
In 2019, we reported that QBot had started to steal victims' email threads, using them as part of a context-aware phishing campaign during late March 2019.
According to a new report by Check Point, QBot continues to employ a tactic previously used by the Gozi ISFB banking trojan, the URSNIF information-stealing trojan, and the Emotet trojan [1, 2, 3]: the stealing of full email threads to use in reply-chain, or 'hijacked email thread' attacks.
A reply-chain phishing attack is when threat actors use a stolen email thread and then reply to it with their own message and an attached malicious document.
After infecting victims, one of the malicious activities conducted by Qbot is to steal emails from a user's Outlook client.
These stolen emails are then uploaded to the Qbot threat actors servers to be used in future spam campaigns targeting other potential victims.

Reply-chain phishing email (Check Point)
This type of attack makes the phishing campaign more believable, especially when it is used against those in the original thread.
Check Point has observed that these reply-chain attacks contain ZIP attachments with malicious VBS scripts enclosed. When executed, these VBS scripts will download the Qbot malware on the system and infect the user.
"During our tracking of the malspam campaign, we have seen hundreds of different URLs for malicious ZIP dropping when most of them were compromised WordPress sites," Check Point researchers explain.
Using a victim's stolen email against other recipients creates a perpetuating cycle of new victims being used against others to spread the malware.
Since this email thread stealing module has been added, Check Point’s researchers have spotted targeted, hijacked email threads being used in ongoing campaigns with subjects related to tax payment reminders, the Covid-19 pandemic, and job offers.

Infection chain (Check Point)
Malware used in highly-targeted campaigns
Qbot's authors have also added unusual capabilities at one point or another, as well as a clever way for the malware to assemble itself from two encrypted halves to evade detection when being delivered onto a target's system.
The malware is also known for infecting other devices on the same network using network share exploits and as well as highly aggressive brute-force attacks that target Active Directory admin accounts.
Even though it has been active for over a decade, this banking trojan was mostly used in highly targeted attacks on enterprise entities that could provide a higher return on investment.
As proof of this, Qbot attacks have been quite infrequent over time, with researchers spotting one in October 2014, one in April 2016, as well as another one during mid-May 2017. Qbot came back last year, being dropped as a first stage or as a second stage payload by the Emotet gang.

Related Articles:
New Qbot malware variant uses fake Adobe installer popup for evasionQbot malware returns in campaign targeting hospitality industryNew ‘Gold Pickaxe’ Android, iOS malware steals your face for fraudNew critical Microsoft Outlook RCE bug is trivial to exploitUbuntu 'command-not-found' tool can be abused to spread malware











Attachments
Emotet
Maldoc
Malware
Outlook
QakBot
Qbot
Spam
























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











