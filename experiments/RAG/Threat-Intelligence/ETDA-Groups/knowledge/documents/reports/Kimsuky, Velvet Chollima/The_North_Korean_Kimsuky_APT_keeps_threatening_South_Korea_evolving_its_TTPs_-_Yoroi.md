# Reference for threat actor for "Kimsuky, Velvet Chollima"

**Title**: The North Korean Kimsuky APT keeps threatening South Korea evolving its TTPs - Yoroi

**Source**: https://blog.yoroi.company/research/the-north-korean-kimsuky-apt-keeps-threatening-south-korea-evolving-its-ttps/

## Content







The North Korean Kimsuky APT keeps threatening South Korea evolving its TTPs - Yoroi











































































 












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






The North Korean Kimsuky APT keeps threatening South Korea evolving its TTPs
	03/03/2020
Introduction
Recently we have observed a significant increase in state-sponsored operations carried out by threat actors worldwide. APT34, Gamaredon, and Transparent Tribe are a few samples of the recently uncovered campaigns, the latter was spotted after four years of apparent inactivity. Cybaze-Yoroi ZLab decided to study in depth a recent threat attributed to a North Korean APT dubbed Kimsuky.
Figure 1: tweet on 28 February 2020
The Kimsuky APT group has been analyzed by several security teams. It was first spotted by Kaspersky researcher in 2013, recently its activity was detailed by ESTsecurity.
We decided to analysed the activity of the group after noticing a tweet of the user “@spider_girl22” in February 28th 2020.
Technical Analysis
Unlike other APT groups using long and complex infection chains, the Kimsuky group leverages a shorter attack chain, but at the same time, we believe it is very effective in achieving a low detection rate.
The infection starts with a classic executable file with “scr” extension, an extension used by Windows to identify Screensaver artifacts. In the following table are reported some information about the sample.
Hash757dfeacabf4c2f771147159d26117818354af14050e6ba42cc00f4a3d58e51fThreatKimsuky loaderBrief DescriptionScr file, initial loaderSsdeep12288:APWcT1z2aKqkP/mANd2JiEWKZ52zfeCkIAYfLeXcj6uuLl:uhT1z4q030JigZUaULeXc3uLl
Table 1: Information about initial loader with .scr extension
Upon execution, the malware writes a file named “<random_name>.tmp.db” inside the “%AppData%\Local\Temp” path through the usage of the Microsoft Utility “regsvr32.exe”.

Figure 2: Written file (AutoUpdate.dll) in the “%AppData%\Local\Temp” path
Despite the “.db” extension, the written file is actually a well formed DLL that acts as the second stage of the malware infection. Static information of DLL are shown below:
Hashcaa24c46089c8953b2a5465457a6c202ecfa83abbce7a9d3299ade52ec8382c2ThreatKimsuky second stageBrief DescriptionDLL used by the Kimsuky group as second stageSsdeep6144:6lhe64TNUalJMRRfS5mABlakVxOfLnePfcNl6GwUDuL/:6zfeCkIAYfLeXcj6uuL
Table 2: AutoUpdate.dll Information
The dll is then copied into the folder “%AppData%\Roaming\Microsoft\Windows\Defender\” and it is renamed into “AutoUpdate.dll”. 
The “AutoUpdate.dll” library then gains persistence by setting the following registry key “HKCU\Software\Microsoft\Windows\CurrentVersion\RunOnce\WindowsDefender”. The name and the path used by the attacker is absolutely tricky, because they reference to Windows Defender:

Figure 3: registry key set for persistence .
Furthermore, exploring the content of the folder “%AppData%\Local\Temp” path, we observed another temporary file created and immediately removed dubbed “<random_name>.tmp.bat”. By analyzing its contents, we noticed that it is used to delete the initial artifact (scr) and file itself.

