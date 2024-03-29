# Reference for threat actor for "Wizard Spider, Gold Blackburn"

**Title**: The Curious Case of a Fileless TrickBot Infection

**Source**: https://securityintelligence.com/posts/the-curious-case-of-a-fileless-trickbot-infection/

## Content




 

The Curious Case of a Fileless TrickBot Infection











































































































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








































The Curious Case of a Fileless TrickBot Infection 








 





Light
Dark






August 8, 2019
By Ofir Ozer

  7 min read




Malware
Threat Intelligence














 


IBM X-Force Research actively watches the banking Trojan threat landscape and helps defenders learn more about threats as they evolve. In a recent analysis in our cybercrime research labs, we noticed changes in the deployment of the TrickBot Trojan. At the time, the change we observed only applied to infection attempts on Windows 10 64-bit operating systems (OSs). In those cases, TrickBot ran the payload, but did not save its typical modules and configurations to disk.
X-Force malware researcher Ofir Ozer took a closer look at this change in TrickBot’s deployment routine and found that it was a fileless version. Let’s look into the changes and the possible reasons they were implemented.
Special thanks to X-Force researchers Maor Wiesen and Amir Tal for collaborating on the initial research.
What Is TrickBot?
TrickBot is one of the top crimeware codes and cybercrime gangs in existence today. The malware emerged in August 2016 and launched into a testing and development period. It is a modern, sophisticated and modular Trojan horse that bears a striking resemblance to the Dyre Trojan’s capabilities. The malware’s modularity means that its executable file relies on pulling extra modules from its command-and-control (C&C) server to grant its operators better control and access to the infected device.
TrickBot’s modules contain the malicious functions it uses to trick users into divulging their online banking credentials and others that enable it to exfiltrate and receive the information. Over the years, TrickBot has constantly evolved, with its developers making frequent improvements in a quest to keep it stealthy, hard to research and able to bypass basic security controls on user devices.
While it has already seen quite a number of updates over the years, one of the most recent enhancements to TrickBot’s code was designed to help keep it stealthier on devices running Windows 10.
TrickBot’s Classic Deployment Routine
Before we discuss what changed, let’s outline the classic deployment routine of the TrickBot Trojan as it unfolds on most OS versions/architectures. After the initial infection takes place, whether coming through a booby-trapped productivity file or a loader, a newly infected device runs the malware’s executable file, creating a folder inside the %APPDATA% local user folder with a different hardcoded name on each version.
Next, TrickBot copies its payload with a generated name and creates a scheduled task that runs the copied file with SYSTEM privileges. The scheduled task is the Trojan’s persistence mechanism. It is set to run at startup, a minute after the task is created, and then every nine minutes from that point on. As the scheduled task is triggered, the malware extracts and executes a shellcode in its own memory space.
The Architectural Divide
TrickBot’s main payload may be a 32-bit PE file, but it uses different payloads to ensure compatibility with both 32- and 64-bit architectures. To use the right piece, the malware checks which architecture it is running on.
In the case of a 32-bit OS, a 32-bit shellcode is decrypted and executed in the malware’s memory space. When running on a 64-bit OS, the malware creates a new svchost process in suspended state. Next, a 64-bit shellcode is decrypted and injected into the suspended svchost process. The instruction at the entry point is made to jump to the injected code, a standard part of the process hollowing technique.
For this injection to work, the malware preforms a switch from 32-bit compatibility mode to 64-bit using a known technique called Heaven’s Gate. It is a misdirection on Windows 64-bit systems that was discovered in the mid-2000s. By using Heaven’s Gate, the attackers can have 32-bit applications running on 64-bit systems trick the OS into executing 64-bit code, despite initially appearing to be 32-bit processes.
In TrickBot’s case, both the 32- and 64-bit shellcodes operate in the same fashion, but it’s important to understand that the main process of the malware differs between the two architectures. In the 32-bit case, the scheduled task triggers the executable; in the 64-bit case, it’s the injected svchost that triggers the executable.

