# Reference for threat actor for "Pinchy Spider, Gold Southfield"

**Title**: REvil / Sodinokibi: The Crown Prince of Ransomware

**Source**: https://www.cybereason.com/blog/the-sodinokibi-ransomware-attack

## Content






REvil / Sodinokibi: The Crown Prince of Ransomware











































































Back to Cybereason.com









All Posts
Research
Podcasts
Webinars
Resources
Videos
News


Subscribe






















Subscribe




All
Research
Podcasts
Webinars
Resources
Videos
News







Search


Subscribe






 
            X
        




Search



























REvil / Sodinokibi: The Crown Prince of Ransomware


Written By
Cybereason Nocturnus







Research By: Tom Fakterman




What is Sodinokibi RANSOMWARE?
In April of 2019, the Cybereason Nocturnus team encountered and analyzed a new type of ransomware dubbed REvil/Sodinokibi. REvil/Sodinokibi is highly evasive, and takes many measures to prevent its detection by antivirus and other means.
The authors of REvil/Sodinokibi have previously been connected to the same authors of the prolific GandCrab ransomware, which was recently retired. GandCrab is responsible for 40% of all ransomware infections globally. If the association is accurate, GandCrab sets a good example for just how impactful REvil/Sodinokibi may become.
Ransomware remains a huge business risk to organizations in many vectors. Highly evasive ransomware such as REvil/Sodinokibi and GandCrab are the cause of huge damage to organizations each year.
In this report we analyze the attack and malware, and offer security recommendations for defenders to consider when coming up against this attack.
WHO IS BEHIND SODINOKIBI?
Initially, most of the REvil / Sodinokibi attacks were observed in Asia. Although recently Europe became one of the significant affected regions.
When the ransomware first emerged, it exploited vulnerabilities in servers and other critical assets of SMBs. As time went by, we saw other infection vectors such as phishing and exploit kits.
During our investigation, we also encountered several instances where the REvil / Sodinokibi ransomware purposefully searches for an AV made by the  South Korean security vendor "Ahnlab" in the infected machine in order to inject its malicious payload to the trusted AV vendor.
There is evidence presented in this research and by previous vendors that suggests that the REvil / Sodinokibi ransomware was created by the same group as the prolific GandCrab ransomware.
Security Recommendations
Do not download files from suspicious sources or click on suspicious links.
Make regular backups of important files, both locally and externally in the cloud.
Enable PowerShell prevention in the Cybereason solution.
Activate Cybereason anti-ransomware in Prevention mode to detect and prevent this threat and other, similar threats.
Table of Contents
Introduction
Analysis of the Attack
Loader Phase One: The UAC Bypass
Loader Phase Two: Injection to Ahnlab
The Sodinokibi Payload
Conclusion
MITRE ATT&CK Technique Breakdown
Indicators of Compromise

Introduction
In April of 2019, the Cybereason Nocturnus team encountered several instances where REvil / Sodinokibi was dropped to the target machine via a malicious link as a zip file containing malicious JavaScript.
Though the Cybereason solution prevented the ransomware, we have seen it successfully execute in other organizations. It is able to completely incapacitate a business by preventing the access of data and critical assets of a target machine, among other damage. As of now, the malware does not have the capability to self-propagate, but once that is implemented, it could extend its impact across a network.
When first discovered in late April, REvil / Sodinokibi (AKA Sodin) was reported as being installed on machines by exploiting an Oracle WebLogic vulnerability (CVE-2019-2725) and subsequently started propagating through exploit kits and spam. 
In this blog post, we perform a deep technical analysis of the Sodinokibi ransomware, focusing on the ransomware delivery method as well as the defensive mechanisms put in place by the malware authors in order to evade AV detection. 
This malware showcases a resurgence of ransomware we have been tracking in the industry. Though some have reported ransomware attacks decreasing, we are seeing that ransomware is here to stay. In fact, ransomware attack payments have doubled in the second quarter of this year. Organizations need security products that are able to defend against the latest attacks in order to stay on top and detect and prevent successfully.
During our analysis, we have noticed interesting similarities between the GandCrab ransomware, whose operators claimed in June 2019 that they are retiring and discontinuing their operation. Our findings bode well with other reports by other security researchers that also found similarities between the two ransomware.
HOW IS SODINOKIBI DELIVERED?

