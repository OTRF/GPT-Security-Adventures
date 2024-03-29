# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: Lazarus Group Targeting Windows IIS Web Servers - ASEC BLOG

**Source**: https://asec.ahnlab.com/en/53132/

## Content


















Lazarus Group Targeting Windows IIS Web Servers - ASEC BLOG





































































 

Malware Information
AhnLab Detection
Statistics
Response Guide
AhnLab
 














Posted By muhan  , May 23, 2023 

Lazarus Group Targeting Windows IIS Web Servers 
AhnLab Security Emergency response Center (ASEC) has recently confirmed the Lazarus group, a group known to receive support on a national scale, carrying out attacks against Windows IIS web servers. Ordinarily, when threat actors perform a scan and find a web server with a vulnerable version, they use the vulnerability suitable for the version to install a web shell or execute malicious commands. The AhnLab Smart Defense (ASD) log displayed below in Figure 1 shows that Windows server systems are being targeted for attacks, and malicious behaviors are being carried out through w3wp.exe, an IIS web server process. Therefore, it can be assumed that the threat actor uses poorly managed or vulnerable web servers as their initial breach routes before executing their malicious commands later.
The threat actor places a malicious DLL (msvcr100.dll) in the same folder path as a normal application (Wordconv.exe) via the Windows IIS web server process, w3wp.exe. They then execute the normal application to initiate the execution of the malicious DLL. In MITRE ATT&CK, this method of attack is categorized as the DLL side-loading (T1574.002) technique.

Figure 1. Initial infiltration behavior log of the Lazarus group exploiting a poorly managed Windows IIS web server
The Lazarus group’s use of the DLL side-loading technique to run malware has been confirmed many times already. The threat actor has been continuously changing the name of the normal process used in the DLL side-loading technique. This post will cover the DLL side-loading technique used by the threat actor during their initial infiltration process as well as their follow-up behaviors.
1. Initial Infiltration: DLL Side-Loading Using Windows IIS Web Servers (Wordconv.exe, msvcr100.dll)
The threat actor creates Wordconv.exe, msvcr100.dll, and msvcr100.dat through the Windows IIS web server process (w3wp.exe) before executing Wordconv.exe. As shown in the below figure, msvcr100.dll is contained within the import DLL list of Wordconv.exe, so the first DLL file that is loaded when Wordconv.exe is executed is determined by the DLL search priority of the operating system. As a result, the malicious msvcr100.dll is run in the memory of the Wordconv.exe process.

Figure 2. Import DLL list of Wordconv.exe
As can be seen in the below Figure 3, the functionality of msvcr100.dll involves decrypting an encoded PE file (msvcr100.dat) and the key (df2bsr2rob5s1f8788yk6ddi4x0wz1jq) that is transmitted as a command-line argument during the execution of Wordconv.exe by utilizing the Salsa20 algorithm. The decrypted PE file is then executed in the memory. It then performs the function of clearing the malicious DLL module that was loaded through the FreeLibraryAndExitThread WinAPI call before deleting itself (msvcr100.dll).

Figure 3. Execution log of Wordconv.exe
Also, msvcr100.dll is very similar in both appearance and features to the cylvc.dll malware covered in the ASEC Blog post “A Case of Malware Infection by the Lazarus Attack Group Disabling Anti-Malware Programs With the BYOVD Technique”, which was released back in 2022. Thus, it is speculated that msvcr100.dll is a variant malware of cylvc.dll.

Figure 4. API Hashing value comparison between msvcr100.dll and cylvc.dll
Similarly to msvcr100.dll, cylvc.dll decrypts the data files with the .dat extension using the Salsa20 algorithm before executing the PE file within the memory space. The PE that was executed within the memory space back in 2022 was a backdoor that communicated with the threat actor’s C&C server.

Figure 5. Data decryption code routine comparison between msvcr100.dll and cylvc.dll
2. Establishing Foothold and Stealing Certificates
After the initial infiltration, the threat actor established a foothold before creating additional malware (diagn.dll) by exploiting the open-source “color picker plugin”, which is a plugin for Notepad++.

Figure 6. diagn.dll icon resource information

Figure 7. Open-source color picker plugin page (Github)
diagn.dll is responsible for receiving the PE file encoded with the RC6 algorithm as an execution argument value before using an internally hard-coded key to decrypt the data file and execute the PE file in the memory.

