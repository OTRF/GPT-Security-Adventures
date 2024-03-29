# Reference for threat actor for "Gamaredon Group"

**Title**: The Russian Shadow in Eastern Europe: A Month Later - Yoroi

**Source**: https://blog.yoroi.company/research/the-russian-shadow-in-eastern-europe-a-month-later/

## Content







The Russian Shadow in Eastern Europe: A Month Later - Yoroi








































































 












Home






Defence center






Threat intelligence






Solutions







Before Attack







Technologies







Threat intelligence






DNS Defence






Kanwa






Genku






Digital Surveillance








Services







Infrastructure & Systems compliance






Scam Protection






SCADA Security






Early Warning






Wi-Fi Infrastructure Assessment






Vulnerability Assessment






Adversarial Simulation






Threat Hunting






SIEM management






Security Infrastructure Assessment (SIA)






Penetration Testing










During Attack







Technologies







Threat intelligence






Kanwa






Yomi






Email Protection








Services







IRT (Incident Response Team)






Managed Advanced Threat Protection






KickBack Attack










After Attack







Technologies







Threat intelligence






Kanwa








Services







Wi-Fi Infrastructure Assessment






Threat Hunting












Blogs







Yoroi Blog






Marco Ramilli Blog








Downloads






About us






Contacts






English







Italiano






The Russian Shadow in Eastern Europe: A Month Later
	06/04/2019
