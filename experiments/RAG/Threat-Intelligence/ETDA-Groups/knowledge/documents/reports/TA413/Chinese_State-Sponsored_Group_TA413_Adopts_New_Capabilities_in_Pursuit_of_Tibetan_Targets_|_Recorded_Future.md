# Reference for threat actor for "TA413"

**Title**: Chinese State-Sponsored Group TA413 Adopts New Capabilities in Pursuit of Tibetan Targets | Recorded Future

**Source**: https://www.recordedfuture.com/chinese-state-sponsored-group-ta413-adopts-new-capabilities-in-pursuit-of-tibetan-targets

## Content
Chinese State-Sponsored Group TA413 Adopts New Capabilities in Pursuit of Tibetan Targets | Recorded FutureCareersContact UsLoginPlatformSolutionsProductsServicesResearchResourcesCompanyGet a demo
Book a demo
BlogChinese State-Sponsored Group TA413 Adopts New Capabilities in Pursuit of Tibetan TargetsPosted: 22nd September 2022By: Insikt Group®
Editor’s Note: The following post is an excerpt of a full report. To read the entire analysis, click here to download the report as a PDF.
This report details multiple campaigns conducted by the likely Chinese state-sponsored threat activity group TA413. The activity was identified through a combination of large-scale automated network traffic analytics and expert analysis. This report will be of most interest to individuals and organizations with strategic and operational intelligence requirements relating to Chinese cyber threat activity, as well as humanitarian and other organizations concerned with Tibetan interests. With thanks to our colleagues at Sophos for early sharing and collaboration.
Executive Summary
Recorded Future's analysts continue to observe targeting of ethnic and religious minority communities by Chinese state-sponsored groups for surveillance and intelligence-gathering purposes. Previously, we covered activity of this nature that we attributed to RedAlpha. We have since identified an additional group that has been particularly relentless in its targeting of the Tibetan community, commonly referred to in open source as TA413. Over the first half of 2022, we have observed TA413 exploit a now-patched zero-day vulnerability targeting the Sophos Firewall product (CVE-2022-1040), weaponize the "Follina" (CVE-2022-30190) vulnerability shortly after discovery and publication, and employ a newly observed custom backdoor we track as LOWZERO in campaigns targeting Tibetan entities. This willingness to rapidly incorporate new techniques and methods of initial access contrasts with the group’s continued use of well known and reported capabilities, such as the Royal Road RTF weaponizer, and often lax infrastructure procurement tendencies.
Key Judgments

TA413 likely conducts cyber espionage on behalf of the Chinese state. This assessment is based on the group’s persistent targeting of the Tibetan community for intelligence-gathering purposes, use of custom capabilities shared across other known Chinese state-sponsored groups, and other technical evidence supporting this attribution.
TA413 is likely a consumer of a shared capability development pipeline serving multiple Chinese state-sponsored groups, exemplified by the group’s continued use of the Royal Road RTF builder, a shared zero-day exploit in Sophos Firewall observed in use by multiple China-linked groups, and historical access to other shared malware families such as the TClient backdoor. 
In total, we observed at least 3 Chinese state-sponsored groups targeting Sophos Firewall zero-day vulnerability CVE-2022-1040. More widely, this activity is further evidence of both the continued increase in zero-day use by Chinese state-sponsored actors and the ongoing sharing of custom capabilities — including exploits — across groups linked to China’s intelligence agencies. 
TA413 drops a new custom backdoor, LOWZERO, deviating from using well known or open-source tooling.

