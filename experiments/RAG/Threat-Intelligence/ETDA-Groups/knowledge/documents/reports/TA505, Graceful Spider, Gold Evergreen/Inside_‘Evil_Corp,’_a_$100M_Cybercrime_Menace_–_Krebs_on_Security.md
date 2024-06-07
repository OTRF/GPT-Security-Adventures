# Reference for threat actor for "TA505, Graceful Spider, Gold Evergreen"

**Title**: Inside ‘Evil Corp,’ a $100M Cybercrime Menace – Krebs on Security

**Source**: https://krebsonsecurity.com/2019/12/inside-evil-corp-a-100m-cybercrime-menace/

## Content











Inside ‘Evil Corp,’ a $100M Cybercrime Menace – Krebs on Security











































Advertisement



Advertisement

























Skip to content

HomeAbout the Author
Advertising/Speaking







Inside ‘Evil Corp,’ a $100M Cybercrime Menace










December 16, 2019


46 Comments
 




The U.S. Justice Department this month offered a $5 million bounty for information leading to the arrest and conviction of a Russian man indicted for allegedly orchestrating a vast, international cybercrime network that called itself “Evil Corp” and stole roughly $100 million from businesses and consumers. As it happens, for several years KrebsOnSecurity closely monitored the day-to-day communications and activities of the accused and his accomplices. What follows is an insider’s look at the back-end operations of this gang.
Image: FBI
The $5 million reward is being offered for 32 year-old Maksim V. Yakubets, who the government says went by the nicknames “aqua,” and “aquamo,” among others. The feds allege Aqua led an elite cybercrime ring with at least 16 others who used advanced, custom-made strains of malware known as “JabberZeus” and “Bugat” (a.k.a. “Dridex“) to steal banking credentials from employees at hundreds of small- to mid-sized companies in the United States and Europe.
From 2009 to the present, Aqua’s primary role in the conspiracy was recruiting and managing a continuous supply of unwitting or complicit accomplices to help Evil Corp. launder money stolen from their victims and transfer funds to members of the conspiracy based in Russia, Ukraine and other parts of Eastern Europe. These accomplices, known as “money mules,” are typically recruited via work-at-home job solicitations sent out by email and to people who have submitted their resumes to job search Web sites.
Money mule recruiters tend to target people looking for part-time, remote employment, and the jobs usually involve little work other than receiving and forwarding bank transfers. People who bite on these offers sometimes receive small commissions for each successful transfer, but just as often end up getting stiffed out of a promised payday, and/or receiving a visit or threatening letter from law enforcement agencies that track such crime (more on that in a moment).
HITCHED TO A MULE
KrebsOnSecurity first encountered Aqua’s work in 2008 as a reporter for The Washington Post. A source said they’d stumbled upon a way to intercept and read the daily online chats between Aqua and several other mule recruiters and malware purveyors who were stealing hundreds of thousands of dollars weekly from hacked businesses.
The source also discovered a pattern in the naming convention and appearance of several money mule recruitment Web sites being operated by Aqua. People who responded to recruitment messages were invited to create an account at one of these sites, enter personal and bank account data (mules were told they would be processing payments for their employer’s “programmers” based in Eastern Europe) and then log in each day to check for new messages.
Each mule was given busy work or menial tasks for a few days or weeks prior to being asked to handle money transfers. I believe this was an effort to weed out unreliable money mules. After all, those who showed up late for work tended to cost the crooks a lot of money, as the victim’s bank would usually try to reverse any transfers that hadn’t already been withdrawn by the mules.
One of several sites set up by Aqua and others to recruit and manage money mules.
When it came time to transfer stolen funds, the recruiters would send a message through the mule site saying something like: “Good morning [mule name here]. Our client — XYZ Corp. — is sending you some money today. Please visit your bank now and withdraw this payment in cash, and then wire the funds in equal payments — minus your commission — to these three individuals in Eastern Europe.”
Only, in every case the company mentioned as the “client” was in fact a small business whose payroll accounts they’d already hacked into.
Here’s where it got interesting. Each of these mule recruitment sites had the same security weakness: Anyone could register, and after logging in any user could view messages sent to and from all other users simply by changing a number in the browser’s address bar. As a result, it was trivial to automate the retrieval of messages sent to every money mule registered across dozens of these fake company sites.
So, each day for several years my morning routine went as follows: Make a pot of coffee; shuffle over to the computer and view the messages Aqua and his co-conspirators had sent to their money mules over the previous 12-24 hours; look up the victim company names in Google; pick up the phone to warn each that they were in the process of being robbed by the Russian Cyber Mob.
My spiel on all of these calls was more or less the same: “You probably have no idea who I am, but here’s all my contact info and what I do. Your payroll accounts have been hacked, and you’re about to lose a great deal of money. You should contact your bank immediately and have them put a hold on any pending transfers before it’s too late. Feel free to call me back afterwards if you want more information about how I know all this, but for now please just call or visit your bank.”
Messages to and from a money mule working for Aqua’s crew, circa May 2011.
In many instances, my call would come in just minutes or hours before an unauthorized payroll batch was processed by the victim company’s bank, and some of those notifications prevented what otherwise would have been enormous losses — often several times the amount of the organization’s normal weekly payroll. At some point I stopped counting how many tens of thousands of dollars those calls saved victims, but over several years it was probably in the millions.
Just as often, the victim company would suspect that I was somehow involved in the robbery, and soon after alerting them I would receive a call from an FBI agent or from a police officer in the victim’s hometown. Those were always interesting conversations. Needless to say, the victims that spun their wheels chasing after me usually suffered far more substantial financial losses (mainly because they delayed calling their financial institution until it was too late).
Collectively, these notifications to Evil Corp.’s victims led to dozens of stories over several years about small businesses battling their financial institutions to recover their losses. I don’t believe I ever wrote about a single victim that wasn’t okay with my calling attention to their plight and to the sophistication of the threat facing other companies.
LOW FRIENDS IN HIGH PLACES
According to the U.S. Justice Department, Yakubets/Aqua served as leader of Evil Corp. and was responsible for managing and supervising the group’s cybercrime activities in deploying and using the Jabberzeus and Dridex banking malware. The DOJ notes that prior to serving in this leadership role for Evil Corp, Yakubets was also directly associated with Evgeniy “Slavik” Bogachev, a previously designated Russian cybercriminal responsible for the distribution of the Zeus, Jabber Zeus, and GameOver Zeus malware schemes who currently has a $3 million FBI bounty on his head.
Evgeniy M. Bogachev, in undated photos.
As noted in previous stories here, during times of conflict with Russia’s neighbors, Slavik was known to retool his crime machines to search for classified information on victim systems in regions of the world that were of strategic interest to the Russian government – particularly in Turkey and Ukraine.
“Cybercriminals are recruited to Russia’s national cause through a mix of coercion, payments and appeals to patriotic sentiment,” reads a 2017 story from The Register on security firm Cybereason’s analysis of the Russian cybercrime scene. “Russia’s use of private contractors also has other benefits in helping to decrease overall operational costs, mitigating the risk of detection and gaining technical expertise that they cannot recruit directly into the government. Combining a cyber-militia with official state-sponsored hacking teams has created the most technically advanced and bold cybercriminal community in the world.”
This is interesting because the U.S. Treasury Department says Yukabets as of 2017 was working for the Russian FSB, one of Russia’s leading intelligence organizations.
“As of April 2018, Yakubets was in the process of obtaining a license to work with Russian classified information from the FSB,” notes a statement from the Treasury.
The Treasury Department’s role in this action is key because it means the United States has now imposed economic sanctions on Yukabets and 16 accused associates, effectively freezing all property and interests of these persons (subject to U.S. jurisdiction) and making it a crime to transact with these individuals.
The Justice Department’s criminal complaint against Yukabets (PDF) mentions several intercepted chat communications between Aqua and his alleged associates in which they puzzle over why KrebsOnSecurity seemed to know so much about their internal operations and victims. In the following chat conversations (translated from Russian), Aqua and others discuss a story I wrote for The Washington Post in 2009 about their theft of hundreds of thousands of dollars from the payroll accounts of Bullitt County, Ky:
tank: [Are you] there?
indep: Yeah.
indep: Greetings.
tank: http://voices.washingtonpost.com/securityfix/2009/07/an_odyssey_of_fraud_part_ii.html#more
tank: This is still about me.
tank: Originator: BULLITT COUNTY FISCAL Company: Bullitt County Fiscal Court
tank: He is the account from which we cashed.
tank: Today someone else send this news.
tank: I’m reading and thinking: Let me take a look at history. For some reason this name is familiar.
tank: I’m on line and I’ll look. Ah, here is this shit.
indep: How are you?
tank: Did you get my announcements?
indep: Well, I congratulate [you].
indep: This is just fuck when they write about you in the news.
tank: Whose [What]?
tank: 😀
indep: Too much publicity is not needed.
tank: Well, so nobody knows who they are talking about.
tank: Well, nevertheless, they were writing about us.
aqua: So because of whom did they lock Western Union for Ukraine?
aqua: Tough shit.
tank: *************Originator: BULLITT COUNTY FISCAL Company: Bullitt
County Fiscal Court
aqua: So?
aqua: This is the court system.
tank: Shit.
tank: Yes
aqua: This is why they fucked [nailed?] several drops.
tank: Yes, indeed.
aqua: Well, fuck. Hackers: It’s true they stole a lot of money.
At roughly the same time, one of Aqua’s crew had a chat with Slavik, who used the nickname “lucky12345” at the time:
tank: Are you there?
tank: This is what they damn wrote about me.
tank: http://voices.washingtonpost.com/securityfix/2009/07/an_odyssey_of_fraud_part_ii.html#more
tank: I’ll take a quick look at history
tank: Originator: BULLITT COUNTY FISCAL Company: Bullitt County Fiscal Court
tank: Well, you got [it] from that cash-in.
lucky12345: From 200K?
tank: Well, they are not the right amounts and the cash out from that account was shitty.
tank: Levak was written there.
tank: Because now the entire USA knows about Zeus.
tank: 😀
lucky12345: It’s fucked.
On Dec. 13, 2009, one of the Jabberzeus gang’s money mule recruiters –- a crook who used the pseudonym “Jim Rogers” — somehow learned about something I hadn’t shared beyond a few trusted friends at that point: That The Washington Post had eliminated my job in the process of merging the newspaper’s Web site (where I worked at the time) with the dead tree edition. The following is an exchange between Jim Rogers and the above-quoted “tank”:
jim_rogers: There is a rumor that our favorite (Brian) didn’t get his contract extension at Washington Post. We are giddily awaiting confirmation 🙂 Good news expected exactly by the New Year! Besides us no one reads his column 🙂
tank: Mr. Fucking Brian Fucking Kerbs!
In March 2010, Aqua would divulge in an encrypted chat that his crew was working directly with the Zeus author (Slavik/Lucky12345), but that they found him abrasive and difficult to tolerate:
dimka: I read about the king of seas, was it your handy work?
aqua: what are you talking about? show me
dimka: zeus
aqua: 🙂
aqua: yes, we are using it right now
aqua: its developer sits with us on the system
dimka: it’s a popular thing
aqua: but, he, fucker, annoyed the hell out of everyone, doesn’t want to write bypass of interactives (scans) and trojan penetration 35-40%, bitch
aqua: yeah, shit
aqua: we need better
aqua: http://voices.washingtonpost.com/securityfix read it 🙂 here you find almost everything about us 🙂
dimka: I think everything will be slightly different, if you think so
aqua: we, in this system, the big dog, the rest on the system are doing small crap
Later that month, Aqua bemoaned even more publicity about their work, pointing to a KrebsOnSecurity story about a sophisticated attack in which their malware not only intercepted a one-time password needed to log in to the victim’s bank account, but even modified the bank’s own Web site as displayed in the victim’s browser to point to a phony customer support number.
Ironically, the fake bank phone number was what tipped off the victim company employee. In this instance, the victim’s bank — Fifth Third Bank (referred to as “53” in the chat below) was able to claw back the money stolen by Aqua’s money mules, but not funds that were taken via fraudulent international wire transfers. The cybercriminals in this chat also complain they will need a newly-obfuscated version of their malware due to public exposure:
aqua: tomorrow, everything should work.
aqua: fuck, we need to find more socks for spam.
aqua: okay, so tomorrow Petro [another conspirator who went by the nickname Petr0vich] will give us a [new] .exe
jtk: ok
jim_rogers: this one doesn’t work
jim_rogers: http://www.krebsonsecurity.com/2010/03/crooks-crank-up-volume-of-e-banking-attacks/
jim_rogers: here it’s written about my transfer from 53. How I made a number of wires like it said there. And a woman burnt the deal because of a fake phone number.
ANTI-MULE INITIATIVE
In tandem with the indictments against Evil Corp, the Justice Department joined with officials from Europol to execute a law enforcement action and public awareness campaign to combat money mule activity.
“More than 90% of money mule transactions identified through the European Money Mule Actions are linked to cybercrime,” Europol wrote in a statement about the action. “The illegal money often comes from criminal activities like phishing, malware attacks, online auction fraud, e-commerce fraud, business e-mail compromise (BEC) and CEO fraud, romance scams, holiday fraud (booking fraud) and many others.”
The DOJ said U.S. law enforcement disrupted mule networks that spanned from Hawaii to Florida and from Alaska to Maine. Actions were taken to halt the conduct of over 600 domestic money mules, including 30 individuals who were criminally charged for their roles in receiving victim payments and providing the fraud proceeds to accomplices.
Some tips from Europol on how to spot money mule recruitment scams dressed up as legitimate job offers.
It’s good to see more public education about the damage that money mules inflict, because without them most of these criminal schemes simply fall apart. Aside from helping to launder funds from banking trojan victims, money mules often are instrumental in fleecing elderly people taken in by various online confidence scams.
It’s also great to see the U.S. government finally wielding its most powerful weapon against cybercriminals based in Russia and other safe havens for such activity: Economic sanctions that severely restrict cybercriminals’ access to ill-gotten gains and the ability to launder the proceeds of their crimes by investing in overseas assets.
Further reading:
DOJ press conference remarks on Yakubets
FBI charges announced in malware conspiracy
2019 indictment of Yakubets, Turashev. et al. 
2010 Criminal complaint vs. Yukabets, et. al.
FBI “wanted” alert on Igor “Enki” Turashev
US-CERT alert on Dridex



         This entry was posted on Monday 16th of December 2019 09:08 AM 
         
