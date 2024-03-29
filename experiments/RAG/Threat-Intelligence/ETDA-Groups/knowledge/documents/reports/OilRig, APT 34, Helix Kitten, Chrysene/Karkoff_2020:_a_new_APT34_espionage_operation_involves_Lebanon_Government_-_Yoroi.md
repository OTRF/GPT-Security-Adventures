# Reference for threat actor for "OilRig, APT 34, Helix Kitten, Chrysene"

**Title**: Karkoff 2020: a new APT34 espionage operation involves Lebanon Government - Yoroi

**Source**: https://blog.yoroi.company/research/karkoff-2020-a-new-apt34-espionage-operation-involves-lebanon-government/

## Content







Karkoff 2020: a new APT34 espionage operation involves Lebanon Government - Yoroi










































































 












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






Karkoff 2020: a new APT34 espionage operation involves Lebanon Government
	03/02/2020
Introduction
In November 2018, researchers from Cisco Talos tracked and detailed a “DNSEspionage” campaign against targets in Lebanon and UAE. At the time of the report, the threat actor carried out a cyber espionage campaign by redirecting DNS traffic from domains owned by the Lebanon government to target entities in the country.
In April 2019, Cisco Talos discovered evidence of the link between APT34 (codename Helix Kitten or OilRig) and the “DNSEspionage” operation. Talos analysts discovered several overlaps in the infrastructure employed by attackers and identified common TTPs. They tracked this new implant “Karkoff”.
Experts from Cybaze/ Yoroi Zlab, as part of ordinary Threat Intelligence activities, spotted a new sample which they believe to be an update of the Karkoff implant. It could prove that  APT34 is still active and threat actors used it in a new campaign that appears to be active at the time of writing. The APT group made some changes in its technique, tactics, and procedures, but the target is the same, the Lebanon Government.
In this campaign, the APT group may have compromised a Microsoft Exchange Server belonging to a Lebanon government entity, in fact, we found some evidence in the communication logic.
This new implant has some similarities with the samples of Karkoff involved in past campaigns, including:
similar Macro structure.NET modular implant with similar logicexploit Microsoft Exchange Server as communication channel
Moreover, the new Karkoff implant implements a new reconnaissance logic in order to drop the final payload only to specific targets, gathering system information, the domain name, hostname and running Operating System.
Update
A few hours before this report has been publicly disclosed, malware researchers at the Italian cyber security firm Telsy also published their analysis.
Both reports are related to the same sample, but let me suggest reading both analyses to have a clear vision of the threat actors and all the technical details related to the implant. The report published by Telsy is available here: LINK.
Technical Analysis
Hash926e29f9242feb3e11c532616f7c90c5d7acab115d38ebf748cabaaa6a2a3667ThreatAPT34 Karkoff macro loaderBrief DescriptionMalicious Excel macro Ssdeep24576:zLNkxqHOPi1K5sLMKd2rVIehO/KBhjPyVuVX/+2PPbK:wl4E
Table 1. Sample information
The Malware is an Excel Document with a malicious macro embedded. The following image (Fig:1) shows the highlights of the extracted code. 

Fig.1. Malicious Macro: drop and execute monitor.exe
The macro extracts a custom base64 code from the body of the file and, after a decoding routine, it downloads an executable file  into the following path “C:\Users\public\.Monitor\monitor.exe”. Persistence is assured by scheduling a new task named SystemExchangeService. 

Fig.2.Persistence with SystemExchangeService
The extracted  payload is summed up as follows: :

Fig.3.Static details of monitor.exe
The payload were not obfuscated at all. This made a simple and quick analysis.
As shown in the above figure, the creation date is on 29 February, this is an indicator of the recent build of this implant. Moreover, a small file size (1.13MB) allows malicious content to be downloaded and executed quickly.

Fig.4. details of compromised mail exchange server parameters
As the first step, as shown in Fig 4, the sample tries to connect to its own command and control server, which happens to be an Exchange mail server belonging to the Lebanon government. Once it connects, the C2 answers back with the list of available commands as attachments in a replied e-mail. Fig 5 shows the GetList function from where we might appreciate the eMail body decoding process. From the body, a custom encoded string is decoded and later it is interpreted as a command.

Fig.5. detail of GetList function responsible for getting the list of available commands as mail attachments
Following our analysis, we noticed the malware tries to connect back and forth to its C2 to get authorization and to share detailed information about the infected system. It used “UserAgent” of the exchange client. Fig 6 shows details on what is hijacked from the victim’s side.

Fig.6. details of Information stolen on the victim’s machine
Another evidence is the domain registration of the second command control: it has been registered on January, 27, probably indicating the date of the beginning of the new attack.

Fig.7. details of domain registration godoycrus[.com
Conclusions
APT34 is still active, and this campaign against the Lebanon government demonstrates it. The new version of the Karkoff malware is the demonstration that the Iran-linked APT34 cyberespionage group continues to improve its arsenal. The sample involved in this campaign implements new reconnaissance capabilities, it implements a covert and effective C2 communication channel through the use of the Microsoft Exchange Protocol.
The Group likely exploited or brute-forced a Lebanon related mail account with another tool of its arsenal, the JASON tool. The Jason tool was leaked at the end of 2019, it could be used by attackers to carry out bruteforce attacks on exchange servers.
Indicators of Compromise
Hashes59cbc7e788425120c2dde50f037afbf3b1d2108c0b7e27540e924cad2463fe5b26995a1cd99a5c70fd7bfa925cb0bbbdbd419bedc2d664dffd3b7c57ad07de661b2c5354eb567132a341c1b15ad5cc71c3f5ba8e2788b67c0fbc0e7993beb1d2ebae23be2e24139245cc32ceda4b05c77ba393442482109cc69a6cecc6ad1393678d59bcd469e4cf236c7af7517c54ab9ad643523383875bd875131d7130941fC2godoycrus[.comPersistenceSet Task scheduler
Yara Rules
rule Karkoff_Attack_2020_Excel_macro {
	meta:
  	description = "Yara Rule for new APT34 Karkoff campaign excel malicious macro"
  	author = "Cybaze Zlab_Yoroi"
  	last_updated = "2020-03-02"
  	tlp = "white"
  	category = "informational"

	strings:
	
	   $a1 = "EncodedData0"
	   $a2 = "NewTask9"
	   $a3 = "EAAMYEKwUAAEsEWQUAAMYEnQUAAMYEqAUAAJwSrgU"
	   $a4 = "TVqQAAMAAAAEAAAA"
    condition:
	all of them

}


rule Karkoff_Campaign_2020 {
	meta:
		description = "Yara Rule for new APT34 Karkoff campaign"
		author = "Cybaze Zlab_Yoroi"
		last_updated = "2020-03-02"
		tlp = "white"
		category = "informational"

	strings:
	
	   $a1 = "SystemExchangeService" ascii wide
	   $a2 = "getWindowsVersion" ascii wide
	   $a3 = "GetCommands" ascii wide
	   $s1 = {0A 7A 1E 02 7B 9C 12 00 04 2A}

    condition:
	uint16(0) == 0x5A4D and all of them

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



