Analysis of the Attack
The initial infection vector used by the threat actor is a phishing email containing a malicious link. When pressed, the link downloads a supposedly legitimate zip file that is actually malicious. REvil / Sodinokibi zip files have a very low detection rate on VirusTotal, which signals that the majority of antivirus vendors do not flag the initial payload as malicious.
Since the initial REvil / Sodinokibi payload is able to pass undetected, the first layer of defense for many organizations is immediately bypassed:

The REvil / Sodinokibi zip file detection rate on VirusTotal is quite low. 
The zip file contains an obfuscated JavaScript file. When the user double clicks on the JavaScript file, WScript executes it:

WScript executing malicious JavaScript.

The first stage process tree as seen in the Cybereason solution.
The JavaScript file de-obfuscates itself by rearranging characters from a list called eiculwo, which is located in the JavaScript file:

The first half of the obfuscated JavaScript file. 
The variable vhtsxspmssj, located in the JavaScript file, is an obfuscated PowerShell script that will be de-obfuscated by the attackers later on in the attack:

The de-obfuscated JavaScript file.
The JavaScript file de-obfuscates the variable vhtsxspmssj, mentioned earlier as the PowerShell script, and saves it in the directory temp with the name jurhtcbvj.tmp.
Note: We have encountered variants of the malware where the script downloads the secondary payload instead of embedding it within the initial script.
The file jurhtcbvj.tmp is a PowerShell script filled with multiple unnecessary exclamation marks, most likely to further obfuscate itself. The JavaScript file launches a PowerShell command to remove the exclamation marks and execute the PowerShell script:

The contents of the obfuscated PowerShell script jurhtcbvj.tmp.

The command to replace exclamation marks and execute the PowerShell script.
The PowerShell script decodes an additional script that is Base64-encoded and executes it. The decoded script contains a .NET module also encoded with Base64, which is subsequently decoded and loaded into the PowerShell process memory. Once loaded, it executes the function Install1:

The decoded script decrypting and loading module test.dll into memory.
The module test.dll is one of many layers of this delivery process. The function Install1 contains yet another module encoded with Base64. The function decodes the module and loads it into memory:

Base64-encoded module Install1.

Loading the module Install1 into memory.
If the malware was unable to gain high enough privileges, it will attempt a User Access Control bypass.

Loader Phase One: The UAC Bypass
The module loaded into memory functions as a loader for the next phase of the malware. The module uses CheckTokenMembership to confirm the processes’ privileges. If the processes’ privileges are insufficient, it tries to bypass User Access Control (UAC). In order to bypass UAC, the malware writes itself to the registry key Software\Classes\mscfile\shell\open\command\ and launches a new instance of explorer.exe to execute CompMgmtLauncher.exe:

Creating the registry key and launching CompMgmtLauncher.exe.

Explorer.exe is used to launch ComMgmtLauncher.exe.
When CompMgmtLauncher.exe is executed, it executes anything configured in the registry key Software\Classes\mscfile\shell\open\command\. In this instance, it is executing the same PowerShell command executed earlier to replace exclamation marks and execute the PowerShell script, but with higher privileges:

The registry key creation in order to bypass UAC.
The process is now being executed with the highest privileges, and the attack continues:

The process tree after the UAC bypass as seen in the Cybereason solution.
The loader module is loaded into memory and checks again for privileges. This time, it has sufficient privileges and continues the attack. Within the loader module resources is an xor encrypted portable executable.

The xor encrypted PE.
The loader loads the portable executable from the resource into memory, decrypts it in memory using the key 7B, then executes it:

The portable executable in memory before the xor decryption.


The portable executable in memory after the xor decryption.

Loader Phase Two: Injection to Ahnlab
The portable executable in memory is the second loader module that will be used for the final payload. In this phase, the malware attempts to inject the ransomware payload into an Ahnlab antivirus process.
In order to do so, the second loader checks to see if Ahnlab antivirus is installed on the target machine. If the Ahnlab V3 Lite software service V3 Service exists, it checks if the file autoup.exe is available. autoup.exe is part of the Ahnlab Updater and is vulnerable to attack.
The GandCrab authors have been reported to be bitter with Ahnlab. Given this, it is interesting to note that REvil / Sodinokibi specifically searches for Ahnlab and attempts to use it for the attack:

