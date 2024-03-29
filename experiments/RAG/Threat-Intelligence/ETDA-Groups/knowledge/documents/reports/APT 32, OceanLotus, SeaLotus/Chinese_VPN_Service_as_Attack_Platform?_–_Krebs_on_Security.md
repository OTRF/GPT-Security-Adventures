# Reference for threat actor for "APT 32, OceanLotus, SeaLotus"

**Title**: Chinese VPN Service as Attack Platform? – Krebs on Security

**Source**: https://krebsonsecurity.com/2015/08/chinese-vpn-service-as-attack-platform/

## Content











Chinese VPN Service as Attack Platform? – Krebs on Security











































Advertisement


Advertisement

























Skip to content

HomeAbout the Author
Advertising/Speaking







Chinese VPN Service as Attack Platform?










August 4, 2015


31 Comments
 




Hardly a week goes by without a news story about state-sponsored Chinese cyberspies breaking into Fortune 500 companies to steal intellectual property, personal data and other invaluable assets. Now, researchers say they’ve unearthed evidence that some of the same Chinese hackers also have been selling access to compromised computers within those companies to help perpetrate future breaches.
The so-called “Great Firewall of China” is an effort by the Chinese government to block citizens from accessing specific content and Web sites that the government has deemed objectionable. Consequently, many Chinese seek to evade such censorship by turning to virtual private network or “VPN” services that allow users to tunnel their Internet connections to locations beyond the control of the Great Firewall.

Security experts at RSA Research say they’ve identified an archipelago of Chinese-language virtual private network (VPN) services marketed to Chinese online gamers and those wishing to evade censorship, but which also appear to be used as an active platform for launching attacks on non-Chinese corporations while obscuring the origins of the attackers.
Dubbed by RSA as “Terracotta VPN” (a reference to the Chinese Terracotta Army), this satellite array of VPN services “may represent the first exposure of a PRC-based VPN operation that maliciously, efficiently and rapidly enlists vulnerable servers around the world,” the company said in a report released today.
The hacker group thought to be using Terracotta to launch and hide attacks is known by a number of code names, including the “Shell_Crew” and “Deep Panda.” Security experts have tied this Chinese espionage gang to some of the largest data breaches in U.S. history, including the recent attack on the U.S. Office of Personnel Management, as well as the breaches at U.S. healthcare insurers Anthem and Premera.
According to RSA, Terracotta VPN has more than 1,500 nodes around the world where users can pop up on the Internet. Many of those locations appear to be little more than servers at Internet service providers in the United States, Korea, Japan and elsewhere that offer cheap virtual private servers.
But RSA researchers said they discovered that many of Terracotta’s exit nodes were compromised Windows servers that were “harvested” without the victims’ knowledge or permission, including systems at a Fortune 500 hotel chain; a hi-tech manufacturer; a law firm; a doctor’s office; and a county government of a U.S. state.
The report steps through a forensics analysis that RSA conducted on one of the compromised VPN systems, tracking each step the intruders took to break into the server and ultimately enlist the system as part of the Terracotta VPN network.
“All of the compromised systems, confirmed through victim-communication by RSA Research, are Windows servers,” the company wrote. “RSA Research suspects that Terracotta is targeting vulnerable Windows servers because this platform includes VPN services that can be configured quickly (in a matter of seconds).”
RSA says suspected nation-state actors have leveraged at least 52 Terracotta VPN nodes to exploit sensitive targets among Western government and commercial organizations. The company said it received a specific report from a large defense contractor concerning 27 different Terracotta VPN node Internet addresses that were used to send phishing emails targeting users in their organization.
“Out of the thirteen different IP addresses used during this campaign against this one (APT) target, eleven (85%) were associated with Terracotta VPN nodes,” RSA wrote of one cyber espionage campaign it investigated. “Perhaps one of the benefits of using Terracotta for Advanced Threat Actors is that their espionage related network traffic can blend-in with ‘otherwise-legitimate’ VPN traffic.”
DIGGING DEEPER
RSA’s report includes a single screen shot of software used by one of the commercial VPN services marketed on Chinese sites and tied to the Terracotta network, but for me this was just a tease: I wanted a closer look at this network, yet RSA (or more likely, the company’s lawyers) carefully omitted any information in its report that would make it easy to locate the sites selling or offering the Terracotta VPN.
RSA said the Web sites advertising the VPN services are marketed on Chinese-language Web sites that are for the most part linked by common domain name registrant email addresses and are often hosted on the same infrastructure with the same basic Web content. Along those lines, the company did include one very useful tidbit in its report: A section designed to help companies detect servers that may be compromised warned that any Web servers seen phoning home to 8800free[dot]info should be considered hacked.

