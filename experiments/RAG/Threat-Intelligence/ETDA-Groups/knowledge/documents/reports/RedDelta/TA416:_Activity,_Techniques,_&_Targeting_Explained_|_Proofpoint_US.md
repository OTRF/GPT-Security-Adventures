# Reference for threat actor for "RedDelta"

**Title**: TA416: Activity, Techniques, & Targeting Explained | Proofpoint US

**Source**: https://www.proofpoint.com/us/blog/threat-insight/good-bad-and-web-bug-ta416-increases-operational-tempo-against-european

## Content

































































TA416: Activity, Techniques, & Targeting Explained | Proofpoint US









      Skip to main content
    







Products
Solutions
Partners
Resources
Company











English (Americas)
English (Europe, Middle East, Africa)
English (Asia-Pacific)
Español
Deutsch
Français
Italiano
Português
日本語
한국어



Login

Support Log-in
Digital Risk Portal
Email Fraud Defense
ET Intelligence
Proofpoint Essentials
Sendmail Support Log-in


Contact






Aegis Threat Protection PlatformDisarm BEC, phishing, ransomware, supply chain threats and more.
Sigma Information Protection PlatformDefend your data from careless, compromised and malicious users.
Identity Threat Defense PlatformPrevent identity risks, detect lateral movement and remediate identity threats in real time.
Intelligent Compliance PlatformReduce risk, control costs and improve data visibility to ensure compliance.
Premium ServicesLeverage proactive expertise, operational continuity and deeper insights from our skilled experts.





Email Security and Protection
Email Protection
Email Fraud Defense
Secure Email Relay
Threat Response Auto-Pull
Sendmail Open Source
Essentials for Small Business

Advanced Threat Protection
Targeted Attack Protection in Email
Threat Response
Emerging Threats Intelligence

Security Awareness Training
Assess
Change Behavior
Evaluate


Information Protection
Enterprise Data Loss Prevention (DLP)
Insider Threat Management
Intelligent Classification and Protection
Endpoint Data Loss Prevention (DLP)
Email Data Loss Prevention (DLP)
Email Encryption
Data Discover

Cloud Security
Isolation
Cloud App Security Broker
Web Security


Identity Threat Detection and Response
Spotlight
Shadow


Compliance and Archiving
Automate
Capture
Patrol
Track
Archive
Discover
Supervision


Premium Services
Managed Email Threat Protection
Managed Information Protection
Managed Security Awareness
Managed Abuse Mailbox
Recurring Consultative Services
Technical Account Managers
Threat Intelligence Services
People-Centric Security Program






  New threat protection solution bundles with flexible deployment options 
  AI-powered protection against BEC, ransomware, phishing, supplier risk and more with inline+API or MX-based deployment
Learn More






Solutions by Topic


Combat Email and Cloud ThreatsProtect your people from email and cloud threats with an intelligent and holistic approach.
Change User BehaviorHelp your employees identify, resist and report attacks before the damage is done.
Combat Data Loss and Insider RiskPrevent data loss via negligent, compromised and malicious insiders by correlating content, behavior and threats.
Modernize Compliance and ArchivingManage risk and data retention needs with a modern compliance and archiving solution.
Protect Cloud AppsKeep your people and their cloud apps secure by eliminating threats, avoiding data loss and mitigating compliance risk.


Prevent Loss from RansomwareLearn about this growing threat and stop attacks by securing today’s top ransomware vector: email.
Secure Microsoft 365Implement the very best security and compliance solution for your Microsoft 365 collaboration suite.
Defend Your Remote Workforce with Cloud EdgeSecure access to corporate resources and ensure business continuity for your remote workers.
Authenticate Your EmailProtect your email deliverability with DMARC.
Why ProofpointToday’s cyber attacks target people. Learn about our unique people-centric approach to protection.




Solutions by Industry

Federal Government
State and Local Government
Higher Education
Financial Services
Healthcare
Mobile Operators
Internet Service Providers
Small and Medium Businesses






Partner Programs


Channel PartnersBecome a channel partner. Deliver Proofpoint solutions to your customers and grow your business.
Archive Extraction PartnersLearn about Proofpoint Extraction Partners.
Global System Integrator (GSI) and Managed Service Provider (MSP) PartnersLearn about our global consulting and services partners that deliver fully managed and integrated solutions.


