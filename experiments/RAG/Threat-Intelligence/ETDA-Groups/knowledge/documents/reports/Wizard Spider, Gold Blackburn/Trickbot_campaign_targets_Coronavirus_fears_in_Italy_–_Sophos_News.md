# Reference for threat actor for "Wizard Spider, Gold Blackburn"

**Title**: Trickbot campaign targets Coronavirus fears in Italy – Sophos News

**Source**: https://news.sophos.com/en-us/2020/03/04/trickbot-campaign-targets-coronavirus-fears-in-italy/

## Content





















Trickbot campaign targets Coronavirus fears in Italy – Sophos News

























































Skip to content




















								Search							







Products & Services
Security Operations
Threat Research
AI Research
Naked Security
Sophos Life
 





Search













Open main menu




















Search








Products & Services
Security Operations
Threat Research
AI Research
Naked Security
Sophos Life
 









 








Trickbot campaign targets Coronavirus fears in Italy


		Written by 				
Sean Gallagher 



March 04, 2020 

Threat Research coronavirus current events JS/Agent malspam Spam Trickbot virus 





The operators of a Trickbot spam campaign have found a new way to spread their digital infection: by using fears of a biological one. Spam targeting Italian e-mail addresses is playing on fears over the Coronavirus outbreak in that country.
The e-mail carries a document purported to be a list of precautions to take to prevent infection. But the enclosed file is in fact a weaponized Word document, carrying a Visual Basic for Applications (VBA) script that carries a dropper used to deliver a new Trickbot variant.
Hunting for a hook
The Coronavirus twist to the spam message and the Trickbot malware delivered on it may be new, but the mechanisms used to deliver it (including the spam “bots” that send the message, the enclosed scripted Word document and the JavaScript dropper) are similar or identical to those used in campaigns that have been active for at least six months.
Sophos detected other email payloads from the same spam-generating malware dating back to September of last year, spiking on October 29, 2019. But these earlier spam messages, which also carried malicious documents, carried a different variety of concern-inducing calls to action, with subject lines such as “you have email about your credit” and “you have received fax about your loan.”
Incidents of messages sent by the spambot behind the Trickbot campaign over the past six months caught by SophosLabs spam traps.
But with concerns about COVID-19 on the rise – particularly in Italy, where cases are surging – the spam campaign’s subject line is now in tune with the concerns of the day.
The emails, with the subject line “coronavirus: informazioni importanti su precauzioni” – purportedly from a “Dr. Penelope Marchetti ”—state (in Italian):
Due to the fact that cases of coronavirus infection are documented in your area, the World Health Organization has prepared a document that includes all necessary precautions against coronavirus infection. We strongly recommend that you read the document attached to this message!
The attached document is, of course, viral in a totally different sense of the word.
The chain of infection
When opened, if macros are disabled, the Word document displays a message asking the recipient to enable editing and content because “this document was created in an earlier version of Microsoft Office Word.”
If macros are already enabled, or if the targeted user complies with the instructions, the VBA script does a number of things:

It disgorges files encoded within the document to disk: a VBA macro file (vbaProject.bin), and several Word-related XML files. The macro, in turn, contains an obfuscated JavaScript (jse) file.
It connects back to a PHP script on a remote server (hxxps://185[.]234.73.125/wMB03o/Wx9u79.php in some samples) – passing the IP address and some basic details about the target as variables within an HTTP GET request.
It calls the macro file. While the macro script is obfuscated by code from legitimate VBA script, its actual function is to create the JavaScript dropper and a .bat batch file that executes the dropper with the Windows Script Host (WSH) command line tool, cscript.exe.


The JavaScript file (detected by Sophos as JS / Agent-BCAJ ) connects back to a command and control server (in some cases, the same PHP script as the VBA script does] 1, sending back the computer name and some other data in its . request . When successful, it downloads a Base64-encoded Windows executable, saving it in the system’s set location for temporary files; For example:
 C:\Users\username\AppData\Local\Temp\320455ed.pro
Next, it creates a separate JavaScript file to decode and execute the malicious payload, and then launches it using wscript.exe, another WSH executable. In one sample tested, once launched, the dropper’s malicious payload attempts to connect to 23 [.] 19 [.] 227 [.] 235.
As with most viruses – digital or biological – this particular contagion can be prevented through good hygiene: Disable macros in Office applications for all but the most trusted documents, and train everyone in the organization what not to do with documents received via email. 
IoCs
Network indicators
hxxps://185[.]234.73.125/wMB03o/Wx9u79.php
 23[.]19.227.235
We analyzed the following files during this investigation:



SHA256
Filename


dd7023dd82b641c9307566b87acf0951f16b27c34094a341fa1fe7671d269bf4
RANLSOJF.JSE


58e918466a61740abe42a2d1ca29bd8d56daf53912e6d65879cbe944466fb80c
ERRORFIX.BAT


8e3240a2a6b07ae8a6fde884c0e18e476ca3e92438022fe1a1ad4b2ba2334737
A.COM



 
Acknowledgments
SophosLabs would like to acknowledge the contributions to this report from analysts Richard Cohen, Brett Cove, and Suriya Natarajan.






Share on Facebook







Share on X







Share on LinkedIn










1











  



								About the Author							

Sean Gallagher 

Sean Gallagher is Principal Threat Researcher, Sophos X-Ops. Prior to joining Sophos, he was an information security and technology journalist for over 30 years, including 10 as information security and national security editor for Ars Technica.
 


 







				Read Similar Articles			











				May 24, 2021			

What to expect when you’ve been hit with Avaddon ransomware 













				May 19, 2021			

What’s New in Sophos EDR 4.0 













				May 19, 2021			

Sophos XDR: Driven by data 






 



1 Comment		






													J. Harold Jones											
17 May 2020 at 11:49 pm


Sean, You may remember me from BB-63.  I was a Weapon Systems Analyst from Dahlgren and participated heavily in 16″ ballistics training, use of the HP 85 PC to generate initial ballistic corrections to shoot modified ammo, management of velocimeter data, etc. Training and riding all 4 BBs was a dream job.  You are on to other things now but I wanted to contact you to compliment you on the Gears of War article.  My grandson is building an unbelievable Lego BB model with lots of gears and motors and has gained insight from the article.  Contact me if interested.
Reply 





Leave a Reply Cancel replyYour email address will not be published. Required fields are marked *Comment * Name 
Email 
Website 
 Save my name, email, and website in this browser for the next time I comment.
 

Δ 





 



		Subscribe to get the latest updates in your inbox.	






			Which categories are you interested in?		










		You’re now subscribed!	











		Change Region		








						América Latina					



						Brasil					



						Deutschland					



						English					



						France					



						Iberia					



						Italia					



						Japan					





Terms



		Privacy
		







					Privacy Notice				



					Cookies				







		Legal
		







					General				



					Modern Slavery Statement				



					Speak Out				







							© 1997 - 2024 Sophos Ltd. All rights reserved						












