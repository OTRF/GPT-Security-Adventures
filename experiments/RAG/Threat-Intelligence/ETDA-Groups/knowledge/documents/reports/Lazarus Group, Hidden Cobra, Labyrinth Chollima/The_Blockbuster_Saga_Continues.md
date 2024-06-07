# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: The Blockbuster Saga Continues

**Source**: https://unit42.paloaltonetworks.com/unit42-blockbuster-saga-continues/

## Content
























The Blockbuster Saga Continues






























































 



































Menu






Tools
ATOMs
Security Consulting
About Us
Under Attack?
 












The Blockbuster Saga Continues


45,727
 people reacted

8
  3  min. read



Share 


















 







          By Anthony Kasza 
August 14, 2017 at 5:00 AM
Category: Malware, Unit 42
Tags: AutoFocus, Blockbuster, Korea, Lazarus Group, spearphishing



 



 
Unit 42 researchers at Palo Alto Networks have discovered new attack activity targeting individuals involved with United States defense contractors. Through analysis of malicious code, files, and infrastructure it is clear the group behind this campaign is either directly responsible for or has cooperated with the group which conducted Operation Blockbuster Sequel and, ultimately, Operation Blockbuster (originally outlined  by researchers from Novetta). The threat actors are reusing tools, techniques, and procedures which overlap throughout these operations with little variance. Attacks originating from this threat group have not ceased since our previous report (from April of 2017) and have continued through July of 2017.
New Activity
Recently, we’ve identified weaponized Microsoft Office Document files which use the same malicious macros as attacks from earlier this year. Based on the contents of these latest decoy documents which are displayed to a victim after opening the weaponized document the attackers have switched targets from Korean language speakers to English language speakers. Most notably, decoy document themes now include job role descriptions and internal policies from US defense contractors.
The following image shows the content of one of the recent decoy documents (de2d458c8e4befcd478a0010789d80997793790b18a347d10a595d6e87d91f34). It is a job description at a defense contractor.

The following images also shows the contents of a recent decoy document (062aadf3eb69686f4881860d88ce472e6b1c07e1f586d840dd2ee1f7b76cabe7). It contains an exact copy of a publicly available job description, including typos, at a US defense contractor.

The weaponized documents have been hosted on systems which we believe have likely been compromised and repurposed. Two of the URL paths used to host the weaponized documents on the compromised systems are exact matches (event/careers/jobs/description/docs). The payloads delivered by the weaponized documents are extremely similar to the payloads delivered by weaponized documents detailed in our April 2017 report on the threat group's activity.
For a more comprehensive understanding of the relationships between samples and infrastructure used in the recent activity see the following network graph.

The document metadata Author "ISkyISea" is used across multiple weaponized document files. IPv4 addresses (210.202.40[.]35) hosting the weaponized documents have also been hardcoded as command and control servers for previous samples (16c3a7f143e831dd0481d2d57aae885090e22ec55cc8282009f641755d423fcd).
Ties to Blockbuster
The source code used in the macros embedded in the weaponized documents described above was also detailed in a previous report where it was included in testing documents uploaded to VirusTotal. This reuse of macro source code, XOR keys used within the macro to decode implant payloads, and the functional overlap in the payloads the macros write to disk demonstrates the continued use of this tool set by this threat group. The use of an automated tool to build the weaponized documents would explain the common but not consistent reuse of metadata, payloads, and XOR keys within the documents.
Other similarities between the previously reported activity and this new activity can be seen within the PE payloads written to disk by the malicious documents. The payloads function similarly to other implants associated with this threat group. The use of a fake TLS communications protocol, encoded strings within samples, filenames and contents of batch files embedded within implants, as well implants beaconing directly to IPv4 addresses (and not resolving domains for command and control) are all known techniques associated with the threat group. These tactics have changed very little since the original Operation Blockbuster.
In addition to tool reuse, infrastructure overlaps also exist. URLs used for hosting the malicious documents and IPv4 addresses used for command and control overlap with infrastructure previously used by the group.
Final Thoughts
The techniques and tactics the group uses have changed little in recent attacks. Tool and infrastructure overlaps with previous campaigns are apparent. Given that the threat actors have continued operations despite their discovery and public exposure it is likely they will continue to operate and launch targeted campaigns.
Palo Alto Networks researchers will continue to monitor this group’s activities and stay abreast to additional attacks using this tool set.

The malicious files describe in this report are flagged as malicious by WildFire and in Threat Prevention.
AutoFocus users can learn more about the threat group and their indicators by examining the BlockBuster_Sequel tag.

Indicators of Compromise
SHA256 
4d4465bd9a57c7a3c0b80fa3282697554a1419794afa36e544a4ae06d60c1615
f390ef86a4ad92dde125c983e6470f08344b9eaa14c17a1e6c4bb7ebfa7c4ec9
acfae7e2fdda02e81b3e03f8c30741744d629cd672db424027f7caa59c975897
7429a6b6e8518a1ec1d1c37a8786359885f2fd4abde560adaef331ca9deaeefd
e09224a24a14a08c6fcb79b00b4a7b3097c84f805f5f2adefe2f7d04d7b4a8ee
062aadf3eb69686f4881860d88ce472e6b1c07e1f586d840dd2ee1f7b76cabe7
c63a415d23fc4ab10ad3acfdd47d42b5c7444604485ab45147277cca82fffb34
16c3a7f143e831dd0481d2d57aae885090e22ec55cc8282009f641755d423fcd
de2d458c8e4befcd478a0010789d80997793790b18a347d10a595d6e87d91f34
2f133525f76ab0ebb0b370601673361253074c337f0b0895d0f0cb5bc261cfcb
e83a08bcb4353bfd6edcdedbc9ead9ab179a620e15155b60d18153bed9892f38
6f673981892701d42159489c1b2614c098a04e4674b23e1cd0fd8911766e71a0
ad075279d2ee6958105889d852e0d7f4266f746cb0078ac1b362f05a45b5828d
1288e105c83a6f4bbad8471a9b5bedafeea684a8d8b73a1a7518137d446c2e1e
IPv4
104.192.193[.]149
176.35.250[.]93
213.152.51[.]169
108.222.149[.]173
197.246.6[.]83
118.140.97[.]6
210.202.40[.]35
59.90.93[.]97
107.6.12[.]135
URLs
http://210.202.40[.]35/CKRQST/event/careers/jobs/description/docs/NGC1398.doc
http://210.202.40[.]35/CKRQST/Company/HR/Position/lm/L1915.doc
http://104.192.193[.]149/Event/careers/jobs/description/docs/LJC077.doc
http://lansingturbo[.]org/docs/WebDAV.exe

Get updates from  Palo Alto Networks!
Sign up to receive the latest news, cyber threat intelligence and research from us














Please enter your email address!







Please mark, I'm not a robot!



By submitting this form, you agree to our Terms of Use and acknowledge our Privacy Statement.




















Popular ResourcesResource Center
Blog
Communities
Tech Docs
Unit 42
Sitemap
Legal NoticesPrivacy
Terms of Use
Documents
AccountManage Subscriptions
 
Report a Vulnerability
 



© 2024 Palo Alto Networks, Inc. All rights reserved.