Background
TA413 activity was first publicly reported by Proofpoint in September 2020 when the group was observed conducting persistent targeting of the Tibetan community, as well as briefly targeting multiple European entities in the early months of the COVID-19 pandemic. In this activity, TA413 used the Royal Road RTF weaponizer, which is shared across multiple Chinese state-sponsored groups, in order to load a custom malware family tracked as Sepulcher. More historically, TA413 infrastructure and email sender domains are linked to publicly reported ExileRAT activity also targeting Tibetan entities, as well as the use of the LuckyCat Android malware.
In February 2021, further TA413 activity was reported that featured the use of a customized malicious Mozilla Firefox browser extension tracked as FriarFox. FriarFox allowed access and control of targeted users’ Gmail accounts and contacted command-and-control infrastructure associated with the Javascript reconnaissance framework Scanbox. This activity and other related TA413 campaigns around this time also targeted organizations and individuals associated with the Tibetan community and featured continued use of Sepulcher and Royal Road.
Surprisingly, TA413 actors have regularly reused phishing email sender addresses for up to several years (such as tseringkanyaq@yahoo[.]com and mediabureauin@gmail[.]com), allowing for the connection of disparate campaign activity to the group. We have also observed historical correlations between TA413 and publicly reported Tropic Trooper (Keyboy, Pirate Panda) activity, suggesting a degree of overlap between these clusters. For instance, a December 2018 campaign that we observed targeting the Tibetan community used the sender email address mediabureauin@gmail[.]com historically associated with TA413 activity, and also shared C2 infrastructure overlaps with the peopleoffreeworld[.]tk domain noted in the Cisco Talos LuckyCat campaign. The infection chain ultimately loaded the custom TClient backdoor seen in historical Tropic Trooper activity reported by Citizen Lab, Trend Micro, and PWC. Both TA413- and Tropic Trooper-attributed activity also used the URI string /qqqzqa. The use of TClient was also recently sighted by Check Point researchers bundled with a Chinese language greyware, “SMS Bomber”.
There was also observable Infrastructure overlap between Tropic Trooper activity and TA413 campaigns. For example, the domain tibetnews[.]today referenced in Citizen Lab and Trend Micro reporting was hosted on Forewin Telecom IP Address 118.99.13[.]68 until early 2019, which later hosted multiple Tibet-themed domains matching unique TA413 infrastructure tactics, techniques, and procedures (TTPs). Importantly, the Citizen Lab report discusses some ambiguity around public reporting on the Tropic Trooper cluster that has conflated campaign and group names. Furthermore, based on wider trends in Chinese cyber-espionage activity, it is also highly plausible that these groups have shared a capability and/or infrastructure pipeline, and that TA413 is a subset of wider Tropic Trooper activity.
Threat/Technical Analysis
Over the past several years, we have observed TA413 activity relentlessly targeting organizations and individuals associated with the Tibetan community. While the group has occasionally expanded to a wider target set, targeting this community has been a constant and is almost certainly indicative of one of the group’s primary intelligence assignments. TA413 has also displayed an unusual mixture of consistency in using well publicized toolsets and infrastructure TTPs while also proving adaptable and agile in adopting zero-day or recently publicized vulnerabilities into infection chains. In the section below, we highlight some notable TA413 campaign activity observed throughout 2022 to date.
Analysis of Recent TA413 Campaign Activity
Exploitation of Sophos Firewall Zero-Day
On March 25, 2022, Sophos published an advisory regarding a patched authentication bypass vulnerability allowing remote code execution (RCE) in the User Portal and Webadmin of Sophos Firewall, which is tracked as CVE-2022-1040. According to the advisory, Sophos observed this vulnerability being exploited to gain initial access to a small number of targeted organizations primarily in the South Asia region. All affected organizations were informed directly by Sophos. Subsequently, Volexity and Sophos both published research regarding multiple likely Chinese state-sponsored threat activity groups exploiting CVE-2022-1040. In total, we identified at least 3 distinct Chinese state-sponsored threat activity groups with access to this exploit prior to public reporting, including TA413. 
The targeting observed within TA413-attributed exploitation of CVE-2022-1040 aligned with the group’s typical activity. The group used the Choopa (Vultr) IP address 192.46.213[.]63 in post-exploitation activity, which hosted multiple known TA413 domains at the time. A second IP address used in post-exploitation, 134.122.129[.]102, hosted applestatic[.]com at the time of activity, which has historical hosting overlaps with the TA413 domain newsindian[.]xyz.

Table 1: Post-exploitation infrastructure linked to TA413 targeting of CVE-2022-1040 (Source: Recorded Future)
Continued Use of the Royal Road RTF Weaponizer
TA413 continues to use variants of the shared Royal Road RTF weaponizer tool in targeted phishing attempts. Royal Road is widely shared across Chinese state-sponsored groups and allows the creation of malicious RTF files intended to exploit vulnerabilities in Microsoft Equation Editor (CVE-2017-11882, CVE-2018-0798, CVE-2018-0802). In May 2022, we identified a targeted spearphishing attempt against a Tibetan organization containing a link to a Royal Road sample hosted on the Google Firebase service. The group used the sender domain tibet[.]bet, which we had previously linked to TA413 activity based on infrastructure characteristics specific to the group, while a Proofpoint security researcher also attributed this campaign to the group.