Figure 4: Content of the bat script.
In order to hide the malicious operation and avoid raising suspicion, a legit document is created in the same folder containing the “.scr” file, the document is named “이력서 양식.hwp”. Translating its name from Korean to English language, is possible to obtain the “CV Form” string. The name and other information about the document are the following:
Hashd21523b7b8f6584305a0a6a83cd65c8ce0777a42ab781c35aa06c46c91f504b4ThreatKimsuky legit documentBrief DescriptionLegit document used to divert attention on the malware in “hwp” extensionSsdeep192:zXEKVs7kRvm+1FsO2ui/VpIkCnH5QVSV9VahhU:r3YkA+1aJukWQVS9avU
Table 3: Information about legit document with “.hwp” extension
As implied by the file name (CV Form), the document contains a CV form with empty fields, as shown in the following figure.

Figure 6: Legit document overview
Bypassing AV Detection
An interesting behaviour is the “explorer.exe” injection performed by the “AutoUpdate.dll” in order to avoid AVs detection. Digging in the malicious code, it is possible to see the methods used to perform this operation. First of all, the malware sets the right privileges, as reported in the following image.

Figure 7: Privilege set for the correct injection
Once obtained the necessary privileges, the malware is able to proceed with the injection. As described by the analysis published by elastic, the malware writes the path to its malicious DLL in the virtual address space of another process through the “VirtualAllocEx” function. In this case, the target process is “explorer.exe”, it ensures the remote process loads it by creating a remote thread inside it. 
To perform these operations, first of all the malware needs to know the Process ID of the target, this is performed through the navigation of all processes tree. This task can be executed using the Tool Help Library Windows API family using CreateToolhelp32Snapshot(), Process32First(), and Process32Next() API. Then, the malware calls VirtualAllocEx() to allocate a space to write the path to the malicious DLL, then it calls WriteProcessMemory()  to write the DLL path inside the allocated memory. 
After that, the malware calls the CreateRemoteThread() API to link the thread newly created to the host process (explorer.exe). Parts of the described logic are shown in the below figure:

Figure 8: API used for injection
Two components are implanted in the “explorer.exe” process. In the following tables are presented some information about the two DLLs extracted.
Hashbbad65136d73cbd5262bc88571677b5434ceb54fc1103f2133757dae2ec4b47bThreatInjected DLLBrief DescriptionFirst injected DLLSsdeep3072:AFSYAyju5JpkC7xfYZo9cPqvTV+ql4yFa+zB+K+H/kocFAQUG5R:AFJ0qC7xAZliT004+p10fkoefUG5
Table 4: Information about first DLLinjected  in explorer.exe process
Hash817ef0d9d3584977d1114b7e92012b653d339434a90967cbe8016899801f3751ThreatInjected DLLBrief DescriptionSecond injected DLLSsdeep3072:AFSYAyju5JpkC7xfYZo9cPqvTV+ql4yFa+zo+K+H/kocFAnRG5R:AFJ0qC7xAZliT004+p00fkoegRG5
Table 5: Information about second DLL injected in explorer.exe process 
Comparing the ssdeep of the two DLLs is possible to notice several overlaps between the two libraries, a circumstance that confirms a high “similarity” between them. Below are highlighted the different portions of the hash:
3072:AFSYAyju5JpkC7xfYZo9cPqvTV+ql4yFa+z * +K+H/kocFAnRG5R:AFJ0qC7xAZliT004+p * 0fkoe * RG5
There are tiny differences between the DLLs as shown below performing a simple binary diffing analysis.
Due to these differences between the two DLLs, we decided to continue the analysis on one of them. Digging into the DLL, we notice that every time a function has to be performed by the malware, it relies on a recurrent decryption routine, which decodes the strings containing the actual instruction and executes it. An example of the decryption routine is reported in the following figure on top right:

Figure 10: Decryption flow graph
Figure 11: Parts of subroutines used to perform network communication
Every 15 minutes, the malware contacts the C2 (suzuki.]datastore.]pe.]hu) and sends back the information about the compromised machine, as reported in the previous figure. In particular, three HTTP requests are made using different URLs paths and different User-Agent fields for each request.  An example of the C2 registration is the following:

