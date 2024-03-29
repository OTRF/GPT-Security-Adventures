# Reference for threat actor for "Mummy Spider, TA542"

**Title**: The Banking Trojan Emotet: Detailed Analysis | Securelist

**Source**: https://securelist.com/the-banking-trojan-emotet-detailed-analysis/69560/

## Content















The Banking Trojan Emotet: Detailed Analysis | Securelist




































































Solutions for:

Home Products
Small Business 1-50 employees
Medium Business 51-999 employees
Enterprise 1000+ employees
 



















by Kaspersky


CompanyAccount
Get In Touch
Dark mode off
EnglishRussianSpanish













Solutions



Hybrid Cloud SecurityLearn More
Internet of Things & Embedded SecurityLearn More
Threat Management and DefenseLearn More
Industrial CybersecurityLearn More
Fraud PreventionLearn More



Other solutions
Blockchain Security
Kaspersky for Security Operations Center


Industries



National CybersecurityLearn More
Industrial CybersecurityLearn More
Finance Services CybersecurityLearn More
Healthcare CybersecurityLearn More
Transportation CybersecurityLearn More
Retail CybersecurityLearn More



Other Industries
Telecom Cybersecurity
Blockchain Security
View all


Products



KasperskyEndpoint Security for BusinessLearn More
KasperskyEndpoint Detection and Response (EDR)Learn More
KasperskyEDR OptimumLearn More
KasperskyAnti Targeted Attack PlatformLearn More
KasperskyManaged Detection and ResponseLearn More
KasperskySandboxLearn More



Other Products
Kaspersky Security for Mail Server
Kaspersky Security for Internet Gateway
Kaspersky Embedded Systems Security
Kaspersky Hybrid Cloud Security for AWS
Kaspersky Hybrid Cloud Security for Azure
View All


Services



KasperskyCybersecurity ServicesLearn More
KasperskyAdaptive Online TrainingLearn More
KasperskyPremium SupportLearn More
KasperskyThreat IntelligenceLearn More
KasperskyAPT Intelligence ReportingLearn More
KasperskyTargeted Attack DiscoveryLearn More



Other Services
Kaspersky Professional Services
Kaspersky Incident Response
Kaspersky Cybersecurity Training
Kaspersky Incident Communications
Kaspersky Security Awareness
View All


Resource Center

Case Studies
White Papers
Datasheets
Technologies
MITRE ATT&CK

About Us

Transparency
Corporate News
Press Center
Careers
Innovation Hub
Sponsorship
Policy Blog
Contacts

GDPR
 





Subscribe
 Dark mode off
Login


Securelist menu

EnglishRussianSpanish
Existing Customers

Personal

My Kaspersky
Renew your product
Update your product
Customer support

Business

KSOS portal
Kaspersky Business Hub
Technical Support
Knowledge Base
Renew License


Home

Products
Trials&Update
Resource Center

Business

Small Business (1-50 employees)
Medium Business (51-999 employees)
Enterprise (1000+ employees)


Securelist
Threats

Financial threats
Mobile threats
Web threats
Secure environment (IoT)
Vulnerabilities and exploits
Spam and Phishing
Industrial threats

Categories

APT reports
Incidents
Research
Malware reports
Spam and phishing reports
Publications
Kaspersky Security Bulletin

Archive
All Tags
APT Logbook
Webinars
Statistics
Encyclopedia
Threats descriptions
KSB 2021

About Us

Company
Transparency
Corporate News
Press Center
Careers
Sponsorships
Policy Blog
Contacts

Partners

Find a Partner
Partner Program
















Content menu
Close













Subscribe













by Kaspersky

 Dark mode off




ThreatsThreats

APT (Targeted attacks)
Secure environment (IoT)
Mobile threats
Financial threats
Spam and phishing
Industrial threats
Web threats
Vulnerabilities and exploits


CategoriesCategories

APT reports
Malware descriptions
Security Bulletin
Malware reports
Spam and phishing reports
Security technologies
Research
Publications


Other sections

Archive
All tags
Webinars
APT Logbook
Statistics
Encyclopedia
Threats descriptions
KSB 2023


 











 

Publications

The Banking Trojan Emotet: Detailed Analysis 