Technology and Alliance PartnersLearn about our relationships with industry-leading firms to help protect your people, data and brand.
Social Media Protection PartnersLearn about the technology and alliance partners in our Social Media Protection Partner program.
Proofpoint Essentials Partner ProgramsSmall Business Solutions for channel partners and MSPs.




Partner Tools

Become a Channel Partner
Channel Partner Portal








Resource LibraryFind the information you're looking for in our library of videos, data sheets, white papers and more.
BlogKeep up with the latest news and happenings in the ever‑evolving cybersecurity landscape.
PodcastsLearn about the human side of cybersecurity. Episodes feature insights from experts and executives.
New Perimeters MagazineGet the latest cybersecurity insights in your hands – featuring valuable knowledge from our own industry experts.


Threat GlossaryLearn about the latest security threats and how to protect your people, data, and brand.
EventsConnect with us at events to learn how to protect your people and data from ever‑evolving threats.
Customer StoriesRead how Proofpoint customers around the globe solve their most pressing cybersecurity challenges.
WebinarsBrowse our webinar library to learn about the latest threats, trends and issues in cybersecurity.




Security Hubs

Get free research and resources to help you protect against threats, build a security culture, and stop ransomware in its tracks.

Threat Hub
CISO Hub
Cybersecurity Awareness Hub
Ransomware Hub
Insider Threat Management Hub









About ProofpointProofpoint is a leading cybersecurity company that protects organizations' greatest assets and biggest risks: their people.
Why ProofpointToday’s cyber attacks target people. Learn about our unique people-centric approach to protection.
CareersStand out and make a difference at one of the world's leading cybersecurity companies.


News CenterRead the latest press releases, news stories and media highlights about Proofpoint.
Privacy and TrustLearn about how we handle data and make commitments to privacy and other regulations.
Environmental, Social, and GovernanceLearn about our people-centric principles and how we implement them to positively impact our global community.




Support

Access the full range of Proofpoint support services.
Learn More











 




BlogThreat Insight
                                    The Good, the Bad, and the Web Bug: TA416 Increases Operational Tempo Against European Governments as Conflict in Ukraine Escalates 
                              

 












The Good, the Bad, and the Web Bug: TA416 Increases Operational Tempo Against European Governments as Conflict in Ukraine Escalates 





Share with your network!








 March 07, 2022


                Michael Raggi and Myrtus
  
        

 
