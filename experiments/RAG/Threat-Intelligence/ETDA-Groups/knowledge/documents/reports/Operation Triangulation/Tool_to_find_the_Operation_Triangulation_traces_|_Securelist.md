# Reference for threat actor for "Operation Triangulation"

**Title**: Tool to find the Operation Triangulation traces | Securelist

**Source**: https://securelist.com/find-the-triangulation-utility/109867/

## Content















Tool to find the Operation Triangulation traces | Securelist



































































Solutions for:

Home Products
Small Business 1-50 employees
Medium Business 51-999 employees
Enterprise 1000+ employees
 



















by Kaspersky


CompanyAccount
Get In Touch
Dark mode off
EnglishRussianSpanish













Solutions



Hybrid Cloud SecurityLearn More
Internet of Things & Embedded SecurityLearn More
Threat Management and DefenseLearn More
Industrial CybersecurityLearn More
Fraud PreventionLearn More



Other solutions
Blockchain Security
Kaspersky for Security Operations Center


Industries



National CybersecurityLearn More
Industrial CybersecurityLearn More
Finance Services CybersecurityLearn More
Healthcare CybersecurityLearn More
Transportation CybersecurityLearn More
Retail CybersecurityLearn More



Other Industries
Telecom Cybersecurity
Blockchain Security
View all


Products



KasperskyEndpoint Security for BusinessLearn More
KasperskyEndpoint Detection and Response (EDR)Learn More
KasperskyEDR OptimumLearn More
KasperskyAnti Targeted Attack PlatformLearn More
KasperskyManaged Detection and ResponseLearn More
KasperskySandboxLearn More



Other Products
Kaspersky Security for Mail Server
Kaspersky Security for Internet Gateway
Kaspersky Embedded Systems Security
Kaspersky Hybrid Cloud Security for AWS
Kaspersky Hybrid Cloud Security for Azure
View All


Services



KasperskyCybersecurity ServicesLearn More
KasperskyAdaptive Online TrainingLearn More
KasperskyPremium SupportLearn More
KasperskyThreat IntelligenceLearn More
KasperskyAPT Intelligence ReportingLearn More
KasperskyTargeted Attack DiscoveryLearn More



Other Services
Kaspersky Professional Services
Kaspersky Incident Response
Kaspersky Cybersecurity Training
Kaspersky Incident Communications
Kaspersky Security Awareness
View All


Resource Center

Case Studies
White Papers
Datasheets
Technologies
MITRE ATT&CK

About Us

Transparency
Corporate News
Press Center
Careers
Innovation Hub
Sponsorship
Policy Blog
Contacts

GDPR
 





Subscribe
 Dark mode off
Login


Securelist menu

EnglishRussianSpanish
Existing Customers

Personal

My Kaspersky
Renew your product
Update your product
Customer support

Business

KSOS portal
Kaspersky Business Hub
Technical Support
Knowledge Base
Renew License


Home

Products
Trials&Update
Resource Center

Business

Small Business (1-50 employees)
Medium Business (51-999 employees)
Enterprise (1000+ employees)


Securelist
Threats

Financial threats
Mobile threats
Web threats
Secure environment (IoT)
Vulnerabilities and exploits
Spam and Phishing
Industrial threats

Categories

APT reports
Incidents
Research
Malware reports
Spam and phishing reports
Publications
Kaspersky Security Bulletin

Archive
All Tags
APT Logbook
Webinars
Statistics
Encyclopedia
Threats descriptions
KSB 2021

About Us

Company
Transparency
Corporate News
Press Center
Careers
Sponsorships
Policy Blog
Contacts

Partners

Find a Partner
Partner Program
















Content menu
Close













Subscribe













by Kaspersky

 Dark mode off




ThreatsThreats

APT (Targeted attacks)
Secure environment (IoT)
Mobile threats
Financial threats
Spam and phishing
Industrial threats
Web threats
Vulnerabilities and exploits


CategoriesCategories

APT reports
Malware descriptions
Security Bulletin
Malware reports
Spam and phishing reports
Security technologies
Research
Publications


Other sections

Archive
All tags
Webinars
APT Logbook
Statistics
Encyclopedia
Threats descriptions
KSB 2023


 











 

Software

In search of the Triangulation: triangle_check utility 

Software

02 Jun 2023

  minute read								
















Table of Contents





How to back up your deviceWindowsmacOSLinuxHow to use our triangle_check utilityThe triangle_check Python packageBinary buildsInterpreting the results 






 

Authors



 Igor Kuznetsov




Valentin Pashkov



 Leonid Bezvershenko



 Georgy Kucherin