A Little Sunshine Employment Fraud Ne'er-Do-Well News Target: Small Businesses
aqua aquamo Bugat Dridex Europol Evgeniy Mikhailovich Bogachev Evil Corp. Igor “Enki” Turashev JabberZeuS luck12345 Maksim V. Yukabets money mules Slavik U.S. Justice Department U.S. Treasury Department ZeuS Trojan




Post navigation
← The Great $50M African IP Address Heist
Ransomware Gangs Now Outing Victim Businesses That Don’t Pay Up →



			46 thoughts on “Inside ‘Evil Corp,’ a $100M Cybercrime Menace”		




Jim December 16, 2019 

Biran, if we have a family member that is recruited as a money mule, is there somewhere to report it? (Like, they sign up for a work from home job, and get a letter telling them about how their job will be to ‘test wire transfers’, so they havent sent any money yet) Is that a thing to report to the local police or is there a better group to call? Thanks!








Bryan December 16, 2019 

Check out ic3.gov








Nick Hunt December 16, 2019 

In   USA there is a crime organization that has came to Power.  Those close to the situation acknowledge that there is a identity theft impersonation of billionaire dual national Towery M Burris near Charlotte  North Carolina USA that has led to the largest embezzlement in the States history. The billionaire is the dark skin beneficiary grandson of Johnny Bryan Hunt founder of J.B Hunt transportation. He was recognized in 2013 & 2014 taking the nickname J.B Hunt Jr after receiving the largest combined inheritance & Trust in modern US History involving J.P Morgan DuPont Freeman and J.B Hunt Fortunes








