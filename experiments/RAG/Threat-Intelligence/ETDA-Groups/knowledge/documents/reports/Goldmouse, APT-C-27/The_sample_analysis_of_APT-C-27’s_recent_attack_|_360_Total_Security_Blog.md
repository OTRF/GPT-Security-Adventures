# Reference for threat actor for "Goldmouse, APT-C-27"

**Title**: The sample analysis of APT-C-27’s recent attack | 360 Total Security Blog

**Source**: https://blog.360totalsecurity.com/en/the-sample-analysis-of-apt-c-27s-recent-attack/

## Content





















The sample analysis of APT-C-27’s recent attack | 360 Total Security Blog









































 















Blog










Back to 360 Home





Latest PostProductsCompany NewsSecurity News 





Latest PostProductsCompany NewsSecurity News 
Download







The sample analysis of APT-C-27’s recent attack
Oct 19, 2018Elley



Tweet



Choose a language
English
Русский
Español
Deutsch

 


Learn more about 360 Total Security
Background
APT-C-27 is a group that has long been engaged in cyber attacks against Arab countries such as Syria. It mainly uses APK, PE, VBS, JS files as attack vectors, involving Android and Windows platforms, using social networks and spear phishing email to spread malicious payloads.
The malicious sample captured by 360 CERT(360 Computer Emergency Readiness Team) is the Office phishing document with the embedded Package object. From the sample type, the attack was suspected to be delivered to the victim by means of a spear phishing email. The United Nations Relief and Works Agency for Palestine Refugees in the Near East (UNRWA) issued a public letter embedding an important form to induce victims to execute Package objects to carry out attack payloads.
Attack analysis
From the sample captured by 360 CERT, the attack started with the Office phishing document containing the Package object. The entire attack chain consists of phishing documents, Dropper scripts, and backdoors.

The bait file shows an official letter issued by UNRWA. After the victim executes the embedded Package object, another Word document <السيرة الذاتية> is displayed. From the language used in the documentation, the attack was mainly targeted at Arabic victims, using fraudulent documents to trick victims into filling in personal details.

The embedded package belongs to the features of Microsoft Office, and its compatibility is very strong. It can be executed stably under all versions of Office. Once the user double clicks on the object, the embedded VBS script will be released and executed.

The script under the Word process is a Dropper, which releases the VBA backdoor and the <السيرة الذاتية> document executed in the next stage. Then, it uses the backdoor script to interact with C2. Unlike the common attack process, there is no PE file in the entire attack chain, and the APT-C-27 group chooses to use the script to communicate directly with C2. We found that this script spreads the classic script backdoor on the network for a long time. 

Sample technical analysis
Analysis of fishing documents
The main technique used in this phishing document is to embed a malicious VBS script in a Word document with confusing information. A letter was issued on behalf of UNRWA to induce victims to trust the source of the document and double-click on the embedded Package icon to perform malicious operations.

According to the properties of the embedded package in the Office document, analyze the files in the \word\embeddings\ directory to get the path of the attacker to insert the object as C:\Users\gorin fulcroum\Desktop\CV.vbs

The author of the bait file is: مستخدم Windows, the last modification time of the document is: 2018-09-19T09:53:00Z, which is the long-term working environment from the comparison of the author name of the document.

Dropper analysis
The Dropper uses Base64 encoded data. There is a certain degree of interference with the detection of software vendors.

After analysing the Dropper script, it is obvious that its main function is to save and execute the sh3r.doc and program.vbs scripts. Its original content is stored in two base64 encoded strings.

Backdoor analysis
The Program.vbs script is a heavily confusing backdoor. Its encoding inserts a large amount of invalid code, invisible special characters, encoded strings, and cluttered encoding to interfere.

After analysing the backdoor script, as mentioned earlier, we found that this is a classic backdoor that has been circulating on the network for a long time. Features include getting system information and uploading, setting up scheduled tasks, downloading files, executing shell commands, deleting files, ending processes, traversing file drivers and processes, and more. The backdoor script execution flow and main functions are as follows:
1. Back up the script to the %APPDATA%\MICROSOFT\ directory.

2. Decode a base64 string and save it as %temp%\R.jpg. Parsing R.jpg in XML format to create a backdoor for backup as a scheduled task WindowsUpda2ta


3. Obtain the basic information such as the disk volume label, computer name, user name, and operating system version, and send it back to the C2 server.


4. Receive and respond to the C2 server command to complete the subsequent attack steps. Received instructions include executing shell commands, updating backdoors, uninstalling, and so on.

Network Basic Analysis
The backdoor program uses IP to communicate with the C2 server. The host IP is 82.137.255.56 and the communication port is 5602. This IP address is an inherent IP asset of the Golden Rat organization and has appeared several times in its attacks. The location of the IP is located in Syria and the ASN is AS29256.


   No domain name has been resolved to this IP address in recent months. Opened 80 and 82 two recognized ports. Port 5602 is not open when a port is scanned for a report.


Data association through the 360netlab graph system:

Summary
   Obviously, this incident is still the network penetration activity initiated by the APT-C-27 group against the Arab countries. From the constructed document content, the author name of the document, and the Arabic part of the code comment section, it is possible to judge that the members of the APT-C-27 group are proficient in Arabic. 
The phishing document forged a letter issued by UNRWA, which not only acquired the computer system for victims’ computer information control victims during the attack, but also forged the forms to allow victims to fill in personal details to better understand the victim’s situation.
Although the final payload of the attack chain uses the backdoor of the VBS script that has been circulated on the network. However, its use of intricate confusing techniques for the script makes the backdoor program not easily detected by the software manufacturer, thus anti-av.
The C2 server used by the event is an intrinsic asset of the the APT-C-27 group. From the use of the IP asset and the current state of the asset, the group may continue to use the IP asset for cyberattacks in the near future.
Learn more about 360 Total Security



Share: 











Related Articles




 


TLauncher Software Security Testing and Evaluation






 


Win11 users beware! Magniber ransomware has been upgraded again, aiming at win11






 


Exclusive in-depth analysis: directly attack the key technical details of Ukraine’s cyber warfare






 


Urgent! Minecraft players are under massive attack










Facebook
Twitter

VK






Free Download
For Windows 10/8.1/8/7/Vista/XP (32,64bit)











Top Articles




3 outside resources to make today’s security services even more secure





Attention! You may have become a susceptible group of “WannaRen” ransomware!





Qihoo 360’s precise analysis of ransomware for September





More than 200,000 MikroTik routers are infected by CryptoMining malware




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














