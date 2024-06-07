# Reference for threat actor for "Reaper, APT 37, Ricochet Chollima, ScarCruft"

**Title**: ITG10 Likely Targeting South Korean Entities of Interest to the Democratic People's Republic of Korea (DPRK)

**Source**: https://securityintelligence.com/posts/itg10-targeting-south-korean-entities/

## Content




 

ITG10 Likely Targeting South Korean Entities of Interest to the Democratic People's Republic of Korea (DPRK)

































































































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








































ITG10 likely targeting South Korean entities of interest to the Democratic People’s Republic of Korea (DPRK) 








 





Light
Dark






June 6, 2023
By Joshua Chung



Melissa Frydrych

Claire Zaboeva

Agnes Ramos-Beauchamp


  7 min read




Threat Intelligence
Government
Intelligence & Analytics
Malware
Security Services
X-Force














 


In late April 2023, IBM Security X-Force uncovered documents that are most likely part of a phishing campaign mimicking credible senders, orchestrated by a group X-Force refers to as ITG10, and aimed at delivering RokRAT malware, similar to what has been observed by others. ITG10’s tactics, techniques and procedures (TTPs) overlap with APT37 and ScarCruft. The initial delivery method is conducted via a LNK file, which drops two Windows shortcut files containing obfuscated PowerShell scripts in charge of downloading a second stage RokRAT shellcode. RokRAT can execute remote C2 commands, data exfiltration, file download/upload, and keylogging. The uncovered lure documents suggest ITG10 may be targeting individuals and organizations involved in foreign policy associated with the Korean peninsula.
Key Findings:

ITG10 likely targeting South Korean government, universities, think tanks, and dissidents
Phishing emails spoof legitimate senders to deliver RokRAT via LNK files
Email attachments mimic legitimate documents
Additional malware samples possibly related to ITG10 RokRAT campaigns

Decoy documents
In late April 2023, X-Force uncovered several Zip Archives files hosting multiple lure documents likely sent via phishing campaigns operated by ITG10. X-Force assesses that the documents are likely decoys geared toward various personnel within two subsets of activity: South Korean government, communication, and educational centers; and energy, manufacturing, and supply chain. This section provides analysis of the lure documents and potential targets.
South Korean government, communications and educational centers
The first suspected subset of activity revealed Korean-language lure documents. The first titled (0722)상임위원회 및 상설특별위원회 위원 명단(최종).zip [(0722) List of Standing Committee and Standing Special Committee members (final).zip)], contains charts listing the Standing Committee members and assignments associated with broadcast media in South Korea as of July 2022. Examination of the contents suggests that it is a directory of eighteen South Korean parliamentary committee assignments, the number of committee members, their names, and political party affiliation. Committees include Education and Judicial, International and Foreign Affairs, Defense, and Intelligence. The intended targets for this lure are likely to be parliamentary members seeking information on their committee assignment or reporters covering parliament.
(0722)상임위원회 및 상설특별위원회 위원 명단(최종).zip

An additional decoy document titled 계약서내용.pdf (Contract detail.pdf) appears to be associated with a national South Korean broadcaster. The contents detail the company’s approach to radio drama production scheduled for broadcast in May 2023. North Korean sponsored threat actors have previously been known to create accounts posing as broadcasting scriptwriters to deceive watchers. In 2021, North Korean threat actors compromised several email accounts of prominent defectors to send malicious documents to contacts working on DPRK issues. ITG10 has also been known to infect news websites with malware likely to spy on readers.

A third decoy 2023년도 4월 29일 세미나.pdf (April 29, 2023 Seminar.pdf) appears to be an itinerary for an event hosted in April 2023 by a South Korean think tank. The event includes multiple seminars on political theory, military history, and a talk on “Intelligence activities and cyber security of the National Intelligence Service.” Members of this think tank include professors from multiple universities and South Korean government entities. There are two mobile phone numbers and a Zoom link with a password in the decoy document, which can be scraped to launch phishing material over social medial platforms. Based on the document’s content, academic and government employees, especially those in intelligence and cybersecurity, are probable targets for phishing emails containing this type of decoy document.
2023년도 4월 29일 세미나.pdf

