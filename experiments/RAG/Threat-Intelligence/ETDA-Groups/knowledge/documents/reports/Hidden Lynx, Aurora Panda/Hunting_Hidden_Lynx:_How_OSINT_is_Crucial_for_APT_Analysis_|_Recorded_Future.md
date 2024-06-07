# Reference for threat actor for "Hidden Lynx, Aurora Panda"

**Title**: Hunting Hidden Lynx: How OSINT is Crucial for APT Analysis | Recorded Future

**Source**: https://www.recordedfuture.com/hidden-lynx-analysis/

## Content
Hunting Hidden Lynx: How OSINT is Crucial for APT Analysis | Recorded FutureCareersContact UsLoginPlatformSolutionsProductsServicesResearchResourcesCompanyGet a demo
Book a demo
BlogHunting Hidden Lynx: How OSINT is Crucial for APT AnalysisPosted: 1st May 2014By: CHRISAnalysis Summary

Visualization of open source intelligence on APTs reveals overlapping infrastructure, tools, and exploits used in the VOHO campaign and Operations Aurora, DeputyDog, and Ephemeral Hydra.

Two vulnerabilities were identified as exploited by Hidden Lynx in its VOHO campaign (2012) and the Elderwood Gang responsible for Operation Aurora (2010). Command and control infrastructure was also shared between Hidden Lynx and threat actors responsible for two campaigns during 2013: Operation DeputyDog and Operation Ephemeral Hydra.

Threat intelligence derived from disparate open web sources bolsters security efforts by identifying and contextualizing links between threat actors.


When the_New York Times_ and Mandiant last year unmasked a large scale Chinese hacking operation, pinpointing its location down to the building, the report drew mainstream attention to what security professionals already well knew: sophisticated threat actors carry out persistent cyber operations over months and years.
This post illustrates how open source intelligence (OSINT) from the web is not only useful but crucial to threat intelligence teams analyzing advanced persistent threats. Through OSINT analysis, we discover clues to APT attack methods that link together the research of independent threat intelligence teams, suggesting new lines of analysis that were not prominent when looking at the work of any single threat intel team in isolation.
We will detail how the C&C infrastructure and tools used by hacker group Hidden Lynx during its VOHO campaign (2012), excellently documented by Symantec researchers last September, overlap with tools used in other high profile operations during the past few years. The other campaigns evaluated are Operation Aurora (2010), Operation DeputyDog (2013), and Ephemeral Hydra (2013).
History of Hidden Lynx Malware
Security researchers have shown time and again that cyber actors frequently recycle effective attack methods. These attack methods retain telltale signatures even as a threat actor’s targeting and tools evolve. Therefore, our investigation looked for clues that linked hackers across one or more of the campaigns in question.
Seeking to tease out any possible links between Operation Aurora, VOHO, Operation DeputyDog, and Ephemeral Hydra, we began with Symantec’s Hidden Lynx report as our foundation. The authors of that report identify three primary tools used in the campaigns attributed to Hidden Lynx: Trojan.Naid, Backdoor.Moudoor, and Backdoor.Hikit.
Using Recorded Future, we quickly built a timeline of the reported use of those tools in major security incidents, finding many events prior to the early 2013 exposé on Hidden Lynx.

Click image for larger view
Connecting the Dots
Our analysis, based solely on information openly available on the web, builds on significant technical research that has explicitly linked elements of the aforementioned campaigns. In particular, FireEye during the fall of 2013 called out infrastructure overlap between Ephemeral Hydra and DeputyDog.
Aspects of these two campaigns used tools and C&C infrastructure reportedly used by Hidden Lynx. These include a Hydraq/McRAT variant with lineage traceable to Aurora. Symantec during 2012 linked the Elderwood Project to Operation Aurora; Trojan.Naid and Backdoor.Moudoor were also used in Aurora, by the Elderwood Gang, and by Hidden Lynx.
A brief summary of targets for each campaign:

Aurora: Technology, Finance, Energy and Defense

Elderwood: Defense and Supply Chain

VOHO: Government, Defense, and Education (Hidden Lynx separately targeted Finance)

DeputyDog: Government (Japan and China)

Ephemeral Hydra: Government and Defense


Much of the above was well documented. However, some connections described over the course of several years, oftentimes by different research teams published across a variety of sources, are difficult to recall or might even be obscured by more recent information.
What links did we discover in analysis using Recorded Future?

