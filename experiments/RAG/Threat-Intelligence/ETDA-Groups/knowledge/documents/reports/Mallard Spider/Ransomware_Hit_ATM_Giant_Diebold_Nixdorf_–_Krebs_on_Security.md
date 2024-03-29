# Reference for threat actor for "Mallard Spider"

**Title**: Ransomware Hit ATM Giant Diebold Nixdorf – Krebs on Security

**Source**: https://krebsonsecurity.com/2020/05/ransomware-hit-atm-giant-diebold-nixdorf/

## Content











Ransomware Hit ATM Giant Diebold Nixdorf – Krebs on Security











































Advertisement


Advertisement

























Skip to content

HomeAbout the Author
Advertising/Speaking







Ransomware Hit ATM Giant Diebold Nixdorf










May 11, 2020


33 Comments
 




Diebold Nixdorf, a major provider of automatic teller machines (ATMs) and payment technology to banks and retailers, recently suffered a ransomware attack that disrupted some operations. The company says the hackers never touched its ATMs or customer networks, and that the intrusion only affected its corporate network.
Canton, Ohio-based Diebold [NYSE: DBD] is currently the largest ATM provider in the United States, with an estimated 35 percent of the cash machine market worldwide. The 35,000-employee company also produces point-of-sale systems and software used by many retailers.
According to Diebold, on the evening of Saturday, April 25, the company’s security team discovered anomalous behavior on its corporate network. Suspecting a ransomware attack, Diebold said it immediately began disconnecting systems on that network to contain the spread of the malware.
Sources told KrebsOnSecurity that Diebold’s response affected services for over 100 of the company’s customers. Diebold said the company’s response to the attack did disrupt a system that automates field service technician requests, but that the incident did not affect customer networks or the general public.
“Diebold has determined that the spread of the malware has been contained,” Diebold said in a written statement provided to KrebsOnSecurity. “The incident did not affect ATMs, customer networks, or the general public, and its impact was not material to our business. Unfortunately, cybercrime is an ongoing challenge for all companies. Diebold Nixdorf takes the security of our systems and customer service very seriously. Our leadership has connected personally with customers to make them aware of the situation and how we addressed it.”
NOT SO PRO LOCK
An investigation determined that the intruders installed the ProLock ransomware, which experts say is a relatively uncommon ransomware strain that has gone through multiple names and iterations over the past few months.
For example, until recently ProLock was better known as “PwndLocker,” which is the name of the ransomware that infected servers at Lasalle County, Ill. in March. But the miscreants behind PwndLocker rebranded their malware after security experts at Emsisoft released a tool that let PwndLocker victims decrypt their files without paying the ransom.
Diebold claims it did not pay the ransom demanded by the attackers, although the company wouldn’t discuss the amount requested. But Lawrence Abrams of BleepingComputer said the ransom demanded for ProLock victims typically ranges in the six figures, from $175,000 to more than $660,000 depending on the size of the victim network.
Fabian Wosar, Emsisoft’s chief technology officer, said if Diebold’s claims about not paying their assailants are true, it’s probably for the best: That’s because current versions of ProLock’s decryptor tool will corrupt larger files such as database files.
As luck would have it, Emsisoft does offer a tool that fixes the decryptor so that it properly recovers files held hostage by ProLock, but it only works for victims who have already paid a ransom to the crooks behind ProLock.
“We do have a tool that fixes a bug in the decryptor, but it doesn’t work unless you have the decryption keys from the ransomware authors,” Wosar said.
WEEKEND WARRIORS
BleepingComputer’s Abrams said the timing of the attack on Diebold — Saturday evening — is quite common, and that ransomware purveyors tend to wait until the weekends to launch their attacks because that is typically when most organizations have the fewest number of technical staff on hand. Incidentally, weekends also are the time when the vast majority of ATM skimming attacks take place — for the same reason.
“After hours on Friday and Saturday nights are big, because they want to pull the trigger [on the ransomware] when no one is around,” Abrams said.
Many ransomware gangs have taken to stealing sensitive data from victims before launching the ransomware, as a sort of virtual cudgel to use against victims who don’t immediately acquiesce to a ransom demand.
Armed with the victim’s data — or data about the victim company’s partners or customers — the attackers can then threaten to publish or sell the information if victims refuse to pay up. Indeed, some of the larger ransomware groups are doing just that, constantly updating blogs on the Internet and the dark Web that publish the names and data stolen from victims who decline to pay.
So far, the crooks behind ProLock haven’t launched their own blog. But Abrams said the crime group behind it has indicated it is at least heading in that direction, noting that in his communications with the group in the wake of the Lasalle County attack they sent him an image and a list of folders suggesting they’d accessed sensitive data for that victim.
“I’ve been saying this ever since last year when the Maze ransomware group started publishing the names and data from their victims: Every ransomware attack has to be treated as a data breach now,” Abrams said.



         This entry was posted on Monday 11th of May 2020 12:37 PM 
         