Energy, manufacturing and supply chain
The second grouping of lure documents features a zip file projects in Libya.zip containing a LNK file Pipelines Profile (Elfeel- Sharara-Mellitah + Wafa – Mellitah).lnk, as well as additional English-language decoy files. The decoy files are a Microsoft Word Document and PDF copy of a document titled Proposed MOU GTE Korea. The documents appear to be legitimate and establish a written Memorandum of Understanding (MOU) between an authentic privately owned Libyan energy company and a South Korean consulting firm specializing in energy, procurement, construction and finance (EPC&F). In addition, the zip contains a second non-malicious lure PDF titled MFZ Executive Summary Korea detailing a feasibility study regarding the development and expansion of the “sea port free zone of Misurata.”
Based on the decoy content, the likely recipients of this phishing campaign would be organizations or individuals involved with a construction project in the Middle East. The Middle East has been a traditional customer for many large-scale construction projects for multiple South Korean companies, and there has been a recent push by the South Korean administration to what’s known as the ‘2nd construction boom’. These construction projects are part of the South Korean government’s pivot to the Middle East, deepening ties both militarily and economically.


Sample analysis
RokRAT has been previously analyzed as having a multi-stage process with two components. The first involves tooling, and the second involves the payload, likely to inhibit researchers from analyzing the final payload, while maintaining the ability to stop delivery once a target system is infected. RokRAT campaigns typically begin with a phishing email with a ZIP file attachment, containing a LNK file disguised as a Word document. When the LNK file is activated, a PowerShell script is executed, opening a decoy document to start the download process of RokRAT which is hosted at OneDrive or similar cloud application. In another campaign, ITG10 was observed delivering RokRAT via HWP and Word files containing LNK files. In X-Force’s analysis of recent RokRAT-related files, in lieu of a ZIP file, we found Optical Disc Image files (ISO) containing LNK files that had slightly modified PowerShell scripts, and Hangul Word Processor decoy documents (HWP).
 ISO files
The ISO files that X-Force observed contained a LNK file disguised as an exe icon, subsequently containing a HWP file, and a batch file. The LNK file contains a PowerShell command, as seen below as an example. Once the LNK file is executed, it extracts and drops a decoy file, and a batch file within the user’s %TEMP% folder. In this instance, the files were 2023년도 4월 29일 세미나.pdf – decoy file, and 230415.bat.
icon_location = C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe


PowerShell Commands:

Related malware?
While researching the RokRAT-related files, X-Force also uncovered three LNK files that behave differently than expected. There is no use of OneDrive or similar cloud applications to host a second-stage payload, and instead of dropping a batch file, these LNK files drop VBS, with the obfuscation technique for the dropped files being hex-encoding vs. string concatenation. In addition, the RokRAT LNK files drop batch files and downloads the payload that is decoded using the first byte as a key, then the payload is executed using Windows API functions (VirtualProtect). With these additional LNK files, the VBS downloaders do not perform these actions.
The LNK files analyzed contain an encoded PowerShell, and once the LNK files are executed, the PowerShell script is run, and two files are dropped to the user’s %TEMP% folder. In one analyzed sample, the files dropped were a VBS file (tmp<random-9-digit-number>.vbs ), and a Plaintext file with contents asdfgqwert. The VBS file will get executed via Wscript.exe:
“C:\Windows\System32\WScript.exe” “C:\Users\Usuario\AppData\Local\Temp\tmp<nine-digit-number>.vbs”.  Wscript.exe is a service 
Wscript.exe is a service provided by the Windows system with scripting abilities. Subsequently, two GET requests are initiated. In a third file we analyzed, instead of the LNK file dropping a VBS and a Plaintext file, a VBS file and a JPEG decoy file are dropped to the users %TEMPT% folder. In this case, the JPEG decoy file appears to be a correspondence related to the “Proof of Digital Assets”. At the time of this analysis, X-Force was unable to retrieve the final payload from the servers as they have been taken down; therefore, it is uncertain whether these additional LNK files are related to ITG10 activity. Further research and analysis are needed to determine relevance and attribution.
Encoded PowerShell:

Decoded PowerShell:

tmp1698268529.vbs

GET requests:

Proof of digital assets JPEG

