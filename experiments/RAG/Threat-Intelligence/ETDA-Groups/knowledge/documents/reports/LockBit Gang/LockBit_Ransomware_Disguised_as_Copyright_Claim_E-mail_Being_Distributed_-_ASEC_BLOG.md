# Reference for threat actor for "LockBit Gang"

**Title**: LockBit Ransomware Disguised as Copyright Claim E-mail Being Distributed - ASEC BLOG

**Source**: https://asec.ahnlab.com/en/35822/

## Content

















LockBit Ransomware Disguised as Copyright Claim E-mail Being Distributed - ASEC BLOG




































































 

Malware Information
AhnLab Detection
Statistics
Response Guide
AhnLab
 














Posted By jcleebobgatenet  , June 24, 2022 

LockBit Ransomware Disguised as Copyright Claim E-mail Being Distributed 
The ASEC analysis team has once again discovered the distribution of LockBit ransomware using phishing e-mail, and disguising itself as copyright claims e-mail which was introduced in the previous blog. The filename of the attachment in e-mail had password included, which is similar to that of phishing e-mail distributed last February (see the link below).
LockBit Ransomware Being Distributed Using Resume and Copyright-related Emails

Figure 1. E-mail details
As shown in Figure 2, the phishing e-mail has a compressed file as an attachment that contains another compressed file inside.

Figure 2. Inside the compressed file
Upon decompressing the file in the compressed file, an executable disguised using a PDF file icon is found.

Figure 3. Executable disguised as a PDF file

As shown in Figure 4, this file is confirmed to be a NSIS File. Looking into the nsi script detail, it decodes the data file ‘162809383’ and performs malicious behaviors through recursions and injections.

Figure 4. Inside the NSIS file


Figure 5. Part of nsi script

This ransomware prevents recovery by deleting volume shadow copy. Furthermore, to make sure the ransomware runs continuously, it registers Run Key to registry and drops LockBit_Ransomware.hta on the desktop to keep it running even after a desktop change or a reboot.
bcdedit /set {default} bootstatuspolicy ignoreallfailuresbcdedit /set {default} recoveryenabled novssadmin delete shadows /all /quietwmic shadowcopy deleteTable 1. Execution command


Figure 6. Registry registered

It then terminates multiple services and processes to avoid detection of file infection behavior and analysis.
wrapper, vmware-converter, vmware-usbarbitator64, MSSQL, MSSQL$, sql and etc.Table 2. Terminated services

winword.exe, QBDBMgr.exe, 360doctor.exe, Adobe Desktop Service.exe, Autorunsc64a.exe, Sysmon.exe, Sysmon64.exe, procexp64a, procexp64a.exe, procmon.exe, procmon64.exe, procmon64a, procmon64a.exe, Raccine_x86, ProcessHacker.exe and etc.Table 3. Terminated processes

The encryption happens after certain services and processes are terminated. If the drive type is DRIVE_REMOVABLE, DRIVE_FIXED, or DRIVE_RAMDISK, it will also be encrypted. Extensions and name of folders or files that are excluded from encryption are as follows:
system volume information, windows photo viewer, windowspowershell, internet explorer, windows security, windows defender, $recycle.bin, Mozilla, msbuild, appdata, windows and etc.Table 4. Folders excluded from encryption

.mp4 .mp3 .reg .ini .idx .cur .drv .sys .ico .lnk .dll .exe .lock .lockbit .sqlite .accdb .lzma .zipx .7z .db and etc.Table 5. Extensions excluded from encryption

Encrypted files have an extension named .lockbit and a certain icon. Also, a ransom note named ‘Restore-My-Files.txt’ is created in the encrypted folder.

Figure 7. Ransom note


Figure 8. When infected by ransomware

As shown above, the distribution of ransomware disguised as copyright-related claims has been continually done in the past. Because emails distributing such malware types may include names of actual illustrators, users may run attached files without realizing it. Hence they should take extreme caution.
[File Detection]
Malware/Gen.Reputation.C4312359
[Behavior Detection]
Malware/MDP.SystemManipulation.M1751

Figure 9. Behavior block

[IOC Info]
3a05e519067bea559491f6347dd6d296 (eml)74a53d9db6b2358d3e5fe3accf0cb738 (exe)
Subscribe to AhnLab’s next-generation threat intelligence platform ‘AhnLab TIP’ to check related IOC and detailed analysis information.


Categories:Malware Information 
Tagged as:Copyright Phishing E-mail,LockBit,NSIS Ransomware,Phishing email,Ransomware 




Windows MSDT Zero-day Vulnerability ‘DogWalk’ Detected by V3 

New Info-stealer Disguised as Crack Being Distributed 







5
2
votes
Article Rating

 





 Subscribe




 Login 




Notify of 


new follow-up comments
new replies to my comments








 







 


