# Reference for threat actor for "Mummy Spider, TA542"

**Title**: Emotet SMiShing Uses Fake Bank Domains in Targeted Attacks, Payloads Hint at TrickBot Connection

**Source**: https://securityintelligence.com/posts/emotet-smishing-uses-fake-bank-domains-in-targeted-attacks-payloads-hint-at-trickbot-connection/

## Content




 

Emotet SMiShing Uses Fake Bank Domains in Targeted Attacks, Payloads Hint at TrickBot Connection








































































































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








































Emotet SMiShing Uses Fake Bank Domains in Targeted Attacks, Payloads Hint at TrickBot Connection 








 





Light
Dark






February 19, 2020
By Limor Kessem



Christopher Kiefer


  3 min read




Malware
Threat Intelligence














 


Before a short lull in mid-February, Emotet was in the midst of a rise in activity that has been apparent since late 2019 — in terms of both spam and infecting potential victims via SMiShing attacks.
In cases observed by IBM X-Force researchers, SMS messages sent from what would appear to be local U.S. numbers are being delivered to mobile phones impersonating well-known banks and alerting users about a locked account.
Figure 1: SMiShing spam leading to Emotet infection zone (Source: IBM X-Force)
Those who tap to access the link from the message are redirected from the first hop to a second domain: shabon[.]co. This is a known domain that distributes Emotet as of February 2020.
Visually, the potential victim sees a customized phishing page that mimics the bank’s mobile banking page with a domain that was registered on the same day by those distributing Emotet. The domain features the bank’s name with a different top-level domain (TLD) and is likely designed to grab the victim’s credentials as a first step and then have them download a document file loaded with malicious macros. Our researchers found the file on the distributing domain and looked into some obfuscated malicious PowerShell scripts that led us to additional Emotet-serving domains.

Figure 2: Deobfuscated malicious PowerShell script reveals four additional Emotet-serving URLs (Source: IBM X-Force)
A Possible Connection to TrickBot?
Having located two additional URLs that serve Emotet infections, X-Force researchers examined two binary files served to potential victims. We found some junk content in the file, copied from current events.

Figure 3: Emotet first-stage binary containing “news” excerpts, likely as an anti-detection tactic (Source: IBM X-Force)
This practice, an old trick to evade antivirus detection, has been observed recently in some malware families, including the TrickBot Trojan. Knowing that Emotet is one of the ways TrickBot payloads are dropped to infected systems, there is a possibility that this attack is a targeted campaign designed to enable the spread of the TrickBot Trojan.
Mealybug on Fire
Emotet’s operator, the Mealybug gang, has varied its activity levels over time, sometimes going into lengthy lulls and periods of low-volume activity. Since late 2019, Mealybug has been pushing its activity through various channels, including spam, sextortion emails, SMiShing and ploys like fake Coronavirus warnings that were spread in Japan. It appears that Mealybug is gearing up to expand its botnet, diversify its illicit income sources and prepare for a wider attack surface in Japan, possibly ahead of the 2020 international sporting event coming to Tokyo in the summer.
To receive notifications about emerging campaigns as IBM X-Force continues to follow Emotet — as well as indicators of compromise (IoCs) from this campaign — make sure you’re tuned in to the latest threat intelligence.


Antivirus | Banking Security | Phishing | SMiShing | SMS | Targeted Attacks | Threat Intelligence | TrickBot | Trojan | X-Force




Limor Kessem
Principal Consultant, X-Force Cyber Crisis Management, IBM





Christopher Kiefer
Threat Hunt and Discovery Analyst






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