Table 2: TA413 MalDoc weaponized using Royal Road (Source: Recorded Future)
The RTF drops a file named dcnx18pwh.wmf which is encoded using the XOR key B2 A6 6D FF associated with a known Royal Road variant. The decoded payload (028e07fa88736f405d24f0d465bc789c3bcbbc9278effb3b1b73653847e86cf8) ultimately loads a custom backdoor which we track as LOWZERO and contacts a hardcoded C2 IP address 45.77.19[.]75 over TCP Port 110. Further analysis of LOWZERO is included in the section Malware Analysis: TA413’s Custom LOWZERO Backdoor.

Figure 1: Tibetan language Royal Road lure used by TA413 (Source: Recorded Future)
Exploitation of MSDT Vulnerability CVE-2022-30190 (Follina)
On May 30, 2022, we identified a spearphishing attempt targeting an entity associated with the Tibetan government-in-exile. In this activity, the attackers spoofed the Central Tibetan Administration and used a theme of a photography grant intended to support female photographers within the Tibetan community. The phishing email again used the sender domain tibet[.]bet. The phishing email linked to a file hosted on a subdomain associated with the Google Firebase service, tibet-gov.web[.]app, as also referenced in subsequent open-source reporting by Proofpoint.
The phishing emails were sent in 2 waves: the first linked to a Microsoft Word .docx attachment hosted on the Google Firebase service that attempts to use the Follina vulnerability, and a second linked to a .RAR archive file containing both the malicious Microsoft Word attachment and a decoy .png image file.

Table 3: Malicious TA413 .docx file exploiting Follina vulnerability (Source: Recorded Future)

Figure 2: Contents of RAR file hosted on Google Firebase domain: decoy PNG file (left) and contents of malicious .docx file (right) (Source: Recorded Future)
Once the Word document is opened, it attempts to retrieve an HTML file from a remote web server, http://65.20.75[.]158/poc.html. The downloaded HTML file uses the ms-msdt MSProtocol URI scheme to trigger the Follina exploit and ultimately execute a Base64-encoded PowerShell command to download a follow-on payload from http://65.20.75[.]158/0524x86110.exe. At the time of analysis, 65.20.75[.]158 also hosted the recently registered Tibet-themed domains t1bet[.]net and airjaldi[.]online, which spoofs the Indian ISP AirJaldi. Notably, AirJaldi runs the Dharamshala Network which provides internet access to multiple Tibetan entities.

Figure 3: ms-msdt command used by TA413 to execute Base64-encoded PowerShell command and download follow-on payload (Source: Recorded Future)

Figure 4: Decoded PowerShell command (Source: Recorded Future)
The downloaded file 0524x86110.exe is UPX-packed and has the SHA256 file hash 5217c2a1802b0b0fe5592f9437cdfd21f87da1b6ebdc917679ed084e40096bfd. The unpacked UPX file also loads LOWZERO and uses the Choopa C2 IP address 45.77.45[.]222 for C2 over port TCP 110. Notably, 45.77.45[.]222 hosted the domain tibetyouthcongress[.]com at the time of this activity, which our analysis also previously attributed to TA413.
Other Tooling in Use by TA413
From further analysis of TA413 activity, we also identified evidence that the group is likely using the open-source proxy tool Stowaway. This is based on the identification of an ELF sample (SHA256: 86f45f0d6778fda90a56ea8986a9124d768715af425784bbd1c371feeb2bfe68) configured to communicate with the IP address 134.122.129[.]38, which was uploaded to public malware repositories in close proximity to the time this IP hosted the TA413 domain freetibet[.]in. Notably, Stowaway has also been observed in use by other likely Chinese state-sponsored groups, per recent reporting by Kaspersky.
Additionally, through historical scanning data we identified an open directory present on a TA413-controlled server 172.105.35[.]111 in June 2022. While this was no longer accessible at the time of discovery, one of the files present was named fscan_amd64. This is likely indicative of the group’s use of the open-source internal network scanning tool fscan, which uses a file of the same name. This tool was also observed in use by another suspected Chinese state-sponsored actor TAG-22 (Bronze University, Earth Lusca, Fishmonger, Red Dev 10) by Trend Micro researchers.
Victimology
In all of these recent campaigns, we have observed TA413 persistently targeting organizations associated with the Tibetan community, including entities associated with the Tibetan government-in-exile. While this appears to make up a large proportion of the group’s activity, open-source reporting also identified short-lived TA413 activity targeting European diplomatic and legislative bodies, non-profit policy research organizations, and global organizations dealing with economic affairs during the early stages of COVID-19 in 2020. Using Recorded Future Network Traffic Analysis (NTA), we also identified infrastructure associated with multiple government organizations in Nepal and the corporate network of an Indian Internet Service Provider (ISP) regularly communicating with TA413 C2 infrastructure during the first half of 2022.
Infrastructure Analysis
TA413 continues to use a consistent set of infrastructure TTPs aligning with historical public reporting when procuring and weaponizing operational infrastructure. The group has predominantly registered domains through GoDaddy and used a combination of Forewin Telecom, Choopa (Vultr), and Linode for hosting. Notably, a large majority of identified TA413 domains also used the registrant organization name “asfasf”, likely due to consistent keyboard walking of the left hand keyboard home keys. These TTPs also align with publicly attributed TA413 domains such as vaccine-icmr[.]net, as featured in historical Proofpoint reporting.
TA413 also continues to largely use domains spoofing organizations associated with Tibet such as non-government organizations (like Tibetan National Congress and Tibetan Youth Congress) and media organizations (such as Tibet Times). The group has also registered domains spoofing wider organizations such as the remote working employment site FlexJobs and Indian news firm Rediff News.

