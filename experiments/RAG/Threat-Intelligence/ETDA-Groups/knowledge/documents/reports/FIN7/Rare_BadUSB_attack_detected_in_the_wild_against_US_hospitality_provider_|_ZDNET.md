# Reference for threat actor for "FIN7"

**Title**: Rare BadUSB attack detected in the wild against US hospitality provider | ZDNET

**Source**: https://www.zdnet.com/article/rare-badusb-attack-detected-in-the-wild-against-us-hospitality-provider/

## Content




Rare BadUSB attack detected in the wild against US hospitality provider | ZDNET


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
      
    Rare BadUSB attack detected in the wild against US hospitality provider
   
    Hackers use snail-mail to send target company an envelope with a malware-laced USB thumb drive.
      Written by 
            Catalin Cimpanu, Contributor   March 26, 2020 at 6:00 a.m. PT                      A US hospitality provider has recently been the target of an incredibly rare BadUSB attack, ZDNet has learned from cyber-security firm Trustwave.The attack happened after the company received an envelope containing a fake BestBuy gift card, along with a USB thumb drive.The receiving company was told to plug the USB thumb drive into a computer to access a list of items the gift card could be used for.     Image: TrustwaveBut in reality, the USB thumb drive was what security experts call a "BadUSB" -- a USB thumb drive that actually functions as a keyboard when connected to a computer, where it emulates keypresses to launch various automated attacks.Trustwave, who couldn't reveal the target company's name for confidentiality reasons, said the victim recognized the attempted hack and called it in to investigate the incident.In a report published today and shared with ZDNet, Trustwave said that once they plugged the BadUSB into a test workstation, the BadUSB triggered a series of automated keypresses that launched a PowerShell command.This Powershell command downloaded a bulkier PowerShell script from an internet site and then installed malware on the test machine -- a JScript-based bot.     Image: Trustwave"At the time of the analysis, we did not found a similar strain of malware," Phil Hay, Senior Research Manager at Trustwave, told ZDNet in an email yesterday."The malware is unknown to us. It is also hard to say if it is custom-built, but it probably is, because it is not wide spread and seems to be targeted," Hay added.However, the Trustwave researcher also told us that since their initial analysis, a file similar to the malware they analyzed was later uploaded on VirusTotal, a web-based file scanning engine. Per subsequent analysis from Facebook and Kaspersky researchers, the file is believed to be the work of a hacking group known as FIN7.It is unclear who uploaded this file, or if it comes from another cyber-security vendor also investigating a BadUSB attack at another victim.But the lesson here is that someone actually detected a BadUSB attack in the real world. BadUSB attacks were first detailed at the start of the 2010s, and for many years they represented a theoretical attack scenario, something that employees are often warned about, but which has rarely been seen in the wild."These sorts of [BadUSB] attacks are often simulated in penetration testing and used during red teaming exercises," Hay told ZDNet. "Seeing these types of attacks in the real world is much more rare."An FBI spokesperson told ZDNet that any users or companies who receive  malware-laced USBs should report the incident to their local FBI office  for further investigations.  Last known attack happened two years ago in Eastern EuropeThe last known case of a BadUSB attack -- also known as a Bash Bunny attack -- was detailed in December 2018 by Russian cyber-security firm Kaspersky.At the time, the company said it found BadUSB devices, along with cheap laptops and Raspberry Pi boards, on location at eight banks in Eastern Europe. The banks called Kaspersky to investigate a series of mysterious cyber-heists during which hackers stole tens of millions of dollars.
    10 worst hacks and data breaches of 2019 (in pictures)
               Security    

          8 habits of highly secure remote workers
         

          How to find and remove spyware from your phone
         

          The best VPN services: How do the top 5 compare?
         

          How to find out if you are involved in a data breach -- and what to do next
            

            8 habits of highly secure remote workers
           

            How to find and remove spyware from your phone
           

            The best VPN services: How do the top 5 compare?
           

            How to find out if you are involved in a data breach -- and what to do next
           Editorial standards  Show Comments  
          Log In to Comment
         Community Guidelines     Related   
      3 million smart toothbrushes were not used in a DDoS attack after all, but it could happen
      
      Microsoft and OpenAI detect and disrupt nation-state cyber threats that use AI, report shows
      
      Meet Rufus: Amazon launches an AI chatbot to help shoppers
              ZDNET we equip you to harness the power of disruptive innovation, at work and at home. TopicsGalleriesVideosDo Not Sell or Share My Personal Information about ZDNETMeet The TeamSitemapReprint Policy Join |
    Log InNewslettersSite AssistanceLicensing     
  © 2024 ZDNET, A Red Ventures company. All rights reserved.
 Privacy Policy |
  Cookie Settings |
  Advertise |
  Terms of Use 