Publications

09 Apr 2015

  minute read								
















Table of Contents





IntroductionInfectionLoading  the TrojanCommunication  with the command centerCommand  center addressesCommunication  with the C&C when run in a virtual machineData transferredModulesStand  and Deliver!Getting round two-factor authenticationConclusionSome MD5 hashes 






 

Authors



 Alexey Shulmin





Introduction
In the summer of 2014, the company Trend Micro announced the detection of a new threat – the  banking Trojan Emotet.  The description  indicated that the malware could  steal bank account details by intercepting traffic.  We call this modification version 1. 
In the autumn of that year a new version  of Emotet was found.  It caught our attention for the following reasons: 

The developers of this Trojan had begun  to use technology that stole money automatically from victims’ bank accounts – so called “Automatic  Transfer System (ATS)”. 
The Trojan had a modular  structure: it contained its own installation module, a banking module, a spam  bot module, a module for stealing address books from MS Outlook and a module  for organizing DDoS attacks (Nitol DDoS bot).
The creators made a significant  effort to remain unnoticed: they didn’t attack users in the RU zone but targeted the clients of a small number of German and Austrian  banks (other well-known banking Trojans are less discerning in their choice of  target),and the domain name of the ATS server  changed frequently (once or several times a day).

We are going to refer to this  modification as Emotet version 2. The bot contains and transfers the numbers one and seven to the command and control center  (C&C), which suggests that the Trojan’s authors considers this variant to be version  1.7. 
Both versions of the Trojan attacked  clients of German and Austrian banks.
#Trojan #Emotet targeted the clients of a small number of German, Austrian and Swiss banksTweet
We closely monitored Emotet version 2.  In December 2014 it ceased activity and the command servers stopped responding  to infected computers.  We recorded the  last command sent from the command centers on 10/12/2014, at 11:33:43 Moscow time.
However, the thoroughness with which the authors had approached the development  of this Trojan and the high level of automation in its operation, left little doubt that this was not the end of the  story.  And so it turned out – after a  short break in January 2015, Emotet reappeared!   We are calling this modification version 3 (the bot contains and transfers the  numbers one and 16 to the C&C, which we assume  means that the authors consider this variant to be  version 1.16).
In essence, Emotet version 3 is not that different to version 2 – the main differences are designed to  make the Trojan less visible. Of the changes we noted, we would like to highlight the  following:

The Trojan has a new built-in  public RSA key and, although the communication protocols with the command center  are identical for Emotet versions 2 and 3, if the old key is used the bot does  not receive the correct answer from the command center.
The ATS scripts are partially  cleaned of debugging information and comments.
New  targets! Emotet is  now also targeting clients of Swiss banks. 
There has been a slight change in  the technology used to inject code into the address space of  explorer.exe.  Version 2 used a classic model for code injection:  OpenProcess+WriteProcessMemeory+CreateRemoteThread. Version 3 uses only two stages of the previous  model:OpenProcess+WriteProcessMemory;  and the injected code is initiated with the help of modified code of the  ZwClose function in the address space of the explorer.exe process, which is  also achieved using WriteProcessMemory.
Emotet version 3 resists investigation: if the Trojan  detects that it has been started in a virtual machine it functions as usual but  uses a different address list for the command centers.  However, all these addresses are false and are  used only to mislead investigators. 
The Trojan contains very few lines of text:   all lines that could warn investigators are encrypted using RC4 and are  decrypted in allocated memory directly before use and deleted after use.

On the whole, we formed the impression that the  main techniques used in version 3  of the banking Trojan were developed  “in the field” using version 2 as a basis, and with the addition of improved stealth techniques.
Kaspersky Lab products detect all versions of this Trojan as Trojan-Banker.Win32.Emotet.  We also detect the following  modulesof Emotet:

Module for modifying HTTP(S)  traffic – Trojan-Banker.Win32.Emotet. 
Spam module –  Trojan.Win32.Emospam. 
Module for the collection of email  addresses – Trojan.Win32.Emograbber. 
Module for stealing email account  data – Trojan-PSW.Win32.Emostealer.
Module designed for organising  DDoS attacks — Trojan.Win32.ServStart. 

