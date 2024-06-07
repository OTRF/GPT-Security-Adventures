# Reference for threat actor for "APT 29, Cozy Bear, The Dukes"

**Title**: The Dukes of Moscow - VMware Security Blog - VMware

**Source**: https://www.carbonblack.com/2020/03/26/the-dukes-of-moscow/

## Content












The Dukes of Moscow - VMware Security Blog - VMware































































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
The Dukes of Moscow

March 26, 2020
16 min read
 

 









Share on:



Share on Twitter




Share on LinkedIn




Share on Facebook




Share on Reddit




Email this post



Copy Link

 



Overview
APT29, also known as The Dukes or Cozy Bear, is a cyberespionage group active since at least 2008. It’s believed that the group operates either under the Russian Foreign Intelligence Service (SVR) or the Russian Federal Security Service (FSB). They primarily target western governments and related organizations. Targets include government ministries, government agencies, political think tanks, and even governmental subcontractors.
With an upcoming election in the United States, and the history of APT29 targeting western governments, it’s a good time to review some of the more recent campaigns from APT29. APT29 is an extremely stealthy threat group. As much as possible they attempt to blend their network traffic in with other legitimate traffic. They do this by using compromised servers as their Command and Control (C2) infrastructure as well as using social media sites to deliver C2 messages. They have often used encrypted data in images to both deliver messages and help blend in.
In this post we take a look at some of the notable campaigns that have been discovered since 2015 up to the present day as well as the malware used in these more recent campaigns.
 
Timeline
2008 – 2015
F-Secure’s The Dukes whitepaper provides great coverage of the history of the group between 2008 and 2015. Some of the notable early campaigns are as follows:

A campaign aimed at gathering information about Georgia-NATO relations
Exploitation of an Adobe 0-day vulnerability (CVE-2013-0640 and CVE-2013-0641) to target organizations in Ukraine, Belgium, Portugal, Romania, the Czech Republic, Ireland, the United States and Hungary
Delivering malware via a malicious Tor exit node
A high volume spear phishing campaign using e-fax themed spam usually only seen in crimeware or ransomware campaigns

2016
In June of 2016 it was discovered that APT29 had successfully breached and exfiltrated data from Democratic National Committee (DNC) servers. Crowdstrike performed an investigation and it was determined that APT29 had most likely been present in the DNC servers for at least a year. Additionally it was determined that APT28 had also breached the network. APT29 was primarily using the SeaDuke malware as part of the attack.
In August of 2016 Volexity detected a wave of spear phishing attempts against humanitarian non-governmental organizations (NGOs) and think tanks. Volexity believes this targeting initially began in 2015 but continued up to the 2016 election. Shortly after the 2016 election closed a new email phishing campaign was discovered very similar to the attempts from August of 2016. Both times the emails were attempting to distribute a PowerDuke malware variant.
2017
In February of 2017 the Norwegian Police Security Service (PST) reported on attempts to spearphish multiple individuals within the Ministry of Defence, Ministry of Foreign Affairs, and the Labour Party. These spear phishing attempts were attributed to APT29.
Also in 2017 it was revealed that attempts were made by APT29 to hack into the Dutch Ministries. Targeted phishing attempts were made by APT29 to obtain credentials for government employees in the Dutch Ministries.
2018
Most of 2018 was relatively quiet in regards to APT29 activity. In November however, FireEye reported on a possible APT29 phishing campaign targeting multiple U.S. companies and organizations. In this case the phishing attempts contained a Cobalt Strike beacon payload. While the attack was not definitively attributed to APT29, the similarities in the malicious LNK files and PowerShell used makes it seem plausible.
2019
In October of 2019 ESET released a report on what they called Operation Ghost. They noted that targets in the attacks varied from the Ministry of Foreign Affairs in at least three different countries in Europe as well as the Washington, DC embassy of a European Union country. In this case four new malware families were identified with enough similarities to previous APT29 tools that it was concluded these new attacks were most likely also carried out by APT29.
 
Malware Families
First we will take a look at each malware family used in the recent campaigns. Then we will cover common functionality used by multiple malware families that can possibly be used to detect new unknown samples.
SeaDuke

SeaDuke was used in the 2016 DNC breaches. It’s written in python and compiled with PyInstaller. It communicates over HTTP using RC4 to encrypt its information and passes it across to the server in a base64 encoded cookie value. According to a report by Palo Alto Networks, The malware provides the ability to download and upload files and execute new payloads.
PowerDuke

PowerDuke was part of the spear phishing campaign in 2016 targeting NGOs and think tanks. It was delivered via email as malicious LNK files which executed PowerShell to then drop the PowerDuke backdoor. The backdoor itself was a DLL file executed from rundll32. It supports remote information gathering of the machines it’s been installed on.
MiniDuke