Introduction
The Gamaredon attacks against Ukraine doesn't seem to have stopped. After a month since our last report we spotted a new suspicious email potentially linked to the Gamaredon group. The group was first discovered by Symantec and TrendMicro in 2015 but evidence of its activities has been dated back to 2013. During recent times, Gamaredon is targeting the Ukrainian military and law enforcement sectors too, as officially stated by the CERT-UA.
Cybaze-Yoroi ZLAB team dissected the artifact recovered from their latest attack to figure out evolution or changes in the threat actor TTPs.
Technical Analysis
Figure 1. Malicious e-mail 
The infection chain is composed by different stages of password protected SFX (self extracting archive), each containing vbs or batch scripts.
At the final stage of this malicious chain, we found a customized version of UltraVNC, a well known off-the-shelf tool for remote administration, modified by the Group and configured to connect to their command and control infrastructure. Despite its apparent triviality, the Matryoshka of SFX archives reached a low detection rate, making it effective. 
Stage 1
Hash5555a3292bc6b6e7cb61bc8748b21c475b560635d8b0cc9686b319736c1d828eThreatGamaredon Pteranodon implantBrief DescriptionSFX fileSsdeep24576:PXwOrRsTyuURQFsVhIe74lpyevrM4vZxn6k1gQ Guo:PgwRAyuURQ2/1YpyeT7ok8
Table 1. Information about initial SFX file 
The mail attachment is a RAR archive containing a folder named “suspected” in Ukrainan and a single suspicious file with “.scr” extension. At first glance, it is possible to notice the PowerPoint icon associated to the file, normally not belonging to .scr files.
Figure 2. Content of malicious e-mail
Figure 3. Low AV detection of SFX malware
The file has a very low detection rate on VirusTotal platform: only four AV engines are able to identify it as malicious and only on engine understands it may be associated to the Gamaredon implant.
After a quick analysis, the real nature of the .scr file emerges: it is a Self Extracting Archive containing all the files in Figure 4.
They are extracted into “%TEMP%\7ZipSfx.000\” and the first command to be executed is “15003.cmd”, which firstly checks for the presence of  malware analysis tools. If it detects the presence of Wireshark or Procexp tools, it kill itself. Otherwise, it copies: 
Figure 4. Content of SFX 
the “11439” file in “%USERNAME%\winupd.exe” the “28509” file in “%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup\winupd.lnk” pointing to the previous executable and granting persistence to machine rebootthe “20261” file in “%TEMP%\7ZipSfx.000\Document.docx”
Figure 5. Script content in  “15003.cmd” file
At the same time, the extracted document will be shown in order to divert the user attention and to continue the infection unnoticed. This document, written in Ukraine language, contains information about a criminal charge.
Figure 6. Fake document to divert attention on malware execution 
Figure 7. Execution of “winupd.exe” (SFX) and relative password (uyjqystgblfhs)
Instead, exploring the LNK file is possible to see it's able to start the “winupd.exe” file, with a particular parameter: %USERPROFILE%\winupd.exe -puyjqystgblfhs. This behavior indicates the “winupd.exe” executable is another Self Extracting Archive, but this time it is password protected. 
Stage 2
Hashfd59b1a991df0a9abf75470aad6e2fcd67c070bfccde9b4304301bc4992f678eThreatGamaredon Pteranodon implantBrief DescriptionSFX fileSsdeep24576:bGKUQ8Lj7S6Jr1ye4SM4vzxn3k1jQ GujR:biJr1yeNxJkro
Table 2. Information about second SFX file 
When launched, it extracts its content in “%TEMP%\RarSFX0\”, then executes the “setup.vbs” script, which contains only two code lines. So, the execution flow moves on “1106.cmd”.
Figure 8. Content of “setup.vbs” script
Figure 9. Content of “%APPDATA%\Local\Temp\RarSFX0” after “winupd.exe” (SFX) extraction
The source code of “1106.cmd” is full of junk instructions. However, in the end it performs a simple action: it writes a new VBS script in “%APPDATA%\Microsoft\SystemCertificates\My\Certificates\” . This script tries to download another malicious file from “http://bitvers.ddns[.net/{USERNAME}/{DATE}/index.html”.  Performing many researches abot this server we noticed the continuously modification of associated records. Indeed, the attacker has changed many time the domain names in the latest period. Moreover,  querying the services behind  the latest associated DNS record the host responds with “403 Forbidden” message too, indicating the infrastructure may still be operative.
Figure 10. Information about C2 and relative DNS
The scripts creates a new scheduled task in order to periodically execute (every 20 mins) the previous VBS script. 
Figure 11. POST request sent to C2 with victim machine information 
Also, it collects all the information about the victim’s system using the legit “systeminfo” Microsoft tool and sends them to the remote server through a POST request using the “MicrosoftCreate.exe” file, which actually is the legit “wget” utility. The response body will contain a new executable file, named “jasfix.exe”,  representing the new stage. 
Stage 3
Hashc479d82a010884a8fde0d9dcfdf92ba9b5f4125fac1d26a2e36549d8b6b4d205ThreatGamaredon Pteranodon implantBrief DescriptionSFX fileSsdeep24576:Gfxwgmyg5EOJ+IIpBz2GAROm560XVEC1Ng MdfaQbhUfEIg+m:GJpgIdPzeRBJVEC1CMd
Table 3. Information about third SFX file 
After few researches, we were able to retrieve the “jasfix.exe” file, the next stage of the infection chain. After downloading it, we notice that it is another SFX archive other files. 
Figure 12. Content of “jasfix.exe” (SFX) downloaded from the C2
The first file to be executed is “20387.cmd” that renames the “win.jpg” into “win.exe”, another password protected SFX. 
Stage 4
Hash28eff088a729874a611ca4781a45b070b46302e494bc0dd53cbaf598da9a6773ThreatGamaredon Pteranodon implantBrief DescriptionSFX fileSsdeep24576:9GKUQ8vCTAaaJVssTk3OwO+vl+3yt6Xf IAR:9vaJes2Ocl7t9S
Table 4. Information about fourth SFX file 
This latest SFX archive follows the typical pattern of the Gamaredon archives Matryoshka, where the “.cmd” file is in designed to decrypt and run next stage. This time using the string “gblfhs” as password.
Figure 13. Script to rename “win.jpg” into “win.exe”, decrypt and run next stage
Figure 14. Content of “win.exe” (last SFX of infection)
However, the file named “win32.sys” is particularly interesting: it actually is a PE32 executable file. Exploring the “.rsrc” section of the PE32 executable, we noticed different “.class” files. Two of them are named “VncCanvas” and “VncViewer”. These files are part of a legit Remote Administration Tool (RAT) named UltraVNC, available at this link. 
Figure 15. Content of “win32.sys”
The “win.exe” SFX archive contains other interesting files too: one of them is an “.ini” configuration file containing all the parameters and the password used by the UltraVNC tool.
Figure 16. Configuration file used by “win32.sys” (Custom ultraVNC)
Finally, the RAT tries to establish a connection to the “torrent-vnc[.ddns[.net” domain, headed to an endpoint reachable on 195.88.208.51, a VPS hosted by the Russian provider IPServer.
Figure 17. C2 and relative port used by RAT
Conclusion
This recent attack campaign shows the Gamaredon operation are still ongoing and confirms the potential Russian interest about infiltrating the East European ecosystem, especially the Ukranian one. The techniques and the infection patterns the Group is using is extremely similar to the other attacks spotted in the past months of 2019, showing the Matryoshka structure to chain SFX archives, typical of their implant, but still effective and not easily detectable by several antivirus engines. 
Also, digging into this infection chain, we noticed the come back of third party RATs as payload, a Gamaredon old habit that the usage of the custom-made Pterodo backdoor replaced few times ago.
Indicators of Compromise
Hashes
601d85c0236f8d3a82fecf353adb106fac23f1681ef866783ff6e634538c9ce0566f495f334cbf4bf019d9ad58636ad0839eadce8d9e5e3fd78deececbcb6fdc5555a3292bc6b6e7cb61bc8748b21c475b560635d8b0cc9686b319736c1d828e3ed4ba91886309f8c25a9d2c052effab37193ffbb1dbbf29cbd1e9b7e9691514fd59b1a991df0a9abf75470aad6e2fcd67c070bfccde9b4304301bc4992f678ef53bb852e0721e623f55a63e325db1c13c4eddad2a8d6743f358430dfcbe9c23b511e05100b3a4f3515c5526d2dc3c873f66384225c174c65931744d9e682dc045a4db08585ae8148fc1f23644b04e431e2b945f285797e235002f2a41c04462ddd5b5ca4c0816d9983cb200a55a345a5dbe005e38642d088f05bb137174828aa48ad33695a44de887bba8f2f3174fd8fb01a46a19e3ec9078b0118647ccf599 (WGET)774925ca3134dabfa57c548c11080fc383c9ed89af8cdc11e6caab5a25fc9564c479d82a010884a8fde0d9dcfdf92ba9b5f4125fac1d26a2e36549d8b6b4d20557b094d0ad345a2654843bed9fdcd2af3f1d9f5d567919f5cb78d9e547093f2328eff088a729874a611ca4781a45b070b46302e494bc0dd53cbaf598da9a6773d8a01f69840c07ace6ae33e2f76e832c22d4513c07e252b6730b6de51c2e438599c9440a84cdc428ce140de901452eb334faec49f1f6258acdde1ddcbb34376eef0f0e80e5e1fae63b946f87d571fac8646e6ba90995536c08cd20d2e40da18ecedbbbc4deb6569c23aa20ac64ad1c2b2bef6f7b3405cef861f26a0b44d836d9
URL
my-certificates[.ddns[.netbitvers[.ddns[.nettorrent-vnc[.ddns[.net:5612
Components
%TEMP%\RarSFX0\11060.cmd%TEMP%\RarSFX0\jasfix.exe%TEMP%\RarSFX0\MicrosoftCreate.exe%TEMP%\RarSFX0\NnDBzUE%TEMP%\RarSFX0\setup.vbs%TEMP%\7ZipSfx.000\11439%TEMP%\7ZipSfx.000\15003.cmd%TEMP%\7ZipSfx.000\20261%TEMP%\7ZipSfx.000\28509%TEMP%\7ZipSfx.000\Document.docx%USERNAME%\winupd.exe%APPDATA%\Microsoft\SystemCertificates\My\Certificates\{filename}.vbs%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup\winupd.lnk%TEMP%\RarSFX0\win\32.sys
IP
195.62.52.119
Yara Rules
rule GamaredonPteranodon_SFX {
meta:
   	 description = "Yara Rule for Pteranodon implant Family"
   	 author = "ZLAB Yoroi - Cybaze"
   	 last_updated = "2019-04-19"
   	 tlp = "white"
   	 category = "informational"

   strings:
      $s1 = "SFX module - Copyright (c) 2005-2012 Oleg Scherbakov"
      $s2 = "7-Zip archiver - Copyright (c) 1999-2011 Igor Pavlov" 
      $s3 = "RunProgram=\"hidcon" 
      $s4 = "7-Zip - Copyright (c) 1999-2011 " ascii
      $s5 = "sfxelevation" ascii wide
      $s6 = "Error in command line:" ascii wide
      $s7 = "%X - %03X - %03X - %03X - %03X" ascii wide
      $s8 = "- Copyright (c) 2005-2012 "  ascii
      $s9 = "Supported methods and filters, build options:" wide ascii
      $s10 = "Could not overwrite file \"%s\"." wide ascii
      $s11 = "7-Zip: Internal error, code 0x%08X." wide ascii
      $s12 = "@ (%d%s)"  wide ascii
      $s13 = "SfxVarCmdLine0" ascii
      $s14 = "11326"
      $s15 = "29225"
      $s16 = "6137"
      $cmd = ".cmd" wide ascii 

condition:
      12 of ($s*) and $cmd
}

import "pe"
rule GamaredonPteranodon_SFX_intermediate_stage{
meta:
	description = "Yara Rule for Pteranodon implant Family Intermediate Stage"
	author = "Cybaze - Yoroi ZLab"
	last_updated = "2019-05-31"
	tlp = "white"
	category = "informational"
strings:
	$a1 = {56 8B F1 8D 46 04 50 FF}
	$a2 = {14 7A 19 5D 01 EB 18 02 85}
	$a3 = {0D 4D 38 B1 2D EE 1E 2B}
   	$b1 = {34 9B 43 00 50 FF 15 30}
    	$b2 = {AB B9 89 97 2F DD 7D 82}
    	$b3 = {9D CA C6 91 EF}
    	$c1 = {24 0C FF 15 34 9B 43 00}
    	$c2 = {32 31 32 F0 32 2E 39}
    	$c3 = {45 3B 4B 21 A7}

condition:
	pe.number_of_sections == 4 and all of ($a*) or
    	pe.number_of_sections == 6 and all of ($b*) or
    	pe.number_of_sections == 6 and all of ($c*)
}

Acknowledgement: special thanks to @JAMESWT_MHT for info and samples.
SeatYoroi S.r.l.Piazza Sallustio, 900187 Roma (RM)Contact[email protected]+39 051 0301005LegalTerms & ConditionsMOG D.Lgs 231/01Privacy PolicyCookie PolicyCode of Ethics andConductWarning systemSubscribe to our early warning systemDownloadsNewsSocialP.IVA. 03407741200 - R.E.A. RM 1559639 - Codice Fiscale 03407741200 - Capitale Sociale: Euro 100.000 IVYoroi S.r.l. società soggetta ad attività di direzione e coordinamento esercitata dalla Tinexta S.p.A.credits: SimpleNetworks
 
×Subscribe to our early warning system

 











Name *




Last Name *




Company *




Email *




Details






Dichiaro di aver letto e compreso l’informativa privacy resa ai sensi dell’art. 13 e autorizzo il Titolare del trattamento alla raccolta dei miei dati personali secondo le modalità e per le finalità ivi descritte.






Autorizzo il Titolare del trattamento alla raccolta dei miei dati personali secondo le modalità descritte nell’informativa privacy per l’invio di comunicazioni commerciali e/o promozionali anche tramite l’invio di newsletter














 


Questo sito, come la maggior parte dei siti web, utilizza cookie, anche di terze parti, per migliorare la tua esperienza di navigazione e raccogliere informazioni sull'utilizzo del sito stesso. Cliccando su "Accetta tutti" ti dichiari d'accordo all'utilizzo di cookie analitici (che ci aiutano a capire in che modo gli utenti usano il sito e come migliorarlo, insieme ai nostri servizi) e di tracciamento (inclusi quelli di nostri partner di fiducia) che ci aiutano a decidere quali prodotti mostrarti, a misurare il volume di visite sul nostro sito e a darti la possibilità di mettere "mi piace" e di condividere contenuti direttamente sui social media. Clicca qui per vedere a cosa hai dato il tuo consenso e trovare più informazioni sui cookie che utilizziamo.Read MoreGestisci ImpostazioniRifiuta TuttiAccetta tutti  Manage consent




Close






Privacy Overview 
Questo sito, come la maggior parte dei siti web, utilizza cookie, anche di terze parti, per migliorare la tua esperienza di navigazione e raccogliere informazioni sull'utilizzo del sito stesso.

 





								Necessary							


Necessary

Always Enabled




									I cookie funzionali contribuiscono al buon funzionamento del nostro sito e ti permettono di creare un account, accedere e gestire le tue prenotazioni. Questi cookie ricordano la lingua e la valuta che hai selezionato, le tue ricerche passate e altre preferenze. Si tratta di cookie tecnici che devono essere attivati per poter utilizzare il nostro sito e i nostri servizi.
CookieDurationDescription_GRECAPTCHA5 months 27 daysThis cookie is set by the Google recaptcha service to identify bots to protect the website against malicious spam attacks.cookielawinfo-checkbox-advertisement1 yearSet by the GDPR Cookie Consent plugin, this cookie is used to record the user consent for the cookies in the "Advertisement" category .cookielawinfo-checkbox-analytics11 monthsThis cookie is set by GDPR Cookie Consent plugin. The cookie is used to store the user consent for the cookies in the category "Analytics".cookielawinfo-checkbox-functional11 monthsThe cookie is set by GDPR cookie consent to record the user consent for the cookies in the category "Functional".cookielawinfo-checkbox-necessary11 monthsThis cookie is set by GDPR Cookie Consent plugin. The cookies is used to store the user consent for the cookies in the category "Necessary".cookielawinfo-checkbox-others11 monthsThis cookie is set by GDPR Cookie Consent plugin. The cookie is used to store the user consent for the cookies in the category "Other.cookielawinfo-checkbox-performance11 monthsThis cookie is set by GDPR Cookie Consent plugin. The cookie is used to store the user consent for the cookies in the category "Performance".pll_language1 yearThe pll _language cookie is used by Polylang to remember the language selected by the user when returning to the website, and also to get the language information when not available in another way.viewed_cookie_policy11 monthsThe cookie is set by the GDPR Cookie Consent plugin and is used to store whether or not user has consented to the use of cookies. It does not store any personal data. 






								Performance							


Performance





									Performance cookies are used to understand and analyze the key performance indexes of the website which helps in delivering a better user experience for the visitors.
								






								Marketing							


Marketing





									Questo sito e i nostri partner di fiducia usano cookie di terze parti per mostrare messaggi pubblicitari personalizzati su questo sito e su altri siti in base alla tua cronologia di navigazione. Questi cookie vengono usati per integrare i social media sul nostro sito, in modo che tu possa mettere "mi piace" sulle nostre pagine o sui nostri prodotti e condividerli sui social.
CookieDurationDescriptionVISITOR_INFO1_LIVE5 months 27 daysA cookie set by YouTube to measure bandwidth that determines whether the user gets the new or old player interface.YSCsessionYSC cookie is set by Youtube and is used to track the views of embedded videos on Youtube pages.yt-remote-connected-devicesneverYouTube sets this cookie to store the video preferences of the user using embedded YouTube video.yt-remote-device-idneverYouTube sets this cookie to store the video preferences of the user using embedded YouTube video.yt.innertube::nextIdneverThis cookie, set by YouTube, registers a unique ID to store data on what videos from YouTube the user has seen.yt.innertube::requestsneverThis cookie, set by YouTube, registers a unique ID to store data on what videos from YouTube the user has seen. 






								Others							


Others





									Other uncategorized cookies are those that are being analyzed and have not been classified into a category as yet.
								






								Analytics							


Analytics





									I cookie analitici ci aiutano a capire in che modo i clienti come te utilizzano questo sito. In questo modo possiamo migliorare il sito, le app e le comunicazioni e assicurarci di offrire sempre contenuti interessanti e rilevanti.
CookieDurationDescription_gat_gtag_UA_209986505_11 minuteSet by Google to distinguish users.CONSENT2 yearsYouTube sets this cookie via embedded youtube-videos and registers anonymous statistical data. 












SAVE & ACCEPT


Powered by 





















        mobile-menu-eng 


Home







Defence center







Threat intelligence







Solutions



     Solutions  


Before Attack



     Before Attack  


Technologies



     Technologies  


Threat intelligence







DNS Defence







Kanwa







Genku







Digital Surveillance




 Back 



Services



     Services  


Infrastructure & Systems compliance







Scam Protection







SCADA Security







Early Warning







Wi-Fi Infrastructure Assessment







Vulnerability Assessment







Adversarial Simulation







Threat Hunting







SIEM management







Security Infrastructure Assessment (SIA)







Penetration Testing




 Back 
 Back 



During Attack



     During Attack  


Technologies



     Technologies  


Threat intelligence







Kanwa







Yomi







Email Protection




 Back 



Services



     Services  


IRT (Incident Response Team)







Managed Advanced Threat Protection







KickBack Attack




 Back 
 Back 



After Attack



     After Attack  


Technologies



     Technologies  


Threat intelligence







Kanwa




 Back 



Services



     Services  


Wi-Fi Infrastructure Assessment







Threat Hunting




 Back 
 Back 
 Back 



Blogs



     Blogs  


Yoroi Blog







Marco Ramilli Blog




 Back 



Downloads







About us







Contacts







English



     English  


Italiano




 Back 
© 2020 credits: SimpleNetworks     menu-it 


Defence center







Solutions



    Back   Solutions  


Before Attack



    Back   Before Attack  


Technologies



    Back   Technologies  


Threat intelligence







DNS Defence







Kanwa







Genku







Digital Surveillance








Services



    Back   Services  


Infrastructure & Systems compliance







Scam Protection







SCADA Security







Early Warning







Wi-Fi Infrastructure Assessment







Vulnerability Assessment







Adversarial Simulation







Threat Hunting







SIEM management







Security Infrastructure Assessment (SIA)







Penetration Testing









During Attack



    Back   During Attack  


Technologies



    Back   Technologies  


Threat intelligence







Kanwa







Yomi







Email Protection








Services



    Back   Services  


IRT (Incident Response Team)







Managed Advanced Threat Protection







KickBack Attack









After Attack



    Back   After Attack  


Technologies



    Back   Technologies  


Threat intelligence







Kanwa








Services



    Back   Services  


Wi-Fi Infrastructure Assessment







Threat Hunting










Blogs



    Back   Blogs  


Yoroi Blog







Marco Ramilli Blog








Home







Downloads







About us









linkedin





facebook



pinterest



youtube



rss



twitter



instagram





facebook-blank



rss-blank



linkedin-blank



pinterest



youtube



twitter



instagram




