A lookup at Domaintools.com for the historic registration records on 8800free[dot]info show it was originally registered in 2010 to someone using the email address “xnt50@163.com.” Among the nine other domains registered to xnt50@163.com is 517jiasu[dot]cn, an archived version of which is available here.
Domaintools shows that in 2013 the registration record for 8800free[dot]info was changed to include the email address “jzbb@foxmail.com.” Helpfully, that email was used to register at least 39 other sites, including quite a few that are or were at one time advertising similar-looking VPN services.
Pivoting off the historic registration records for many of those sites turns up a long list of VPN sites registered to other interesting email addresses, including “adsyb@163.com,” “asdfyb@hotmail.com” and “itjsq@qq.com” (click the email addresses for a list of domains registered to each).
Armed with lists of dozens of VPN sites, it wasn’t hard to find several sites offering different VPN clients for download. I installed each on a carefully isolated virtual machine (don’t try this at home, kids!). Here’s one of those sites:
A Google-translated version of one of the sites offering the VPN software and service that RSA has dubbed “Terracotta.”
All told, I managed to download, install and use at least three VPN clients from VPN service domains tied to the above-mentioned email addresses. The Chinese-language clients were remarkably similar in overall appearance and function, and listed exit nodes via tabs for several countries, including the Canada, Japan, South Korea and the United States, among others. Here is one of the VPN clients I played with in researching this story:

This one was far more difficult to use, and crashed repeatedly when I first tried to take it for a test drive:

None of the VPN clients I tried would list the Internet addresses of the individual nodes. However, each node in the network can be discovered simply by running some type of network traffic monitoring tool in the background (I used Wireshark), and logging the address that is pinged when one clicks on a new connection.
RSA said it found more than 500 Terracotta servers that were U.S. based, but I must have gotten in on the fun after the company started notifying victim organizations because I found only a few dozen U.S.-based hosts in any of the VPN clients I checked. And most of the ones I did find that were based in the United States appeared to be virtual private servers at a handful of hosting companies.
The one exception I found was a VPN node tied to a dedicated Windows server for the Web site of a company in Michigan that manufactures custom-made chairs for offices, lounges and meeting rooms. Contacted by KrebsOnSecurity, the company confirmed that its serve was infected and beaconing home to the control servers described in the RSA report.
In addition to the U.S.-based hosts, I managed to step through a huge number of systems based in South Korea. I didn’t have time to look through each record to see whether any of the Korean exit nodes were interesting, but here’s the list I came up with in case anyone is interested. I simply haven’t had time to look at and look up the rest of the clients in what RSA is calling the Terracotta network. Here’s a more simplified list of just the organizational names attached to each record.
Assuming RSA’s research is accurate (and I have no reason to doubt that it isn’t) the idea of hackers selling access to hacked PCs for anonymity and stealth online is hardly a new one. In Sept. 2011, I wrote about how the Russian cybercriminals responsible for building the infamous TDSS botnet were selling access to computers sickened with the malware via a proxy service called AWMProxy, even allowing customers to pay for the access with PayPal, Visa and MasterCard.
It is, after all, incredibly common for malicious hackers to use systems they’ve hacked to help perpetrate future cybercrimes – particularly espionage attacks. A classified map of the United States obtained by NBC last week showing the victims of Chinese cyber espionage over the past five years lights up like so many exit nodes in a VPN network.
Source: NBC
Update, 2:34 p.m. ET: Updated the story to note that I heard back from the furniture company victim named in the story, and that the company was able to confirm a breach of its servers by this VPN service.



         This entry was posted on Tuesday 4th of August 2015 08:03 AM 
         
