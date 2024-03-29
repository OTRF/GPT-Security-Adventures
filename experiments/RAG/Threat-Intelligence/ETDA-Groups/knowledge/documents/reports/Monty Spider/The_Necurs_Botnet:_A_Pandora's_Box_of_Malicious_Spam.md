# Reference for threat actor for "Monty Spider"

**Title**: The Necurs Botnet: A Pandora's Box of Malicious Spam

**Source**: https://securityintelligence.com/the-necurs-botnet-a-pandoras-box-of-malicious-spam/

## Content




 

The Necurs Botnet: A Pandora's Box of Malicious Spam










































































































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








































The Necurs Botnet: A Pandora’s Box of Malicious Spam 








 





Light
Dark






April 24, 2017
By Limor Kessem

  11 min read




Malware
Banking & Finance
Fraud Protection
Threat Intelligence














 


This is the tale of a cybercrime botnet operation that, within about five years of its existence, has been named one of the largest botnets in the world.
It’s called the Necurs botnet. It militarizes up to 6 million zombie endpoints, delivers some of the worst banking Trojans and ransomware threats in batches of millions of emails at a time, and it keeps reinventing itself. The bottom line is that Necurs is indirectly responsible for a major chunk of cybercrime and the losses it produces. According to reports, cybercrime damages are expected to cost the world $6 trillion by 2021. This magnitude alone makes it worthwhile to get to know more about one the top players in that nefarious game.
Read the white paper: Shifting the balance of power with cognitive fraud prevention 
Necurs: The Nitty Gritty
Cybercrime history has had its share of malicious botnets and evil infrastructure in the past two decades, including Grum, Storm and Conficker. But while most past cases were single-flavored in terms of their lifetime vocation, one resilient and active example definitely stands out: the multipurpose Necurs botnet.
Necurs emerged in 2012 as an infector and rootkit, and quickly partnered with elite cybercrime gangs to become part of the top spamming and infection forces in the malware realm. Unlike most botnets, Necurs stands out due to its technical complexity, partnership diversity and continued evolution in an era when even the most complex malicious infrastructures can no longer withstand disruption.
In the past year alone, we have seen Necurs take on various roles. Linked with the spam distribution of the Dridex gang, it is used to spread one of the world’s most nefarious banking Trojans. It also moved to mass distributing Locky, Dridex’s ransomware child, then added distributed denial-of-service (DDoS) attacks. Most recently, Necurs moved to pump-and-dump stock scam distribution before returning to spreading millions of Dridex-laden spam emails a day.
This article will take you through the history of Necurs, a botnet dubbed “one of the world’s largest spam botnets.” It will take you down the rabbit hole of its evil partnerships with the most infamous cybercrime gangs, including Necurs’ varying current activity, which was recently renewed with a couple of peculiar surprises.
2012: Necurs Launches With a Bang
The Necurs botnet emerged in late 2012 and launched with a bang when it was reportedly detected in over 83,000 infections on endpoints all over the world. Necurs never had a humble beginning. Right from the start, it was clear that its operators were not only well-versed in operational security, but they were also well-connected in to the cybercrime elite in Eastern Europe, revealing the level of their customers to this very day.
Upon its emergence, Necurs’ operators started using a Dot-Bit domain to create a peer-to-peer network that would allow them to evade detection in quite an interesting manner. The bit top-level domain (TLD) was created outside the domain name system, which means it is not controlled by the Internet Corporation for Assigned Names and Numbers (ICANN).
This resulted in a decentralized Domain Name Server (DNS) in which the TLD is not owned by any single entity and DNS lookup tables are shared only on a peer-to-peer basis. This means that DNS servers can be neither updated nor seized by any authority, and once a domain is registered, only its owner can control it. Access to the Dot-Bit domains was limited to those using a very particular proxy setting, which Necurs had configured inside its own code. This uncommon workaround is clever, but more than that, it was rather telling of what’s to come.
2013: Game-Not-Over Zeus
By 2013, Necurs went into second gear and started leveraging the Upatre loader to make way for itself and delivering the Gameover Zeus (aka Zeus P2P) malware to compromised endpoints. It is a known fact that Gameover Zeus was a malware variant developed and controlled by none other than Zeus’ original developer and his cybercrime gang. This suggests that the Necurs operators were linked to the very centrum of the banking malware elite in the early days.
In 2014, Necurs continued to bolster Gameover Zeus’ resilience on infected endpoints, this time as an exploit-laden kernel-mode rootkit, one of the most invasive and persistent holds malware can have on a Windows PC. Malicious emails or malvertising campaigns carrying Upatre would download Gameover Zeus into a compromised PC. This time, Gameover Zeus was the one to run Necurs. Necurs’ rootkit features made it nearly impossible to remove Gameover Zeus from the infected PC.
2014 to 2015: The Ransomware Era
Unsurprisingly, by the time law enforcement disrupted the Gameover Zeus botnet in late 2014, it had already grown its secondary income source: CryptoLocker ransomware. CryptoLocker was one of the most infamous ransomware codes at the time, and a cybercrime business that reaped an estimated $30 million in illicit profits within a mere 100 days. It was disrupted alongside Gameover Zeus and has not returned since. As you can see, Necurs always kept very bad company. Pretty much the worst.
Following the booming ransomware trend that picked up speed in 2015, Necurs continued to distribute crypto-ransomware Trojans that year, sometimes through well-known exploits kits such as Magnitude and Angler. One of its favorites was apparently CryptoWall, the successor to CryptoLocker. Necurs’ operators continued to reap the rewards of associating themselves with cybercrime lords; CryptoWall’s operators stole no less than $325 million from infected victims in the first half of 2015, most of which were located in the U.S.
2016: The Dridex-Locky Gang Era
By 2016, Necurs turned a new page in its operations. It started using its million-strong botnet as a spamming infrastructure and launched a partnership, by no means lesser than its previous one, with the Dridex malware gang.
Dridex is a sophisticated modular banking Trojan project based the original Bugat Trojan’s source code. Dridex first emerged in June 2014 and rapidly evolved into one of the top malware threats in the financial sector. It targets banks in over 30 countries across the globe, focusing on businesses and robbing its victims of millions of dollars in each attack.
Dridex’s owners are believed to be an organized cybercrime gang that calls itself Evil Corp, thought to have spun off from the Business Club, another Eastern European organized cybercrime gang. The Business Club was accused of stealing more than $100 million from banks and companies worldwide.
Evil Corp is infamous for defrauding corporate banking customers, nefarious tactics dubbed Dyre Wolf attacks. Using Dridex as its tool, the gang mixes its advanced technical capabilities, such as redirection attacks and hidden VNC remote control modules, with social engineering and advanced persistent threat (APT)-style planning. Its most recent major version upgrade exemplified its operators’ skill level and sophistication grade, and its potential involvement in SWIFT heists in 2016 offers a hint as to the circles it moves in.
Necurs’ Dridex spam service resulted in some hefty spam campaigns in 2016, alongside some spam for other gangs such as Shifu, TeslaCrypt ransomware, Neverquest and others. It was at that time that it also started distributing a new ransomware variant: Locky. Due to its in-tandem campaigns originating from Dridex-spewing sources, Locky was tied both to Dridex and to the Necurs botnet.
In an up-and-down style that’s rather typical of the Dridex malware, Necurs campaigns came to a halt starting in late May 2016 due to a possible glitch in the botnet’s infrastructure. Researchers operating a Necurs sinkhole noted that after a sudden 24-hour outage of its command-and-control server (C&C), nearly 1.1 million Necurs-infected hosts attempted to connect to the sinkhole in search of a new C&C, revealing the botnet’s true magnitude.
Following that outage, Necurs’ spam volumes, which used to peak at hundreds of millions of messages, dropped drastically, and with it dropped spam volumes delivering both Dridex and Locky. But it did not take Necurs long to recoup. By late June 2016, it was back online, delivering hordes of Locky- and Dridex-laden spam emails to unsuspecting user inboxes. The activity was ramped up throughout summer of 2016, and then came to yet another halt in December 2016.
2017: Q1 Hiatus and Relaunch
And so the Necurs botnet went into yet another unexplained lull after the holiday season, when it is quite customary for cybercriminals to slow down. Many expected Necurs to return in January, but things remained pretty quiet, with limited campaign volumes all the way until late February 2017. Researchers observed roughly 50,000 IPs related to spam attacks in their blacklists during this time, as opposed to approximately 350,000 to 400,000 while Necurs was active.

