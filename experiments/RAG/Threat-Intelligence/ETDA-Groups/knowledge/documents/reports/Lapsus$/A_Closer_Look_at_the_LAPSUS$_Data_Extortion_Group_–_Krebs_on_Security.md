# Reference for threat actor for "Lapsus$"

**Title**: A Closer Look at the LAPSUS$ Data Extortion Group – Krebs on Security

**Source**: https://krebsonsecurity.com/2022/03/a-closer-look-at-the-lapsus-data-extortion-group/

## Content











A Closer Look at the LAPSUS$ Data Extortion Group – Krebs on Security











































Advertisement


Advertisement

























Skip to content

HomeAbout the Author
Advertising/Speaking







A Closer Look at the LAPSUS$ Data Extortion Group










March 23, 2022


33 Comments
 




Microsoft and identity management platform Okta both this week disclosed breaches involving LAPSUS$, a relatively new cybercrime group that specializes in stealing data from big companies and threatening to publish it unless a ransom demand is paid. Here’s a closer look at LAPSUS$, and some of the low-tech but high-impact methods the group uses to gain access to targeted organizations.
First surfacing in December 2021 with an extortion demand on Brazil’s Ministry of Health, LAPSUS$ made headlines more recently for posting screenshots of internal tools tied to a number of major corporations, including NVIDIA, Samsung, and Vodafone.
On Tuesday, LAPSUS$ announced via its Telegram channel it was releasing source code stolen from Microsoft. In a blog post published Mar. 22, Microsoft said it interrupted the LAPSUS$ group’s source code download before it could finish, and that it was able to do so because LAPSUS$ publicly discussed their illicit access on their Telegram channel before the download could complete.
One of the LAPSUS$ group members admitted on their Telegram channel that the Microsoft source code download had been interrupted.
“This public disclosure escalated our action allowing our team to intervene and interrupt the actor mid-operation, limiting broader impact,” Microsoft wrote. “No customer code or data was involved in the observed activities. Our investigation has found a single account had been compromised, granting limited access. Microsoft does not rely on the secrecy of code as a security measure and viewing source code does not lead to elevation of risk.”
While it may be tempting to dismiss LAPSUS$ as an immature and fame-seeking group, their tactics should make anyone in charge of corporate security sit up and take notice. Microsoft says LAPSUS$ — which it boringly calls “DEV-0537” — mostly gains illicit access to targets via “social engineering.” This involves bribing or tricking employees at the target organization or at its myriad partners, such as customer support call centers and help desks.
“Microsoft found instances where the group successfully gained access to target organizations through recruited employees (or employees of their suppliers or business partners),” Microsoft wrote. The post continues:
“DEV-0537 advertised that they wanted to buy credentials for their targets to entice employees or contractors to take part in its operation. For a fee, the willing accomplice must provide their credentials and approve the MFA prompt or have the user install AnyDesk or other remote management software on a corporate workstation allowing the actor to take control of an authenticated system. Such a tactic was just one of the ways DEV-0537 took advantage of the security access and business relationships their target organizations have with their service providers and supply chains.”
The LAPSUS$ Telegram channel has grown to more than 45,000 subscribers, and Microsoft points to an ad LAPSUS$ posted there offering to recruit insiders at major mobile phone providers, large software and gaming companies, hosting firms and call centers.
Sources tell KrebsOnSecurity that LAPSUS$ has been recruiting insiders via multiple social media platforms since at least November 2021. One of the core LAPSUS$ members who used the nicknames “Oklaqq” and “WhiteDoxbin” posted recruitment messages to Reddit last year, offering employees at AT&T, T-Mobile and Verizon up to $20,000 a week to perform “inside jobs.”
LAPSUS$ leader Oklaqq a.k.a. “WhiteDoxbin” offering to pay $20,000 a week to corrupt employees at major mobile providers.
Many of LAPSUS$’s recruitment ads are written in both English and Portuguese. According to cyber intelligence firm Flashpoint, the bulk of the group’s victims (15 of them) have been in Latin America and Portugal.
“LAPSUS$ currently does not operate a clearnet or darknet leak site or traditional social media accounts—it operates solely via Telegram and email,” Flashpoint wrote in an analysis of the group. “LAPSUS$ appears to be highly sophisticated, carrying out increasingly high-profile data breaches. The group has claimed it is not state-sponsored. The individuals behind the group are likely experienced and have demonstrated in-depth technical knowledge and abilities.”
Microsoft said LAPSUS$ has been known to target the personal email accounts of employees at organizations they wish to hack, knowing that most employees these days use some sort of VPN to remotely access their employer’s network.
“In some cases, [LAPSUS$] first targeted and compromised an individual’s personal or private (non-work-related) accounts giving them access to then look for additional credentials that could be used to gain access to corporate systems,” Microsoft wrote. “Given that employees typically use these personal accounts or numbers as their second-factor authentication or password recovery, the group would often use this access to reset passwords and complete account recovery actions.”
In other cases, Microsoft said, LAPSUS$ has been seen calling a target organization’s help desk and attempting to convince support personnel to reset a privileged account’s credentials.
“The group used the previously gathered information (for example, profile pictures) and had a native-English-sounding caller speak with the help desk personnel to enhance their social engineering lure,” Microsoft explained. “Observed actions have included DEV-0537 answering common recovery prompts such as “first street you lived on” or “mother’s maiden name” to convince help desk personnel of authenticity. Since many organizations outsource their help desk support, this tactic attempts to exploit those supply chain relationships, especially where organizations give their help desk personnel the ability to elevate privileges.”
LAPSUS$ recruiting insiders via its Telegram channel.

