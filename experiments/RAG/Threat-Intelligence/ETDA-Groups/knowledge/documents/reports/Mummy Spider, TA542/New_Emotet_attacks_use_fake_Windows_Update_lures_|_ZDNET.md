# Reference for threat actor for "Mummy Spider, TA542"

**Title**: New Emotet attacks use fake Windows Update lures | ZDNET

**Source**: https://www.zdnet.com/article/new-emotet-attacks-use-fake-windows-update-lures/

## Content




New Emotet attacks use fake Windows Update lures | ZDNET


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
      
    New Emotet attacks use fake Windows Update lures
   
    Emotet diversifies arsenal with new lures to trick users into infecting themselves.
      Written by 
            Catalin Cimpanu, Contributor   Oct. 15, 2020 at 6:27 a.m. PT                          In today's cyber-security landscape, the Emotet botnet is one of the largest sources of malspam — a term used to describe emails that deliver malware-laced file attachments.  These malspam campaigns are absolutely crucial to Emotet operators.  They are the base that props up the botnet, feeding new victims to the Emotet machine — a Malware-as-a-Service (MaaS) cybercrime operation that's rented to other criminal groups.  To prevent security firms from catching up and marking their emails as "malicious" or "spam," the Emotet group regularly changes how these emails are delivered and how the file attachments look.  Emotet operators change email subject lines, the text in the email body, the file attachment type, but also the content of the file attachment, which is as important as the rest of the email.  That's because users who receive Emotet malspam, besides reading the email and opening the file, they still need to allow the file to execute automated scripts called "macros." Office macros only execute after the user has pressed the "Enable Editing" button that's shown inside an Office file.       Image: MicrosoftTricking users to enable editing is just as important to malware operators as the design of their email templates, their malware, or the botnet's backend infrastructure.  Across the years, Emotet has developed a collection of boobytrapped Office documents that use a wide variety of "lures" to convince users to click the "Enable Editing" button.  This includes:  Documents claiming they've been compiled on a different platform (i.e., Windows 10 Mobile, Android, or iOS) and the user needs to enable editing for the content to appear.Documents claiming they've been compiled in older versions of Office and the user needs to enable editing for the content to appear.  Documents claiming to be in Protected View and asking the user to enable editing. (Ironically, the Protected View mechanism is the one blocking macros and showing the Enable Editing button/restriction.)Documents claiming to contain sensitive or limited-distribution material that's only visible after the user enables editing.Documents showing fake activation wizards and claiming that Office activation has been completed and the user only needs to click enable editing to use Office; and many more.But this week, Emotet arrived from a recent vacation with a new document lure.  File attachments sent in recent Emotet campaigns show a message claiming to be from the Windows Update service, telling users that the Office app needs to be updated. Naturally, this must be done by clicking the Enable Editing button (don't press it).       Image: @catnap707/TwitterAccording to an update from the Cryptolaemus group, since yesterday, these Emotet lures have been spammed in massive numbers to users located all over the world.  Per this report, on some infected hosts, Emotet installed the TrickBot trojan, confirming a ZDNet report from earlier this week that the TrickBot botnet survived a recent takedown attempt from Microsoft and its partners.These boobytrapped documents are being sent from emails with spoofed identities, appearing to come from acquaintances and business partners.  Furthermore, Emotet often uses a technique called conversation hijacking, through which it steals email threads from infected hosts, inserts itself in the thread with a reply spoofing one of the participants, and adding the boobytrapped Office documents as attachments.  The technique is hard to pick up, especially among users who work with business emails on a daily basis, and that is why Emotet very often manages to infect corporate or government networks on a regular basis.  In these cases, training and awareness is the best way to prevent Emotet attacks. Users who work with emails on a regular basis should be made aware of the danger of enabling macros inside documents, a feature that is very rarely used for legitimate purposes.  Knowing how the typical Emotet lure documents look like is also a good start, as users will be able to dodge the most common Emotet tricks when one of these emails lands in their inboxes, even from a known correspondent.  Below is a list of the most popular Emotet document lures, according to a list shared with ZDNet by security researcher @ps66uk.        Image: Cryptolaemus     Image: Sophos     Image: @pollo290987/Twitter     Image: @ps66uk/Twitter     Image: Cryptolaemus     Image: Cryptolaemus     Image: @JAMESWT_MHT/Twitter     Image: @ps66uk/Twitter     Image: @ps66uk/Twitter     Image: @ps66uk/Twitter     Image: @Myrtus0x0/Twitter     Image: Cryptolaemus     Image: @catnap707/Twitter     Image: @ps66uk/Twitter     Image: @ps66uk/Twitter Security    

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
      Bumble's new 'Deception Detector' uses AI to weed out fake dating profiles
      
      3 million smart toothbrushes were not used in a DDoS attack after all, but it could happen
      
      Sick of mistaking legit calls for spam? This new AT&T wireless service might help
              ZDNET we equip you to harness the power of disruptive innovation, at work and at home. TopicsGalleriesVideosDo Not Sell or Share My Personal Information about ZDNETMeet The TeamSitemapReprint Policy Join |
    Log InNewslettersSite AssistanceLicensing     
  © 2024 ZDNET, A Red Ventures company. All rights reserved.
 Privacy Policy |
  Cookie Settings |
  Advertise |
  Terms of Use 