Source: IBM X-Force
February 2017: Enter DDoS
In February 2017, the Necurs botnet started rearing its more familiar ugly head once again, coming back with new tricks up its sleeve. This time, Necurs made the rounds, serving itself with a side of DDoS module that was added to it back in September 2016. For size, with over 1 million active bots at any given time, a DDoS attack leveraging the Necurs botnet could far exceed the volume and effect of attacks the size of recent Mirai botnet onslaughts.
March 2017: Pump-and-Dump Stock Scams
Next up, Necurs diversified its portfolio, and in March 2017, it swamped masses of email boxes with pump-and-dump stock scams — quite a peculiar choice considering its malware-ridden past. IBM X-Force researchers started seeing a sharp rise in Necurs spam on March 20, 2017. At that point, the botnet was sending at least seven different versions of an email crafted to entice investors to buy shares of a little-known media holding company in the U.S.
This new trend for Necurs was somewhat surprising, since penny stock scams are considered rather outdated. Yet it appears that Necurs succeeded in pumping its unwitting target’s stock value, which may have enabled its operator to reap the illicit rewards. It likely worked well enough, because Necurs was right back at it a week later with yet another target. This time, a small firm that develops marketing channels to distribute third-party fitness equipment to wholesale markets in the U.S. was the subject of Necurs’ affection. Necurs’ botnet succeeded yet again, pumping the stock price high enough to yield a profit to those who stand behind it.
April 2017: Dridex Spam Skyrockets
In the wake of the ongoing penny stock scams that flowed out of Necurs bots in March, the botnet’s operators also went back to serving one of their most infamous customers: the Dridex Trojan.
Dridex’s developers were hard at work during the first quarter of 2017, tweaking the malware’s capabilities. But they also got ready for something bigger: a major version release. It’s no coincidence that they then launched into a multimillion-message spam campaign, delivering Dridex via an unpatched Microsoft Word exploit.
On the side, Necurs has been delivering Kegotip via the Upatre loader for at least a year now. This is merely a low-grade information stealer with a pretty nefarious loader, right? But one of Kegotip’s main functions is scraping email addresses from hard drives of endpoints it infects, even crossing to additional partitions on the endpoint. This generates quite a handsome bounty for its operators, likely in the form of the Necurs botnet itself, which then uses these addresses in its spam runs. Kegotip has been appearing alongside Dridex and Locky infections since April 2016, either via the RockLoader or Upatre.
While Necus is focused on spreading itself over its newfound endeavors, Locky spam slipped down and let the Cerber ransomware snatch its crown as the most prevalent ransomware pest in the cybercrime arena in the first quarter of 2017.
April 2017: What’s Love Got to Do With It?
April 2017 campaigns originating from Necurs are apparently spreading dating spam, advertising a website that specializes in Russian dating prospects for Western men.
According to data from X-Force research, Necurs blasted out 7,087,535 emails using one of the formats of this spam in just one day in April.