SIM-SWAPPING PAST SECURITY
Microsoft said LAPSUS$ also has used “SIM swapping” to gain access to key accounts at target organizations. In a fraudulent SIM swap, the attackers bribe or trick mobile company employees into transferring a target’s mobile phone number to their device. From there, the attackers can intercept any one-time passwords sent to the victim via SMS or phone call. They can also then reset the password for any online account that allows password resets via a link sent over SMS.
“Their tactics include phone-based social engineering; SIM-swapping to facilitate account takeover; accessing personal email accounts of employees at target organizations; paying employees, suppliers, or business partners of target organizations for access to credentials and multifactor authentication (MFA) approval; and intruding in the ongoing crisis-communication calls of their targets,” Microsoft wrote.
Allison Nixon is chief research officer at Unit 221B, a cybersecurity consultancy based in New York that closely tracks cybercriminals involved in SIM-swapping. Working with researchers at security firm Palo Alto Networks, Nixon has been tracking individual members of LAPSUS$ prior to their forming the group, and says the social engineering techniques adopted by the group have long been abused to target employees and contractors working for the major mobile phone companies.
“LAPSUS$ may be the first to make it extremely obvious to the rest of the world that there are a lot of soft targets that are not telcos,” Nixon said. “The world is full of targets that are not used to being targeted this way.”
Microsoft says LAPSUS$ also has been known to gain access to victim organizations by deploying the “Redline” password-stealing malware, searching public code repositories for exposed passwords, and purchasing credentials and session tokens from criminal forums.
That last bit is interesting because Nixon said it appears at least one member of LAPSUS$ also was involved in the intrusion at game maker Electronic Arts (EA) last year, in which extortionists demanded payment in exchange for a promise not to publish 780 GB worth of source code. In an interview with Motherboard, the hackers claimed to have gained access to EA’s data after purchasing authentication cookies for an EA Slack channel from a dark web marketplace called Genesis.
“The hackers said they used the authentication cookies to mimic an already-logged-in EA employee’s account and access EA’s Slack channel and then trick an EA IT support staffer into granting them access to the company’s internal network,” wrote Catalin Cimpanu for The Record.
Why is Nixon convinced LAPSUS$ was behind the EA attack? The “WhiteDoxbin/Oklaqq” identity referenced in the first insider recruitment screenshot above appears to be the group’s leader, and it has used multiple nicknames across many Telegram channels. However, Telegram lumps all aliases for an account into the same Telegram ID number.
Back in May 2021, WhiteDoxbin’s Telegram ID was used to create an account on a Telegram-based service for launching distributed denial-of-service (DDoS) attacks, where they introduced themself as “@breachbase.” News of EA’s hack last year was first posted to the cybercriminal underground by the user “Breachbase” on the English-language hacker community RaidForums, which was recently seized by the FBI.
WHO IS LAPSUS$?
Nixon said WhiteDoxbin — LAPSUS$’s apparent ringleader — is the same individual who last year purchased the Doxbin, a long-running, text-based website where anyone can post the personal information of a target, or find personal data on hundreds of thousands who have already been “doxed.”
Apparently, Doxbin’s new owner failed to keep the site functioning smoothly, because top Doxbin members had no problems telling WhiteDoxbin how unhappy they were with his stewardship.
“He wasn’t a good administrator, and couldn’t keep the website running properly,” Nixon said. “The Doxbin community was pretty upset, so they started targeting him and harassing him.”
Nixon said that in January 2022, WhiteDoxbin reluctantly agreed to relinquish control over Doxbin, selling the forum back to its previous owner at a considerable loss. However, just before giving up the forum, WhiteDoxbin leaked the entire Doxbin data set (including private doxes that had remained unpublished on the site as drafts) to the public via Telegram.
The Doxbin community responded ferociously, posting on WhiteDoxbin perhaps the most thorough dox the community had ever produced, including videos supposedly shot at night outside his home in the United Kingdom.
According to the denizens of Doxbin, WhiteDoxbin started out in the business of buying and selling zero-day vulnerabilities, security flaws in popular software and hardware that even the makers of those products don’t yet know about.
“[He] slowly began making money to further expand his exploit collection,” reads his Doxbin entry. “After a few years his net worth accumulated to well over 300BTC (close to $14 mil).”
WhiteDoxbin’s Breachbase identity on RaidForums at one point in 2020 said they had a budget of $100,000 in bitcoin with which to buy zero-day flaws in Github, Gitlab, Twitter, Snapchat, Cisco VPN, Pulse VPN and other remote access or collaboration tools.
“My budget is $100000 in BTC,” Breachbase told Raidforums in October 2020. “Person who directs me to someone will get $10000 BTC. Reply to thread if you know anyone or anywhere selling this stuff. NOTE: The 0day must have high/critical impact.”
KrebsOnSecurity is not publishing WhiteDoxbin’s alleged real name because he is a minor (currently aged 17), and because this person has not officially been accused of a crime. Also, the Doxbin entry for this individual includes personal information on his family members.
Nixon said that prior to launching LAPSUS$, WhiteDoxbin was a founding member of a cybercriminal group calling itself the “Recursion Team.” According to the group’s now-defunct website, they mostly specialized in SIM swapping targets of interest and participating in “swatting” attacks, wherein fake bomb threats, hostage situations and other violent scenarios are phoned in to police as part of a scheme to trick them into visiting potentially deadly force on a target’s address.
“The team is made up of Cyber-enthusiasts who major in skills including security penetration, software development, and botting,” reads the now-defunct Recursion Team website. “We plan to have a bright future, and we hope you do too!”
Update, March 24, 11:11 a.m. ET: The BBC is quoting City of London Police as saying seven people between the ages of 16 and 21 have been arrested in connection with an investigation into a hacking group. All have been released under investigation.



         This entry was posted on Wednesday 23rd of March 2022 06:00 PM 
         
