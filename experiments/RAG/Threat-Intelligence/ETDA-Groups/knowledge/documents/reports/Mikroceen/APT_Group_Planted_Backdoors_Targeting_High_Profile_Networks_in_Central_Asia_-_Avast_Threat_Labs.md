# Reference for threat actor for "Mikroceen"

**Title**: APT Group Planted Backdoors Targeting High Profile Networks in Central Asia - Avast Threat Labs

**Source**: https://decoded.avast.io/luigicamastra/apt-group-planted-backdoors-targeting-high-profile-networks-in-central-asia/

## Content








APT Group Planted Backdoors Targeting High Profile Networks in Central Asia - Avast Threat Labs


























































 







 


Mobile
Network
PC
IoT
Careers
 
Menu






Search


 








 


Menu






 


APT Group Planted Backdoors Targeting High Profile Networks in Central Asia 
by Luigino CamastraMay 14, 20209 min read 









Last fall, APT malware intrusions targeting high-profile companies in Central Asia caught our attention. A few months later, we began working together with fellow malware analysts from ESET to analyze samples used by the group to spy on a telecommunications company, a gas company, and a governmental institution in Central Asia. An APT group, which we believe could possibly be from China, planted backdoors to gain long-term access to corporate networks. Based on our analysis, we suspect the group was also behind attacks active in Mongolia, Russia, and Belarus.
The group behind the attack frequently recompiled their custom tools to avoid AV detection, which, in addition to the backdoors, included Mimikatz and Gh0st RAT. This has led to a large number of samples, with binaries often protected by VMProtect, making analysis more difficult.
The backdoors gave the actors the ability to manipulate and delete files, take screenshots, manipulate processes, and services, as well as execute console commands, remove itself, and more. Further, some commands may have instructed the backdoors to exfiltrate data to a C&C server. Infected devices could also be commanded by a C&C server to act as a proxy or listen on a specific port on every network interface. The group also used tools such as Gh0st RAT and Management Instrumentation to move laterally within infiltrated networks.
Timeline
Figure 1: Timeline of events related to the tracking of Microcin, and Avast notifying the targeted company
Avast’s and Eset’s antivirus engines blocked the samples used by the APT group prior to it attracting our attention, as our antivirus engines’ detections are automated.
Attribution & Clusterization
The samples we analyzed contain links to malware samples and campaigns, such as Microcin, BYEBY, and Vicious Panda, previously described by Kaspersky, Palo Alto Networks, and Check Point, respectively. The backdoors we found are custom tools that have not previously been analyzed, as far as we know. The majority of the C&C servers are registered to Choopa, LLC, a hosting platform that has been used by cybercriminals in the past. A GoDaddy registrar was also seen early in the campaign, these servers were removed early on.
We suspect the APT group behind these attacks is from China. Gh0st RAT, one of the tools used, has been known to be used by Chinese APT groups in the past. Similarities in the code used in the Vicious Panda campaign, (TTPS, especially the use of the RTF Weaponizer in the infection vector), which is also thought to have come from China, and the code we analyzed, also lead us to believe the group might be from China. The targeted companies and institutions, as well as the professional coding point to an APT group.  
Toolset
Backdoors
Throughout our analysis, we stumbled upon the following backdoors. Details on these backdoors are provided below the complete list of backdoors.
sqllauncher.dll (VMProtected backdoor)
bbc5a9a49757abdbfcaca22f3b2a8b7e79f61c30d31812a0ccc316536eb58ca3C&C server 45.76.132[.]207
logon.dll (VMProtected backdoor)
61e4c91803d0d495681400fb9053b434f4852fdad1a305bbcec45ee0b2926d6aC&C server 45.76.132[.]207
logsupport.dll (VMProtected backdoor)
 d5c1e947d84791ac8e6218652372905ddb7d3bc84ff04e709d635f60e7224688C&C server  104.194.215[.]194
pcaudit.bat 
1395B863AE5697EA5096F4E2EBEF54FC20D5380B6921F8835D1F030F2BA16A40
Technical details (pcaudit.bat)
pcaudit.bat is a batch file that is used to invoke the svchost.exe in order to load the DLL file for a given service specified in the registry. This batch file is responsible for the backdoor’s persistence. The contents of the pcaudit.bat script can be found below:

Figure 2: The batch file that is responsible for the backdoor’s persistence

