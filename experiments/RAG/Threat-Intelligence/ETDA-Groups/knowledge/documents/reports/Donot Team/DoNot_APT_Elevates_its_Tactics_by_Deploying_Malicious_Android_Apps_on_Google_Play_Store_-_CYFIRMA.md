# Reference for threat actor for "Donot Team"

**Title**: DoNot APT Elevates its Tactics by Deploying Malicious Android Apps on Google Play Store - CYFIRMA

**Source**: https://www.cyfirma.com/outofband/donot-apt-elevates-its-tactics-by-deploying-malicious-android-apps-on-google-play-store/

## Content















DoNot APT Elevates its Tactics by Deploying Malicious Android Apps on Google Play Store - CYFIRMA




































































































CompanySolutionsProductsProductsDeCYFIRThreat Visibility and Intelligence DeTCTDigital Risk DiscoveryDeFNCECyber Defence Mobile AppPartnersPartnersChannel PartnersTechnology PartnersResourcesResourcesResearchBlogsNewsroomDatasheetsWhitepapersCase StudiesGet StartedContact Sales 










EN

















DoNot APT Elevates its Tactics by Deploying Malicious Android Apps on Google Play Store 








Published On : 2023-06-16

Share :  







EXECUTIVE SUMMARY
The team at CYFIRMA recently obtained suspicious Android apps hosted on the Google Play Store under the account “SecurITY Industry”. Further technical analysis revealed that the app has malware characteristics and belongs to the notorious Advanced Persistent Threat Group; “DoNot”, which recently targeted individuals in the Kashmir region. In a recent observation, we found the threat actor is using Android payload against individuals in the Pakistan region, however, it is still unknown what drives them to conduct cyber strikes in the South Asian region. Technical analysis indicates that the motive behind the attack is to gather information via the stager payload and use the gathered information for the second-stage attack, using malware with more destructive features.

INTRODUCTION
The team at CYFIRMA obtained Android Apps deployed on Google Play Store that were used against individuals in the Pakistan region. The apps were stationed under an account named “SecurITY Industry” on Google Play Store. A total of three Android apps were hosted with the name Device Basic Plus, nSure Chat, and iKHfaa VPN, with two of them having malicious characteristics, that are nSure Chat and iKHfaa VPN. The threat actor used cleaned and innocent Android Libraries and made them fetch contacts and the location of the compromised victim. iKHfaa VPN copied its code from a genuine VPN service provider and injected additional libraries to silently perform malicious activity. Normally, VPN apps don’t use location and contact permission to make a VPN app work. These are the least required permissions app for VPN apps to perform their job. All these suspicious findings made us dig more, and after thorough technical analysis, we found the perpetrator to be DoNot. Further technical analysis reveals the tactics employed by the threat actor to deploy the Android payload on Google Play Store to target victims in the South Asian Region.
TECHNICAL ANALYSIS
Process Overview
After installing the iKHfaa VPN, a message asks the user to turn on the location permission.

The about us page also reflects poor modification of the app as the about us content displays the actual name of the app.

Included is a screenshot after opening nSure Chat app after installation.

On skipping the Chat page, the app asks the user to grant contact permission.

After skipping the signup/sign up page shows that lets the user login and sign up into the chatting app. 


CODE REVIEW
We have decompiled apps and did thorough code analysis to reveal the threat actor performing a malicious activity with limited permission. iKHfaa VPN had lines of codes similar to the genuine Liberty VPN app, and the threat actor made modifications by injecting legitimate Android libraries to make the app act maliciously, and fetch contacts and the precise location of victims. The RoomDB and Retrofit Libraries were added silently to store data and fetch the contacts and the precise location to the web-based command-and-control server, which also acts as the official website of the Apps.
The snippet below is from the Android manifest file of iKHfaa VPN, obtained after decompiling the app, which reveals permissions that the app is accessing after installation. (Please note that the permissions used by iKHfaa VPN are the same as the permissions used by nSure Chat.)

The below table covers dangerous permissions with descriptions that apps take for malicious activity.


Sr.no
Permissions
Descriptions


1.
ACESS_FINE_LOCATION
Allows the threat actor to fetch precise locations and track the live movement of mobile phones. 


2.
READ_CONTACTS
This permission allows the threat actor to read and fetch contacts.


The snippet below is from the module of iKHfaa VPN that gains access to the precise location of the compromised victim if its GPS is turned ON. If not, then it captures the last known location of the compromised device. This module was injected in code stolen from Liberty VPN; Liberty VPN didn’t have any module to access the location.

The code snapshot shared here-in is from iKHfaa VPN, the code shows using of the Android Room library to create and store the data using SQLite statement.

Snippet below is from iKHfaa VPN’s decompiled code, the code reveals employing ROOM Library, provided by Android Jetpack. The snippet shows the use of the ROOM library’s DAO (Data Access Object) interface feature, which is responsible for inserting, updating, and deleting the data. The instance used for fetching and storing contacts in the RoomDatabase is using the SQLite statement.