Brian Krebs December 17, 2019 

Please send them a copy of this story. If they still won’t listen to reason, feel free to reach out to me at krebsonsecurity @ gmail dot com.












Patricia December 16, 2019 

So, Brian — now that you’re rich, or will be soon, will you (please) NOT STOP working?  You are the top resource for understanding online criminal threats. We really need your website and list!
Take great vacations with your family. Hire some help. But please keep Krebs_on_Security up.








concernedcit December 16, 2019 

seconded with a friendly amendment – give nice gifts to your intel sources this holiday








Brian Krebs December 17, 2019 

Thank you, but as I’ve said time and again, if I ever got any kind of financial award related to one of these guys, I would give it all away to worthwhile causes in a heartbeat.








CatsAreGods December 20, 2019 

Please be careful. These guys probably have some kind of “contract” on you at this point.












True Love December 16, 2019 

“our favorite (Brian)”
They love you, Brian!








JoeHx December 16, 2019 

I have no idea what I would do if someone called me claiming to be Brian Krebs. Then again, I’m not in charge of anything financial at work, so hopefully hackers wouldn’t target me in that area.








Song Bird December 16, 2019 

Truly wonderful stuff, just wonderful.  
Except, “So, each day for several years my morning routine went as follows: Make a pot of coffee; shuffle over to the computer and . . .”.
Mr Krebs sir, I can see you kick stating on caffeine but you’re not a shuffler.  I do not click on that.








