# Reference for threat actor for "Wizard Spider, Gold Blackburn"

**Title**: TrickBot teams up with Shatak phishers for Conti ransomware attacks

**Source**: https://www.bleepingcomputer.com/news/security/trickbot-teams-up-with-shatak-phishers-for-conti-ransomware-attacks/

## Content






















TrickBot teams up with Shatak phishers for Conti ransomware attacks
































































































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




























HomeNewsSecurityTrickBot teams up with Shatak phishers for Conti ransomware attacks







 














TrickBot teams up with Shatak phishers for Conti ransomware attacks


By Bill Toulas


November 10, 2021
10:52 AM
0




A threat actor tracked as Shatak (TA551) recently partnered with the ITG23 gang (aka TrickBot and Wizard Spider) to deploy Conti ransomware on targeted systems.
The Shatak operation partners with other malware developers to create phishing campaigns that download and infect victims with malware.
Researchers from IBM X-Force discovered that Shatak and TrickBot began working together in July 2021, with what appears to be good results, as the campaigns have continued until today.
A recent technical analysis from Cybereason provides more details on how the two distinct actors partnered to deliver ransomware attacks.
Attack starts with a phishing email
A typical infection chain starts with a phishing email sent by Shatak, carrying a password-protected archive containing a malicious document.
According to an October report by IBM X-Force, Shatak commonly uses reply-chain emails stolen from previous victims and adds password-protected archive attachments.

Example Shatak phishing emailSource: IBM X-Force
These attachments contain scripts that execute base-64 encoded code to download and install the TrickBot or BazarBackdoor malware from a remote site.
The distribution sites used in the most recent campaign are based in European countries such as Germany, Slovakia, and the Netherlands.

Shatak's infection chainSource: Cybereason
After successfully deploying TrickBot and/or BazarBackdoor, ITG23 takes over by deploying a Cobalt Strike beacon on the compromised system, adding it to the scheduled tasks for persistence.
The Conti actors then use the dropped BazarBackdoor for network reconnaissance, enumerating users, domain admins, shared computers, and shared resources.
Then they steal user credentials, password hashes, and Active Directory data, and abuse what they can to spread laterally through the network.
Some signs of this activity include fiddling with registry values that enable the RDP connectivity and modifying Windows Firewall rules with the 'netsh' command.
Windows Defender's real-time monitoring feature is also disabled to prevent alerts or interventions during the encryption process.
The next step is data exfiltration, which is the final stage before the file encryption, with Conti using the 'Rclone' tool to send everything to a remote endpoint under their control.

Conti disabling Defender's real-time protections.Source: Cybereason
After harvesting all valuable data from the network, the threat actors deploy the ransomware to encrypt devices.
Other potential collaborations
In a recent report from France's Computer Emergency Response Team (CERT), TA551 appears as a collaborator of 'Lockean', a newly discovered ransomware group with multiple affiliations.
In that case, Shatak was sending phishing emails to distribute the Qbot/QakBot banking trojan, which was used for deploying the ProLock, Egregor, and DoppelPaymer ransomware infections.
As such, TA551 may have more collaborations with other ransomware gangs besides those spotted by analysts.
This threat actor is also identified under different names, such as Shathak, UNC2420, and Gold Cabin.
How to protect yourself
The best defense against these types of attacks is to train employees on the risks of phishing emails.
Apart from that, admins should enforce the use of multi-factor authentication on accounts, disable unused RDP services, and regularly monitor the relevant event logs for unusual configuration changes.
Finally, an important safety measure is regularly backing up important data to a secured remote location and then taking those backups offline so they can't be targeted by threat actors.

Related Articles:
New Qbot malware variant uses fake Adobe installer popup for evasionNew RustDoor macOS malware impersonates Visual Studio updateMicrosoft Teams phishing pushes DarkGate malware via group chatsThe Week in Ransomware - January 26th 2024 - Govts strike backRussian TrickBot malware dev sentenced to 64 months in prison








BazarBackdoor
Conti
Malware
Phishing
Ransomware
TrickBot



















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