We have seen the last module used with  other malware and assume that it was added to  Emotet by a cryptor.  It is quite  possible that Emotet’s authors are totally unaware of the presence of this  module in their malware.  Whatever the  case may be, the command centers of this  module do not respond and the module has not been updated (its compilation date is 19 October 2014).
Infection
We currently know of  only one method of distribution for the Emotet banking Trojan: distribution of spam mailings that  include malicious attachments or links.
The attached files are usually ZIP archives containing the Emotet  loader.  The files in the archives have  long names, e.g.  rechnung_november_2014_11_0029302375471_03_44_0039938289.exe.  This is done on purpose: a user opening the  archive in a standard Windows panel might not see the extension .exe, as the  end of the file name might not be displayed.   Sometimes there is no attachment and the text in the main body of the email contains a link to a malicious  executable file or archive.
#Emotet banking #Trojan is distributed of spam mailings that include malicious attachments or linksTweet
Examples of emails used to spread Emotet are given below.
Version 2 (link to malware):

Version 2 (attached archive):

Version 3 (link to malware):


The emails we found are almost identical to ones from well-known companies – for example Deutsche Telekom AG and DHL  International GmbH.  Even the images  contained in the messages are loaded from the official servers  telekom.de and dhl.com, respectively.
When the email contains a link to malware, it downloads it from the addresses of  compromised legitimate sites:
hxxp://*******/82nBRaLiv (for version 2)
  or from the addresses
  hxxp://*******/dhl_paket_de_DE and hxxp://*******/dhl_paket_de_DE (for  version 3).
In Emotet version 3, when addresses are contacted with the form hxxp://*/dhl_paket_de_DE, the user receives a ZIP archive of the  following form hxxp://*/dhl_paket_de_DE_26401756290104624513.zip.
The archive contains an exe-file with a  long name (to hide the extension) and a PDF document icon.
Loading  the Trojan
The Trojan file is packed by a cryptor,  the main purpose of which is to avoid detection by anti-virus  programs.  After being started and processed by the cryptor, control is passed to the  main Emotet module – the loader.  This has to embed itself in the system, link  with the command server, download additional modules and then run them. 
Consolidation in the system is fairly standard — Emotet version 2 saves itself in %APPDATA%\Identities  with a random name of eight characters (for example — wlyqvago.exe); adds itself to the autoloader  (HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run) and  then deletes its source file with the help of a launched bat-file that is  created in %APPDATA% with the name “ms[7_random_numbers].bat.
Emotet version 3 saves itself in %APPDATA%\Microsoft\  with a name in the format msdb%x.exe” (for example – C:\Documents and  Settings\Administrator\Application Data\Microsoft\msdbfe1b033.exe); adds itself to the autoloader  (HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run) and then deletes itself with the help of a  launched bat-file (which is created in %APPDATA%\del%x.bat).
After consolidating itself in the system, Emotet obtains a list of the names of  all processes running and calculates a hash from the name of every function,  comparing the resulting value with the hardcoded  0xB316A779 (this hash corresponds to the process  explorer.exe).   In this way, Emotet locates the process into which to inject itself.  Further, the Trojan unpacks its main code and  injects it into the process explorer.exe.
Communication  with the command center
The main module of the Trojan, the  loader, communicates with the C&C using RC4 encryption.
The port used by the loader is hardcoded  into it – 8080. 
Command  center addresses
The IP  addresses of Emotet’s command-and-control servers are hardcoded into the bot.  There are several of these – one of the version 2 samples that we analyzed  included 30 (note that 3 addresses on the list below belong to well-known  legitimate resources): 
hxxp://109.123.78.10
  hxxp://66.54.51.172
  hxxp://108.161.128.103
  hxxp://195.210.29.237
  hxxp://5.35.249.46
  hxxp://5.159.57.195
  hxxp://206.210.70.175
  hxxp://88.80.187.139
  hxxp://188.93.174.136
  hxxp://130.133.3.7
  hxxp://162.144.79.192
  hxxp://79.110.90.207
  hxxp://72.18.204.17
  hxxp://212.129.13.110
  hxxp://66.228.61.248
  hxxp://193.171.152.53
  hxxp://129.187.254.237
  hxxp://178.248.200.118
  hxxp://133.242.19.182
  hxxp://195.154.243.237
  hxxp://80.237.133.77
  hxxp://158.255.238.163
  hxxp://91.198.174.192
  hxxp://46.105.236.18
  hxxp://205.186.139.105
  hxxp://72.10.49.117
  hxxp://133.242.54.221
  hxxp://198.1.66.98
  hxxp://148.251.11.107
  hxxp://213.208.154.110
