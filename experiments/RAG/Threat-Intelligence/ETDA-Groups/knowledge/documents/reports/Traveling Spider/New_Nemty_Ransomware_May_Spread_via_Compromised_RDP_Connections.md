# Reference for threat actor for "Traveling Spider"

**Title**: New Nemty Ransomware May Spread via Compromised RDP Connections

**Source**: https://www.bleepingcomputer.com/news/security/new-nemty-ransomware-may-spread-via-compromised-rdp-connections/

## Content






















New Nemty Ransomware May Spread via Compromised RDP Connections































































































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




























HomeNewsSecurityNew Nemty Ransomware May Spread via Compromised RDP Connections







 














New Nemty Ransomware May Spread via Compromised RDP Connections


By Ionut Ilascu


August 26, 2019
03:29 AM
0




A new ransomware has been spotted over the weekend, carrying references to the Russian president and antivirus software. The researchers call it Nemty.
This is the first version of Nemty ransomware, named so after the extension it adds to the files following the encryption process.
The ransom demand
Like any proper file-encrypting malware, Nemty will delete the shadow copies for the files it processes, taking away from the victim the possibility to recover versions of the data as created by the Windows operating system.
Victims will see a ransom note informing that the attackers hold the decryption key and that data is recoverable for a price.

In BleepingComputer's tests, the ransom demand was 0.09981 BTC, which converts to around $1,000 at the moment.
The payment portal is hosted on the Tor network for anonymity, and users have to upload their configuration file.
Based on this, they are provided with the link to another website that comes with a chat function and more information on the demands.

Messages in the code
Security researcher Vitali Kremez took a closer look at the malware and noticed that it comes with an unusual name for the mutex object. The author called it "hate," as visible in the image below.

A mutually exclusive (mutex) object is a flag that allows programs to control resources by allowing access to them to one execution thread at a time.
Another weird thing Kremez noticed in Nemty's code is a link to this picture of Vladimir Putin, with a caption saying "I added you to the list of [insult], but only with pencil for now."
The list of peculiarities does not stop at this. A straight message to the antivirus industry was spotted by the researcher.
At first, the reference seemed an odd thing in the code but a second look at how Nemty worked revealed that it was the key for decoding base64 strings and create URLs is a straight message to the antivirus industry.

Another interesting thing is a verification Nemty makes to identify computers in Russia, Belarus, Kazakhstan, Tajikistan, and Ukraine. This is not to exempt the hosts from the file encryption routine, though, Kremez told BleepingComputer.
The "isRU" check in the malware code simply marks the systems as being in one of the five countries and then sends to the attacker data that includes the computer name, username, operating system, and computer ID.

It's unclear how Nemty is distributed but Kremez heard from a reliable source that the operators deploy it via compromised remote desktop connections.
Compared to phishing email, which is currently the common distribution method, leveraging a RDP connection puts the attacker in control as they no longer have to wait for the victim to take the phishing bait.
Kremez published his research notes on Nemty where he includes the list of folders (anything needed for booting the OS) and the file extensions (binaries, shortcuts, and log data) the malware does not touch.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBank of America warns customers of data breach after vendor hackFree Rhysida ransomware decryptor for Windows exploits RNG flaw








Nemty Ransomware
Ransomware



















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











