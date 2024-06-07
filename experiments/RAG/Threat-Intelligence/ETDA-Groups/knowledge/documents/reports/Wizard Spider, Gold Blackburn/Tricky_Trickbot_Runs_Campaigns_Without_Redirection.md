# Reference for threat actor for "Wizard Spider, Gold Blackburn"

**Title**: Tricky Trickbot Runs Campaigns Without Redirection

**Source**: https://www.f5.com/labs/articles/threat-intelligence/tricky-trickbot-runs-campaigns-without-redirection

## Content




Tricky Trickbot Runs Campaigns Without Redirection
































































                FOLLOW US
            


Twitter
Labs on Twitter









LinkedIn
Labs on LinkedIn












                LATEST NEWS
            


RSS













Subscribe














F5 Sites


















DevCentral


F5.com







                        Sign In
                    



                        Sign In
                    




My Account


















My Profile




                                    Sign Out
                                



                                    Sign Out
                                



































Threats

























back

Threats









close





All Content


Research Series


Application Protection




Bots and Automated Attacks



reset focus




Learning Center




CISO




















open search










close search

Search



reset focus























toggle navigation












Threats

























back

Threats









close





All Content


Research Series


Application Protection




Bots and Automated Attacks



reset focus




Learning Center




CISO











                FOLLOW US
            


Twitter
Labs on Twitter









LinkedIn
Labs on LinkedIn












                LATEST NEWS
            


RSS













Subscribe














F5 Sites


















DevCentral


F5.com







                        Sign In
                    



                        Sign In
                    




My Account


















My Profile




                                    Sign Out
                                



                                    Sign Out
                                









reset focus














F5 Labs





Threat Intelligence







                    Fraud
                


Tricky Trickbot Runs Campaigns Without Redirection


                Known for redirection attacks, recent Trickbot banking trojan campaigns use server-side injection and target fewer victims.
            


                    By Doron VoolfRemi CohenMalcolm Heath




                    September 17, 2019
                

                    8 min. read
                






















Table of Contents












Active Campaigns Without Redirection










Active Campaigns With Redirection










How Banks React










Conclusion










Security Controls



















During June and July, F5 researchers first noticed Trickbot campaigns aimed at a smaller set of geographically oriented targets and did not use redirection attacks—a divergence from previous Trickbot characteristics.
In this research, we compared two different target configurations, one older, more “traditional” configuration that uses redirection, and a new Trickbot configuration that does not us redirection and exclusively uses dynamic injection.
The vast majority of all spotted Trickbot campaigns target US financial services institutions; a much smaller percentage target other industries, including cryptocurrencies, credit card companies, and e-commerce.
Notably, the access pages of financial services institutions, including single sign-on pages, are the most targeted, which indicates that access is still imperative in order to conduct lucrative cybercriminal attacks.

Trickbot, one of today’s most active banking trojans, was first reported on in 2016. It was originally known for its geographically centered campaigns targeting only the financial services industry. But it quickly expanded its targets to include credit card, wealth management, customer relationship management software companies. (For more background on Trickbot, check out the F5 Labs banking malware reference guide.)
Since 2016, Trickbot campaigns have continued to evolve. New campaigns are pivoting to be much more regionally focused, and they exploit using only one type of attack: dynamic Injection (Dinj), also known as server-side injection. The details of these attacks are stored in Dinj files. While the dynamic injection technique isn’t new, it is the first time it has been applied by Trickbot in such a geographically centered campaign.
Over the last few months, F5 researchers have gathered target configuration files from Trickbot campaigns and, for this analysis, compared two of the most different ones. (Note that the traditional Trickbot configuration we analyzed has not been active over the last four months.) Since there is such a stark difference in Trickbot’s current tactics, we used the older configuration as a comparison, which highlights Trickbot’s transition to attacking without redirection, because it is so much more sophisticated. The configurations we compared are v459, composed of new Trickbot tactics of shorter target lists and no redirection, and v420, a more traditional configuration that utilizes both redirection and dynamic injection attacks and has a very long target list.
Active Campaigns Without Redirection
Historically known for using redirection attackA user is forwarded from a trusted site to another, possibly malicious site.s, Trickbot is not using this tactic in some of its latest target configurations. This change, first noticed by F5 researchers in June and July, continues in August and September 2019. Along with the absence of target lists, redirection is also absent in the encrypted webinject files from the latest campaigns. There is no trace of the previous redirection targets alongside Dinj elements. While this seems to be an intentional shift in tactics, Trickbot continues to target the financial services industry, with 91% of targets on the v459 target list falling into this industry.









        
            Figure 1. Industries targeted in the Trickbot v459 configuration 
        
    



