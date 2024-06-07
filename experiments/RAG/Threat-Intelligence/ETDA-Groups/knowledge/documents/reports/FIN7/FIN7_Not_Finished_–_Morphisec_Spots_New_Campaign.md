# Reference for threat actor for "FIN7"

**Title**: FIN7 Not Finished – Morphisec Spots New Campaign

**Source**: http://blog.morphisec.com/fin7-not-finished-morphisec-spots-new-campaign

## Content






FIN7 Not Finished – Morphisec Spots New Campaign
















































































ON-DEMAND WEBINAR: Morphisec's Top 10 Security Predictions - Outlook into 2024























Support
Partners
Contact Us













Products

Product Overview
Morphisec for Windows Endpoints
Morphisec for Windows Servers & Workloads
Morphisec for Linux Server Protection
Morphisec Vulnerability Visibility & Prioritization
Incident Response Services
About Moving Target Defense

Solutions

By Industry

Finance
Hedge Funds
Healthcare
Technology
Manufacturing
Legal
K-12 Education
SMB

By Use Case

Microsoft Defender AV
Microsoft Defender for Endpoint
Virtual Desktop Protection
Cloud Workload Protection
Remote Employee Security
Ransomware Prevention
Virtual Patching and Compliance
Supply Chain Attack Protection
Browser Attack Protection


Company

About Us
News & Events
Careers

Resources

Blog
Learning Center
Customer Stories 




































Products

Products
Product Overview
Morphisec for Windows Endpoints
Morphisec for Windows Servers & Workloads
Morphisec for Linux Server Protection
Morphisec Vulnerability Visibility & Prioritization
Incident Response Services
About Moving Target Defense

Solutions

Solutions
By Industry

Finance
Hedge Funds
Healthcare
Technology
Manufacturing
Legal
K-12 Education
SMB

By Use Case

Microsoft Defender AV
Microsoft Defender for Endpoint
Virtual Desktop Protection
Cloud Workload Protection
Remote Employee Security
Ransomware Prevention
Virtual Patching and Compliance
Supply Chain Attack Protection
Browser Attack Protection


Company

Company
About Us
News & Events
Careers

Resources

Resources
Learning Center
Customer Stories 

Blog
Support
Partners
Contact Us



































Cybersecurity Blog
Cybersecurity News, Threat Research, and more from the Team Spearheading the Evolution of Endpoint Security






















FIN7 Not Finished – Morphisec Spots New Campaign

Posted by
Michael Gorelik on November 21, 2018

Find me on:

LinkedIn
Twitter 










Tweet















This blog was co-authored by Alon Groisman.

It seems like the rumors of FIN7’s decline have been hasty. Just a few months after the well-publicized indictment of three high-ranking members in August, Morphisec has identified a new FIN7 campaign that appears to be targeting the restaurant industry.
FIN7, also known as Carbanak, is one of the major threat groups tracked by Morphisec and numerous other security entities, and among the top three criminal computer intrusion cases that the FBI is currently working. FIN7 is composed of a very sophisticated network of developers and hackers and brings in an estimated $50 million a month. They target very specific industries, hospitality – hotels and restaurants – being one of them, and are behind a string of high-profile breaches including Red Robin, Chili’s, Arby’s, Burgerville, Omni Hotels and Saks Fifth Avenue, among many others.
FIN7 is known for its stealth techniques and ability to continuously evade security systems. In the case of Burgerville, malware sat on the company’s network collecting payment data for nearly a year before it was discovered. And that was only due to an FBI investigation.
In this blog post, we present our findings on two campaigns, which occurred in the first and second weeks of November. These campaigns follow patterns similar to those presented by FireEye in August but with just enough variations to bypass many security vendors.
Technical Description
The initial document was probably sent within the Baltic region (or tested there). It was submitted to VirusTotal from Latvia. The name of the document translated from Russian is “new questioner”. It is password-protected with the password: “goodmorning”.
Oprosnik_new.doc 6e1230088a34678726102353c622445e1f8b8b8c9ce1f025d11bfffd5017ca82)

It uses social engineering to convince the recipient to enable macros through the use of the images, logo and tagline of a newly launched, legitimate VPN tool InvinciBull by cybersecurity company Finjan.
If the “enable macro” button is activated, the following obfuscated Macro runs and the next stage obfuscated JavaScript is extracted from the form caption, similar to the last several FIN7 campaigns.

