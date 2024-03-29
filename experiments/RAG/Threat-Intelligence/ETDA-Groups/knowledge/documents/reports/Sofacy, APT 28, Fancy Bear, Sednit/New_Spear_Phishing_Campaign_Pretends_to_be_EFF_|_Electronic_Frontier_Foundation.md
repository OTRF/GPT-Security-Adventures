# Reference for threat actor for "Sofacy, APT 28, Fancy Bear, Sednit"

**Title**: New Spear Phishing Campaign Pretends to be EFF | Electronic Frontier Foundation

**Source**: https://www.eff.org/deeplinks/2015/08/new-spear-phishing-campaign-pretends-be-eff

## Content














































































New Spear Phishing Campaign Pretends to be EFF | Electronic Frontier Foundation












Skip to main content



AboutContact
Press
People
Opportunities

IssuesFree Speech
Privacy
Creativity and Innovation
Transparency
International
Security

Our WorkDeeplinks Blog
Press Releases
Events
Legal Cases
Whitepapers
Podcast
Annual Reports

Take ActionAction Center
Electronic Frontier Alliance
Volunteer

ToolsPrivacy Badger
Surveillance Self-Defense
Certbot
Atlas of Surveillance
Cover Your Tracks
Crocodile Hunter

DonateDonate to EFF
Giving Societies
Shop
Other Ways to Give
Membership FAQ

DonateDonate to EFF
Shop
Other Ways to Give


Search form

Search 






 



    Email updates on news, actions,
    and events in your area.
  

Join EFF Lists



Copyright (CC BY)
Trademark
Privacy Policy
Thanks
 






Electronic Frontier Foundation 



Donate











Electronic Frontier Foundation 




AboutContact
Press
People
Opportunities

IssuesFree Speech
Privacy
Creativity and Innovation
Transparency
International
Security

Our WorkDeeplinks Blog
Press Releases
Events
Legal Cases
Whitepapers
Podcast
Annual Reports

Take ActionAction Center
Electronic Frontier Alliance
Volunteer

ToolsPrivacy Badger
Surveillance Self-Defense
Certbot
Atlas of Surveillance
Cover Your Tracks
Crocodile Hunter

DonateDonate to EFF
Giving Societies
Shop
Other Ways to Give
Membership FAQ

DonateDonate to EFF
Shop
Other Ways to Give


Search form

Search 






 















New Spear Phishing Campaign Pretends to be EFF


            DEEPLINKS BLOG    

By Cooper QuintinAugust 27, 2015 




 






New Spear Phishing Campaign Pretends to be EFF






Share It
Share on Twitter
Share on Facebook
Copy link











Update 01/28/16: EFF now controls the Electronicfrontierfoundation.org domain and that URL currently redirects to this blog post. If you arrived at this page via a link in a message that may have been phishing, please let us know and we will investigate.

Google's security team recently identified a new domain masquerading as an official EFF site as part of a targeted malware campaign. That domain, electronicfrontierfoundation.org, is designed to trick users into a false sense of trust and it appears to have been used in a spear phishing attack, though it is unclear who the intended targets were. The domain was registered on August 4, 2015, under a presumably false name, and we suspect that the attack started on the same day. At the time of this writing the domain is still serving malware.
Electronicfrontierfoundation.org was not the only domain involved in this attack. It seems to be part of a larger campaign, known as “Pawn Storm”. The current phase of the Pawn Storm attack campaign started a little over a month ago, and the overall campaign was first identified in an October 2014 report from Trend Micro (PDF). The group behind the attacks is possibly associated with the Russian government and has been active since at least 2007.
The attack is relatively sophisticated—it uses a recently discovered Java exploit, the first known Java zero-day in two years. The attacker sends the target a spear phishing email containing a link to a unique URL on the malicious domain (in this case electronicfrontierfoundation.org). When visited, the URL will redirect the user to another unique URL in the form of http://electronicfrontierfoundation.org/url/{6_random_digits}/Go.class containing a Java applet which exploits a vulnerable version of Java. Once the URL is used and the Java payload is received, the URL is disabled and will no longer deliver malware (presumably to make life harder for malware analysts). The attacker, now able to run any code on the user's machine due to the Java exploit, downloads a second payload, which is a binary program to be executed on the target's computer.
We were able to recover the following samples of the malicious Java code from electronicfrontierfoundation.org.