Table 4: TA413 domains spoofing specific organizations (Source: Recorded Future)
Malware Analysis: TA413’s Custom LOWZERO Backdoor
LOWZERO is a backdoor that, after profiling the infected machine and sending the data to the command-and-control server, will receive additional modules to run. We believe the modules are only delivered and executed if the fingerprinted machine is of interest to the actors, as we did not observe any additional modules while executing within a sandbox environment. The modules likely expand upon the basic backdoor functionality residing in LOWZERO. LOWZERO is also capable of proxying communication received via the network listener out through another connection, defined based upon prior data received.
The following analysis was performed on a sample of the malware with SHA256 hash 5217c2a1802b0b0fe5592f9437cdfd21f87da1b6ebdc917679ed084e40096bfd
Layers to Execution
The LOWZERO execution chain contains multiple layers/stages:

Stage 1 — Decompresses an embedded DLL file (stage 2) before XOR decrypting it and executing it 
Stage 2 — Launches rundll32.exe in a suspended state and injects the Stage 3 DLL into it; then it calls the DllEntryPoint and the exported function F exposed by the Stage 3 DLL 
Stage 3 — Exported function F contains the backdoor functionality


Figure 5: LOWZERO loading process (Source: Recorded Future)
Config BreakDown
LOWZERO’s configuration information is passed in as a buffer to Stage 3’s exported function F. The configuration data is both encrypted and compressed. The decompression algorithm is applied after the not operator is applied to decrypt the buffer. The decompression algorithm is likely LZF (Lempel-Ziv-Free). This same decompression algorithm is also used to decompress the Stage 2 dll and is used as part of the encryption / decryption scheme for C2 communication.

Figure 6: Encrypted and compressed configuration data (Source: Recorded Future)
Figure 7 shows the contents of the configuration information buffer after decryption and decompression.

Figure 7: Decrypted and decompressed configuration data (Source: Recorded Future)
The campaign ID is used as the mutex and can be extracted from the configuration data. The campaign ID found in this sample is: 8C9BB583-7C26-4990-AA73-E66F594A5AD5.
The C2 information is still obfuscated at this stage. The binary not operator is applied to each byte in order to partly deobfuscate the string. The string is then base64-decoded using the custom alphabet Vhw4W3uB5OcY8qrp21NxbHs7ynSJFoPTEdAUtv9QagIDl6MR0KZkmjfeiCzGXL+/ to get the final result. The final result is extracted and parsed as seen in Table 5.

Table 5: Extracted C2 values (Source: Recorded Future)
C2 Communications
This sample of LOWZERO mimics a TLS version 1.1 connection over a non-standard TLS port (TCP 110). However, the TLS connection is custom and does not adhere to the protocol standard, and was likely created to look like TLS on the surface. This helps the communication to blend in with other TLS traffic while allowing the actor not to worry about certificate procurement or management.
The communication starts with the standard TLS handshake components Client Hello and Server Hello. During the Server Key Exchange the C2 passes the EC (Elliptic Curve) Diffie-Hellman public key of b113bc93dcd87d350850b7fd643c2c5aee678c3dcb717d1296b0cf57c749f0ab. It is important to note that both of the C2s we identified use the same public key.
After the TLS hello packets are sent, LOWZERO exchanges its EC Diffie-Hellman public key with the C2, which the backdoor randomly generates at runtime, meaning that each C2 session will have a different public key. Figure 8 shows the TLS version 1.1 handshake from the LOWZERO backdoor to the C2.

