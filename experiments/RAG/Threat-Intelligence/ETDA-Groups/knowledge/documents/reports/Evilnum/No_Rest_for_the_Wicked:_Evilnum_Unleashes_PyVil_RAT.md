# Reference for threat actor for "Evilnum"

**Title**: No Rest for the Wicked: Evilnum Unleashes PyVil RAT

**Source**: https://www.cybereason.com/blog/no-rest-for-the-wicked-evilnum-unleashes-pyvil-rat

## Content






No Rest for the Wicked: Evilnum Unleashes PyVil RAT









































































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



























No Rest for the Wicked: Evilnum Unleashes PyVil RAT


Written By
Cybereason Nocturnus







Over the course of the last few months, the Cybereason Nocturnus team has been investigating the activity of the Evilnum group. The group first emerged in 2018, and since then, Evilnum’s activity has been varied, with recent reports using different components written in Javascript and C# as well as tools bought from the Malware-as-a-Service provider Golden Chickens.

The group’s operations appear to be highly targeted, as opposed to a widespread phishing operation, with a focus on the FinTech market by way of abusing the Know Your Customer regulations (KYC), documents with information provided by clients when business is undertaken. Since its first discovery, the group’s mainly targeted different companies across the UK and EU.
In recent weeks, the Nocturnus team has observed new activity by the group, including several notable changes from tactics observed previously. These variations include a change in the chain of infection and persistence, new infrastructure that is expanding over time, and the use of a new Python-scripted Remote Access Trojan (RAT) Nocturnus dubbed PyVil RAT. 
PyVil RAT possesses different functionalities, and enables the attackers to exfiltrate data, perform keylogging and the taking of screenshots, and the deployment of more tools such as LaZagne in order to steal credentials.
In this write-up, we dive into the recent activity of the Evilnum group and explore its new infection chain and tools.

Key Findings

Evilnum: The Cybereason Nocturnus team is tracking the operations of the Evilnum group, which has been active for the past two years, using a variety of tools.
Targeting the Financial Sector: The group is known to target FinTech companies, and is abusing the usage of the Know Your Customer( KYC) procedure in order to start the infection.
New Tricks: In this research, we see a deviation from the infection chain, persistence, infrastructure, and tools observed previously, including:

Modified versions of legitimate executables employed in an attempt to remain undetected by security tools.
Infection chain shift from a JavaScript Trojan with backdoor capabilities to a multi-process delivery procedure of the payload. 
A newly discovered Python-scripted RAT dubbed PyVil RAT that was compiled with py2exe, which has the capability to download new modules to expand functionality. 


table of contents

Key Findings
Overview of the Group
New Infection Chain
Trojanized Program
Functionality
fplayer.exe
PyVil: A New Python RAT
Expanding Infrastructure
Conclusion
Mitre Attack Breakdown
Indicators of Compromise


Overview of the Group
The Evilnum group has been reported to target financial technology companies, mostly located in the UK and other EU countries. The main goal of the group is to spy on its infected targets and steal information such as passwords, documents, browser cookies, email credentials and more.
Aside from the group’s own proprietary tools, Evilnum has been observed deploying Golden Chickens tools in some cases, as reported in the past. Golden Chickens is a Malware-as-a-Service (MaaS) provider that is known to have been used by groups such as FIN6 and Cobalt Group. Among the tools used by the Evilnum group are More_eggs, TerraPreter, TerraStealer, and TerraTV.
The Evilnum group’s activity was first identified in 2018, when they used the first version of their infamous JavaScript Trojan. The script extracts C2 addresses from sites like GitHub, DigitalPoint and Reddit by querying specific pages created for this purpose. This technique enables the attackers to change the C2 address of deployed agents easily while keeping the communications masked as requests are made to legitimate known sites. 
Since then, the group has been mentioned several times, in different attacks, each time upgrading its toolset with new capabilities as well as adding new tools to the group’s arsenal.
The initial infection vector of Evilnum typically begins with spear phishing emails, with the goal of delivering ZIP archives that contain LNK files masquerading as photos of different documents such as driving licenses, credit cards, and utility bills. These documents are likely to be stolen and belong to real individuals.
Once an LNK file is opened, it deploys the JavaScript Trojan, which in turn replaces the LNK file with a real image file, making this whole operation invisible to the user.
Up to this date, as described in this publication, six different iterations of the JavaScript trojan have been observed in the wild, each with small changes that don’t alter the core functionality. The JavaScript agent has functionalities such as upload and download files, steal cookies, collect antivirus information, execute commands and more. 
In addition to the JavaScript component, as described in a previous research, the group has been observed deploying a C# Trojan, that possesses similar functionality to the former JavaScript component.