Breaking down the financial services industry further, these campaigns using dynamic injection are mostly continuing to target banking institutions and investment arms of banks.









        
            Figure 2. Breakdown of Trickbot v459’s dynamic injection targets in the financial services industry 
        
    



We postulate that Trickbot continues to target financial services with a narrow scope since server-side injection is a dynamic injection technique and needs to be very precise. Dynamic injection needs to make sure the injected content doesn’t break legitimate page behavior, and it must take into account that there could be other scripts defending the target page. This is an expensive attack, both in time to set up and insight needed about the target page infrastructure, which helps to explain the whittled down target list for campaigns using only this dynamic injection technique. It is also possible that the v459 target list is under maintenance, with targets that have performed poorly in past campaigns being culled out.
The current campaigns we sampled didn’t use redirection attacks. The geographic targeting is clearly against the U.S.









        
            Figure 3. Trickbot v459 target list by geolocation, broken out by country
        
    



Active Campaigns With Redirection
As stated earlier, the v420 Trickbot campaign utilizes traditional Trickbot tactics. Geographically, the top targeted countries are similar, but the v420 campaign has a broader reach, attempting to target users either logging into banks around the world or users based in certain locations for global institutions. Further, v420 has a much longer target list with 1,135 unique URIs, compared with v459’s 360 unique URIs. Along with that, the v420 target list casts a larger net. There are more smaller financial services institutions that are geographically dispersed. Along with the clear industry targeting included in the target list are a number of general extensions, redirection attempts, or URLs that do not resolve.









        
            Figure 4. Trickbot v420’s targeted industries by unique URL targeted
        
    



Similar to the v459 target configuration, when the financial services industry is broken out by segment, banks and investment banks are heavily targeted. Cryptocurrency exchanges also make up a portion of this list, which makes sense, due to their anonymity. Notably, due to the larger list size and the focus on Italy and Italian financial consulting firms, there is a broader spread in subindustry across the financial services industry.









        
            Figure 5. Trickbot v420 breakdown of the financial services industry by unique URL targeted
        
    



Geographically, the Trickbot v420 target file is more scattered than the v459 target file—not really targeting regionally, but targeting wealthy countries or countries known for their relaxed banking laws. Notably, Russia and China do not appear on this list at all. As of this analysis, Trickbot does not have official attribution to either a country or a group, and the list of nations not on this list may be telling.









        
            Figure 6. Trickbot v420 target list geographic distribution showing unique URLs targeted by country 
        
    



Further breaking down the “global” category of the geographic distribution from the v420 configuration, there were a number of URLs. Most URLs are general extensions/redirection attempts, which mean that they do not target one website specifically; instead, they are meant as a catchall. These were not seen in the same volume in the v420 configuration. Along with that, cryptocurrency exchanges are categorized as targeting a global market instead of an individual country anyone in the world can access them.









        
            Figure 7. Breakdown of Trickbot v420 global targets by specific industry
        
    



Overall, the Trickbot v420 and the v459 target files are similar in that they both heavily target financial services institutions and are geographically centered around the US. Digging a little deeper, the Trickbot v459 target list seems to be a more focused version of the v420 target file.
The behavior exhibited from the v420 target list is much more of a traditional Trickbot campaign and is more representative of the direction, based on previous behaviors, in which analysts thought Trickbot seemed to be going. F5 threat researchers speculate that the recent change could be in defense of some action taken against the malware’s authors or supporting infrastructure.
How Banks React
Targeting users is not uncommon. Banks have known from inception of the Internet that they would be an obvious target for attackers. In response, banks have hardened their websites to the point where the best way in is through a human. So instead of attacking the bank’s website, malicious actors go after users. On the target files analyzed, many of the targets are specific access points to the institution. Notably, some banks that were on the v420 target list have acknowledged this publicly and warn users about this danger.









        
            Figure 8. Example of a bank warning users about Trickbot and other banking trojans
        
    



