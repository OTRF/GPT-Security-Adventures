# Reference for threat actor for "TA505, Graceful Spider, Gold Evergreen"

**Title**: The Stealthy Email Stealer in the TA505 Arsenal - Yoroi

**Source**: https://blog.yoroi.company/research/the-stealthy-email-stealer-in-the-ta505-arsenal/

## Content







The Stealthy Email Stealer in the TA505 Arsenal - Yoroi










































































 












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






The Stealthy Email Stealer in the TA505 Arsenal
	05/16/2019
Introduction
During the last month our Threat Intelligence surveillance team spotted increasing evidence of an operation intensification against the Banking sector. In fact, many independent researchers pointed to a particular email attack wave probably related to the known TA505 hacking group, active since 2014 and focusing on Retail and Banking companies. The group is also known for some evasive techniques they put in place over time to avoid the security controls and penetrate corporate perimeters with several kinds of malware, for instance abusing the so called LOLBins (Living Off The Land Binaries), legit programs regularly used by victim, or also the abuse of valid cryptographically signed payloads.
Figure 1. Attack campaign spotted in the wild.
Investigating and tracking their operations during April and May we detected an interesting tool was delivered through the victim machine. Just after the opening of malicious documents and the installation of FlawedAmmy RAT implants, the group used to deploy a particular credential stealing software, part of their arsenal, revealing details of their recent operation. 
Figure 2. Attack campaign spotted in the wild.
Technical Analysis
The piece of malware under analysis were downloaded from “bullettruth[.com/out[.exe”, it was executed into the victim machines after the establishment of the infection. 
Sha256f3e8f68c31c86d431adea1633c875c32434a42aee5ed70af74af5c5e5aa58883ThreatCustom Email StealerBrief DescriptionExecutable of the email stealerSsdeep12288:tlICpzmDFPJ+d7SQX5PsTrKjL43vNa77pu:XI+mDFx+d7vcrKv43X
Figure 3: Malware Signature by SLON LTD
Firstly, we noticed this secondary component was well protected against antivirus detection, in fact the PE file was signed by Sectigo in the first half of May, one of the major Russian Certification Authority. Analyzing the trust chain we found the attackers were relying on cryptographic keys released to a UK company named  SLON LTD. At this time, we have no evidence to hypothesize it could be victim of previous hacks or not.
Anyway, a static inspection of the binary revealed that the malware has a quite high entropy level, suggesting it may be packed. 
Figure 4: Malware suspicious entropy level
Dynamically executing the malware, more information about its behaviour is revealed. The malicious executable is substantially an email stealer, in fact, the only purpose is to retrieve all the emails and passwords accounts present inside the victim machine. After executing the information gathering routine, the malware sends to its C2 all the retrieved emails and passwords:
Figure 5: HTTP POST communication
The interesting thing about the communication with the C2 is the fact that there is no encryption: the data harvested are sent to the C2 in JSON format. Investigating the attacker infrastructure we noticed interesting information such as the information of the stolen emails through our Digital Surveillance systems.
In order to retrieve more details about this Email Stealer, the analysis has moved into debugging and disassembling. As previously mentioned, the malware sample is heavily obfuscated and packed. However, by letting the malware execute itself within a debugger, we were able to extract the unpacked payload of the malware.
Figure 6: Static information about the packed sample (on the left) and the unpacked one (on the right)
As shown by the above figure, we notice a peculiarity of these two components: while the packed sample is compiled in Microsoft Visual C++ version 6.0, the unpacked one is compiled in Microsoft Visual C++ version 8. At this point, we deepen the analysis on the extracted payload. However, we are not able to execute it, because it always references many memory addresses of the original one. So, we carry on static analysis on the extracted sample.
As previously described, the malware’s principal purpose is to iterate through the filesystem looking for email accounts.. The first step is to check whether the “outlook.exe” process is running and, in this case it kills the process.The malware iterate through user processes with Process32FirstW API and then kill it with TerminateProcess:
Figure 7: Outlook process search routine
The extracted payload does not present any type of code obfuscation of other types. In fact the C2 server and the path is not encoded:
Figure 8: C2 connection routine
The last routine being analyzed is the credential harvesting inside the entire filesystem. 
Apart from the routine that searches for the email account registered in Outlook and Thunderbird clients (as shown in Figure 7), there is another one which scans the filesystem looking for hardcoded extensions, then, if one of them is found, a reference to the found file is conserved inside the %TEMP% directory. At this point, all the gathered email accounts are sent to the server and then erasing  all traces of itself from the infected machine, in fact, the malware creates a simple batch script which delete itself and all the tracks of infection.
Figure 9: Autodeletion batch script
Analysis of Exposed Emails
In this paragraph are shown some statistics about the harvested emails in the attack campaign, recovered during surveillance and hunting operations. So we decided to create a graph in which sort the most frequent TLD occurrences of all the stolen data.
Figure 10: Distribution of TLD
As seen in the graph above, the most frequent TLD is .com with 193.194 occurrences, following .kr with 102.025 occurrences, .cn with 26.160 occurrences, it with 6.317 occurrences and so on. To better visualize the macro-locations involved in this exposure we built a heatmap showing the geographical distribution of the TOP 100 countries referenced in the TLDs.
Figure 11: Geolocation of emails TLD exposure
The heatmap shows the less-affected countries with a greenish color, on the contrary, the most-affected ones tend to an orange or red-tinged color. The first thing that emerges from these 2 distributions is that this specific threat seems not to be targeted, in fact, the diffusion is almost global with some red or orange zones in UK, Italy, Republic of Korea, China, Germany, Hungary, Taiwan, Japan, India and Mexico. All these countries exceeded the thousand occurrences. 
Conclusion
Nowadays, the email accounts are an effective source of revenue for the cyber criminals. In fact all these information can be used to spread other malware through phishing campaigns, to perform BEC attacks (Business Email Compromise) and also to try credential stuffing attacks. 
Evan a simple Info-Stealer malware like this one could be a dangerous threat, especially if used by organized groups  in conjunction with other malware implants. In fact, as reported by the independent researcher Germán Fernández Bacian too, this Email Stealer has been recently used by the infamous TA505 hacking group. This link means, with good confidence, the exposed data, full email accounts in some cases and email contacts in general, are now available to a cyber-criminal group who launched targeted attacks against Banks and Retail industries in the near past.
Indicators of Compromise
Dropurl:bullettruth[.com/out[.exeC2:nettubex[.top/es/es[.php178.48.154.385.253.53.236 87.241.136.1 197.255.225.249 95.140.195.178 186.74.208.84 86.61.75.99 86.101.230.109 89.47.94.113 130.204.181.90 78.90.243.124Hash:104dae7457c10b7fe6c42a335f2a57ff708ff20d70597fbaa5fe0083c1c628c7e4b40cba02dc1de1a1c2ed2001d39a87c476c11ca08f09a80fd3f1fbaae0daebf3e8f68c31c86d431adea1633c875c32434a42aee5ed70af74af5c5e5aa58883899bfac53c3439a7ea68f9a5bbff2733ebf7b9158f18ef5d03360a09b18b5e0d
Yara Rules 
import "pe"
rule EmailStealer_201905 {
meta:
	description = "Yara rule for EmailStealer"
	author = "Cybaze - Yoroi ZLab"
	last_updated = "2019-05-14"
	tlp = "white"
	category = "informational"
strings:
	$a1 = { 80 F2 F3 00 56 53 A7 }
	$a2 = { 4D 26 9A 00 56 4B AC 55 } 
	$a3 = { 1C 4A 77 00 00 89 B4 B7 }


condition:
	uint16(0) == 0x5A4D and pe.number_of_sections == 3 and all of them
}

Searched Extensions
.msf; .dat; .pst; .ost; .asp; .cdd; .cpp; .doc; .docm; .docx; .dot; .dotm; .dotx; .epub; .fb2; .gpx; .ibooks; .indd; .kdc; .key; .kml; .mdb; .mdf; .mobi; .mso; .ods; .odt; .one; .oxps; .pages; .pdf; .pkg; .pl; .pot; .potm; .potx; .pps; .ppsm; .ppsx; .ppt; .pptm; .pptx; .ps; .pub; .rtf; .sdf; .sgml; .sldm; .snb; .wpd; .wps; .xar; .xlr; .xls; .xlsb; .xlsm; .xlsx; .xlt; .xltm; .xltx; .xps; .3dm; .aspx; .cer; .cfm; .chm; .crdownload; .csr; .css; .download; .eml; .flv; .htaccess; .htm; .html; .jnlp; .js; .jsp; .magnet; .mht; .mhtm; .mhtml; .msg; .php; .prf; .rss; .srt; .stl; .swf; .torrent; .url; .vcf; .webarchive; .webloc; .xhtml; .xul; .asf; .asm; .cgi; .class; .cs; .dtd; .fla; .ged; .gv; .icl; .java; .jse; .json; .lua; .mb; .mod; .msp; .obj; .po; .ps1; .py; .sh; .sln; .so; .sql; .ts; .vbe; .vbs; .vc4; .vcproj; .vcxproj; .wsc; .xcodeproj; .xsd; .apt; .err; .log; .pwi; .sub; .ttf; .tex; .text; .txt; .accdb; .b2; .crypt; .crypt5; .crypt6; .crypt7; .crypt8; .crypt12; .db; .dbf; .dbx; .sis; .awb; .bin; .cdi; .cdr; .csv; .eap; .efx; .gam; .gbr; .gtp; .mpp; .msc; .mts; .otf; .nbk; .nbp; .ndb; .prj; .rtp; .sav; .scppy; .tax2010; .tbl; .tmp; .vcd; .xml; .xsl; .xslt; .bak; .dmp; .gho; .ghs; .v2i; .zip; .asx; .iff; .inf; .temp; .ai; .aif; .amr; .apk; .bp1; .ccd; .cdw; .dds; .dmg; .dxf; .ext; .ics; .ini; .m4p; .max; .md0; .mng; .mp3; .mpa; .msu; .nrg; .pak; .part; .pkpass; .psd; .rnd; .rom; .spl; .swb; .svg; .xla; .application; .appref; .cfg; .conf; .config; .cpl; .cue; .deskthemepack; .diagcfg; .ds_store; .iso; .pdi; .plist; .reg; .scr; .theme; .themepack; .thm
This blog post was authored by Luigi Martire, Davide Testa, Antonio Pirozzi and Luca Mella of Cybaze-Yoroi Z-LAB
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




































