# Reference for threat actor for "Bronze Butler, Tick, RedBaldNight, Stalker Panda"

**Title**: Additional Activities of the Tick Group That Attacks with a Modified Q-Dir and Their Ties with Operation Triple Tiang - ASEC BLOG

**Source**: https://asec.ahnlab.com/en/51340/

## Content


















Additional Activities of the Tick Group That Attacks with a Modified Q-Dir and Their Ties with Operation Triple Tiang - ASEC BLOG





































































 

Malware Information
AhnLab Detection
Statistics
Response Guide
AhnLab
 














Posted By AhnLab_en  , April 17, 2023 

Additional Activities of the Tick Group That Attacks with a Modified Q-Dir and Their Ties with Operation Triple Tiang 
In March 2023, Eset analyzed malware that was found in an East Asian DLP manufacturer and announced that the Tick group was responsible for it.
The Tick group has been active mainly in Korea and Japan since 2014, targeting various sectors such as aerospace, military, defense industries, heavy industries, electronics, telecommunications, government agencies, and diplomacy.
AhnLab Security Emergency response Center (ASEC) has confirmed additional activities from this group and will be disclosing them here.
* Modified Q-Dir Variants
From January 2021 to August 2022, AhnLab Security Emergency response Center (ASEC) discovered 3 additional malware disguised as Q-Dir in Korea.
Two of the confirmed variants drop a ReVBSHell backdoor, but the variant (md5: 00b170970d46c9212b6d75ce7afc0870) discovered in August of 2022 creates an FTP server file.
* ShadowPY Variant
Eset also revealed information about the ShadowPY malware used in the attack, and upon verification, it was found to be similar to the malware that was reported to AhnLab in September 2021 by a Korean client.
The program used as a loader at the time was Avira’s avshadow.exe, and the name of the malicious DLL file was also vssapi.dll. Both of these align with the information disclosed by Eset.
The code was also found to be similar.
vssapi.dll file comparison

 * Ties with Operation Triple Tiang
Eset revealed that there is a chance that Operation Triple Tiang, which was reported on by AhnLab, is related to the Tick group.
Operation Triple Tiang is a cyber attack campaign that has been targeting political and diplomatic sectors of Korea. A clear culprit behind this campaign was not identified at the point the report was released in 2022.
AhnLab Security Emergency response Center (ASEC) has confirmed that the ReVBSHell dropper used in Operation Triple Tiang and the ReVBSHell dropper variant used in the attack against the DLP manufacturer utilizes the same technique.
Both droppers check the number of files in the temp folder when the malware is executed, and only create the malware file when the number exceeds a certain amount (10 or 18 depending on the variant).
Operation comparison to check number of files inside Temp

Considering that they both use the same ReVBSHell and their droppers use similar codes, there is a high possibility that the Tick group is behind Operation Triple Tiang.
* Conclusion
The Tick group has been targeting government agencies, the military, and various industries in Korea and Japan for over a decade. There is a high possibility that they are still active covertly, and AhnLab plans to continue tracking their activities.
* Special thanks to Facundo Muñoz from Eset for providing the samples and information.
[File Detection]
Backdoor/VBS.Agent (2023.03.29.02)
Dropper/Win.Revbshell (2023.03.28.03)
Dowonloader/Win.Agent (2022.03.15.00)
Trojan/VBS.Obfus (2023.04.06.00)
Trojan/Win.ShadowPY (2023.04.05.03)
[IOC]
00b170970d46c9212b6d75ce7afc0870
19d0edc452b32b0d3da407459a1a9c56
2db7b0e8b0a3b7f142c4246d8c8bf892
31329cce9d0517233053b5363f06f5af
574df15b8bc888750ca28dd4f4f11fae
cb4a15d941a20985d145cd99fcaf3c82
ddbd1fcf0c332ce8dc38f6b48b29c597
ed97cf996bda070de3b7fa1e75b762b1
Subscribe to AhnLab’s next-generation threat intelligence platform ‘AhnLab TIP’ to check related IOC and detailed analysis information.


Categories:Malware Information 
Tagged as:MODIFIEDQ-DIR,ReVBSHell,ShadowPY,Tick,TripleTiang,vssapi.dll 




ASEC Weekly Malware Statistics (April 3rd, 2023 – April 9th, 2023) 

Trigona Ransomware Attacking MS-SQL Servers 







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






1 Comment                    









 Inline Feedbacks                    
View all comments











Additional Activities of the Tick Group That Attacks with a Modified Q-Dir and Their Ties with Operation Triple Tiang - Ciberdefensa



    9 months ago













[…] post Additional Activities of the Tick Group That Attacks with a Modified Q-Dir and Their Ties with Opera… appeared first on ASEC […]






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















































































































































































































