Previous infection chain

New Infection Chain
In the past, Evilnum’s infection chain started with spear phishing emails, delivering zip archives that contain LNK files masquerading as images. These LNK files will drop a JavaScript Trojan with different backdoor capabilities as described above. 
In recent weeks, we observed a change in this infection procedure: first, instead of delivering four different LNK files in a zip archive that in turn will be replaced by a JPG file, only one file is archived. This LNK file masquerades as a PDF whose content includes several documents, such as utility bills, credit card photos, and Drivers license photos:

LNK file in ZIP
When the LNK file is executed, asin previous versions, a JavaScript file is written to disk and executed, replacing the LNK file with a PDF:

Example KYC documents from the PDF
Unlike previous versions that possessed an array of functionalities, this version of the JavaScript acts mainly as a dropper and lacks any C2 communication capabilities. This JavaScript is the first stage in this new infection chain, culminating with the delivery of the payload, a Python written RAT compiled with py2exe that Nocturnus researchers dubbed PyVil RAT:

Initial infection process tree
In Cybereason, we are able to view the process tree and the extraction of the JavaScript from the LNK file:

Initial infection process tree in Cybereason
The JavaScript is extracted by outputting all lines that contain the string “END2” (commented out in the script) to a file named “0.js” in the temp folder and the LNK is copied to the temp folder as “1.lnk”:

Extraction of the embedded JS script
The JavaScript file is using a similar path to previous versions to drop binaries ("%localappdata%\\Microsoft\\Credentials\\MediaPlayer\\”):

Snippet from JS file
After the script replaces the LNK file with the real PDF, the JS file is copied to “%localappdata%\Microsoft\Credentials\MediaPlayer\VideoManager\media.js” and is executed again.
In this second execution of the script, an executable file named “ddpp.exe” that is embedded inside the LNK file is extracted and saved to "%localappdata%\Microsoft\Credentials\MediaPlayer\ddpp.exe".
Unlike previous versions where the malware used the Run registry key for persistence, in this new version, a scheduled task named “Dolby Selector Task” for ddpp.exe is created instead:

ddpp.exe scheduled task
With this scheduled task, the second stage of retrieving the payload begins:

Downloaders process tree
In Cybereason, we see the attempted credential dump by the payload:

Downloaders process tree in Cybereason

ddpp.exe: Tojanzed Program
The ddpp.exe executable appears to be a version of “Java(™) Web Start Launcher” modified to execute malicious code:

ddpp.exe icon
When comparing the malware executable with the original Oracle executable, we can see the similar metadata between the files. The major difference at first sight, is that the original Oracle executable is signed, while the malware is not:

ddpp.exe file properties 

Original javaws.exe file properties 
According to Intezer engine there is huge amount of shared code between the malware executable and the legitimate Oracle Corporation file:

ddpp.exe code reuse in Intezer 

ddpp.exe Functionality
The ddpp.exe executable functions as a downloader for the next stages of the infection.
It is executed by the scheduled task with three arguments:

The encoded UUID of the infected machine
An encoded list of installed Anti-virus products
The number 0


ddpp.exe scheduled task arguments
When ddpp.exe is executed, it unpacks shellcode:

ddpp.exe passing execution to shellcode
The shellocode connects to the C2 using a GET request, sending in the URI the three parameters received that were described above. In turn, the malware receives back another encrypted executable, which is saved to disk as “fplayer.exe” and is executed using a new scheduled task: 

ddpp.exe C2 communication over HTTP

fplayer.exe
fplayer.exe functions as another downloader. The downloaded payload is then loaded by fplayer.exe to memory and serves as a fileless RAT. The file is saved in “%localappdata%\microsoft\media player\player\fplayer.exe” and is executed with a scheduled task named “Adobe Update Task”: 

fplayer.exe scheduled task
Fplayer.exe is executed with several arguments as well:

The encoded UUID of the infected machine
Three arguments that will be used by the PyVil RAT at a later stage:

“-m”: The name of the scheduled task
“-f”: tells the PyVil RAT to parse the rest of the arguments
“-t”: update the scheduled task



fplayer.exe scheduled task arguments
Similarly to ddpp.exe, fplayer.exe appears to be a modified version of “Stereoscopic 3D driver Installer”:

fplayer.exe icon
In here as well, we can see the similar metadata between the files with the difference being that the original Nvidia  executable is signed, while the malware is not:

fplayer.exe file properties

Original nvStinst.exe file properties 
This time as well, according to Intezer engine there are high percentage of code similarities with Nvidia Corporation:

fplayer.exe code reuse in Intezer 
When fplayer.exe is executed, it also unpacks shellcode:

 fplayer.exe passing execution to shellcode
The shellcode connects to the C2 using a GET request, this time sending in the URI the only the encoded UUID.  fplayer.exe was observed to receive another encrypted executable, which is saved as ‘%localappdata%\Microsoft\Media Player\Player\devAHJE.tmp’:

fplayer.exe C2 communication
The process decrypts the received executable, and maps it to memory, passing it the execution.
The decrypted file is a compiled py2exe executable. py2exe is a Python extension which converts Python scripts into Microsoft Windows executables.

PyVil: A New Python RAT
The Python code inside the py2exe is obfuscated with extra layers, in order to prevent decompilation of the payload using existing tools. Using a memory dump, we were able to extract the first layer of Python code. The first piece of code decodes and decompresses the second layer of Python code:

The first layer of deobfuscation code 
The second layer of Python code decodes and loads to memory the main RAT and the imported libraries:

Snippet from the second layer of code: extraction of Python libraries
The PyVil RAT has several functionalities including:

Keylogger
Running cmd commands
Taking screenshots
Downloading more Python scripts for additional functionality 
Dropping and uploading executables
Opening an SSH shell
Collecting information such as: 

Anti-virus products installed
USB devices connected
Chrome version



PyVil RAT’s Global variables give a clear understanding of the malware’s capabilities:

Global variables showing PyVil RAT's functionality
PyVil RAT has a configuration module that holds the malware’s version, C2 domains, and user agents to use when communicating with the C2:

Configuration module
PyVil RAT’s C2 communications are done via POST HTTP requests and are RC4 encrypted using a hardcoded key encoded with base64:

RC4 key

data exfiltration from the infected machine being sent to the C2
This encrypted data contains a Json of different data collected from the machine and configuration:

One of the decrypted JSONs sent to the C2 




Field


Usage




type


Not clear




xmode


Not clear




req_type


Request type




svc_ver


Malware version in the configuration




ext_ver


A version of an executable the malware may download (-2 means the  executables folder does not exist)




ext_exists


Checks for the existence of a particular executable 




svc_name


Appears to be a name used to identify the malware by the C2.




ext_uuid


Encoded machine UUID




svc_uuid


machine UUID




host


Hostname




uname


User name




ia


Is user admin




wv


Windows version




dt


Current date and time




avs


List of installed anti-virus products




gc


Dictionary of different configuration




sc_secs_min


Minimum sleep time between sending screenshots




sc_secs_max


Maximum sleep time between sending  screenshots




kl_secs_min


Minimum sleep time between sending keylogging data




kl_secs_max


Maximum sleep time between sending keylogging data




kl_run


Is keylogger activated




klr


Is keylogger activated




tc


Is USB connected




cr


Is chrome.exe is running




ct


Type of downloaded  module to run: executable or Python module




cn


Module name corresponding to “ct”




imp


Execute the downloaded module (corresponds with “ct”)




pwds


Extracted passwords




cooks


Cookies information




Fields used in C2 communication
During the analysis of PyVil RAT, on several occasions, the malware received from the C2 a new Python module to execute. This Python module is a custom version of the LaZagne Project which the Evilnum group has used in the past. The script will try to dump passwords and collect cookie information to send to the C2:

Decrypted LaZagne output sent to the C2 

Expanding Infrastructure
In previous campaigns of the group, Evilnum’s tools avoided using domains in communications with the C2, only using IP addresses. In recent weeks, we encountered an interesting trend with Evilnum’s growing infrastructure. 
By tracking Evilnum’s new infrastructure that the group has built in the past few weeks, a trend of expansion can be seen. While the C2 IP address changes every few weeks, the list of domains associated with this IP address keeps growing. A few weeks ago, three domains associated with the malware were resolved to the same IP address:




Domains


Resolved IP




crm-domain[.]net


5.206.227[.]81




telecomwl[.]com




leads-management[.]net




Shortly thereafter, the C2 IP address of all three domains changed. In addition, three new domains were registered with the same IP address and were used by the malware:




Domains


Resolved IP




crm-domain[.]net


185.236.230[.]25




telecomwl[.]com




leads-management[.]net




voipssupport[.]com




voipasst[.]com




voipreq12[.]com




 
A few weeks later, this change occurred again. The resolution address of all domains changed in the span of a few days, with the addition of three new domains:




Domains


Resolved IP




crm-domain[.]net


193.56.28[.]201




telecomwl[.]com




leads-management[.]net




voipssupport[.]com




voipasst[.]com




voipreq12[.]com




telefx[.]net




fxmt4x[.]com




xlmfx[.]com




 

Evilnum’s Infrastructure

Conclusion
In this write-up, we examined a new infection chain by the Evilnum group - threat actors who have started to make a name for themselves. Since the first reports in 2018 through today, the group’s TTPs have evolved with different tools while the group has continued to focus on  FinTech targets. 
The Evilnum group employed different types of tools along its career, including JavaScript and C# Trojans, malware bought from the malware-as-a-service Golden Chickens, and other existing Python tools. With all these different changes, the primary method of gaining initial access to their FinTech targets stayed the same: using fake Know your customer (KYC) documents to trick employees of the finance industry to trigger the malware. 
In recent weeks we observed a significant change in the infection procedure of the group, moving away from the JavaScript backdoor capabilities, instead utilizing it as a first stage dropper for new tools down the line. During the infection stage, Evilnum utilized modified versions of legitimate executables in an attempt to stay stealthy and remain undetected by security tools.
The group deployed a new type of Python RAT that Nocturnus researchers dubbed PyVil RAT which possesses abilities to gather information, take screenshots, keylog data, open an SSH shell and deploy new tools. These tools can be a Python module such as LaZagne or an executable, and thus adding more functionality for the attack as required. This innovation in tactics and tools is what allowed the group to stay under the radar, and we expect to see more in the future as the Evilnum group’s arsenal continues to grow.

Mitre ATT&CK BREAKDOWN




Initial Access


Execution


Persistence


Privilege Escalation


Defense Evasion




Spearphishing Link


User Execution


Scheduled Task


Scheduled Task


Deobfuscate/Decode Files or Information



 

Windows Command Shell

 
 

Masquerading



 

JavaScript/JScript

 
 

Obfuscated Files or Information




 




Credential Access


Discovery


Collection


Command and Control


Exfiltration




Credentials from Password Stores


Process Discovery


Keylogging


Data Encoding


Exfiltration Over C2 Channel




Credentials from Web Browsers


Security Software Discovery


Screen Capture


Ingress Tool Transfer

 



OS Credential Dumping


System Information Discovery

 

Application Layer Protocol

 



Keylogging

 
 

Encrypted Channel

 



Steal Web Session Cookie

 
 
 
 



 

INDICATORS OF COMPROMISE
Click here to download this campaign's IOCs (PDF)
Click here to read the threat alert for PyVil RAT.
 

Tom Fakterman 

 


Tom Fakterman, Cyber Security Analyst with the Cybereason Nocturnus Research Team, specializes in protecting critical networks and incident response. Tom has experience in researching malware, computer forensics and developing scripts and tools for automated cyber investigations.




Share



















About the Author
Cybereason Nocturnus






The Cybereason Nocturnus Team has brought the world’s brightest minds from the military, government intelligence, and enterprise security to uncover emerging threats across the globe. They specialize in analyzing new attack methodologies, reverse-engineering malware, and exposing unknown system vulnerabilities. The Cybereason Nocturnus Team was the first to release a vaccination for the 2017 NotPetya and Bad Rabbit cyberattacks.
All Posts by Cybereason Nocturnus











Related Posts




StrifeWater RAT: Iranian APT Moses Staff Adds New Trojan to Ransomware Operations
Cybereason discovered an undocumented RAT dubbed StrifeWater attributed to Iranian APT Moses Staff who deploy destructive ransomware following network infiltration and the exfiltration of sensitive data...





THREAT ANALYSIS REPORT: From Shathak Emails to the Conti Ransomware
The ITG23 group is partnering with the TA551 (Shatak) threat group to distribute ITG23’s TrickBot and BazarBackdoor malware which attackers use to deploy Conti ransomware on compromised systems...




















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




StrifeWater RAT: Iranian APT Moses Staff Adds New Trojan to Ransomware Operations
Cybereason discovered an undocumented RAT dubbed StrifeWater attributed to Iranian APT Moses Staff who deploy destructive ransomware following network infiltration and the exfiltration of sensitive data...





THREAT ANALYSIS REPORT: From Shathak Emails to the Conti Ransomware
The ITG23 group is partnering with the TA551 (Shatak) threat group to distribute ITG23’s TrickBot and BazarBackdoor malware which attackers use to deploy Conti ransomware on compromised systems...














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









































