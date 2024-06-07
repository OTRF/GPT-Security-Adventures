# Reference for threat actor for "APT 19, Deep Panda, C0d0so0"

**Title**: Carefirst Blue Cross Breach Hits 1.1M – Krebs on Security

**Source**: https://krebsonsecurity.com/2015/05/carefirst-blue-cross-breach-hits-1-1m/

## Content











Carefirst Blue Cross Breach Hits 1.1M – Krebs on Security











































Advertisement


Advertisement

























Skip to content

HomeAbout the Author
Advertising/Speaking







Carefirst Blue Cross Breach Hits 1.1M










May 21, 2015


60 Comments
 




CareFirst BlueCross BlueShield on Wednesday said it had been hit with a data breach that compromised the personal information on approximately 1.1 million customers. There are indications that the same attack methods may have been used in this intrusion as with breaches at Anthem and Premera, incidents that collectively involved data on more than 90 million Americans.
According to a statement CareFirst issued Wednesday, attackers gained access to names, birth dates, email addresses and insurance identification numbers. The company said the database did not include Social Security or credit card numbers, passwords or medical information. Nevertheless, CareFirst is offering credit monitoring and identity theft protection for two years.
Nobody is officially pointing fingers at the parties thought to be responsible for this latest health industry breach, but there are clues implicating the same state-sponsored actors from China thought to be involved in the Anthem and Premera attacks.
As I noted in this Feb. 9, 2015 story, Anthem was breached not long after a malware campaign was erected that mimicked Anthem’s domain names at the time of the breach. Prior to its official name change at the end of 2014, Anthem was known as Wellpoint. Security researchers at cybersecurity firm ThreatConnect Inc. had uncovered a series of subdomains for we11point[dot]com (note the “L’s” in the domain were replaced by the numeral “1”) — including myhr.we11point[dot]com and hrsolutions.we11point[dot]com.
ThreatConnect also found that the domains were registered in April 2014 (approximately the time that the Anthem breach began), and that the domains were used in conjunction with malware designed to mimic a software tool that many organizations commonly use to allow employees remote access to internal networks.
On Feb. 27, 2015, ThreatConnect published more information tying the same threat actors and modus operandi to a domain called “prennera[dot]com” (notice the use of the double “n” there to mimic the letter “m”).
“It is believed that the prennera[dot]com domain may have been impersonating the Healthcare provider Premera Blue Cross, where the attackers used the same character replacement technique by replacing the ‘m’ with two ‘n’ characters within the faux domain, the same technique that would be seen five months later with the we11point[dot]com command and control infrastructure,” ThreatConnect observed in a February 2015 blog post.
Turns out, the same bulk registrant in China that registered the phony Premera and Anthem domains in April 2014 also registered two Carefirst look-alike domains — careflrst[dot]com (the “i” replaced with an “L”) and caref1rst[dot]com (the “i” replaced with the number “1”).
Additionally, ThreatConnect has unearthed evidence showing the same tactics were used on EmpireB1ue.com (note the “L” replaced with a number “1”), a domain registered April 11, 2014 (the same day as the phony Carefirst domains). EmpireBlue BlueCross BlueShield was one of the organizations impacted by the Anthem breach.



         This entry was posted on Thursday 21st of May 2015 09:03 AM 
         
A Little Sunshine Data Breaches
carefirst bluecross blueshield breach EmpireBlue BCBS breach premera prennera ThreatConnect we11point wellpoint




Post navigation
← mSpy Denies Breach, Even as Customers Confirm It
Recent Breaches a Boon to Extortionists →



			60 thoughts on “Carefirst Blue Cross Breach Hits 1.1M”		




Katrina L. May 21, 2015 

So they managed to only steal insurance ID info but not SSNs, medical information and credit card info? Sorry, that just does not sound true.








mike~acker May 21, 2015 

once again the real issue is that client computers are not required to authenticate and countersign x.509 certificates using their local copy of PGP or GnuPG.
Certificates distributed en mass by browser software makers should be accorded only marginal trust
before using a certificate for critical processing the client needs to make sure that the correct certificate is being used.
this will require a second authentication over and above the current system of Certficate Authorities.
my suggestion is that local credit unions could help with this.    then need to do it for their online banking activity anyway …
we also need to dispel the myth that PGP is too complicated for people to use.   it isn’t, particularly when properly packaged .








