# Reference for threat actor for "Wizard Spider, Gold Blackburn"

**Title**: Something strange is going on with Trickbot | Intel471

**Source**: https://intel471.com/blog/trickbot-2022-emotet-bazar-loader

## Content





























Something strange is going on with Trickbot | Intel471




























Skip to content












Return to Intel471 homepage.





















Platform













TITAN Cybercrime Intelligence Platform



Platform







Capabilities




Adversary Intelligence




Credential Intelligence




Malware Intelligence




Vulnerability Intelligence




Marketplace Intelligence














Gaining the Advantage with Covert Cyber HUMINT



Delve deep into the world of Cyber Human Intelligence (HUMINT) — where traditional human intelligence meets the digital world. Discover the strengths, challenges, and best practices to arm your organization with advanced, holistic defense strategies.








Solutions







Identity & Access




Compromised Credential Management




Account Takeover Protection






Risk & Compliance




Insider Threat Mitigation




Data or System Breach






Security Operations




Incident Response




Malicious Traffic Detection




Threat Hunting






Third-Party Risk




Breach Monitoring




Compromised Credential Monitoring




Vulnerability Monitoring




Attack Surface Monitoring






System Integrity




Vulnerability Management




Attack Surface Protection






Fraud Protection




Fraud




Brand Protection




PII Abuse












"A major factor that distinguishes Intel 471 from competitors is its emphasis on specific target profiles... No other product was found to offer this valuable capability."

- U.S. Government Agency









Resources







Resource Center




Intel 471 Blog




White Papers




Data Sheets






471 Live




Podcasts




Webinars On-Demand






Tools & Support




Cyber Underground Handbook




Glossary




Attack Surface Documentation








Trending Article



A Ransomware Forecast for 2023



There were signs of change in 2022 for ransomware. We explore what defenders may see this year.









Company







Intel 471




About Us




Leadership




Careers




News & Press




Contact Us






Events




Trade Shows & Conferences




Webinars On-Demand






Partners




Technology Partners




Channel Partners




Industry Partners












"More sources, a better understanding of the threat landscape, and better professionals working undercover in the darkest corners of the cybercrime world."

- E.U. Electronics Manufacturer










Let's Talk



























blog article

Something strange is going on with Trickbot
There hasn't been any new activity from this malware in 2022. Why? 
Feb 24, 2022

























Share this article on Facebook



Share this article on Facebook






Share this article on Twitter



Share this article on Twitter






Share this article on LinkedIn



Share this article on LinkedIn





















It’s been a turbulent 18 months for Trickbot.
The notorious modular malware has been in the spotlight, largely due to actions taken by both private companies and the U.S. government to thwart the attacks. Even as U.S. Cyber Command and Microsoft seized servers and the U.S. Department of Justice arrested several people alleged to be involved with the group that runs the malware, Trickbot stayed active throughout 2021 with various infection campaigns. 
These sporadic periods of activity have not continued into 2022. From December 28, 2021 until February 17, 2022, Intel 471 researchers have not seen new Trickbot campaigns. While there have been lulls from time-to-time, this long of a break can be considered unusual. Our team assesses with high confidence that this break is partially due to a big shift from Trickbot’s operators, including working with the operators of Emotet. 
Trickbot’s recent behavior
Examination of individual malware campaigns, tracked by identifiers known as “gtags,” further show there has been a lull in activity since mid-December 2021. These gtags are often listed as a three-letter term followed by a three-number sub-tag that further delineates individual campaigns. Intel 471 researchers tracking “lipXXX” campaigns show that the latest builds, categorized as “lip166,” came on December 28, 2021. That was one of three malware campaigns that were active during the month. As a contrast, eight different “lipXXX” builds were discovered in November 2021. 
We found a similar pattern in campaigns with a “topXXX” gtag. The last known build came from the “top166” gtag on December 28, 2021, which was one of three “topXXX” builds in December. Yet eight separate “topXXX” builds were discovered the prior month. 
In addition to the unusual disappearance of new builds (gtags), we have also observed that the onboard malware configuration files (mcconf), which contain a list of controller addresses the bot can connect to, have gone untouched for long periods of time. The most recent mcconf version numbers are 100021 (Dec 9) and 2000036 (Oct 25). These were once updated frequently, but are receiving fewer and fewer updates. It should be mentioned that Trickbot can receive controller address list updates on-the-fly, so the lack of updates could mean that there isn’t anyone cleaning up Trickbot controllers nor is there any pressure to update the on-board controller list. 
The scarcity of campaigns only tells part of the story. While the campaigns themselves have been quiet, command and control infrastructure tied to Trickbot continues to operate normally, serving additional plugins, web injects and additional configurations to bots in the botnet. This activity shows that while there haven’t been any new campaigns, there is evidence of some effort to maintain Trickbot’s command and control infrastructure, even if that effort is essentially an automated one. 
Looking at this holistically, this is unusual behavior, but it’s part of a trend that Intel 471 and other researchers have been observing for several months. The amount of Trickbot campaigns observed by researchers has continuously decreased over time. However, the amount of ransomware deployments of ransomware families linked with Trickbot, such as Conti, has continued. What can we deduce from this behavior? 
Trickbot’s new teammates
Our team assesses with high confidence that Trickbot operators are working closely with the operators of Emotet. There is clear evidence of this relationship, for example, the resurrection of Emotet began with Trickbot. On November 14, 2021, we observed Trickbot pushing a command to its bots to download and execute Emotet samples. This marked the beginning of the return of Emotet. 
Even before this event, Trickbot and Emotet operators had a relationship. Emotet was often used to drop Trickbot samples until the Emotet takedown. These Trickbot samples often had the gtag “morXXX.” The relationship worked both ways: Intel 471 has observed commands from Trickbot controllers to download and execute Emotet, long before the Emotet’s 2021 return.
Intel 471 cannot confirm, but it’s likely that the Trickbot operators have phased Trickbot malware out of their operations in favor of other platforms, such as Emotet. Trickbot, after all, is relatively old malware that hasn’t been updated in a major way. Detection rates are high and the network traffic from bot communication is easily recognized. 
Another crucial piece of the puzzle is the Bazar malware family, which has development ties to the Trickbot group. Multiple threat actors leverage this stealthy backdoor to gain an initial foothold into high-value targets and execute follow-up payloads, such as Cobalt Strike and IcedID aka Bokbot. We have also seen Bazar controllers pushing commands to download and execute Trickbot (mid-2021) and Emotet (November 2021). These events connect Bazar to Trickbot operators, as well as to the revival of Emotet.
Bazar, Bokbot and Emotet likely aren’t the only tools leveraged by the threat actor group ditching Trickbot. Our monitoring registered instances of Trickbot pushing Qbot installs to bots of the Trickbot botnet shortly after the Emotet return from November 2021. This observation is yet another indicator that the Trickbot bots are being migrated to other malware platforms.