Technical details (sqllauncher.dll, logon.dll) 
Both DLLs, sqllauncher.dll and logon.dll, are primarily used as backdoors. These are installed as services by the aforementioned batch file. They both create a log file under the path: %COMMON_DOCUMENT%\WZ9JuN00.tmp aggregating errors during the backdoor’s runtime. Each entry contains an error code, an error message, and a timestamp formatted as “[yyyy-mm-dd hh-mm-ss] %error code% %message%”. 
If the infected device can’t connect to the C&C server, the malware attempts to determine whether the traffic is routed through a proxy. This information may be retrieved either from %WINDOWS%\debug\netlogon.cfg or from the TCP table. After successfully connecting to the C&C server, a secure communication channel (Schannel) is established and telemetry (OS version, username) is sent to the C&C server. The following commands are issued by the C&C server:
CommandSubCommand ParameterDescriptionOriginal commandAmbYDkEx––Send malware version to the C&CWELCOMeYTS5IwW––Terminate previously launched payloadKi0Swb7I––Send all used drive letters to the C&CLIST D5fdi2TfG––Start remote shellSTARTCh71RBG8X–%command%Execute “cmd %command%” via CreateProcess APIJ8AoctiBQHbU0hQo%path%, %subcommand%Read from %path% and send data to C&CUPLOADJ8AoctiBhwuvE43y%path%, %subcommand%,%data%Write %data% into %path%DOWNLOgRQ7mIYr–%command%Execute %command% via CreateProcess APIEXECUT
Technical details (logsupport.dll)
Similarly to the previous DLLs, the logsupport.dll is primarily used as a backdoor, but uses a different C&C server than the other backdoors. Its corresponding log file is located at %TEMP%\rar%[A-Z0-9]{4}%.tmp. The structure of the log file is also the same. The main difference is that the log file is encrypted by a XOR cipher with a hardcoded key.
Figure 3: Log file is decrypted by a XOR cipher with a hardcoded key
This backdoor checks whether the malware is running in a virtualized environment. Additionally, the DLL fingerprints the infected device (NETBIOS name, IP address, username, OS version, MAC address and RAM usage, OEM code page, token information, number of CPU cores, is64bit), and sends this information to the C&C server.
The communication with the C&C server is encrypted by a simple stream cipher. If the malware fails to establish an encrypted channel, it checks whether a proxy is being used, using different methods than the previous two DLLs. It tries to connect to http://www.google.com/index.asp and retrieve information about a possible proxy from the connection, and it also checks the value of ProxyServer in the Windows registry key:
HKLM\Software\Microsft\Windows\CurrentVersion\Internet Settings.
Based on what we saw in the code, the backdoor is also capable of accepting various commands from the C&C server. These commands allow the backdoor to manipulate files (move, read, delete, check existence), manipulate processes (create, terminate, retrieve parent, and process ID) and Windows services (start, stop, check), execute console commands, remove itself, and more. Some of these commands (read/check file, check services, check processes) also send data back to C&C. The infected device can also be commanded by C&C to act as a proxy or listen on a specific port on every network interface.
Interestingly, the backdoor has a set of commands specifically targeting files with .tu and .tut file extension. These commands may similarly check for their existence, send their content back to the C&C, and modify their content (append or rewrite by data given by the C&C server).
Other tools
Lateral Movement via Mimikatz
fc66353fb26fd82227700beb47c4fa90118cea151eb1689fd8bf48e93fda71d0
Mimikatz is an open source project by a French security researcher named Benjamin Delpy which started in 2007. It is a robust tool that exploits various Windows authentication schemes and dumps credential-related data from a Windows Local Security Account database. For these reasons it is often misused by a wide spectrum of APT actors such as the Lazarus Group or Telebots.
The Mimikatz version used in this campaign has a two-stage installation mechanism (installer.exe installing Yokel64.exe and mktz64.dll), and contains a PDB string “E:\2018_\MimHash\mimikatz\Bin\mktzx64.pdb”. Calling a mktz64.dll exported function MktzDumpbyInjection inside our testing virtual machine yields the following output:
#1 domain = MSEDGEWIN10, user = Administrator ,nthash=FC525C9683E8FE067095BA2DDC971889 #2 domain = MSEDGEWIN10, user = IEUser , nthash=FC525C9683E8FE067095BA2DDC971889
Lateral Movement via WMI
2615e5585a5db77b973c74e0a87551978a9322c820362a148a995e571923b59c
The lateral movement via WMI is done with a file that parses its own filename, which we suspect uses the following format: “@@<ComputerName>,<UserName>,<Password>,.exe”. Afterwards, the data described in the filename is extracted and used to establish a remote console to a computer identified by the retrieved name. Afterwards, Windows Management Instrumentation (WMI) is leveraged to set a strict proxy security, leading to the encryption of arguments of each remote procedure call, and allowing the server to access local resources. Then WMI is used again to retrieve the Win32_Process class which in turn is used to create a process with given parameters. At the end, it terminates itself.
Gh0st RAT
3a3b05a08180013a37fbdbe65e3fe017440c1cb34289647ef1f60316964ef6a9
Gh0st RAT is an old well-known backdoor, predominantly associated with East-Asian attackers. It is commonly assumed that its source code is widely available. Its presence is often indicated by a file named rastls.dll, using an export DLL name svchost.dll and containing a string Gh0st. A string uwqixgze} is used as a placeholder for the C&C domain.
The version we’ve seen in this campaign tries to connect to https://yuemt.zzux[.]com.
Figure 4: Gh0st RAT malware
Code Similarities
While analyzing one of the files, we noticed that it has several correlations to the Microcin sample from 2017, the BYEBY sample from 2017, and Vicious Panda: The COVID campaign from 2020. Figure 5 below provides a comparison of the decryption loop used to decrypt the main configuration data of the first backdoor.
Figure 5: Part of code used to decipher the main configuration data
Name of fileSHA256irmon.dll170008187EBCEF183E792513608B82572FAF0AAEB33212BFA44736439453218Fcryptbase.dll383A2D8F421AD2F243CBC142E9715C78F867A114B037626C2097CB3E070F67D6NWCWorkstation.dll2A42F500D019A64970E1C63D48EEFA27727F80FE0A5B13625E0E72A6EC98B968nwsapagent.dll92315CDCDD3ECDAFBAC1D46EF872AAA333E1EA159D662CB61C4FA029D3896DF7
Conclusion
Avast reported its findings to the local CERT team and reached out to the telecommunications company. We have not heard back from either organization.
Avast has recently protected users in Central Asia from further attacks using the samples we analyzed. This, along with tying elements of the samples we discovered back to attacks carried out on other countries, makes me assume the group is still active. 
I would like to thank Peter Kalnai from ESET for working with me on the analysis, Lukáš Obrdlík, and Adolf Středa from Avast for helping me with this research, as well as Alexey Shulmin from Kaspersky for his support.
Indicators of Compromise (IoC)
 Repository: https://github.com/avast/ioc/tree/master/Microcin List of SHA-256: https://github.com/avast/ioc/blob/master/Microcin/samples.sha256
