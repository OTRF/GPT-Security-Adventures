# Reference for threat actor for "LockBit Gang"

**Title**: LockBit 2.0: Ransomware Attacks Surge After Successful Affiliate Recruitment

**Source**: https://securityintelligence.com/posts/lockbit-ransomware-attacks-surge-affiliate-recruitment/

## Content




 

LockBit 2.0: Ransomware Attacks Surge After Successful Affiliate Recruitment



































































































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








































LockBit 2.0: Ransomware attacks surge after successful affiliate recruitment 








 





Light
Dark






September 9, 2021
By Megan Roddie

  7 min read




Malware
Security Services
Threat Hunting
Threat Intelligence














 


After a brief slowdown in activity from the LockBit ransomware gang following increased attention from law enforcement, LockBit is back with a new affiliate program, improved payloads and a change in infrastructure. According to IBM X-Force, a major spike in data leak activity on the gang’s new website indicates that their recruitment attempts have been successful. IBM’s data shows that LockBit is nearly six times more active than other groups, such as the Conti ransomware operators. This blog post delves into LockBit’s 2.0 version, its recent activity and an analysis of the new payloads.
LockBit is a ransomware-as-a-service (RaaS) gang that writes and distributes its malware through affiliates. RaaS has become an increasingly popular business model for ransomware operators in the past few years, helping gangs expand their reach without growing their core team or their expenses. These groups are able to make a profit while turning over the actual deployment of their ransomware payloads to affiliates, who also shoulder part of the risk of being exposed by law enforcement.
Announcing LockBit 2.0
The LockBit gang was first found advertising their affiliate program in January 2020 on a well-known, Russian-speaking forum known as XSS. This underground forum has been used by many RaaS gangs in the past to advertise their malware and hunt for new affiliates. That includes gangs like REvil/Sodinokibi, DarkSide, Netwalker and others. But with increased attention from law enforcement, XSS banned all ransomware topics from their forum in early 2021.
With this avenue shut down, LockBit’s owners pivoted to using their own infrastructure for advertising. At the end of June 2021, those behind LockBit posted a page on their leak site (bigblog[.]at) announcing recruitment for their LockBit 2.0 affiliate program.

Figure 1: LockBit’s June 2021 advertisement with new features, seeking new affiliates (source: bigblog[.]at)
According to their post, the affiliate is responsible for gaining access to “the core server”, likely referring to a domain controller, and then the rest will be carried out by the LockBit payload.
The group mentions their payload does not operate in Russian-language speaking countries and specifies that they will only work with experienced penetration testers. Additionally, the group claims their ransomware is faster than any other ransomware families and includes a table for comparing supposed encryption speeds against other prolific ransomware codes.
The affiliate also gets to decide the ransom amount and will receive the payment directly, sending the LockBit gang’s cut of the profit after the ransom is paid.

Figure 2: LockBit operators’ encryption speed comparison vs. top competitors (source: bigblog[.]at)
To facilitate extortion if a victim refuses to pay for a decryption key, LockBit also includes access to an information stealer they call StealBit, which allegedly exfiltrates files from victim networks to the LockBit blog. This malware is also touted as a high-speed uploader, which is supposed to reassure affiliates that their operation will be swift.
X-Force researchers were able to identify files submitted to VirusTotal in August 2021 that may be samples of the StealBit malware, but analysis is still ongoing at the time of this publication.

Figure 3: LockBit operators boast StealBit’s upload speeds (source: bigblog[.]at)
A spike in victims’ data exposure
Prior to the announcement of LockBit 2.0’s affiliate program, the last dark web leak from the gang appears to have been published on December 30, 2020. Posting activity resumed approximately seven months later on July 21, 2021, shortly after new recruitment attempts began, with about 76 new posts published within a six-day period.

Figure 4: Stolen data posts created per day on bigblog[.]at
Looking at other ransomware families’ leak sites in the three-week period since LockBit’s return (7/21/2021-8/11/2021), LockBit appears to be currently operating one of the most active ransomware leak sites.

