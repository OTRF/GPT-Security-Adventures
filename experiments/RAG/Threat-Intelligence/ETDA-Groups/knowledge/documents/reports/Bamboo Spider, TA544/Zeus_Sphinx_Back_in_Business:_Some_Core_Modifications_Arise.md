# Reference for threat actor for "Bamboo Spider, TA544"

**Title**: Zeus Sphinx Back in Business: Some Core Modifications Arise

**Source**: https://securityintelligence.com/posts/zeus-sphinx-back-in-business-some-core-modifications-arise/

## Content




 

Zeus Sphinx Back in Business: Some Core Modifications Arise











































































































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








































Zeus Sphinx Back in Business: Some Core Modifications Arise 








 





Light
Dark






May 11, 2020
By Nir Shwarts



Limor Kessem


  8 min read




Malware














 


The Zeus Sphinx banking Trojan is financial malware that was built upon the existing and leaked codebase of the forefather of many other Trojans in this class: Zeus v2.0.8.9. Over the years, Sphinx has been in different hands, initially offered as a commodity in underground forums and then suspected to be operated by various closed gangs.
After a lengthy hiatus, this malware began stepping up attack campaigns starting in late 2019 and increased its spreading power in the first quarter of 2020 via malspam featuring coronavirus relief payment updates.
With Sphinx back in the financial cybercrime arena, IBM X-Force wrote the following technical analysis of the Sphinx Trojan’s current version, which was first released into the wild in late 2019. We will be covering the following components, shedding light on parts of the malware that were modified in this version, as other parts likely remained the same:

Persistence mechanism
Injection tactics
Bot configuration
Hidden configuration nuggets
Bot identification method
Sphinx’s naming algorithms

Let’s dive in.
Establishing Persistence
Almost any malware nowadays seeks to establish persistence on infected devices, both desktop and mobile, with the goal of surviving system reboots. Sphinx establishes persistence using a very common method: adding a Run key to the Windows Registry. This tactic has been used by Sphinx since its earliest versions, released in 2015.




HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run



Scroll to view full table 

Figure 1: Run key set for Sphinx’s executable payload
Since Sphinx’s malicious payload can come in two different formats, an executable file or a dynamic link library (DLL), it also sets the Registry Run key according to the format being installed. For the DLL format, we would see the following string type created:

Figure 2: Run key set for a Sphinx DLL
The malicious DLL’s entry point is named DllRegisterServer, which is usually an entry point for a COM module. When malware elects to use generic system names for its resources, it is done to blend in with the other benign elements in the operating system (OS).
Sphinx’s Code Injection Choice: Process Injection
Since its main function is to grab user credentials and other personal information from online banking sessions, Zeus Sphinx is designed with the ability to hook browser functions. Before gaining the ability to hook these types of functions, Sphinx has to ensure its stealthy ongoing operations on the OS. It does this by injecting malicious code into other processes first.
The tactic Sphinx uses is a process injection technique:

Sphinx calls on the CreateProcessA function, which creates a new process and its primary thread. The function’s parameters are msiexec.exe for the new process name and the suspend flag applied as the process state. This is another part of the malware’s stealth mechanism, as msiexec.exe usually stands for the name of a legitimate Windows Installer process that is responsible for installation, storage and removal of programs.


Figure 3: Sphinx’s process injection

It calls the WriteProcessMemory function to inject a payload into the msiexec.exe process.
Next, Sphinx changes the execution point of the targeted process to start from the injected payload, using GetThreadContext and SetThreadContext functions. GetThreadContext is used to get the current extended instruction pointer of the remote process. SetThreadContext is used to set the current extended instruction pointer of the remote process.

The extended instruction pointer holds the address of the next instruction.

Figure 4: Sphinx’s process injection
Bot Configuration
The bot’s encrypted configuration is embedded within the injected executable in msiexec.exe.
What makes it rather easy to decrypt is that both the configuration and its decryption key reside near each other in a hardcoded address location. The following function decrypts the configuration using the hardcoded addresses of each component:

Figure 5: Bot configuration decryption process
Let’s take a look at the main components of a January 2020 campaign configuration. It began with noting the malware’s variant ID by using Russian language words that translate to “2020 Upgrade” (obnovlenie2020).
Next, we see the attacker’s command-and-control (C&C) server domain list. Sphinx does not use a domain generation algorithm (DGA).
These elements can help defenders better protect networks against Sphinx infections by monitoring or blocking any communications to the listed C&C servers. The RC4 key itself is an important element to those looking to analyze the malware since it is the same key that Sphinx uses to encrypt and decrypt most of its data.
Please note that the key inside the configuration is different from the key used to decrypt the configuration itself.
In the following image, we can see an example of two different Sphinx configurations.

Figure 6: Sphinx configuration excerpts from January 2020 Campaign
Taking into consideration the date they first appeared in the wild, similar C&C domains and the same RC4 key they contain, we can conclude that both configurations are related to the same campaign. On the left, a configuration fetched by an executable-type payload and on the right, one fetched by a DLL-type payload — both are from a January 2020 campaign.
Sphinx configurations are modified as campaigns are launched, changing the C&C addresses and the RC4 keys. In the following image, we can see a newer configuration fetched from an April 2020 campaign.

Figure 7: A different Sphinx configuration excerpt from an April 2020 campaign
Please note the main differences from the January 2020 configurations: a different RC4 key, a smaller and different set of C&C domains, a changed variant ID and the precise date of publish were added.
Bot Identification
Once infected by Sphinx, every device sends information home and is defined in the botnet by a bot ID to ensure control and updates through the attacker’s server. To do that, Sphinx uses an algorithm that includes the following elements from the infected device:

