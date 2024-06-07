# Reference for threat actor for "Mummy Spider, TA542"

**Title**: Secret Service Investigates Breach at U.S. Govt IT Contractor – Krebs on Security

**Source**: https://krebsonsecurity.com/2019/09/secret-service-investigates-breach-at-u-s-govt-it-contractor/

## Content











Secret Service Investigates Breach at U.S. Govt IT Contractor – Krebs on Security











































Advertisement


Advertisement

























Skip to content

HomeAbout the Author
Advertising/Speaking







Secret Service Investigates Breach at U.S. Govt IT Contractor










September 9, 2019


56 Comments
 




The U.S. Secret Service is investigating a breach at a Virginia-based government technology contractor that saw access to several of its systems put up for sale in the cybercrime underground, KrebsOnSecurity has learned. The contractor claims the access being auctioned off was to old test systems that do not have direct connections to its government partner networks.
In mid-August, a member of a popular Russian-language cybercrime forum offered to sell access to the internal network of a U.S. government IT contractor that does business with more than 20 federal agencies, including several branches of the military. The seller bragged that he had access to email correspondence and credentials needed to view databases of the client agencies, and set the opening price at six bitcoins (~USD $60,000).

A review of the screenshots posted to the cybercrime forum as evidence of the unauthorized access revealed several Internet addresses tied to systems at the U.S. Department of Transportation, the National Institutes of Health (NIH), and U.S. Citizenship and Immigration Services (USCIS), a component of the U.S. Department of Homeland Security that manages the nation’s naturalization and immigration system.
Other domains and Internet addresses included in those screenshots pointed to Miracle Systems LLC, an Arlington, Va. based IT contractor that states on its site that it serves 20+ federal agencies as a prime contractor, including the aforementioned agencies.
In an interview with KrebsOnSecurity, Miracle Systems CEO Sandesh Sharda confirmed that the auction concerned credentials and databases were managed by his company, and that an investigating agent from the Secret Service was in his firm’s offices at that very moment looking into the matter.
But he maintained that the purloined data shown in the screenshots was years-old and mapped only to internal test systems that were never connected to its government agency clients.
“The Secret Service came to us and said they’re looking into the issue,” Sharda said. “But it was all old stuff [that was] in our own internal test environment, and it is no longer valid.”
Still, Sharda did acknowledge information shared by Wisconsin-based security firm Hold Security, which alerted KrebsOnSecurity to this incident, indicating that at least eight of its internal systems had been compromised on three separate occasions between November 2018 and July 2019 by Emotet, a malware strain usually distributed via malware-laced email attachments that typically is used to deploy other malicious software.
The Department of Homeland Security did not respond to requests for comment, nor did the Department of Transportation. A spokesperson for the NIH said the agency had investigated the activity and found it was not compromised by the incident.
“As is the case for all agencies of the Federal Government, the NIH is constantly under threat of cyber-attack,” NIH spokesperson Julius Patterson said. “The NIH has a comprehensive security program that is continuously monitoring and responding to security events, and cyber-related incidents are reported to the Department of Homeland Security through the HHS Computer Security Incident Response Center.”
One of several screenshots offered by the dark web seller as proof of access to a federal IT contractor later identified as Arlington, Va. based Miracle Systems. Image: Hold Security.

The dust-up involving Miracle Systems comes amid much hand-wringing among U.S. federal agencies about how best to beef up and ensure security at a slew of private companies that manage federal IT contracts and handle government data.
For years, federal agencies had few options to hold private contractors to the same security standards to which they must adhere — beyond perhaps restricting how federal dollars are spent. But recent updates to federal acquisition regulations allow agencies to extend those same rules to vendors, enforce specific security requirements, and even kill contracts that are found to be in violation of specific security clauses.
In July, DHS’s Customs and Border Patrol (CPB) suspended all federal contracts with Perceptics, a contractor which sells license-plate scanners and other border control equipment, after data collected by the company was made available for download on the dark web. The CPB later said the breach was the result of a federal contractor copying data on its corporate network, which was subsequently compromised.
For its part, the Department of Defense recently issued long-awaited cybersecurity standards for contractors who work with the Pentagon’s sensitive data.
“This problem is not necessarily a tier-one supply level,” DOD Chief Information Officer Dana Deasy told the Senate Armed Services Committee earlier this year. “It’s down when you get to the tier-three and the tier-four” subcontractors.



         This entry was posted on Monday 9th of September 2019 12:47 PM 
         
