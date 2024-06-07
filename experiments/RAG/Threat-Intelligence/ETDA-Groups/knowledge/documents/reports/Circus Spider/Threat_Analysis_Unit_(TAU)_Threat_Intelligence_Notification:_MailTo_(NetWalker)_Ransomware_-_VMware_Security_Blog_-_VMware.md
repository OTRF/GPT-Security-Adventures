# Reference for threat actor for "Circus Spider"

**Title**: Threat Analysis Unit (TAU) Threat Intelligence Notification: MailTo (NetWalker) Ransomware - VMware Security Blog - VMware

**Source**: https://www.carbonblack.com/blog/threat-analysis-unit-tau-threat-intelligence-notification-mailto-netwalker-ransomware/

## Content












Threat Analysis Unit (TAU) Threat Intelligence Notification: MailTo (NetWalker) Ransomware - VMware Security Blog - VMware































































Menu


VMware Security Blog





Search




Search
 







VMware Blogs
Communities
Tech Zone




RSS







 





Featured
CategoriesToggle submenu

Announcements
Executive Viewpoint
Multi-Cloud Security
Modern Apps Security
Workload Security
Endpoint Security
Network Security
Threat Analysis Unit
VMware Security Response Center


VMware Security
Get A Demo
 







RSS




























Announcements
Why CISOs Should Invest More Inside Their Infrastructure


Tom Gillis

June 2, 2022
5 min read
 












Threat Analysis Unit
Serpent - The Backdoor that Hides in Plain Sight


Threat Analysis Unit

April 25, 2022
11 min read
 












Executive Viewpoint
How Not to Build a SOC


Martin Holzworth

April 18, 2022
14 min read
 












Executive Viewpoint
Podcast: Discussing the latest security threats and threat actors - Tom Kellermann (Virtually Speaking)


Editorial Staff

April 13, 2022
1 min read
 






















Threat Analysis Unit
Threat Analysis Unit (TAU) Threat Intelligence Notification: MailTo (NetWalker) Ransomware

February 7, 2020
12 min read
 

 









Share on:



Share on Twitter




Share on LinkedIn




Share on Facebook




Share on Reddit




Email this post



Copy Link

 



MailTo is a ransomware variant that has recently been reported to have been part of a targeted attack against Toll Group, an Australian freight and logistics company. This ransomware makes no attempt to remain stealthy, and quickly encrypts the user’s data as soon as the ransomware is launched. Once the encryption phase completes, the encrypted files are renamed to contain the word “mailto”, which is where the name originated from. The Australian Signals Directorate’s Australian Cyber Security Centre (ACSC) released an alert advisory for this ransomware. This ransomware also masquerades as a legitimate software application known as “Sticky Password”, which was created by formed executives of trusted AV company AVG. A sample of the ransom note is shown below.


Behavioral Summary
The TTPs for this particular sample discussed in this report are displayed within VMware Carbon Black Endpoint Standard as shown below.


Details
When the ransomware is first executed, a registry key is created under HKLM\Software\<6-digit-ID>. An example is shown below.


During execution, the ransomware makes an API call to AdjustTokenPrivileges in order to assign SeDebugPrivilege and SeImpersonatePrivilege to its own process. The ransomware immediately starts to encrypt the files on the victim’s local drive by using the Windows system calls NtQueryInformationFile and NtSetInformationFile. A ransom note is created using {ID}-Readme.txt (e.g. 8066A-Readme.txt) and is automatically opened using Notepad once the encryption completes. The same ID is used when a file is encrypted, and the email address used in the ransom note is appended to the encrypted file along with the {ID} used for the ransom note, for example: slides.pptx.mailto[sevenoneone@cock.li].8066A. The email used in the filename is the first email address shown in the ransom note. Once complete, the command C:\Windows\system32\vssadmin.exe delete shadows /all /quiet is executed to silently delete the volume shadow copies stored on the victim’s machine, making it impossible for the user to restore their system to its original state.
Next a batch file is temporarily written to the users %TEMP% directory. The file will be randomly named, for example BC7B.tmp.bat.This batch file is responsible for opening up two taskkill.exe processes and executing taskkill /F /im “<name-of-ransomware>.exe”. This forces (/F) the ransomware to kill its own process by specifying its own process name (/im).
The ransomware uses self-injection in order to hide part of the ransomware configuration by embedding the configuration into the resources section of the PE file. As the ransomware performs this unpacking in-memory, manual debugging of the sample is required in order to locate the unpacking stub. After further debugging, we come across a completely new PE file as shown by the MZ header. 