8/24 Editor’s Note: Since the publication, SMTP2Go has updated its security measures.
Key Takeaways
Proofpoint researchers have identified ongoing activity by the China-aligned APT actor TA416 in which the group is targeting European diplomatic entities, including an individual involved in refugee and migrant services.
This targeting is consistent with other activity reported by Proofpoint, showing an interest in refugee policies and logistics across the APT actor landscape which coincides with increased tensions and now armed conflict between Russia and Ukraine.
The campaigns utilize web bugs to profile the victims before sending a variety of PlugX malware payloads via malicious URLs.
TA416 has recently updated its PlugX variant, changing its encoding method and expanding its configuration capabilities.
Overview
Since 2020, Proofpoint researchers have observed TA416, an actor assessed to be aligned with the Chinese state, utilizing web bugs to profile their targets. Commonly referred to as tracking pixels, web bugs embed a hyperlinked non-visible object within the body of an email that, when enabled, will attempt to retrieve a benign image file from an actor-controlled server. This provides a “sign of life” to threat actors and indicates that the targeted account is valid with the user being inclined to open emails that utilize social engineering content. TA416 has been using web bugs to target victims prior to delivering malicious URLs that have installed a variety of PlugX malware payloads. The operational tempo of these campaigns, specifically those against European governments, have increased sharply since Russian troops began amassing on the border of Ukraine.
The use of the web bug reconnaissance technique suggests TA416 is being more discerning about which targets the group chooses to deliver malware payloads. Historically, the group primarily delivered web bug URLs alongside malware URLs to confirm receipt. In 2022, the group started to first profile users and then deliver malware URLs. This may be an attempt by TA416 to avoid having their malicious tools discovered and publicly disclosed. By narrowing the lens of targeting from broad phishing campaigns to focus on targets that have proven to be active and willing to open emails, TA416 increases its chance of success when following up with malicious malware payloads.
What’s In a Web Bug – Delivery in 2020 and 2021
Starting in early November 2021, Proofpoint researchers identified web bug reconnaissance campaigns targeting European diplomatic entities. Notably this activity aligned with the escalation of tensions between Russia, Ukraine, and, by extension, NATO member states in Europe. The emails first originated from a spoofed sender that impersonated a Meetings Services Assistant at the United Nations General Assembly Secretariat. Proofpoint did not observe these campaigns targeting the United Nations (UN), but did observe the targeting of diplomatic entities in Europe under the pretense of communicating with the UN. The threat actor achieved this impersonation by utilizing the legitimate email marketing service SMTP2Go, which allows users to alter the envelope sender field while using a unique sender address generated by the service.
TA416 has used SMTP2Go to impersonate various European diplomatic organizations since at least 2020. The threat actor in an August 2020 campaign impersonated the same Meetings Services Assistant at the UN General Assembly and again targeted governmental entities in Europe. In this historical campaign, TA416 delivered a DropBox URL that delivered a PlugX variant aligning with Recorded Future’s analysis of "Red Delta" PlugX malware. Proofpoint assesses that there is sizeable overlap between the entities TA416 and the publicly disclosed group “Red Delta.” Both campaigns from August 2020 and November 2021 targeted European diplomatic entities and utilized SMTP2Go to impersonate an external diplomatic organization that may communicate with the end targets. Included below is a publicly available malicious Zip file hash from August 2020 delivered via a DropBox URL which is attributable to TA416/Red Delta.
Advance version of the 2020 Report of the Secretary-General on Peacebuilding and Sustaining Peace .zip | 0e3e47697539f1773fb53114ab53229c0304d86ed35aec05e5f5bfdf3bd35f9a

Figure 1. TA416 August 2020 “Advance version of the 2020 Report of the Secretary-General on Peacebuilding and Sustaining Peace” PDF decoy 54b491541376bda85ffb02b9bb40b9b5adba644f08b630fc1b47392625e1e60a.
From Web Bugs to PlugX
Proofpoint researchers continued to identify web reconnaissance campaigns in November and December 2021 that utilized a rudimentary style of encoding and resource names. Fundamentally, a web bug URL includes infrastructure that hosts a benign image file, several designations about the email campaign, which can include date and campaign name, and a unique designation for each individual user targeted in the email campaign. This allows a threat actor to validate which recipients received and opened the phishing email. TA416 web bugs appear rudimentary while demonstrating slight evolution over time. The web bug URL structure began with an actor-controlled IP which retrieved jpg resources named after the email aliases of the targeted victims from the actor-controlled servers. Proofpoint researchers next observed base64 encoded values of the entire email address.
Example:
hxxp://45.154.14[.]235/jdoe.jpg  
hxxp://45.154.14[.]235/amRvZUBwcm9vZnBvaW50LmNvbQ==/328.jpg
Researchers identified the same method of base64 encoded target emails, including in the web bug URL, consistently from August to November 2020 in TA416 campaigns that preceded the delivery of PlugX malware. On more than one occasion in 2020, this web bug technique appeared in an email alongside a Dropbox URL that ultimately delivered the Trident Loader variant of PlugX malware. Proofpoint, Avira, and Recorded Future have publicly attributed this installation technique to TA416/Red Delta. In the above referenced campaign from August 2020 in which TA416 impersonated UN personnel, the threat actor utilized base64 encoded web bug resources representing targeted emails alongside the cloud hosted URLs that delivered PlugX malware. Actor-controlled IPs observed during web bug reconnaissance campaigns during the November to December 2021 period included the IP 45.154.14[.]235.
Beginning on January 17, 2022, Proofpoint researchers observed TA416 threat actors utilizing the IP address 45.154.14[.]235 in phishing emails attempting to deliver a malicious Zip file to European Diplomatic entities. These entities had previously received web bug URLs in phishing emails during the prior months. Rather than the emails delivering further reconnaissance URLs, this IP now attempted to deliver malicious Zip files. The phishing email also included a Dropbox URL attempting to deliver the same malicious archive file. Like historical TA416 campaigns, the Zip file had a geopolitically themed title, which was shared with a PDF decoy that would be later downloaded as part of the infection chain. For example, the campaign on January 17, 2022 included the following Zip and PDF file titles:
State_aid__Commission_approves_2022-2027_regional_aid_map_for_Greece.zip 
State_aid__Commission_approves_2022-2027_regional_aid_map_for_Greece.pdf