MiniDuke has been around since at least 2010. It consists of a downloader component as well as some backdoor functionality. Some parts of MiniDuke obtain its C2 information from Twitter. Interestingly, the malware is coded in assembly. The most recent samples provide the same basic functionality as the older ones but include additional obfuscation in the form of control-flow flattening. This also has the side effect of increasing the overall size of the newer samples.
PolyglotDuke

PolyglotDuke is a downloader. ESET noted that when they encountered PolyglotDuke, it was being used to download Miniduke. PolyglotDuke acts as the initial component to install the second stage payload. It will reach out to Twitter to retrieve its real C2 address. After some initial communication with the C2 server PolyglotDuke will download an image from the C2 server over HTTP. The image retrieved is a valid image with extra RC4 encrypted data appended at the end.
RegDuke

RegDuke is a first stage implant. Its purpose is to ensure access to a machine isn’t lost by staying undetected as long as possible. It is written using the .NET framework and is composed of a loader as well as a payload. The payload is a backdoor that uses Dropbox as its C2 server. The backdoor will regularly connect to a specific Dropbox account and look for PNG files to download. In this case the malicious payload is embedded within the image data itself. Data is stored in the least significant bits of each pixel and the malware can then extract the data. It then AES decrypts the data using a hardcoded key.
LiteDuke
LiteDuke is a third stage backdoor. It appears to use the same dropper as PolyglotDuke. Its payload makes use of an AES encrypted SQLite database to store its configuration. LiteDuke supports a large number of individual commands including host information retrieval, file upload and download, and the ability to execute other code. LiteDuke C2 servers appear to be compromised servers, and the malware communicates with them using normal HTTP requests. It attempts to use a realistic User-Agent string to blend in better with normal HTTP traffic.
FatDuke

FatDuke is the current third stage backdoor being used by APT29. It is dropped by MiniDuke.  FatDuke has its configuration contained in the PE files resource section. It’s stored as a base64 encoded JSON string. FatDuke supports C2 communication over HTTP or named pipes on the local network. Like LiteDuke, when FatDuke communicates using HTTP, it attempts to get the User-Agent string from the installed browser so that its traffic blends in better with normal HTTP traffic. FatDuke downloads malicious image files from the C2 server in order to decrypt its commands. The image files contain a corrupt PNG header and instead contains AES encrypted data from the C2 server.
 
Common String Encryption
The most recent samples of APT29 malware seem to make use of a common string encryption routine. This encryption routine was used as far back as 2013 in an OnionDuke sample (19972cc87c7653aff9620461ce459b996b1f9b030d7c8031df0c8265b73f670d). The strings are encoded as a sequence of hexadecimal digits. Every two hexadecimal digits decode into a single character. For example, with d35b448d9c5b6c95, there are 16 hexadecimal characters and, when decoded, we get the string “Software”.
The string decryption routine is interesting because it makes use of the srand() and rand() API calls to provide a deterministic constant used in the decryption of each character. The srand call is used to seed the pseudo-random number generator and is seeded with the malware’s compilation timestamp. Then during each iteration of the string decryption loop rand will be called and that number will be used to decode the character.
The algorithm works as follows. Loop through every two characters in the encrypted string. Convert each hexadecimal ascii character to its decimal equivalent. Call rand and then perform the following computation:
character = 16 * hex1 + hex2 – rand()
This is converting the two ascii hex digits into its decimal equivalent and then subtracting the random number.
As mentioned before this string encryption is used in old OnionDuke samples but also used in PolyglotDuke, LiteDuke and FatDuke. A python routine to decrypt the strings can be seen below:

 
Detection
Given the level of sophistication of APT29 malware, detection can be a challenge. The malware attempts to blend in with normal network traffic as much as possible. This is done with a handful of different tactics. Communication is often done with the HTTP protocol. Some of the malware will attempt to use realistic looking User-Agent strings with the requests. The websites contacted can be various popular social media sites as well as real websites that have been compromised. Finally in the most sophisticated samples the payloads are simply image files retrieved which might look like a normal request from a web browser loading images on a page. All of these tactics contribute to the network traffic looking very similar to typical web browsing traffic.
While the network traffic itself might be hard to notice amidst all the other requests going on in your network, if you’re monitoring your endpoints it might be more noticeable. For instance, in some cases the droppers are writing the malicious backdoors to disk as a DLL and then executing them using rundll32. On the endpoint monitoring side, seeing a process like rundll32 making connections to popular web sites like Twitter or Dropbox is probably not going to be something that typically happens. This in combination with detecting untrusted new files being executed can be some of the best ways to detect this malware.
 
Conclusion
Since 2015 APT29 has continued its targeted campaigns against governments and related organizations. Their stealthy network communication tactics and obfuscated binaries make them hard to detect. With another U.S. election coming up it’s safe to say that we will continue to see APT29 attempting to target government entities here in the U.S. as well as around the globe. We will continue to monitor their activity to provide insight and information to our customers. 









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