Dumping the memory region to a new PE file and loading it into IDA, we can get an idea of some of the configuration used by the ransomware. A snippet of part of the function is shown below. 


Above are some of the configuration options contained in the binary. For example, “crmask” contains the “.mailto[email].{ID}”, “mail” contains the email addresses shown in the ransom note, and “lend” contains the base64 encoded ransom note. 
The process activity from VMware Carbon Black Cloud Enterprise EDR is shown below.


To learn more about how to defend against this attack, click here.
To learn more about further ransomware behavior, detection and protection capabilities within the VMware Carbon Black platform against Zeppelin ransomware, you may refer to the following blog post:
TAU-TIN – Ransomware Threats
Remediation:
MITRE ATT&CK TIDs




TID


Tactic


Description




T1083


Discovery


File and Directory Discovery




T1119


Collection


Automated Collection




T1081


Credential Access


Credentials in Files




T1005


Collection


Data from Local System




T1486


Impact


Data Encrypted for Impact




Indicators of Compromise (IOCs)




Indicator


Type


Context




416556c9f085ae56e13f32d7c8c99f03efc6974b2897070f46ef5f9736443e8e


SHA256


MailTo Ransomware




d60d91c24570770af42816602ac19c97


MD5


MailTo Ransomware




eeba4f8b5ca7fd0e9bf27332d8d957a4523c79858ac4f0629880a619aa208a08


SHA256


MailTo Ransomware




ae2f1633bfdf059334757a67cdfa3fb8


MD5


MailTo Ransomware




df46c6da5eb78f41b1ae65077b05fd0bc03fba9372cdb8d1f09b05f2fa990dfe


SHA256


MailTo Ransomware




4a6202cd8ff1fd4d1fed5726b09da630


MD5


MailTo Ransomware




40e1a3fa5f081cc63f88760c50631c27f611bed899e4b46e2c28dd9a78b9b3d5


SHA256


MailTo Ransomware




391f23602d353219ba17703fa3b86a01


MD5


MailTo Ransomware




af5e73121d31a15c64d9cb03ef13a0b5cad74caaef9366f62173a63ad5356320


SHA256


MailTo Ransomware




d4173a6c727b0d77cf01fbb5819a9976


MD5


MailTo Ransomware




c5f7e0e9793beaf3ceb5af40f02446ca055aa1ead41838ed6aab67e233ef0c56


SHA256


MailTo Ransomware




7208ce1fe6d9b468f044a625f4ad9633


MD5


MailTo Ransomware




b4d3af805a9f2b73d893766982317eb215bd3887669131cb8ab8f7bf978d02cc


SHA256


MailTo Ransomware




38bc79fd79ba8b0add94dfa30d717af4


MD5


MailTo Ransomware




b372eac506e8c86009608552c0738884545a37877a150260f42ac23a5ec3e966


SHA256


MailTo Ransomware




4bea06dcd8c6edbb045502aa3749888a


MD5


MailTo Ransomware




5138380ef6aed6cd4c287997a15e58eab8f20fac0f23684ee34d1316867f190e


SHA256


MailTo Ransomware




1df515b51e3d3e6301327497e02432d3


MD5


MailTo Ransomware




46ab670dc5c8205646480299f93e7eb729f46a2cbe35bd6bebdfdccf2abb76b8


SHA256


MailTo Ransomware




b9f4fd9bb861a1f090ca8089e5f2069d


MD5


MailTo Ransomware




e4b995dd1f4a2f797e047676ef5f935fad3e60baa543b9ae5276589ead52317a


SHA256


MailTo Ransomware