RC6 key: 5A 27 A3 E8 91 45 BE 63 34 23 11 4A 77 91 53 31 5F 47 14 E2 FF 75 5F D2 3F 58 55 6C A8 BF 07 A1

The malicious behavior of the PE file executed in the memory is unknown since the PE data file that was encoded during the attack could not be collected, but a log was confirmed through the AhnLab Smart Defense (ASD) infrastructure of the threat actor accessing the memory space of the lsass.exe process through this module. Thus, it is suspected that the threat actor had executed a credential theft tool such as Mimikatz.

Figure 8. Log of credential theft history
3. Lateral Movement
After acquiring the system credentials, the threat actor performed internal reconnaissance before utilizing remote access (port 3389) to perform lateral movement into the internal network. No further malicious activities by the threat actor have been uncovered since then.

Figure 9. Log of lateral movement status
4. Conclusion and Response
The Lazarus group used a variety of attack vectors to perform their initial breach, including Log4Shell,  public certificate vulnerability, 3CX supply chain attack, etc. This group is one of the highly dangerous groups that are actively launching attacks worldwide. Therefore, corporate security managers should utilize attack surface management to identify the assets that could be exposed to threat actors and practice caution by applying the latest security patches whenever possible.
In particular, since the threat group primarily utilizes the DLL side-loading technique during their initial infiltrations, companies should proactively monitor abnormal process execution relationships and take preemptive measures to prevent the threat group from carrying out activities such as information exfiltration and lateral movement.
AhnLab’s products detect and block the malware identified in the attack case covered in this post using the following aliases.
[File Detection]– Trojan/Win.LazarLoader.C5427612 (2023.05.15.02)– Trojan/Win.LazarLoader.C5427613 (2023.05.15.03)
[IOC][DLL Side-loading File Path]– C:\ProgramData\USOShared\Wordconv.exe– C:\ProgramData\USOShared\msvcr100.dll
[MD5]– e501bb6762c14baafadbde8b0c04bbd6: diagn.dll– 228732b45ed1ca3cda2b2721f5f5667c: msvcr100.dll– 47d380dd587db977bf6458ec767fee3d: ? (Variant malware of msvcr100.dll)– 4d91cd34a9aae8f2d88e0f77e812cef7: cylvc.dll (Variant malware of msvcr100.dll)


Categories:Malware Information 
Tagged as:Lazarus 




DarkCloud Infostealer Being Distributed via Spam Emails 

StrelaStealer Being Distributed To Spanish Users 







5
3
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






96 Comments                    









 Inline Feedbacks                    
View all comments











Lazarus Group Striking Vulnerable Windows IIS Web Servers - IT LinesIT Lines



    8 months ago













[…] “In particular, since the threat group primarily utilizes the DLL side-loading technique during their initial infiltrations, companies should proactively monitor abnormal process execution relationships and take preemptive measures to prevent the threat group from carrying out activities such as information exfiltration and lateral movement,” the AhnLab report added. […]






0






Reply













Lazarus Group Striking Vulnerable Windows IIS Web Servers – Cyber Social Hub



    8 months ago













[…] “In particular, since the threat group primarily utilizes the DLL side-loading technique during their initial infiltrations, companies should proactively monitor abnormal process execution relationships and take preemptive measures to prevent the threat group from carrying out activities such as information exfiltration and lateral movement,” the AhnLab report added. […]






0






Reply













Lazarus Group Hanging Susceptible Home Windows IIS Net Servers – Tamilwin.in



    8 months ago













[…] “Particularly, because the risk group primarily makes use of the DLL side-loading method throughout their preliminary infiltrations, corporations ought to proactively monitor irregular course of execution relationships and take preemptive measures to stop the risk group from finishing up actions similar to info exfiltration and lateral motion,” the AhnLab report added. […]






0






Reply













North Korea-linked Lazarus APT targets Microsoft IIS servers to deploy malware – Source: securityaffairs.com - CISO2CISO.COM & CYBER SECURITY GROUP



    8 months ago













[…] argument during the execution of Wordconv.exe by utilizing the Salsa20 algorithm.” reads the analysis published by ASEC. “The decrypted PE file is then executed in the memory. It then performs the […]






0






Reply













Lazarus Group Striking Vulnerable Windows IIS Web Servers. Hackers News | Hackers News



    8 months ago