Data Breaches
Dana Deasy Emotet Hold Security Julius Patterson Miracle Systems LLC National Institutes of Health Perceptics Sandesh Sharda U.S. Citizenship and Immigration Services U.S. Department of Homeland Security U.S. Department of Transportation U.S. Secret Service




Post navigation
← ‘Satori’ IoT Botnet Operator Pleads Guilty
Patch Tuesday, September 2019 Edition →



			56 thoughts on “Secret Service Investigates Breach at U.S. Govt IT Contractor”		




Matthew Kramer September 9, 2019 

Cobalt Strike – nice.








Joe September 9, 2019 

Suspiciously included in a screenshot… probably trying to seem legit by casually showing that.  That makes me think they don’t have good, up to date, information.  It seems desperate, like “look, I’m a leet hax0r”.










Neil September 9, 2019 

Does anyone believe it was only old stuff?








Joe September 9, 2019 

Yes.  Absolutely.
99% of the data out there is “old stuff”.  Because as companies at least try to practice good cyber security… they won’t go back and scrub the old data from where the reside…. much easier to just change passwords than to scrub the entire environment of any existence of the old credentials.








ASB September 11, 2019 

All it takes is for ONE of the credentials to be valid.
Frankly, in my experience, I’ve seen *test* credentials have much longer shelf life than production creds.
Consider this: in this case, according to the CEO, it is the test environment that has been breached.  This lends more credence to the fact that less security is applied there than in the production environment, which means that it is more likely that the creds still work.
Maybe they won’t easily lead to access to production or maybe they will, but the idea that better security hygiene is being performed in that environment is undermined by the mere fact of its breach.








Joe September 11, 2019 

Agreed.  But if we accept that the CEO was right about these creds being for a test environment… we also should accept what he says about them being invalid, “and it is no longer valid.”
Even if they did miss something years ago, best believe they are going back to ensure that everything had been changed since that screenshot.












ASB September 11, 2019 

>Does anyone believe it was only old stuff?
No.  Not from what I have seen across dozens of environments, in multiple industries, whether large or small.










vb September 9, 2019 

There is plenty of good information on most test systems.  Dismissing the importance of the data because it is test data is poor thinking.
Also, given the glacial pace of most federal government departments and agencies, even years-old data is still good data.
Another instance of a corporate breach response consisting of “hide and minimize”.








Joe September 9, 2019 

True.  Service accounts and database credentials are usually the last to be rotated, if ever.  So it is definitely true that “old data” or credentials on “test systems” are still very valuable…
The key phrase is “it is no longer valid.”  Which suggests that these credentials are no longer going to work even for test systems.
I certainly don’t fully trust the CEO who has every incentive to “hide and minimize” the breach.  But he would be very stupid to outright lie, since the investigation will find this out.  The reputational hit will be detrimental and may sink the company.
On the other hand… the anonymous “dark web seller” has every incentive to lie.
No real world consequences for exaggerating the loot.  Some sucker could pay 6BTC (~$60,000) and this guy is gone.  There isn’t much honor in thieves.
So it comes down to, who are you going to believe more.  The CEO who may lose his company for lying to federal investigators?  Or some anonymous guy on the dark web?








tim September 10, 2019 

like the ceo isn’t going to lie. we live in the real world joe. i trust the hackers more in this case because now they have the test systems and know how the real systems are designed. too easy to get in now, using the old framework as leverage, then pivoting for persistence and system level access. hell, if i had permission i could probably get in in about an hour. to the gov’s sites, not this 3d party’s, using the screenshots and linkedin. and i am not even a leet haxor.








