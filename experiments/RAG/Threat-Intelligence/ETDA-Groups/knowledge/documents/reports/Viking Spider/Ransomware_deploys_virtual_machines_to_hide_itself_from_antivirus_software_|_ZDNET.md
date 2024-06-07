# Reference for threat actor for "Viking Spider"

**Title**: Ransomware deploys virtual machines to hide itself from antivirus software | ZDNET

**Source**: https://www.zdnet.com/article/ransomware-deploys-virtual-machines-to-hide-itself-from-antivirus-software/

## Content




Ransomware deploys virtual machines to hide itself from antivirus software | ZDNET


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
      
    Ransomware deploys virtual machines to hide itself from antivirus software
   
    The operators of the RagnarLocker ransomware are running Oracle VirtualBox to hide their presence on infected computers inside a Windows XP virtual machine.
      Written by 
            Catalin Cimpanu, Contributor   May 21, 2020 at 5:49 p.m. PT                      See als 
          10 dangerous app vulnerabilities to watch out for (free PDF)
        The operators of the RagnarLocker ransomware are installing the VirtualBox app and running virtual machines on computers they infect in order to run their ransomware in a "safe" environment, outside the reach of local antivirus software.This latest trick has been spotted and detailed today by UK cyber-security firm Sophos and shows the creativity and great lengths some ransomware gangs will go to avoid detection while attacking a victim.What's RagnarLocker?Avoiding detection is crucial because RagnarLocker is not your typical ransomware gang. They're a group that carefully selects targets, avoiding home consumers, and goes after corporate networks and government organizations only.Sophos says the group has targeted victims in the past by abusing internet-exposed RDP endpoints and has compromised MSP (managed service provider) tools to breach companies and gain access to their internal networks.On these networks, the RagnarLocker group deploys a version of their ransomware -- customized per each victim -- and then demands an astronomical decryption fee in the tune of tens and hundreds of thousands of US dollars.Because each of these carefully planned intrusions represents a chance to earn large amounts of money, the RagnarLocker group has put a primer on stealth and has recently come up with a novel trick to avoid detection by antivirus software.The virtual machine trickThe "trick" is actually pretty simple and clever when you think of it.Instead of running the ransomware directly on the computer they want to encrypt, the RagnarLocker gang downloads and installs Oracle VirtualBox, a type of software that lets you run virtual machines.The group then configures the virtual machine to give it full access to all local and shared drives, allowing the virtual machine to interact with files stored outside its own storage.The next step is to boot up the virtual machine, running a stripped-down version of the Windows XP SP3 operating system, called MicroXP v0.82.The final phase is to load the ransomware inside the virtual machine (VM) and run it. Because the ransomware runs inside the VM, the antivirus software won't be able to detect the ransomware's malicious process.From the antivirus software's point of view, files on the local system and shared drives will suddenly be replaced with their encrypted versions, and all the file modifications appear to come from a legitimate process -- namely the VirtualBox app.Mark Loman, director of engineering and threat mitigation at Sophos told ZDNet today that this is the first time he's seen a ransomware gang abuse virtual machines during an attack."In the last few months, we've seen ransomware evolve in several ways. But, the Ragnar Locker adversaries are taking ransomware to a new level and thinking outside of the box," he added.An overview of the entire RagnarLocker ransomware, including its VM trick, is available in Sophos' recent report.
    Europol’s top hacking ring takedowns
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
      Microsoft and OpenAI detect and disrupt nation-state cyber threats that use AI, report shows
      
      Secure a reliable IT education resource — $60 for Presidents' Day
      
      LinuxONE 4 Express: How IBM's budget mainframe could be right for you
              ZDNET we equip you to harness the power of disruptive innovation, at work and at home. TopicsGalleriesVideosDo Not Sell or Share My Personal Information about ZDNETMeet The TeamSitemapReprint Policy Join |
    Log InNewslettersSite AssistanceLicensing     
  © 2024 ZDNET, A Red Ventures company. All rights reserved.
 Privacy Policy |
  Cookie Settings |
  Advertise |
  Terms of Use 