Label












{}
[+]

 















Name*





Email





Website






[Important] Consent to Collection and Use of Personal Information


Purpose: Identify the contact information of user who left a comment and respond to inquiries on our blog posts.
Personal Information We Collect: Name of user and organization, Email address
Period of Retention: We store personal information for 3 months. Then, we delete and destroy personal information without delay.

 



I agree to AhnLab’s collection and use of personal information.




















Δ 










 


Label












{}
[+]

 















Name*





Email





Website






[Important] Consent to Collection and Use of Personal Information


Purpose: Identify the contact information of user who left a comment and respond to inquiries on our blog posts.
Personal Information We Collect: Name of user and organization, Email address
Period of Retention: We store personal information for 3 months. Then, we delete and destroy personal information without delay.

 



I agree to AhnLab’s collection and use of personal information.




















Δ 






45 Comments                    









 Inline Feedbacks                    
View all comments











Gefälschte E-Mails zu Urheberrechtsverletzungen installieren LockBit-Ransomware - Nach Welt



    1 year ago













[…] E-Mails, entdeckt von Analysten bei AhnLabKorea, nicht feststellen, welche Dateien unlauter im Text verwendet wurden, und stattdessen den […]






0






Reply













Los correos electrónicos falsos de infracción de derechos de autor instalan el ransomware LockBit - Notiulti



    1 year ago













[…] correos electrónicos, detectados por analistas en AhnLabCorea, no determine qué archivos se usaron injustamente en el cuerpo y, en su lugar, dígale al […]






0






Reply













Fake copyright infringement emails install LockBit ransomware – Cyber Reports Cybersecurity News & Information



    1 year ago













[…] emails, spotted by analysts at AhnLab, Korea, do not determine which files were unfairly used in the body and instead tell the recipient […]






0






Reply













LockBit: Ransomware in emails claiming copyright infringement - California18



    1 year ago













[…] emails were from AhnLab (via bleeding computer) discovers and informs the operator that allegedly copyrighted content is […]






0






Reply













LockBit: Ransomware in emails claiming copyright infringement – Research Snipers



    1 year ago













[…] infringement. Site operators usually have to follow up on such reports. The emails were from AhnLab (through bleeping computer) discovers and informs the operator that alleged copyrighted content is […]






0






Reply













Fake copyright infringement emails install LockBit ransomware - itechnewsonline.com



    1 year ago













[…] emails, spotted by analysts at AhnLab, Korea, do not determine which files were unfairly used in the body and instead tell the recipient […]






0






Reply













Fake copyright infringement emails install LockBit ransomware - Shackle Media



    1 year ago













[…] emails, spotted by analysts at AhnLab, Korea, do not determine which files were unfairly used in the body and instead tell the recipient […]






0






Reply













Pretend Copyright Infringement Emails Set Up LockBit Ransomware - Frayd US



    1 year ago













[…] emails, noticed by analysts at AhnLab, Korea, don’t decide which recordsdata have been unfairly used within the physique and as a […]






0






Reply













Phishing emails for copyright infringement install LockBit ransomware



    1 year ago













[…] emails, spotted by analysts at AhnLab, Korea, do not determine which files were unfairly used in the body and instead tell the recipient […]






0






Reply













Lockbit Ransomware Delivered Through Fake Copyright Claim E-mail - Gadget News Hub



    1 year ago













[…] researchers at South Korean security firm, AhnLab identified the emails, but they were unable to determine which files were being unfairly […]






0






Reply













Hackers Delivered a Lockbit Ransomware Through Fake Copyright Claim E-mail – USA People Search Directory



    1 year ago













[…] researchers at South Korean security firm, AhnLab identified the emails, but they were unable to determine which files were being unfairly […]






0






Reply













Cyber Security Today, June 27, 2022 – A warning to firms using VoIP systems, malicious files in an open source Python registry, and more - thetechnewslite



    1 year ago













[…] ways of tricking victims into clicking on email attachments that hide malware. One of the latest was discovered by researchers at a South Korean firm called ASEC. A victim received an email alleging their firm has violated another company’s copyright. The […]






0






Reply













Lockbit Ransomware Delivered Via Pretend Copyright Declare E-mail - Hostor Infotech %



    1 year ago













[…] researchers at South Korean safety firm, AhnLab recognized the emails, however they have been unable to find out which recordsdata have […]






0






Reply













Fake copyright emails install LockBit ransomware – BleepingComputer – aseelexpress



    1 year ago













[…] spotted by analysts at AhnLabKorea, do not specify which files have been unfairly used in the body and instead tell the recipient […]






0






Reply













Lockbit Ransomware Delivered By means of Pretend Copyright Declare E-mail – Jinsla News | Latest Cybersecurity



    1 year ago













