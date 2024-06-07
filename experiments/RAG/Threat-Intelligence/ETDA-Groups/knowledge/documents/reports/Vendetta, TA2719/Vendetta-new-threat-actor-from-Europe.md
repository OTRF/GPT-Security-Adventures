# Reference for threat actor for "Vendetta, TA2719"

**Title**: Vendetta-new-threat-actor-from-Europe

**Source**: https://blog.360totalsecurity.com/en/vendetta-new-threat-actor-from-europe/

## Content





















Vendetta-new-threat-actor-from-Europe



































 















Blog










Back to 360 Home





Latest PostProductsCompany NewsSecurity News 





Latest PostProductsCompany NewsSecurity News 
Download







Vendetta-new threat actor from Europe
May 14, 2020kate



Tweet



Choose a language
English
Русский

 


Learn more about 360 Total Security
Starting in April this year, 360 Baize Lab intercepted a large number of attack samples from an unknown hacker organization. The hacker organization sent a phishing email to the victim by forging a police station investigation letter, COVID-19 detection notice, etc. , Through the backdoor virus to control the victim’s machine, steal valuable sensitive data related to the target.
The PDB path of the virus samples used by the organization points to a user named “Vendetta”, and we will later also name the hacker organization Vendetta:
“C:\Users\Vendetta\source\repos\{project name}\*\obj\Debug\{project name}.pdb”
In some samples, we have repeatedly detected the following tags, the virus author claims that he is from Italy:

However, we found in the naming of virus samples that virus authors like to use certain Turkish names to name variables, such as “RoboSki”, so we suspect that the organization originated in Europe:

Vendetta is a hacker organization that is very good at using social engineering. They forge phishing emails very realistically. They can easily gain users’ trust and guide users to open the malicious programs they carry.
The picture below is a Vendetta forgery of the investigation letter issued by the Austrian Federal Ministry of the Interior (BMI)

Forged investigation letter from the Romanian police station:

Forged the COVID-19 virus test email issued by the Australian Government Department of Health. The email stated that the victim had contact with a confirmed case within the past 14 days. It is recommended to read the test guide in the attachment and accept the test:
Forged a virus test email issued by the Mexican health department:

As well as the forged email quoted by the Egyptian Orascom Group:.

The compressed file in the email attachment contains the Trojan file, which is generally named after pdf.exe, Document.exe, etc. After running, it decrypts and loads the subsequent virus module in memory.

RoboSki
In all samples, we detected the same type of code obfuscator, and according to its PDB debugging path, we named it RoboSki:

RoboSki encrypts and stores the shellcode in the pixels of the picture. The following figure is the code logic to extract the available pixel data and decrypt the shellcode:

ReZer0
The execution logic of ReZer0 is controlled by hard-coded built-in instructions. According to different instructions, different malicious functions are executed. Its design logic resembles the design method of backdoor programs:

We have sorted out the hard-coded instructions and their corresponding meanings, most of which are not used:



Hardcode[x]
Description


0
[0] == 4 load the plugin from the resource into memory


[0]! = 4 Inject the plugin in the resource into the system process to execute


1
Whether to register scheduled tasks


4
Download and execute any file


5
Download file URL


6
The execution path of the downloaded file


7
Whether to detect the virtual machine


8
Whether to detect sandbox


9
ByPass antivirus software


29
Show file version


34
Sleep()


35
Sleep duration



In the 360 massive data, we found that ReZer0 has an obvious version identification. In conjunction with the above-mentioned large number of instructions used, we speculate that the software is still in the development stage, and it will not be ruled out that the program will be controlled through network communication in the future:

In addition to the nature of the backdoor virus, ReZer0 also carries known remote control Trojans such as NanoCore and Remcos in the resources. We will not repeat the remote control functions such as NanoCore. We take some of the victims of Vendetta as an example to speculate the purpose of their actions.

Passion Fruit Company of Australia (PAI) is a representative institution and a non-profit membership organization that supports the passion fruit industry in Australia. PAI is an umbrella organization that represents and enhances the interests of everyone in the passion fruit industry, including growers, packers, wholesalers, exporters, researchers, and retail stores.

Of course, Vendetta’s attack target is not only the PAI family. We have roughly described the distribution of Vendetta’s attack target by statistically the distribution of related samples, and its attack purpose is to steal related commercial information.

Summary
Vendetta is an active hacking organization that started in April 2020. The organization may have originated in Europe. It is good at using social engineering to launch cyber attacks. The purpose of the attack is to steal targeted business intelligence.
C2:
172.111.188.199:8829
Md5:
e73d9b2eba5e818cd4699f1484af5bce
dabbfc6a7d939c4c41fb2c7cee295220
dd93825ca5bd3afda1c238ce2ded84e1
500dc2b3fbea8f13b29f494afb9465ec
2106b19ffb7bf327d64d4cd6bdb606b4
e73d9b2eba5e818cd4699f1484af5bce
Learn more about 360 Total Security



Share: 











Related Articles




 


360 Total Security and the Embassy of Pakistan Reach a Cooperation






 


360 Total Security was Successfully  Shortlisted for the World Internet Conference 2022 Excellent Practice Cases






 


Data Shield, Creating a Copper Wall for Privacy Protection






 


Exclusive in-depth analysis: directly attack the key technical details of Ukraine’s cyber warfare










Facebook
Twitter

VK






Free Download
For Windows 10/8.1/8/7/Vista/XP (32,64bit)











Top Articles




CryptoMiner, ScheduledUpdateMiner, Uses Rootkit to Terminate Antivirus and Avoid Detection





Driver Updater, your ultimate driver’s problem solver





DarkSide’s Targeted Ransomware Analysis Report for Critical U.S. Infrastructure





Superfish the Adware




360 Total Security









Products

360 Total Security


360 Total Security Essential


360 Total Security Premium


360 Total Security for Mac


360 Total Security for Business





News
ProductsCompany NewsSecurity News 
Presskit


Investor Announcement





Contact us

Support


Qihoo 360





Business Partner

Affiliate


Reseller
















© 2014 - 2023 Qihu 360 Software Co. Limited