Fred Schlip May 21, 2015 

The problem is that end users are dumb.  No amount of authentication magic will stop stupid.








patti May 21, 2015 

Harsh.  Most folks don’t have any idea what makes the internet work.  What we need is a better system.








pboss May 22, 2015 

A better system would probably be going back to paper. But even then, people are mind-boggling stupid when it comes to challenging people trying to sneak in a building.








Mark Allyn May 22, 2015 

Once  upon a time, when I showed up at a building for a job interview, I did not know it I was even at the correct campus, let alone building as my directions in the invite mail (paper days) were poor.
When I arrived, they not only buzzed me in but all but pulled me in by the arm through the lobby and into the inner-sanctum. When we found out that I was in the wrong building, they did not bother to escort me back out but to point through the window to the building I was supposed to go to.
Please, folks, check me out before pulling me in by the arm into the wrong building and please do not leave me standing there, but escort me to the correct place.
Now, these types of errors are not  unique to now. They happened throughout the ages!








Markus May 24, 2015 

I have a friend who was a teacher at a school. She was sitting in the staff room doing some work when an IT guy came in to take some of the laptops away to ‘service’ them. She even had a chat with him for a while. It wasn’t until after he left that another teacher came in and asked where all the computers where. Turned out he was just some guy off the street dressed like a IT professional. Doesn’t matter what safeguards you put in place, people will always be the weakest link.
















Lisa May 21, 2015 

Why don’t these companies/insurers/etc learn from each other and take steps to prevent this from happening? I understand the ‘It’ll never happen to me’ mentality to a point but c’mon people you’ve been entrusted with very valuable information and if it ever does get fully cleaned up it’ll take years!








George G May 21, 2015 

“I understand the ‘It’ll never happen to me’ mentality to a point”
I don’t.
One of the things I learned from Brian’s blog:
It is not a question of if, but when.








Dave B. May 21, 2015 

Because in order to implement what was learned they would have to spend money.








Billbo May 21, 2015 

And there’s no penalty if they leave the barn door open.










timeless May 22, 2015 

It sounds like the various health insurance breaches discussed here were carried out in parallel, we’re just learning about them serially. You can’t blame one of these companies from not learning from its peers given that they were all attacked at the same time and took over a year to analyze and report…
Also, the attacks are basically social engineering. A company can know that’s a risk, but it’s really hard to protect against that risk. I’m not sure if people were attacked only through corporate devices or also through personal ones, if the latter, then there’s very little the company could have done– you can’t log connections that aren’t made by your devices and aren’t made to your devices. You could ask people to review the connection log each time they connect, but people will quickly adapt to the “yeah, whatever” button.








whatever May 22, 2015 

Because the don’t care? Because these breaches won’t hurt them in any way?








Soy Tenley May 23, 2015 

Maybe it’s because the CEOs are too big for their breaches.








Leon J. May 26, 2015 

Keep in mind that it is difficult to change an environment where there are several layers, or more, of staff below the CEO.  For various reasons, they may have been deficient in providing adequate security, and now these people will feel defensive and threatened.  This situation acts as a coagulant to the change that needs to occur.  I also suspect that the threatscape now is a complex problem to comprehend for people who don’t live and breathe cyber security.  That being said, I also see the financial aspect as a valid culprit, as often times the basics get neglected in favor of landing a working product.












Christopher Karel May 21, 2015 

For anyone out there looking to avoid falling for this sort of trap:  Get a password manager.  (Lastpass, 1Pass, etc)  Modern password managers come with browser plugins that can auto-fill your credentials for the website you’re on.  They’re also not fooled by domain names that look like another.  Computers are impossible to trick with such character substitutions.  The fact that your password manager doesn’t allow you to auto-fill your credentials is an easy red flag that you’re being phished.
And that’s on top of all the other incredible security benefits a password manager provides.








markD May 21, 2015 

Any recommendations as to which pw manager to use?








JimV May 21, 2015 

+1 for LastPass — I have used it now for several years with no problems or issues, although there are a few sites where it won’t automatically fill in the blanks (likely a script being blocked by NoScript). In those instances, a right-click in the UI/PW boxes brings up a window from which a LP instruction can be issued, so it’s not a big deal.








Jon Marcus May 21, 2015 

I’ve been happy with LastPass so far. (Had it for a few years now.)








Christopher Karel May 21, 2015 