[…] “In particular, since the threat group primarily utilizes the DLL side-loading technique during their initial infiltrations, companies should proactively monitor abnormal process execution relationships and take preemptive measures to prevent the threat group from carrying out activities such as information exfiltration and lateral movement,” the AhnLab report added. […]






0






Reply













Grupo Lazarus atacando servidores Web Windows IIS vulneráveis – Neotel Segurança Digital



    8 months ago













[…] “Em particular, uma vez que o grupo de ameaças utiliza principalmente a técnica de sideload de DLL durante suas infiltrações iniciais, as empresas devem monitorar proativamente as relações de execução de processos anormais e tomar medidas preventivas para impedir que o grupo de ameaças realize atividades como exfiltração de informações e movimentação lateral”, acrescentou o relatório do AhnLab. […]






0






Reply













Red-teaming Or Attack Tool, CosmicEnergy Arouses Concern. Volt Typhoon Update. Legion In The Cloud. Disaster-themed Scams.. Hackers News | Hackers News



    8 months ago













[…] Lazarus Group Targeting Windows IIS Web Servers (ASEC BLOG) AhnLab Security Emergency response Center (ASEC) has recently confirmed the Lazarus group, a group known to receive support on a national scale, carrying out attacks against Windows IIS web servers. Ordinarily, when threat actors perform a scan and find a web server with a vulnerable version, they use the vulnerability suitable for the version to install a web shell or execute malicious commands. The AhnLab Smart Defense (ASD) log displayed below in Figure 1 shows that Windows server systems are… […]






0






Reply













IT Security Weekend Catch Up – May 27, 2023 – BadCyber



    8 months ago













[…] Lazarus group targeting Windows IIS web servers […]






0






Reply













Lazarus Group, Savunmasız Windows IIS Web Sunucularını Çarpıyor - Dünyadan Güncel Teknoloji Haberleri | Teknomers



    8 months ago













[…] “Özellikle, tehdit grubu ilk sızmaları sırasında öncelikle DLL yandan yükleme tekniğini kullandığından, şirketler anormal süreç yürütme ilişkilerini proaktif olarak izlemeli ve tehdit grubunun bilgi sızdırma ve yanal hareket gibi faaliyetler yürütmesini önlemek için önleyici tedbirler almalıdır.” the AhnLab raporu katma. […]






0






Reply













Weekendowa Lektura: odcinek 521 [2023-05-27]. Bierzcie i czytajcie | Zaufana Trzecia Strona



    8 months ago













[…] Północnokoreańska grupa Lazarus atakuje podatne serwery Windows IIS […]






0






Reply













Security Affairs newsletter Round 421 by Pierluigi Paganini – International edition – ITSecurityNewsBox



    8 months ago













[…] Lazarus Group Targeting Windows IIS Web Servers    […]






0






Reply













Security Affairs newsletter Round 421 by Pierluigi Paganini – International edition – Cyber News



    8 months ago













[…] Lazarus Group Targeting Windows IIS Web Servers    […]






0






Reply













Lazarus Group Striking Vulnerable Windows IIS Web Servers - The Network Company | Cyber Security | IT Services | Network Security



    8 months ago













[…] from carrying out activities such as information exfiltration and lateral movement,” the AhnLab report added.Copyright © 2023 Informa PLC Informa UK Limited is a company registered in England and Wales […]






0






Reply













Lazarus Group Putting Susceptible Home windows IIS Internet Servers - top10-webhosting.com. All rights reserved.



    8 months ago













[…] “Specifically, because the menace group primarily makes use of the DLL side-loading approach throughout their preliminary infiltrations, corporations ought to proactively monitor irregular course of execution relationships and take preemptive measures to forestall the menace group from finishing up actions resembling data exfiltration and lateral motion,” the AhnLab report added. […]






0






Reply













N. Korean Lazarus Group Targets Microsoft IIS Servers to Deploy Espionage Malware – Tech News and Articles



    8 months ago













[…] a normal application (Wordconv.exe) via the Windows IIS web server process, w3wp.exe,” ASEC explained. “They then execute the normal application to initiate the execution of the malicious […]






0






Reply













Lazarus Group Striking Vulnerable Windows IIS Web Servers - Di-Markets



    8 months ago













[…] “Particularly, because the menace group primarily makes use of the DLL side-loading approach throughout their preliminary infiltrations, firms ought to proactively monitor irregular course of execution relationships and take preemptive measures to stop the menace group from finishing up actions equivalent to info exfiltration and lateral motion,” the AhnLab report added. […]






