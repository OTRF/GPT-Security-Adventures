# Reference for threat actor for "InvisiMole"

**Title**: Ukraine warns of InvisiMole attacks tied to state-sponsored Russian hackers | ZDNET

**Source**: https://www.zdnet.com/article/ukraine-warns-of-invisimole-attacks-tied-to-state-sponsored-russian-hackers/

## Content




Ukraine warns of InvisiMole attacks tied to state-sponsored Russian hackers | ZDNET


                                         />                                                                                                                                                                                                     X     Trending    CES 2024: 3 trends to watch as we learn what's next in tech ZDNET's product of the year: Meta Quest 3 is the quiet shocker of 2023 Have 10 hours? IBM will train you in AI fundamentals - for free Two breakthroughs made 2023 tech's most innovative year in over a decade Which Windows apps to keep (and which to dump) 7 useful things to do with your Flipper Zero  The Apple Watch to buy this year Meta's $299 Ray-Ban smart glasses may be the most useful gadget I've tested all year iPhone 15 Pro review: Who this upgrade will wow Samsung Galaxy S23 Ultra review: One of the best smartphones of the year Sonos Era 300 review: Close to a perfect smart speaker I tried Apple Vision Pro and it's far ahead of where I expected  Best laptops Best VPNs Best TVs Best Headphones Best robot vacuums ZDNET Recommends  Tech    Gaming Headphones Laptops Mobile Accessories Networking PCs  Printers Smartphones Smart Watches Speakers Streaming Devices Streaming Services  Tablets TVs Wearables  Kitchen & Household Office Furniture Office Hardware & Appliances Smart Home Smart Lighting Yard & Outdoors  Innovation    Artificial Intelligence AR + VR Cloud Digital Transformation Energy  Robotics Sustainability Transportation Work Life  Accelerate your tech game Paid Content How the New Space Race Will Drive Innovation How the metaverse will change the future of work and society  Managing the Multicloud The Future of the Internet The New Rules of Work The Tech Trends to Watch in 2023  Business    See all Business Amazon Apple Developer E-Commerce  Edge Computing Enterprise Software Executive Google Microsoft  Professional Development Social Media SMB Windows  Digital transformation: Trends and insights for success Software development: Emerging trends and changing roles  Security      See all Security Cyber Threats Password Manager Ransomware VPN  Cybersecurity: Let's get tactical Securing the Cloud  Advice      Deals How-to Product Comparisons Product Spotlights Reviews  Buying Guides    See all Buying Guides Best all-in-one computers Best budget TVs Best gaming CPUs Best gaming laptops Best gaming PCs  Best headphones Best iPads Best iPhones Best laptops Best large tablets Best OLED TVs  Best robot vacuum mops Best rugged tablets Best Samsung phones Best smart rings Best smartphones Best smartwatches  Best speakers Best tablets Best travel VPNs Best TVs Best VPNs Best Coupons   tomorrow belongs to those who embrace it today       
          Asia
        
          Australia
        
          Europe
        
          India
        
          United Kingdom
        
          United States
         ZDNET France ZDNET Germany ZDNET Korea ZDNET Japan        Go  Most Popular          See all Topics Finance Education Health  Special Features ZDNET In Depth ZDNET Recommends  Newsletters Videos Editorial Guidelines        Trending  CES 2024: 3 trends to watch as we learn what's next in tech ZDNET's product of the year: Meta Quest 3 is the quiet shocker of 2023 Have 10 hours? IBM will train you in AI fundamentals - for free Two breakthroughs made 2023 tech's most innovative year in over a decade Which Windows apps to keep (and which to dump) 7 useful things to do with your Flipper Zero The Apple Watch to buy this year Meta's $299 Ray-Ban smart glasses may be the most useful gadget I've tested all year iPhone 15 Pro review: Who this upgrade will wow Samsung Galaxy S23 Ultra review: One of the best smartphones of the year Sonos Era 300 review: Close to a perfect smart speaker I tried Apple Vision Pro and it's far ahead of where I expected Best laptops Best VPNs Best TVs Best Headphones Best robot vacuums ZDNET Recommends Tech  Gaming Headphones Laptops Mobile Accessories Networking PCs Printers Smartphones Smart Watches Speakers Streaming Devices Streaming Services Tablets TVs Wearables Kitchen & Household Office Furniture Office Hardware & Appliances Smart Home Smart Lighting Yard & Outdoors Innovation  Artificial Intelligence AR + VR Cloud Digital Transformation Energy Robotics Sustainability Transportation Work Life Accelerate your tech game Paid Content How the New Space Race Will Drive Innovation How the metaverse will change the future of work and society Managing the Multicloud The Future of the Internet The New Rules of Work The Tech Trends to Watch in 2023 Business  See all Business Amazon Apple Developer E-Commerce Edge Computing Enterprise Software Executive Google Microsoft Professional Development Social Media SMB Windows Digital transformation: Trends and insights for success Software development: Emerging trends and changing roles Security  See all Security Cyber Threats Password Manager Ransomware VPN Cybersecurity: Let's get tactical Securing the Cloud Advice  Deals How-to Product Comparisons Product Spotlights Reviews Buying Guides  See all Buying Guides Best all-in-one computers Best budget TVs Best gaming CPUs Best gaming laptops Best gaming PCs Best headphones Best iPads Best iPhones Best laptops Best large tablets Best OLED TVs Best robot vacuum mops Best rugged tablets Best Samsung phones Best smart rings Best smartphones Best smartwatches Best speakers Best tablets Best travel VPNs Best TVs Best VPNs Best Coupons More  See all Topics Finance Education Health Special Features ZDNET In Depth ZDNET Recommends Newsletters Videos Editorial Guidelines  Tech     
      Home
    
      Tech
    
      Security
      
    Ukraine warns of InvisiMole attacks tied to state-sponsored Russian hackers
   
    InvisiMole has been collaborating with the Gamaredon APT for years.
      Written by 
            Charlie Osborne, Contributing Writer   March 21, 2022 at 5:49 a.m. PT                      Ukrainian security officials have warned of ongoing attacks by InvisiMole, a hacking group with ties to the Russian advanced persistent threat (APT) group Gamaredon. Ukraine Crisis 
          Coding inside a war zone
        
          How you can help: Donation sites and resources
        
          Ukrainian police take down phishing gang behind payments scam
        
          International Refugee Assistance Project partners with Rosetta Stone to aid refugees
        Last week, the Computer Emergency Response Team for Ukraine (CERT-UA) said that the department has been advised of new phishing campaigns taking place against Ukrainian organizations that spread the LoadEdge backdoor. According to CERT-UA, phishing emails are being sent that have an attached archive, 501_25_103.zip, together with a shortcut (LNK) file. If opened, an HTML Application file (HTA) downloads and executes VBScript designed to deploy LoadEdge.  Once the backdoor has formed a link to an InvisiMole command-and-control (C2) server, other malware payloads are deployed and executed including TunnelMole, malware that abuses the DNS protocol to form a tunnel for malicious software distribution, and both RC2FM and RC2CL, which are data collection and surveillance backdoor modules. Persistence is maintained through the Windows registry.  InvisiMole was first discovered by ESET researchers in 2018. The threat actors have been active since at least 2013 and have been connected to attacks against "high-profile" organizations in Eastern Europe that are involved in military activities and diplomatic missions.  In 2020, the cybersecurity researchers forged a collaborative link between InvisiMole and Gamaredon/Primitive Bear, the latter of which appears to be involved in initially infiltrating networks before InvisiMole begins its own operation.  "We discovered InvisiMole's arsenal is only unleashed after another threat group, Gamaredon, has already infiltrated the network of interest, and possibly gained administrative privileges," ESET said at the time. "This allows the InvisiMole group to devise creative ways to operate under the radar." Palo Alto Networks has also been tracking Gamaredon, and in February, said the APT had attempted to compromise an unnamed "Western government entity" in Ukraine through fake job listings.  CERT-UA has also begun tracking the activities of Vermin/UAC-0020, a group that has been attempting to break into the systems of Ukrainian state authorities. Vermin has been using the topic of supplies in spear phishing emails as a lure, and if opened by a victim, these emails contain a letter and password-protected archive containing the Spectr malware.  In 2018, ESET and Palo Alto Networks published research on Vermin, a group that has been active for at least the past four years, although may date back as far as 2015.  Vermin was targeting Ukrainian government institutions from the outset, with remote access Trojans (RATs) Quasar, Sobaken, and Vermin being the malicious tools of choice.  While the variants of Quasar and Sobaken were compiled using freely-available open source code, Vermin is called a "custom-made" RAT able to perform activities including data exfiltration, keylogging, audio recording, and credential theft.  In related news this month, Aqua Security's Team Nautilus said that public cloud repositories are being used to host resources on both sides of the war, with Ukraine's call for an "IT Army" of volunteers becoming a catalyst for public tools to launch denial-of-service (DoS) attacks against online Russian services.  It is not just RATs and surveillance-based malware that Ukrainian organizations are having to contend with. ESET has detected three forms of wiper malware – designed to destroy computer files and resources, rather than to steal information or spy on victims – in as many weeks.  The latest wiper, dubbed CaddyWiper, has been found "on a few dozen systems in a limited number of organizations," according to ESET.   	 	Previous and related coverage   Security researchers warn of phishing attempts against officials helping refugeesUkraine security agencies warn of Ghostwriter threat activity, phishing campaignsCaddyWiper: More destructive wiper malware strikes UkraineHave a tip? Get in touch securely via WhatsApp | Signal at +447713 025 499, or over at Keybase: charlie0 Editorial standards  Show Comments  
          Log In to Comment
         Community Guidelines     Related   
      3 million smart toothbrushes were not used in a DDoS attack after all, but it could happen
      
      AI breakthrough enables scientists to read Roman scrolls once buried by Mount Vesuvius
      
      Google is making sharing passwords with your family members a lot easier
              ZDNET we equip you to harness the power of disruptive innovation, at work and at home. TopicsGalleriesVideosDo Not Sell or Share My Personal Information about ZDNETMeet The TeamSitemapReprint Policy Join |
    Log InNewslettersSite AssistanceLicensing     
  © 2024 ZDNET, A Red Ventures company. All rights reserved.
 Privacy Policy |
  Cookie Settings |
  Advertise |
  Terms of Use 