[…] researchers at South Korean safety agency, AhnLab recognized the emails, however they had been unable to find out which recordsdata had been […]






0






Reply













Cyber Security Today, June 27, 2022 – A warning to firms using VoIP systems, malicious files in an open source Python registry, and more - Cloud Defense - Cloud Security



    1 year ago













[…] ways of tricking victims into clicking on email attachments that hide malware. One of the latest was discovered by researchers at a South Korean firm called ASEC. A victim received an email alleging their firm has violated another company’s copyright. The […]






0






Reply













Cyber Security Today, June 27, 2022 – A warning to firms using VoIP systems, malicious files in an open source Python registry, and more - Techmonsterr



    1 year ago













[…] ways of tricking victims into clicking on email attachments that hide malware. One of the latest was discovered by researchers at a South Korean firm called ASEC. A victim received an email alleging their firm has violated another company’s copyright. The […]






0






Reply













LockBit 2.0 ransomware disguised as PDFs distributed in email attacks – Mustafa.net



    1 year ago













[…] Security Emergency Response Center (ASEC) has collected evidence of emails sent to companies with a password-protected compressed file attached, within which lies […]






0






Reply













Fake copyright infringement emails install LockBit ransomware



    1 year ago













[…] emails, spotted by analysts at AhnLab, Korea, do not determine which files were unfairly used in the body and instead tell the recipient […]






0






Reply













Copyright Infringement Emails Contains Virus -



    1 year ago













[…] cyber security analysts at AhnLab were the first to reveal the fake emails launched by the LockBit ransomware hacking group. […]






0






Reply













RH-ISAC | Ongoing Trend of Ransomware Campaigns Using Copyright Claim as Theme - RH-ISAC



    1 year ago













[…] Security Emergency response Center (ASEC) researchers reported the technical details of an ongoing phishing campaign that uses malicious files disguised as copyright claim documents to deliver the LockBit ransomware. […]






0






Reply













This fake copyright scam is infecting PCs with ransomware — what to know - News Bit



    1 year ago













[…] to a blog post (opens in new tab) from the antivirus company AhnLab which first discovered the campaign, the emails themselves […]






0






Reply













Bu sahte telif hakkı dolandırıcılığı, bilgisayarlara fidye yazılımı bulaştırıyor - bilmeniz gerekenler - Dünyadan Güncel Teknoloji Haberleri | Teknomers



    1 year ago













[…] Blog yazısı (yeni sekmede açılır) itibaren antivirüs Kampanyayı ilk keşfeden AhnLab şirketi için, e-postaların kendileri, hangi […]






0






Reply













Lockbit Ransomware Delivered Through Fake Copyright Claim E-mail – Krypto Tech Lens



    1 year ago













[…] researchers at South Korean security firm, AhnLab identified the emails, but they were unable to determine which files were being unfairly […]






0






Reply













This fake copyright scam is infecting PCs with ransomware — what to know — Fight Scams Now



    1 year ago













[…] to a blog post (opens in new tab) from the antivirus company AhnLab which first discovered the campaign, the emails themselves […]






0






Reply













Lockbit Ransomware Delivered By means of Pretend Copyright Declare E-mail – #HashtagNerdBag



    1 year ago













[…] researchers at South Korean security firm, AhnLab identified the emails, but they were unable to determine which files were being unfairly […]






0






Reply













LockBit 3.0 Ransomware Emerges With Bug Bounty Program – Jinsla News | Latest Cybersecurity



    1 year ago













[…] South Korean cybersecurity agency AhnLab reported final week that the LockBit ransomware has been distributed by way of malicious emails claiming to ship copyright claims. […]






0






Reply













LockBit 3.0 Ransomware Emerges With Bug Bounty Program - Firnco



    1 year ago













[…] South Korean cybersecurity firm AhnLab reported last week that the LockBit ransomware has been distributed via malicious emails claiming to deliver copyright claims. […]






0






Reply













LockBit 2.0 ransomware disguised as PDFs distributed in e-mail attacks - Naijal



    1 year ago













[…] Security Emergency Response Center (ASEC) has collected evidence of e-mails sent to companies with a password-protected compressed file attached, within which lies […]






0






Reply













Anomali Cyber Watch: API Hammering Confuses Sandboxes, Pirate Panda Wrote in Nim, Magecart Obfuscates Variable Names, and More - F1TYM1



    1 year ago













[…] Lockbit Ransomware Disguised as Copyright Claim E-mail Being Distributed […]






0






Reply













Anomali Cyber Watch: API Hammering Confuses Sandboxes, Pirate… – Unified Networking



    1 year ago













[…] Lockbit Ransomware Disguised as Copyright Claim E-mail Being Distributed […]






0






Reply