The malware checking for the Ahnlab antivirus.

The path string for autoup.exe.
If the malware is able to find the Ahnlab service and executable, the loader automatically launches the autoup.exe process in a suspended state and attempts to inject the REvil / Sodinokibi payload into it via process hollowing.
If the Ahnlab antivirus is not installed on the machine, the loader will launch a separate instance of the current PowerShell process in a suspended state and try to inject the REvil / Sodinokibi payload into it via process hollowing.
The payload is stored in the module resources as an xor-encrypted portable executable with key 7B:

The xor encrypted portable executable.

The Sodinokibi Payload
The malware stores encrypted configuration data with RC4 encryption in the .grrr. The name differs among various malware variants:

The sections of the REvil/Sodinokibi payload.
The configuration file contains information about which folders, files, and file extensions to exclude from encrypting. It also contains information on which processes to kill, which services to delete, how to escalate privileges with CVE-2018-8453, how to communicate with C2s, and ransom note to display:

The configuration file for REvil / Sodinokibi.
REvil / Sodinokibi identifies which keyboard languages are configured using GetKeyboardLayoutList. It checks the primary language ID with a switch case. If one of the chosen languages is configured, the malware shuts down. The malware authors do not want to ransom files from the specific set of countries seen in the switch case below.
In this REvil / Sodinokibi variant, a check for Syrian was added, along with new checks for the system language using GetSystemDefaultUILanguage and GetUserDefaultUILanguage:

The switch case for the primary language ID.
Once the language checks pass, the malware continues its execution. It deletes shadow copies from the machine with vssadmin.exe to make file recovery more difficult:

Shadow copy deletion with vssadmin.exe.
The ransomware iterates through all folders on the machine, encrypts all files, and drops a ransom note in each folder. Once it has finished encryption, it changes the desktop wallpaper to help inform the user of the attack:

The new wallpaper after the ransomware encrypts the files. 

The ransom note for the ransomware.
After the malware encrypts the files on the target machine, it tries to establish communication with a C2 server. In order to generate the URL for the C2, it iterates through a list of domains configured in the previously decoded configuration file:

The domain list from the configuration file. 
The malware creates several random URLs using the domains with a combination of hard-coded and randomly generated strings. A recent report by Tesorion covers the similarities in the way REvil / Sodinokibi and GandCrab generate random URLs, which further strengthens suspicions of a potential shared author:
The hard-coded strings for random URL generation.
Once the URLs are generated, the malware sends encrypted machine information to each of the domains including usernames, machine name, domain name, machine language, operating system type, and CPU architecture:

The data sent to the C2 server before encryption.
When the user clicks on the ransom note and enters the key, a page appears that lists the price they must pay in bitcoin to retrieve their files:

The Tor browser ransom note.
The Cybereason anti-ransomware solution identified the threat and mitigated the incident before any damage was caused:

The Cybereason anti-ransomware solution detects and prevents the REvil/Sodinokibi ransomware. 

Conclusion
In this blog, we took a deep dive into the REvil / Sodinokibi ransomware infection process, and showed that even though the obfuscation techniques used by the ransomware authors are quite simple,  they are still proving to be very effective in bypassing most antivirus vendors.
Our analysis further supports the suspicion that the threat actors behind the REvil / Sodinokibi ransomware are the same allegedly retired authors who created the GandCrab ransomware, based on findings detailed in this report, such as: similarities in the language and countries whitelist (Russian-speaking countries and even Syrian Arabic), the “revengeful” targeting of an Ahnlab product for process injection,  and the similarities in the URL-generation routine. 
Since April 2019, the REvil / Sodinokibi ransomware has become very prolific and has become the 4th most common ransomware within less than 4 months after its first appearance. It has since gone through several minor updates, and it is our assessment that its industrious authors will continue to develop the ransomware, adding more features and improving its evasive capabilities. 

MITRE ATT&CK TECHNIQUES BREAKDOWN




Initial Access


Execution


Privilege Escalation


