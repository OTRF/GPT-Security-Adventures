# Reference for threat actor for "ALPHV, BlackCat Gang"

**Title**: Lockbit, Hive, and BlackCat attack automotive supplier in triple ransomware attack – Sophos News

**Source**: https://news.sophos.com/en-us/2022/08/10/lockbit-hive-and-blackcat-attack-automotive-supplier-in-triple-ransomware-attack/

## Content





















Lockbit, Hive, and BlackCat attack automotive supplier in triple ransomware attack – Sophos News

























































Skip to content




















								Search							







Products & Services
Security Operations
Threat Research
AI Research
Naked Security
Sophos Life
 





Search













Open main menu




















Search








Products & Services
Security Operations
Threat Research
AI Research
Naked Security
Sophos Life
 









 








Lockbit, Hive, and BlackCat attack automotive supplier in triple ransomware attack

						After gaining access via RDP, all three threat actors encrypted files, in an investigation complicated by event log clearing and backups. 3 attackers, 2 weeks – 1 entry point.					


		Written by 				
Linda Smith,				

Rajat Wason,				

Syed Zaidi 



August 10, 2022 

Security Operations BlackCat featured Hive Lockbit Ransomware Sophos X-Ops 





In May 2022, an automotive supplier was hit with three separate ransomware attacks. All three threat actors abused the same misconfiguration – a firewall rule exposing Remote Desktop Protocol (RDP) on a management server – but used different ransomware strains and tactics.
The first ransomware group, identified as Lockbit, exfiltrated data to the Mega cloud storage service, used Mimikatz to extract passwords, and distributed their ransomware binary using PsExec.
The second group, identified as Hive, used RDP to move laterally, before dropping their ransomware just two hours after the Lockbit threat actor.
As the victim restored data from backups, an ALPHV/BlackCat affiliate accessed the network, installed Atera Agent (a legitimate remote access tool) to establish persistence, and exfiltrated data. Two weeks after the Lockbit and Hive attacks, the threat actor distributed their ransomware, and cleared Windows Event Logs. Sophos’ Rapid Response (RR) team investigated, and found several files which had been encrypted multiple times – as many as five in some instances.
Figure 1: Files which had been encrypted five times – twice each by Lockbit and Hive, and once by ALPHV/BlackCat

Figure 2: The multi-attacker timeline discovered by Sophos X-Ops
We’ve covered several dual ransomware attacks before – and recently investigated the phenomenon of multiple attacks more generally, as it’s something which appears to be increasingly common – but this is the first incident we’ve seen where three separate ransomware actors used the same point of entry to attack a single organization.
Locks, bees, and cats: The perfect storm

Figure 3: A brief overview of the three ransomware groups that consecutively attacked one organization
While the attacks took place in May, we discovered that a threat actor established an RDP session on the organization’s domain controller, way back in December 2021. This might have been an initial access broker (IAB) – an attacker who finds vulnerable systems and sells access to them on criminal marketplaces – or an early scouting mission by one of the three threat actors.
Either way, in mid-April 2022, a Lockbit affiliate gained RDP access to the organization’s corporate environment through an exposed management server.
Next, the threat actor moved laterally to a domain controller and other hosts, and began exfiltrating data to the Mega cloud storage service, as well as executing two PowerShell scripts: sharefinder.ps1 (to gather information about connected domain network shares) and invoke-mimikatz.ps1 (to extract passwords from LSASS, the Local Security Authority Subsystem Service).
On May 1st, the Lockbit affiliate created two batch scripts (1.bat and 2.bat) to distribute the ransomware binaries LockBit_AF51C0A7004B80EA.exe and Locker.exe across the network, via PsExec.
Figure 4: 1.bat script

Figure 5: 2.bat script
Upon execution, the ransomware encrypted files on nineteen hosts and dropped ransom notes entitled Restore-My-Files.txt.

Figure 6: The Lockbit ransom note
Two hours later, while the Lockbit threat actor was still encrypting files, a Hive ransomware affiliate gained access to the network via the same exposed RDP server and used RDP to move laterally to other hosts.
Hive used legitimate software (PDQ Deploy) already installed on the network to distribute its ransomware binary windows_x32_encrypt.exe. This tactic, known as ‘living off the land’, is popular among threat actors – particularly ransomware actors – as it has a small footprint and is less likely to be detected than downloading malicious tools.
Hive’s ransomware binary encrypted files on sixteen hosts and dropped a further ransom note, HOW_TO_DECRYPT.txt, on impacted devices.