In our initial blogpost about “Operation Triangulation”, we published a comprehensive guide on how to manually check iOS device backups for possible indicators of compromise using MVT. This process takes time and requires manual search for several types of indicators. To automate this process, we developed a dedicated utility to scan the backups and run all the checks. For Windows and Linux, this tool can be downloaded as a binary build, and for MacOS it can be simply installed as a Python package.
How to back up your device
Windows
On Windows, the easiest way to do a backup is via iTunes:

Connect your device to a computer that has iTunes installed. Unlock your device and, if needed, confirm that you trust your computer.
Window asking to trust the computer
Your device should now be displayed in iTunes. Right click on it and press “Back Up”.

The created backup will be saved to the %appdata%\Apple Computer\MobileSync\Backup directory.

macOS
If your macOS version is lower than Catalina (10.15), you can create a backup using iTunes, using instructions for Windows. Starting from Catalina, backups can be created through Finder:

Connect your device to the computer and, if needed, confirm that you trust the computer.
Your device should now be displayed in Finder. Select it and then click “Create a backup“.
The created backup will be saved to the ~/Library/Application Support/MobileSync/Backup/ directory.

Linux
To create a backup on Linux, you will need to install the libimobiledevice library. In order to create backups of devices with the latest versions of iOS installed, you will need to compile this library from source code (you can find the build instructions in the Installation/Getting Started section).
After you install the library and connect your device to the computer, you can create a backup using the idevicebackup2 backup --full  command.
During the backup process, you may need to enter your device passcode multiple times.
How to use our triangle_check utility
After you do a backup of your device using the instructions above, you will need to install and launch our triangle_check utility.
The triangle_check Python package
No matter what operating system you have, you can install the triangle_check Python package that we have published to the Python Package Index (PyPi). To do that, you need to have internet access as well as have the pip utility installed.
You can install the utility using two methods:

From PyPI (recommended):
Run the python -m pip install triangle_check command.
Building from Github:
Run the following commands:
git clone https://github.com/KasperskyLab/triangle_check
cd triangle_check
python -m build
python -m pip install dist/triangle_check-1.0-py3-none-any.whl

After installing, you can launch the utility with the following command:
python -m triangle_check path to the created backup.
Binary builds
If you have Windows or Linux, you can also use the binary builds of the triangle_check utility that we have published on GitHub. Follow the instructions below to use it:
Windows

Download the triangle_check_win.zip archive from the GitHub releases page and unpack it.
Launch the command prompt (cmd.exe) or PowerShell.
Change your directory to the one with the unpacked archive (e.g. cd %userprofile%\Downloads\triangle_check_win).
Launch triangle_check.exe, specifying the path to the backup as an argument (e.g. triangle_check.exe "%appdata%\Apple Computer\MobileSync\Backup\00008101-000824411441001E-20230530-143718" ).

Linux

Download the triangle_check_win.zip archive from the GitHub releases page and unpack it.
Launch the terminal.
Change your directory to the one with the unpacked archive (e.g. cd ~/Downloads/triangle_check_linux).
Allow the utility to be executed with the chmod +x triangle_check command.
Launch the utility, specifying the path to the backup as an argument (e.g. ./triangle_check  ~/Desktop/my_backup/00008101-000824411441001E-20230530-143718 ).

Interpreting the results
The utility outputs “DETECTED” when it locates specific indicators of compromise, and that would mean that the device was infected.
Also, it may print out “SUSPICION” that would mean that a combination of less specific indicators points to a likely infection. Finally, if the message displayed is “No traces of compromise were identified“, then the utility did not find any signs of ‘Operation Triangulation’ compromise.






Python
Researchers tools
Triangulation



Authors



 Igor Kuznetsov




Valentin Pashkov



 Leonid Bezvershenko



 Georgy Kucherin





In search of the Triangulation: triangle_check utility 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







u 


							Posted on							June 5, 2023. 9:09 am 



Question about the backup password protection: does the triangulation check work with iphone-backup password protection or do I have to make a backup without password protection?
Reply 








Securelist 


							Posted on							June 6, 2023. 12:28 pm 



Hi U!
The tool works both with unprotected and password-protected backups.
Reply 








Forrai Tibor 


							Posted on							June 6, 2023. 1:50 pm 



It asks you for the iPhone backup’s password on the command line.
Reply 










Klaus 


							Posted on							June 6, 2023. 4:41 am 



Thanks very much!
Reply 








Ivan 


							Posted on							June 8, 2023. 12:29 am 



Y para los que no sabemos hacer nada de esto, como hacemos?
Reply 








Anton 


							Posted on							June 11, 2023. 5:08 pm 



Hello, the tool identified that my iPhone was infected (“DETECTED” result), but the system was successfully updated to the latest IOS (16.5). Does this mean that now my device is clean?
Reply 








