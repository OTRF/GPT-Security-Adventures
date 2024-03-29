# Reference for threat actor for "Wizard Spider, Gold Blackburn"

**Title**: TrickBot Widens Infection Campaigns in Japan Ahead of Holiday Season

**Source**: https://securityintelligence.com/posts/trickbot-widens-infection-campaigns-in-japan-ahead-of-holiday-season/

## Content




 

TrickBot Widens Infection Campaigns in Japan Ahead of Holiday Season











































































































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








































TrickBot Widens Infection Campaigns in Japan Ahead of Holiday Season 








 





Light
Dark






December 3, 2019
By Limor Kessem



Itzik Chimino


  4 min read




Banking & Finance
Threat Intelligence














 


The threat group operating the TrickBot Trojan, the most active banking Trojan family according to IBM X-Force data, has been modifying some of the malware’s modules lately as they continue to deploy their attacks in the wild. As code modifications take place, so do widespread TrickBot campaigns that target a large number of entities across the globe — with Japan becoming a growing target as we approach the holiday season.
Just in Time for the Holidays
TrickBot campaigns have been known to target Western countries and English-speaking geographies, and while the malware also targets other parts of the world, this is the first time we are seeing it focused on Japanese banks.
As Japanese consumers look to kick off their holiday shopping, they should be wary of TrickBot infection campaigns growing in the region, targeting banks, e-commerce sites and cryptocurrency exchange platforms. TrickBot configurations have been loaded with hundreds of targeted URLs, most belonging to banks, but some nontraditional targets in recent lists were also recognized, such as fuel cards, a hotel chain and an industrial supply company, to name a few.
Campaigns in Japan have been leveraging malicious spam and distribution by the Emotet botnet to drop TrickBot onto user devices. The predominant attack mode involves web injections on banking websites that lead to eventual online banking fraud. On-the-fly injections pulled in real time from the attacker’s server are a TrickBot staple that traditionally lures victims into divulging personally identifiable information (PII), payment card details and PIN codes, as well as transaction authorization elements.

Figure 1: TrickBot campaign targets by service type (Source: IBM X-Force)
This shift of TrickBot attacks targeting Japan is not the first time we have seen malware attributed to Eastern European gangs reach the country. Previous banking Trojans, such as URLZone and Gozi (Ursnif), have been active in Japan for years now.

Figure 2: Geo-targeting of recent TrickBot campaigns per brand’s location (Source: IBM X-Force)
Japanese Businesses Beware: TrickBot Can Usher in Ryuk Ransomware Attacks
TrickBot infections are a worrying trend on their own, but amid the growing concern over ransomware, Japanese companies should also remain vigilant about the potential of TrickBot attacks turning into Ryuk ransomware attacks. A kill chain that begins with Emotet and TrickBot infections has been known to result in Ryuk attacks, widespread ransomware infections that can paralyze organizations and extort them with demands of millions of dollars in ransom money.

Figure 3: An example kill chain that involves Emotet and TrickBot infections
More About TrickBot
TrickBot emerged in August 2016 and launched into a testing and development period. The malware started out with a striking resemblance to the Dyre Trojan in its internal configuration, attack tactics and the infection methods it used to reach new endpoints. Over time, TrickBot rapidly evolved and spread out to different parts of the world, boasting the ability to operate in a number of language-specific geographies, use redirection attacks and continuously progress on the code level, adding and retiring modules in line with its operator’s cybercrime objectives.
Banking Trojans have gradually become the go-to business of organized crime groups over the past decade, evolving into increasingly stealthy and sophisticated codes. The global chart of the top, most-active malware in this class features TrickBot at the leading position, followed by similar groups that operate Gozi, Ramnit and IcedID — all of which are modular Trojans being used by organized crime groups.

Figure 4: Top banking Trojan families per attempted infection volume (Source: IBM X-Force)
Tips for Mitigating the Risk of TrickBot Infections
Avoiding malware infections is an ongoing battle that organizations engage in through employee education and security controls. Here are some tips from our team that can help businesses focus on threat-centric prevention and response:

Malware often looks for an unpatched system. Keep tight control of OS and application update schedules. Don’t skip on patching as close as possible to patch releases. Segregate and use compensating controls on assets that cannot be patched.
Layer relevant security controls to detect malware, such as antivirus, embedded malware detection, email security and filtering known malicious communication resources.
Use role-based training to inform accounting staff about TrickBot attacks, business email compromise and wire-fraud tactics.
For known malicious IPs, and those related to malware like TrickBot, blacklist URLs and IP-based indicators of compromise (IoCs) at the firewall, intrusion detection system (IDS), web gateways, routers or other perimeter security devices.
Escalate suspicious events to your incident response team, especially if communication with known bad IPs is taking place.
To better respond to potential ransomware attacks, create and maintain a backup program that will ensure data redundancy on and offline, as well as periodic testing to provide a way to recover from possible attacks by using up-to-date backups.

If your team suspects a TrickBot or Ryuk infection spreading, do not wait to launch incident response plans to contain and begin remediation. If your organization is in need of response assistance, please contact the X-Force Incident Response and Intelligence Services (IRIS) hotline — U.S. hotline: 1-888-241-9812 | Global hotline: (+001) 602-220-1440.
Learn more about fraud protection


Banking Malware | Banking Trojan | Cybercrime | Cybercrime Trends | Fraud Protection | Incident Response (IR) | Malware | Personally Identifiable Information (PII) | Ransomware | Threat Detection | TrickBot | Trojan | X-Force




Limor Kessem
Principal Consultant, X-Force Cyber Crisis Management, IBM





Itzik Chimino
Security Web Researcher in Security Intelligence






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
























More from Banking & Finance
















                        January 26, 2024                    





                            DORA and your quantum-safe cryptography migration                        

  5 min read - Quantum computing is a new paradigm with the potential to tackle problems that classical computers cannot solve today. Unfortunately, this also introduces threats to the digital economy and particularly the financial sector.The Digital Operational Resilience Act (DORA) is a regulatory framework that introduces uniform requirements across the European Union (EU) to achieve a "high level of operational resilience" in the financial services sector. Entities covered by DORA — such as credit institutions, payment institutions, insurance undertakings, information and communication technology…                        



















                        December 19, 2023                    





                            Web injections are back on the rise: 40+ banks affected by new malware campaign                        

  8 min read - Web injections, a favored technique employed by various banking trojans, have been a persistent threat in the realm of cyberattacks. These malicious injections enable cyber criminals to manipulate data exchanges between users and web browsers, potentially compromising sensitive information. In March 2023, security researchers at IBM Security Trusteer uncovered a new malware campaign using JavaScript web injections. This new campaign is widespread and particularly evasive, with historical indicators of compromise (IOCs) suggesting a possible connection to DanaBot — although we…                        



















                        October 30, 2023                    





                            Virtual credit card fraud: An old scam reinvented                        

  3 min read - In today's rapidly evolving financial landscape, as banks continue to broaden their range of services and embrace innovative technologies, they find themselves at the forefront of a dual-edged sword. While these advancements promise greater convenience and accessibility for customers, they also inadvertently expose the financial industry to an ever-shifting spectrum of emerging fraud trends. This delicate balance between new offerings and security controls is a key part of the modern banking challenges. In this blog, we explore such an example.…                        















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














