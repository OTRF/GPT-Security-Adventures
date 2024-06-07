# Reference for threat actor for "TA505, Graceful Spider, Gold Evergreen"

**Title**: TA505 is Expanding its Operations - Yoroi

**Source**: https://blog.yoroi.company/research/ta505-is-expanding-its-operations/

## Content







TA505 is Expanding its Operations - Yoroi










































































 












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






TA505 is Expanding its Operations
	05/29/2019
Introduction
In the last few days, during monitoring activities, Yoroi CERT noticed a suspicious attack against an Italian organization. The malicious email contains a highly suspicious sample which triggered the ZLAB team to investigate its capabilities and its possible attribution, discovering a potential expansion of the TA505 operation. The threat group is also known for its recent attack campaign against Bank and Retail business sectors,  but the latest evidence indicates a potential expansion of its criminal operation to other industries too. 
Technical Analysis
Hash0c88e285b6fc183c96b6f03ca5700cc9ca7c83dfccc6ad14a946d1868d1cc273ThreatDropperBrief DescriptionExcel file with malicious macroSsdeep3072:Mc38TehYTdeHVhjqabWHLtyeGxml8/dgzxXYhh3vVYwrq 8/P5HKuPF1+bkm13Kkf:B38TehYTdeHVhjqabWHLty/xml8/dgNr
Table 1. Information about initial dropper
The intercepted attack starts with a spear phishing email embedding a spreadsheet. The document is weaponized with malicious macro code triggered when the user opens the document to see the content under the obfuscated view. 
Figure 1. XLS document
To understand its capabilities, the macro code has been isolated and analyzed in detail. Part of the macro’s content is shown in the following figure.
Figure 2. Part of extracted macro
Surprisingly, the source code is composed by more than 1600 lines of code and it is highly obfuscated. Paying more attention during the code analysis, we discovered that it is full of junk instructions used to declare and initialize variables never used, as shown in Figure 2. Only a small portion of this code is actually used to start the infection, the rest is just junk code.
Figure 3. Example of junk instructions used in macro 
Once the macro is executed, the malware downloads two files from “kentona[.su”, using an SSL encrypted communication, and stores them in “C:\Users\Public” path: “rtegre.exe” and “wprgxyeqd79.exe”. 
Hashaafa83d5e0619e69e64fcac4626cfb298baac54c7251f479721df1c2eb16bee7ThreatGenericBrief DescriptionTrojan/Downloader (Executable file)Ssdeep12288:3gL3qJxG5hfNV6oYYbDRcY4KhbmwPMCchbjBxwhrVm HAyzNkyRJK7hRMCQ:3mqkhfzYZY4kmgsbdm2HAENk0K7Dm
Table 2. Information about “rtegre.exe” downloaded from “kentona[.su”
Hash6f1a8ee627ec2ed7e1d818d32a34a163416938eb13a97783a71f9b79843a80a2ThreatTrojanBrief DescriptionSFX (self-extracting archive) (Executable file)Ssdeep49152:sIWB74MncmEWy4i1LkjoAwG2PI/mfqtftvMKcr+7Ao95 xQW1vB38PELaacVzWTV3:sICtHsJoMAwG
Table 3. Information about “wprgxyeqd79.exe” (SFX) downloaded from “kentona[.su”
Figure 4. Files contained in “wprgxyeqd79.exe” (SFX)
The “wprgxyeqd79.exe” sample actually is a Self Extracting Archive (SFX/SFA) containing four files designed to be extracted in the %TEMP% folder. After that, it executes “exit.exe” which launches the “i.cmd” batch script.  
Figure  5. “i.cmd” script contained in “pasmmm.exe”
This new script performs a ping to “www[.cloudflare[.com” for three times with a delay of 3000ms, testing the connectivity of the victim machine. If the host is successfully reached, the script renames a file named “kernel.dll”, obviously not the real one, in “uninstall.exe”, another misleading name. Then it invokes the renamed executable and runs it passing a series of parameter: “uninstall.exe x -pQELRatcwbU2EJ5 -y” 
These parameters are needed to self-decrypt the “uninstall.exe” file which is again another SFX archive. The “-p” parameter, indeed, specify the password of the archive to be extracted. The crucial file, at this point of the infection, is the SFX executable named “uninstall.exe”. It has a structure similar to previous “wprgxyeqd79.exe” file: two of their files have the same name, but the content of this new SFX is extracted in the “%ALLUSERSPROFILE%\Windows Anytime Upgrade” directory. 
Figure 6. Files contained in “uninstall.exe” (SFX)
Another time, the execution flow moves from “exit.exe to “i.cmd”. The script is quite different from the previous one: it guarantees its persistence on the victim machine through the setting of “HKCU\Software\Microsoft\Windows\CurrentVersion\Run” registry key, creating a new entry named “Windows Anytime Upgrade” which points to “winserv.exe”, just stored into the same folder. Thus, the script provides to run “winserv.exe”.
Figure 7. “i.cmd” script contained in “uninstall.exe”
An interesting part of the script is the continuous killing of every “rundll32.exe” process running into the victim machine, generates a huge amount of noise, as visible in the following process explorer view.
:Repeattaskkill /f /im “rundll32.exe” || goto :Repeat

Figure 8. List of malware’s processes 
Anyway, just before the kill loop, the real malicious payload is executed: the  “winserv.exe” file. Analyzing it in depth, we discover it actually is the RMS (Remote Manipulator System) client by TektonIT, encrypted using the MPress PE compressor utility, a legitimate tool, to avoid antivirus detection.
Figure 9. Information about MPress packer used in “winserv.exe” payload
TektonIT RMS acts as a remote administration tool, allowing the attacker to gain complete access to the victim machine. Together with the RMS executable, there is another file named “settings.dat” containing the custom configuration prepared by the attacker. It contains information like: 
Server address and port the client will connect toThe password chosen by the attacker for the remote accessThe ID associated to the victim client
All these information are automatically loaded by the RMS executable and firstly stored in the registry key “HKCU\Software\tektonik\Remote MANIPULATOR System\Host\parameters”. At the next startup, the software will directly load the configuration from the just created key. 
Figure 10. Registry key set by “winserv.exe” (on the left); “settings.dat” file (on the right)
The client establishes a new connection with the remote command and control server hosted on a Bulgarian remote host 217.12.201.159, part of a Virtual Dedicated Server subnet of the AS-21100, operated by ITL LLC.
Figure 11. C2’s parameters
The attack is composed by a complex flow we synthesize in the following scheme:
Figure 12. Complete infection chain
The TA505 Connection
After the reconstruction of the full infection chain, we noticed strong similarities with a recent spear-phishing attack campaign against an unspecified US retail company. The attack, as stated by CyberInt, leveraged a command and control server located in Germany related to the TA505 actor: a very active group involved in cyber-criminal operation all around the world, threatening a wide range of high profile companies, active since 2014.
Figure 13. Comparison between infection chains
The comparison of the infection chains reveals in both cases the attacker used a couple of SFX stages to deploy the “RMS” software: a legitimate remote administration tool produced by the Russian company “TektonIT”. The tool is able to grant remote access and full, direct control of the infected machine to the group. Also, some code pieces are directly re-used in the  analyzed campaigns, such as the “i.cmd” and “exit.exe” files, and, at the same time, some new components have been introduced, for instance the “rtegre.exe” and the “veter1605_MAPS_10cr0.exe” file. 
During the analysis, we also noticed the “veter1605_MAPS_10cr0.exe” file slightly changed run after run, a few hours after the initial discovery the infection chain dropped it with different icons, different suffix, from “cr0” to “cr24”, and appendix from “veter1605_” to “veter2005_”. This may indicate the campaign is still ongoing.
Conclusion
The TA505 group is one of the most active threat groups operating since 2014, it has traditionally targeted Banking and Retail industries, as we recently documented during the analysis of the “Stealthy Email Stealer” part of their arsenal. The peculiarity of this recent attack wave is it actually hit a company not strictly in the Banking or Retail sector, as they recently did, suggesting the threat group could be potentially widening their current operations. 
Indicators of Compromise
Dropurl:kentona[.su - 47.245.58.124hxxps://kentona[.su/xpepriubgpokejifuv7efrhguskdgfjn/ananas.exehxxps://kentona[.su/xpepriubgpokejifuv7efrhguskdgfjn/pasmmm.exeC2:217[.12.201.159Persistence:HKCU\Software\Microsoft\Windows\CurrentVersion\RunHash:0c88e285b6fc183c96b6f03ca5700cc9ca7c83dfccc6ad14a946d1868d1cc2731ee1ba514212f11a69d002005dfc623b1871cc808f18ddfa2191102bbb9f623bfd701894e7ec8d8319bc9b32bba5892b11bdf608c3d04c2f18eff83419eb6df0c69ce39ac3e178a89076136af7418c6cb664844b0ce5cb643912ed56c373a08a5310c2397ba4c783f7ee9724711a6da9b5c603b5c9781fff3407b46725e338b3aafa83d5e0619e69e64fcac4626cfb298baac54c7251f479721df1c2eb16bee7210bb55664d291d82b94b9cea6fcf41029eded9eca6e7fe7b7d58715407a07032b5eefc4bc2d34cbe5093332c47b5405cf5c32e8156767fc8bc9ddd9cdcf3018609b0a416f9b16a6df9b967dc32cd739402af31566e019a8fb8abdf3cb573e306f1a8ee627ec2ed7e1d818d32a34a163416938eb13a97783a71f9b79843a80a2
Yara Rules
rule excel_dropper {
meta:
    description = "Yara rule for excel dropper"
    author = "Cybaze - Yoroi ZLab"
    last_updated = "2019-05-22"
    tlp = "white"
    category = "informational"
strings:
    $a1 = { 98 C3 AB F0 E7 F3 BD F4 }
    $a2 = { 41 6E D5 7E F0 10 AB A7 }
    $a3 = "gxbgarjktzyu"
    $a4 = "Bob Brown"

condition:
    all of them
}

import "pe"
rule pasmmm_exe {
meta:
    description = "Yara rule for pasmmm SFX archive"
    author = "Cybaze - Yoroi ZLab"
    last_updated = "2019-05-22"
    tlp = "white"
    category = "informational"
strings:
    $a1 = { 1C Cf 43 39 C8 32 B4 B0 }
    $a2 = { 60 6C B8 7C 5F FA }
    $a3 = "LookupPrivilege"
    $a4 = "LoadBitmap"

condition:
    pe.number_of_sections == 6 and all of them
}

import "pe"
rule uninstall_exe {
meta:
    description = "Yara rule for uninstall SFX archive"
    author = "Cybaze - Yoroi ZLab"
    last_updated = "2019-05-22"
    tlp = "white"
    category = "informational"
strings:
    $a1 = { E8 68 BA 01 00 51 }
    $a2 = { 58 E9 8B C6 4F 6F 7A }
    $a3 = { D9 4E D5 FA D4 34 }

condition:
    pe.number_of_resources == 24 and all of them
}

import "pe"
rule winserv_exe {
meta:
    description = "Yara rule for winserv backdoor"
    author = "Cybaze - Yoroi ZLab"
    last_updated = "2019-05-22"
    tlp = "white"
    category = "informational"
strings:
    $a1 = "MPRESS1"
    $a2 = { 90 C4 73 05 E6 92 }
    $a3 = { E9 64 4B 56 3F EC }
    $a4 = { 10 EF D0 E1 36 E1 14 3C }

condition:
    all of them and pe.version_info["CompanyName"] contains "tox"
}

import "pe"
rule veter_random {
meta:
    description = "Yara rule for veter_trojan"
    author = "Cybaze - Yoroi ZLab"
    last_updated = "2019-05-22"
    tlp = "white"
    category = "informational"
strings:
    $a = { 5E C2 04 00 F6 44 24 04 01 56 }
    
    $b1 = { 01 8B 02 8B 48 04 03}
    $b2 = { 4A 3B C2 7E 08 8B C2 }
    
    $c1 = { E8 83 CA 04 89 55 E8 }
    $c2 = { 1F DF 70 07 22 84 82 }

condition:
    $a and (($b1 and $b2 and pe.version_info["CompanyName"] contains "Miranda") or ($c1 and $c2 and pe.version_info["InternalName"] contains "DrldwgRom"))
}

This blog post was authored by Davide Testa, Antonio Farina and Luca Mella of Cybaze-Yoroi Z-LAB
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




