Joe September 10, 2019 

Oh the arrogance.
Sure, test systems do provide insight into an environment.  Depending how old it is, it could resemble the real network.  Then again, it may not.  But this guy isn’t selling a detailed network diagram.  He is selling credentials that are old and probably won’t work.  Those credentials were probably rotated years ago.
The CEO is not anonymous, and faces severe consequences for lying.  Yeah, he might lie.  That’s the real world.
But you are naive to trust some rando dude on the dark web just because he shows a screenshot and demands $60,000.
A sucker is born every minute, and this guy is going to get away with selling a box of old crap, and then move along.
Do you really think a criminal who is fine at hacking and stealing, draws the line at lying to people?
Haha… naive suckers every minute.  He’ll probably get his Bitcoin, because someone like you will buy his fake warez.








Internet Achievement Unlocked! September 10, 2019 

Congratulations on your Internet Achievement, Joe! With the powers vested in me, I hereby award you with two Internet Achievement Medals:
  – 1 Platinum medal:  “Mr. Argumentative”
  – 1 Gold medal with Silver Star:  “Ad Hominem Champ” 
Keep up the great work, Joe! You are doing the internet a service with constant arguments and unnecessary ad hominem attacks on strangers on our dear internet.
–Internet Medal Hander-Outter Extraordinaire 2.0








Joe September 10, 2019 

Who was the ad hominem attack against exactly?  The anonymous hacker selling invalid creds… or the anonymous commentator who made the claim of being able to get into government systems within an hour?
Perhaps the high and mighty (and sarcastic) should look up what an ad hominem attack really means.














DefenseContractorsLie September 26, 2019 

Not sure about where you live, but from what I’ve seen defense contractors lie more than the sleaziest of used car salesmen and never seem to suffer any repercussions.  I wish the feds would investigate some of these companies inside and out.










Tony September 10, 2019 

I agree.  Our test system is typically a periodic snapshot of our production system.  While the credentials differ, the goodies in the data are real and valuable.








Joe September 10, 2019 

But only the credentials are for sale… so even if there is value in the test environment… that isn’t for sale.
It’s like buying “a chance to win”.  They are nearly always a scam.  If these creds don’t work, and they probably don’t…. then there is very little value.












Small Victory September 9, 2019 

I’m hoping somebody on that criminal forum paid the ~$60k to have access to all of that information, but the admin saw this article and changed the passwords forcing them to be out ~$60k now.








The Sunshine State September 9, 2019 

More  Russian  wannabe   “script kiddies”    with  Asperger’s  who will get caught  due to a lack of good  OPSEC? 
Stay  tuned !








Joe September 9, 2019 

Looks like you are getting your articles confused.
People running botnets, or active campaigns have to continuously practice good OPSEC to avoid getting caught.
People who hack once and just sell breach data on the dark web don’t get caught very often.  They don’t really have to stay active, and being one seller is MUCH easier to manage anonymously compared to running the store or service.
Also, why would anyone in Russia try to claim Asperger’s?  They just have to be Russian, and avoid attacking any political allies.  They won’t be prosecuted.








The Sunshine State September 10, 2019 

You didn’t know ” Asperger’s” is the  go to excuse  for cyber-criminals  LOL
Miscreants  in Russia  do get caught  and are extradited back  to the United  States for prosecution.








Joe September 10, 2019 

Who “in Russia” has been extradited?
Are you talking about the russian guy who was arrested and extradited from Czech Republic to the US?  Russia tried to fight it.
Go ahead, name all the hackers who have used Asperger’s as a defense.  It’ll be counted on one hand.










Matt Parkes September 10, 2019 

I think Sunshine State  was being sarcastic, not literal in their comment – all you ever hear when reading articles about perpetrators of cyber crime getting caught is that it was some particular nation state backed group or it was some teenage kid in their bedroom who is super intelligent and bored because they have autism or some form of learning disability which makes them socially awkward or unacceptable in their own eyes.








