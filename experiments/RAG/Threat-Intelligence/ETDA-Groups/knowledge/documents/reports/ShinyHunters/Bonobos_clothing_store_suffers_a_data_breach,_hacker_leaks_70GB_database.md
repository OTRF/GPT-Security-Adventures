# Reference for threat actor for "ShinyHunters"

**Title**: Bonobos clothing store suffers a data breach, hacker leaks 70GB database

**Source**: https://www.bleepingcomputer.com/news/security/bonobos-clothing-store-suffers-a-data-breach-hacker-leaks-70gb-database/

## Content






















Bonobos clothing store suffers a data breach, hacker leaks 70GB database
































































































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




























HomeNewsSecurityBonobos clothing store suffers a data breach, hacker leaks 70GB database







 














Bonobos clothing store suffers a data breach, hacker leaks 70GB database


By Lawrence Abrams


January 22, 2021
02:11 PM
0




Bonobos men's clothing store has suffered a massive data breach exposing millions of customers' personal information after a cloud backup of their database was downloaded by a threat actor. Bonobos states that the corporate systems were not breached during the attack.
Bonobos started as an online men's clothing store but later expanded to sixty locations to try on clothes before purchasing them. Walmart bought Bonobos in 2017 for $300 million to sells its clothing on their Jet.com site.
Last weekend, a threat actor known as ShinyHunters, who is notorious for hacking online services and selling stolen databases, posted the full Bonobos database to a free hacker forum.

Forum post leaking the Bonobos database
Massive 70 GB database leaked
This leaked database is a monstrous 70 GB SQL file containing various internal tables used by the Bonobos website. The database also includes various data far more interesting to threat actors, such as customers' addresses, phone numbers, partial credit card numbers (last four digits), order information, password histories.
The amount of records varies depending on the category of the data. For example, the address and phone numbers are for 7 million shipping addresses, account information for 1.8 million registered customers, and 3.5 million partial credit card records.

Leaked user records table
The passwords stored in the database are hashed using SHA-256 or SHA-512 according to threat actors who have started to analyze the database. One threat actor claims to have already cracked the passwords for 158,000 SHA-256 passwords but has been unable to crack the SHA-512 passwords.
The hacker turned the cracked passwords into a 'combolist' used in credential stuffing attacks, which is to log in using the stolen credentials at other sites.
Backup database was stolen from the cloud
After BleepingComputer contacted Bonobos about the leaked database, the clothing store told us that the threat actors did not gain access to internal systems but rather to a backup file hosted in an external cloud environment.
"Protecting our customers’ data is something we take very seriously. We’re investigating this matter further and, so far, have found no evidence of unauthorized parties gaining access to Bonobos’ internal system. What we have discovered is an unauthorized third party was able to view a backup file hosted in an external cloud environment. We contacted the host provider to resolve this issue as soon as we became aware of it."
"Also, we have taken additional precautionary steps, including turning off access points, invalidating account passwords and requiring password resets, to further secure customer accounts. We're emailing customers to notify them that their contact information and encrypted passwords may have been viewed by an unauthorized third party. Payment information was not affected by this issue. We’ll continue to share updates with customers as they become available," Bonobos told BleepingComputer via email.
Though the database did not include full payment information in the database, threat actors can use the partial data in targeted phishing attacks.

Partial credit card information in the database
Update 1/24/21: Bonobos has begun to email data breach notifications to affected customers, as shown below.

Bonobos data breach notification
What should Bonobos users do?
As this is a confirmed data breach, it is strongly recommended that all Bonobos users immediately change their password on the site.
If the same password has been used at other sites, change your password to a unique one there as well.
Using unique passwords at every site you have an account prevents a data breach at one site from affecting you at other websites you use.
BleepingComputer recommends using a password manager to track strong and unique passwords for the sites you have accounts.
Finally, all Bonobos customers should be on the lookout for emails asking for credit card or login information, as it could be targeted phishing scams resulting from this data breach.
Update 1/22/21: Our story originally mentioned that the database contained virtual gift cards. Bonobos told us that this data is store credit and cannot be redeemed as tender.Update 1/24/21: Bonobos has begun to email data breach notifications to affected users.

Related Articles:
Johnson Controls says ransomware attack cost $27 million, data stolenHow SMBs can lower their risk of cyberattacks and data breachesCredentials are Still King: Leaked Credentials, Data Breaches and Dark Web MarketsFidelity National Financial: Hackers stole data of 1.3 million peopleHalara probes breach after hacker leaks data for 950,000 people








Bonobos
Clothing
Cyberattack
Data Breach
Database
Hacker Forum



















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