Examining the metadata of the document, it clearly shows that the document was created on the 11.02.2018:

Following deobfuscation of the macro, we notice known FIN7 patterns of executing JavaScript from VBScript with the slight modification of copying the wscript.exe file and renaming it to mses.exe. This may allow it to bypass some EDR solutions that are tracing WScript by name.

Below is the obfuscated JavaScript that is written to the temp directory as error.txt file. The obfuscation pattern is similar to previously seen FIN7 patterns and most probably is a derivation of the same obfuscation toolkit.

Deobfuscated JavaScript
The deobfuscated JavaScript is actually a backdoor component that directly communicates to the C2 server (in this case hxxps://bing-cdn[.]com). It executes the response which is yet another JavaScript command, which can be evaluated by eval. Although there have been slight modifications in the Macro delivery in the last couple of campaigns, the JavaScript backdoor stays the same, including its communication protocol.
During the first request, the MAC address and the computer domain are also delivered to the target C2. We believe that the next stage is only delivered to specific targets based on domains as the data that is delivered in the first request is very limited.

Yara Rules
Some additional observations that can be used to create Yara-rules for this campaign are the locations of the loaded VBControl files that are written in clear text as part of the document files:

Additional Samples
After this search, we identified more samples that were created just a couple of days ago and point to a known C2 registered to the same entity (hxxps://googleapi-cdn[.]com)
Below is a summary of information for one of those documents:
The document was submitted from Ukraine (yet another former soviet union country) with the name “dinners.doc” (f5f8ab9863dc12d04731b1932fc3609742de68252c706952f31894fc21746bb8).
The document again uses the social engineering technique of spoofing a known and trusted entity to convince the victim to enable macros.

Based on the submission date and creation time, the document is sent to the target within 2-3 days.

The macro is nearly identical to that described above except that wscript->script, errors->settings, has multiple captions instead of a single one.

The JavaScript backdoor is decrypted into a similar backdoor:

Conclusion
Like the Hydra, cutting off one, or even three, heads of FIN7 barely slows it down. With the holiday rush nearly upon us, we expect the threat group to step up its activities to take advantage of increased email traffic flow and seasonal staff that may be less security conscious. Workers in any industry should stay vigilant against social engineering methods – although with today’s highly targeted campaigns this can sometimes be tough to spot. And never enable macros unless you are 100 percent certain that the file is safe. 















Subscribe to our blog
Stay in the loop with industry insight, cyber security trends, and cyber attack information and company updates.






























Search Our Site





























Recent Posts














Posts by Tag



Moving Target Defense (127)


Cyber Security News (123)


Morphisec Labs (111)


Threat Research (60)


Threat Post (59)


Morphisec News (52)


Automated Moving Target Defense (8)


Defense-in-Depth (6)


in-memory attacks (6)


Gartner (4)


runtime attacks (4)


Legacy security (3)


Linux cyber security (3)


advanced threat defense (3)


threat and vulnerability management (3)


ChatGPT (2)


Gartner endpoint protection (2)


Ransomware (2)


financial cybersecurity (2)


patch management (2)


Anti-tampering (1)


Evasive loader (1)


Fileless malware (1)


Gartner Emerging Tech (1)


Healthcare cybersecurity (1)


IoT security (1)


Securing IoT devices (1)


Server security (1)


See all



























Products

Product Overview
Morphisec for Windows Endpoints
Morphisec for Windows Servers & Workloads
Morphisec for Linux Server Protection
Morphisec Vulnerability Visibility & Prioritization
Incident Response Services
About Moving Target Defense

Solutions By Industry

Banking & Finance
Hedge Funds
Healthcare
Technology
Manufacturing
Legal
K-12 Education
SMB

Solutions by Use Case

Microsoft Defender for Endpoint
Microsoft Defender AV
Virtual Desktop Protection
Ransomware Protection
Supply Chain Attack Protection
Cloud Workload Protection
Remote Employee Security
Virtual Patching & Compliance
Browser Attack Protection







Company

About Us
News & Events
Careers

Blog
Support
Partners
Contact Us
Privacy & Legal
Contact Sales
Inquire via Azure














© 2023 Morphisec Ltd. | All rights reserved































