The example shown in Figure 8 is from a bank only seen in the v420 target list, but these warnings are not only put out by smaller institutions. Banks need to find ways to let users know who to trust and make them aware of the resources available to them. Making sure this information is on the page of Google search results helps them to try to keep users safe.
Conclusion
Researchers can only speculate why Trickbot has dropped the redirection attack vector in some of its newest, active campaigns. The v459 target list is much more focused and may be under maintenance, to just fixate on the top preforming targets. Researchers hypothesize that this may be due to the need for a lot of computing power and servers to support the large waves of spam campaigns—and to keep steady pressure on infected users in order to steal money. Whatever the reason for the change, Trickbot remains an active and engaged threat to financial services institutions and their users.






Download the Trickbot v459 and v420 target lists here






  
Security Controls
The following security controls are recommended in order to mitigate these malware attacks.







Technical



Preventative


Deploy a web application firewall.
Implement multifactor authentication.
Implement web fraud protection to detect infected clients logging into your applications.
Use an intrusion detection system to catch trojan malware.








Technical



Detective


Continuously monitor the health of critical systems.
Implement endpoint protection on all points of entry to your network in order to prevent and detect fraud trojans.








Administrative



Preventative


Train application developers in secure coding practices.
Provide security awareness training to employees and customers.








Administrative



Corrective


Review access controls.
Notify customers of malware detected on their systems during login so they can take steps to clean their systems.












            Join the Discussion
        












            To comment, first sign in and opt in to Disqus.
            Sign In













            To comment, first opt in to Disqus.
            View Disqus opt in options





        Please enable JavaScript to view the comments powered by Disqus.






        Authors & Contributors
    





















                    Doron Voolf (Author)


                    Malware Analyst
                

About Doron
All Articles








reset focus











close





















Doron Voolf

							Malware Analyst, F5
						



Working at F5 for 5 years, Doron handles and analyzes cyber threat investigations for most of the major banking malware families in recent years. Doron holds a Bachelor of Science focused in Computer Science.

Latest Articles



Top Risks
06/11/2020



								Qbot Banking Trojan Still Up to Its Old Tricks
							



article

6 min. read




IoT
04/24/2020



								Mirai “COVID” Variant Disregards Stay-at-Home Orders
							



article

7 min. read




IoT
12/26/2019



								Gafgyt Targeting Huawei and Asus Routers and Killing Off Rival IoT Botnets
							



article

7 min. read




Fraud
09/17/2019



								Tricky Trickbot Runs Campaigns Without Redirection
							



article

8 min. read




See All Articles by Doron Voolf



reset focus





















                    Remi Cohen (Author)




About Remi
All Articles








reset focus











close





















Remi Cohen

							F5
						



Remi Cohen was a Threat Research Evangelist with F5 Labs. Prior to F5 she worked for a large national laboratory conducting vulnerability assessments, and research on current threats as well as an civilian analyst for the US Department of Defense. Her specialty areas of research include mobile vulnerabilities, Industrial Control Systems, and Eastern European threats. She is an associate of (ISC)2 by passing the CISSP exam and is certified in both COMPTIA Security+ and ECCouncil C|EH. She holds a Master’s degree from New Mexico State University in Industrial Engineering as well as Bachelor’s degrees in Computer Science and Government from Georgetown University.

Latest Articles



Strategies
12/14/2023



								2024 Cybersecurity Predictions
							



article

12 min. read




Strategies
12/05/2022



								5 Cybersecurity Predictions for 2023  
							



article

11 min. read




Strategies
01/18/2022



								Cybersecurity Predictions for 2022 from F5 Labs (and Friends)
							



article

13 min. read




IoT
04/24/2020



								Mirai “COVID” Variant Disregards Stay-at-Home Orders
							



article

7 min. read




See All Articles by Remi Cohen



reset focus





















                    Malcolm Heath (Author)


                    Sr. Threat Researcher
                

About Malcolm
All Articles








reset focus











close





















Malcolm Heath

							Sr. Threat Researcher, F5
						



Malcolm Heath is a Senior Threat Researcher with F5 Labs.  His career has included incident response, program management, penetration testing, code auditing, vulnerability research, and exploit development at companies both very large and very small. Prior to joining F5 Labs, he was a Senior Security Engineer with the F5 SIRT.

Latest Articles



Top Risks
01/24/2024



								Sensor Intel Series: Top CVEs in December 2023
							