A Little Sunshine Breadcrumbs
Deep Panda Great Firewall RSA Research Shell_Crew Terracotta VPN




Post navigation
← ‘Like Cutting Off a Limb to Save the Body’
Inside the $100M ‘Business Club’ Crime Gang →



			31 thoughts on “Chinese VPN Service as Attack Platform?”		




John August 4, 2015 

Well Brian, you learned Russian before…  Now I guess you have to learn Chinese 😉








BrianKrebs  Post authorAugust 4, 2015 

I really do want to learn it, but it’s so daunting. I learned a few things from this story, though, like the words for United States, Japan, Canada, etc.








Eric August 4, 2015 

As one who has studied both Russian and Chinese, I can say that it isn’t as hard as you think.  I found the grammar and sentence structure to be pretty straightforward.  The daunting bit was all of the characters, of course, but even then once you get a bit of experience you can tease out information from characters you think you might have forgotten and “sound them out”.  Some people choose to only study the spoken language and bypass the characters, but that’s not likely to be something you would find to be useful.
The USDA Graduate School has language programs that are really quite good and very affordable.  When I studied Mandarin, the classes were close to L’Enfant Plaza Metro.












Matthew P Clements August 4, 2015 

Thanks for this research and article. Keep up the great work keeping us informed on the crazy world we live in.








Forebode August 4, 2015 

… why not having an actual system of blocking all non US traffic on certain routers/sites? Add to the system a request access system.  Or hold a country responsible.  Why have customs for people but not for data? We need to stop thinking about the internet in networking terms of blocking at the closest point of origination.  We can’t control other countries routers, so start putting rules on our systems to block them.  I know it’s not simple.








bob August 4, 2015 

Did you read the article? This is about software that make it looks as though your attack comes from the US. How is blocking China going to help?
On the other hand, is USA still the biggest spammer in the world? I guess blocking USA would put a big dent in spam.








LessThanObvious August 4, 2015 

@Forebode “why not having an actual system of blocking all non US traffic on certain routers/sites? ”
I agree with that and I’ve been pushing the same. There are a couple issues with it. One issue is that they are often compromising U.S. resources and launching attacks from there so only the administrators of those resources can do anything. The other issue is that IPv4 address space has been sold and traded in ways that don’t always respect regional boundaries that were intended. I really do think it’s still worth doing. Many internet attached devices and services get no benefit to offset the risk of international exposure. I myself block at least 110 class A /8 networks and a handful of smaller blocks that have gotten my attention and I haven’t seen any negative impact.








SeymourB August 5, 2015 

The bigger issue is that if you block all non-US addresses, now you can’t communicate with non-US addresses. Good luck trying to communicate with your suppliers in China, partners in Germany, etc.
Blocking the non-US addresses won’t help against servers that are already in place, but could help isolate new infections since they won’t be able to initiate those connections to/from China unless they go through a more convoluted network map (e.g. servers A talks to server B, which then talks to China).












Mike August 4, 2015 

I wonder if Chinese Language browsers have a search function.  You’d just need to find maybe 100 words or so and you could know where something was worth digging into.








Tom August 4, 2015 

Hi Brian,
Do you have a link to the RSA report?








Tom August 4, 2015 

Ignore me, I seem to be blind and completely missed it in the article!










-stephen August 4, 2015 