Defense Evasion


Impact




Spearphishing Link


Command-Line Interface


Access Token Manipulation


Deobfuscate/Decode Files or Information


Data Encrypted for Impact




Spearphishing Attachment


Execution through Module Load


Bypass User Account Control


Disabling Security Tools


Inhibit System Recovery




Exploit Public-Facing Application


PowerShell


Exploitation for Privilege Escalation


Process Hollowing

 


 

User Execution

 
 
 


 

Scripting

 
 
 




Indicators of Compromise
Java Script 
MD5 - 3e974b7347d347ae31c1b11c05a667e2
SHA1 - 2cc597d6bffda9ef6b42fed84f7a20f6f52c4756
 
Jurhrtcbvj.tmp
MD5 - e402d34e8d0f14037769294a15060508
SHA1 - b751d0d722d3c602bcc33be1d62b1ba2b0910e03
 
Test.dll
MD5 - 8ea320dff9ef835269c0355ca6850b33
SHA1 - f9df190a616653e2e1869d82abd4f212320e9f4b
 
sodinokibi_loader_1.dll
MD5 - 7d4c2211f3279201599f9138d6b61162
SHA1 - ee410f1d10edc70f8de3b27907fc10fa341f620a
 
sodinokibi_loader_2.dll
MD5 - 613dc98a6cf34b20528183fbcc78a8ee
SHA1 - 5cd8eadcd70b89f6963cbd852c056195a17d0ce2
 
sodinokibi_payload.exe
MD5 - b488bdeeaeda94a273e4746db0082841
SHA1 - 5dac89d5ecc2794b3fc084416a78c965c2be0d2a




Share



















About the Author
Cybereason Nocturnus






The Cybereason Nocturnus Team has brought the world’s brightest minds from the military, government intelligence, and enterprise security to uncover emerging threats across the globe. They specialize in analyzing new attack methodologies, reverse-engineering malware, and exposing unknown system vulnerabilities. The Cybereason Nocturnus Team was the first to release a vaccination for the 2017 NotPetya and Bad Rabbit cyberattacks.
All Posts by Cybereason Nocturnus











Related Posts




PowerLess Trojan: Iranian APT Phosphorus Adds New PowerShell Backdoor for Espionage
Cybereason discovered a new toolset developed by Iranian APT Phosphorus which revealed a connection to Memento ransomware and includes the newly discovered PowerLess Backdoor that evades detection by running PowerShell in a .NET context...





Cybereason vs. Lorenz Ransomware
Prior to the deployment of the Lorenz ransomware, the attackers attempt to infiltrate and move laterally throughout the organization, carrying out a fully-developed RansomOps attack - the Cybereason XDR Platform fully detects and prevents the Lorenz ransomware...




















Subscribe
Never miss a blog.



Recent Posts


From Cracked to Hacked: Malware Spread via YouTube Videos




THREAT ALERT: Ivanti Connect Secure VPN Zero-Day Exploitation




Malicious Life Podcast: SIM Registration: Security, or Surveillance?




Categories

Research
Podcasts
Webinars
Resources
Videos
News

All Posts














Related Posts




PowerLess Trojan: Iranian APT Phosphorus Adds New PowerShell Backdoor for Espionage
Cybereason discovered a new toolset developed by Iranian APT Phosphorus which revealed a connection to Memento ransomware and includes the newly discovered PowerLess Backdoor that evades detection by running PowerShell in a .NET context...





Cybereason vs. Lorenz Ransomware
Prior to the deployment of the Lorenz ransomware, the attackers attempt to infiltrate and move laterally throughout the organization, carrying out a fully-developed RansomOps attack - the Cybereason XDR Platform fully detects and prevents the Lorenz ransomware...














NEWSLETTER
Never miss a blog
Get the latest research, expert insights, and security industry news.
Subscribe












Want to see the Cybereason Defense Platform in action?
Schedule a Demo

X
























About

Who We Are
Careers

Contact



Resources

Blog
Case Studies
Webinars
White Papers



Platform

Overview
Endpoint Protection
EDR
MDR








©Cybereason 2024. All Rights Reserved.



Terms of Use
Privacy Notice
Do Not Sell
Security









































