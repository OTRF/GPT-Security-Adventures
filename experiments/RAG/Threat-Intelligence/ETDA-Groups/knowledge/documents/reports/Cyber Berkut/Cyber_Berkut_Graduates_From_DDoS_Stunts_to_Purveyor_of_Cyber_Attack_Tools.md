# Reference for threat actor for "Cyber Berkut"

**Title**: Cyber Berkut Graduates From DDoS Stunts to Purveyor of Cyber Attack Tools

**Source**: https://www.recordedfuture.com/cyber-berkut-analysis/

## Content
Cyber Berkut Graduates From DDoS Stunts to Purveyor of Cyber Attack ToolsCareersContact UsLoginPlatformSolutionsProductsServicesResearchResourcesCompanyGet a demo
Book a demo
BlogCyber Berkut Graduates From DDoS Stunts to Purveyor of Cyber Attack ToolsPosted: 8th June 2015By: RODRIGOAnalysis Summary

Recorded Future has collected threat intelligence on Cyber Berkut for over a year as the group advanced from perpetrating crude DDoS to distribution of proprietary cyber attack tools and high-level leaks.

Temporal analysis shows the group to be well-coordinated hacktivists that have been digitally active since the first few days of fighting in Ukraine.

The group has leaked documents from multiple Ukrainian government agencies, including alleged plans for Western intervention in the conflict.

Recorded Future analysis identified a Cyber Berkut-associated dark website, accessible as of late May 2015.

Cyber Berkut remains active across multiple domains and effective in their online propaganda efforts, with cyber attacks against Western and Ukrainian targets likely to continue.




Recorded Future has collected threat intelligence on the hacking activities of Cyber Berkut for over a year, aligning with the first month of ground fighting in Ukraine, at which time the group began coordinated cyber attacks. This article presents temporal and technical analysis of these activities, based on open source intelligence (OSINT) from the Web. Appropriating the Ukrainian special police force name and logo, the group has aligned itself as pro-Russian, anti-Ukrainian, and most recently attacked Western intervention efforts in the Ukrainian conflict. While the group has taken Ukrainian identities, technical links and contextual analysis connect the group to Russia.
The group began with successful distributed denial of service (DDoS) attacks on multiple NATO websites just as separatists in the physical world were beginning to storm military buildings. Since their initial attacks the group has continued to take down websites, and most recently leaked confidential documents between US billionaire George Soros and the Ukrainian prime minister and president which contained plans for Western intervention.

Click image for larger view
The timeline image above shows the full year of activity for Cyber Berkut, from their initial DDoS attacks to attack tool distribution and subsequent high-profile leaks. The group has also been purportedly active in hacking the physical domain, as evidenced through multiple videos showing hacked billboards in the Ukrainian capital, Kiev, displaying anti-Ukrainian propaganda images of “war crimes.”
Recorded Future initially alerted on the latest leaks within hours, listing Cyber Berkut as the top threat actor. The following dashboard view is a snapshot of Recorded Future Cyber taken at the time of the reported Cyber Berkut attack. Each data point is collected and organized by Recorded Future technology and represents an organization or sponsor country that has been reported on the Web as an attacker or threat actor.

Drilling down on the recent activity, the initial chatter around the attack centered on social media where various users began sharing the leaked documents. The links pointed directly to the Cyber Berkut website, where the documents were hosted.

Click image for larger view
The documents hosted on the Cyber Berkut site appear to be original documents, including “Confidential” watermarks on strategic plans for military assistance. Neither the US government or the Soros Foundation have commented on the validity of the documents. The group claimed the documents showed the real “owners of the Ukrainian regime” following their standard procedure of propagandizing documents to fit an anti-West, pro-Russian narrative.

The Russian Connection
Turning to the group’s own site for analysis, a good starting point is their registration information. A WHOIS lookup shows that the group initially created the domain in the first few days of fighting in March 2014. The site is registered using a private front which makes attribution more difficult, but the temporal information illustrates the group was quick to establish an online presence as coordinated violence was just beginning to occur offline.

Corroborating the Russian connection, the group hosts clones of their site on .ru and .net TLD. WHOIS lookups for both sites show the .net was created two months after the original site, with the Russian site following four months after.


