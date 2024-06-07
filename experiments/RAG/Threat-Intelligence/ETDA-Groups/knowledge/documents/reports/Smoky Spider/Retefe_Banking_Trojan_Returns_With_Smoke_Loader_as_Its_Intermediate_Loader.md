# Reference for threat actor for "Smoky Spider"

**Title**: Retefe Banking Trojan Returns With Smoke Loader as Its Intermediate Loader

**Source**: https://securityintelligence.com/news/retefe-banking-trojan-returns-with-smoke-loader-as-its-intermediate-loader/

## Content




 

Retefe Banking Trojan Returns With Smoke Loader as Its Intermediate Loader











































































































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








































Retefe Banking Trojan Returns With Smoke Loader as Its Intermediate Loader 








 





Light
Dark






May 7, 2019
By David Bisson

  2 min read



















 


The Retefe banking Trojan has resumed its activity with a new series of attack campaigns that leverage Smoke Loader as an intermediate loader.
Proofpoint observed that the malware returned to regular attacks against German and Swiss users in April 2019 after taking a hiatus in 2018. These campaigns helped reveal several new techniques now employed by the banking Trojan. One geographically targeted campaign against Switzerland, for instance, used an Object Linking and Embedding (OLE) package to deliver Smoke Loader. This threat, in turn, downloaded Retefe two hours after infection.
The banking malware incorporated other changes as well. One operation detected by Proofpoint abused a shareware application to run an executable and a Python script. This code, in turn, wrote two files: convert-pdf-to-word-plus.exe and convert-pdf-to-word-plus_driver.exe. The former was a legitimate installer for the Convert PDF to Word Plus application that’s executed as a decoy, while the latter acted as a Retefe loader.
In another campaign, the malware turned away from Tor toward a stunnel, most likely in a bid to cause less noise in an enterprise environment and thereby avoid detection.
Looking to the Past of Retefe
This resurgence of Retefe comes after a busy period several years ago. In June 2016, Avast observed the malware using fake certificates to target U.K. banking customers and steal their login credentials. More than a year later, Proofpoint discovered the banking Trojan leveraging EternalBlue, the same exploit used by WannaCry ransomware, to move laterally through a network following the initial infection of a victim.
How to Defend Against a Banking Trojan
Security professionals can defend against banking Trojans like Retefe by using ahead-of-threat detection to discover potentially malicious domains before threat actors take advantage of them in attacks. Security teams should also use tools such as VBA editor to inspect the macro code in Microsoft Office documents for signs of malicious functionality.


Banking Malware | Banking Trojan | Cyberattacks | Macros | Malware | Microsoft Office | Python | Ransomware | Risk Management | Threat Detection | Tor | Trojan | WannaCry




David Bisson
Contributing Editor






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
























More from 
















                        February 14, 2024                    





                            Feds release urgent guidance for U.S. water sector                        

  3 min read - The water and wastewater sector (WWS) faces cybersecurity challenges that leave it wide open to attacks. In response, the CISA, EPA and FBI recently released joint guidance to the sector, citing variable cyber maturity levels and potential cybersecurity solutions.The new Incident Response Guide (IRG) provides the water sector with information about the federal roles, resources and responsibilities for each stage of the cyber incident response lifecycle. Sector owners and operators can use this information to augment their incident response plans,…                        



















                        February 13, 2024                    





                            Data residency: What is it and why it is important?                        

  3 min read - Data residency is a hot topic, especially for cloud data. The reason is multi-faceted, but the focus has been driven by the General Data Protection Regulation (GDPR), which governs information privacy in the European Union and the European Economic Area.The GDPR defines the requirement that users’ personal data and privacy be adequately protected by organizations that gather, process and store that data. After the GDPR rolled out, other countries such as Australia, Brazil, Canada, Japan, South Africa and the UAE…                        



















                        February 12, 2024                    





                            What to expect from the new National Cyber Director                        

  4 min read - As cyber threats show no sign of slowing down in terms of sophistication and frequency, the role of the National Cyber Director (NCD) in the United States is becoming a cornerstone of the nation’s defense strategy. Inaugural NCD Chris Inglis set a high bar for the office during his tenure, steering the country through a gauntlet of cyber challenges. Now, as Harry Coker Jr. steps into this critical role, he faces a landscape that continues to evolve with new threats on…                        















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