Filename
MD5 Sum
SHA1 Sum


App.class
0c345969a5974e8b1ec6a5e23b2cf777
95dc765700f5af406883d07f165011d2ff8dd0fb


Go.class
25833224c2cb8050b90786d45f29160c
df5f038d78f5934bd79d235b4d257bba33e6b3


The decompiled Java for App.class
The decompiled Java for App.class
The Go.class applet bootstraps and executes App.class, which contains the actual attack code. The App.class payload exploits the same Java zero-day reported by Trend Micro and then downloads a second stage binary, internally called cormac.mcr, to the user's home directory and renames it to a randomly chosen string ending in `.exe`. Interestingly, App.class contains code to download a *nix compatible second stage binary if necessary, implying that this attack is able to potentially target Mac or Linux users.
Unfortunately we weren't able to retrieve the second stage binary, however this is the same path and filename that has been used in other Pawn Storm attacks, which suggests that it is likely to be the same payload: the malware known as Sednit. On Windows, the Sednit payload is downloaded to the logged-in user's home directory with a randomly generated filename and executed. On running it hooks a variety of services and downloads a DLL file. The DLL file is executed and connects to a command and control server where it appears to verify the target and then execute a keylogger or other modules as may be required by the attacker.
Because this attack used the same path names, Java payloads, and Java exploit that have been used in other attacks associated with Pawn Storm, we can conclude that this attack is almost certainly being carried out by the same group responsible for the rest of the Pawn Storm attacks. Other security researchers have linked the Pawn Storm campaign with the original Sednit and Sofacy targeted malware campaigns–also known as “APT 28”–citing the fact that they use the same custom malware and have similar targets. In a 2014 paper the security company FireEye linked the “APT 28” group behind Sednit/Sofacy with the Russian Government (PDF) based on technical evidence, technical sophistication, and targets chosen. Drawing from these conclusions, it seems likely that the organization behind the fake-EFF phishing attack also has ties to the Russian government. Past attacks have targeted Russian dissidents and journalists, U.S. Defense Contractors, NATO forces, and White House staff. We do not know who the targets were for this particular attack, but it does not appear that it was EFF staff.
The phishing domain has been reported for abuse–though it is still active, and the vulnerability in Java has been patched by Oracle. Of course this is an excellent reminder for everyone to be vigilant against phishing attacks. Our SSD guide contains advice on how to improve your security, watch for malicious emails, and avoid phishing attacks such as this one.
 



Related Issues
SecurityState-Sponsored Malware 

Related Cases
Kidane v. Ethiopia 


Share It
Share on Twitter
Share on Facebook
Copy link




Join EFF Lists

Discover more.
 Email updates on news, actions, events in your area, and more.

Email Address



Postal Code (optional) 



Anti-spam question: Enter the three-letter abbreviation for Electronic Frontier Foundation:




Don't fill out this field (required)






    Thanks, you're awesome! Please check your email for a confirmation link.
  


    Oops something is broken right now, please try again later.
  



Related Updates





Deeplinks Blog
 by Karen Gullo
 | February 7, 2024
 Protect Good Faith Security Research Globally in Proposed UN Cybercrime Treaty


Statement submitted to the UN Ad Hoc Committee Secretariat by the Electronic Frontier Foundation, accredited under operative paragraph No. 9 of UN General Assembly Resolution 75/282, on behalf of 124 signatories. We, the undersigned, representing a broad spectrum of the global security research community, write to express our serious concerns... 





Deeplinks Blog
 by Karen Gullo
 | February 7, 2024
 Draft UN Cybercrime Treaty Could Make Security Research a Crime, Leading 124 Experts to Call on UN Delegates to Fix Flawed Provisions that Weaken Everyone’s Security


Security researchers’ work discovering and reporting vulnerabilities in software, firmware, networks, and devices protects people, businesses and governments around the world from malware, theft of critical data, and other cyberattacks. The internet and the digital ecosystem are safer because of their work.The UN Cybercrime Treaty,... 





Deeplinks Blog
 by Cooper Quintin
 | January 31, 2024
 Worried About AI Voice Clone Scams? Create a Family Password


Your grandfather receives a call late at night from a person pretending to be you. The caller says that you are in jail or have been kidnapped and that they need money urgently to get you out of trouble. Perhaps they then bring on a fake police officer or kidnapper... 