Volume C GUID
Computer Name
Windows Version
Windows Install Date
Digital Product ID

We can see the generated string when we run Sphinx dynamically as well:

Figure 8: Sphinx creating Bot ID string
After creating the bot ID, it’s encrypted with an RC4 stream cipher using the key derived from the bot’s configuration and then stored in the Registry with other binary data.
For example, a key created for storing this information:
HKCU\Software\Microsoft\bmqhcn\gwehhxf
The name of the key depends on the variant of the malware and is produced by encoding some constants.
Looking at the function’s output before the result is encrypted reveals Sphinx’s bot ID layout:

[VOLUME_C_GUID][COMPUTER_NAME][2EBFF1F4][0ADE2A62]
[VOLUME_C_GUID] – Bot’s volume C GUID
[COMPUTER_NAME] – Bot’s computer name
[2EBFF1F4] – A hash of the operating system version.
[0ADE2A62] – A hash of InstallDate and DigitalProductID registry values.
Both hashes mentioned above are computed using a Sphinx internal hash function.

Sphinx’s Naming Algorithms
Malware codes often use a naming algorithm to create different names for files and resources on each infected device. They do this to evade static detection that might search for a certain file name as an indicator of compromise (IoC).
In Sphinx’s case, one naming algorithm is used to create files and resource names and a different one is used to create a unique mutex object name.
File/Resource Name Generator
Beginning with the algorithm used to create file and resource names, to create what would appear to be random names, Sphinx uses a pseudo-random number generator (PRNG) named MT19937 (also known as the Mersenne Twister). Let’s look at how Zeus Sphinx implements this PRNG to create names for its resources.
The Sphinx naming algorithm function takes four parameters to create its names: maximum length, minimum length, output buffer pointer and a binary option to upper or not the first character. As shown in the next example, these parameters are hardcoded, which can help write more regular expressions (RegEx) for detecting such names.

Figure 9: Sphinx’s naming algorithm
Let’s look at the naming_algo function:

Sphinx starts the process by decoding two hardcoded strings, which amount to 25 of the 26 English language characters:



Aeiouy
bcdfghklmnpqrstvwxz




It uses randomization for choosing the output (name) size and loops through additional steps to build it.
It randomly selects one of the two initial strings.
It randomly chooses one character from the selected string.
It appends the character to what’s going to eventually compose the generated name.
If the name has not yet met the selected length requirement, it loops back and repeats the process.


Figure 10: Choosing between the “aeiouy” or “bcdfghklmnpqrstvwxz” strings
Mutex Name Generator
Like other malware, Sphinx generates mutex names upon execution. Mutex names are often searched by security tools and researchers as a way to gather IoCs. Therefore, it can be a better way for malware to hide on infected devices if its mutex name is harder to find. The use of a unique mutex name also helps prevent the malware from infecting the same machine twice.
In Sphinx’s case, the mutex name is always a unique string created per machine, and the algorithm used to create it is relatively complicated.
To start, Sphinx uses two system data components for building its mutex names:

The device’s volume C globally unique identifier (GUID)
The current user’s security identifier (SID)

To fetch the first value, it uses the Windows function GetVolumeNameForVolumeMountPointW.

Figure 11: Sphinx composing its unique mutex name
To fetch the second value, it uses two functions: OpenProcessToken and GetTokenInformation.

Figure 12: Sphinx composing its unique mutex name
Next, to generate a unique name, Sphinx takes the following steps:

It creates a hash of the infected device’s SID value that it obtained earlier on.


Figure 13: Sphinx composing its unique mutex name

It uses the GUID to encode the SID’s hash.

This function is called seven times, with varying constants being used. Then, some of the names are randomly selected to become mutex names.

Figure 14: Sphinx generates seven different mutex names on each device
Technically, there could be seven different mutex names created on each device, which Sphinx checks for to ensure that the device is not already running the malware.

Next, using the key derived from the bot’s configuration, the mutex is encrypted with an RC4 cipher.


Figure 15: Sphinx encrypts mutex name

To make its mutex names blend in with other system elements, it calls on the function ole32!StringFromGUID2, making the names look like GUIDs.

Below is an example of two mutex names created within msiexec.exe:

Figure 16: Examples of Sphinx mutex names generated through its process
Sphinx Is Back in Business
The Sphinx Trojan emerged in 2015, at which point its main focus was banks in North America. Over the years, different operators of this malware launched it into campaigns in other parts of the world, such as the U.K., then Brazil, then Canada and Australia. Most recently, Sphinx was implemented in infection campaigns targeting users in Japan.
While Sphinx has been an on-and-off type of operation over the years, it appears it is now on-again, with version updates and new infection campaigns that are back to targeting North American banks.
While less common in the wild than Trojans like TrickBot, for example, Sphinx’s underlying Zeus DNA has been an undying enabler of online banking fraud. Financial institutions must reckon with its return and spread to new victims amid the current pandemic.
Sphinx is just one more threat we regularly cover. To learn more about emerging threats and campaigns, please join us on X-Force Exchange. Our research team also regularly releases blogs on Security Intelligence to keep you up to date on what we see in the wild.


Botnet | Banking Malware | Banking Trojan | Command-and-Control (C&C) | Cybercrime | Indicator of Compromise (IoC) | Malware | Online Banking | Online Fraud | Threat Intelligence | Trojan | X-Force | Zeus | Zeus Sphinx




Nir Shwarts
Malware Research-Reverse Engineering, IBM Security





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














