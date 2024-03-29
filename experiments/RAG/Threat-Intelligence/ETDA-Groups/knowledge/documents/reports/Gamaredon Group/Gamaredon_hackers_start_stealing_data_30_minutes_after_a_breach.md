# Reference for threat actor for "Gamaredon Group"

**Title**: Gamaredon hackers start stealing data 30 minutes after a breach

**Source**: https://www.bleepingcomputer.com/news/security/gamaredon-hackers-start-stealing-data-30-minutes-after-a-breach/

## Content






















Gamaredon hackers start stealing data 30 minutes after a breach
































































































News



Featured
Latest







Microsoft: New critical Exchange bug exploited as zero-day





LockBit claims ransomware attack on Fulton County, Georgia





Trans-Northern Pipelines investigating ALPHV ransomware attack claims





Microsoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flaws









Over 13,000 Ivanti gateways vulnerable to actively exploited bugs





Three critical application security flaws scanners can’t detect





Turla hackers backdoor NGOs with new TinyTurla-NG malware





New Qbot malware variant uses fake Adobe installer popup for evasion








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




























HomeNewsSecurityGamaredon hackers start stealing data 30 minutes after a breach







 















Gamaredon hackers start stealing data 30 minutes after a breach


By Bill Toulas




July 15, 2023
10:07 AM
0





Ukraine's Computer Emergency Response Team (CERT-UA) is warning that the Gamaredon hacking operates in rapid attacks, stealing data from breached systems in under an hour.
Gamaredon, aka Armageddon, UAC-0010, and Shuckworm, is a Russian, state-sponsored cyber-espionage hacking group with cybersecurity researchers linking them to the FSB (Russian Federal Security Service) and having members who are former SSU officers who defected to Russia in 2014.
Since the start of the Russian invasion, the threat actors are believed to be responsible for thousands of attacks against the government and other critical public and private organizations in Ukraine.
The accumulation of data from these attacks has enabled CERT-UA to outline the group's attacks, which it shares to help defenders detect and stop network infiltration attempts.
Gamaredon attack traits
Gamaredon attacks commonly start with an email or message sent to targets via Telegram, WhatsApp, Signal, or other IM apps.
The initial infection is achieved by tricking the victim into opening malicious attachments such as HTM, HTA, and LNK files disguised as Microsoft Word or Excel documents.
Once the victim launches the malicious attachments, PowerShell scripts and malware (usually 'GammaSteel') are downloaded and executed on the victim's device.
The initial infection step also modifies Microsoft Office Word templates so that all documents created on the infected computer carry a malicious macro that can spread Gamaredon's malware to other systems.
The PowerShell script targets browser cookies containing session data to enable the hackers to take over online accounts protected by two-factor authentication.
Regarding GammaSteel's functionality, CERT-UA says it targets files with a specified list of extensions that are: .doc, .docx, .xls, .xlsx, .rtf, .odt, .txt, .jpg, .jpeg, .pdf, .ps1, .rar, .zip, .7z, .mdb.
If the attackers are interested in the documents found on a breached computer, they exfiltrate them within 30-50 minutes.
Another interesting aspect of Gamaredon infections is that the threat actors plant as many as 120 malicious infected files per week on the compromised system to increase the likelihood of re-infection.
"If during the disinfection process, after cleaning the operating system registry, deleting files, scheduled tasks, etc., at least one infected file or document is left on the computer (quite often users reinstall the OS and transfer "necessary" documents without checking), then the computer will likely be infected again." explains CERT-UA (machine translated).
Any USB sticks inserted on the ports of an infected computer will also be automatically infected with Gamaredon's initial compromise payloads, potentially furthering the breach to isolated networks.
Finally, the hackers change the IP addresses of intermediate victim command and control servers three to six times daily, making it harder for defenders to block or trace their activities.
At this time, CERT-UA says the best way to limit the effectiveness of Gamaredon attacks is to block or restrict the unauthorized execution of mshta.exe, wscript.exe, cscript.exe, and powershell.exe.

Related Articles:
Ukraine: Hack wiped 2 petabytes of data from Russian research centerPro-Ukraine hackers breach Russian ISP in revenge for KyivStar attackRussian hackers wiped thousands of systems in KyivStar attackRussian military hackers target Ukraine with new MASEPIE malwareTurla hackers backdoor NGOs with new TinyTurla-NG malware











Armageddon
CERT
Gamaredon
Russia
Ukraine
























Bill Toulas   
Bill Toulas is a tech writer and infosec news reporter with over a decade of experience working on various online publications, covering open-source, Linux, malware, data breach incidents, and hacks.




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