Deeplinks Blog
 by Karen Gullo
 | January 29, 2024
 In Final Talks on Proposed UN Cybercrime Treaty, EFF Calls on Delegates to Incorporate Protections Against Spying and Restrict Overcriminalization or Reject Convention


UN Member States are meeting in New York this week to conclude negotiations over the final text of the UN Cybercrime Treaty, which—despite warnings from hundreds of civil society organizations across the globe, security researchers, media rights defenders, and the world’s largest tech companies—will, in its present form, endanger... 





Deeplinks Blog
 by Paige Collings
 | January 19, 2024
 EFF’s 2024 In/Out List 


Since EFF was formed in 1990, we’ve been working hard to protect digital rights for all. And as each year passes, we’ve come to understand the challenges and opportunities a little better, as well as what we’re not willing to accept. Accordingly, here’s what we’d like to see a lot... 





Deeplinks Blog
 by Bill Budington, Alexis Hancock
 | December 23, 2023
 Sketchy and Dangerous Android Children’s Tablets and TV Set-Top Boxes: 2023 in Review


In a series of investigations this year, EFF researchers confirmed the existence of dangerous malware on set-top boxes manufactured by AllWinner and RockChip, and discovered sketchyware on a tablet marketed for kids from the manufacturer Dragon Touch. 





Deeplinks Blog
 by Ross Schulman
 | December 13, 2023
 Spritely and Veilid: Exciting Projects Building the Peer-to-Peer Web


While there is a surge in federated social media sites, like Bluesky and Mastodon, some technologists are hoping to take things further than this model of decentralization with fully peer-to-peer applications. Two leading projects, Spritely and Veilid, hint at what this could look like.There are many technologies used behind the... 





Deeplinks Blog
 by Cooper Quintin, Mona Wang
 | December 7, 2023
 Meta Announces End-to-End Encryption by Default in Messenger 


Yesterday Meta announced that they have begun rolling out default end-to-end encryption for one-to-one messages and voice calls on Messenger and Facebook. While there remain some privacy concerns around backups and metadata, we applaud this decision. It will bring strong encryption to over one billion people,... 





Deeplinks Blog
 by Alexis Hancock
 | November 14, 2023
 Low Budget Should Not Mean High Risk: Kids' Tablet Came Preloaded with Sketchyware


It’s easy to get Android devices from online vendors like Amazon at different price points. Unfortunately, it is also easy to end up with an Android device with malware at these lower budgets. There are several factors that contribute to this: multiple devices manufactured in the... 





Press Release
 | November 14, 2023
 EFF Urges FTC to Address American Resellers of Malware on Android TV Set-Top Boxes


SAN FRANCISCO—The Federal Trade Commission (FTC) must act to halt sales by Amazon, AliExpress, and other resellers of Android television set-top boxes and mobile devices manufactured by AllWinner and RockChip that have been pre-infected with malware before ever reaching consumers, the Electronic Frontier Foundation (EFF) urged Tuesday in ... 



 




Discover more.
Email updates on news, actions, events in your area, and more.

Email Address



Postal Code (optional) 



Anti-spam question: Enter the three-letter abbreviation for Electronic Frontier Foundation:




Don't fill out this field (required)






    Thanks, you're awesome! Please check your email for a confirmation link.
  


    Oops something is broken right now, please try again later.
  


Share It
Share on Twitter
Share on Facebook
Copy link


Related IssuesSecurityState-Sponsored MalwareRelated casesKidane v. Ethiopia 









Back to top



 

Follow EFF:

x
facebook
instagram
youtube
flicker
linkedin
mastodon
tiktok
threads



Check out our 4-star rating on Charity Navigator.


Contact
General
Legal
Security
Membership
Press
 

About
Calendar
Volunteer
Victories
History
Internships
Jobs
Staff
Diversity & Inclusion
 

Issues
Free Speech
Privacy
Creativity & Innovation
Transparency
International
Security
 

Updates
Blog
Press Releases
Events
Legal Cases
Whitepapers
EFFector Newsletter
 

Press
Press Contact
 

Donate
Join or Renew Membership Online
One-Time Donation Online
Giving Societies
Shop
Other Ways to Give
 



Copyright (CC BY)
Trademark
Privacy Policy
Thanks
 

JavaScript license information