Figure 8: LOWZERO TLS version 1.1 handshake (Source: Recorded Future)
Up until this point, the C2 connection has seemingly followed the standard TLS 1.1 handshake. In a standard implementation of TLS, when data is exchanged between a client / server, the process is to use asymmetric encryption to securely exchange the symmetric key and then switch to the symmetric encryption as it's faster. However, this is where LOWZERO breaks protocol and doesn’t use public key encryption to securely transfer the symmetric key. Instead, the Random Bytes from the Client Hello packet and the Random Bytes from the Server Hello packet are XORed together to derive a key for the AES encryption algorithm that is used to decrypt / encrypt the C2 communication.

Figure 9: LOWZERO AES encryption / decryption key creation (Source: Recorded Future)
LOWZERO Initialization Packet
After the TLS handshake and the deriving of the AES key, LOWZERO sends the following basic system and user information to the C2:

Username
Campaign ID
Process name and Process ID
IP Address
Hostname

The data is then encoded and encrypted using the below LOWZERO custom scheme and is also depicted in Figure 10.

LZF-compressed
XORed with 0x2b
Base64-encoded with the custom alphabet
AES-encrypted with randomly generated key (provided in C2 transmission)
AES-encrypted with derived key from the XOR of the Client / Server Random Bytes Key

Decryption of the traffic is possible by simply reversing the operations above.

Figure 10: LOWZERO C2 encryption scheme (Source: Recorded Future)
Figure 11 shows the C2 communication structure representing the decrypted AES traffic to and from the C2. The core parts of the response are the Command (0x06) and the Command Data (0x0C).

Figure 11: LOWZERO C2 communication structure (Source: Recorded Future)
LOWZERO Commands
LOWZERO has the ability to receive 1 or more commands at a time (see Figure 11 for command structure) and then execute each of them one at a time. The function at offset 0x10005090 handles the header check that confirms the presence of the bytes representing the ASCII values PK at the start of the command section, prior to parsing and running the commands. The command choices are:

Table 6: LOWZERO commands (Source: Recorded Future)
We were unable to recover any modules from the C2, and as a result, are unable to determine what capabilities the modules add to LOWZERO.
Weak C2 Protocol
We were able to decrypt captured communication as the AES key is derived from the TLS handshake itself. This allows us to review the commands sent and provides us an opportunity to extract out any modules delivered to the victim machine. Details are provided in Appendix C.
Mitigations

Configure your intrusion detection systems (IDS), intrusion prevention systems (IPS), or any network defense mechanisms in place to alert on — and upon review, consider blocking connection attempts to and from — the external IP addresses and domains linked in Appendix A.
Ensure security monitoring and detection capabilities are in place for all external-facing services and devices. Monitor for follow-on activity likely to take place following exploitation of these external-facing services, such as the deployment of webshells, backdoors, or reverse shells.
Ensure a risk-based approach for patching of vulnerabilities, prioritizing high-risk vulnerabilities and those being exploited in the wild as determined through the Recorded Future Vulnerability Intelligence module.
Monitor for domain abuse, such as typosquat domains spoofing your organization and vendors, through the Recorded Future Brand Intelligence module.
Employ detection and hardening coverage for the MITRE ATT&CK techniques highlighted in Appendix B.

Outlook
Our research identified persistent targeting of the Tibetan community in the first half of 2022 from the probable Chinese state-sponsored threat activity group TA413. The group continues to incorporate new capabilities while also relying on tried-and-tested TTPs. In particular, the stark contrast between some of the tooling employed by the group versus infrastructure management practices is likely indicative of separate teams involved in the development of malware and exploits versus those conducting operations. While mainly focused on Tibetan targeting, TA413 also has multiple historical infrastructure and malware ties to the group known as Tropic Trooper (Keyboy, Pirate Panda) that are indicative of some degree of operational overlap. More widely, TA413’s adoption of both zero-day and recently published vulnerabilities is indicative of wider trends with Chinese cyber-espionage groups whereby exploits regularly appear in use by multiple distinct Chinese activity groups prior to their widespread public availability.
About usIntelligence CloudServices & SupportResearchResourcesCompanyHelpful linksCareersContact UsGet a DemoThe Intelligence GraphJoin us onlineWant to learn more?Contact us today
Copyright © 2024 Recorded Future, Inc.Security FAQCookiesPrivacy PolicyTerms & Conditions