Figure 12: Network traffic performed by the malware 
Conclusion
During our Threat Intelligence activities, we discovered a new malware implant compatible with the previous campaigns of Kimsuky APT actor. According to the ESTsecurity firm, the initial dropper contains two malicious resources embedding the malicious DLLs, however, in our sample there aren’t.
Despite these little differences, we can affirm with good confidence that the Threat Actor is Kimsuky due to strong similarities with the TTPs.
Indicator of Compromise
Hashes:757dfeacabf4c2f771147159d26117818354af14050e6ba42cc00f4a3d58e51fcaa24c46089c8953b2a5465457a6c202ecfa83abbce7a9d3299ade52ec8382c2bbad65136d73cbd5262bc88571677b5434ceb54fc1103f2133757dae2ec4b47b817ef0d9d3584977d1114b7e92012b653d339434a90967cbe8016899801f3751C2:suzuki.]datastore.]pe.]huPersistence:HKCU\Software\Microsoft\Windows\CurrentVersion\RunOnce\WindowsDefender
Yara Rules
import "pe"
rule loader {
    meta:
      description = "Yara rule for the initial loader SRC"
      author = "Yoroi - ZLab"
      last_updated = "2020-03-02"
      tlp = "white"
      category = "informational"
    
strings:
      	$a1 = " goto Repeat1"
		$a2 = {84 58 43 F4 39 1B 96 32 E4 2D 63}
		$a3 = {89 04 4D 30 7A 05 10 41 EB E8 8B}
		$a4 = {80 A1 B2 F7 15 DE F0 7E 35 75}
		$a5 = {9C 0E 57 4C 77 B1 0E 06 08 5E}

	  
    condition:
      uint16(0) == 0x5A4D and pe.number_of_sections == 5 and 3 of ($a*) 
}

import "pe"
rule AutoUpdate_dll {
    meta:
      description = "Yara rule for the AutoUpdate_dll"
      author = "Yoroi - ZLab"
      last_updated = "2020-03-02"
      tlp = "white"
      category = "informational"
    
strings:
      	$a1 = {48 8B 3F 48 83 78 18 10 72}
		$a2 = {36 42 35 45 35 41 42 33 42 41 39}
		$a3 = { DD E7 FE DA C6 F7 F9 8D 7D F9 }
		$a4 = "1#SNAN"
		$a5 = "d$4D9L$t"
		$a6 = "DllRegisterServer"
		$a7 = "DllUnregisterServer"
	  
    condition:
      uint16(0) == 0x5A4D and pe.number_of_sections == 6 and (4 of ($a*)) 
}

import "pe"
rule injectedDLL {
    meta:
      description = "Yara rule for the injected DLL"
      author = "Yoroi - ZLab"
      last_updated = "2020-03-02"
      tlp = "white"
      category = "informational"
    
strings:
      	$a1 = {41 80 3E 5E 89 45 A4 75 08 49}
		$a2 = {60 03 50 02 30 58 68 01 00 70}
		$a3 = {98 F7 02 00 7B 44 00 00 91 44}
		$a4 = "/?m=b&p1="
		$a5 = "&p2=b"
		$a6 = "/?m=a&p1="
		$a7 = "AUAVAWH"
	  
    condition:
      uint16(0) == 0x5A4D and pe.number_of_sections == 6 and (4 of ($a*)) 
}

rule legit_DOC {
    meta:
      description = "Yara rule for the Legit DOC"
      author = "Yoroi - ZLab"
      last_updated = "2020-03-02"
      tlp = "white"
      category = "informational"
    
strings:
      	$a1 = "HWP Document File"
		$a2 = "UPcfZrc"
		$a3 = {D1 A9 30 1A 5D C1 16 41 15 DA DF 54}
		$a4 = {B4 D5 31 1B F9 66 7C 56 5A 15}
		$a5 = {30 30 F8 18 18 F8 00 00 E0 00 00 C8}
		$a6 = {DC 66 43 0C 53 00 65 00 63 00}
		$a7 = {05 00 48 00 77 00 70 00 53 00 75 00 6D 00 6D}
	  
    condition:
      all of them 
}
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



