article

9 min. read




Sensor Intel Series
12/19/2023



								Sensor Intel Series: Top CVEs in November 2023
							



article

6 min. read




Strategies
12/14/2023



								2024 Cybersecurity Predictions
							



article

12 min. read




Sensor Intel Series
11/27/2023



								Sensor Intel Series: Top CVEs in October 2023
							



article

6 min. read




See All Articles by Malcolm Heath



reset focus








TAGS:

Client-side Attacks


Client-platform malware


Threats


Cybercrime


Client


banking trojan


Web Application Attacks


Redirection


Injection


Dynamic Injection


Access Tier


Credential Theft


Fraud


Services Tier


Trojan


Trickbot




















				F5 Labs Newsletter
            














						Great! You should receive your first email shortly.
					





The information you provide will be treated in accordance with the F5 Privacy Notice.























App Tiers Affected












Attack Type:


Client-side Attacks


Web Application Attacks




Attack Method:


Injection


Client-platform malware


Credential Theft




Attack Motive:


Cybercrime




Malware Type:




Malware / Campaign Name:


Trickbot





Affected Tiers




Client









Services





Access





TLS





DNS





Network







Client
Services
Access
TLS
DNS
Network


































What's trending?





Forward and Reverse Shells







                                    Forward and Reverse Shells
                                


                                Learn how attackers use server initiated connections and other clever tricks to deliver shells to attackers, circumventing inbound firewalls and access controls.
                            


                                    09/15/2023
                                

article


                                    5 min. read
                                







Web Shells: Understanding Attackers’ Tools and Techniques







                                    Web Shells: Understanding Attackers’ Tools and Techniques
                                


                                Explore the concept of web shells, their usage by attackers, and effective defenses against this post-exploit activity in this article by F5 Labs.
                            


                                    07/06/2023
                                

article


                                    6 min. read
                                







What Is Zero Trust Architecture (ZTA)?







                                    What Is Zero Trust Architecture (ZTA)?
                                


                                Learn what zero trust architecture (ZTA) is and how to apply it to your environment.
                            


                                    07/05/2022
                                

article


                                    13 min. read
                                












            Load more stories





















                        F5 Labs Newsletter
                    


One email per quarter
Latest security research insights
CISO-level expert analysis
Newsletter exclusives






                            F5 Labs Newsletter
                        










The information you provide will be treated in accordance with the F5 Privacy Notice.






Great! You should receive your first email shortly.

                    Thanks for signing up! Get started with some of the articles below:
                




2023 Identity Threat Report: The Unpatchables




                                        Top Risks
                                    

                                        11/01/2023
                                    



                                        2023 Identity Threat Report: The Unpatchables
                                    



report


                                        80 min. read
                                    







Sensor Intel Series: Top CVEs in December 2023




                                        Top Risks
                                    

                                        01/24/2024
                                    



                                        Sensor Intel Series: Top CVEs in December 2023
                                    



article


                                        9 min. read
                                    







Bots Cheat to Win




                                        Bots and Automated Attacks
                                    

                                        02/05/2024
                                    



                                        Bots Cheat to Win
                                    



article


                                        17 min. read
                                    



















        Research & Insights Featured On
    

































image/svg+xml













ResourcesResources


Threat Research


Application Protection


Bots & Automated Attacks


Learning Center


CISO




F5 SitesF5 Sites


F5.com


DevCentral




Follow UsFollow Us


X @F5Labs


LinkedIn


RSS








©2024 F5 Networks, Inc. All rights reserved.




                            Trademarks
                        



                            Policies
                        



                            Privacy
                        



                            California Privacy
                        



                            Do Not Sell My Personal Information
                        

















F5 Labs Newsletter

One email per quarter
Latest security research insights
CISO-level expert analysis
Newsletter exclusives









Great! You should receive your first email shortly.

                                Thanks for signing up! Get started with some of the articles below:
                            




11/01/2023



                                                2023 Identity Threat Report: The Unpatchables
                                            


80 min. read






01/24/2024



                                                Sensor Intel Series: Top CVEs in December 2023
                                            


9 min. read






02/05/2024



                                                Bots Cheat to Win
                                            


17 min. read
















The information you provide will be treated in accordance with the F5 Privacy Notice.











                        You already have a subscription
                    

















