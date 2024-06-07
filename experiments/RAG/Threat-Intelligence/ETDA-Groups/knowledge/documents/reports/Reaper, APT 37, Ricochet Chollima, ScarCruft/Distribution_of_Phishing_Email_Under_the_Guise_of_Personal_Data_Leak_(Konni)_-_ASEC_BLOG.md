# Reference for threat actor for "Reaper, APT 37, Ricochet Chollima, ScarCruft"

**Title**: Distribution of Phishing Email Under the Guise of Personal Data Leak (Konni) - ASEC BLOG

**Source**: https://asec.ahnlab.com/en/59763/

## Content















Distribution of Phishing Email Under the Guise of Personal Data Leak (Konni) - ASEC BLOG



































































 

Malware Information
AhnLab Detection
Statistics
Response Guide
AhnLab
 














Posted By leeikgyu  , December 11, 2023 

Distribution of Phishing Email Under the Guise of Personal Data Leak (Konni) 
AhnLab Security Emergency response Center (ASEC) recently identified the distribution of a malicious exe file disguised as material related to a personal data leak, targeting individual users. The final behavior of this malware could not be observed because the C2 was closed, but the malware is a backdoor that receives obfuscated commands from the threat actor and executes them in xml format.

Figure 1. An email impersonating a cyber investigation team

Figure 2. The malicious exe file disguised as a Word file
When the malicious exe file is executed, the files in the .data section are created into the %Programdata% folder. Out of the created files, all files are obfuscated except for the legitimate doc file.

Lomd02.png (Malicious jse script)
Operator.jse (Malicious jse script)
WindowsHotfixUpdate.jse (Malicious jse script)
20231126_9680259278.doc (Legitimate doc file)
WindowsHotfixUpdate.ps1 (Malicious PowerShell script)


Figure 3. Files in the .data section
A legitimate document file, ‘20231126_9680259278.doc’, is included among the created files. The threat actor has probably included this to deceive the user into thinking that they opened a legitimate file.

Figure 4. 20231126_9680259278.doc
Operator.jse creates a Task Scheduler entry that executes WindowsHotfixUpdate.jse, which in turn executes the file WindowsHotfixUpdate.ps1. The file WindowsHotfixUpdate.ps1 receives commands from the C2, and it is presumed that these commands are obfuscated, because the jse file with the file name Lomd02.png was observed deobfuscating such commands and loading them in xml format.
While additional commands could not be examined due to the C2 being unavailable for access at the moment, it seems that various additional attacks would be possible depending on the commands sent from the C2.

Task Scheduler name: WindowsHotfixUpdate[B409302303-02940492024]
Trigger: Repeat every minute indefinitely
Action: Execute C:\ProgramData\WindowsHotfixUpdate.jse


Figure 5. Deobfuscated Operator.jse

Figure 6. Deobfuscated WindowsHotfixUpdate.jse

Figure 7. Deobfuscated WindowsHotfixUpdate.ps1

Figure 8. Deobfuscated Lomd02.png (jse)
Because the bait file is also run, ordinary users cannot recognize that their systems are infected by malware. Since such malware are aimed at specific targets, users should refrain from running attachments in emails sent from unknown sources.
[File Detection]

Backdoor/JS.Konni (2023.12.06.03)
Backdoor/Win.Konni (2023.12.06.03)
Backdoor/PowerShell.Konni (2023.12.06.03)

[IOC]

MD5b58eb8a3797d3a52aba30d91d207b688 ([Date]_[Name].exe)78ea811850e01544ca961f181030b584 (Lomd02.png)682b5a3c93e107511fdd2cdb8e50389a (Operator.jse)a93474c3978609c8480b34299bf482b7 (WindowsHotfixUpdate.jse)d634cb7b45217ca4fd7eca5685a64f50 (20231126_9680259278.doc)d06d1c2ec1490710133dea445f33bd19 (WindowsHotfixUpdate.ps1)
C2hxxp://gjdow.atwebpages.com/dn[.]php?name=[Computer name]&prefix=tt

Subscribe to AhnLab’s next-generation threat intelligence platform ‘AhnLab TIP’ to check related IOC and detailed analysis information.


Categories:Malware Information 
Tagged as:backdoor,KONNI,phishing 




Kimsuky Group Uses AutoIt to Create Malware (RftRAT, Amadey) 

Infected Systems Controlled Through Remote Administration Tools (Detected by EDR) 







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






9 Comments                    









 Inline Feedbacks                    
View all comments











Hackers Trick Users With Data Leak Message to Deploy Malware - Tempyx Blog



    2 months ago













[…] the created files, all files are obfuscated except for the legitimate doc file”, ASEC said in a report shared with Cyber Security […]






0






Reply













Hackers Trick Users With Data Leak Message to Deploy Malware - h4ckers-news



    2 months ago













[…] the created files, all files are obfuscated except for the legitimate doc file”, ASEC said in a report shared with Cyber Security […]






0






Reply













Hackers Trick Users With Data Leak Message to Deploy Malware – ZBM Security News



    2 months ago













[…] the created files, all files are obfuscated except for the legitimate doc file”, ASEC said in a report shared with Cyber Security […]






0






Reply













    Ymmah



    2 months ago













Don’t you agree at this point we ought to be sharing at least the SHA-256 instead of MD5?






0






Reply













Hackers Trick Users With Data Leak Message to Deploy Malware | GB Hackers - xWebfingers Blog



    2 months ago













[…] the created files, all files are obfuscated except for the legitimate doc file”, ASEC said in a report shared with Cyber Security […]






0






Reply













Hackers Trick Users With Data Leak Message to Deploy Malware | GB Hackers » Webfingers Blog



    2 months ago













[…] the created files, all files are obfuscated except for the legitimate doc file”, ASEC said in a report shared with Cyber Security […]






0






Reply













Lazarus Group Using Log4j Exploits to Deploy Remote Access Trojans - The Network Company | Cyber Security | IT Services | Network Security



    2 months ago













[…] phishing campaign that uses a malicious executable file disguised as a Microsoft Word file to deliver a backdoor that “receives obfuscated commands from the threat actor and executes them in XML […]






0






Reply













Lazarus Group uses Log4j exploits to deploy remote access Trojans – ITDEVSEC



    1 month ago













[…] phishing campaign that uses a malicious executable disguised as a Microsoft Word file to provide a back door which “receives obfuscated commands from the threat actor and executes them in XML […]






0






Reply













Los hackers distribuyen correos electrónicos de phishing con mensajes de fuga de datos - Boletines Dicofra



    1 month ago













[…] Distribution of Phishing Email Under the Guise of Personal Data Leak (Konni) […]






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
















































































































































































































