Securelist 


							Posted on							June 13, 2023. 11:12 am 



Hi Anton!
We have not observed any indicators of compromise on latest iOS versions. For additional protection against Operation Triangulation, we recommend to disable iMessage, enable Lockdown Mode and reboot device more often/periodically
Reply 








James Pearson 


							Posted on							June 20, 2023. 10:47 am 



Hi Anton – I’m a journalist with the Reuters news agency. We’ve been keen to speak to people whose devices were infected with triangulation. If you’re comfortable doing so, there are secure ways to contact me here: https://pearswick[.]press
Reply 








Christina 


							Posted on							July 1, 2023. 11:58 pm 



Hi Anton,
My device has been affected with this virus as well. There is zero support from Apple on this. It’s very disheartening. The entire Apple support team still downplay the whole scenario and refuse to help me.
Reply 








Kate 


							Posted on							September 5, 2023. 3:52 pm 



I’ve had the same experience. They just deny that it’s even possible. I have zero click malware on all my devices – running current OS and don’t even know how I can have it detected. (I have someone cyberstalking me who’s a hacker). I don’t know what to do or where to go for help..
Reply 








Paul 


							Posted on							December 21, 2023. 7:19 pm 



Still happening iOS 17.3 beta
 has also been for years comes up with an exclamation mark on messages but can’t find what for, check file system I have a modified Var/Hardware and various others

















YONI 


							Posted on							June 23, 2023. 8:21 pm 



It doesn’t work if the backup is encrypted in Windows, it requires a password – you can’t press anything in CMD that asks for a password
Reply 








Alex 


							Posted on							June 29, 2023. 9:10 pm 



C:\triangle_check_win>triangle_check.exe “C:\Users\manol\Apple\MobileSync\Backup\00008030-000C11A02163802E”
Traceback (most recent call last):
  File “triangle_check.py”, line 8, in
  File “triangle_check\__main__.py”, line 29, in main
  File “triangle_check\__init__.py”, line 133, in scan_dir
FileNotFoundError: [Errno 2] No such file or directory: ‘C:\\Users\\manol\\Apple\\MobileSync\\Backup\\00008030-000C11A02163802E\\Manifest.plist’
[10304] Failed to execute script ‘triangle_check’ due to unhandled exception!
i dont know how to do that can you help me please?
Backup route:
C:\Users\manol\Apple\MobileSync\Backup\00008030-000C11A02163802E
IS in windows.
thank you
Reply 








Securelist 


							Posted on							July 3, 2023. 9:51 am 



It seems that the path to the backup is wrong. The backup folder must contain a Manifest.plist file.
Reply 








San 


							Posted on							July 16, 2023. 11:20 pm 



Hi, I am receiving the same error as this commentor  but on my Mac for Manifest.plist file. However it is present in my backup folder. So I am not sure why I am also recieving this same error despite having the file present within the folder
Reply 










gugo 


							Posted on							February 3, 2024. 10:59 am 



You have to put the PATH between brackets : python -m triangle_check “PATH”
I’ve had the same error and I think it’s easy to misunderstand the command the way it’s written in the article. You can right click on your backup folder to copy as a file path and it will paste it directly between brackets
Reply 










Julie 


							Posted on							July 6, 2023. 1:57 pm 



Can you help me I have a iPhone iOS16.5 12
Reply 








San 


							Posted on							July 14, 2023. 7:48 pm 



I strongly I am a target of this attack due to strange activities that have happened on my device from past 2 months. I am not well versed with python, so can you please make a video tutorial on how to download and use this script?
Reply 








T 


							Posted on							September 9, 2023. 12:49 pm 



Nice tool!
Is there a version for full extracted filesystems available?
Reply 








Mike 


							Posted on							October 8, 2023. 7:35 pm 



Unfortunately, the instructions are not very readable. The program doesn’t open for me. Wasn’t it possible to make a graphical version of the program? How about recording a video on how to run the program?
Reply 








Securelist 


							Posted on							October 10, 2023. 1:59 pm 



Hi Mike!
Unfortunately, there’re no such plans right now. If you post here what precisely you have done to open the program, our experts may suggest what can be done to fix the issue.
If one day a more user-friendly version of the utility or instructions to it is out, we’ll inform you about it.
Reply 





















Table of Contents





How to back up your deviceWindowsmacOSLinuxHow to use our triangle_check utilityThe triangle_check Python packageBinary buildsInterpreting the results 





GReAT webinars






																		13 May 2021, 1:00pm								
GReAT Ideas. Balalaika Edition 





Boris Larin



Denis Legezo










																		26 Feb 2021, 12:00pm								