032fba3f179706e74c584e95bb8ce2f7


MD5


MailTo Ransomware




3ae36b88d84b327f1cc3e7cb92f76d991b5db0776c7161079ef7bcf9e6c6a61b


SHA256


MailTo Ransomware




c84f7f1523452ac7252a7793ac7db4b1


MD5


MailTo Ransomware




0b62dc536d38af7cedce21f74cb7d6c9ae6378faf9ad8fc6ac1d55c5ba44c0b8


SHA256


MailTo Ransomware




c84a00b0228722cc560ee6385e194d54


MD5


MailTo Ransomware




c02935e80c8be5b8b758224b41b9c2c9507c0d344572adec45398fa02ac1b989


SHA256


MailTo Ransomware




9bf5cca0ee633b17e3be7ac5dc53bfc5


MD5


MailTo Ransomware




97d71faa77f245498f46624e34e95cdc30216f41d1e38c068b0ae595cb25df41


SHA256


MailTo Ransomware




7875d19f9d1dd8a623eb19aab9f06025


MD5


MailTo Ransomware




41d45132a28b370192167a696d5636e07eb9e552857141985b9d24b091e6a4ab


SHA256


MailTo Ransomware




f69240d52d11a41c040ad9d9365968bf


MD5


MailTo Ransomware




1a3a80e5724a3ad68ff4cd11cfb6360a6c1d2f650349dc3148f37ada4de5b530


SHA256


MailTo Ransomware




da88c6a02ccd4d00ce32408e32d8f487


MD5


MailTo Ransomware




0d0a5a1c0e938f5ff8b017bcd8804b52a00f275890742b8a2622576636c0f2b7


SHA256


MailTo Ransomware




1d60d1713af6281359baefe1f50532bb


MD5


MailTo Ransomware




06b8638fdd478672cfe140221233cacfae6d2890446a5c57c8b1317a27d2a036


SHA256


MailTo Ransomware




9aa3089af134627ef48b178db606268a


MD5


MailTo Ransomware




b8690ef15f4af6c731a46a1b8e0fbeeb4d44548fe445628fc87204ff335e0691


SHA256


MailTo Ransomware




4bdb2f712e8a4fd02a89b469978fd847


MD5


MailTo Ransomware




b25fd6a7782582a1c7e9248793316b2ed459c5629ff9f769065b4ddbfb610856


SHA256


MailTo Ransomware




e47b4be4a1f5c1566f713daee22a2326


MD5


MailTo Ransomware




5d44e240fdd9cc08ae35120775e361d009c160f15c3a8a23e6b7a133483a3f5e


SHA256


MailTo Ransomware




9aac488ed45c08c1de7a17ea918f9dc5


MD5


MailTo Ransomware




3f3130d2660e41b6b36a5e98bcd1b2b4e0b7ff017856b15269aa9d60fb414f47


SHA256


MailTo Ransomware




51e6d4390110743b37192817423de8f8


MD5


MailTo Ransomware




f735aaa68bca015b9ecc31dc24271fc0dc18e28fd869dfa072339951c5d83527


SHA256


MailTo Ransomware




ac53cd84bb08e6219c85781c77e3f896


MD5


MailTo Ransomware




6d032ea56a49235a186bc7f8971fa6111cad902f3cd7ce804f1af2b9ad147dde


SHA256


MailTo Ransomware




409287548dc7a2a97ab3163fb6ff8354


MD5


MailTo Ransomware




  









Related Articles












Misc
NetSupport RAT: The RAT King Returns


Alan Ngo,                         Abe Schneider,                         Fae Carlisle 
November 20, 2023
18 min read
 












Misc
Jupyter Rising: An Update on Jupyter Infostealer


Swee Lai Lee,                         Bria Beathley,                         Abe Schneider,                         Alan N  ...
                    Swee Lai Lee, Bria Beathley, Abe Schneider, Alan Ngo, Sean McKnight


November 6, 2023
18 min read
 












Misc
Hunting Vulnerable Kernel Drivers


Takahiro Haruyama

October 31, 2023
34 min read
 













×


















 Cookie Settings