Figure 2. TA416 January 2021 PDF decoy - EU adopts conclusions on EU priorities in UN human rights fora in 2022.zip.
While historically TA416 has delivered Zip files from cloud hosting providers containing a decoy file, legitimate PE file, a DLL loader, and a PlugX malware configuration DAT file, recent campaigns used a different tactic. Proofpoint researchers noted that the malicious Zip files delivered from DropBox now contain a rudimentary executable which is a dropper malware. This malware establishes persistence for a legitimate executable file used in DLL search order hijacking, as well as initiates the download of four components. These components are included below and resemble the components used in the past to install PlugX malware. Public research has previously documented TA416’s propensity for including PlugX Trident Loader components and decoy in the initial delivered Zip file. Actors in recent months use a more convoluted delivery chain, in which a PE dropper is used to retrieve the Trident Loader components from an actor-controlled resource. The method of installing PlugX via DLL Search Order hijacking that displays a PDF decoy remains constant.
Requests Resulting from the Execution of Malware Dropper Executable
PDF Decoy File
hxxps://45.154.14[.]235/State_aid__Commission_approves_2022- 2027_regional_aid_map_for_Greece.pdf
Legitimate PotPlayer PE file used in DLL Search Order Hijacking 
hxxps://45.154.14[.]235/PotPlayer.exe
Malicious PlugX Malware Loader
hxxps://45.154.14[.]235/PotPlayer.dll
PlugX Malware Configuration Executed by DLL Search Order Hijacking
hxxps://45.154.14[.]235/PotPlayerDB.dat
Most recently on February 28, 2022, TA416 began using a compromised email address of a diplomat from a European NATO country to target a different country’s diplomatic offices. The targeted individual worked in refugee and migrant services. The below URL was sent in a phishing email and delivered a compressed archive containing a PE dropper. This dropper similarly called out to an actor-controlled URL to deliver a decoy document and the components of an updated Trident Loader PlugX malware payload.
hxxp://www.zyber-i[.]com/europa/2022.zip
Situation at the EU borders with Ukraine.zip|8a7fbafe9f3395272548e5aadeb1af07baeb65d7859e7a1560f580455d7b1fac 
Situation at the EU borders with Ukraine.exe|effd63168fc7957baf609f7492cd82579459963f80fc6fc4d261fbc68877f5a1(Stage 1 Dropper)
hxxp://103.107.104.19/2022/eu.docx (Decoy Document)
hxxp://103.107.104.19/FontEDL.exe (PE Legit)
hxxp://103.107.104.19/DocConvDll.dll (DLL Loader)
hxxp://103.107.104.19/FontLog.dat (PlugX Encrypted Payload)
Communicates with C2
hxxps://92.118.188[.]78/

Figure 3. TA416 February 28, 2022 Word document decoy – eu.docx.
A More Discerning Breed of TA416 PlugX Malware
Close analysis of the delivered payloads and legitimate resources retrieved from URLs by the first stage malware dropper reveals that TA416 is once again using an updated version of PlugX malware to target their victims. Historically, the group has relied on a variety of legitimate antivirus files, including the Avast file resource wsc_proxy.exe, to begin the process of DLL search order hijacking that results in PlugX malware installation. In the January 2022 campaigns, TA416 used the PE file potplayermini.exe to initiate DLL search order hijacking. This is a legitimate executable file that is part of the publicly available media player Daum PotPlayer 1.5.29825, which Mandiant has previously documented as being susceptible to search order hijacking since at least 2016. Numerous Chinese APT groups, which are not directly correlated to TA416, have utilized it since that time. This campaign leveraged the vulnerability of potplayermini.exe to load the file PotPlayer.dll which contains an obfuscated launcher that in turn executes the file PotPlayerDB.dat. The file DocConvDll.dll has also intermittently been used as a loader of the PlugX DAT configuration files. For those that are familiar with TA416’s historic tactics, techniques, and procedures (TTPs), this is highly similar to the Trident Loader method which the group used to install PlugX in previous campaigns.
While PotPlayerDB.dat is a variant of PlugX malware, TA416 has updated the payload by changing both its encoding method and expanding the payload’s configuration capabilities. Historically, TA416 relied on the DLL launcher to decode the PlugX payload utilizing an XOR key included at the offset 0 within the PlugX DAT configuration file. In this case, TA416 has abandoned that approach in favor of something with less dependencies that is more convoluted. The latest version contains obfuscation to thwart analysis. One of the main ways it does this is by resolving API functions during runtime. Generally, malware loads a DLL, iterates over the set of exports of the DLL and hashes the string, looking for a matching hash. This iteration of PlugX does standard API hashing, but only to resolve the address of the functions GetProcAddress as well as LoadLibrary. Once those functions are resolved properly, it loads the rest of the functions via their text name.