A Little Sunshine Ne'er-Do-Well News SIM Swapping
Allison Nixon Breachbase Catalin Cimpanu DEV-0537 Doxbin Electronic Arts Flashpoint LAPSUS$ microsoft Oklaqq Okta Palo Alto Networks RaidForums Recursion Team SIM swapping SWATting Unit 221B Vodafone WhiteDoxbin




Post navigation
← ‘Spam Nation’ Villain Vrublevsky Charged With Fraud
Estonian Tied to 13 Ransomware Attacks Gets 66 Months in Prison →



			33 thoughts on “A Closer Look at the LAPSUS$ Data Extortion Group”		




Ian March 23, 2022 

Sad this fella will never see jail time and will probably keep most of the money, if you already know who it is then the FBI probably knows too (I’d hope lol)








Howdy March 23, 2022 

Arion K.








JamminJ March 23, 2022 

If he lives in the UK, the FBI won’t get first dibs.  Either way, both countries can and do prosecute minors.  Even if no jail time, all money can be seized.  His parents might be on the hook for millions in damages.  And when he comes of age, that debt isn’t wiped out.  His finances will be closely watched for decades.








asdasd March 23, 2022 

Right. Cuz jail time is such a good deterrent, especially against teenage hackers.








John March 23, 2022 

Disagree. with the first part. This kid is absolutely f&%#ed for life. Law enforcement is probably closing in on him as we speak








Christopher March 24, 2022 

You’re correct. There are reports (afternoon of March 24th) that UK police have arrested 7 members of the Lapsus$ hacking group in conjunction with their latest hack.
A number of them are minors, which means they’ll not be publicly named, however the media is still likely going to leak who they are at some point.












