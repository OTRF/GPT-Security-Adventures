# Reference for threat actor for "Carbanak, Anunak"

**Title**: Linux version of BlackMatter ransomware targets VMware ESXi servers

**Source**: https://www.bleepingcomputer.com/news/security/linux-version-of-blackmatter-ransomware-targets-vmware-esxi-servers/

## Content






















Linux version of BlackMatter ransomware targets VMware ESXi servers
































































































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




























HomeNewsSecurityLinux version of BlackMatter ransomware targets VMware ESXi servers







 















Linux version of BlackMatter ransomware targets VMware ESXi servers


By Lawrence Abrams




August 5, 2021
05:32 PM
0





​The BlackMatter gang has joined the ranks of ransomware operations to develop a Linux encryptor that targets VMware's ESXi virtual machine platform.
The enterprise is increasingly moving to virtual machines for their servers for better resource management and disaster recovery.
With VMware ESXi being the most popular virtual machine platform, almost every enterprise-targeting ransomware operation has begun to release encryptors that specifically target its virtual machines.
BlackMatter targets VMware ESXi
Yesterday, security researcher MalwareHunterTeam found a Linux ELF64 encryptor [VirusTotal] for the BlackMatter ransomware gang that specifically targets VMware ESXi servers based on its functionality.
BlackMatter is a relatively new ransomware operation that started last month and is believed to be a rebrand of DarkSide. After researchers found samples, it was determined that the encryption routines used by the ransomware were the same custom and unique ones used by DarkSide.
DarkSide shut down after attacking and shutting down Colonial Pipeline and then feeling the total pressure of international enforcement and the US government.
From the sample BlackMatter's Linux encryptor shared with BleepingComputer, it is clear that it was designed solely to target VMWare ESXi servers.
Advanced Intel's Vitali Kremez reverse engineered the sample and told BleepingComputer that the threat actors created an 'esxi_utils' library that is used to perform various operations on VMware ESXi servers

/sbin/esxcli
bool app::esxi_utils::get_domain_name(std::vector >&)
bool app::esxi_utils::get_running_vms(std::vector >&)
bool app::esxi_utils::get_process_list(std::vector >&)
bool app::esxi_utils::get_os_version(std::vector >&)
bool app::esxi_utils::get_storage_list(std::vector >&)
std::string app::esxi_utils::get_machine_uuid()
bool app::esxi_utils::stop_firewall()
bool app::esxi_utils::stop_vm(const string&)

Kremez told us that each function would execute a different command using the esxcli command-line management tool, such as listing VMs, stopping the firewall, stopping a VM, and more.
For example, stop_firewall() function will execute the following command:

esxcli network firewall  set --enabled false
While the stop_vm() will execute the following esxcli command:

esxcli vm process kill --type=force --world-id [ID]
All ransomware that targets ESXi servers attempts to shut down virtual machines before encrypting the drives. This is done to prevent data from being corrupted while it is encrypted.
Once all the VMs are shut down, it will encrypt files that match specific file extensions based on the configuration included with the ransomware.
Targeting ESXi servers is very efficient when conducting ransomware attacks, as it allows the threat actors to encrypt numerous servers at once with a single command.
As more businesses move to this type of platform for their servers, we will continue to see ransomware developers focus primarily on Windows machines but also create a dedicated Linux encrypted targeting ESXi.
Emsisoft CTO Fabian Wosar told BleepingComputer that other ransomware operations, such as REvil, HelloKitty, Babuk, RansomExx/Defray, Mespinoza, GoGoogle, have also created Linux encryptors for this purpose.

Related Articles:
MGM casino's ESXi servers allegedly encrypted in ransomware attackLockBit claims ransomware attack on Fulton County, GeorgiaUbuntu 'command-not-found' tool can be abused to spread malwareTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offline











BlackMatter
DarkSide
Encryptor
Linux
Ransomware
Server
Virtual Machine
Vmware ESXi
























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