In the sample of version 3 we investigated there were 19 command  centers:
hxxp://192.163.245.236
  hxxp://88.80.189.50
  hxxp://185.46.55.88
  hxxp://173.255.248.34
  hxxp://104.219.55.50
  hxxp://200.159.128.19
  hxxp://198.23.78.98
  hxxp://70.32.92.133
  hxxp://192.163.253.154
  hxxp://192.138.21.214
  hxxp://106.187.103.213
  hxxp://162.144.80.214
  hxxp://128.199.214.100
  hxxp://69.167.152.111
  hxxp://46.214.107.142
  hxxp://195.154.176.172
  hxxp://106.186.17.24
  hxxp://74.207.247.144
  hxxp://209.250.6.60
Communication  with the C&C when run in a virtual machine
Emotet version 3 contains another list of “command center”  addresses, as given below:
hxxp://142.34.138.90
  hxxp://74.217.254.29
  hxxp://212.48.85.224
  hxxp://167.216.129.13
  hxxp://91.194.151.38
  hxxp://162.42.207.58
  hxxp://104.28.17.67
  hxxp://8.247.6.134
  hxxp://5.9.189.24
  hxxp://78.129.213.41
  hxxp://184.86.225.91
  hxxp://107.189.160.196
  hxxp://88.208.193.123
  hxxp://50.56.135.44
  hxxp://184.106.3.194
  hxxp://185.31.17.144
  hxxp://67.19.105.107
  hxxp://218.185.224.231 
The Trojan tries to contact these  addresses if it detects that it is being run in a virtual machine.  But none of the addresses correspond to the bot’s command centers, and the bot is therefore unsuccessful  in trying to establish contact with them. This is probably done to confuse any  investigators and give them the impression that the Trojan command centers are  dead.  A similar approach was used previously in the high-profile banking Trojan, Citadel.
#Trojan #Emotet tries to contact the wrong addresses of the C&C if it is being run in a virtual machineTweet
The detection of a virtual machine is  organized quite simply — by the names of processes that are usual for various  virtual machines.  The following  algorithm is used to calculate a hash value from the name of every process in the system:

Algorithm  for calculation of a hash value from a process name
The resulting hash value is then  compared with a list of values hardcoded into the Trojan:

Hashes  from the names of processes used for the detection of virtual machines
We derived the names of the processes  for several hashes. For example, hash 0xBCF398B5 corresponds to the  process vboxservice.exe, hash 0x2C967737 to the process vmacthlp.exe, hash  0xE3EBFE44 to the process vmtoolsd.exe, and 0x61F15513 to the process vboxtray.exe.
Data transferred
A request to the command center appears  in the traffic as follows (the example given is from  version 2, but a version 3 request looks the same):

Dialogue  between the Emotet bot and its command center
The URL-path that the bot communicates  with appears as follows: /722ffc5e/355c7a0a/, where 722ffc5e is a number  calculated on the basis of information from the access marker of the user, and   0x355c7a0a = 0x722ffc5e xor 0x47738654 (the value 0x47738654 is  hardcoded into the bot).
The data sent by the bot and the command  center are encrypted using RC4 and the answers received from the command center  are signed with a digital signature.   Probably this is done to make it difficult to seize control over the  botnet: in order for the bot to accept a packet it must be signed and for that  it is necessary to know the secret key.
There is a public RSA key in the body of  the bot. In PEM format for version 2 it  appears as follows:

PEM  representation of the open RSA key coded into the bot in version 2
As noted above, in version 3 the key changed.  In PEM format it looks like this:

PEM  representation of the open RSA key coded into the bot in version 3
A packet sent to the server is made up  as follows: 

