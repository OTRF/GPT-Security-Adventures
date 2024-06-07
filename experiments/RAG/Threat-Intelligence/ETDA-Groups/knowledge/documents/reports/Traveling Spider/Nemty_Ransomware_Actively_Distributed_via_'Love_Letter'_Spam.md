# Reference for threat actor for "Traveling Spider"

**Title**: Nemty Ransomware Actively Distributed via 'Love Letter' Spam

**Source**: https://www.bleepingcomputer.com/news/security/nemty-ransomware-actively-distributed-via-love-letter-spam/

## Content






















Nemty Ransomware Actively Distributed via 'Love Letter' Spam































































































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




























HomeNewsSecurityNemty Ransomware Actively Distributed via 'Love Letter' Spam







 














Nemty Ransomware Actively Distributed via 'Love Letter' Spam


By Sergiu Gatlan


February 27, 2020
02:16 PM
0




Security researchers have spotted an ongoing malspam campaign using emails disguised as messages from secret lovers to deliver Nemty Ransomware payloads on the computers of potential victims.
The spam campaign was identified by both Malwarebytes and X-Force IRIS researchers and has started distributing malicious messages yesterday via a persistent stream of emails.
The attackers use several subject lines that hint at the contents of the email being sent by someone the recipient already knows and are built using a love letter template with statements such as "Don't tell anyone," "I love you," "Letter for you," "Will be our secret," and "Can't forget you."
What sets this campaign apart from others is that the operators didn't bother composing an enticing email since all these spam messages only contain a wink ;) text emoticon.
This might be a hint at the attackers thinking that the 'secret lover' bait — as it was dubbed by Malwarebytes — is effective enough on its own.

Sample spam email
"Attached to each email is a ZIP archive with a name formatted as 'LOVE_YOU_######_2020.zip' with only the #s changing," researchers at X-Force IRIS found.
"The hash of the file contained within each of these archives remains the same and is associated with a highly obfuscated JavaScript file named LOVE_YOU.js,"
This malicious JavaScript file has a very low VirusTotal detection rate at the moment which might lead to an increased number of infections until other security solutions add it to their definitions.

The attackers use it to drop a Nemty ransomware executable on the victims' computers when executed by downloading the malicious payload from a remote server and launching it.
"The downloaded executable was identified to be the Nemty ransomware and performs encryption of system files upon execution, leaving behind a ransom note demanding payment in exchange for the decryption key," the researchers discovered.

Nemty ransomware was first spotted in August 2019 and is known for deleting the shadow copies of all the files it encrypts, making it impossible for victims who don't have separate backups to recover their data.
Researchers discovered one month later that the malware's developers upgraded it to include code for killing Windows services and processes to allow it to encrypt files that are currently in use.
Security firm Tesorion created a free Nemty ransomware decryptor in October 2019 for Nemty versions 1.4 and 1.6, and working for a limited number of document types including images, videos, office docs, and archives.
Last month the operators behind the Nemty ransomware said that they're planning to create a leak blog to be used to publish information stolen for ransomware victims who refused to pay the ransoms.
This trend was started by Maze Ransomware in November 2019, with Sodinokibi, BitPyLock, and Nemty following on their tracks and saying that they'll adopt the same tactic (1, 2, 3).

Related Articles:
New Qbot malware variant uses fake Adobe installer popup for evasionNew ‘Gold Pickaxe’ Android, iOS malware steals your face for fraudUbuntu 'command-not-found' tool can be abused to spread malwareHackers used new Windows Defender zero-day to drop DarkMe malwareFBI seizes Warzone RAT infrastructure, arrests malware vendor








MalSpam
Malware
Nemty Ransomware
Spam



















Sergiu Gatlan   
Sergiu is a news reporter who has covered the latest cybersecurity and technology developments for over a decade. Email or Twitter DMs for tips.



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