The Sunshine State December 16, 2019 

Fascinating  article  !








Car Dealer in Kansas December 16, 2019 

Good work, Brian!
This all sounds very familiar.








Sam December 16, 2019 

> On Dec. 13, 2009, one of the Jabberzeus gang’s money mule recruiters –- a crook who used the pseudonym “Jim Rogers” — somehow learned about something I hadn’t shared beyond a few trusted friends at that point
Did you ever work out how they knew this?








Required December 16, 2019 

Most likely there was an investor in the Post who was made aware of the likelihood of the merger occuring and how restructuring would occur. That person forwarded that info to someone Rogers knew or to Rogers himself.  
Another way for criminals to make money is for them to invest laundered money into legit businesses. Just look south of the US border to Mexico for that as many resort towns have businesses in them that are run and policed by drug cartels.










JCitizen December 16, 2019 

Years ago when Brian was still with the Post, I was reading local newspaper want ads for work, and saw an item that met all the factors put forth in the “Fake Job Offers” list above. I called that local paper and told them they should be careful about accepting such ads, and explained the reason why, and referenced Brian’s column in the Washington Post to help. However I was still shocked they took my word for it on the face of the matter, and took down the ad the very next day. I haven’t seen one worded the same way since.
Kudos to Brian – I can imagine how much heart ache he saved some unsuspecting “mule” in my region by helping me and the local paper recognize such advertisements.