Figure 4. PlugX malware API hashing method.
In addition to this obfuscation attempt, most of the functions that contain the "business logic" of the malware are obfuscated with a state machine. At a high level this obscures the order of which blocks are executed within a function. It does this by maintaining a state variable with many comparisons in the function. After each block, the state variable is modified to whatever the subsequent block should be, making analysis more difficult. This sample further implements anti-analysis techniques via the malware’s design. After every iteration of the state machine, the malware sample will modify the state with a XOR operation. This makes it difficult to analyze as the states are not hardcoded as the result of a function. This control obfuscation is apparent below with the highly cyclical nature of the control flow graph.

Figure 5. PlugX malware control flow graph.
Once researchers defeated the PlugX anti-analysis techniques, they were able to examine the malware’s configuration. Notably the configuration contained three additional fields that were not present in the previous versions nor in standard PlugX malware. The new version included:
Two hardcoded dates for latest write time used to filter over files within a specified directory.
A minimum and maximum file size to filter over files within a specified directory.
A format string that defaults to “public/Publics” that modifies characteristics of the folder and hide it from the infected user.
In the past, when fields have been added to PlugX malware configurations they have persisted in future samples identified in subsequent campaigns. Recently, this has not always proven to be true. In recent campaigns, a consistent and clear configuration that is repeated has not been present. The expansion of the malware’s configuration fields demonstrates that this tool is undergoing additional development by TA416. Further, the type of added features that enable better filtering of victim files for exfiltration and better concealment from the infected user demonstrates that the actor is going beyond anti-analysis to create a more functional and precise tool to use during intrusions. It also indicates the varying versions of the PlugX payload that are being used in a short period of time.
Command and Control
The January 2022 version of PlugX malware utilizes RC4 encryption along with a hardcoded key that is built dynamically. For communications, the data is compressed then encrypted before sending to the command and control (C2) server and the same process in reverse is implemented for data received from the C2 server. Below shows the RC4 key "sV!e@T#L$PH%" as it is being passed along with the encrypted data. The data is compressed and decompressed via LZNT1 and RtlDecompressBuffer. During the January 2022 campaigns, the delivered PlugX malware samples communicated with the C2 server 92.118.188[.]78 over port 187. In the February 2022 campaign, Proofpoint researchers observed a variation in which PlugX malware used an RC4 key that was sent to the bot in the first HTTP response which was then used to encrypt data going to the C2 server.

Figure 6. PlugX malware RC4 encryption key with encrypted data.
A Rapid Pace of Malware Development
In response to historical disclosures detailing TA416 PlugX malware infection and encoding methods, the group appears to have adopted a rapid rate of development for their PlugX payloads. While the distinctly TA416 installation method of a PE dropper retrieving Trident loaded payload components using a legitimate PE and a DLL loader file to load a PlugX payload remains constant, the components in this infection chain are regularly changing. The group uses different legitimate PE files to initiate sideloading, as well as a variety of PlugX DLL loaders including the PotPlayer and DocCon versions noted in this publication. TA416 also uses different variants of the final PlugX payload in which the communication routines are observed to be different when closely analyzed. Additionally, the payload DAT file decryption method has evolved regularly since the beginning of 2022. Several observed decryption schemas and a sample configuration are included below with date ranges detailing the evolution of observed PlugX payloads.