0






Reply













Lazarus Group Targets IIS Servers - LetsAskBinu.com



    8 months ago













[…] as their initial breach routes before executing their malicious commands later,” researchers at AhnLab, who have been tracking the attacks, […]






0






Reply













Lazarus Group Striking Vulnerable Windows IIS Web Servers – Flyytech.com



    8 months ago













[…] “In particular, since the threat group primarily utilizes the DLL side-loading technique during their initial infiltrations, companies should proactively monitor abnormal process execution relationships and take preemptive measures to prevent the threat group from carrying out activities such as information exfiltration and lateral movement,” the AhnLab report added. […]






0






Reply













Lazarus Group Striking Vulnerable Windows IIS Web Servers - Shackle Media



    8 months ago













[…] “In particular, since the threat group primarily utilizes the DLL side-loading technique during their initial infiltrations, companies should proactively monitor abnormal process execution relationships and take preemptive measures to prevent the threat group from carrying out activities such as information exfiltration and lateral movement,” the AhnLab report added. […]






0






Reply













Lazarus Group Striking Vulnerable Windows IIS Web Servers - ThreatsHub Cybersecurity News



    8 months ago













[…] “In particular, since the threat group primarily utilizes the DLL side-loading technique during their initial infiltrations, companies should proactively monitor abnormal process execution relationships and take preemptive measures to prevent the threat group from carrying out activities such as information exfiltration and lateral movement,” the AhnLab report added. […]






0






Reply













N. Korean Lazarus Group Targets Microsoft IIS Servers to Deploy Espionage Malware - Digital Creations LLC



    8 months ago













[…] a normal application (Wordconv.exe) via the Windows IIS web server process, w3wp.exe,” ASEC explained. “They then execute the normal application to initiate the execution of the malicious […]






0






Reply













Peretas Lazarus menargetkan server web Windows IIS untuk akses awal - Teknokrat Network



    8 months ago













[…] terbaru penargetan server Windows IIS ditemukan oleh peneliti Korea Selatan di Pusat Tanggap Darurat Keamanan AhnLab […]






0






Reply













Lazarus hackers target Windows IIS web servers for initial access – thequintessentialjournal



    8 months ago













[…] The latest tactic of targeting Windows IIS servers was discovered by South Korean researchers at the AhnLab Security Emergency Response Center (ASEC). […]






0






Reply













Lazarus hackers target Windows IIS web servers for initial access - Shackle Media



    8 months ago













[…] The latest tactic of targeting Windows IIS servers was discovered by South Korean researchers at the AhnLab Security Emergency Response Center (ASEC). […]






0






Reply













Lazarus hackers target Windows IIS web servers for initial access » Webfingers Blog



    8 months ago













[…] The latest tactic of targeting Windows IIS servers was discovered by South Korean researchers at the AhnLab Security Emergency Response Center (ASEC). […]






0






Reply













Lazarus hackers target Windows IIS web servers for initial access – Source: www.bleepingcomputer.com - CISO2CISO.COM & CYBER SECURITY GROUP



    8 months ago













[…] The latest tactic of targeting Windows IIS servers was discovered by South Korean researchers at the AhnLab Security Emergency Response Center (ASEC). […]






0






Reply













مجموعة "لازاروس" الكورية الشمالية تهاجم "مايكروسوفت".. التفاصيل الكاملة - إكسڤار | ExVar



    8 months ago













[…] الجنوبية في مركز استجابة الطوارئ للأمان في شركة “AhnLab“، اكتشفوا أحدث تكتيك يستهدف خوادم ويندوز (IIS) من قبل […]






0






Reply













Lazarus hackers target Windows IIS web servers to gain initial access



    8 months ago













[…] The latest tactic of targeting Windows IIS servers was discovered by South Korean researchers at the AhnLab Security Emergency Response Center (ASEC). […]






0






Reply













Lazarus hackers target Windows IIS web servers for initial access



    8 months ago













[…] The latest tactic of targeting Windows IIS servers was discovered by South Korean researchers at the AhnLab Security Emergency Response Center (ASEC). […]






0






Reply













LE GROUPE DE HACKERS LAZARUS OBTIENT UN PREMIER ACCÈS EN EXPLOITANT DES SERVEURS WEB WINDOWS IIS VULNÉRABLES - Blog KoDDoS



    8 months ago













