# Reference for threat actor for "Promethium, StrongPity"

**Title**: Whack-A-Mole: The Impact of Threat Intelligence on Adversaries

**Source**: https://threatvector.cylance.com/en_us/home/whack-a-mole-the-impact-of-threat-intelligence-on-adversaries.html

## Content








Whack-A-Mole: The Impact of Threat Intelligence on Adversaries

































Skip Navigation






BlackBerry Logo































Cybersecurity


Automotive & IOT


Critical Communications


Inside BlackBerry











×




























BlackBerry Blog













BlackBerry Blog


        Whack-A-Mole: The Impact of Threat Intelligence on Adversaries
    










Whack-A-Mole: The Impact of Threat Intelligence on Adversaries




RESEARCH & INTELLIGENCE / 10.23.18 / 
Cylance Threat Intelligence Bulletin






Share on Twitter







Share on Facebook







Share on Linked In







Email















Introduction One of the great paradoxes in cybersecurity is that as defenders race ahead to identify the next and newest methods of attack, attackers often lag behind and reuse the old and obvious ones with success. A similar irony haunts threat intelligence research. Often, when researchers identify and unveil the work of threat groups, the malicious activity exposed disappears from view, and the researchers move on. The trouble is, the more advanced threat actors often do not. And with more people looking ahead rather than behind, attackers are free to restructure old attacks and resume them. In this Threat Intelligence Bulletin, Cylance looks back and traces the changes one such threat actor made – the one behind malware known as Promethium or StrongPity – after a number of researchers at different organizations exposed aspects of both their malware toolset as well as their methods of deployment. Readers of this blog will learn how easy it is for threat actors to change course after the publication of threat intelligence reports and how valuable it can be for researchers, organizations and the public they serve to keep looking back. Background and Discussion In March of 2018, researchers at Citizen Lab, an interdisciplinary research institute of the University of Toronto focused on the overlap of technology, human rights, and security, published a lengthy report in their Free Expression Online series called “Bad Traffic.” Their findings shed light on what they said was the apparent use of Sandvine/Procera Deep Packet Inspection (DPI) hardware to essentially “man-in-the-middle” benign Internet traffic and insert malware known as Promethium (a.k.a. StrongPity) to targeted regions in Turkey and, indirectly, into Syria. They also claimed to uncover the apparent use of these DPI boxes to “covertly raise money through affiliate ads and cryptocurrency mining in Egypt” .    It was a notable report, not just because of its content, but also because it was a good example of the power of a communal effort in public threat intelligence and research. What Citizen Lab did was to effectively synthesize prior findings published by a number of disparate groups about both malware and new delivery methods and put them together with their own original research to yield new insights. Citizen Lab first drew on 2016 research by Kaspersky Lab into malware called StrongPity – research that was expanded upon later that year by Microsoft, which calls the malware Promethium. Then Citizen Lab incorporated the findings of researchers at ESET, who noted the apparent use of a Promethium/StrongPity variant being used at the Internet Service Provider (ISP) level in two unnamed countries . Citizen Lab’s research suggested that the countries to which the ESET researchers were referring were in fact Turkey and Egypt. It should be noted that spokespeople for Sandvine/Procera and their owner Francisco Partners strenuously denied the findings of Citizen Lab. Nevertheless, Citizen Lab’s research, complete with technical indicators of compromise regarding the Promethium malware, resulted in coverage in several media outlets, including the Wall Street Journal as recently as July of this year. In March, almost immediately upon publication by Citizen Lab, Cylance observed the threat actors behind the malware described in their report change tack. We believe the malware is likely part of yet another commercial (grayware) solution sold to governments and law enforcement agencies, and we have reason to believe it bears a strong connection to a company based in Italy – a lead we hope to investigate in the near future. Technical Analysis Two months after the Citizen Lab report, Cylance found new Promethium/StrongPity activity, utilizing new infrastructure. The observed domains all appeared to have been registered about two weeks after Citizen Lab’s report.  The malware has continued to adapt as new information is published. Minimal effort and code changes were all that was required to stay out of the limelight. Cylance observed new domains, new IP addresses, filename changes, and small code obfuscation changes. In the Citizen Lab report, researchers said that Promethium/StrongPity malware was inserted into Internet traffic after users made legitimate requests for common, often free application installers. In this latest run, Cylance found the following legitimate installers were targeted by the unknown operators of the malware, many of which are exactly the same as those cited in the original Citizen Lab report:  Internet Download Manager (https://www.internetdownloadmanager.com/) VLC Player (https://www.videolan.org/vlc/) Avast (https://www.avast.com/) WinRAR 5.50 (https://rarlab.com/rar/wrar550.exe) (English and Arabic) CCleaner (https://www.ccleaner.com) DAEMON Tools Lite (https://www.daemon-tools.cc)  Host Indicators: In addition, Cylance observed several new filenames and paths utilized by the latest round of droppers:     %windows%\system32\IpeOve32.exe    %temp%\ AC315BA-864X-64AA-C23B-C3DDC042AB2\evntwn32.xml    %temp%\AC315BA-864X-64AA-C23B-C3DDC042AB2\mscorw32.xml    %windows%\system32\netplviz.exe  The “netplvliz.exe” binary is installed as a service with the display name “Advanced User Accounts Control” to maintain persistence on affected systems. Its primary role is to launch the “IpeOve32.exe” binary which performs the bulk of the malicious actions. The new droppers additionally take advantage of the following PowerShell command: powershell.exe Set-MpPreference -ExclusionPath 'C:\Windows\System32', 'C:\Windows\SysWOW64', 'C:\DOCUME~1\<USER>~1\LOCALS~1\Temp' -MAPSReporting 0 -DisableBehaviorMonitoring 1 -SubmitSamplesConsent 2 This command attempts to alter the default behavior of Windows Defender on Windows 10 systems by excluding the system and temp directories as well as turning off sample submission and disabling behavior monitoring.  We assume this was done in response to Microsoft’s earlier research and an attempt to keep malicious samples out of the hands of researchers. This type of behavior is relatively unique, though, and will be a dead giveaway if defenders are monitoring PowerShell usage across their networks. The only major difference Cylance observed in the backdoor involved the encoding methods used for string obfuscation. The group abandoned the previously used configuration files that ESET documented well . In late March of 2018, the threat actors behind Promethium just pushed sensitive strings like C2 domains onto the stack in Unicode. In May, their method of attack evolved to push encoded Unicode strings onto the stack then XOR those values against a single byte key and subtract one from that value. Both domain names for the malware are stored in this way. In the latest samples Cylance analyzed the XOR keys 0x45 and 0x25 were used to encode C2 domains. Network Indicators:  The malware Cylance observed will communicate over SSL on port 443 using HTTP requests to the C2 server. In the samples we analyzed, the PHP pages were all unique; however, the samples all communicated to one of five domains over TCP port 443: 1.     ms-sys-security[.]com, 2.     svr-sec2-system[.]com, 3.     upd2-app-state[.]com 4.     srv-mx2-cdn-app[.]com 5.     system-upload-srv[.]com The malware utilizes a unique User-Agent string “Edge/8.0 (Windows NT [OS Version Number]; Win[32 or 64]; [Processor Architecture])”. An example check-in POST is presented below: 







About Cylance Threat Intelligence Bulletin
    Monthly bulletin from the Cylance Threat Intelligence Team.
  








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
                    














