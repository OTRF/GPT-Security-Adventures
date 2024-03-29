# Reference for threat actor for "Kimsuky, Velvet Chollima"

**Title**: Distribution of Kimsuky Group's xRAT (Quasar RAT) Confirmed - ASEC BLOG

**Source**: https://asec.ahnlab.com/en/31089/

## Content


















Distribution of Kimsuky Group's xRAT (Quasar RAT) Confirmed - ASEC BLOG





































































 

Malware Information
AhnLab Detection
Statistics
Response Guide
AhnLab
 














Posted By jcleebobgatenet  , February 8, 2022 

Distribution of Kimsuky Group’s xRAT (Quasar RAT) Confirmed 
On January 26th, 2022, the ASEC analysis team has discovered that the Kimsuky group was using the xRAT (Quasar RAT-based open-source RAT) malware.
xRAT Github Address: https://github.com/tidusjar/xRAT
According to the logs collected by AhnLab’s ASD (AhnLab Smart Defense) infrastructure, the attacker installed a variant of Gold Dragon on the first infected PC on January 24th. The basis for assuming that the obtained file is a variant of Gold Dragon is as follows:
Injection method is same as the method used by the original Gold Dragon (behavior of process hollowing on iexplore.exe, svchost.exe,etc.)Feature of terminating AhnLab product’s real-time detection window class (49B46336-BA4D-4905-9824-D282F05F6576)Termination of Daum Cleaner (daumcleaner.exe) process
The attacker installed Gold Dragon through the exclusive installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed in the form of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” in the %temp% path, then executes it via rundll32.exe.
The installed Gold Dragon has 4 export functions.
PerformProcessStartWork
The installer first executes Gold Dragon by giving the “Start” argument. Once the “Start” export function is executed, Gold Dragon copies itself to a certain path and registers the copied DLL to the autorun registry key. The “Perform” export function is given for DLL execution argument.
Figure 1. Path for registry registration and self-copy

It is assumed that the info leaking feature of the variant that was discovered was modularized. The system information acquisition command execution feature that is mainly used by Gold Dragon did not exist in the Gold Dragon variant. This means that additional payloads can be downloaded from the attacker’s server to obtain system information.
cmd.exe /c ipconfig/all >>”%s” & arp -a >>”%s”cmd.exe /c systeminfo >>”%s”cmd.exe /c tasklist >>”%s”
The attacker does not obtain information through system processes, but instead additionally installs xRAT (Filename: cp1093.exe) that allows remote control of the system to the infected PC to perform info-stealing features. Once cp1093.exe is executed, it copies a normal powershell process (powershell_ise.exe) to the “C:\ProgramData\”path and executes xRAT via process hollowing technique.
Figure 2. xRAT malware

The attacker was also meticulous enough to also distribute an additional file (UnInstall_kr5829.co.in.exe) along with xRAT to delete the traces of attack existing in the target PC.
Figure 3. Code related to deletion of traces of infection

AhnLab is constantly monitoring and responding to such APT attacks, and users should refrain from opening attachments from emails from unknown sources and update the security software to the latest version to prevent damage by information leakage.
[IOC]
[Installer]Installer_sk5621.com.co.exe (40b428899db353bb0ea244d95b5b82d9)Alias (Engine Version): Downloader/Win.Akdoor.C4936791 (2022.01.28.02)
[Gold Dragon]glu32.dll (4ea6cee3ecd9bbd2faf3af73059736df)Alias (Engine Version): Backdoor/Win.Akdoor.C4936792 (2022.01.28.02)C&C : https[:]//sk5621.com[.]co
[xRAT]cp1093.exe (070f0390aad17883cc8fad2dc8bc81ba)Alias (Engine Version): Backdoor/Win.XRat.C4936798 (2022.01.28.02)C&C : 45.77.71[.]50:8082
[Uninstaller]UnInstall_kr5829.co.in.exe (b841d27fb7fee74142be38cee917eda5)Alias (Engine Version): Trojan/Win.Akdoor.C4936809 (2022.01.28.02)


Categories:Malware Information 
Tagged as:Gold Dragon,Kimsuky,QuasarRAT,xRAT 




ASEC Weekly Malware Statistics (January 17th, 2022 – January 23rd, 2022) 

Phishing Email Disguised as a Well-Known Korean Web Portal 







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






21 Comments                    









 Inline Feedbacks                    
View all comments











Kimsuki hackers use commodity RATs with custom Gold Dragon malware – Simply Commodities



    2 years ago













[…] “The attacker installed Gold Dragon through the exclusive installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed in the form of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” in the %temp% path, then executes it via rundll32.exe.” – ASEC. […]






-1






Reply













Kimsuki hackers use commodity RATs with custom Gold Dragon malware



    2 years ago













[…] “The attacker installed Gold Dragon through the exclusive installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed in the form of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” in the %temp% path, then executes it via rundll32.exe.” – ASEC. […]






0






Reply













Kimsuki hackers use commodity RATs with custom Gold Dragon malware - Voice of Time Online



    2 years ago













[…] “The attacker put in Gold Dragon via the unique installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed within the type of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” within the %temp% path, then executes it through rundll32.exe.” – ASEC. […]






0






Reply













Kimsuki-Hacker verwenden Standard-RATs mit benutzerdefinierter Gold Dragon-Malware - Gamingsym Germany



    2 years ago













[…] „Der Angreifer hat Gold Dragon über das exklusive Installationsprogramm (installer_sk5621.com.co.exe) installiert. Der Installer lädt Gold Dragon komprimiert in Form einer Gzip-Datei vom Server des Angreifers herunter, dekomprimiert sie als „in[random 4 numbers].tmp“ im %temp%-Pfad und führt es dann über rundll32.exe aus.“ – EINE SEKUNDE. […]