X-Force recommendations
Multiple lure documents uncovered in this campaign suggest ITG10 continues to target individuals and organizations involved in foreign policy, potentially related to shifts in the geopolitical and security environment on the Korean peninsula. IBM X-Force assesses with high confidence that individuals and organizations holding strategic, political, or military information in connection with the Korean peninsula will see elevated threats from the DPRK, given ITG10’s previous and recent activity.
Organizations that may be at elevated risk of targeting from ITG10 have the potential to decrease the risk to their organization by employing heightened vigilance toward potential phishing emails, warning employees of the phishing email threats, employing and closely monitoring endpoint detection and response (EDR) tools, and leveraging behavioral analytics to identify malicious behavior. We also recommend that potentially targeted organizations alert on the following indicators of compromise to detect behavior related to this campaign.
Indicators of compromise



Indicator
Indicator Type
Context




f92297c4efabba98befeb992a009462d1aba6f3c3a11210a7c054ff5377f0753
LNK



7ef2c0d2ace70fedfe5cd919ad3959c56e7e9177dcc0ee770a4af7f84da544f1
PDF Decoy
2023년도 4월 29일 세미나.pdf


06431a5d8f6262cc3db39d911a920f793fa6c648be94daf789c11cc5514d0c3d
Batch File
230415.bat


1c5b9409243bfb81a5924881cc05f63a301a3a7ce214830c7a83aeb2485cc5c3
ZIP
(0722)상임위원회 및 상설특별위원회 위원 명단(최종).zip


cb4c7037c7620e4ce3f8f43161b0ec67018c09e71ae4cea3018104153fbed286
LNK



5815a6f7976e993fcdf9e024f4667049ec5a921b7b93c8c8c0e5d779c8b72fcc
HWP Decoy
0722.hwp


240e7bd805bd7f2d17217dd4cebc03ac37ee60b7fb1264655cfd087749db647a
Batch File
202207221.bat


9854750f3880c7cee3281d8c33292ca82d0d288963f0f2771d938c06ccaffaa9
LNK



ce56b011ac4663a40f0ba606c98c08aaf7caf6a45765aa930258fe2837b12181
PDF Decoy
계약서내용.pdf


cc6ae9670e38244e439711b1698f0db3cff000b79bec7f47bc4aa5ab1f6177c0
Batch File
230422.bat


00d88009fa50bfab849593291cce20f8b2f2e2cf2428d9728e06c69fced55ed5
ZIP
projects in Libya.zip


6753933cd54e4eba497c48d63c7418a8946b4b6c44170105d489d29f1fe11494
LNK
Pipelines Profile (Elfeel- Sharara-Mellitah + Wafa – Mellitah).lnk


f1289e7229ace984027f29cf8e2dd8fdd19b0c4b488da31ff411ee95305eaecc
docx
Proposed MOU GTE Korea.docx


fa2ebcdfce8bbe4245ed77b43d39e22c0c7593ca3f65be3fd0ccdf7ee02130a9
PDF Decoy
Proposed MOU GTE Korea.pdf


76d0133d738876f314ae792d0cf949710b66266ba0cebefbd98ce40c64a9b15b
PDF Decoy
MFZ Executive Summary Korea.pdf


5678196f512f8a531c7d85af8df4f40c7a5f9c27331b361bb1a1c46d317a77d8
PDF Decoy
230130.pdf


C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe

Icon Location


C:\Program Files (x86)\Hnc\Office 2020\HOffice110\Bin\Hwp.exe

Icon Location


hxxps[:]//api.onedrive[.]com/v1.0/shares/u!aHR0cHM6Ly8xZHJ2Lm1zL3UvcyFBalFOTHZFRV9DVU9iUFdnLXhPZG8xRXFYckU_ZT1BM1QwV2Q/root/content
URL
Document Location


hxxps[:]//api.onedrive[.]com/v1.0/shares/u!aHR0cHM6Ly8xZHJ2Lm1zL2kvcyFBaFhFWExKU05NUFRlNnFWazdDNHp2Yy1SekU_ZT1SSFZJSk4/root/content
URL
Document Location


hxxps[:]//api.onedrive[.]com/v1.0/shares/u!aHR0cHM6Ly8xZHJ2Lm1zL3UvcyFBaFFNUDZlZzhhUkZiN0xVMUNPQ2YzeE5vVFU_ZT1wZ2liaUM/root/content
URL
Document Location