Figure 1: The process tree in 32-bit vs 64-bit systems
Configuration Extraction
For TrickBot’s configuration, the main process extracts the configuration data, encrypts it and writes it to a file called settings.ini in the malware folder (inside the %APPDATA% folder) that was previously created. From this point on, the Trojan relies on its C&C servers to fetch attack modules and version updates.
Server Comms
To communicate with a control server, TrickBot’s executable has an encrypted list of IP addresses leading to potential C&C servers it could communicate with. To keep these resources protected, the list is encrypted with a symmetric AES-256 cipher.
Communication with the C&C server takes place over HTTP GET requests. Each request contains some basic information about the victim’s device and a command code. Responses from the C&C servers are also encrypted and decrypted by the malware in the same manner as the IP address list is decrypted by the bot.
Upon initial communication with the C&C server, the first response to come through is another list of server IPs. Those servers are the attack servers that will deliver TrickBot’s modules and configuration files when the bot requests them.
Each module downloaded from the attack servers is decrypted and injected into a new instance of svchost.
The injection to svchost is a technique that’s identical to the injection tactic used in the 64-bit version of the malware. TrickBot creates a new svchost process in suspended state, allocates memory in the process memory space, copies the module code to the allocated memory, and then changes the context and the state to running.
In older versions of TrickBot, the malware encrypted the modules and configuration files and then wrote them to a Data or Modules folder in the executable folder for future use.
What’s Changed? The Win10 Adaptation
In an apparent attempt to avoid detection, TrickBot’s developers have changed its installation procedure as it applies to devices running Windows 10.
Per our analysis, TrickBot modules and downloaded configuration files are no longer saved locally to the infected device, which means the malware will have to download modules and configurations anew every time it needs to reload a module or a configuration file.
Since this change only applies to Win10 deployments at this time, TrickBot has to check the environment’s details first. If it is running on any other version of Windows, the malware will write the files to disk, as usual. If it is running on Win10, it will hold off on writing to disk.
As we can see in Figure 2, there is a check before a file is supposed to be written to disk. This check is made with the global variable we called isWindows10Bool, so that if the malware is being run on a Windows 10 device, it should not write the modules and configuration files to disk.

Figure 2: To write or not to write?
However, in Windows 10’s 32-bit architecture, the modules and configuration files are still being written to the disk. To get the current OS’s version and set the right value to the global variable isWindows10Bool, TrickBot uses the GetVersionEx API call. This call gives information about the device’s OS and version, which is the most important data for the Trojan’s deployment modification.
The image below shows the GetVersionEx function being called to get the OS version:

Figure 3: Windows 10 checking function
Microsoft documentation on this function further contains the following comment:

Figure 4: GetVersionEx changes notice (source: Windows Dev Center)
Having an application manifested for a given OS version is achieved via an XML file containing settings that inform the Windows OS how to handle a program when it is started. The manifest can be embedded into the program file as a resource or located in a separate, external XML file. A mismatch can occur here because of the way the malware runs itself in a 32-bit OS versus a 64-bit OS.
For a 64-bit OS, as we discussed earlier, the malware runs a new svchost process in suspend state and injects shellcode into it. This svchost instance operates as the main executable that later performs the OS checks and downloads the required modules and configuration files. In this case, GetVersionEx would return the correct OS version value because svchost is manifested and part of the OS files.
In the 32-bit OS, the scheduled task starts the malware’s executable. This PE acts as the “main” process of the malware. OS checks and calls to GetVersionEx take place through this process, which therefore provides the malware with the wrong OS version because the malware executable is not manifested.
For this reason, in 32-Bit OS, we still see TrickBot files being written to disk as opposed to 64-bit OS deployments of the malware.
From this point onward, the malware’s operations are unchanged; it uses modules injected into svchost processes to steal passwords, deploy webinjections, steal email information and spread to other devices on the network.
The Continued Evolution of Banking Trojans
Banking Trojans have increasingly been the business of organized crime for the past few years, with the global chart topped by malware families such as TrickBot, Gozi, Ramnit and IcedID. Financially motivated threat actors’ use of TrickBot variants made this financial malware the most actively tracked gang in 2018, according to X-Force Research’s analysis of global banking Trojan activity.
It is only logical to infer, therefore, that malware authors are driven to keep evolving their codes, evading controls and shuffling their tactics, techniques and procedures (TTPs) to keep security controls guessing.
The chart below shows 2019’s most prevalent financial malware to date, with TrickBot topping the chart yet again this year.

Figure 5: Most prevalent banking Trojan families in 2019 (source: IBM X-Force)
To learn more about threats like TrickBot, join us on X-Force Exchange. To mitigate banking Trojan threats to users, find out how IBM Trusteer can help fight fraud and establish digital identity trust.


Advanced Malware | Advanced Threats | Banking Trojan | Cybercrime | Finanacial Malware | Financial Industry | Malware | Malware Analysis | Microsoft | Microsoft Windows | Threat Intelligence | TrickBot | Windows | Windows 10




Ofir Ozer
Malware Researcher for Trusteer IBM






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