References
Vasily Berdnikov, Dmitry Karasovsky, Alexey Shulmin: “Microcin malware”, Kaspersky Labs 2017-9-25 https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07170759/Microcin_Technical_4PDF_eng_final_s.pdf
Josh Grunzweig, Robert Falcone: “Threat Actors Target Government of Belarus Using CMSTAR Trojan”, Palo Alto Networks, September 2017, https://unit42.paloaltonetworks.com/unit42-threat-actors-target-government-belarus-using-cmstar-trojan/
Checkpoint Research: “Vicious Panda: The COVID Campaign”, 2020-03-12 https://research.checkpoint.com/2020/vicious-panda-the-covid-campaign/
Avast Threat Intelligence https://github.com/avast/ioc
ESET Threat Intelligence https://github.com/eset/malware-ioc
Dhia Mahjoub, Jeremiah O’Connor, Thibault Reuille, Thomas Mathew: “Phishing, Spiking, and Bad Hosting”, Cisco Umbrella Blog, 2015-09-14
https://umbrella.cisco.com/blog/2015/09/14/phishing-spiking-and-bad-hosting/
https://github.com/gentilkiwi/mimikatz



Tagged asAPT, backdoor, Central Asia 
Share:XFacebook







Further reading









PC 


Decrypted: Rhysida Ransomware 
February 13, 2024by Threat Research Team 


The team at Avast has developed a decryptor for the Rhysida ransomware and released it for public download. The Rhysida ransomware has been active since May 2023. As of Feb 2024, their TOR site lists 78 attacked companies, including IT (Information Technology) sector, healthcare, universities, and...

 





MobilePCReports 


Avast Q4/2023 Threat Report 
February 7, 2024by Threat Research Team 


10 Billion Attacks Blocked in 2023, Qakbot's Resurrection, and Google API Abused

 





PC 


Avast Updates Babuk Ransomware Decryptor in Cooperation with Cisco Talos and Dutch Police 
January 9, 2024by Threat Research Team 


In cooperation with Cisco Talos and Dutch Police, Avast is releasing an updated version of the Avast Babuk decryption tool, capable of restoring files encrypted by the Babuk variant called Tortilla.

 











2024 Copyright © Avast Software s.r.o.











































 



Menu
Mobile
Network
PC
IoT
Careers
 


Search


 

Categories

Events

IoT

Mobile

Network

Other/Research

PC

Reports


Tagsanalysis
Android
APT
backdoor
botnet
brazil
cryptocurrency
cryptomining
csrf
ddos
decryptor
decryptors
desktop
DirtyMoe
dns hijack
dropper
exploit
fake-app
ghostdns
Google Play Store
HW
iot
malware
mobile
obfuscation
P-Code
phishing
ransomware
rat
report
Research
reversing
risk
rootkit
router
security
series
spyware
stealer
takedown
threat-intel
threats
VB
vulnerability
worm


Recent Posts


Decrypted: Rhysida Ransomware


Avast Q4/2023 Threat Report


Avast Updates Babuk Ransomware Decryptor in Cooperation with Cisco Talos and Dutch Police


Opening a new front against DNS-based threats


Avast Q3/2023 Threat Report


Archive

February 2024
January 2024
December 2023
November 2023
October 2023
September 2023
August 2023
July 2023
June 2023
May 2023
April 2023
February 2023
January 2023
December 2022
November 2022
October 2022
September 2022
August 2022
July 2022
June 2022
May 2022
April 2022
March 2022
February 2022
January 2022
December 2021
November 2021
October 2021
September 2021
August 2021
July 2021
June 2021
May 2021
April 2021
March 2021
February 2021
December 2020
November 2020
October 2020
September 2020
August 2020
June 2020
May 2020
April 2020
December 2019
September 2019
August 2019
July 2019
April 2019
March 2019
February 2019
January 2019
August 2018
January 2018
October 2017

Meta

Log in
Entries feed
Comments feed
WordPress.org