Figure 5: Leak site activity by the number of posts within the monitored period
Victims by industry, geography
With regards to victims, IBM X-Force identified the below industries and geographies being impacted by LockBit and its affiliates:

Figure 6: Top LockBit victims by industry (source: IBM X-Force)

Figure 7: Top LockBit victims by region (source: IBM X-Force)
While a few regions and industries have multiple victims involved, IBM was unable to identify any clear targeting patterns. Each LockBit affiliate likely has its own choices of targeting, which may be targeted or opportunistic.
Given the timing of the new affiliate program being advertised and the spike in activity, IBM X-Force suspects that LockBit was able to recruit affiliates who had already begun compromising networks.
New infrastructure
LockBit’s use of a data leak site first appeared in September 2020. Their leak sites and support sites (where victims can purchase a decryptor) are offered at both surface and dark web addresses. Along with the observed uptick in activity, IBM researchers discovered the use of newly registered infrastructure for these sites.
LockBit’s primary blog that publishes victim data and advertises its affiliate program is currently being hosted on the clear web at bigblog[.]at. Whois information for this domain indicates that LockBit registered the domain on July 6, 2021. Pivoting off the unique registrant email reveals that their new clear web decryptor site, decoding[.]at, was also registered on the same date.
IBM X-Force was able to uncover the domain locksupp[.]at, which was leveraging the same name servers as decoding[.]at. Whois and nameserver history indicates that this domain was in use around June 6, 2021, but it appears it was suspended by June 29, 2021. It is not currently reachable and its purpose is unknown at this time.
New samples
X-Force identified over a dozen new submissions of LockBit samples to VirusTotal occurring since the launch of the LockBit 2.0 affiliate program. Analysis was performed on several of these samples to determine any changes in these new variants.
Much of LockBit’s functionality remains the same in version 2.0, with a similar encryption routine. A hybrid AES/RSA encryption approach is still used. The two minor updates are the renaming of the registry key in which the RSA public session key is stored and the creation of a file used as a mutex while files are being encrypted. Additionally, the registry run key used for persistence is now a GUID-type string instead of an alpha-numeric string.
On top of these minor changes, two major additions were discovered: the addition of a new deployment technique and the physical printing of ransom notes.
Active directory deployment
One of the most significant changes identified during the analysis was the implementation of a novel technique for deployment. The payload has the capability to automatically deploy itself to Microsoft Active Directory clients via Group Policy Objects (GPO). When executed on an Active Directory Domain Controller, LockBit 2.0 creates several GPOs to carry out the infection process. The Windows Defender configuration is altered to avoid detection. It refreshes network shares, stops certain services and kills processes. The LockBit executable is then copied into the client desktop directories and executed. PowerShell is used to apply the new GPOs to all domain-joined hosts in a specified organization unit (OU).
Ransom note
The following is an example of the ransom note left behind after files are encrypted:

Figure 8: LockBit’s post-encryption ransom note (source: IBM X-Force)
Another interesting addition to the extortion techniques is a new LockBit functionality to repeatedly print the ransom note to any printers connected to the victim host.
A growing threat to watch for
LockBit does not appear to be slowing down, with regular leaks being published daily since the launch of their 2.0 affiliate program. It is likely that the ransomware payload will also continue to evolve and expand its capabilities. This ransomware group and the many others currently operating in the threat landscape present a major threat to organizations in all industries and geographies, except those in the Commonwealth of Independent States (CIS) countries where most malware operators avoid attacking local organizations.
Organizations should prioritize protecting their networks and data from this threat or risk joining the growing list of victims of RaaS affiliates. The following are a few actions companies can take that can help mitigate risks and minimize damage:

Establish and drill an incident response team. Whether in-house or as a retained service, the formation of an incident response team and drilling the most relevant attack scenarios can make a big difference in attack outcomes and costs.
Establish and maintain offline backups. Ensure you have files safely stored from attacker accessibility with read-only access. Also, consider the use of offsite/cold storage solutions. The availability of backup files is a significant differentiator for organizations that can help them recover from a ransomware attack.
Implement a strategy to prevent unauthorized data theft, especially as it applies to uploading large amounts of data to legitimate cloud storage platforms that attackers can abuse. Consider blocking outbound traffic to unapproved cloud hosting services.
Employ user and entity behavior analytics to identify potential security incidents. When triggered, assume a breach has taken place. Audit, monitor and quickly act on suspected abuse related to privileged accounts and groups.
Deploy multifactor authentication on all remote access points into an enterprise network — with particular care given to secure or disable remote desktop protocol (RDP) access. Multiple ransomware attacks have been known to exploit weak RDP access to gain initial entry into a targeted network.
Use penetration testing to identify weak points in enterprise networks and vulnerabilities that should be prioritized for patching. In particular, we recommend implementing mitigations for CVE-2019-19781, which multiple threat actors have used to gain initial entry into enterprises in 2020 and 2021 — including for ransomware attacks.
Consider prioritizing the immediate remediation, as applicable, of the following frequently exploited software vulnerabilities:




CVE-2019-2725
CVE-2020-2021
CVE-2020-5902
CVE-2018-8453



VPN-related CVEs



CVE-2019-11510
CVE-2019-11539
CVE-2018-13379
CVE-2019-18935
CVE-2021-22893



RDP



Restrict port access on TCP port 3389
Apply multifactor authentication to remote access logins
Remediate RDP vulnerabilities such as Windows RDP CVE-2019-0708 (BlueKeep)
CVE-2020-3427
CVE-2020-0610
CVE-2020-0609


Segment networks according to the data they host.
Encrypt the data most likely to be stolen in an attack.
Consider adopting a zero trust approach and framework to better control what users can access and potentially halt an attack in its tracks.

If you are experiencing cybersecurity issues or an incident, contact X-Force for assistance: U.S. Hotline: 1-888-241-9812 | Global Hotline: +(001) 312-212-8034. Learn more about X-Force’s threat intelligence and incident response services.
Indicators of compromise



SHA256 Hashes


00260c390ffab5734208a7199df0e4229a76261c3f5b7264c4515acb8eb9c2f8


0545f842ca2eb77bcac0fd17d6d0a8c607d7dbc8669709f3096e5c1828e1c049


2ba9fab56458fe832afecf56aae37ff89a8b9a494f3c2570d067d271d3b97045


4de287e0b05e138ab942d71d1d4d2ad5fb7d46a336a446f619091bdace4f2d0a


743ecc953dcd83a48140c82d8a7dcac1af28e0839aed16628ddfc9454bec8dfa


8155c6bea7c1112f022e9c70279df6759679295bd4d733f35b6eea6a97d3598f


856d5253f68bebcba161bc8f8393f34c806717faa6297c669c75fb13b17f8d03


9bca4fe6069de655467e59929325421b93617bccfdf23e9fba02615d36d60881


a98ffa66c07f634d19dc014bb2d63fa808d7af5dc9fb9b33aa19a8b944608816


acad2d9b291b5a9662aa1469f96995dc547a45e391af9c7fa24f5921b0128b2c


b3faf5d8cbc3c75d4c3897851fdaf8d7a4bd774966b4c25e0e4617546109aed5


dd8fe3966ab4d2d6215c63b3ac7abf4673d9c19f2d9f35a6bf247922c642ec2d


ea028ec3efaab9a3ce49379fef714bef0b120661dcbb55fcfab5c4f720598477


f32e9fb8b1ea73f0a71f3edaebb7f2b242e72d2a4826d6b2744ad3d830671202


f3e891a2a39dd948cd85e1c8335a83e640d0987dbd48c16001a02f6b7c1733ae


Scroll to view full table 


lockbit | ransomware attacks | IBM X-Force Research | Ransomware | Ransomware-as-a-Service (RaaS) | X-Force




Megan Roddie
Cyber Threat Researcher - IBM X-Force IRIS






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