Figure 7. 2020 - 2022 PlugX DAT file decryption.

Figure 8. January 2022 – February 2022 PlugX DAT file decryption.

Figure 9. Mid-February 2022 PlugX DAT file decryption.

Figure 10. PlugX malware configuration sample.
Attribution
Proofpoint researchers assess with high confidence that the operator identified in recent campaigns delivering PlugX malware is the same as previously identified in 2020 as part of Recorded Future's Red Delta campaign. This assessment is based on the use of the same email marketing service to deliver emails, the consistent impersonation of European diplomatic entities, the repetition of web bug patterns in the 2020, 2021, and 2022 campaigns, the consistent victimology observed between the campaigns, a nearly identical file naming structure observed between Zip and PDF decoy files, and the highly similar Trident Loader TTPs used for the execution of PlugX malware.

Tactic


2020 
TA416 Campaigns


2021 – 2022 
TA416 Campaigns


Spoofing Via SMPT2Go








Impersonation of UN Personnel








Rudimentary Base64 Web Bugs








Trident Loaded PlugX








Politically Themed PDF Decoys








Shared Zip and PDF Decoy File Names








Targeted European Diplomatic Entities







Figure 11. Mapping TA416 TTPs over time.
Conclusion
The multiyear campaign against diplomatic entities in Europe suggests a consistent area of responsibility belonging to TA416. This mandate may have increased against entities in Europe during the current period of geopolitical conflict and economic upheaval in Europe. While historically the phishing tactics and tools of this group have not been so thoroughly explored, the consistent reliance on updating PlugX malware installation using the Trident Loader method belies a lack of innovation on the part of TA416 following several major publications surrounding this actor. TA416 has chosen to compensate for this lack of innovation with a greater tempo of variation. The group has proved to be pragmatic, making incremental and staggered changes to their PlugX toolkit rapidly and regularly altering a toolset it has used for the past number of years. Despite these variations, the group’s persistent targeting of a habitual target set paired with ingrained phishing tactics often leads to periodic discovery by threat researchers. Once TA416 reads this latest publication regarding their tactics, researchers at Proofpoint fully anticipate they will remain the metaphorical “Tubthumping” of the APT landscape. Researchers can publish their tactics but will never keep them down.
Indicators of Compromise (IOCs)  

IOC


Type of IOC


Description


hxxps://45.154.14[.]235/State_aid__Commission_approves_2022-2027_regional_aid_map_for_Greece.zip 


URL 


Malicious Delivery URL


hxxps://www.dropbox[.]com/s/State_aid__Commission_approves_2022-2027_regional_aid_map_for_Greece.zip?dl=1 


URL 


Malicious Delivery URL


hxxps://www.dropbox[.]com/s/EU adopts conclusions on EU priorities in UN human rights fora in 2022.zip/?dl=1 


URL 


Malicious Delivery URL


hxxps://www.dropbox[.]com/s/EU%20adopts%20conclusions%20on%20EU%20priorities%20in%20UN%20human%20rights%20fora%20in%202022.zip/?dl=1 


URL 


Malicious Delivery URL


hxxps://uepspr[.]com/2023/EU%20adopts%20conclusions%20on%20EU%20priorities%20in%20UN%20human%20rights%20fora%20in%202022.zip 


URL 


Malicious Delivery URL


hxxps://uepspr[.]com/2023/EU adopts conclusions on EU priorities in UN human rights fora in 2022.zip 


URL 


Malicious Delivery URL


hxxps://www.dropbox[.]com/s/EU adopts conclusions on EU priorities in UN human rights fora in 2022.zip/?dl=1 


URL 


Malicious Delivery URL


hxxps://www.dropbox[.]com/s/EU%20adopts%20conclusions%20on%20EU%20priorities%20in%20UN%20human%20rights%20fora%20in%202022.zip/?dl=1 


URL 


Malicious Delivery URL


hxxps://uepspr[.]com/2023/EU%20adopts%20conclusions%20on%20EU%20priorities%20in%20UN%20human%20rights%20fora%20in%202022.zip 


URL 


Malicious Delivery URL