Two vulnerabilities were found to be exploited by both the Elderwood Gang and Hidden Lynx: CVE-2012-1875 and CVE-2012-1889.

One of those common exploits, targeting CVE-2012-1889, was on November 22, 2012 reportedly added to the “popular” Gong Da exploit kit.

Three C&C servers were known to be shared between VOHO and various elements of Operation DeputyDog and Operation Ephemeral Hydra: 58[.]64[.]143[.]244, 66[.]153[.]86[.]14, 111[.]68[.]9[.]93

Backdoor.Hikit, which appears to have been developed post-Operation Aurora, was used in both VOHO and DeputyDog campaigns.

Reported use of the Hydraq Trojan from Aurora (2010) fell off until September 2012. The delivery method appears to have then switched from spearphishing to a watering hole attack when a variant of Hydraq was discovered in Ephemeral Hydra during November 2013.



Click image for larger view
The above network shows relationships between three tools used by Hidden Lynx during its VOHO campaign: Trojan.Naid, Backdoor.Moudoor, and Backdoor.Hikit. The connections indicate actors, targets, vulnerabilities, and technical information related to those tools. Note the density of connections between Moudoor and Naid, which are commonly reported as complementary tools.
Trojan.Naid specifically was used to attack security firm Bit9 ultimately compromising its digital code signing certificate. This allowed the hackers to then take on higher value targets as part of the VOHO campaign. Naid was also used in the 2010 campaign known as Operation Aurora.
One of the key findings noted above was the identification of two vulnerabilities that were exploited by both Hidden Lynx and the Elderwood Gang, which has been linked to Operation Aurora. CVE-2012-1875 and CVE-2012-1889 are at the center of the network below, surrounded by targets and other related vulnerabilities.

Click image for larger view
After visualizing these links, we explored the vulnerabilities at the edges of the graph, looking for connections with exploits used in other campaigns. We found such a link in CVE-2013-3893, which was leveraged in the August 2013 attacks on Japanese targets that FireEye dubbed Operation DeputyDog.
Similar to our approach with Symantec’s report on Hidden Lynx, we used Recorded Future to organize the technical details about the DeputyDog attacks to reveal technical information described in the open source reporting across multiple campaigns.

Click image for larger view
The above network shows technical details and locations, both server hosts and targets, related to Operation DeputyDog. This enabled creation of useful lists for us to seek overlap with other operations, establish the timing of exploits and C&C infrastructure used, and arrange alerts for ongoing monitoring.
To wrap up our investigation, we built a timeline of events related to the IP addresses associated with both Hidden Lynx campaigns as well as operations DeputyDog and Ephemeral Hydra. The timeline details events related to the three previously cited IPs – 58.65[.]143[.]244, 66[.]153[.]86[.]14, and 111[.]68[.]9[.]93 – used in both the Bit9 attacks and either DeputyDog or Ephemeral Hydra.
Analysts were able to track 66[.]153[.]86[.]14 back to an email address linking DeputyDog and the Hidden Lynx VOHO campaign. Separate analyses in November 2013 describe C&C servers used by Trojan.APT.9002 also used in the Hidden Lynx attacks against Bit9.

Click image for larger view
Revealing Links and Context With Web Intelligence
This investigation sheds new light on these campaigns, without depending on private or freshly disclosed technical intelligence. Once assembled and structured for analysis, the collective knowledge about Hidden Lynx and many other APT campaigns, some publicly available for years, allows us to better understand intent and capabilities.
We often hear leaders lament the present state of intelligence sharing, and advocate for new approaches with hold great promise. Meanwhile, large amounts of intelligence are already being shared in open source reporting. To yield insights, we must deal with great variety in sources and formats. The above data points were derived from PDFs, blog posts, and write ups from security firms coming from hundreds of websites. Recorded Future captures and structures that information, and provides analytic tools to help quickly make sense of this information from disparate sources.
The results of such threat actor and campaign analysis, corroborating evidence across multiple sources and linking technical details across security blogs, social media, and research forums, are insights that are useful from incident response to threat intelligence.
About usIntelligence CloudServices & SupportResearchResourcesCompanyHelpful linksCareersContact UsGet a DemoThe Intelligence GraphJoin us onlineWant to learn more?Contact us today
Copyright © 2024 Recorded Future, Inc.Security FAQCookiesPrivacy PolicyTerms & Conditions