francois December 16, 2019 

Sorry for being naive but why is it so hard to arrest these crooks since they seem to be clearly identified now?
As far as I understood, money went from a mule’s account to the crook’s account. So we know exactly where the stolen money landed and who exactly is having a great time with it. What’s even left to investigate considering these trails?








BrianKrebs  Post authorDecember 16, 2019 

Most of these guys are thought to be in Russia, which isn’t about to help the US in this case and does not extradite its own citizens. In fact, if you check out some of the recent stories here, the Russian government has been going out of their way to keep Russian hackers arrested in other countries from being extradited here. 
https://krebsonsecurity.com/2019/11/why-were-the-russians-so-set-against-this-hacker-being-extradited/








vb December 16, 2019 

It’s well known that Russia uses computer criminals for government intelligence work.
There is no way that Russia is going to extradite someone who… “as of 2017 was working for the Russian FSB, one of Russia’s leading intelligence organizations.”










Beeker25 December 18, 2019 

We don’t have a extradition treaty with Russia and won’t get their help even if we identified them.  The only way we can get them is  when they go to countries where we have such treaty.










Mckee December 16, 2019 

Very interesting article! Thanks








Sinclair December 16, 2019 

The “Evil Corp” thing is hilarious to me. It’s like they decided to be real-life supervillains and you’re a real-life superhero.








