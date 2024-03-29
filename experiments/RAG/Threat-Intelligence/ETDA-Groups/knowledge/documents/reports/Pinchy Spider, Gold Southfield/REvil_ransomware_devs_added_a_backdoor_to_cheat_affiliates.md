# Reference for threat actor for "Pinchy Spider, Gold Southfield"

**Title**: REvil ransomware devs added a backdoor to cheat affiliates

**Source**: https://www.bleepingcomputer.com/news/security/revil-ransomware-devs-added-a-backdoor-to-cheat-affiliates/

## Content






















REvil ransomware devs added a backdoor to cheat affiliates
































































































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




























HomeNewsSecurityREvil ransomware devs added a backdoor to cheat affiliates







 















REvil ransomware devs added a backdoor to cheat affiliates


By Ionut Ilascu




September 23, 2021
02:26 AM
0





Cybercriminals are slowly realizing that the REvil ransomware operators may have been hijacking ransom negotiations, to cut affiliates out of payments.
By using a cryptographic scheme that allowed them to decrypt any systems locked by REvil ransomware, the operators left their partners out of the deal and stole the entire ransom.
Conversations about this practice started a while ago on underground forums, in posts from collaborators of the gang, and have been confirmed recently by security researchers and by malware developers.
REvil ransomware, also known as Sodinokibi, emerged in the first half of 2019 and built a reputation as a successor of the GandCrab ransomware-as-a-service (RaaS) operation.
The RaaS cybercriminal business model involves a developer, who creates the ransomware malware and sets up the infrastructure, and affiliates recruited to breach and encrypt victims. The proceedings are divided between the two parties with affiliates taking the larger cut (typically 70-80%). 
Promoted by veterans of underground forums, the REvil gang developed a highly lucrative private operation that accepted only experienced network hackers.
REvil name goes down the drain
If the REvil operation started as an “honest” cybercriminal endeavor, it soon switched to scamming affiliates out of the promised 70% share of a ransom from paying victims.
Yelisey Boguslavskiy, head of research at Advanced Intel, told BleepingComputer that since at least 2020 various actors on underground forums claimed that the RaaS operators were taking over negotiations with victims in secret chats, unbeknownst to affiliates.
The rumor became more frequent after the sudden shut down of DarkSide ransomware and Avaddon’s exit by releasing the decryption keys for their victims.
The conversations involved individuals that played a role in REvil ransomware attacks, such as partners that provided network access, penetration-testing services, VPN specialists, and potential affiliates.
Boguslavskiy says that REvil admins reportedly opened a second chat, identical to the one used by their affiliate to negotiate a ransom with the victim.
When talks reached a critical point, REvil would take over by posing as the victim quitting the negotiations without paying the ransom, Boguslavskiy explained to BleepingComputer.
The gang would continue the talks with the victim and obtain the full ransom with the affiliate being none the wiser.
Recently, these claims got more substance as an underground malware reverse engineer provided evidence of REvil’s double-dipping practices. They talk of a “cryptobackdoor” in the REvil samples that RaaS operators gave affiliates to deploy on victim networks.
The author’s revelation comes after cybersecurity company Bitdefender released a universal REvil decryption tool that works for all victims encrypted up to July 13, 2021.

source: Advanced Intel
Public key in the image above:

FF5EEDCAEDEE6250D488F0F04EFA4C957B557BDBDC0BBCA2BA1BB7A64D043A3D
What the author of the above post is saying is that affiliates were not the only ones that could decrypt the systems they locked with the REvil ransomware sample they received.
REvil operators had a master key they could use to restore encrypted files.
Researcher revealed the trick in July
Fabian Wosar, “ransomware slayer” par excellence and chief technology officer at Emsisoft, in early July provided a clear explanation for how REvil’s cryptographic scheme worked.
GandCrab’s successor uses in their malware four sets of public-private keys responsible for the encryption and decryption tasks:
An operator/master pair that has the public part hardcoded in all REvil samples
A campaign pair, whose public part is stored in the configuration file of the malware as a PK value
A system-specific pair - generated upon encrypting the machine, with the private part encrypted using both the public master and campaign keys
A key pair generated for each encrypted file

“The private file key and public system key are then used as inputs for ECDH using Curve25519 in order to generate the Salsa20 key (called a shared secret) that is being used to actually encrypt the file content,” Wosar explains.

The system private key is essential to unlocking a machine because it is the only one required to decrypt individual files. Recovering it is possible with either the master private key - available only to REvil operators, or the campaign key that affiliates have.
Wosar notes that the master private key is REvil’s insurance against rogue affiliates, allowing them to decrypt any victim. This is also what Bitdefender used for their REvil decryption tool and likely what helped Kaseya victims recover files for free.
To access the REvil payment portal, the ransomware threat actor requires a blob of data present in the ransom note. That string of apparently nonsensical characters includes various data about the machine, campaign, version of the malware used, and the system private key.

source: Fabian Wosar
Keeping an ace up their sleeve that gives ransomware operators total control over decrypting any system locked by their malware is a practice seen with other, newer ransomware groups.
Boguslavskiy says that the DarkSide ransomware gang was rumored to run their operation in the same way.
After rebranding as BlackMatter, the actor was open about this practice, letting everybody know that they reserved their right to take over the negotiations at any point, without explaining.
Reverse engineer and Advanced Intelligence CEO Vitali Kremez told BleepingComputer that the latest REvil samples, which emerged when the gang restarted operations, no longer have the master key that enabled the decryption of any system locked with REvil ransomware.

Related Articles:
Ransomware victims targeted by fake hack-back offersLockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBank of America warns customers of data breach after vendor hack











Decryption Key
Ransomware
REvil
Scam
























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