Figure 7: The Hive ransom note
At this point, the organization’s IT team restored most of the infected systems to April 30, the day before the Lockbit threat actor began to encrypt files. From an investigative perspective, this meant some crucial evidence was lost. But the attacks were not over yet.
Only a day after that system restore, an ALPHV/BlackCat affiliate arrived, making RDP connections to domain controllers, file servers, application servers, and other hosts – all from the same management server exploited by Lockbit and Hive.
The ALPHV/BlackCat threat actor exfiltrated data to Mega over the course of a week, and established persistence by installing a backdoor: a legitimate remote access tool named Atera Agent. On May 15th – two weeks after the Lockbit and Hive attacks – the ALPHV/BlackCat affiliate used the credentials of a compromised user to drop ransomware binaries fXXX.exe and fXXXX.exe on six hosts, leaving a ransom note titled RECOVER-eprzzxl-FILES.txt in every folder.

Figure 8: The ALPHV/BlackCat ransom note
Based on analysis from SophosLabs researchers, these binaries not only encrypted files but also deleted volume shadow copies and Windows Event logs. This further complicated our subsequent investigation, as the ALPHV/BlackCat actor erased not only logs relating to their attack, but also those relating to the attacks by Lockbit and Hive.
It’s not clear why Lockbit and ALPHV/BlackCat deployed two ransomware binaries, but one possible reason is fault tolerance: If one executable is detected or blocked, or fails to encrypt, the second might act as a back-up.
Key features of the BlackCat ransomware binaries
The two BlackCat ransomware binaries, fXXX.exe and fXXXX.exe, have the following functionality:

Encrypt files and add the extension .eprzzxl
Collect Universally Unique IDs (UUIDs) from the impacted devices:

wmic csproduct get UUID

Enable Remote to Local and Remote to Remote symbolic link evaluations that allow easy access to files and folders in remote locations:

fsutil behavior set SymlinkEvaluation R2L:1
fsutil behavior set SymlinkEvaluation R2R:1

Modify a registry key to allow the maximum number of network requests by remote processes:

reg add HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters /v MaxMpxCt /d 65535 /t REG_DWORD /f

Delete Volume Shadow copies:

vssadmin.exe Delete Shadows /all /quiet

Disable Windows automatic repair on the impacted device

bcdedit /set {default} recoveryenabled No

Clear Windows Event logs

cmd.exe /c for /F \"tokens=*\" %1 in ('wevtutil.exe el') DO wevtutil.exe cl \"%1\"

The aftermath
After the dust had settled, Sophos’ RR team found files that had been encrypted by all three ransomware groups. In fact, as shown in the screenshot below, some files had even been encrypted five times! Because the Hive attack started 2 hours after Lockbit, the Lockbit ransomware was still running – so both groups kept finding files without the extension signifying that they were encrypted.

Figure 9: An example of quintuple-encrypted files
However, despite all three ransomware groups being known for ‘double extortion’ techniques (where, in addition to encrypting files, threat actors threaten to publish the victim’s data if the ransom is not paid), no information was published on any of the groups’ leak sites.
Several things complicated this investigation. The system restoration, BlackCat’s log-wiping, and a lack of DHCP logging all contrived to make piecing together the attacks extremely difficult. Despite these challenges, Sophos’ Rapid Response team was able to gather and analyze the evidence left behind.
When it comes to defense, there are two elements: proactive (following security best practices to minimize the risk of being attacked), and reactive (how to recover quickly and safely if an attack does happen).
On the proactive side, our white paper on multiple attackers includes several learning points and best-practice guidance, including:

Patch and investigate. Keep Windows and other software up to date (and consider setting up some vulnerability alerts, and monitoring in-the-know sources, to get a head start on breaking news about new bugs). This also means double-checking that patches have been installed correctly and are in place for critical systems like internet-facing machines or domain controllers. Patching early is the best way to avoid being compromised in the future – but it doesn’t mean that you haven’t already been attacked. It’s always worth investigating to ensure that your organization wasn’t breached prior to patching. Threat actors may leave backdoors (which may include the installation of legitimate software) or introduce new vulnerabilities, either deliberately or inadvertently, so this is a key thing for responders to look for to reduce the likelihood of a second attack.
Lock down accessible services. Perform scans of your organization’s network from the outside and identify and lock down the ports commonly used by VNC, RDP, or other remote-access tools. If a machine needs to be reachable using a remote management tool, put that tool behind a VPN or zero-trust network access solution that uses MFA as part of its login. It’s also worth remembering that attacks can happen more than once; if an access point remains open, other threat actors are likely to find and exploit it.
Practice segmentation and zero-trust. Separate critical servers from each other and from workstations by putting them into separate VLANs as you work towards a zero-trust network model.
Set and enforce strong passwords and multifactor authentication (MFA). Strong passwords serve as one of the first lines of defense. Passwords should be unique or complex and never re-used. This is easier to do if you provide staff with a password manager that can store their credentials. But even strong passwords can be compromised. Any form of multifactor authentication is better than none for securing access to critical resources such as e-mail, remote management tools, and network assets.
Inventory your assets and accounts. Unprotected and unpatched devices in the network increase risk and create a situation where malicious activities could pass unnoticed. It is vital to have a current inventory of all connected computers and IoT devices. Use network scans and physical checks to locate and catalog them.
Install layered protection to block attackers at as many points as possible. Extend that security to all endpoints that you allow onto your network.

But once threat actors are inside a network, there’s not much that can be done to ‘stop the bleeding’ without having comprehensive Incident Response and remediation plans, and taking immediate action. We’ve written a series of articles called ‘Hindsight security: Actions breach victims wish they had taken sooner’, which includes advice on securing RDP, enforcing MFA, setting up an incident response plan, and more. You can also request a copy of the Sophos Incident Response Guide here.
IOCs
Sophos X-Ops has posted IOCs relating to the Lockbit, Hive, and BlackCat attacks covered in this report on our Github repository.





Share on Facebook







Share on X







Share on LinkedIn





















  



								About the Author							

Linda Smith 

Linda is an incident lead in the Rapid Response team at Sophos, with experience working in digital forensics and incident response projects within police, industry, academia, and government. Before joining Sophos, Linda worked as a detective for a regional police service in a technological crime unit. Linda works as a part-time professor in a cybersecurity analytics college program and is the founder of Codify Zone, a tech-education company where children learn computer science and programming. Linda’s passion for education and security has led her to obtain a bachelor’s degree in computer engineering and 20+ related certifications in infosec and digital forensics.
 


 


  



								About the Author							

Rajat Wason 

Rajat is an incident response analyst at Sophos. He specializes in providing digital forensics and incident response services for customer environments infected with ransomware, crypto miners and unauthorized access. He holds a Master of Information Systems Security and Management degree from Concordia University of Edmonton.
 


 


  



								About the Author							

Syed Zaidi 

Syed Zaidi is a senior analyst with over fifteen years of experience working in DFIR (Digital Forensic and Incident Response), and IT (Information Technology). He holds a bachelor’s and master’s degrees in engineering with an emphasis in computer systems, network security and telecommunications, as well as multiple incident response, digital forensics, and threat hunting-related certifications. He is passionate about security and takes great pride in mentoring like-minded individuals. 
 


 







				Read Similar Articles			











				May 24, 2021			

What to expect when you’ve been hit with Avaddon ransomware 













				May 19, 2021			

What’s New in Sophos EDR 4.0 













				May 19, 2021			

Sophos XDR: Driven by data 






 



Leave a Reply Cancel replyYour email address will not be published. Required fields are marked *Comment * Name 
Email 
Website 
 Save my name, email, and website in this browser for the next time I comment.
 

Δ 





 



		Subscribe to get the latest updates in your inbox.	






			Which categories are you interested in?		










		You’re now subscribed!	











		Change Region		








						América Latina					



						Brasil					



						Deutschland					



						English					



						France					



						Iberia					



						Italia					



						Japan					





Terms



		Privacy
		







					Privacy Notice				



					Cookies				







		Legal
		







					General				



					Modern Slavery Statement				



					Speak Out				







							© 1997 - 2024 Sophos Ltd. All rights reserved						












