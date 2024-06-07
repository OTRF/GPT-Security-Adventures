# Reference for threat actor for "Pinchy Spider, Gold Southfield"

**Title**: REvil ransomware scans victim's network for Point of Sale systems

**Source**: https://www.bleepingcomputer.com/news/security/revil-ransomware-scans-victims-network-for-point-of-sale-systems/

## Content






















REvil ransomware scans victim's network for Point of Sale systems































































































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




























HomeNewsSecurityREvil ransomware scans victim's network for Point of Sale systems







 















REvil ransomware scans victim's network for Point of Sale systems


By Sergiu Gatlan




June 23, 2020
11:38 AM
0





REvil ransomware operators have been observed while scanning one of their victim's network for Point of Sale (PoS) servers by researchers with Symantec's Threat Intelligence team.
REvil (also known as Sodinokibi) is a ransomware-as-a-service (RaaS) operation known for breaching corporate networks using exploits, exposed remote desktop services, spam, as well as hacked Managed Service Providers.
After getting access to a target's network, the operators spread laterally while also stealing data from servers and workstations, later encrypting all the machines on the network after gaining administrative access to a domain controller.
As part of the campaign observed by Symantec, the REvil affiliates used the off-the-shelf Cobalt Strike penetration testing toolkit to deploy REvil (aka Sodinokibi) ransomware payloads on their targets' networks.
Ransom doubled within three hours
In total, the researchers found Cobalt Strike on the networks of eight firms targeted in this campaign, with the attackers infecting and encrypting three companies from the services, food, and healthcare industry sectors with the REvil ransomware.
"The companies targeted in this campaign were primarily large, even multinational, companies, which were likely targeted because the attackers believed they would be willing to pay a large ransom to recover access to their systems," Symantec explained.
Each of the victims was asked to pay $50,000 worth of Monero cryptocurrency or $100,000 if a three hours deadline expired.
The REvil actors did their best to evade detection after gaining access to their targets' networks by using infrastructure hosted on legitimate services such as Pastebin (payload storage) and Amazon CloudFront (command and control server).
They also disabled security software to prevent security teams from detecting their attacks and stole credentials later used to add rogue accounts as a simple way to gain persistence on the compromised machines.
Scans for PoS systems
While the services and food companies were the perfect targets as they were large organizations capable of paying a large ransom to have their systems decrypted, the smaller healthcare org was a smaller outfit that couldn't pay the ransom.
In this case, probably prompted by the fact that there was a high possibility that the victim won't be able to pay for their "decryptor," the REvil operators also scanned the healthcare organization's network for PoS systems as part of a credit card data theft attempt or as an additional valuable target worth encrypting.
"While many of the elements of this attack are 'typical' tactics seen in previous attacks using Sodinokibi, the scanning of victim systems for PoS software is interesting, as this is not typically something you see happening alongside targeted ransomware attacks," Symantec concluded.
"It will be interesting to see if this was just opportunistic activity in this campaign, or if it is set to be a new tactic adopted by targeted ransomware gangs."
Earlier this month, REvil ransomware also launched an auction site for selling their victims' stolen data to the highest bidder.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBank of America warns customers of data breach after vendor hackFree Rhysida ransomware decryptor for Windows exploits RNG flaw











Point of Sale
POS
Ransomware
REvil
























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











