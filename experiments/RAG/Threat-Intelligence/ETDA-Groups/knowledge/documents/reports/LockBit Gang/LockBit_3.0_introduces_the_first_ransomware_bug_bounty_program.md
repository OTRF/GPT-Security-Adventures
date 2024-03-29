# Reference for threat actor for "LockBit Gang"

**Title**: LockBit 3.0 introduces the first ransomware bug bounty program

**Source**: https://www.bleepingcomputer.com/news/security/lockbit-30-introduces-the-first-ransomware-bug-bounty-program/

## Content






















LockBit 3.0 introduces the first ransomware bug bounty program
































































































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




























HomeNewsSecurityLockBit 3.0 introduces the first ransomware bug bounty program







 














LockBit 3.0 introduces the first ransomware bug bounty program


By Lawrence Abrams


June 27, 2022
11:09 AM
0




The LockBit ransomware operation has released 'LockBit 3.0,' introducing the first ransomware bug bounty program and leaking new extortion tactics and Zcash cryptocurrency payment options.
The ransomware operation launched in 2019 and has since grown to be the most prolific ransomware operation, accounting for 40% of all known ransomware attacks in May 2022.
Over the weekend, the cybercrime gang released a revamped ransomware-as-a-service (RaaS) operation called LockBit 3.0 after beta testing for the past two months, with the new version already used in attacks.
While it is unclear what technical changes were made to the encryptor, the ransom notes are no longer named 'Restore-My-Files.txt' and instead have moved to the naming format, [id].README.txt, as shown below.

LockBit 3.0 ransom noteSource: BleepingComputer
LockBit 3.0 bug bounty program
With the release of LockBit 3.0, the operation has introduced the first bug bounty program offered by a ransomware gang, asking security researchers to submit bug reports in return for rewards ranging between $1,000 and $1 million.
"We invite all security researchers, ethical and unethical hackers on the planet to participate in our bug bounty program. The amount of remuneration varies from $1000 to $1 million," reads the LockBit 3.0 bug bounty page.

LockBit 3.0 bug bounty programSource: BleepingComputer
However, this bug bounty program is a bit different than those commonly used by legitimate companies, as helping the criminal enterprise would be illegal in many countries.
Furthermore, LockBit is not only offering bounties for rewards on vulnerabilities but is also paying bounties for "brilliant ideas" on improving the ransomware operation and for doxxing the affiliate program manager.
The following are the various bug bounty categories offered by the LockBit 3.0 operation:

Web Site Bugs: XSS vulnerabilities, mysql injections, getting a shell to the site and more, will be paid depending on the severity of the bug, the main direction is to get a decryptor through bugs web site, as well as access to the history of correspondence with encrypted companies.
Locker Bugs: Any errors during encryption by lockers that lead to corrupted files or to the possibility of decrypting files without getting a decryptor.
Brilliant ideas: We pay for ideas, please write us how to improve our site and our software, the best ideas will be paid. What is so interesting about our competitors that we don't have?
Doxing: We pay exactly one million dollars, no more and no less, for doxing the affiliate program boss. Whether you're an FBI agent or a very clever hacker who knows how to find anyone, you can write us a TOX messenger, give us your boss's name, and get $1 million in bitcoin or monero for it.
TOX messenger: Vulnerabilities of TOX messenger that allow you to intercept correspondence, run malware, determine the IP address of the interlocutorand other interesting vulnerabilities.
Tor network: Any vulnerabilities which help to get the IP address of the server where the site is installed on the onion domain, as well as getting root access to our servers, followed by a database dump and onion domains.

The $1,000,000 reward for identifying the affiliate manager, known as LockBitSupp, was previously offered on the XSS hacking forum in April.

LockBitSupp offering a $1 million bounty to anyone who identifies themSource: BleepingComputer
Upcoming ZCash payment option?
When opening the Tor sites for the LockBit 3.0 negotiation and data leak sites, visitors are presented with an animated logo with various cryptocurrency icons rotating around it.
The cryptocurrency icons shown in this animation are Monero and Bitcoin, which the operation accepted as ransom payments in the past, but also includes the privacy coin known as Zcash.

New cryptocurrency animation on LockBit 3.0 sitesSource: BleepingComputer
The addition of Zcash as a payment option is not surprising for a ransomware operation.
Cryptocurrency tracking companies and law enforcement seizures have repeatedly shown that Bitcoin can be traced, and while Monero is a privacy coin, it isn’t offered for sale by the vast majority of US crypto exchanges.
Zcash is also a privacy coin, making it harder to trace. Still, it is currently offered for sale at the most popular US crypto exchange, Coinbase, making it easier for victims to purchase for ransom payments.
However, if ransomware operations switch to accepting payments in this coin, we will likely see it be removed from US exchanges due to pressure from the US government.
LockBit to sell victim's stolen data?
LeMagIT's Valery Marchive discovered that the LockBit 3.0 operation is utilizing a new extortion model, allowing threat actors to buy data stolen during attacks.
One of the JavaScript files used by the new LockBit 3.0 data leak site shows a new HTML modal dialog that allows people to purchase data leaked on the site.
As you can see below, the modals will offer the ability to buy the data and download it either through a Torrent or directly on the site. The available options may be determined based on the size of the stolen data, with Torrents being used for large data dumps and direct downloads for smaller amounts.

JavaScript source showing new data extortion methodSource: BleepingComputer
As the LockBit 3.0 data leak site does not currently contain any victims, it is not clear how this new extortion tactic will work or if it is even enabled.
LockBit is one of the most active ransomware operations, with its public-facing operator actively engaging with other threat actors and the cybersecurity community.
Due to its ongoing adoption of new tactics, technology, and payment methods, it is vital for security and network professionals to stay up to date on the evolution of the operation.

Related Articles:
Capital Health attack claimed by LockBit ransomware, risk of data leakLockbit ransomware disrupts emergency care at German hospitalsLockBit claims ransomware attack on Fulton County, GeorgiaBank of America warns customers of data breach after vendor hackRansomware payments reached record $1.1 billion in 2023








Bug Bounty
Extortion
LockBit
LockBit 3.0
Ransomware
Zcash



















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