A request is generated containing  the identifier of the infected computer, a value presumably indicating the  version of the bot; information about the system (OS  version, service pack version, product type); a hardcoded dword (value in the  investigated sample — seven); control sums for the banker module; and information about the  web-injects.  Information about the  web-injects contains: a page address (with jokers), into which the injection is needed; data  coming before the injected data; data coming after injected data; and injected data.
An SHA1 hash is calculated from  the generated request.
The request is encrypted with a  randomly generated 128 bit RC4 key. 
The generated RC4 key is encrypted  using the public RSA key.
The total packet is the  concatenation of the results obtained at steps 4, 2 and 3.

The request packet can be represented by  the following diagram:

Structure of a request from the bot to  the server
In response the server sends a packet with the  following structure:

Structure  of the server’s answer to the bot
The answer  can contain information about the Emotet web-injects, Emotet modules and links  for loading external modules (for example a spam bot or an updated loader).
Modules
Like most modern banking Trojans, Emotet has a modular structure.  To date we have detected the  following modules:




Name
Description
Method of delivery to infected system


loader
loader
In  spam emails or by downloading via a link from a compromised site (for updates). 


nitol-like-ddos-module
DDoS-bot


mss
Spam  module
Downloaded  from compromised sites by the loader module.


email_accounts_grabber
Email  account grabber, uses Mail PassView – a legitimate program designed for  recovering forgotten passwords and mail accounts
Received  by the loader module in the answer packet from the command center.


banker
Module  for modifying HTTP(S)-traffic
Received  by the loader module in the answer packet from the command center.


outlook_grabber
Outlook  address book grabber
Received  by the loader module in the answer packet from the command center.




Several  modules can work independently  of the loader module, as they don’t need to  import anything from it.
The whole  arrangement of the bot is evidence  of a high level of automation: new email addresses are collected automatically  from the victims’ address books, spam with the  Emotet loader is sent automatically, and money is  transferred automatically from the user.  Operator participation is kept to a minimum.
As an example, here is the report of the  outlook_grabber module sent to the attacker (from Emotet version 2) with a stolen Outlook address book:

A stolen  Outlook address book, transferred to the criminals’ server
One  positive note is that when trying to contact one of the attackers’ servers an answer is obtained  containing “X-Sinkhole: Malware  sinkhole”, meaning that the stolen data will not reach the criminals — this  domain, which is used by Emotet version 2, is no longer controlled by the authors  of the Trojan.
However, for version 3 things are different.  This is how the report of the  email_accounts_grabber module appears for Emotet version 3:

Report  containing data about the user’s email accounts
It is  clear that the server answers “200 OK”. This means that the criminals have successfully received the data.
Stand  and Deliver!
Information  about the data for injection into the page that is received by Emotet after unpacking  appears as follows:

Decrypted  data on the web-injects of Emotet version 2

Decrypted  data in the web-injects of Emotet version 3
The  significant difference in data on injects between the two versions is as  follows: Emotet version 3 is aimed at the clients of Swiss  credit organizations.   To date we have not seen scripts for the automatic stealing of money  from clients’ accounts in these credit organizations but we are certain that such  scripts will be written soon. 
Although  individual fragments of HTML code in the decrypted packet can be read easily,  understanding the rules for use of the web-injects from the deciphered data is  difficult.  Below, in JSON format,  several web-inject rules are given for one target — the site of a German bank  (Emotet version 2).

The  web-inject rules for the site of a German bank (Emotet version 2)
The use of this web-inject leads to the creation of a new  element of type ‘div’, which will have the size of the whole visible page, and  to the addition of a new script in the HTML document.  In the example given the script is loaded  from the address hxxps://*******.eu/birten/luck.php?lnk=js&id=44. 
And an analogous view of several inject  rules for a new target — the site of a large Austrian bank (Emotet version 3).

The  web-inject rules for the site of an Austrian bank (Emotet version 3)
It is clear that the configuration file  with the web-injects has a classic structure,  using fields conventionally called   data_before, data_after and data_inject.
It should be noted that the address of  the host on which the file luck.php (for version 2) and a_00.php (for version 3) is located is changed frequently.  The rest of the address of the script is  constant. 
If the investigator tries the script  directly, only an error message is  received.  However, in a real attack when  the line