hxxps://uepspr[.]com/2023/EU adopts conclusions on EU priorities in UN human rights fora in 2022.zip  


URL 


Malicious Delivery URL


https://upespr[.]com/Council conclusions on the European security situation.zip 


URL 


Malicious Delivery URL


hxxps://45.154.14[.]235/mfa/Council%20conclusions%20on%20the%20European%20security%20situation.pdf 


URL 


Malicious Delivery URL


hxxp://www.zyber-i[.]com/europa/2022.zip 


URL 


Malicious Delivery URL


hxxps://69.90.184[.]125/lt/2023.rar 


URL 


Malicious Delivery URL


Council conclusions on the European security situation.exe


6fd9d745faa77a58ac84a5a1ef360c7fc1e23b32d49ca9c3554a1edc4d761885 


Executable File


Malicious PE Dropper


State_aid__Commission_approves_2022-2027_regional_aid_map_for_Greece.exe


5851043b2c040fb3dce45c23fb9f3e8aefff48e0438dec7141999062d46c592d


Executable File


Malicious PE Dropper


Situation at the EU borders with Ukraine.exe


effd63168fc7957baf609f7492cd82579459963f80fc6fc4d261fbc68877f5a1


Executable File


Malicious PE Dropper


REGULATION OF THE EUROPEAN PARLIAMENT AND OF THE COUNCIL.exe


b2ff5535caa1d70c9d0d59cd68619b142858ae018064c891b4671154aa93abf3 


Executable File


Malicious PE Dropper


Advance version of the 2020 Report of the Secretary-General on Peacebuilding and Sustaining Peace.pdf


54b491541376bda85ffb02b9bb40b9b5adba644f08b630fc1b47392625e1e60a 


PDF File


Decoy Files 


Council conclusions on the European security situation.pdf


a4ff2c5913cce536759777acee3cfcc8824b927304c8a93ac64d37d1b01a576f


PDF File


Decoy Files 


Situation at the EU borders with Ukraine.docx


a07cece1fa9b3c813c0b6880b24a6494a9db83e138102da3bce30ebff51909c0


Doc File


Decoy Files 


REGULATION OF THE EUROPEAN PARLIAMENT AND OF THE COUNCIL.pdf


0c2f5b6fe538d088fed11ab10925210cb2eb782f471e6f09c484677e82fc5f26 


PDF File


Decoy Files 


State_aid__Commission_approves_2022-2027_regional_aid_map_for_Greece.pdf


ec32ff0c049bd8812a35aeaaaae1f66eaf0ce8aefce535d142862ae89435c2e2 


PDF File


Decoy Files 


PotPlayer.exe


76da9d0046fe76fc28b80c4c1062b17852264348fd873b7dd781f39491f911e0


Executable File 


Legit PE File for DLL Search Order Hijacking 


FontEDL.exe


19870dd4d8c6453d5bb6f3b2beccbbbe28c6f280b6a7ebf5e0785ec386170000 


Executable File 


Legit PE File for DLL Search Order Hijacking 


PotPlayer.dll


e1dbe58393268d7ddabd4bed0cdedf0fbba85d4c3ef1300580ed4c74e147aa61 


DLL File 


Malicious Loader DLL


DocConvDll.dll


436d5bf9eba974a6e97f6f5159456c642e53213d7e4f8c75db5275b66fedd886 


DLL File 


Malicious Loader DLL


DocConvDll.dll


a01f353c92afcd45b5731815c79f1e1d01366cefa75b41550a28d999857c5b88 
 


DLL File 


Malicious Loader DLL


PotPlayer.dll


472822c6bdc710175987eb7d9171f780c974a83ea2b26f117b748babb9b796b8 


DLL File 


Malicious Loader DLL


PotPlayerDB.dat


fac8de00f031299f6c698b34534d6523428b544aad6a40fdc4b000a04ee82e7c 


DAT File


PlugX Malware Payload


FontLog.dat


82df9817d0a8dca7491b0688397299943d9279e848cdc4a5446d3159d8d71e6f 


DAT File


PlugX Malware Payload


FontLog.dat


b9e330373b382beaf4f0bcce83d65f13399d42dc3e9fcdc7b4ef26fa89360762 


DAT File


PlugX Malware Payload


