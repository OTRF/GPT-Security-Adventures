# Reference for threat actor for "Sandworm Team, Iron Viking, Voodoo Bear"

**Title**: Russian Sandworm hackers breached 11 Ukrainian telcos since May

**Source**: https://www.bleepingcomputer.com/news/security/russian-sandworm-hackers-breached-11-ukrainian-telcos-since-may/

## Content






















Russian Sandworm hackers breached 11 Ukrainian telcos since May
































































































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




























HomeNewsSecurityRussian Sandworm hackers breached 11 Ukrainian telcos since May







 














Russian Sandworm hackers breached 11 Ukrainian telcos since May


By Bill Toulas


October 16, 2023
02:06 PM
0




The state-sponsored Russian hacking group tracked as 'Sandworm' has compromised eleven telecommunication service providers in Ukraine between May and September 2023.
That is based on a new report by Ukraine's Computer Emergency Response Team (CERT-UA) citing 'public resources' and information retrieved from some breached providers.
The agency states that the Russian hackers "interfered" with the communication systems of 11 telcos in the country, leading to service interruptions and potential data breaches.
Sandworm is a very active espionage threat group linked to Russia's GRU (armed forces). The attackers have focused on Ukraine throughout 2023, using phishing lures, Android malware, and data-wipers.
Targeting telcos
The attacks begin with Sandworm performing reconnaissance on telecommunication company's networks using the 'masscan' tool to perform scans on the target's network.

Example of masscan script (CERT-UA)
Sandworm looks for open ports and unprotected RDP or SSH interfaces they can leverage to breach the network.
Additionally, the attackers use tools like 'ffuf', 'dirbuster', 'gowitness', and 'nmap' to find potential vulnerabilities in web services that can be exploited to gain access.
Compromised VPN accounts that weren't protected by multi-factor authentication have also been leveraged to gain network access.
To make their intrusions stealthier, Sandworm uses 'Dante', 'socks5,' and other proxy servers to route their malicious activities through servers within the Ukrainian internet region they compromised previously, making it appear less suspicious.
CERT-UA reports seeing two backdoors in breached ISP systems, namely 'Poemgate' and 'Poseidon.'
Poemgate captures the credentials of admins who attempt to authenticate in the compromised endpoint, providing the attackers with access to additional accounts they can use for lateral movement or deeper network infiltration.
Poseidon is a Linux backdoor that the Ukrainian agency says "includes the full range of remote computer control tools." Persistence for Poseidon is achieved by modifying Cron to add rogue jobs.

Cron binary modification to add persistence for Poseidon (CERT-UA)
Sandworm uses the 'Whitecat' tool to remove the attack's traces and delete access logs.
At the final stages of the attack, the hackers were seen deploying scripts that would cause service disruption, especially focusing on Mikrotik equipment, and wipe backups to make recovery more challenging.

Script to impair Mikrotik devices (CERT-UA)
CERT-UA advises that all service providers in the country follow the recommendations in this guide to make it harder for cyber intruders to breach their systems.

Related Articles:
Pro-Ukraine hackers breach Russian ISP in revenge for KyivStar attackRussian hackers wiped thousands of systems in KyivStar attackRussian military hackers target Ukraine with new MASEPIE malwareUkraine: Hack wiped 2 petabytes of data from Russian research centerTurla hackers backdoor NGOs with new TinyTurla-NG malware








Backdoor
Hackers
Russia
Sandworm
Telecommunications
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