is added  to the real bank page, the script loads successfully.
This  happens because the criminals’ server checks the “Referer”  field of the header of the HTTP request and sends the script only if the  request came from a page of one of the banks attacked by Emotet.
Having  supplied the necessary Referrer one can easily obtain the script code. 
At  Kaspersky Lab we obtained scripts designed for injection into the pages of the  attacked banks.
Table 1.  Targets of Emotet version 2, types of  attacks and the identification numbers of scripts  loaded for carrying out these attacks.

Table 2.  Targets of Emotet version 3, types of attacks and the identification numbers of scripts loaded  for carrying out these attacks.

In one of  the scripts of Emotet version 2 that was used to attack a German bank the  comments contain the following line:

Artifact  from the script for an attack on a German bank (Emotet version 2)
Clearly the script developers speak Russian.
Getting round two-factor authentication
The main  purpose of the scripts looked at above is to carry out the illicit transfer of  money from the user’s account.  However  the bot cannot independently get round the system of two-factor authentication (Chip TAN or SMS  TAN), it needs the user’s help.  To  mislead the potential victim, social engineering techniques are  used: the message injected into the webpage using the script informs the user  that the site is introducing a new security system and normal operations cannot  be continued until the user has tested it in the demo-regime.

False  message about new security system
This is  followed by a request to enter real data  from the Chip TAN or SMS TAN to carry out a “test transfer”:

And  finally – congratulations that the task has been completed successfully:

In fact, instead of a test transfer the malicious script  carries out a real transfer of money from the victim’s account to the account  of a nominated person — the so-called “drop”, and the user themselves confirms this transfer using the Chip  TAN or SMS TAN.
Details of  the accounts for the transfer of the stolen money are not initially indicated  in the script, but are received from the command  server of the criminals using a special request.  In reply the command  server returns a line with information about the “drop” for each specific  transaction.  In the comments in one  script we found the following line: 

Clearly  the criminals tested this script with a transfer of 1500.9 EUR to a test account.
In addition, this script contained the following  information about the drop:

In the  corresponding script in Emotet version 3, designed to attack the same bank, we also found information on the drop,  but this time another one:

Let’s  compare the fields JSON __DropParam and the fields in the legitimate form from  a demo-access to the online system of the attacked bank.

Online banking  form for transfer of money within Germany or in the SEPA zone
Table 3. Relationship between the drop  data and the fields in the form for transfer of money and explanations of these  fields




Name of fields in the  __DropParam JSON
Name of corresponding field in the form
Translation
Field contents


name
Empfängername
Name of  recipient
Real  name of drop who will receive the stolen money


ibanorkonto
IBAN/Konto-Nr.
International  bank account number/ account number 
Account  number, international or local, to which money will be transferred


bicorblz
BIC/BLZ 
BIC or  BLZ code
International  bank identification code or identification code used by German and Austrian  banks (Bankleitzahl)


description
Verwendungszweck
Purpose
Purpose  of payment


amount
Betrag
Amount
Transferred  amount