If the bad guys can easily and routinely discover vulnerable or compromised Windows servers on the Internet, then surely anyone can identify them, as well. Similar to an auto manufacturer which is required to recall and repair defective automobiles, I think Microsoft should use it engineers, tools and resources to identify, locate and, in cooperation with the owners where possible, repair the “defective” Windows PCs and servers or have them removed from the Internet.
Does that sound impossible or like too much work? Microsoft has been able to pinpoint *millions* of Windows 7, 8 and 9 PCs and download software to upgrade them to Windows 10. Why not use the same technology to fix the dysfunctional PCs and servers which are causing the legitimate Internet community so much grief, time and money? At the very least they should be able to identify the compromised servers owned by users who don’t even know they are being abused.
Microsoft has earned bazillions on the PCs and servers which are out there already, let them spend a few mazillions to fix the problems and help to make the Internet safe.
(My point is not so much to thrash Microsoft, but to point out that the technology exists today to address the problem of dysfunctional PCs and servers. If not Microsoft, then some other organization should take on this task, such as ICANN through a few cents tax on IP address registrations).








Bob August 4, 2015 

stephen,
“Microsoft has been able to pinpoint *millions* of Windows 7, 8 and 9 PCs and download software to upgrade them to Windows 10.”
Microsoft didn’t pinpoint the PCs, the PCs phoned home to Microsoft via Windows / Microsoft Update.
“Why not use the same technology to fix the dysfunctional PCs and servers…”
Microsoft already does this to the extent that the Malicious Software Removal Tool is listed as an important update in Windows / Microsoft Update and runs once a month unless disabled by the user.
The key issues are that the user, or malware installed on the PC, can prevent it from running, and by definition, it can’t detect and fix a zero-day exploit.








Peter August 4, 2015 

Another key point is that many of these severs are not patched. These were not zero-dayed, these were simply admins that forgot about the server and the server not auto-updating (which for a server is not completely bad).










Barry August 4, 2015 

And they could call up the machine’s owner and announce they are from MS, tell the owner they are infected and demand access to the machine to clean up the infection. Of course, it sounds like a scam when you frame it that way.










Patrick August 4, 2015 

Excellent article, some of your best work yet.








NotMe August 4, 2015 

Way to dig in and get your hands on the issue Brian!
I can always count on you to find an angle on the story and run with it.  I hope you continue to pursue the chinese sites  with the same energy you put into our friends in Russia and the Euro zone.
Brazil is also full of internet scammers, maybe some portuguese would also be useful?
Thanks for your work!








TGuerrant August 4, 2015 

Symantec’s fingered a group it called “Black Vine” for the OPM and Anthem hacks.  Is that a competing theory or is Black Vine ostensibly part of or an ally of Shell Crew and Deep Panda?  (And nobody, just NOBODY, say “Bilderburger with a Side of Thais,” dammit.)








stvs August 4, 2015 

RSA Research suspects that Terracotta is targeting vulnerable Windows servers because this platform includes VPN services that can be configured quickly (in a matter of seconds).
That Microsoft hasn’t completely dismantled PPTP is breathtakingly irresponsible.








Steven August 7, 2015 

Because things will break.  fyi, os x still support pptp. too










jim August 4, 2015 

As one stated above, the technology phones home. Home is where the technology was constructed, was the American technology that was constructed made in America? I’d bet not. Never heard of programed chips? Embedded programs have been available for many years now.maybe they don’t have to open/interstate a system, if its open by built in back doors, and you don’t have to even knock.








squirrel August 4, 2015 

Not sure if I understand Terracotta VPN’s logic correctly. But here’s what I see: chinese hackers enlisted VPN nodes from the globe, for both  illegitimate hacking and commercial selling purpose(the commercial VPN service listed in this article)?








Amper$and August 4, 2015 

Terracotta VPN?  More like:  HacKripAttack as a Service – HaaS?








student August 4, 2015 

.txt?… .json next time please so I can ingest it a little easier and nslookup the ips








Amper$and August 4, 2015 

