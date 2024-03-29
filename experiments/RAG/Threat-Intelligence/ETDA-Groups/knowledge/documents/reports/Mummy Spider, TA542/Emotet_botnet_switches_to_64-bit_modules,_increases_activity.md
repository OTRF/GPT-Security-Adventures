# Reference for threat actor for "Mummy Spider, TA542"

**Title**: Emotet botnet switches to 64-bit modules, increases activity

**Source**: https://www.bleepingcomputer.com/news/security/emotet-botnet-switches-to-64-bit-modules-increases-activity/

## Content






















Emotet botnet switches to 64-bit modules, increases activity
































































































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




























HomeNewsSecurityEmotet botnet switches to 64-bit modules, increases activity







 















Emotet botnet switches to 64-bit modules, increases activity


By Bill Toulas




April 19, 2022
03:57 PM
0





The Emotet malware is having a burst in distribution and is likely to soon switch to new payloads that are currently detected by fewer antivirus engines.
Security researchers monitoring the botnet are observing that emails carrying malicious payloads last month have increased tenfold.
Emotet is a self-propagating modular trojan that can maintain persistence on the host. It is used for stealing user data, performing network reconnaissance, moving laterally, or dropping additional payloads such as Cobalt Strike and ransomware in particular.
It has been spotted growing slowly but steadily since the beginning of the year, but its operators may be shifting up a gear now.
Spike in distribution
According to a report Kaspersky released today, Emotet activity is seeing a sharp rise from February to March, going from 3,000 to 30,000 emails.
The languages used in these messages include English, French, Hungarian, Italian, Norwegian, Polish, Russian, Slovenian, Spanish, and Chinese.
As for the themes, Emotet distributors are known for changing the topics regularly to take advantage of seasonal interest swifts. This time it’s the Easter celebration they're taking advantage of.
Check Point also released a report, which ranked Emotet as the number one most prevalent and active malware in March 2022.

​
Emotet email using Easter lures on many languages(Check Point)

Kaspersky mentions that the ongoing Emotet email distribution campaigns also employ discussion thread hijacking tricks, seen in Qbot campaigns linked to the same operators.

“Cybercriminals intercept already existing correspondence and send the recipients an email containing a file or link, which often leads to a legitimate popular cloud-hosting service,” Kaspersky

“The aim of the email is to convince users to either (i) follow the link and download an archived document and open it – sometimes using a password mentioned in the email, or (ii) simply open an email attachment,” the researchers note.
Because the threat actors have access to previous correspondence, it is reasonably easy for them to present the attachment as something the recipient would expect as a continuation of the discussion with colleagues.
Switch to 64-bit
The Cryptolaemus security research group, who is keeping a sharp eye on Emotet botnet activity, said that the malware operators have also switched to 64-bit loaders and stealer modules on Epoch 4, one of subgroups of the botnet that run on separate infrastructure. Previously, it relied on 32-bit code.
#Emotet Update - Looks like Ivan laid an egg for easter and has been busy. As of about 14:00UTC today 2022/04/18 - Emotet on Epoch 4 has switched over to using 64-bit loaders and stealer modules. Previously everything was 32-bit except for occasional loader shenanigans. 1/x— Cryptolaemus (@Cryptolaemus1) April 19, 2022
The switch is not visible on Epoch 5 but the delay is expected, since Epoch 4 typically serves as a development test-bed for the Emotet operators, researchers from Cryptolaemus say.
Already, the detection rate for Epoch 4 has dropped by 60%, which is believed to be a direct result of this change.

Related Articles:
New Qbot malware variant uses fake Adobe installer popup for evasionNo, 3 million electric toothbrushes were not used in a DDoS attackPurpleFox malware infects thousands of computers in UkraineMicrosoft Teams phishing pushes DarkGate malware via group chatsBigpanzi botnet infects 170,000 Android TV boxes with malware











Botnet
Email
Emotet
Malware
Phishing
Trojan
























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