LockBit ransomware ใช้วิธีการใหม่เพื่อให้ผู้ใช้ติดแรนซัมแวร์ โดยการปลอมแปลงอีเมลล์การแจ้งเตือน และการละเมิดลิขสิทธิ์ - Cybertron



    1 year ago













[…] อ้างอิง2: https://asec.ahnlab.com/en/35822/  […]






0






Reply













Fake copyright infringement emails install LockBit ransomware. - Techie Bro.



    1 year ago













[…] emails, spotted by analysts at AhnLab, Korea, do not determine which files were unfairly used in the body and instead tell the recipient […]






0






Reply













Aviso sobre pirataria é na verdade isca para instalação de ransomware - CITIS



    1 year ago













[…] Fonte: AhnLab […]






0






Reply













Raccoon Stealer COMEBACK !! - Cybertron



    1 year ago













[…] อ้างอิง2: https://asec.ahnlab.com/en/35822/  […]






0






Reply













July 1, 2022 - Red N Security



    1 year ago













[…] Fake copyright infringement emails install LockBit ransomware […]






0






Reply













Lockbit Ransomware Delivered Through Fake Copyright Claim E-mail



    1 year ago













[…] researchers at South Korean security firm, AhnLab identified the emails, but they were unable to determine which files were being unfairly […]






0






Reply













Copyright Claim Email is a LockBit Ransomware Phishing Attack in Disguise -



    1 year ago













[…] and before that attempting to install the IceID information-stealing trojan. But according to security researchers at South Korean security vendor AhnLab, it’s LockBit ransomware’s […]






0






Reply













RH-ISAC | LockBit 3.0 Builder Code Leak Technical Analysis - RH-ISAC



    1 year ago













[…] The June 2022 LockBit Campaign […]






0






Reply













NSIS Type of LockBit 3.0 Ransomware Disguised as Job Application Emails Being Distributed - ASEC BLOG



    1 year ago













[…] LockBit Ransomware Disguised as Copyright Claim E-mail Being Distributed (Posted in June 2022) […]






0






Reply













LockBit Ransomware Being Mass-distributed With Similar Filenames - ASEC BLOG



    1 year ago













[…] LockBit Ransomware Disguised as Copyright Claim E-mail Being Distributed (June 2022) […]






0






Reply













LockBit 3.0 Being Distributed via Amadey Bot - ASEC BLOG



    1 year ago













[…] LockBit Ransomware Disguised as Copyright Claim E-mail Being Distributed (Posted in June 2022) […]






0






Reply













After LockBit Pink and LockBit Black, Operators Release LockBit Inexperienced | Cyware Signals - Firnco



    1 year ago













[…] opposite notable variants come with LockBit Linux-ESXi Locker v1.0, LockBit 2.0, and LockBit 3.0 […]






0






Reply













Continuous Distribution of LockBit 2.0 Ransomware Disguised as Resumes - Ciberdefensa



    1 year ago













[…] LockBit Ransomware Disguised as Copyright Claim E-mail Being Distributed […]






0






Reply













Fake copyright infringement emails install LockBit ransomware | wikinesia.net - Wikinesia.net



    11 months ago













[…] tersebut, dilihat oleh analis di AhnLabKorea, jangan menentukan file mana yang digunakan secara tidak adil di badan dan sebagai gantinya […]






0






Reply




 













Archives Archives

Select Month
 February 2024 
 January 2024 
 December 2023 
 November 2023 
 October 2023 
 September 2023 
 August 2023 
 July 2023 
 June 2023 
 May 2023 
 April 2023 
 March 2023 
 February 2023 
 January 2023 
 December 2022 
 November 2022 
 October 2022 
 September 2022 
 August 2022 
 July 2022 
 June 2022 
 May 2022 
 April 2022 
 March 2022 
 February 2022 
 January 2022 
 December 2021 
 November 2021 
 October 2021 
 September 2021 
 August 2021 
 July 2021 
 June 2021 
 May 2021 
 April 2021 
 March 2021 
 February 2021 
 January 2021 
 December 2020 
 November 2020 
 September 2020 
 August 2020 
 July 2020 
 June 2020 
 May 2020 
 April 2020 
 March 2020 
 February 2020 
 December 2019 
 November 2019 
 October 2019 
 September 2019 
 August 2019 
 June 2019 
 May 2019 
 April 2019 
 March 2019 
 February 2019 
 January 2019 
 November 2018 
 July 2018 
 April 2018 
 February 2018 


FOLLOW US


LinkedIn   


X   


RSS Feed   









footer(en) 220, Pangyoyeok-ro, Bundang-gu, Seongnam-si, Gyeonggi-do, Korea | Privacy & Security© AhnLab, Inc. All rights reserved.family site


한국 (한국어)
Global (English)
日本 (日本語)
 




wpDiscuzInsert 









 




















































































Loading Comments...



 


Write a Comment...




Email



Name



Website















































































































































































































































