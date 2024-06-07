# Reference for threat actor for "APT 32, OceanLotus, SeaLotus"

**Title**: Report: The SpyRATs of OceanLotus

**Source**: https://threatvector.cylance.com/en_us/home/report-the-spyrats-of-oceanlotus.html

## Content








Report: The SpyRATs of OceanLotus

































Skip Navigation






BlackBerry Logo































Cybersecurity


Automotive & IOT


Critical Communications


Inside BlackBerry











×




























BlackBerry Blog













BlackBerry Blog


        Report: The SpyRATs of OceanLotus
    










Report: The SpyRATs of OceanLotus




RESEARCH & INTELLIGENCE / 10.17.18 / 
The BlackBerry Cylance Threat Research Team






Share on Twitter







Share on Facebook







Share on Linked In







Email















During an incident response investigation in the final quarter of 2017, Cylance incident responders and threat researchers uncovered several bespoke backdoors deployed by OceanLotus Group (a.k.a. APT32, Cobalt Kitty), as well as evidence of the threat actor using obfuscated CobaltStrike Beacon payloads to perform C2. The threat actor routinely leveraged PowerShell within the environment, using one-liners to download/deploy malware, as well as obfuscators and reflective PE/shellcode loaders from various exploit kits (including MSFvenom, Veil and DKMC), allowing much of the malware to operate in-memory, with no on-disk footprint. The remote access trojans developed by OceanLotus Group (Roland, Remy and Splinter, named after famous rodents) share subtle code similarities with “Backdoor.Win32.Denis” (Kaspersky), “WINDSHIELD” and "KOMPROGO" (FireEye). Roland was of particular interest, in that it was carefully developed to mimic legitimate software DLLs developed by the victim organization. The malware C2 protocols were largely tailored for each target, and supported a range of communication methods, from raw data over TCP sockets to HTTP/S proxying. In addition, the threat actor relied heavily upon CobaltStrike Beacon for providing malleable C2 communications. DOWNLOAD THE FULL REPORT HERE At a code level, the bespoke remote access trojans, Roland, Remy and Splinter, contain many similarities and code re-use with existing OceanLotus malware, such as Denis. The overall design and development appear to be of a reasonably high-standard, suggesting a well-funded and equipped development team with a wide range of custom library code that can easily be repurposed for use in future targeted attacks. This white paper is dedicated to in-depth technical analysis of the malware, C2 protocols, TTPs and general observations. 







About The BlackBerry Cylance Threat Research Team
    The BlackBerry Cylance Threat Research team examines malware and suspected malware to better identify its abilities, function and attack vectors. Threat Research is on the frontline of information security and often deeply examines malicious software, which puts us in a unique position to discuss never-seen-before threats.









Share on Twitter







Share on Facebook







Share on Linked In







Email









Back













Facebook






Twitter





YouTube





Instagram
























Corporate
                              










Company


Newsroom


Investors


Careers


Leadership


Corporate Responsibility


Certifications


Customer Success







Developers
                              










Enterprise Platform & Apps


BlackBerry QNX Developer Network




Blogs
                              










BlackBerry ThreatVector Blog


Developers Blog


Help Blog







Legal
                              










Overview


Accessibility


Patents


Trademarks


Privacy Policy










                        © 2024 BlackBerry Limited. All rights reserved.
                    