Source: IBM X-Force
Why would Necurs, which was purely a malware botnet serving the most sophisticated malcode and being linked with exploit kit operations, suddenly start sending the lower end spam? The mastermind behind one of the largest spam botnets, Kelihos, was recently arrested by the U.S. Justice Department in Barcelona, Spain. Now that this Russian national, who is considered “one of the world’s most notorious criminal spammers,” is out of the game, Necurs might be filling in for the Kelihos botnet, spamming for junk mail customers in its stead.
What Makes Necurs Resilient?
What allows Necurs to remain a large and resilient botnet over time? It has already been dubbed “the world’s largest spam botnet,” and it continues to thrive in a climate of botnet takedowns and law enforcement pursuit. Let’s look at the factors that contribute to its strength.
Kernel Mode-RootKit
The most significant point about Necurs is that, unlike common botnet malware such as Kelihos, Necurs has kernel-mode rootkit capabilities. It is composed of a kernel-mode driver and a user-mode component. Kernel-mode rootkits are malicious applications that run in the kernel of the OS with absolute rights to system resources, including both software and hardware, which grants them the deepest privilege level, right in Ring 0.
Programming kernel-mode rootkits is considered an advanced skill, and any error in code can cause the kernel to crash, thus disabling the entire operating system. This is why very few malware codes possess this capability, and few ever did. For Necurs, it means that once it is on a newly infected endpoint, it is unlikely to get detected by antivirus applications, which run in Ring 3 (user mode). It will also be very hard, if not impossible to remove.
Modular Architecture
Another notable point about Necurs is its modular architecture. Typical botnet malware that’s only designed to amass bots for other purposes, spread spam or download other malware is relatively simple in technical terms. That is not the case with Necurs. The latter is built in the same way that the most sophisticated Trojans are built, in a modular fashion that allows it to take on different new features as its developers see fit.
Necurs’ modularity is what allows it to switch things up when its operators choose to change its vocation, partner with other malware distributors, use it for pure spam, or leverage its hold on infected endpoints to deliver malware or be delivered as such.
Anti-AV Features
Judging by its spam volume capacity, Necurs manages to infect a large number of endpoints. It is believed to control between 5 and 6 million zombie bots, of which at least 1 million are active at any given time. A sizeable operation indeed. How does it manage to get on so many computers?
It is very possible that this is exactly where Necurs’ kernel-mode feature comes in, backed up by an ability to disable security solutions, down to their actual driver components in some cases, as well as the Windows firewall. The malware ensures that it is met with little to no resistance, which was one of the most significant enablers of Gameover Zeus infections in 2014.
A Double-Edged DGA
Domain generation algorithms (DGA) are seen in various families of malware that are used to periodically generate a large number of domain names to be used as rendezvous points with their C&C servers. Without breaking the algorithm that spews them, each domain name is unpredictable and made up of incoherent sets of letters. These domains are therefore impossible to sinkhole or use to identify malware families when examined individually.
Most modern-day malware, especially banking Trojans, use DGAs to keep their communication channels with their armies of infected bots secret and undisturbed. Necurs uses not one, but two DGAs. To keep its communication channels constantly switching, Necurs employs three different sets of host names, two of which are algorithmically generated:

DGA No. 1 is tasked with detecting lab environments to prevent Necurs from running in a sandbox. This DGA only generates four domains at a time.
Hardcoded set, which is a predetermined list of domains that may be used as a fallback to call the C&C server. This phase cycles between 16 domains. If there is only one domain on the list, Necurs will repeat it 16 times.
DGA No. 2 is tasked with generating 2,048 domain names, covering over 43 different TLDs. These die out every four days.

Such feature is rare for botnet malware, and even sophisticated banking Trojans use only one DGA layer. This makes Necurs more resilient to potential interception and harder to take down overall.
It is worth going back to Necurs’ early days here. Its domain name schema involved .bit domains and the use of Namecoin to access them, making them virtually noncensorable. The intricacy of that schema was but a precursor for Necurs’ increasing technical sophistication.
2017 and Beyond: What’s Next?
What’s next for Necurs, the big bad botnet and its many malicious hats? It is only a logical deduction at this point that Necurs has attracted attention from law enforcement and authorities and is a prime candidate for takedown. But judging by its resilience model, will it actually topple?
In September 2015, a number of entities partnered to take down the Dridex botnet. The elaborate operation was successful for a small amount of time. By October 2015, Dridex was back thanks to the same features that continue to keep it alive.
They say the way to predict behavior relies much on past behavior. If so, Necurs is bound to keep its ties with the top malware operators on the cybercrime scene. It will continue to diversify its portfolio of illicit income in 2017. Unless it is properly disrupted, we are likely to see more of its wrath.
Mitigating Advanced Threats
The Necurs botnet carries powerful malware, but it can never be a match for good browsing and computer hygiene practices. To keep up to date about the threats that are most relevant to your organization, join IBM’s X-Force Exchange and tailor your feeds to receive pertinent and timely threat intelligence.
Organizations looking to protect their users from malware linked with the Necurs botnet are invited to learn more about IBM Trusteer Advanced Fraud Protection and IBM BigFix Detect. Consumers looking for best practices to protect themselves from malware infections are invited to read our advice page on the subject.
Read the white paper: Shifting the balance of power with cognitive fraud prevention 


Advanced Threats | Botnets | Cybercrime | Dridex | Gameover Zeus (GOZ) | Locky | Malware | Ransomware | X-Force




Limor Kessem
Principal Consultant, X-Force Cyber Crisis Management, IBM









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














