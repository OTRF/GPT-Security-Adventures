# Reference for threat actor for "Sofacy, APT 28, Fancy Bear, Sednit"

**Title**: Hackers use fake ‘Windows Update’ guides to target Ukrainian govt

**Source**: https://www.bleepingcomputer.com/news/security/hackers-use-fake-windows-update-guides-to-target-ukrainian-govt/

## Content






















Hackers use fake ‘Windows Update’ guides to target Ukrainian govt
































































































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




























HomeNewsSecurityHackers use fake ‘Windows Update’ guides to target Ukrainian govt







 















Hackers use fake ‘Windows Update’ guides to target Ukrainian govt


By Bill Toulas




April 30, 2023
10:07 AM
0





The Computer Emergency Response Team of Ukraine (CERT-UA) says Russian hackers are targeting various government bodies in the country with malicious emails supposedly containing instructions on how to update Windows as a defense against cyber attacks.
CERT-UA believes that the Russian state-sponsored hacking group APT28 (aka Fancy Bear) sent these emails and impersonated system administrators of the targeted government entities to make it easier to trick their targets.
For this purpose, the attackers created @outlook.com email addresses using real employee names acquired via unknown means in the preparatory stages of the attack.
Instead of legitimate instructions on upgrading Windows systems, the malicious emails advise the recipients to run a PowerShell command.
This command downloads a PowerShell script on the computer, simulating a Windows updating process while downloading a second PowerShell payload in the background.
The second-stage payload is a basic information harvesting tool that abuses the 'tasklist' and 'systeminfo' commands to gather data and send them to a Mocky service API via an HTTP request.
Mocky is a legitimate application that helps users generate custom HTTP responses, which APT28 abused in this case for data exfiltration.
CERT-UA recommends that system administrators restrict the ability to launch PowerShell on critical computers and monitor network traffic for connections to the Mocky service API.

Instructions sent to targets (CERT-UA)
APT28 attacks on Ukraine
Google's Threat Analysis Group reported recently that roughly 60% of all phishing emails targeting Ukraine in the first quarter of 2023 originated from Russian threat actors, highlighting APT28 as a major contributor to this malicious activity.
Earlier in the month, US and UK intelligence services and Cisco warned about APT28 actively exploiting a zero-day flaw affecting the company's routers to deploy a malware named 'Jaguar Tooth' to collect intelligence from US and EU-based targets.
In March 2023, Microsoft patched an Outlook zero-day vulnerability tracked as CVE-2023-23397, which APT28 has exploited since April 2022 to breach the networks of European government, military, energy, and transportation organizations.
Interestingly, Chinese hackers also used Windows updates as a lure to drop malicious executables in attacks against Russian government agencies last year.

Related Articles:
Russian military hackers target Ukraine with new MASEPIE malwareMicrosoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flawsUkraine: Hack wiped 2 petabytes of data from Russian research centerWindows 10 KB5034203 preview update adds EU DMA complianceGoogle: Russian FSB hackers deploy new Spica backdoor malware











APT28
Government
Phishing
Russia
Ukraine
Windows
Windows Update
























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