PotPlayerDB.dat


03a836034360841fd6b99927c5b639d074e9fce4f16bd4f77ab57a9e5c12d976 


DAT File


PlugX Malware Payload


hxxps://45.154.14[.]235/2023/PotPlayer.exe 


URL


Malware Delivery URL


hxxps://45.154.14[.]235/2023/PotPlayer.dll 


URL


Malware Delivery URL


hxxps://45.154.14[.]235/2023/PotPlayerDB.dat  


URL


Malware Delivery URL


hxxp://103.107.104[.]19/2022/eu.docx 


URL


Malware Delivery URL


hxxp://103.107.104[.]19/FontEDL.exe  


URL


Malware Delivery URL


hxxp://103.107.104[.]19/DocConvDll.dll 


URL


Malware Delivery URL


hxxp://103.107.104[.]19/FontLog.dat 


URL


Malware Delivery URL


hxxps://69.90.184[.]125/lt/2022.pdf 


URL


Malware Delivery URL


hxxps://69.90.184[.]125/lt/FontEDL.exe 


URL


Malware Delivery URL


hxxps://69.90.184[.]125/lt/DocConvDll.dll 


URL


Malware Delivery URL


hxxps://69.90.184[.]125/lt/FontLog.dat 


URL


Malware Delivery URL


hxxps://45.154.14[.]235/State_aid__Commission_approves_2022-2027_regional_aid_map_for_Greece.pdf 


URL


Malware Delivery URL


hxxps://45.154.14[.]235/PotPlayer.exe 


URL


Malware Delivery URL


hxxps://45.154.14[.]235/PotPlayer.dll 


URL


Malware Delivery URL


hxxps://45.154.14[.]235/PotPlayerDB.dat 


URL


Malware Delivery URL


hxxp://upespr[.]com/PotPlayerDB.dat 


URL


Malware Delivery URL


hxxp://upespr[.]com/State_aid__Commission_approves_2022-2027_regional_aid_map_for_Greece.pdf 


URL


Malware Delivery URL


hxxp://upespr[.]com/PotPlayer.dll 


URL


Malware Delivery URL


hxxp://upespr[.]com/PotPlayer.exe 


URL


Malware Delivery URL


hxxps://45.154.14[.]235/State_aid__Commission_approves_2022-2027_regional_aid_map_for_Greece.pdf 


URL


Malware Delivery URL


hxxps://45.154.14[.]235/PotPlayer.exe 


URL


Malware Delivery URL


hxxps://45.154.14[.]235/PotPlayer.dll 


URL


Malware Delivery URL


hxxps://45.154.14[.]235/PotPlayerDB.dat 


URL


Malware Delivery URL


103.107.104[.]19 


IP


Actor-Controlled IP 


69.90.184[.]125 


IP


Actor-Controlled IP 


45.154.14[.]235 


IP


Actor-Controlled IP 


upespr[.]com 


Domain


Actor-Controlled Domain 


www.zyber-i[.]com 


Domain


Actor-Controlled Domain 


hxxps://92.118.188[.]78 


URL


PlugX C2 IP 

Emerging Threats Signatures
2851112          ETPRO TROJAN ta416 Related PlugX Activity (POST)
 






Previous Blog Post


Next Blog Post







Subscribe to the Proofpoint Blog

























About


Overview
Why Proofpoint
Careers
Leadership Team
News Center
Nexus Platform
Privacy and Trust




Threat Center


Threat Hub
Cybersecurity Awareness Hub
Ransomware Hub
Threat Glossary
Threat Blog








Products


Email Security & Protection
Advanced Threat Protection
Security Awareness Training
Cloud Security
Archive & Compliance
Information Protection
Product Bundles




Resources


White Papers
Webinars
Data Sheets
Events
Customer Stories
Blog
Free Trial








Connect


+1-408-517-4710
Contact Us
Office Locations
Request a Demo




Support


Support Login
Support Services
IP Address Blocked?
















Facebook
Twitter
linkedin
Youtube





English (US)
English (UK)
English (AU)
Español
Deutsch
Français
Italiano
Português
日本語
한국어





© 2024. All rights reserved.
            Terms and conditions
Privacy Policy
Sitemap

 







 

