As can be seen, the below snippet reveals usage of the Retrofit HTTP client library to interact with https[:]ikhfaavpn[.]com. Retrofit is responsible for communication between Android apps with web service, APIs, and backend servers. In this case, ikhfaavpn[.] acted as the official website of iKHfaa VPN as well as fulfilled the job of command and control that received the location and contact of the device.

Included here-in is a snippet from decompiled code of the nSure Chat application. The module below employs retrofit and communicates with the domain and port configured to it. Note, the same command and control server in the nSure Chat app was used for the Cobalt strike a year ago on a different port.

After capturing live traffic from nSure Chat, we found that the communication between App and port 4000 configured to the domain is encrypted by using letsencrypt, which provides security encryption for HTTP requests.

Below is snippet from the Live HTTP request captured, the request shows data sent over to appnsure.com:9090 in Json using the authorization key. This shows the C2 server is also logging new user, who is installing this app with their username and password in plain text.

EXTERNAL THREAT LANDSCAPE MANAGEMENT (ETLM)
ATTRIBUTION
After conducting a thorough analysis of samples, with a moderate level of confidence, we can confirm that the Google Play store account is linked to APT DoNot, as it hosts Android apps exhibiting malicious characteristics. Furthermore, we have discovered encrypted strings utilizing the AES/CBC/PKCS5PADDING algorithm. The code is also obfuscated using Proguard. Interestingly, the text file generated by the Android application shares the same name as the text file in the previously used Android Malware by DoNot, to store data locally. These encryption techniques were previously employed by APT DoNot in their earlier Android sample, which was extensively researched and documented in a detailed report published in April. These technical findings collectively enable us to attribute these samples to the notorious APT group; DoNot.
THREAT ACTOR PROFILE

VICTIMOLOGY
We know very little about the specific victims targeted using this malware except that they were based in Pakistan. As per malware characteristics and access, it gains hints of the threat actor aiming for information gathering for a second-stage attack, using malware with advanced features. In this instance, we believe that the threat actor used a spear messaging attack on Telegram or WhatsApp messenger to lure victims into installing an app using the Google Play store, whereas, in the past, the threat actor employed malicious Word documents, carrying macros via spear phishing attacks, and targeted various regions in South Asia with Android malware, pretending to be chat apps. 
CONCLUSION
It appears that this Android malware was specifically designed for information gathering. By gaining access to victims’ contact lists and locations, the threat actor can strategize future attacks and employ Android malware with advanced features to target and exploit the victims.
We have observed a shift in the tactics employed by the DoNot APT group, as they have taken a step further by deploying Android malware on the Google Play store. The process of uploading an Android app on Google Play is a meticulous one, involving a thorough examination of each permission by developers. The previous year, APT Sidewinder deployed Android malware on the Play Store by acting as a VPN provider: – In that case, also we observed that the app was a copied version of Nord VPN, with the addition of malicious modules. Every year, researchers discover Android Apps with malware characteristics, or legitimate apps making users download malicious Android apps on Google Play Store, however, there are very few cases of APTs employing Google Play Store to host malicious apps by bypassing security checks. By sharing a Google Play Store link, an app greatly enhances the likelihood of a successful compromise. This approach takes advantage of the people’s trust placed in the Google Play Store, as it is uncommon for individuals to suspect it of hosting malicious applications. The implications would be significant if advanced persistent threats (APTs) were to adopt this strategy in the wild.
DIAMOND MODEL

APPENDIX I
Indicators of Compromise


Indicator
Type
Remarks


EAED560A605374FE23317C1C37BBD05383 CEEC09FF83975B989E4C5D612FC039
SHA256
iKHfaa.apk


EE9900EF830539D113A8BCC0C7B4DD981C 3FD61868319C9FE9491465BCAF4661
SHA256
nSure Chat.apk


Appnsure[.]com[:]4000
Domain and port
Command Control


Appnsure[.]com[:]9090
Domain and port
Command Control


193[.]149[.]176[.]226
IP Address
Command Control


Ikhfaavpn[.]com
Domain
Command Control


APPENDIX II
MITRE ATT&CK Technique Detection


Tactics
Technique ID
Description


TA0101 – Command and Control
T0869-Standard Application Layer Protocol 
The threat actor uses a web service as a command-and-control server 


TA0035 – Collection
T1430-Location Tracking
Fetches precise Location as a part of information gathering.


TA0030 – Defense Evasion
T1406-Obfuscated Files or information 
Obfuscated code in the malicious app as part of a defense mechanism.


TA0035 – Collection
T1636.003- Contact List
Access to updated contacts as a part of information gathering.


TA0035 – Collection
T1532 – Archive Collected Data 
The threat actor uses encryption over data transfer to the command and control.



Back to Listing





 





 
Company
Solutions
Products
Partners
Resources
Careers
 





 





 




Company
Solutions
Products
Partners
Resources
Careers
   
  




Copyright CYFIRMA. All rights reserved.


Privacy Policy
 









×




Your iFrame Code




























































































































































































