# Reference for threat actor for "Kimsuky, Velvet Chollima"

**Title**: Podcast: Recent Activity from ITG16, a North Korean Threat Group

**Source**: https://securityintelligence.com/media/recent-activity-from-itg16-a-north-korean-threat-group/

## Content




 

Podcast: Recent Activity from ITG16, a North Korean Threat Group





























































































Security Intelligence 





News
Series
Topics
X-Force
Podcast






News
Series
Topics
Threat Research
Podcast











Search
























Application Security
Artificial Intelligence
CISO
Cloud Security
Data Protection
Endpoint


Fraud Protection
Identity & Access
Incident Response
Mainframe
Network
Risk Management


Intelligence & Analytics
Security Services
Threat Hunting
Zero Trust
Infographic: Zero trust policy
Timeline: Local Government Cyberattacks


Industries
Banking & Finance
Energy & Utility
Government
Healthcare




View All Topics































News
Series




Topics


All Categories
Application Security
Identity & Access
Artificial Intelligence
Incident Response
CISO
Mainframe
Cloud Security
Mobile Security
Data Protection
Network
Endpoint
Risk Management
Fraud Protection
Threat Hunting
Security Services
Security Intelligence & Analytics


Industries
Banking & Finance
Energy & Utility
Government
Healthcare




X-Force
Podcast



































Home
/
Podcast



Advanced Threats



Recent Activity from ITG16, a North Korean Threat Group
















Play the latest episode
|
Jul 2, 2020

17 minutes







Subscribe



Subscribe
Listen to the Security Intelligence Podcast wherever you get your podcasts.































Recent Activity from ITG16, a North Korean Threat Group










Subscribe

Listen to the Security Intelligence Podcast wherever you get your podcasts.
iTunes
Spotify


























July 2, 2020
|
By Megan Radogna
|
  11 min read









Listen to this podcast on Apple Podcasts, SoundCloud or wherever you find your favorite audio content.
On this week’s Security Intelligence podcast, Joshua Chung and Ryan Castillo of IBM X-Force Incident Response and Intelligence Services (IRIS) join the hosts to continue an exploration of advanced persistent threat (APT) groups. Specifically, they discuss ITG16, a North Korean government state‑sponsored threat group whose recent activity includes targeting South Korean individuals in COVID-19 related phishing campaigns.
Listen Now: Recent Activity from ITG16, a North Korean Threat Group
ITG16 Targets and Tactics Over Time
Criminal and nation-state threat group activities of years past tended to harvest thousands of emails and launch more generalized phishing campaigns. However, stronger network defenses and better security awareness training from companies “resulted in APT groups adapting and evolving to craft the campaigns in a more focused and stealthier fashion,” Castillo explains.
ITG16 evolved in kind. “The group came into prominence around late December 2014,” Chung says, “when ITG16 compromised a South Korean nuclear power plant and released troves of documents and taunted investigators with false media accounts.” The attack against the power plant in 2014 included about 6,000 emails. Recent activity suggests ITG16 is targeting smaller groups with more relevant content — for example, targeting South Korean individuals engaged in international affairs with a COVID-19 related phishing campaign.
In addition to refining its tactics, the threat group has adapted who it targets. Known originally for targeting South Korean organizations such as diplomatic and national security personnel, human rights groups, media, utilities and think tanks, ITG16 has expanded its operations to include financial institutions and cryptocurrency exchanges. “We believe the inclusion of these financial targets may be reflecting shifting North Korean government priorities to utilize multiple threat groups to obtain illicit funds,” says Chung.
The Upside of Predictability
Castillo and Chung anticipate ITG16 will continue to be active in the near future. When looking ahead, predictability offers a small bright spot. Organizations monitoring the geopolitical landscape on the Korean peninsula may have an opportunity to predict and mitigate threats from this group going forward.
APTs are known for capitalizing on confusion and taking advantage of people’s emotions, as displayed by ITG16’s recent COVID-19 related spam activity. “People really need to take a step back and pay attention to detail when thinking about opening e‑mail attachments or searching for news,” Castillo advises.
Missed the first episode in the series about digital assets and assailants? Listen to learn more about the ITG08 threat group, an organized cybercrime gang known for targeting e-commerce environments.
Podcast: Exploring the Impact of the ITG08 Threat Group
Episode Transcript:

MOULTON: We’ve got some really interesting research to dig into for this episode.
COBB: Absolutely. I had a chance to talk to the analysts on the X‑Force IRIS team about another advanced persistent threat group, ITG16.
MOULTON: What is that group known for?
COBB: Well, I’ll let Josh and Ryan get into the full details, but spoiler alert: ultimately, ITG16 is a North Korean government state‑sponsored threat group. This is the Security Intelligence podcast where we discuss cybersecurity industry analysis, tips and success stories. I’m Pam Cobb.
MOULTON: And I’m David Moulton.
COBB: Let’s dive in and take a closer look at this threat group.
Well, welcome to the podcast.  Can you all take a minute to introduce yourselves to our audience. Josh, let’s start with you.
CHUNG: Sure.  Hi, my name is Joshua Chung, and I’m a strategic cyber intel analyst from the TIPT team here within IBM IRIS where we look at strategic cyber threats at various enterprise and industries. I generally focus on advanced persistent threat — or, APT — groups from East Asian regions, looking at strategic pictures and then the threats those groups pose.
CASTILLO: And my name’s Ryan Castillo. I’m an analyst on the threat hunt and discovery team within IBM X‑Force IRIS. My role is to investigate and analyze cyber threat activity and then provide direct or tactical intelligence support to our incident response investigations.
I also conduct threat intelligence research on APT and cyber criminal groups.  We then use that data to populate our databases with current threat information which helps support our customers, future investigations and analytical research.
COBB: Great. On a previous episode of the podcast, we talked about ITG08, and we touched on the distinction between APTs and criminal threats. So, can you briefly recap for us what that difference is and where ITG16 falls?
CHUNG: Right. So, for a quick recap, I think the difference between the two groups can be said between motivations.  Whereas APT groups are state sponsors with defined national objectives, criminal groups tend to, well, generally be more based on illicit financial gains. That’s their motivation.  And they’re very opportunistic.
A good analogy would be for a criminal threat to be like a car thief, right, who prowls the streets in search of cars without an alarm. And an APT group would be somebody like a mob hitman, right, who has a very specific target and objective that he or she must accomplish.
So, that being said, there are certain outlier groups that blend both APT and criminal activity, as in the case of North Korean threat groups, like robbing a bank, for example. And in the case of ITG16, while the group is a state‑sponsored group, I would not be surprised to see this group carrying out those illicit financial activities.
COBB: Why is this threat group classified as an ITG versus a hive, and why does that attribution matter?
CASTILLO: Okay, so you can look at ITGs and hives as an internal classification or a taxonomy tool that helps us and the team stay organized and communicate about the different behaviors and targets that a group might be looking at. We track patterns of unattributed malicious activity in campaigns which we discover in the wild and classify it as a hive.
Once that activity meets a strict analytical threshold based on a full range of tactics, techniques and procedures, including infrastructure or malware tools, targeting and so forth, we then classify the hive to an IBM threat group, or ITG16, and then we attribute that activity to that ITGC…excuse me, that ITG.
ITG16 started out as a hive, and as their campaigns started to increase in 2018, we were able to track them consistently and subsequently reclassify as an ITG in the middle of 2019. Now, this is important because as we get into attribution which of course, we need to first define, is simply put as the process of tracking, identifying and associating malicious activity to a threat actor, and that includes whether they’re state sponsored or not.
We look at that activity that we’ve gathered on the threat and compare it to what we already know about not only that group but other threat groups to associate that activity to the APT or criminal with record in question.
Now, why does that matter? Attribution is important because it allows us to better understand the threat; which in turn, produces better recommendations for defense strategies whether that be strategic or tactical in nature. It allows us to peek into the future, so to speak, and to assess campaigns that are more likely to occur. This also allows us to shift into a proactive state rather than get caught in a reactive state.
COBB: So, who is ITG16?
CHUNG: ITG16 is a North Korean government state‑sponsored threat group. It was first reported in 2013, but may have been active since at least 2010. And it overlaps with groups known in the industry as Kimsuky or Thallium or Black Banshee.
The group came into prominence around late December 2014, right around the time with the Sony incident, when ITG16 compromised a South Korean nuclear power plant and released troves of documents and taunted investigators with false media accounts, right, in kind of like a similar fashion to what was going on with the Sony at the time.
ITG16 traditionally targets South Korean organizations, including diplomatic and national security personnel, human rights groups, media, utility, think tanks. However, in the last two years, we noticed that the group has expanded its operation to include the financial institutions and cryptocurrency exchanges.
We believe the inclusion of these financial targets may be reflecting shifting North Korean government priorities to utilize multiple threat groups to obtain illicit funds because there is…because of the impact from international sanctions, it’s really taking a toll on its economy.
COBB: Can you talk about how the threat group has evolved over time?
CASTILLO: Yes, if we look at APT groups in general, ITG16 included, you could say past campaigns were almost belligerent in nature and all over the place and that they were easily identified because of the limited open‑source intelligence research conducted by these actors.
By that I mean these groups would harvest thousands of e‑mail addresses from all over the Internet and send out e‑mails with subject matter that had nothing to do with the targeted audience, hoping someone would take the bait.
Now, that worked, and to a great extent, but companies’ network defense has stiffened up over the years and employees are being trained on how to spot phishing e‑mails better than they were, say, 10 years ago, which has resulted in APT groups adapting and evolving to craft the campaigns in a more focused and stealthier fashion, which includes targeting smaller groups with content related to that particular target audience.
ITG16 is no different in that respect; for example, the campaign against the South Korean nuclear power plant network, which Josh mentioned earlier, consisted of 6,000 e‑mails.
COBB: So, what is ITG16’s known technique?
CASTILLO: ITG16 is known for specializing in targeting and compromising the theft of highly sensitive information from high‑value computer networks.  They use several different methods to penetrate a network which include utilizing stolen credentials that have been harvested through various campaigns or via spearphishing e‑mails.
They are very good at conducting open‑source intelligence research on their targets. They identify individuals employed by the target organization via publicly available information and by social media interaction, and then package an e‑mail in a way that gives off credibility to the target.
The group has an arsenal of tools at their disposal, including the use of malicious macros and documents, often containing lure content relevant to intended phishing victims.
Their lure content is usually publicly available information harvested from the Internet, but there have been campaigns where they have used nonpublic documents like private documents that have been compromised from other individuals within the target scope; which undoubtedly, as you can imagine, makes it very difficult to sniff out for unsuspecting individuals.
The group has infamously made use of malicious Hangul Word Processor files in their campaigns, which is a Microsoft equivalent of the Office Word program, but it’s widely used in South Korean government agencies and the government related academia and think tanks.
COBB: Well, you’ve talked about techniques. Are they associated with any specific tools?
CASTILLO: Yes. ITG16 has made a couple tools famous through the years. One is the KimJongRAT and BabyShark malware. KimJongRAT is a credential theft utility which exfiltrates e‑mail and Web credentials as well as various pieces of system information which are eventually returned to a command and control server.
The KimJongRAT has been programmed to siphon data from popular Web browsers such as like Google Chrome, Mozilla Firefox, Internet Explorer and Yandex Browser. This particular malware has the ability to target several Web pages and online services such as Facebook, Google, Yahoo!, Mozilla, Thunderbird and Microsoft Outlook.
Now, the BabyShark malware family, which was first seen around 2018, launches from a remote location and such can be delivered via different attack methods, like portable executables or malicious documents. It has the ability to exfiltrate system information so the command and control server maintain…it maintains its persistence on the system, and then it will wait for further instructions from the operator.
Recently, these two pieces of malware have been seen working in conjunction together. KimJongRAT seems to be primarily used as a password extraction and information stealer tool, and the BabyShark malware is responsible for picking up the information stored in the log files and then transmitting it back to the command and control server.
COBB: Has the IRIS team come across ITG16 recently?
CHUNG: Yes, we’ve been monitoring ITG16 activities reported by third parties and conducted our own analysis on the tools used as well.  So, the recent activities includes incorporating COVID‑19 related material into phishing campaigns targeting South Korean individuals engaged in international affairs.
The phishing e‑mails would ask the user to enable macro, which would execute scripts located at remote server.  The remote script was then designed to gather infected host information including host computer names, the versions, the network shares.
That same COVID‑19 related phishing campaign is also seen to be aiming in non‑Korean speaking users, especially Mac OS users, where ITG16 actors leverage similar TTPs using a Word document with the macro that, when enabled, will reach out and give additional payload onto the victims.
CASTILLO: Now, we within IRIS have continually utilized the information we have found to populate our databases with current threat information while monitoring and tracking ITG16 activities.
Although we haven’t encountered them during an incident response incident, we feel that we have developed extensive detection capabilities to isolate their lure documents, malware and infrastructure; which in turn, will help support our customers’ future investigations and analytical research.
CHUNG: Also, just to note, last December Microsoft took the action of taking down 50 domains belonging to ITG16 referred to as Thallium by Microsoft. ITG16 were using spoof Microsoft domains as part of their phishing campaign designed to steal victim credentials, among other things.  And then the targets in that campaign included government employees, think tanks, university staff members, members of organizations focused on world peace and human rights and individuals that work on nuclear proliferation issue, according to Microsoft statements.
And many of these targets were based in U.S. as well as Japan and South Korea.  And these Microsoft findings overlap with our own analysis about ITG16 campaigns and who they target and supports our assessments on the groups from a victimology and TTP perspective.
COBB: So, how does this compare to the ways that ITG16 attacks have been detected in the past?
CASTILLO: IGT16 sometimes uses the same infrastructure to carry out campaigns, so researchers are quick to point out when something happens. We usually go out and pull down that malware associated with the campaign, and then we have our reverse engineers analyze the sample and provide a YARA rule, which are ways to identify malware or other files by creating rules that look for certain characteristics within that file or malware.
We can then find additional malware based off those rules and discover additional malware and infrastructure that we might not have known about before. Sometimes they make it easy for us, like utilizing one IP address to host a couple dozen malicious domains.
ITG16 are also creatures of habit, and it shows in their campaigns. This allows for researchers to make multiple campaigns together through direct connections and similarities in the campaigns themselves.
COBB: Are there particular industries likely to be impacted by ITG16 activity?
CHUNG: Because the North Korean government is undergoing rapid geopolitical situation over its nuclear programs and its economies continue faltering, North Korea government has no choice but to seek an exit strategy to keep their economy afloat while saving their face in the foreign policy area.
So, therefore, I will not be surprised to see addition of ITG16 campaigns against industries like governments, universities, academic think tanks, non profits or even financial sectors because North Korea government has a dual task to keep its economy going when trying to make diplomatic breakthrough via intel gathering.
COBB: So, with that, does IRIS expect to see more of ITG16?
CHUNG: There has been a resurgence of activity from ITG16 in the past several months after some hiatus.  We’re not exactly clear what prompted the results…resurgence of activity from this group.
However, continued deterioration in the North Korean economy coupled with vast changing geopolitical tension in the East Asia may have likely precipitated urgency to conduct increased operations, you know, in order to get money and information.
Therefore, we do expect to see more of ITG16 activities in the near future to advance North Korean government interests politically and financially.  Even during the news of possible death of North Korean leader — that was like as of April 27th — we have continued to observe malware being developed and possibly by a North Korean group.  And as it turned out, the leader eventually reemerged, and so we expect ITG16 activities will likely continue.
CASTILLO: Yes, I would like to add that we expect ITG16 to continue their operations which will likely include the current geopolitical landscape and current event themed campaigns like the COVID‑19 pandemic.
APT groups jump at the chance to take advantage of people’s emotions. APT groups right now have a treasure trove of COVID‑19 themed lures to use due to the overall panic, misinformation, fake news and the uncertainty of the future during these trying times.
People really need to take a step back and pay attention to detail when thinking about opening e‑mail attachments or searching for news. Like most APT groups, we expect ITG16 to adapt and evolve their TTPs in response to our industry proactively hunting and reacting to their campaigns. This conversation that we have today will look completely different if we had it, say, two years from now.
COBB: Well, based on what Ryan just said, it sounds like there may be a very tiny bright spot.
CHUNG: Yes, because this is the nation state, they are predictable. And so if anything happens in the Korean peninsula, looking at the geopolitical landscape, you can be sure certain organizations could be a likely target, for example, governments or think tanks or universities.
And those organizations could prepare themselves for onslaught of phishing campaigns. So, at least some organizations looking at the geopolitical landscape can mitigate the threats going forward.
COBB: How can an organization contact IRIS if they think they’re under attack?
CASTILLO: Ah, yes, Pam, thank you for asking. If you’re an organization and believe you might be under attack, the best thing for you to do is call the IBM X‑Force Emergency Response Hotline, and that number is (888) 241‑9812.
COBB: Well, thank you both so much for joining us. It’s always incredible to learn more about the real activity of the threat actors out there in the market.  So, thank you so much.
MOULTON: So, Pam, as always, fascinating conversation. What was your biggest takeaway?
COBB: Really I think it’s down to the idea that, you know, ITG16 are creatures of habit, so in seeing the same repeated attack patterns over and over, that’s what really lets researchers find those similarities in campaigns and link them back to one threat actor group.
So, like still bad that there’s threat actor groups out there, but the predictability, I think, is one of those things that helps us as those on the front lines kind of, you know, helping stop those threat actors.
MOULTON: And that’s it for the episode. Thanks to Ryan Castillo and Joshua Chung for joining us as guests.
COBB: If you missed it, I definitely recommend you check out our earlier conversation about another APT group, IGT08.  We’re on Apple Podcasts, Google Podcasts, SoundCloud and Spotify.  Subscribe wherever you get your podcasts.  Thanks for listening.
 













Megan Radogna







        Megan Radogna is a contributor for SecurityIntelligence.














Recent Articles




















More from X-Force



















Topic updates



                                    Get email updates and stay ahead of the latest threats to the security landscape, thought leadership and research.
                                    


                                                Subscribe today
                                          

















Analysis and insights from hundreds of the brightest minds in the cybersecurity industry to help you prove compliance, grow business and stop threats.



Cybersecurity News
By Topic
By Industry
Exclusive Series
X-Force
Podcast
Events
Contact
About Us



Follow us on social

























© 2024 IBM
Contact
Privacy
Terms of use
Accessibility
Cookie Preferences




Sponsored by
                                          



si-icon-eightbarfeature



















Press play to continue listening




























00:00



00:00



