While the group has clear technical ties to Russia, contextual evidence from their manifestos and propaganda posts provides further insight. From their first posts, the group posted in Russian language instead of Ukrainian, and they have continued to copy common Russian propagandist views in their characterization of the enemy. For example, in recent mainstream coverage of Russian “trolls” conducting information operations online for the government, enemies are commonly associated with fascism and Nazism. Cyber Berkut spreads these views across many of their posts, with some explicitly attempting to tie fascist sympathy to leaked documents and statements.

Above: Cyber Berkut statements echoing Russian propaganda claims of fascism.
Covered Tracks on Targets and Tool Distribution
The Cyber Berkut group has also removed two components of its site in recent months. One was an “Army” page used to crowdsource involvement through the promise of a special “cyber weapon” developed to DDoS targeted sites. The tool was released for Windows and Linux, and despite the page takedown, the download links for both tools remain live. The Windows link on the site claimed a “new” version, indicating the group had further developed the tool.

Above: The now defunct “CyberArmy” page with translated call-to-action and tool downloads.
When checked with VirusTotal, the timestamped data indicated the Linux and Windows file were both initially checked May 2014 and have not been checked in nearly a year. No anti-virus companies currently flag either file as malware. Considering many hacktivist DDoS tools are commonly flagged, this indicates the group may have actually developed a tool, or just as likely taken the step to repackage it to pass anti-virus mitigations.


Above: VirusTotal results for Linux and Windows attack tools.
The tools include a copy of Python, Tor, and the proprietary tool with instructions for use. The group uses Tor to obfuscate connections to a “control center” and they emphasize that it’s not malicious to users since they can view the source at any time. The folder also includes a “hostname” note with a link to an Onion site on the darknet: epwokus5rkeekoyh.onion. While the site was down at the time of publication, a historical search in Recorded Future indicates the site was accessible as of late May 2015.

Click image for larger view
Above: Recorded Future results indicating the Cyber Berkut dark website active as of May 28, 2015.


Above: Screenshots of the tool download and included instructions on use.
Looking at the tool source code, the group uses various versions of Mozilla Firefox and Opera as user agents when DDoS’ing targets. The most recent version of the tool was compiled about a week before going live for direct downloads across all Cyber Berkut websites.

Above: Screenshot of the attack tool source code, with specific user agents.

Above: PeStudio analysis of the tool showing original creation date and signatures.
The other page taken down across Cyber Berkut websites was a so-called “Traitors” page, which listed documents and personal profiles of targeted Ukrainians. The documents purported to show military and corporate corruption in Ukraine, while the personal profiles were targeted attacks against prominent individuals, including the head of security services and major politicians.

Above: Screenshot of the now defunct “Traitors” page with leaked documents and personal targets.
The personal profiles include photos, educational background, work history, and a full range of accusations from pederasty to political corruption listed as “Facts.” In most profiles, information is embedded with propagandist videos against the individuals.
Conclusion
Cyber Berkut is the latest high-profile hacktivist group to emerge as governments and non-state actors continue to participate in conflict online. While hacktivism has primarily consisted of crude defacements and low-level DDoS attacks, this group shows an evolution in direct distribution of proprietary tools and a rapid coordination to establish digital presence from the first days of ground fighting.
Both the billboard hacks and high-profile nature of the leaked documents also show the ability of inexpensive, rapid attacks to cause damage where conventional methods cannot. While the fighting was far from Kiev and government systems were unable to be physically damaged, Cyber Berkut was able to steal critical information and project information operations far from the front lines.
While attribution of cyber actors is difficult, technical analysis of the group’s domains and the context of their propaganda show clear ties to Russia. While the Russian government may or may not be involved, the rhetoric and political perspective evident in the Cyber Berkut hacks are closely aligned with views expressed in Russian media. Cyber Berkut continues to be effective online and we can expect more attacks from them in the coming days of the Ukrainian conflict.
About usIntelligence CloudServices & SupportResearchResourcesCompanyHelpful linksCareersContact UsGet a DemoThe Intelligence GraphJoin us onlineWant to learn more?Contact us today
Copyright © 2024 Recorded Future, Inc.Security FAQCookiesPrivacy PolicyTerms & Conditions