I’m personally a fan of LastPass (https://lastpass.com/) because it’s the easiest to setup and use.  The notable downside is that the data is stored (encrypted) on LastPass’ servers.  Creating a significant and obvious target for hackers.
But in my experience, it’s hard enough getting people started at all.  So the additional overhead of having to configure separate backup/synchronization for other solutions is just too much.








Andrew Rossetti May 21, 2015 

LastPass, without any hesitation.  Been using it for years (premium version).  Well worth $1 per month.








KT May 21, 2015 

There are several to choose from, but I landed on SafeInCloud.  Works on Android, IOS, and Windows.








Fred Schlip May 21, 2015 

Except now you are giving the exact tools to hackers.  What happens when malware running on your endpoint harvests your password locker?
Now it knows not only your password, but what site it is associated with.










Ian McKenzie May 21, 2015 

I use LastPass premium across all my devices in addition to enabling two-factor auth on every service that offers it.








patti May 21, 2015 

Adding complexity doesn’t necessarily solve a problem and can create new ones.  Any time you use the cloud, you risk everything.








John B May 21, 2015 

Lastpass is by far the best in terms of ease of use and methods they use to protect your security.








Buddha Chris May 22, 2015 

Lastpass +1 (WITH TWO-FACTOR AUTHENTICATION), and it should force you to log in each time you start the browser. For sensitive sites it should not auto-log in but force you to re-enter the pass phase. For your sensitive sites, it should be set to prompt for the password to review the clear text version of it.
The issue here is if your computer gets pwnd, and your Lastpass is set to auto-everything then all your passwords can be sucked down in a single gulp and in some ways it’s just as bad or worse then using the same passwords on all sites. The best part is I as an attacker now have a list of all the sites your on. So password repositories can be a two-edged sword.
Some sites like your bank, brokerage or other sensitive accounts should have a solid pass phase in your human storage unit only.
Lastpass is AWESOME, but even great tools can be misused or mis-configured.












CNorm May 22, 2015 

To all who are suggesting auto-fill from a password manager is a good feature, remember that this is a heavy tradeoff: https://www.schneier.com/blog/archives/2014/09/security_of_pas.html
Password safety is a little bit difficult, and requires discipline to stay ahead of the curve, but consider the information your password safeguards (card #s, address, retirement info, etc.).
Fred Schlip is right, and keep in mind coffee shop landing pages can be configured to grab all of your passwords without you even knowing it.
A password manager, however, is basically a prerequisite for safer online commerce. I use KeePass without any plugins, copy and paste works just fine (KeePass clears your clipboard after a user-configurable delay).








Yair May 22, 2015 

I’m surprised not a word has been said about strengthening user awareness to Phishing attacks.
There are  some very powerful Phishing Simulation tools available today that empower CISOs to effectively manage their organization’s susceptibility to Phishing attacks.










Ed May 21, 2015 

In my experience, it’s not just the “it won’t happen to me/us” mentality, it’s also the fact that many of these organizations are penny wise and dollar foolish when it comes to managing IT security. Throw in the sophistication of the attacks, not to mention that the only “ethic” the fraudsters have is that they have none…these will continue to promulgate.
Consider healthcare in the US. It is the most heavily regulated industry in the country by far. In fact, it’s so heavily regulated, you have parts of one law literally contradicting the parts of another law. For example, federal laws are requiring the open sharing of patient information between various electronic health Record (EHR) software vendors. On the surface, the reasons are pure. If, for example, your EHR records are present at a facility which is managed by Allscripts EHR software, and you have a health emergency, and you wind up in a hospital managed by Epic’s EHR, there could be gaps in your care unless the hospitals can seamlessly share your medical information. The problem is, this very concept flies in the face of federal HIPAA laws. Not to mention, how do you protect those sensitive communications from breaches….if what’s going on is any indication, you will be hard-pressed. So, here’s one example where it can be argued federal laws are contradicting each other. This is a very real problem for healthcare IT departments to deal with. What does this mean to a fraudster? Opportunity, my friends, opportunity.








markD May 21, 2015 

One wonders how it is that the other blues around the country, all pretty much related in the same way the baby bells are, don’t immediately know to take steps after hearing about Anthem.








Ed May 21, 2015 

It is entirely possible that they WERE taking those steps. The Anthem breach without question exposed certain vulnerabilities. So, let’s say BCBS saw this and said…”oh wow, that could happen to us. The logistics of having to identify the issue throughout hosts of servers and endpoints, identifying the best remedy, identifying the vendor from which to purchase it or developing it on your own, installing it, getting it to mesh with existing software, rolling it out to thousands of endpoints, etc. and so on. I don’t know for sure that BCBS did, in fact, recognize the issue and try to prevent, but even if they did, it’s not always as simple as downloading a patch. Believe me, hackers know this.








markD May 21, 2015 

Here’s some folks offering a start.
http://www.darkreading.com/radio.asp?webinar_id=194&cid=DRRS03_0602&gateway_return=true










Rob May 22, 2015 

This looks like it was discovered as part of CareFirst’s response to the Anthem attack. The statement from CareFirst that Brian linked to, states “This was discovered as a part of the company’s ongoing Information Technology (IT) security efforts in the wake of recent cyberattacks on health insurers.” 
The breach happened in June 2014,  long before the Anthem attack had been discovered/announced. So I don’t think it’s fair to imply that they didn’t learn from the Anthem attack.










Blanche Dubois May 21, 2015 

Brian
Has there been any discussion/serious speculation on the reasons why a state actor would work over months to penetrate US large medical insurers or administrators? 
What’s the material direct or indirect national interest to them from stealing this data? 
I can understand a state actor targeting a large US defense contractor (get F-35 blueprints/avionics suit, nuke weapon miniaturization, etc). 
Stealing medical access credentials makes sense for a private enterprise criminal group for resale to those without US medical insurance (uninsured citizens, illegal aliens, etc.) Millions of potential sales there. 
Insert spies with US credentials?
Or are these attacks considered training exercises to raise/test skills at the high school level, in prep for the serious stuff?
(Will presume the state actors have bigger objectives here than just embarrassing private US firms.)
What are the announced reasons on the US side for the attacks on health insurer’s?








wiredog May 22, 2015 

There’s a blackmail potential.  You have AIDS, or Herpes, or some other disease that carries a social stigma, especially in a more conservative place. Or maybe a past mental health issue. One day you get the call “Start feeding us information or we’ll tell your co-workers|neighbors|parents” about it.  
The security clearance process is often looking for people who are blackmail or bribery risks.  Which is why I put everything that got me into AA down on the SF-86, even though I probably didn’t have to.  If some Chinese agent comes to me and says “Tell us all your secrets or we’ll tell your friends|employers|family you’re a former crack dealer” I can reply “They already know” and call the security hotline.  Only downside is, I can never work a DEA contract.








Lee Church May 24, 2015 

RE: decouple the ‘why’ from likelihood of the ‘what’ (probability of  event does not depend on our understanding of why an event happens)
As human beings we try to make sense of the world.  In doing so, we often fall to a mental error of requiring the ‘why’ before we can accept the ‘what’.  In general, just because the ‘why’ of something is not understood should not influence our assessment of the probability of a scenario.  In other words, our own understanding does not make the ‘what’ more or less likely.
I often hear folks discuss the ‘why’ as a modifier to the likelihood of an event, and it’s a huge logical mistake.  It’s whether it’s possible and the consequences, not whether we understand ‘why’ it would happen.  Coupling them basically multiplies the odds of the event and our understanding, making the result even less clear.
Brian Krebs  has succumbed to this error as well (notably in his NK attribution posts), so it’s by no means a rare mistake.  Our analysts missed 9/11 in part due to dismissing an event because it had no known ‘why’ answer to why would anyone want to do such a thing.
A corollary to demanding ‘why’ to accept ‘what’ is that we are also tricked by a false ‘why’.  Once we think we understand ‘why’ we assign a greater likelihood to the event, even if the ‘why’ is false. We all know people who just want an answer, and any answer is fine with them.. but until they get an answer they are not satisfied.  So another exploitation is to present a false but plausable ‘why’ and it leads to errors on the flip side, or over estimating likelihood.
So please folks, particularly Infosec and security people, when you find yourself giving up on a scenario because of lack of clarity on ‘why’, resist the natural human urge to dismiss a probability of the event, particularly if the consequence of the event is large or unknown.  And when we think we know ‘why’, remember we can be wrong as much, if not more than if we don’t know ‘why’ at all.
Sometimes, the ‘why’ presents itself much later after an event… and sometimes never.  This is the nature of tail event risks and I would suspect that most tail events have the ‘it could not have been otherwise’ though pre-event analysis never sees it coming.
One final thought for those that are interested.  When the ‘black hats’ know folks dismiss events that have no readily answerable ‘why’, they can design events that exploit that behavior.  So it’s up to the Infosec and security folks to make sure we take away that bit of human behavior exploitation.
anyway, hope this was of use.
regards








Soy Tenley May 25, 2015 

“Why” reminds me of little kids, and of the character Mindy in the Animaniacs cartoons. From Wikipedia :
Often she would try asking grown-ups questions, and for each answer they gave, she would ask “Why?”, get another answer, and then ask “Why?” again. Once the adult was fed up with her, she would say “Okay, I love you, bye-bye,” and leave.












Jon Marcus May 21, 2015 

Oh, Carepoint is offering free credit monitoring and ID theft prevention services? Well then it’s all okay, their customers will be completely safe.








Robert Scroggins May 21, 2015 

What happens to these companies that are breached?  Besides owning up to it and suffering loss of customers/respect, are there any penalties to which they are subject?  Some of threse companies suffer multiple breaches after the first one.  If loss of customers doesn’t have any effect on their future security posture, then perhaps a penalty would do it.
Regards,








Bill Stadler May 21, 2015 

This is what an attitude of arrogance gets you.  The mind games the execs at the Blues play with themselves is astonishing. Yes it can and does happen and we the American Health Care Consumers pay the price. They try to justify and no doubt mitigate expense by insinuating no sensitive information was obtained-ridicules. Adding insult to injury.








Neo May 21, 2015 

The saddest part about this is that most healthcare companies don’t give a dam about there IT infrastructure and just see it as an expense, and why they should dump money into “IT”  and could still get hacked. They are being careless with our information and are most likely not taking the proper precautions with our sensitive information. They would rather take a chance and possible have more money in their pockets at the end of the year, rather then invest it into solid security infrastructure. And the weakest link still is human stupidity. Can’t fix stupid.








Bob Adams, MD, MBA May 21, 2015 

These attacks are now detectable almost instantly.
Our Eagle Vision software can watch an entire BCBS database for date transfers to unauthorized locations.








Giovanni May 21, 2015 

And if the data is siphoned through a trusted channel?








Soy Tenley May 23, 2015 

But cannot detect MITM exfiltration (Man-In-The-Middle).










GPC May 21, 2015 

There’s a pretty heavy strain of “blame the victim” in the comments, as if these companies are akin to banks that left the safe door wide open, or car owners that left the keys on the driver’s seat.  Given the facts as Brian describes them, it may be unfair to assume that these companies were asleep at the security switch.  They got hacked because their employees fell victim to a phishing scheme, and once the bad guy has the credentials of a trusted user, it’s pretty close to game over.  Perhaps there’s something they could have done to prevent the bad guys from getting into the actual company network once they phished usernames/passwords (2FA springs to mind–Brian?), but getting user creds is a ticket inside, and one that might not easily be prevented through additional company-side measures.








President Donald J Trump May 21, 2015 

China  can not be trusted  !








jim May 22, 2015 

Is it not possible that a website or attack can come from a compromised device?  Or from a third party area? Or register  a domains name in another country?  Just saying, don’t look at, the attack came from China. And say they are the bad guy. That’s too simple.  It could have been a weak defense to start with.
About using a third party, for password protection, I believe, the major news services announced one had been broken into, and compromised. It may be safer to encrypt your device. But then, if you upgrade.  Did you write it all down.
And remember this, all the devices made for consumer use, phones and tablets are made in a third country, the report back, is a built in feature. But what is it reporting back?








Soy Tenley May 23, 2015 

Could be a cheap router that is compromised.










steven May 22, 2015 

China is working together with Latin America and North America as they work this region, nobody paid attention to this type of fraud, sale of information and identities. China saw a very good business, now work together and this being more effective attacks
at some point I could see the sale of information, which wanted to integrate the market, in the forums fraud,
nobody gave importance and now ranks China as it spread in North, Central America and sub America








Jim May 22, 2015 

Wouldn’t two factor authentication of prevented this or am I missing something?








timeless May 25, 2015 

I think you’re missing something. 
Think about how Remote Access Trojans work.
Imagine an employee is authorized to do certain things, and imagine someone successfully spearfishes them with the intent to deliver malware to their computer. That computer is now compromised, they get a “your session has expired” message– something that they’re used to experiencing due to company policy. They log in and receive their 2FA message. They use it to confirm their connection. The software now borrows that confirmed connection and performs the attacks and data exfiltration. (This kind of attack has been described on this blog for banking account compromises– typically payroll)
2FA isn’t a panacea. In this case, an older technology from the credit card industry is more important: atypical customer pattern detection. When I make a purchase using my credit card, my credit card issuer compares all the details of the transaction against my profile, and if the transaction isn’t a good match for my profile, or perhaps for people with similar profiles, then they either block the transaction or my account in general and contact me to explain that they’ve detected a problem. 
If the databases that the employee is authorized to access aren’t directly compromised and are capable of comparing the employee’s requests to typical requests by that employee, then they could potentially recognize a query for too much data…
The other technology that would help is really similar technology, but instead of having detection running between the users and the databases that holds the data, similar technology could run between the employees and the rest of the Internet. — unfortunately, since the Internet is moving to encrypted traffic for everything, this task is much harder, so the analysis would be mostly looking at time & date, network destination (which is a poor indicator since any network can host compromised computers), and data volume (which means that it could catch large scale leaks, but would probably miss targeted instances).










SKINET May 22, 2015 

It’s more trouble than it is worth, thanks to the law.








Igor Artimovich May 24, 2015 

It looks like that Brian worries that stolen database nevertheless  includes medical information. Yes, Brian, that’s true reason to be nervous because now all hackers know how much money was paid to your doctors for the treatment  of your acute dementia.








Itguyatl May 24, 2015 

I am just postulating here but …. Why do we think “whomever” is targeting insurance companies….??? A theory I have is that we were all supposed to get health care because the president said so. In the country where these hackers originate “” if their leader said do something they would have to.  Does anyone think we are all being compiled in a data base somewhere… I shudder to think what purpose someone could put the information too if ever they decided to.








Soy Tenley May 25, 2015 

Prior to the ACA, gaining access to all the data would give hackers and scammers information about people who actually had money to spare, the middle class and upper middle class, as low-income and no-income (poor) people would not be in those databases. A those people have little to take directly, and nothing to take remotely, they are not targets for scamming.
You have heard of the enormous number of scammer calls claiming to be with the IRS and demanding immediate payment? With fresh data – names, addresses, phone numbers – the scammers are better able to target people with threats and intimidation, through voice training, even when the targets know the IRS handles notifications by mail.
Go to the 800notes.com website and peruse the home page, or better yet, when you get any scam call, Google the CallerID number and see what appears in the search results.








Mike May 25, 2015 

“…Does anyone think we are all being compiled in a data base somewhere…”
What do you think all those massive data centers are for? What do you think Facebook is for? What do you think online advertising is for? What do you think targeted advertising is for? What do you really think all these updates are for (sercurity….lmfao)? Why do you think no one has much desire to get rid of flash or java? Why do think think websites are demading you use your real name as logins?
There are many many more…..
What would the point in any of this be if not THAT?










dbalad123 May 24, 2015 

Mandient was called in to do the post mortem of the attack. That is how they know there was no penetration of the SSN and Medical Data DBs which are separated for this very reason.
Mandient was the Security group that identified the Chinese special military group that was tasked with hacking for the country. 
As to why these insurance companies were attacked, it’s because they serve the area that includes NSA, CIA, DIA, NRO, NPIC (now geospatial) and the like. The espionage value of the data lies in gaining further access to employee accounts who work at targeted agencies through bank and medical records to see who is most susceptible for recruitment through bribes based on their lifestyle and needs.








Jayren Ho May 25, 2015 

Well then, I think the biggest immediate threat for CareFirst customers may come from phishing scams, as criminals attempt to use customers’ stolen email addresses to coax them into clicking malicious links or disclosing more sensitive data.








sydkdy June 2, 2015 

And they said, give us all your data for our wellness program and we will help you feel better, enjoy life more, be healthier.  It’s safe, it’s the right thing for you to do.  Then the evil ones came and stole the data and now they say, it’s not so bad, they don’t have all your data, just some pieces which are useless without the other pieces.   Believe in the magic, drink the kool-aid, have no fear, sleep well my friends.  TRUST ME??? REALLY!!!  What a bunch of manure.






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