Joe September 10, 2019 

“all you ever hear when reading articles”
Sounds like a case of observer bias.  
Mostly it is the comment section that focuses and exaggerates these claims that so many hackers are using Asperger’s as a defense.












Assburger September 10, 2019 

Haha…Good one!










Roger Nebel September 9, 2019 

The move to hold federal contractors to the same standard is hardly recent or new – it was literally years in the making and has been in place for at least two years.  A Federal Record entry of proposed contract changes, testimony, proposed standards at NIST, etc., led to additions to the standards from NIST to all DoD contracts.  NIST SP 800-171.








Roger Nebel September 9, 2019 

I should have said all DoD contractors…Federal Executive branch contracts may be different
https://www.nist.gov/mep/cybersecurity-resources-manufacturers/dfars800-171-compliance








ChrisSuperPogi September 10, 2019 

This comment may be outside of this loop but wouldn’t this be covered under DFARs compliance?
I know DFARs refers to acquisition requirements but speculate that the standards demands that contractors (and suppliers) meet higher security standards than we I am seeing on the screen shot.
Hence, my question…








Scott D. September 10, 2019 

NIST SP 800-171 R1 is referenced by DFARS 252-204-7012 (b)…
This only comes into play if a subcontractor  is provided with Controlled Unclassified Information (CUI). Go to the NARA (National Archives) site and check out ISOO and CUI for more details.
The roll out of SP 800-171 had a compliance deadline of 31 Dec 2017 however significant portions of the documentation were not published until well after that deadline (ie NIST SP 800-171A , etc) that would have allowed (at least in my view) a much greater understanding of the compliance requirements.








Roger Nebel September 11, 2019 

The definition of CUI is very soft at best, any data that the government gives you, or that you collect on their behalf is thought to be CUI and warrants protection.  In any case, organizations that may have CUI need to define and treat accoringly.
https://www.fifthdomain.com/dod/2019/09/10/what-does-state-of-the-art-cybersecurity-look-like-to-the-pentagon/?utm_source=Sailthru&utm_medium=email&utm_campaign=Fifth%20Daily%2009.11.19&utm_term=Editorial%20-%20Daily%20Brief
















Tim McSweeney September 9, 2019 

I’m mildly curious why the investigative agency is the Secret Service, rather than the FBI.  I would have contacted the latter one.








Ryan Wilson September 9, 2019 

Hi Tim,
The reason for the Secret Service being the investigating branch is part of the Patriot Act. The Patriot Act mandated that Secret Service enact Electronic Crimes Task Force teams. They are responsible for investigating crimes against United States financial institutions and critical infrastructure.
https://www.secretservice.gov/data/investigation/USSS-Cyber-Investigations-Flyer.pdf








Tim McSweeney September 9, 2019 

Very interesting.  Many thanks for the info, Ryan.








Joe September 9, 2019 

Yep…. and even long before the Patriot Act… even before the FBI existed, to the very founding of the Secret Service in 1865… they have always be the premier investigative agency related to financial crime.  We only know them today for the Presidential Protective Division because they were best federal law enforcement agency at the time so Congress wanted them for Presidential protection in 1901…. still before the FBI.








BrianKrebs  Post authorSeptember 9, 2019 

The reason is primarily that the Secret Service is part of DHS.










George September 9, 2019 

They have quite a good cyber team. USSS has both Financial and Electronic crimes forces. Obviously there is a lot of overlap between the two these days.










Lolli Pop September 9, 2019 

Perhaps we finally found Hillary’s 30,000 missing emails ?








Joe September 9, 2019 

More likely a Pee Pee tape.










Jim September 9, 2019 

Those emails still lost? I would check in the house and the Senate, they are supposed to have direct copies off the  nipple server. If not there, they could get the originals from the state depts server. Which were copied by the FBI. Come to think of it, they probably are missing now.








Please September 9, 2019 