0






Reply













Kimsuki hackers use commodity RATs with custom Gold Dragon malware – Market-Reporter



    2 years ago













[…] “The attacker installed Gold Dragon through the exclusive installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed in the form of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” in the %temp% path, then executes it via rundll32.exe.” – ASEC. […]






0






Reply













Kimsuki hackers use commodity RATs with custom Gold Dragon malware – strideitforward



    2 years ago













[…] “The attacker installed Gold Dragon through the exclusive installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed in the form of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” in the %temp% path, then executes it via rundll32.exe.” – ASEC. […]






0






Reply













Kimsuki hackers use commodity RATs with custom Gold Dragon malware – CyberHon



    2 years ago













[…] “The attacker installed Gold Dragon through the exclusive installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed in the form of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” in the %temp% path, then executes it via rundll32.exe.” – ASEC. […]






0






Reply













Kimsuki-Hacker verwenden Standard-RATs mit benutzerdefinierter Gold Dragon-Malware • nerds.



    2 years ago













[…] „Der Angreifer hat Gold Dragon über das exklusive Installationsprogramm (installer_sk5621.com.co.exe) installiert. Der Installer lädt Gold Dragon komprimiert in Form einer Gzip-Datei vom Server des Angreifers herunter, dekomprimiert sie als „in[random 4 numbers].tmp“ im %temp%-Pfad und führt es dann über rundll32.exe aus.“ – EINE SEKUNDE. […]






0






Reply













Kimsuki hackers use commodity RATs with custom Gold Dragon malware - Digital News Today



    2 years ago













[…] “The attacker installed Gold Dragon through the exclusive installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed in the form of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” in the %temp% path, then executes it via rundll32.exe.” – ASEC. […]






0






Reply













Kimsuki hackers use commodity RATs with custom Gold Dragon malware - DZTECHNO



    2 years ago













[…] “The attacker installed Gold Dragon through the exclusive installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed in the form of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” in the %temp% path, then executes it via rundll32.exe.” – ASEC. […]






0






Reply













Los piratas informáticos de Kimsuki usan RAT de productos básicos con malware Gold Dragon personalizado – Liukin



    2 years ago













[…] “El atacante instaló Gold Dragon a través del instalador exclusivo (installer_sk5621.com.co.exe). El instalador descarga Gold Dragon comprimido en forma de archivo Gzip del servidor del atacante, lo descomprime como «en[random 4 numbers].tmp” en la ruta %temp%, luego lo ejecuta a través de rundll32.exe”. – UN SEGUNDO. […]






0






Reply













Kimsuki hackers use commodity RATs with custom Gold Dragon malware – Cyber Reports Cybersecurity News & Information



    2 years ago













[…] “The attacker installed Gold Dragon through the exclusive installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed in the form of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” in the %temp% path, then executes it via rundll32.exe.” – ASEC. […]






0






Reply













North Korean hackers deploy popular software to spy on targets: Report | NK News



    2 years ago













[…] Korean cybersecurity firm AhnLabs published the findings in a new report Tuesday, which states that hackers linked to the Pyongyang-backed Kimsuky group began distributing […]






0






Reply













Kimsuki hackers use commodity RATs with custom Gold Dragon malware - Shackle Media



    2 years ago













[…] “The attacker installed Gold Dragon through the exclusive installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed in the form of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” in the %temp% path, then executes it via rundll32.exe.” – ASEC. […]






0






Reply













セキュリティインテリジェンス【2022年2月14日】



    2 years ago













[…] 1．KimsukyグループのxRAT*（Qasar RAT)の配布が確認されました。引用：https://asec.ahnlab.com/en/31089/ […]






0






Reply













Word Document Attack Targeting Companies Specialized in Carbon Emissions - ASEC BLOG



    1 year ago













[…] Distribution of Kimsuky Group’s xRAT (Quasar RAT) Confirmed […]






0






Reply













Deteksi Pintu Belakang Naga Emas: Peretas Kimsuky Menyerang Lagi Menggunakan Malware Naga Emas - hapidzfadli



    1 year ago













[…] peneliti ASEC, Kimsuky menggunakan varian Naga Emas pintu belakang kustom mereka. Ini adalah pintu belakang tahap […]






0






Reply













The Best asec datei New Update - Tratamientorosacea.com



    1 year ago













[…]  + mehr hier sehen  […]






0






Reply













Kimsuki hackers use Remote Access Tools with custom Gold Dragon malware￼ – billycousins.tech



    1 year ago













[…] “The attacker installed Gold Dragon through the exclusive installer (installer_sk5621.com.co.exe). The installer downloads Gold Dragon compressed in the form of a Gzip file from the attacker’s server, decompresses it as “in[random 4 numbers].tmp” in the %temp% path, then executes it via rundll32.exe.” – ASEC. […]






0






Reply













ASEC Weekly Malware Statistics (January 30th, 2023 – February 5th, 2023) - Ciberdefensa



    1 year ago













[…] Distribution of Kimsuky Group’s xRAT (Quasar RAT) Confirmed   Attack Cases of CoinMiners Mining Ethereum Classic Coins […]






0






Reply













ASEC Weekly Malware Statistics (February 27th, 2023 – March 5th, 2023) - ASEC BLOG



    9 months ago













[…] Distribution of Kimsuky Group’s xRAT (Quasar RAT) Confirmed   Attack Cases of CoinMiners Mining Ethereum Classic Coins […]






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



















































































































































































