Tired of the hacks March 23, 2022 

Have no knowledge about DDOS other then it can causes major problems for businesses if customers can’t access the business web site. If the bad guys web site is known, can’t white hat hackers and the US and other country gov’ts launch constant DDOS attacks of these web sites to frustrate the bad guys?
Brian’s article states concerning the bad guys mentioned here, “it operates solely via Telegram and email”. Can we disrupt their operations via mail bombs, shutting down servers, what about telegram? I would think we can make business impossible for some. How (if we can) can we make business impossible for most bad guys? 
They use forums, can they be disrutped, hacked, broken? Seems to me that after all these years and all the carnage done by the dirt bags, we should be able to do something (illegal perhaps, who cares?) to severly cripple these ops. Just firing arrows into the air, don’t know what is or can be done, but eventually an arrow hits something, if it’s the bad guys, too bad, get a new job at Burger King to replace your hacking.








JamminJ March 23, 2022 

I beg pardon, sire. Won’t we hit our own troops?








Klaws March 24, 2022 

Renting a new sever every few weeks (under a false name, obviously, in a country which doesn’t care, possibly) is easy. Building you own secret internal communication network is also easy, just set up an IRC server on your server and use ACME for SSL encryption (or issue your own certificates). Email and Telegram is just convenient, but could be replaced easily.
Also, the article does not mention whether the organization uses their own email servers (possibly rented, under a false name, from some hosting company) or gmail or whatever. You’d DDOS (or mail bomb) the whole hosting company (could be Amazon AWS, bought with stolen credit cards), or Google, or whatever. Have fun with that.
Of course, the group still needs to recruit new “employees” every once in a a while. Some groups use regular recruitment web pages (could be Stack Overflow, or Google, but we also knw of Russian recruitment pages where it’s apparently more okay to offer “shady” jobs). However, it could me made slightly harder for the occasional “disgruntled employee” of a potential target company to contact such a group.










Darkrabbit March 23, 2022 

Arion K****j








Yaakov Sternberg March 23, 2022 

“First surfacing in December 2021”
According to Bloomberg:
“Lapsus$ has been on the radar of security researchers since 2020, but gained notoriety last year when it took credit for targeting Brazil’s health ministry…”
Perhaps they’re lumping  Lapsus$ with WhiteDoxbin.








Yaakov Sternberg March 23, 2022 

Sorry, the quote was from Techmonitor, not Bloomberg.
https://techmonitor.ai/technology/cybersecurity/is-lapsus-targeting-big-tech-after-samsung-and-nvidia-data-breaches










wren March 23, 2022 

> WhiteDoxbin’s Breachbase identity on RaidForums at one point in 2020 said they had a budget of $1 million in bitcoin with which to buy zero-day flaws in Github, Gitlab, Twitter, Snapchat, Cisco VPN, Pulse VPN and other remote access or collaboration tools.
> “My budget is $100000 in BTC,” Breachbase told Raidforums in October 2020.
Did a 0 go missing in the quote or were these separate incidents?








BrianKrebs  Post authorMarch 23, 2022 

You’re correct. I inadvertently added an extra zero when I excerpted their message. It should be total $100,000. The story copy above has been changed to reflect that. Thanks!










The Sunshine State March 23, 2022 

17 year  old   hacker  with  autism  , that’s my guess








Nelson March 24, 2022 

This mentality is exactly the reason these threat actors’ got the upper hand. We keep labeling them as anything but a serious concern and the fault is always pushed to the side, it’s never an issue of poor IT Sec practices, never an issue of user education, never a neglected server or a missing patch, it’s the edgy basement dwellers with a chip on their shoulder…
There’s as many stupid deluded people on each end of the spectrum. That’s why we are we where we’re at.










Rodriguez March 24, 2022 

Microsoft and identity management platform Okta both disclosed this week breaches involving LAPSUS$, a relatively new cybercrime group that specializes in stealing data from big companies and threatening to publish the information unless a ransom demand is paid. Here’s a closer look at LAPSUS$, and some of the low-tech but high-impact methods the group uses to gain access to targeted organizations.








Senbonzakura March 24, 2022 

Poor kid, the reason law enforcement hasn’t busted his door in is likely because they’re looking for someone higher up the food chain, someone smarter.
I’m sure he’ll get his due, and honestly it really sucks that we couldn’t have funneled their abilities into something less criminal.








