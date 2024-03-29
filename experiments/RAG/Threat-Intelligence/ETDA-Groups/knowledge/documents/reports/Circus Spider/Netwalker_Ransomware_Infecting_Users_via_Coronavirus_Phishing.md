# Reference for threat actor for "Circus Spider"

**Title**: Netwalker Ransomware Infecting Users via Coronavirus Phishing

**Source**: https://www.bleepingcomputer.com/news/security/netwalker-ransomware-infecting-users-via-coronavirus-phishing/

## Content






















Netwalker Ransomware Infecting Users via Coronavirus Phishing































































































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




























HomeNewsSecurityNetwalker Ransomware Infecting Users via Coronavirus Phishing







 














Netwalker Ransomware Infecting Users via Coronavirus Phishing


By Lawrence Abrams


March 21, 2020
12:06 PM
0




As if people did not have enough to worry about, attackers are now targeting them with Coronavirus (COVID-19) phishing emails that install ransomware.
While we do not have access to the actual phishing email being sent, MalwareHunterTeam was able to find an attachment used in a new Coronavirus phishing campaign that installs the Netwalker Ransomware.
Netwalker is a ransomware formerly called Mailto that has become active recently as it targets the enterprise and government agencies. Two widely reported attacks related to Netwalker are the ones on the Toll Group and the Champaign Urbana Public Health District (CHUPD) in Illinois.
The new Netwalker phishing campaign is using an attachment named "CORONAVIRUS_COVID-19.vbs" that contains an embedded Netwalker Ransomware executable and obfuscated code to extract and launch it on the computer.

VBS Attachment
When the script is executed, the executable will be saved to %Temp%\qeSw.exe and launched.

Netwalker Executable
Once executed, the ransomware will encrypt the files on the computer and append a random extension to encrypted file names.
Head of SentinelLabs Vitali Kremez, the research division of SentinelOne, told BleepingComputer that this version of the ransomware specifically avoids terminating the Fortinet endpoint protection client.
When asked why they would do that, Kremez stated it may be to avoid detection.
"I suppose it might be because they have already disabled the anti-virus functionality directly from the customer admin panel; however, they do not want to trip an alarm by terminating the clients," Kremez told BleepingComputer.
When done, victims will find a ransom note named [extension]-Readme.txt that contains instructions on how to access the ransomware's Tor payment site to pay the ransom demand.

Netwalker Ransom Note
Unfortunately, at this time there is no known weakness in the ransomware that would allow victims to decrypt their files for free.
Instead, victims will need to either restore from backup or recreate the missing files.
Coronavirus attacks have become common
Due to the ongoing Coronavirus pandemic, threat actors have actively started using the outbreak as a theme for their phishing campaigns and malware.
We have seen the TrickBot trojan using text from Coronavirus related news stories to evade detection, a ransomware called CoronaVirus, the data-stealing FormBook malware spread through phishing campaigns, and even an email extortion campaign threatening to infect your family with Coronavirus.
This has led to the US Cybersecurity and Infrastructure Security Agency (CISA) to issue warnings about the rise of Coronavirus-themed scams and the World Health Organization (WHO) to release warnings of phishing scams impersonating their organization.
As threat actors commonly take advantage of topics that spread anxiety and fear, everyone must be more diligent than ever against suspicious emails and the promotion of programs from unknown sources.

Related Articles:
New Qbot malware variant uses fake Adobe installer popup for evasionLockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBumblebee malware attacks are back after 4-month break








Coronavirus
COVID-19
Netwalker
Phishing
Ransomware



















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