DOE regulates Nuclear facilities and sure enough this company consults on Nuclear security.  They will find out which insider sold access.  Hopefully it’s not too late because some bad actors have been already penetrating the power grid.  https://www.utilitydive.com/news/ferc-nerc-propose-to-publicly-identify-utilities-violating-cybersecurity-s/562205/
Thank you Brian.  And yes, it is a contracting issue.  The biggest tech companies do not allow contractors in sensitive roles.  One even segregates their contractors.  When I interviewed with this company they told me they would pay me so well I’d never leave them.  I really wanted the job and hence that’s the secret sauce.  Take care of employees and pay them well and they return that dedication.  Contractors have no such loyalty.








System360 September 9, 2019 

Simple way to clear test environments. Boot from a DOS floppy, CD to C: and do DEL *.*








santa September 10, 2019 

😀 U sirious mate? 😀 90s called and want their floppy back..








ifdef moose September 10, 2019 

The 60’s called; they want their mainframe back.












elf September 9, 2019 

Does anyone else worry that the guidelines are primarily for what to do _after_ a breach event takes place, but are very light on allocations for checking and adversarily testing systems to prevent breaches in the first place?








Dave September 10, 2019 

As near as I can tell, Miracle Systems CEO Sandesh Sharda has a Masters in Business Management. I haven’t been able to find out if he has any training/education in STEM or IT Security.  I know a CEO is only suppose to find the right people and manage them, and that a CEO generally can’t screw in a light bulb, but I’ve always been uncomfortable with sensitive information being handled by organizations where the top people didn’t have at least some training in IT Security. Can we say Whaling?   I think it has been mentioned on comments here on Krebs before that we would all like to see mandatory training for the C-suits.  Anyone else have a comment?








Tony September 10, 2019 

Unfortunately, government agencies often subcontract to get around regulations and costs.  
In some cases government agencies subcontract to other countries to perform actions that would be illegal if performed by an entity in United States of America.  
The solution is to introduce legal accountability.  This will drive service prices through the roof but at least the services will be more secure as they should be in the first place.
As much as I hate Sarbanes Oxley, it placed legal responsibility with the officers of the corporation.  As a result, we now perform regular internal audits to ensure accuracy.  Something we should have been doing as part of the job before Sarbanes Oxley.  Sadly it is a boing pain in the butt and drives costs up and reduces productivity.  But, it is the right thing to do.








Kevin September 11, 2019 

This is why there has been such a push towards NIST SP800-171. The aggressor doesn’t need to get into the government systems; just those of the contractors working for them.








Readership1 September 12, 2019 

Has the culprit been identified as having a personality or mental disorder yet? Or will this just get blamed on yet another crumbling slavic or Asian nation east of Brussels?








Joe September 12, 2019 

Culprit(s) haven’t even been identified at all yet… so save your prejudice worldview for the next article.








Readership1 September 20, 2019 

Sometimes you’re an insufferable troll, Joe.








Joe September 20, 2019 

You are the one trolling these comment sections spewing a nonsense personal agenda.  I am sure you are annoyed that you aren’t getting away with your hit n’ run comments.














adultfriendfilder September 12, 2019 

Truly no matter if someone doesn’t understand afterward
its up to other people that they will assist, so here it takes place.








adultfriendrfinder September 20, 2019 

Marvelous, what a weblog it is! This weblog presents valuable
information to us, keep it up.








Fredro September 23, 2019 

Nice post!








poker-lounge99.asia September 23, 2019 

poker-lounge99.asia adalah satu – satunya situs yang menyediakan turnamen setiap minggu untuk melihat pemain yang berkembang dan layak menjadi raja poker di poker-lounge, jika anda ingin mengikutinya segera daftar dan mainkan sekarang juga !!!!








DefenseContractRecruitersLie September 26, 2019 