BrianKrebs  Post authorDecember 16, 2019 

I don’t know about the latter half of your statement, but these guys are indeed real-life, modern-day supervillains. To quote someone else, they are the “force multipliers” of cybercrime, in that they tend to create, manage, and market much of the machinery that makes it easier for others to follow in their footsteps.








The Sunshine State December 17, 2019 

A “megalomaniac” is a pathological egotist, that is, someone with a psychological disorder with symptoms like delusions of grandeur and an obsession with power. We also use the word megalomaniac more informally for people who behave as if they’re convinced of their absolute power and greatness.












Dennis December 16, 2019 

This part shows how dumb some of those companies are – 
“Just as often, the victim company would suspect that I was somehow involved in the robbery, and soon after alerting them I would receive a call from an FBI agent or from a police officer in the victim’s hometown.”
So knowing that about 50% of those dummies will do this, are you still willing to alert companies in the future like you did, Brian?
PS. It takes only one Google search to know who he is before calling FBI on him. Just pisses me off. I’ve been in those shoes myself.








BrianKrebs  Post authorDecember 16, 2019 

It’s just human nature. Also, in many cases I had no way of knowing whether the victim company was already aware of the robbery, because even when I suspected they were aware they very rarely let on. Think of it this way: You walk into your house and your locked safe with all your prized possessions is gone. Then someone calls and says, hey it looks like you might be missing a safe. How would you react? 
I never faulted victims for reacting poorly. I usually had too many notifications to do each day, and time was of the essence in each case. If my warnings helped, great. If not, no skin off my back. And I genuinely enjoyed the calls from FBI and local PDs. It often gave me a chance to educate these people on a class of crimes that simply weren’t on their radar at all.








Dennis December 17, 2019 

Yes, I hear you. Many people usually overreact and grab the “good” guy in the heat of the moment. Also those companies that got breached probably lack any good online awareness (by definition) to Google your name before calling police on you. So I get that part. 
Although I wouldn’t be as cavalier about talking to PDs & FBI. Sure, your local PD probably knows you, but what if some PD in Brambles, KS decides to add you to some government blacklist simply because they failed to do a diligent check or if you missed their call. I wouldn’t be playing with that. 
Also any security researcher that doesn’t have an online presence as you might be at a risk of mis-identification as a bad guy here.










J. December 17, 2019 

When people get scammed, it’s also common for someone else to come along and scam them again by pretending to be someone helping clean up the first mess. So in a way companies responding like this are actually being properly shrewd.
I’ve read that scammers even share lists of marks, so once scammer #1 has successfully victimized someone, scammer #2 knows the person was had and is likely to fall for another scam.










P Pedersen December 17, 2019 