Ransomware
BleepingComputer Diebold Nixdorf Emsisoft Fabian Wosar Lawrence Abrams ProLock ransomware




Post navigation
← Meant to Combat ID Theft, Unemployment Benefits Letter Prompts ID Theft Worries
Microsoft Patch Tuesday, May 2020 Edition →



			33 thoughts on “Ransomware Hit ATM Giant Diebold Nixdorf”		




AJNorth May 11, 2020 

One question that is begged, of course, is the significance — and crossover — to the various electronic voting systems in use by various states (directly and indirectly).








Tyler May 12, 2020 

Your writing style is, um, odd: “One question that is begged, of course.” Begged by? Of course?










mark May 11, 2020 

Brian,
   This could be even more dangerous. I don’t know what their market share is now, but Diebold was the #1 producer of electronic voting machines.
   Given that, I have to wonder just *what* the invaders were after.








Michael Jacobsen May 11, 2020 

Hi all. I work in communications for Diebold Nixdorf. Just to clarify a couple of the comments here, Diebold sold its voting machine business in September 2009.  
https://www.nytimes.com/2009/09/04/technology/04vote.html
While the Diebold name still appears on many of the voting machines it sold to states and counties between 2002 and 2009, the company is now far removed from the U.S. voting business and has no role whatsoever in the elections process.








The Cyber Post May 11, 2020 

Very interesting information Michael. Thank you for the clarification however!








Ooookay-Sure May 12, 2020 

And of course Diebold didn’t keep any of that voting machine code or recycle any code from their other ATM or POS systems. And the purchaser of the voting business certainly did a complete and thorough audit of all of the old Diebold code and didn’t put modems in any of these voting machines. Whooops
https://www.nbcnews.com/politics/elections/online-vulnerable-experts-find-nearly-three-dozen-u-s-voting-n1112436










Robert May 12, 2020 

Thank you for this information Michael.










security vet May 11, 2020 

…the police supposedly asked Willie Sutton why he robbed banks…to which he replied “…that’s where the money is…”








Wolverine May 12, 2020 

Everyone has heard that story.  Please don’t vote.












JoeS May 11, 2020 

Open source electronic voting systems with paper trail would make me feel a lot better.








Bernhard M. Wiedemann May 11, 2020 

Then every voter needs to verify the paper trail. And then people need to verify the counting and transmission of the votes.
There are so many ways one can subvert electronics, even below open-source software. Even with open-source hardware.
https://betrusted.io/ is what gets closest to verifiable hardware. There was a nice CCCongress discussion by “bunnie” of the issues involved.








Joe May 13, 2020 

Paper can be a great backup in case electronic validation methods are compromised.
But it takes a long time and is technically impossible to verify 100% every vote at scale.  Hand recounts with physical ballots are prone to significant human error (2000, FL).
Electronically, we have blockchain technology now that is well suited to handle the scale and accuracy needed for mass verification.  Then, only random spot checks of paper are needed to make doubly sure.












Alexander May 11, 2020 

Hi,whenever I try to read your articles on my phone, it’s totally unreadable. Either the font is too small or the width of the text is too wide. Can you switch to a responsive design? That would help a lot.
Thanks.








JCitizen May 11, 2020 

Can you install a different browser on your phone? Just wondering.








Dennis May 11, 2020 

He is using some custom-made blog here, so I doubt it’s that easy to “switch it” to mobile responsive design. So unless you’re using Chrome (that doesn’t support it) when you pull up this page switch to “reader view”, that will strip out all the ads and show it as text only that will be very easy to read. I do it all the time on my iPhone. If you’re stuck with Chrome (like an an Android) then install and use Firefox web browser instead.








Mahhn May 11, 2020 

Works fine is Safari and Firefox on my phone.








Brian Fiori (AKA The Dean) May 11, 2020 

Zero issue here with Chrome.
Just a thought, set your mobile browser to open this site as a “desktop site”. That might help.








Ryan May 18, 2020 

If you are using Chrome on Android you can enable their version of reader mode here chrome://flags/#enable-reader-mode










John Campbell May 11, 2020 

Let’s not lite a fire under the voting machine, conspiracy hysteria and stick with the ransomware facts gents.
Diebold sold off that division (Premier Election Solutions) 11 years ago in 2009, ~4 years before Swidarski was let go in 2013. ES&S acquired it in 2009 but due to monopoly charges by the DOJ, they sold it off to Dominion Voting Systems.
Neither company is part of much less has a shared network with Diebold.
While you may walk in and still see the old Diebold logo on the welcome prompt screen, DN has not run that platform in 11 years nor does it have operational connection to it from their corporate systems.