This doesn’t surprise me at all.  I work as a contractor and wish the government would just do away with most of these companies.  They hold too much power over people’s careers and are much more concerned with making money than national security.  The recruiters for these companies lie, lie, lie, and there is no accountability.    They will bait and switch people seeking employment with a completely bogus job description or job title and can blacklist a person from a contract for no legitimate reason.  I’m really disgusted with how rampant the lack of integrity runs in federal contracting.  I put my resume online after suddenly losing my job on a contract and immediately started getting tons of phishing emails.  It scares me to consider who out there now knows who I am and knows I have a security clearance.








CT September 28, 2019 

A letter I wrote to DHS & Congress last month.  
First, this is a bi-partisan issue that affects all Americans.
The security implications that plague our current state of security in Information technology is due to the lack of understanding in government legislation.  The depths in which we have been compromised through our goodwill is evident to many IT security professionals, yet somehow eludes our legislators.  The gravity of the situation must be addressed.
I have seen several state government facilities that have H1B visa workers managing our critical infrastructure.  How did they get there, you may ask?  Well, they are deeply embedded in the HR Contracting process now.  They view applications, see communications through all governing bodies, and make critical decisions about our infrastructure without having to live with the results of their choices.  These predominantly Indian and foreign companies control the flow of civic jobs now and hire contractors through nepotism.  This practice MUST BE INVESTIGATED TO WEED THEM OUT BECAUSE IT’S FRAUDULENT.  The problem here is that they want money and don’t care a lick about our infrastructure.  The positions they hold include but are not limited to, warning systems, parks, and recreation, water supply, environmental controls, communications, and energy, and more.    I’m worried about our safety!   Our water!   We can no longer behave like naive children with our heads in the sand when our lives depend on it.
Human resources and temporary worker fields have also been hijacked and turned into a quagmire of ineptitude.   They have become resume collectors and information phishers.  They go out of their way to exclude American workers from American jobs and aggregate the information for future sales.   I reiterate the only people that should be permitted to touch networks and systems are  American Citizens.  Cloud infrastructure included.  All 3rd party contractors should be eliminated.  The mistakes I have seen lead me to believe that there is a possibility of “built-in” security issues.  
Some of these companies are currently under investigation by the US Immigration Service.  Because of that fact, they are interviewing Americans again but then canceling the requirement when they find someone, and US Immigration isn’t looking.   You may wonder how deep this goes down the rabbit hole.  I’m here to tell you that it is very deep, and if we were to find ourselves at war with another nation, we have set ourselves up for real hurt.  Watching CNN World News, it’s evident that the targeting of critical infrastructure remains the most viable way to attack and cause the most damage anywhere in the world.  9/11 should have taught us that!  So naturally, I have to question the sanity in these decisions.
It’s time to start from absolute scratch.  We must start from scratch with a VISA program that benefits all of America, but I know you as a committee can’t fix that.  What you can do is make decisions to hire people who can do the job well, that are Americans.  We should not care what color, creed, sex they are, but they must not be foreigners via 3rd party and even 2nd party contracts.  I’ll add that it’s important to remember that a lot of the companies that have lobbied
Hopefully, corporations and government bodies will wake up and look at this profoundly troubling security issue soon.  After all, corporations share all of our natural resources as well, and it’s in their best interest to keep it safe.  
Additionally, all Americans who are in IT should have a job before any foreign workers are considered for government jobs.  This goes double for critical infrastructure jobs.
Note that during the last century, many Americans lost their lives for the goal of a better world for all.  I get that, and I want people around the world to have prosperity.  But I do know this, those people who lost their lives did NOT want Americans to give away the homestead.  They gave up their lives to protect the homestead!  It’s corporations and congress that are dead set on giving it away and putting us all at risk.
In closing, many of the jobs these H1B Visa holders are obtaining are no longer specialty professions.  A 3rd grader is learning to code nowadays.  And there are many college grads with English degrees that can learn if a grade-schooler is able to understand and do it.  They need to be offered opportunities to learn.  And don’t forget the older workers in their 40s and 50s.  Many of them have been booted out because of this foreign labor, and they are intelligent and capable.  Just read comments on DICE and other websites, they are will to travel for these contracting jobs that are being fleeced/stolen by foreign labor.






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