The JSON  __DropParam fields correspond to the fields in the form.
In this  way the bot receives all the necessary information about the  drop from its server and draws up a transfer to it, and the misled user confirms the  transfer using the Chip TAN or SMS TAN and waves goodbye to their money.  
Conclusion
The Emotet  Trojan is a highly automated and developing, territorially-targeted bank threat. Its small size, the dispersal methods used  and the modular architecture, all make Emotet a very effective  weapon for the cyber-criminal.
The #Emotet #Trojan is a highly automated and developing, territorially-targeted bank threatTweet
However  this banking Trojan doesn’t incorporate conceptually new technology and so the  use of a modern anti-virus program can provide an effective defense against the threat. 
Furthermore,  the Trojan cannot function effectively without the participation of the user —  the Emotet creators have actively used social engineering techniques to achieve  their criminal ends.
And so the  alertness and technical awareness of the user, together with the use of a  modern anti-virus program can provide reliable protection against not only  Emotet but other` new banking threats working in a similar  way. 
Some MD5 hashes
Emotet version 2:
  7c401bde8cafc5b745b9f65effbd588f
  34c10ae0b87e3202fea252e25746c32d
  9ab7b38da6eee714680adda3fdb08eb6
  ae5fa7fa02e7a29e1b54f407b33108e7
  1d4d5a1a66572955ad9e01bee0203c99
  cdb4be5d62e049b6314058a8a27e975d
  642a9becd99538738d6e0a7ebfbf2ef6
  aca8bdbd8e79201892f8b46a3005744b
  9b011c8f47d228d12160ca7cd6ca9c1f
  6358fae78681a21dd26f63e8ac6148cc
  ac49e85de3fced88e3e4ef78af173b37
  c0f8b2e3f1989b93f749d8486ce6f609
  1561359c46a2df408f9860b162e7e13b
  a8ca1089d442543933456931240e6d45
Emotet  version 3:
  177ae9a7fc02130009762858ad182678
  1a6fe1312339e26eb5f7444b89275ebf
  257e82d6c0991d8bd2d6c8eee4c672c7
  3855724146ff9cf8b9bbda26b828ff05
  3bac5797afd28ac715605fa9e7306333
  3d28b10bcf3999a1b317102109644bf1
  4e2eb67aa36bd3da832e802cd5bdf8bc
  4f81a713114c4180aeac8a6b082cee4d
  52f05ee28bcfec95577d154c62d40100
  772559c590cff62587c08a4a766744a7
  806489b327e0f016fb1d509ae984f760
  876a6a5252e0fc5c81cc852d5b167f2b
  94fa5551d26c60a3ce9a10310c765a89
  A5a86d5275fa2ccf8a55233959bc0274
  b43afd499eb90cee778c22969f656cd2
  b93a6ee991a9097dd8992efcacb3b2f7
  ddd7cdbc60bd0cdf4c6d41329b43b4ce
  e01954ac6d0009790c66b943e911063e
  e49c549b95dbd8ebc0930ad3f147a4b9
  ea804a986c02d734ad38ed0cb4d157a7
The author  would like to express his thanks to Vladimir Kuskov, Oleg Kupreev and Yury  Namestnikov for their assistance in the preparation of this article.






Cybercrime
Emotet
Trojan Banker



Authors



 Alexey Shulmin





The Banking Trojan Emotet: Detailed Analysis 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







J. 


							Posted on							April 10, 2015. 5:42 pm 



to remind ourselves: emotet is sometimes called geodo and is related to the bugat-feodo-geodo-cridex-dridex family, but seems to be generally focussed on areas around Germany.
Reply 








John Patterson 


							Posted on							April 16, 2015. 9:48 pm 



I wonder if computers are worth it ! I was seeing what things were on this, now can’t even log on,
Reply 








Gargeya 


							Posted on							April 22, 2015. 10:40 am 



I always detailed analysis of malware. I was just thinking how would it get around 2 factor auth & there is the answer.. Human stupidity. But most of the banks will have to add new user as beneficiary to transfer funds and it will take 4-16 hours to add new beneficiary. I wonder how would it get worked then.
Reply 








John 


							Posted on							September 13, 2018. 12:56 am 



I just saw a new version of this Trojan in the UK – the CnC servers appear to be in Spain, Italy & Belgium.
Reply 



















Table of Contents





IntroductionInfectionLoading  the TrojanCommunication  with the command centerCommand  center addressesCommunication  with the C&C when run in a virtual machineData transferredModulesStand  and Deliver!Getting round two-factor authenticationConclusionSome MD5 hashes 





GReAT webinars






																		13 May 2021, 1:00pm								
GReAT Ideas. Balalaika Edition 





Boris Larin



Denis Legezo










																		26 Feb 2021, 12:00pm								
GReAT Ideas. Green Tea Edition 





John Hultquist



Brian Bartholomew



Suguru Ishimaru



Vitaly Kamluk



Seongsu Park



Yusuke Niwa



Motohiko Sato










																		17 Jun 2020, 1:00pm								
GReAT Ideas. Powered by SAS: malware attribution and next-gen IoT honeypots 





Marco Preuss



Denis Legezo



Costin Raiu



Kurt Baumgartner



Dan Demeter



Yaroslav Shmelev










																		26 Aug 2020, 2:00pm								
GReAT Ideas. Powered by SAS: threat actors advance on new fronts 





Ivan Kwiatkowski



Maher Yamout



Noushin Shabab



Pierre Delcher



Félix Aime



Giampaolo Dedola



Santiago Pontiroli










																		22 Jul 2020, 2:00pm								
GReAT Ideas. Powered by SAS: threat hunting and new techniques 





Dmitry Bestuzhev



Costin Raiu



Pierre Delcher



Brian Bartholomew



Boris Larin



Ariel Jungheit



Fabio Assolini












From the same authors




 


The Slingshot APT FAQ 






 


Steganography in contemporary cyberattacks 






 


Use of DNS Tunneling for C&C Communications 






 


Inside the Gootkit C&C server 






 


Lurk Banker Trojan: Exclusively for Russia 









Subscribe to our weekly e-mails
The hottest research right in your inbox




Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ








In the same category




 


The dark side of Black Friday: decoding cyberthreats around the year’s biggest shopping season 






 


Gaming-related cyberthreats in 2023: Minecrafters targeted the most 






 


Overview of IoT threats in 2023 






 


How cybercrime is impacting SMBs in 2023 






 


New ransomware trends in 2023 






 















Latest Posts




 



Malware descriptions

Cracked software beats gold: new macOS backdoor stealing cryptowallets 





Sergey Puzan










 



Kaspersky Security Bulletin

Dark web threats and dark market predictions for 2024 





Sergey Lozhkin



Anna Pavlovskaya



Kaspersky Security Services










 



Research

A lightweight method to detect potential iOS malware 





Maher Yamout










 



Research

Operation Triangulation: The last (hardware) mystery 





Boris Larin












Latest Webinars





 




Technologies and services



												11 Dec 2023, 4:00pm					
60 min

The Future of AI in cybersecurity: what to expect in 2024






Vladimir Dashchenko



Victor Sergeev



Vladislav Tushkanov



Dennis Kipker











 




Threat intelligence and IR



												30 Nov 2023, 4:00pm					
70 min

Responding to a data breach: a step-by-step guide






Anna Pavlovskaya











 




Cyberthreat talks



												14 Nov 2023, 4:00pm					
60 min

2024 Advanced persistent threat predictions






Igor Kuznetsov



David Emm



Marc Rivero



Dan Demeter



Sherif Magdy











 




Cyberthreat talks



												09 Nov 2023, 5:00pm					
60 min

Overview of modern car compromise techniques and methods of protection






Alexander Kozlov



Sergey Anufrienko












Reports







HrServ – Previously unknown web shell used in APT attack 

In this report Kaspersky researchers provide an analysis of the previously unknown HrServ web shell, which exhibits both APT and crimeware features and has likely been active since 2021.








Modern Asian APT groups’ tactics, techniques and procedures (TTPs) 

Asian APT groups target various organizations from a multitude of regions and industries. We created this report to provide the cybersecurity community with the best-prepared intelligence data to effectively counteract Asian APT groups.








A cascade of compromise: unveiling Lazarus’ new campaign 

We unveil a Lazarus campaign exploiting security company products and examine its intricate connections with other campaigns








How to catch a wild triangle 

How Kaspersky researchers obtained all stages of the Operation Triangulation campaign targeting iPhones and iPads, including zero-day exploits, validators, TriangleDB implant and additional modules.








 









Subscribe to our weekly e-mails
The hottest research right in your inbox





Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe











Δ








 











ThreatsThreats

APT (Targeted attacks)
Secure environment (IoT)
Mobile threats
Financial threats
Spam and phishing
Industrial threats
Web threats
Vulnerabilities and exploits


CategoriesCategories

APT reports
Malware descriptions
Security Bulletin
Malware reports
Spam and phishing reports
Security technologies
Research
Publications


Other sections

Archive
All tags
Webinars
APT Logbook
Statistics
Encyclopedia
Threats descriptions
KSB 2023


 









© 2024 AO Kaspersky Lab. All Rights Reserved.
Registered trademarks and service marks are the property of their respective owners.



Privacy Policy
License Agreement
Cookies












Subscribe to our weekly e-mails
The hottest research right in your inbox



Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ



