DateBot TransferPayload URLNotesFeb 7, 2020Trickbot -> Emotethttp://66[.]85.173[.]43/59Emotic1.jpgonly morXXX bots received this commandApr 1, 2020Trickbot -> Emotetnone, payload direct from C2only morXXX bots received this commandSep 16, 2020Trickbot -> Emotethttp://104[.]193.252[.]221/FortiPlan1.gifonly morXXX bots received this commandNov 14, 2021Trickbot -> Emotethttp://141[.]94.176[.]124/Loader_90563_1.dllFirst stage of Emotet’s resurrection campaign (bots with all gtags received the command)Nov 24, 2021Bazar -> Bokbotnone, payload direct from C2Bokbot project ID BA205ACANov 26, 2021Bazar -> Emotetnone, payload direct from C2Dec 9, 2021Trickbot -> Qbothttp://46[.]30.41[.]173/stager2.dllQbot botnet ng_domain
Avoiding the spotlight
Despite the takedowns by U.S. Cyber Command in October 2020, Trickbot remained active into 2021. However, with the arrests of two alleged Trickbot developers and an in-depth Wired article that details alleged internal conversations from the group’s leadership, Trickbot is under more scrutiny than ever before. 
Perhaps a combination of unwanted attention to Trickbot and the availability of newer, improved malware platforms has convinced the operators of Trickbot to abandon it. We suspect that the malware control infrastructure (C2) is being maintained because there is still some monetization value in the remaining bots. 
Intel 471 will continue to track Trickbot and will report on any further observations in the future. 









Related Blogs








How Discord is Abused for Cybercrime







Cybercrime Exposed Podcast: Botnet Breakup







Medibank’s Attacker: IT Businessman, Claimed Psychologist and Alleged Cybercriminal







Testing the Efficacy of Security Software












Sign up for our Executive Intel Update


Stay informed with our weekly executive update, sending you the latest news and timely data on the threats, risks, and regulations affecting your organization.




Sign Up Today












Return to Intel471 homepage.


















Whether scaling your cybersecurity presence or starting to build your team, we help you fight cyber threats.





Meet with an expert




+1 (800) 833-1471











Company




Leadership




Careers




News & Press




Contact Us






Resources




Data Sheets




Webinars On-Demand




White Papers










Platform




Adversary Intelligence




Credential Intelligence




Malware Intelligence




Vulnerability Intelligence




Marketplace Intelligence










Solutions




Vulnerability Monitoring




Attack Surface Protection




Incident Response




Compromised Credential Monitoring




Threat Hunting
















© 2024 Intel471
 | 

Privacy Policy

 | 

Terms of Service

 | 

End User Agreement

 | 

Modern Slavery and Human Trafficking Statement








Find Intel471 on Facebook







Find Intel471 on YouTube







Find Intel471 on Twitter







Find Intel471 on LinkedIn







Find Intel471 on Instagram


































Trending Searches



Trending



cyber security




Trending



covid-19




Trending



breach




Trending



malware





Popular Resources









Article

ERMAC 2.0: Perfecting the Art of Account Takeover












Datasheet

Malware Intelligence












Article

Here’s how to use Intel 471 with existing intelligence frameworks




























Featured Resource









AresLoader is a new loader malware-as-a-service (MaaS) offered by threat actors with links to Russian hacktivism that was spotted recently in the wild.




Read full article












Platform











Titan




Adversary Intelligence




Credential Intelligence




Malware Intelligence




Vulnerability Intelligence




Marketplace Intelligence








Solutions











Compromised Credential Monitoring




Account Takeover Protection




Insider Threat Mitigation




Data or System Breach




Incident Response




Malicious Traffic Detection




Threat Hunting




Breach Monitoring




Compromised Credential Monitoring




Vulnerability Monitoring




Attack Surface Monitoring




Vulnerability Management




Attack Surface Protection




Fraud




Brand Protection




PII Abuse








Resources











Intel 471 Blog




White Papers




Data Sheets




Podcasts




Webinars On-Demand




Cyber Underground Handbook




Glossary




Attack Surface Documentation








Company











About Us




Leadership




Careers




News & Press




Contact Us




Trade Shows & Conferences




Industry Partners




Channel Partners




Technology Partners








Let's Talk





Find Intel471 on Facebook







Find Intel471 on YouTube







Find Intel471 on Twitter







Find Intel471 on LinkedIn







Find Intel471 on Instagram








© 2024 Intel471
 | 

Privacy Policy

 | 

Terms of Service

 | 

End User Agreement

 | 

Modern Slavery and Human Trafficking Statement