JoDee May 12, 2020 

This is what is KNOWN:
Premier Election Solutions, formerly Diebold Election Systems, Inc. was a subsidiary of Diebold that makes and sells voting machines.
In 2009, it was sold to competitor ES&S. Another subsidiary selling electronic voting systems in Brazil as Diebold-Procomp, with minor market share in that nation. In 2010, Dominion Voting Systems purchased the primary assets of Premier, including all intellectual property, software, firmware and hardware for Premier’s current and legacy optical scan, central scan, and touch screen voting systems, and all versions of the GEMS election management system from ES&S.
The relationship ES&S had with Dominion (who bought Premier from ES&S) was what dragged the company into the conversation. The relationship with Dominion put a spotlight on ES&S because Premier (a subsidiary of Dominion) was once known as Diebold, which one of the Urosevich brothers once directed. Essentially, ES&S suffered from a loss of trust due to its historical ties with other voting machine companies.
”DON’T BELIEVE THE TRUTH ,UNLESS IT IS THE TRUTH”
REPLY










JCitizen May 11, 2020 

I’m not a shill for Emsisoft, but they have the best detection of any anti-malware I’ve ever used – unfortunately they also can find the MPAA required spyware that is put on your hardware if you have any high definition equipment on your PC. Especially if you have a Blu-ray burner. Because of that, I was unable to continue using their Mamutu (HIPS)product as it was discontinued and melded with their suite product. After that I just couldn’t configure Emsisoft to quit harassing my legal spyware on the machine, and I couldn’t even watch HDTV cable programs because of it. Oh well – if one doesn’t have that problem I think they have the ultimate APT detection of any product out there!








The Cyber Post May 11, 2020 

Ransomware is becoming more and more prevalent. The underlying question here is HOW did the attackers gain access to these servers in the first place? I notice a lot of users on certain Russian underground forums selling access to larger networks or companies “grids” as of late as well. I think every major company needs to beef up security and practice for these types of attacks.








Joe May 13, 2020 

Ransomware spreads even when attackers don’t have “access” to the network.
It is much harder to get backdoor access than it is to simply run code.  For “access”, it is often required to bypass firewalls and run with higher privileges.
But ransomware is becoming so prevalent, because it is easy to automate an algorithm to find and encrypt files.  Usually, non-privileged users are allowed to write to these file stores (local or on shares)… and thus, code run in their context can too.  Users have write access to file servers, and that is basically all that is needed for ransomware.
So while a good defense in depth strategy can prevent malicious actors from gaining interactive “access” as you think… phishing attacks often get through and cause a ransomware infection without running into those defenses.










Name required May 11, 2020 

Have they implicated COBOL yet?








Kabuki Toyama May 11, 2020 

Looks like I have to get an antivirus soon 😀








Jones May 12, 2020 

If such a major incident happened on Diebold and was detected on 25th of April, why did they not even mention and communicate this issue officially on May 5th when presenting their first quarter financial results? Why were they concealing this major attack?








Jim May 12, 2020 

Good write-up. Nice report.  Yes, old reports dibold was sold. Long ago. And counties are, still using their systems.  And the other newer systems are not tested any harder then the old systems. And their programs are not reviewable by outside authorities, except for a few localities. Researchers in voting problems are not allowed into the systems to see if the machines can even produce accurate results. Is there a voting problem, no one knows. If one system is out of wack, can the voting results be trusted?








Jon Marcus May 12, 2020 

Interesting lesson on reputation management that over a decade after they dumped the business, the name Diebold *still* means “shoddy voting software”.








vb May 12, 2020 

Any guess on the method of compromise?








BrianKrebs  Post authorMay 12, 2020 

I somehow forgot to add this detail to the story, but Diebold said the method of infection was through a phishing email.








John May 12, 2020 

As always — Humans are the weakest link!
Somethings will never er change!












Matt May 13, 2020 

Are there any technical reports or samples available of the ProLock ransomware?








Tom May 17, 2020 

Interesting part about “hackers never touched its ATMs or customer networks, and that the intrusion only affected its corporate network.” statement. My wife got a new ATM card  (replacing an expired one) prior to the April 25th date. She has never used her ATM card since she’s had the account. This past week, we saw two charges show up from the new card on her bank account. Rather odd to see with a card that has never been used and still in our possession.
Granted this might only be related if Diebold has the information on ATM cards being issued to users from their banks.
I don’t know what their link is between ATM machines, ATM cards, and banks, but I thought it was interesting.






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