W March 24, 2022 

Impressive skillset for such a young man. Immature maybe, but that is because he is 17. Hopefully he turns to the blue side but he already has a taste of the money on the red side.








Nothxu March 24, 2022 

Benedict Thompson, Oliver Read, Ben Thompson, University of Warwick, bitcoin theft








me@pi March 24, 2022 

I browsed the their Telegram channel, and I got the feeling that they have strong ties to Brazil, not only for their “first”, but also an url they linked for download purposes, which carries Brazil’s President name.
To give further context, the Brazilian gov is known for their suspitious  Internet activities.








Tom March 24, 2022 

The idiots that work at Microsoft, Vodafone, Nvidia, Samsung, Ubisoft, Okta & others should be fired.
BBC: “A 16-year-old from Oxford has been accused of being one of the leaders of cyber-crime gang Lapsus$.”
https://www.bbc.com/news/technology-60864283








Stuart March 24, 2022 

Interesting article and then saw this on the BBC UK website:
https://www.bbc.co.uk/news/technology-60864283








Holden Gatsby March 24, 2022 

” For a fee, the willing accomplice must provide their credentials and approve the MFA prompt or have the user install AnyDesk or other remote management software on a corporate workstation allowing the actor to take control of an authenticated system. ”
– And the potential insiders never consider the possibility that their actions as users, including installing  remote back doors,  are not being logged? This is also a compelling example of why users should not have the level of access to their company computers that allows them to install this.








andyrosa March 24, 2022 

Number of media articles mentioning leader is UK teenager before Brian posted this: 0
After: *all *of *them.








Dean Marino March 24, 2022 

In a way, this is hilarious. 
Key entry mechanism:  underpaid existing IT Staff, with WAY too much access to a corporate network that has not been segmented.  Worst example of failure to segment is to allow a corporate VENDOR access to the MAIN Corporate Network.  This has not been necessary since 2007 – I actually wrote a paper on segmented network infrastructure, about that time, for Dow Chemical.
Corporations really need to hire IT Security staff, at high levels, that can Think Like a Criminal.  Oh, wait…. BE a Criminal, and get an instant Ticket to Corporate IT Security staff :).








JamminJ March 24, 2022 

I didn’t read that as having no segmentation.
Just that LAPSUS$ was looking for any foothold.  They were willing to buy access to vendor networks that were segmented.  
They primarily go after data they can threaten to release publicly.  Which means it isn’t necessary to get to the internal corporate network or domain controller.  There is plenty of juicy data on segmented business partner networks.










Phineas Fudrucker March 25, 2022 

During my evaluation of Okta ASA I discovered that a credential file can be copied from one machine or user to another and used by the second machine/user to log in as the original. I asked Okta support about it and was — eventually — told that it was expected and normal behavior. I didn’t think much about it after that since it only works with ASA and my employer decided to use Okta with Radius for Windows.  We chose a different MFA tool for Linux.
Reading about how LAPSUS$ used insiders in the attacks reminded me of that.








JamminJ March 25, 2022 

https://thehackernews.com/2022/03/7-suspected-members-of-lapsus-hacker.html








Ernestas March 27, 2022 

It is difficult for me to believe this whole story. It reeks of a scape goat. While I could stomach that there is a super talented mastermind teenager, the real issue comes from having all those funds to pay the employees and their massive success in such a short time. If you did something, you know how slow it is to get going. Waiting until you have enough money to scale up operations. When you are skilled enough at what you do.
To me it seems like police had busted lower chain of Lapsus group who were following the script given to them. It seems that they had whole system set up, but they themselves being too immature to be competent at anything. Like using messaging system which is unsafe. Stopping hack, because they got tired. Jeez, even I know better how to evade being caught online and have more dedication to what I do than these kids were. This and that police merely released them with their ill-gotten wealth shows me that they do not have sufficient evidence and what they do have enough evidence.








BrianKrebs  Post authorMarch 27, 2022 

At least you didn’t say “escape goat”.








Up March 27, 2022 

Huh?










mycosys March 31, 2022 

Its just embarrassing for the entire IT industry that you call these teenage scammers/social engineers ‘hackers’ let alone ‘experienced’ and  ‘highly sophisticated’ ‘hackers’. You haven’t detailed anything that could be remotely described as a hack.
I feel shame for every competent hardware hacker in history.






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