hxxps[:]//api.onedrive[.]com/v1.0/shares/u!aHR0cHM6Ly8xZHJ2Lm1zL2kvcyFBaFhFWExKU05NUFRiZnpnVU14TmJJbkM2Q0k_ZT1WZElLSjE/root/content
URL
Document Location


hxxps[:]//api.onedrive[.]com/v1.0/shares/u!aHR0cHM6Ly8xZHJ2Lm1zL3UvcyFBdTJteTF4aDZ0OFhnUjJNem1zOG5oUndvLTZCP2U9akhIQzZ5/root/content
URL
Document Location


6bab11d9561482777757f16c069ebef3f1cd6885dbef55306ffde30037a41d48
LNK



7529eaeeb29c713f8e15827c79001a9227d8bc31c9209bf524a4ff91648a526e
VBS



xn--vn4b27hka971hbue[.]kr
 C2
GET Request


50fe8a981a7d4824f0b297f37804b65672ed4484e198e7c324260a34941ddac7
LNK



3d1d2d0464013d9e1dd7611d73176f3a31328a41d6474d5b6d0582ad09d3b17d
VBS



partybbq.co[.]kr
 C2
GET Request


1ec4d60738a671f00089a86eeba6cb13750bce589e84fd177707718a4cc7d8f1
LNK



88c219656f853b2dc54ae02d32a716e10c8392ed471d1c813e57de2dc170951e
VBS



7aa7233feb8e8a7b71ae6cdd0ddb8c2b192d4b6e131fed1ade82efdcb8096c57
JPEG
Decoy


Scroll to view full table 
To learn how IBM X-Force can help you with anything regarding cybersecurity including incident response, threat intelligence, or offensive security services schedule a meeting here:

IBM X-Force Scheduler
If you are experiencing cybersecurity issues or an incident, contact X-Force to help:
US hotline 1-888-241-9812 | Global hotline (+001) 312-212-8034



IBM X-Force Research | Malware | Phishing | Phishing Attack | X-Force




Joshua Chung
Cyber Threat Intelligence Analyst, IBM Security





Melissa Frydrych
Threat Hunt Researcher, IBM





Claire Zaboeva
Senior Strategic Cyber Threat Analyst, IBM





Agnes Ramos-Beauchamp
Security Consultant, IBM






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
























More from Threat Intelligence
















                        February 1, 2024                    





                            Audio-jacking: Using generative AI to distort live audio transactions                        

  7 min read - The rise of generative AI, including text-to-image, text-to-speech and large language models (LLMs), has significantly changed our work and personal lives. While these advancements offer many benefits, they have also presented new challenges and risks. Specifically, there has been an increase in threat actors who attempt to exploit large language models to create phishing emails and use generative AI, like fake voices, to scam people. We recently published research showcasing how adversaries could hypnotize LLMs to serve nefarious purposes simply…                        



















                        December 8, 2023                    





                            ITG05 operations leverage Israel-Hamas conflict lures to deliver Headlace malware                        

  12 min read - As of December 2023, IBM X-Force has uncovered multiple lure documents that predominately feature the ongoing Israel-Hamas war to facilitate the delivery of the ITG05 exclusive Headlace backdoor. The newly discovered campaign is directed against targets based in at least 13 nations worldwide and leverages authentic documents created by academic, finance and diplomatic centers. ITG05’s infrastructure ensures only targets from a single specific country can receive the malware, indicating the highly targeted nature of the campaign. X-Force tracks ITG05 as…                        



















                        November 30, 2023                    





                            IBM identifies zero-day vulnerability in Zyxel NAS devices                        

  12 min read - While investigating CVE-2023-27992, a vulnerability affecting Zyxel network-attached storage (NAS) devices, the IBM X-Force uncovered two new flaws, which when used together, allow for pre-authenticated remote code execution. Zyxel NAS devices are typically used by consumers as cloud storage devices for homes or small to medium-sized businesses. When used together, the flaws X-Force discovered allow a remote attacker to execute arbitrary code on the device with superuser permissions and without requiring any credentials. This results in complete control over the…                        















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