GReAT Ideas. Green Tea Edition 





John Hultquist



Brian Bartholomew



Suguru Ishimaru



Vitaly Kamluk



Seongsu Park



Yusuke Niwa



Motohiko Sato










																		17 Jun 2020, 1:00pm								
GReAT Ideas. Powered by SAS: malware attribution and next-gen IoT honeypots 





Marco Preuss



Denis Legezo



Costin Raiu



Kurt Baumgartner



Dan Demeter



Yaroslav Shmelev










																		26 Aug 2020, 2:00pm								
GReAT Ideas. Powered by SAS: threat actors advance on new fronts 





Ivan Kwiatkowski



Maher Yamout



Noushin Shabab



Pierre Delcher



Félix Aime



Giampaolo Dedola



Santiago Pontiroli










																		22 Jul 2020, 2:00pm								
GReAT Ideas. Powered by SAS: threat hunting and new techniques 





Dmitry Bestuzhev



Costin Raiu



Pierre Delcher



Brian Bartholomew



Boris Larin



Ariel Jungheit



Fabio Assolini












From the same authors




 


How to catch a wild triangle 






 


The outstanding stealth of Operation Triangulation 






 


Free Download Manager backdoored – a possible supply chain attack on Linux machines 






 


Dissecting TriangleDB, a Triangulation spyware implant 






 


Operation Triangulation: iOS devices targeted with previously unknown malware 









Subscribe to our weekly e-mails
The hottest research right in your inbox




Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ








In the same category




 


How to train your Ghidra 






 


OpenTIP, command line edition 






 


Extracting type information from Go binaries 






 


GReAT thoughts: Awesome IDA Pro plugins 






 


Cybersecurity Research During the Coronavirus Outbreak and After 






 















Latest Posts




 



Malware descriptions

Cracked software beats gold: new macOS backdoor stealing cryptowallets 





Sergey Puzan










 



Kaspersky Security Bulletin

Dark web threats and dark market predictions for 2024 





Sergey Lozhkin



Anna Pavlovskaya



Kaspersky Security Services










 



Research

A lightweight method to detect potential iOS malware 





Maher Yamout










 



Research

Operation Triangulation: The last (hardware) mystery 





Boris Larin












Latest Webinars





 




Technologies and services



												11 Dec 2023, 4:00pm					
60 min

The Future of AI in cybersecurity: what to expect in 2024






Vladimir Dashchenko



Victor Sergeev



Vladislav Tushkanov



Dennis Kipker











 




Threat intelligence and IR



												30 Nov 2023, 4:00pm					
70 min

Responding to a data breach: a step-by-step guide






Anna Pavlovskaya











 




Cyberthreat talks



												14 Nov 2023, 4:00pm					
60 min

2024 Advanced persistent threat predictions






Igor Kuznetsov



David Emm



Marc Rivero



Dan Demeter



Sherif Magdy











 




Cyberthreat talks



												09 Nov 2023, 5:00pm					
60 min

Overview of modern car compromise techniques and methods of protection






Alexander Kozlov



Sergey Anufrienko












Reports







HrServ – Previously unknown web shell used in APT attack 

In this report Kaspersky researchers provide an analysis of the previously unknown HrServ web shell, which exhibits both APT and crimeware features and has likely been active since 2021.








Modern Asian APT groups’ tactics, techniques and procedures (TTPs) 

Asian APT groups target various organizations from a multitude of regions and industries. We created this report to provide the cybersecurity community with the best-prepared intelligence data to effectively counteract Asian APT groups.








A cascade of compromise: unveiling Lazarus’ new campaign 

We unveil a Lazarus campaign exploiting security company products and examine its intricate connections with other campaigns








How to catch a wild triangle 

How Kaspersky researchers obtained all stages of the Operation Triangulation campaign targeting iPhones and iPads, including zero-day exploits, validators, TriangleDB implant and additional modules.








 









Subscribe to our weekly e-mails
The hottest research right in your inbox





Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe











Δ








 











ThreatsThreats

APT (Targeted attacks)
Secure environment (IoT)
Mobile threats
Financial threats
Spam and phishing
Industrial threats
Web threats
Vulnerabilities and exploits


CategoriesCategories

APT reports
Malware descriptions
Security Bulletin
Malware reports
Spam and phishing reports
Security technologies
Research
Publications


Other sections

Archive
All tags
Webinars
APT Logbook
Statistics
Encyclopedia
Threats descriptions
KSB 2023


 









© 2024 AO Kaspersky Lab. All Rights Reserved.
Registered trademarks and service marks are the property of their respective owners.



Privacy Policy
License Agreement
Cookies












Subscribe to our weekly e-mails
The hottest research right in your inbox



Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ



