I’m actually thinking the Michigan ‘custom chair company’ server that looked as if it was “compromised” is a legitament VPN server that’s heavily utilized on a daily basis.  Indeed by, mnny hpppy cwyants!  
Couldn’t the custom chair company be a front for a legitament Chinese tunnel to our door steps…  Real furniture, or more like a legal exit port straight off a Chinese tunnel?  
Reminds me what my mother warned me 36 some years ago during summer break (dig that pit any deeper and you’ll be sharing your fort…. and your supper with a-china-man!).  Turns out she wasn’t far off…
Let’s face it, the 517VPN company you highlighted looks to have a decent setup which someone invested time and money into.  They’re gonna wanna ROI.  Why not setup real VPN exit ramps desiguised as something else which serves a dual purpose:  tax evasion and hackcripting…..  
Worse fear comes true?  Hopefully it’s just a coincidence that 517 is the area code in mid-Michigan where A TON of Chinese students ‘study’.  And BTW – most seemingly drive the most expensive cars available….  Maybe we’re gaining a better idea how they can afford such luxuries…  Opening, and widening tunnels,, virtual custom chairs in out back yard forts, most of which I’m sure is legal.. I’m sure this is just the beginning…








Chris August 5, 2015 

Nice racist comment. Hey Krebs, do you review these? Might wanna think about deleting his.










IA Eng August 5, 2015 

I’ve taken a peek at the 360.cn so-called “free” web browsers and antivirus software they offer. They mimic the Internet Exploder “E” but for 360 – its in green. Its borderline click-fraud, extremely difficult for the average “joe” to remove, and intimidates the users to install all of their products in order to “improve their security score”. 
There isn’t much that comes out of this…… country.








IA Eng August 5, 2015 

This is a subject of Blackhat as well.
I wonder how many compromised servers actually help fuel this Chinese VPN Junk heap….
http://www.csoonline.com/article/2956433/advanced-persistent-threats/terracotta-vpn-hijacks-servers-for-commercial-gain.html










andrew August 5, 2015 

Most of these compromises would be foiled if the targets practiced proper network security methods. Most of them are from things like SQL injection or weak passwords.








Jenny August 6, 2015 

This is just for gaining more customers








Chris Nielsen August 29, 2015 

There were some comments about blocking non-USA IP addresses. I have been doing this for one client whose business is limited to customers in the US. We block at the site and server levels. Entries have been entered by hand over many years of looking up the IP in WHOIS to make sure we don’t block friendly traffic. What we block is entire ranges known to be allocated outside the US, such as 90.x.x.x. but we also block ranges inside the US if they are under the control of a hosting company (not ISP). We block the large ranges at the server, since we don’t want web traffic or email spam, and block at the site level when we want to block visitors from hosting companies (proxies) but don’t want to block email from potential customers.
For my personal email, I am now down to just a few spams per day. After years of filing spam reports I got tired of the battle. My email is now protected from non-US mailers and custom filters screen non-US TLDs, domains, and text from known spam.






Comments are closed.




Advertisement


Advertisement
Mailing ListSubscribe hereSearch KrebsOnSecurity

Search for:





Recent Posts


U.S. Internet Leaked Years of Internal, Customer Emails


Fat Patch Tuesday, February 2024 Edition


Juniper Support Portal Exposed Customer Device Info


From Cybercrime Saul Goodman to the Russian GRU


Arrests in $400M SIM-Swap Tied to Heist at FTX?


 
Story Categories

A Little Sunshine

All About Skimmers

Ashley Madison breach

Breadcrumbs

Data Breaches

DDoS-for-Hire

Employment Fraud

How to Break Into Security

Internet of Things (IoT)

Latest Warnings

Ne'er-Do-Well News

Other

Pharma Wars

Ransomware

Russia's War on Ukraine

Security Tools

SIM Swapping

Spam Nation

Target: Small Businesses

Tax Refund Fraud

The Coming Storm

Time to Patch

Web Fraud 2.0


Why So Many Top Hackers Hail from Russia 










					© Krebs on Security - Mastodon 






