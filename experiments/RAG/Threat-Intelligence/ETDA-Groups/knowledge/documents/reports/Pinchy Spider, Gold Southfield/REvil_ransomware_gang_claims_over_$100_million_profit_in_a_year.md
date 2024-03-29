# Reference for threat actor for "Pinchy Spider, Gold Southfield"

**Title**: REvil ransomware gang claims over $100 million profit in a year

**Source**: https://www.bleepingcomputer.com/news/security/revil-ransomware-gang-claims-over-100-million-profit-in-a-year/

## Content






















REvil ransomware gang claims over $100 million profit in a year
































































































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




























HomeNewsSecurityREvil ransomware gang claims over $100 million profit in a year







 















REvil ransomware gang claims over $100 million profit in a year


By Ionut Ilascu




October 29, 2020
02:02 AM
0





REvil ransomware developers say that they made more than $100 million in one year by extorting large businesses across the world from various sectors.
They are driven by profit and want to make $2 billion from their ransomware service, adopting the most lucrative trends in their pursuit of wealth.
Affiliates do the heavy lifting
A REvil representative that uses the aliases “UNKN” and “Unknown” on cybercriminal forums talked to tech blog Russian OSINT offering some details about the group’s activity and hints of what they have in store for the future.
Like almost all ransomware gangs today, REvil runs a ransomware-as-a-service (RaaS) operation. Per this model, developers supply file-encrypting malware to affiliates, who earn the lion’s share from the money extorted from victims.
With REvil, the developers take 20-30% and the rest of the paid ransom goes to affiliates, who run the attacks, steal data, and detonate the ransomware on corporate networks.

“Most work is done by distributors and ransomware is just a tool, so they think that’s a fair split,” REvil representative, Unknown, told Russian OSINT.

This means that the developers set the ransom amount, run the negotiations, and collect the money that is later split with affiliates.
Long list of victims
The cybercriminal operation has encrypted computers at big-name companies, among them Travelex, Grubman Shire Meiselas & Sacks (GSMLaw), Brown-Forman, SeaChange International, CyrusOne, Artech Information Systems, Albany International Airport, Kenneth Cole, and GEDIA Automotive Group.
Unknown says that REvil affiliates were able to breach the networks of Travelex and GSMLaw in just three minutes by exploiting a vulnerability in Pulse Secure VPN left unpatched for months after the fix became available [1, 2].

source: Bad Packets
REvil’s public-facing representative says that the syndicate has hit the network of a “major gaming company” and will soon announce the attack.
They also say that REvil was responsible for the attack in September against Chile’s public bank, BancoEstado. The incident prompted the bank to close all its branches for a day but did not affect online banking, apps, and ATMs.
Along with managed services providers (MSPs) that have access to networks of multiple organizations, the most profitable targets for REvil are companies in the insurance, legal, and agriculture sectors
As for initial access, Unknown mentioned brute-force attacks as well as remote desktop protocol (RDP) combined with new vulnerabilities.
One example are vulnerabilities tracked as CVE-2020-0609 and CVE-2020-0610 bugs and known as BlueGate. These allow remote code execution on systems running Windows Server (2012, 2012 R2, 2016, and 2019).
New money-making avenues
REvil initially made its profit from victims paying the ransom to unlock encrypted files. Since the attackers also locked backup servers, victims had few options to recover, and paying was the quickest way.
The ransomware business changed last year when operators saw an opportunity in stealing data from breached networks and started to threaten victims with damaging leaks that could have a much worse impact on the company.
Even if it takes longer and causes a significant setback, large businesses can recover encrypted files from offline backups. Having sensitive data in the public space or sold to interested parties, though, can be synonymous with losing the competitive advantage and reputation damage that is difficult to rebuild.
This method proved to be so lucrative that REvil now makes more money from not publishing stolen data than from decryption ransom.
Unknown says that one in three victims are currently willing to pay the ransom to prevent the leaking of company data. This could be the next step in the ransomware business.
REvil is also thinking to adopt another tactic designed to increase their odds of getting paid: hitting the victim with distributed denial-of-service (DDoS) attacks to force them to at least (re)start negotiating a payment.
SunCrypt ransomware used this tactic recently on a company that had stopped negotiations. The attackers made it clear that they launched the DDoS attack and terminated it when negotiations resumed. REvil plans to implement this idea.
REvil’s model for making money is working and the gang already has plenty in their coffers. In their search for new affiliates, they deposited $1 million in bitcoins on a Russian-speaking forum.

The move was designed to show that their operation generates plenty of profit. According to Unknown, this step is to recruit new blood to distribute the malware, as the ransomware scene is full to the brim with professional cybercriminals.
Although they have truckloads of money, REvil developers are confined to the borders of the Commonwealth of Independent States (CIS, countries in the former Soviet Union) region.
A reason for this is attacking a large number of high-profile victims that prompted investigations from law enforcement agencies from all over the world. As such, traveling is a risk REvil developers are not willing to take.
REvil built on older code
This ransomware syndicate is also referred to as Sodin or Sodinokibi but the name REvil is inspired by the Resident Evil movie and stands for Ransomware Evil.
Their malware was first spotted in April 2019 and the group started looking for skilled hackers (elite penetration testers) shortly after GandCrab ransomware closed shop.
Unknown says that the group did not create the file-encrypting malware from scratch but bought the source code and developed on top of it to make it more effective.
It uses elliptic curve cryptography (ECC) that has a smaller key size than the RSA-based public-key system, with no compromise on security. Unknown says that this is one reason affiliates choose REvil over other RaaS operations like Maze or LockBit.
Before shutting their business, GandCrab developers said they made $150 million, while the entire operation collected more than $2 billion in ransom payments.
Clearly, REvil developer’s ambitions are greater.
BleepingComputer was told that Unknown confirmed that the interview (in Russian) was real.

 

Related Articles:
Ransomware payments reached record $1.1 billion in 2023Ransomware payments drop to record low as victims refuse to payRansomware victims targeted by fake hack-back offersMGM casino's ESXi servers allegedly encrypted in ransomware attackIntegris Health patients get extortion emails after cyberattack











Extortion
Ransomware
REvil
Sodinokibi
























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