[…] par le groupe consistait à cibler les serveurs Windows IIS. Cette activité de piratage a été détectée par des chercheurs Sud-Coréens du AhnLab Security Emergency Response Center […]






0






Reply













Lazarus Hacking Group Attack IIS Web Servers



    8 months ago













[…] ASEC advises organizations to monitor for abnormal process execution due to Lazarus’ extensive use of DLL sideloading in their attacks. […]






0






Reply













Lazarus Hacking Group Attack IIS Web Servers - AI Tech Herald



    8 months ago













[…] ASEC advises organizations to monitor for abnormal process execution due to Lazarus’ extensive use of DLL sideloading in their attacks. […]






0






Reply













Lazarus Hacking Group Attack IIS Web Servers to Install Web Shell – ZBM Security News



    8 months ago













[…] ASEC advises organizations to monitor for abnormal process execution due to Lazarus’ extensive use of DLL sideloading in their attacks. […]






0






Reply













Lazarus Hacking Group Obtains Initial Access By Exploiting Vulnerable Windows IIS Web Servers. Hackers News | Hackers News



    8 months ago













[…] tactic that was used by the group included targeting Windows IIS servers. This hacking activity was detected by South Korean researchers at the AhnLab Security Emergency Response Center […]






0






Reply













Lazarus Group Targeting Windows IIS Web Servers – Open Source & Security



    8 months ago













[…] Read more at AHNLAB […]






0






Reply













Anomali Cyber Watch: Shadow Force Targets Korean Servers, Volt Typhoon Abuses Built-in Tools, CosmicEnergy Tests Electric Distribution Disruption - Ciberdefensa



    8 months ago













[…] Lazarus Group Targeting Windows IIS Web Servers […]






0






Reply













Anomali Cyber Watch: Shadow Force Targets Korean Servers, Volt Typhoon Abuses Built-in Tools, CosmicEnergy Tests Electric Distribution Disruption – F1TYM1



    8 months ago













[…] Lazarus Group Targeting Windows IIS Web Servers […]






0






Reply













Anomali Cyber Watch: Shadow Force Targets Korean Servers, Volt… – Unified Networking



    8 months ago













[…] Lazarus Group Targeting Windows IIS Web Servers […]






0






Reply













June 3, 2023 - Red-N Security



    8 months ago













[…] Lazarus hackers target Windows IIS web servers for initial access […]






0






Reply













N. Korean Lazarus Group Targets Microsoft IIS Servers to Deploy Espionage Malware - SPIXNET C2S



    8 months ago













[…] a normal application (Wordconv.exe) via the Windows IIS web server process, w3wp.exe,” ASEC explained. “They then execute the normal application to initiate the execution of the malicious […]






0






Reply













Lazarus hackers target Windows IIS web servers for initial access - SPIXNET C2S



    8 months ago













[…] The latest tactic of targeting Windows IIS servers was discovered by South Korean researchers at the AhnLab Security Emergency Response Center (ASEC). […]






0






Reply













How Lazarus Group Abuses IIS Servers to Spread Malware? How Should You Protect Your IIS Servers from DLL side-loading Attacks? – The Securirty Master



    8 months ago













[…] per the report released by AhnLab Security Emergency Response Center (ASEC), Lazarus group is now targeting […]






0






Reply













Lazarus Targets Microsoft IIS servers



    6 months ago













[…] Group has targeted Microsoft IIS servers earlier. In May, attackers used poorly managed servers as the initial access point and used RDP for lateral […]






0






Reply













Lazarus Targets Microsoft IIS servers – Securitydone



    6 months ago













[…] Group has targeted Microsoft IIS servers earlier. In May, attackers used poorly managed servers as the initial access point and used RDP for lateral […]






0






Reply













Lazarus Threat Group angriber Windows-servere til brug som malware-distributionspunkter  – Ransomware, Kryptering, DeKryptering, Malware og Penetrationstest



    6 months ago













[…] det tidligere blogindlæg (maj 2023), “Lazarus Group Targeting Windows IIS Web Servers”[2]. Det blev identificeret i angrebssagen på det tidspunkt, at trusselsaktøren brugte dårligt […]






0






Reply













Analysis Report on Lazarus Threat Group's Volgmer and Scout Malwares - ASEC BLOG



    3 months ago













[…] also server systems for the purpose of using them as malware distribution or C&C servers. [4] […]






0






Reply




 
« Previous
1
2 










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















































































































































































































