In Denmark even youngsters are using “mule”. 12 y.o. can get a card. They they will use a stolen phone/credentials to transfer money to a school kid, who will then use his debit card to cash out in the local supermarket. Small amounts. $250 max.
So even small scale criminals are using mules to empty accounts/stolen phones with weak password on money transfers.
In Denmark everybody from age 14 has MobilePay. Mobile money transfers. Cash is getting rare, so even beggars needs to accept MobilePay these days.








PattiM December 17, 2019 

Very interesting – this is almost the definition of breakdown of the financial system.








Beeker25 December 18, 2019 

Many banks are pushing to utilize mobile pay rather cash hence the reason why cash usage is down.  US is still behind the curve when it comes to financial transactions because of the use of checks (those paper).
My favorite story is when an employee from EU transferred to the US, she was shocked to see that she had to open a checking account and use a check something she can get it done by phone in EU. The bank employees marveled that she has to learn how to write a check.












manvee December 17, 2019 

Very interesting ! Keep continue the great articles.
Thank you.








Todd December 17, 2019 

Great article! You need to write another book with stories of all the examples. I’d love to read the beginning to end and what happened (how you/others foiled the caper). Would also enjoy reading more about you notifying companies, their reactions and the interaction with police/FBI…those real life stories would be great in a book….just sayin.








Dana December 17, 2019 

Very insightful Brian.  Keep up with the good work; exposing these little low life rats!!!








Notme December 17, 2019 

Always exceedingly interesting,  and always the best written security information available.   Thanks for your diligence!








Readership1 December 18, 2019 

BK epitaph when he’s 120 years old… son, father, husband, writer, harbinger of doom…
Lolol








Andre December 18, 2019 

I would recommend you Brian to write an E-Book with all of these great articles of yours. It would be very interesting. Im a reader of your Website for weeks, and i really do enjoy your articles. Keep doing such a grat job.
Best regards








JFYI December 18, 2019 

It’s hard to have something called Evil Corp mentioned without namechecking MR ROBOT.
I’m sure it’s face value, but Mr. Robot is focused on the takedown of Evil Corp…
(If any reader hasn’t watched this series… it contains one of the most realistic depictions of hacking seen to date on network TV)








rod December 18, 2019 

Here you got the best clue to russias involvement:
https://krebsonsecurity.com/2019/11/why-were-the-russians-so-set-against-this-hacker-being-extradited/
It’s blatant to me…the whole cybercrime was a reaction of the cold war’s ending 1990. I saw russians offer courses in ebay scamming for nigerian fraudsters in 2004: 5k$ for 1 week course in moscow…I saw the nigerians buy flights and pay for the course 😉








Daniel M. December 18, 2019 

What a great job you have made for yourself. I graduated a few years ago with a 4 year degree in cyber security and counter-terrorism, and I have learned more about “real world” issues from reading your blog than my 4 years of school. I also follow Kevin Mitnick and his exploits…. and I remember there was a day when I was war-dialing with ToneLoc and a modem because the movie “Wargames” was my inspiration… ok… so I was a nerd and didn’t have much of a social life…. please keep doing what you are doing…. and thank you!








Beeker25 December 18, 2019 

Great job in how you were able to watch them in real time to call the victim to warn them before it happens.








PostToaster December 19, 2019 

Where is Hitler when we need him?








Dave Watt December 22, 2019 

What’s to keep the mule from just grabbing the cash and closing their own account?








Matrix3D December 23, 2019 

This is some next level fraud. How does someone escape with all that?








Matrix3D December 23, 2019 

Amazing article, you should try posting about the effects of AI and what the pros and cons we’ll have to face.








Frank Alpha January 2, 2020 

Brian Fucking Kerbs? I’d so have a name plate made of that and send it to these dudes at the FSB. 
Kind of funny though, usually they’re not as sloppy as say GRU and their various tentacles, and of course there’s SVR (especially their Zaslon SMU) and Spetssyvaz and they rarely, if ever, get caught.






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






