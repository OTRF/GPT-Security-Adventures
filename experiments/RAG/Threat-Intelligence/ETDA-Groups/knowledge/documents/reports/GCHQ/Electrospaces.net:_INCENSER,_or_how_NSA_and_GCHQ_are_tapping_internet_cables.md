# Reference for threat actor for "GCHQ"

**Title**: Electrospaces.net: INCENSER, or how NSA and GCHQ are tapping internet cables

**Source**: https://www.electrospaces.net/2014/11/incenser-or-how-nsa-and-gchq-are.html

## Content



















Electrospaces.net: INCENSER, or how NSA and GCHQ are tapping internet cables


































































































































































November 29, 2014








INCENSER, or how NSA and GCHQ are tapping internet cables





(Last edited: January 9, 2018)

Recently disclosed documents show that the NSA's fourth-largest cable tapping program, codenamed INCENSER, pulls its data from just one single source: a submarine fiber optic cable linking Asia with Europe.

Until now, it was only known that INCENSER was a sub-program of WINDSTOP and that it collected some 14 billion pieces of internet data a month. The latest revelations now say that these data were collected with the help of the British company Cable & Wireless (codenamed GERONTIC, now part of Vodafone) at a location in Cornwall in the UK, codenamed NIGELLA.

For the first time, this gives us a view on the whole interception chain, from the parent program all the way down to the physical interception facility. Here we will piece together what is known about these different stages and programs from recent and earlier publications.


- NIGELLA - GERONTIC - INCENSER - WINDSTOP - 






The cables tapped at NIGELLA by GERONTIC under the INCENSER and WINDSTOP programs
(Map: ARD.de - Text: Electrospaces.net - Click to enlarge)


 


NIGELLA 

Last week's joint reporting by the British broadcaster Channel 4, the German regional broadcasters WDR and NDR and the German newspaper Süddeutsche Zeitung, identified NIGELLA as an interception facility at the intersection of Cable & Wireless and Reliance cables at Skewjack Farm. 

There, just north-west of Polgigga Cottage in Cornwall, is a large building that was constructed in 2001 for FLAG Telecom UK Ltd for 5.3 million pounds. It serves as a terminus for the two ends of a submarine optical cable: one from across the Atlantic which lands at the beach of nearby Sennen, and one that crosses the Channel to Brittany in France:


- FLAG Atlantic 1 (FA1)
Connecting the east coast of North America to the United Kingdom and France (6.000 kilometers)


The FLAG Atlantic 1 cable to America consists of 6 fibre pairs, each capable of carrying 40 (eventually up to 52) separate light wavelengths, and each wavelength can carry 10 Gigabit/s of traffic. This gives a potential capacity of 2.4 terabit/s per cable. However, in 2009, only 640 gigabit/s were actually used, which went apparently up to 921 gigabit/s in 2011. 





The FLAG terminus station in Skewjack Farm, Cornwall
(still from 'The Secrets of Cornwall' - click to enlarge)



The cable was initially owned by FLAG Telecom, where FLAG stands for Fiber-optic Link Around the Globe. This company was renamed into Reliance Globalcom when it became a fully owned subsidiary of the Indian company Reliance Communications (RCOM). In March 2014, Reliance Globalcom was again renamed, now into Global Cloud Xchange (GCX).

More important is another, much longer submarine cable, which was also owned by this company, and which has its landing point on the shore of Porthcurno, a few miles south-west of Skewjack Farm:


- FLAG Europe-Asia (FEA)
Connecting the United Kingdom to Japan through the Mediterranean, with landing points in Egypt, the Saudi Peninsula, India, Malaysia, Thailand, Hong Kong, China, Taiwan, South Korea and Japan (28.000 kilometers)


This cable has 2 fibre pairs, each capable of carrying up to 40 separate light wavelengths, and each wavelength can again carry 10 gigabit/s of traffic. This gives a potential capacity of 800 gigabit/s, but in 2009 only 70 gigabit/s were used, which went up to 130 gigabit/s in 2011 - still an unimaginable 130.000.000.000 bits per second.




The FLAG Atlantic 1 and FLAG Europe-Asia landing points
and the Skewjack Farm terminus station
(Map: Channel 4 - Click to enlarge)



The backhaul connection between the FLAG Atlantic 1 (FA1) and the FLAG Europe-Asia (FEA) is provided by a local area network of Cable & Wireless, which also connects both submarine cables to its terrestrial internet backbone network.

According to the newly disclosed GHCQ Cable Master List from 2009, the interception of the FA1 and the FEA cables takes place at the intersection with this backhaul connection:



This list also shows that the interception of these two cables is accompanied by a Computer Network Exploitation (CNE) or hacking operation codenamed PFENNING ALPHA.

Because the owner of the cables (Reliance Globalcom, now Global Cloud Xchange) is not a cooperating partner of GCHQ, they hacked into their network for getting additional "router monitoring webpages" and "performance statistics for GTE [Global Telecoms Exploitation]". 


Interception equipment

How the actual interception takes place, can be learned from an article in The Guardian from June 2013, which provides some details about the highly sophisticated computer equipment at cable tapping points.

First, the data stream is filtered through what is known as MVR (Massive Volume Reduction), which immediately rejects high-volume, low-value traffic, such as peer-to-peer downloads. This reduces the volume by about 30%.


Selectors

The next step is to pull out packets of information that contain selectors like phone numbers and e-mail, IP and MAC addresses of interest. In 2011, some 40,000 of these were chosen by GCHQ and 31,000 by the NSA, according to The Guardian.  This filtering is most likely done by devices from Boeing-subsidiary Narus, which can analyse high-volume internet traffic in real-time.

A single NarusInsight machine can monitor traffic up to 10 Gigabit/second, which means there have to be up to a dozen of them to filter the relevant traffic from the FA1 and FEA submarine cables. Most of the information extracted in this way is internet content, such as the substance of e-mail messages. 


Full sessions

Besides the filtering by using specific selectors, the data are also sessionized, which means all types of IP traffic, like  VoIP, e-mail, web mail and instant messages are reconstructed. This is something the Narus devices are also capable of.

These "full take" sessions are stored as a rolling buffer on XKEYSCORE servers: content data for only three to five days, and metadata for up to 30 days. But "at some sites, the amount of data we receive per day (20+ terabytes) can only be stored for as little as 24 hours" according to an NSA document from 2008.

The aim is to extract the best 7,5% of the traffic that flows past the access, which is then "backhauled" from the tapping point to GCHQ Bude through two 10 gigabit/s channels (the "egress" capacity). This might be a dedicated cable, or a secure VPN path over the regular Cable & Wireless backbone that connects Bude with the south-west of Cornwall:




The Cable & Wireless internet backbone (yellow) in Cornwall
and the connections to submarine fiber-optic cables (red)
(Map from before 2006 - Click for the full verion)


 


GERONTIC (Cable & Wireless) 

The secret GCHQ documents about these cable tapping operations only refer to the cooperating telecommunications provider with the cover name GERONTIC. The real name is protected by STRAP 2 dissemination restrictions. But nonetheless, German media already revealed that GERONTIC is Cable & Wireless last year. 

In july 2012, Cable & Wireless Worldwide was taken over by Vodafone for 1.04 billion pounds, but according to the GCHQ documents, the covername GERONTIC was continued, and was seen active until at least April 2013.

According to the press reports, GCHQ had access to 63 undersea internet cables, 29 of which with the help of GERONTIC. This accounted for about 70% of the total amount of internet data that GCHQ had access to in 2009.

Cable & Wireless was involved in these 29 cables, either because it had Direct Cable Ownership (DCO), an Indefeasible Right of Use (IRU) or Leased Capacity (LC). Besides that, the GCHQ Cable Master List from 2009 lists GERONTIC also as a landing partner for the following nine cables:


- FLAG Atlantic 1 (FA1)
- FLAG Europe-Asia (FEA)
- Apollo North
- Apollo South
- Solas
- UK-Netherlands 14
- UK-France 3
- Europe India Gateway (EIG)
- GLO-1


Disclosed excerpts from internal GCHQ wiki pages show that Cable & Wireless held regular meetings with GCHQ from 2008 until at least 2010, in order to improve the access possibilites, like selecting which cables and wavelenghts would provide the best opportunities for catching the communications GCHQ wanted. 

GCHQ also paid Cable & Wireless tens of millions of pounds for the expenses. For example, in February 2009 6 million pound was paid and a 2010 budget references a 20.3 million pound payment to the company. By comparison, NSA paid all its cooperating telecommunications companies a total of 278 million dollars in 2013.


The intensive cooperation between Cable & Wireless and GCHQ may not come as a surprise for those knowing a bit more of British intelligence history. The company already worked with predecessors of GHCQ during World War I: all international telegrams were handed over so they could be copied before being sent on their way, a practice that continued for over 50 years.*

 


INCENSER (DS-300) 

Among the documents about the GCHQ cable tapping is also a small part of an internal glossary. It contains an entry about INCENSER, which says that this is a special source collection system at Bude. This is further specified as the GERONTIC delivery from the NIGELLA access, which can be viewed in XKEYSCORE (XKS):





This entry was also shown in the German television magazine Monitor, although not fully, but without the redactions, so from this source we know the few extra words that were redacted for some reason.


The entry also says that INCENSER traffic is labeled TICKETWINDOW with the SIGINT Activity Designator (Sigad) DS-300. From another source we know that TICKETWINDOW is a system that makes cable tapping collection available to 2nd Party partners. The exact meaning of Sigads starting with DS is still not clear, but probably also denotes 2nd Party collection.


TEMPORA

In Bude, GCHQ has its Regional Processing Center (RPC), which in 2012 had a so-called "Deep Dive" processing capability for 23 channels of 10 gigabit/second each under the TEMPORA program.

TEMPORA comprises different components, like the actual access points to fiber-optic cables, a Massive Volume Reduction (MVR) capability, a sanitisation program codenamed POKERFACE, and the XKEYSCORE system. As we have seen, most of the hardware components are located at the interception point, in this case the facility in Skewjack (NIGELLA).


Analysing

These collection systems can be remotely instructed ("tasked") from Bude, or maybe even also from NSA headquarters. For one part that involves entering the "strong selectors" like phone numbers and internet addresses. For another part, that is by using the additional capabilities of XKEYSCORE.

Because the latter system buffers full take sessions, analysts can also perform queries using "soft selectors", like keywords, against the body texts of e-mail and chat messages, digital documents and spreadsheets in English, Arabic and Chinese. XKEYSCORE also allows analysts to look for the usage of encryption, the use of a VPN or the TOR network, and a number of other things that could lead to a target.

This is particularly useful to trace target's internet activities that are performed anonymous, and therefore cannot be found by just looking for the known e-mail addresses of a target. When such content has been found, the analyst might be able to find new intelligence or new strong selectors, which can then be used for starting a traditional search.

 

Hacking operations

According to a 2010 NSA presentation that was published by The Intercept in December 2014, the INCENSER access is also capable of supporting the QUANTUMBOT (IRC botnet hijacking), QUANTUMBISQUIT (for targets who are behind large proxies), and QUANTUMINSERT (HTML web page redirection) hacking techniques.

Two other components of the QUANTUMTHEORY computer network exploitation framework, QUANTUMSQUEEL (for injection of MySQL databases) and QUANTUMSPIM (for instant messaging), had been tested, but weren't yet operational:





This means that at the INCENSER collection site NIGELLA, there are also TURMOIL sensors which detect when targeted user’s packets are among the traffic that flows past. TURMOIL tips off the central automated command & control system codenamed TURBINE, which then launches one or more QUANTUM attacks, as directed by NSA's hacking division Tailored Access Operations (TAO). An explanation of this method is on the weblog of Robert Sesek and the website of Wired.


Possible targets

The disclosed GCHQ documents contain no specific targets or goals for the INCENSER program, which provided Channel 4 the opportunity to claim that this Cable & Wireless/Vodafone access allows "Britain's spies to gather the private communications of millions of internet users worldwide". Vodafone, which also has a large share of the telecommuncations market in Germany, was even linked to the eavesdropping on chancellor Merkel.

Both claims are rather sensationalistic. Merkel's phone was probably tapped by other means, and both GCHQ and NSA aren't interested in the private communications of ordinary internet users. On the contrary, by tapping into a submarine cable that connects to Asia and the Middle East, INCENSER looks rather focussed at high-priority targets in the latter region.


Update: The redacted source trigraphs of the case notations in the internal GCHQ glossary, which start with IR and YM, seem to point to Iran (Iraq is IQ) and Yemen as target countries of the INCENSER program.



> See also: NSA's Strategic Mission List

Reporting

Despite INCENSER being NSA's fourth-largest cable tapping program regarding to the volume which is collected, the intelligence reports analysts are able to write based upon this only made it to the 11th position of contributors to the President's Daily Brief - according to a slide from a 2010 presentation about Special Source Collection, published by The Washington Post in October last year:




 


WINDSTOP (2nd Party)

Data collected under the INCENSER program are not only used by GHCQ, but also by NSA, which groups such 2nd Party sources under the codename WINDSTOP. As such, INCENSER was first mentioned in a slide that was published by the Washington Post on in October 2013 for a story about the MUSCULAR program:






According to NSA's Foreign Partner Access budget for 2013, which was published by Information and The Intercept last June,  WINDSTOP involves all 2nd Party countries (primarily Britain, but also Canada, Australia and New Zealand) and focusses on access to (mainly internet) "communications into and out of Europe and the Middle East" through an integrated and overarching collection system.


MUSCULAR is a program under which cables linking big data centers of Google and Yahoo are tapped. The intercept facility is also located somewhere in the United Kingdom and the data are processed by GCHQ and NSA in a Joint Processing Centre (JPC) using the Stage 2 version of XKEYSCORE.



A new slide from this presentation about WINDSTOP was published by Süddeutsche Zeitung on November 25, which reveals that a third program is codenamed TRANSIENT THURIBLE. About this program The Guardian reported once in June 2013, saying that it is an XKeyscore Deep Dive capability managed by GHCQ, with metadata flowing into NSA repositories since August 2012.






In November 2013, the Washington Post published a screenshot from BOUNDLESSINFORMANT with numbers about data collection under the WINDSTOP program. Between December 10, 2012 and January 8, 2013, more than 14 billion metadata records were collected:






The bar chart in the top part shows the numbers by date, with DNR (telephony) in green and DNI (internet) in blue. The section in the center of the lower part shows these data were collected by the following programs:


- DS-300 (INCENSER): 14100 million records
- DS-200B (MUSCULAR): 181 million records

 
XKEYSCORE, which is used to index and search the data collected under the INCENSER program, can be seen in the bottom right section of the chart.


With just over 14 billion pieces of internet data a month, INCENSER is the NSA's fourth-largest cable tapping program, accounting for 9 % of the total amount collected by Special Source Operations (SSO), the division responsible for collecting data from internet cables. According to another BOUNDLESSINFORMANT chart, the NSA's Top 5 of cable tapping programs is:





SSO worldwide total:

DANCINGSOASIS:
SPINNERET (part of RAMPART-A):
MOONLIGHTPATH (part of RAMPART-A):
INCENSER (part of WINDSTOP):
AZUREPHOENIX (part of RAMPART-A):
...
Other programs:


 


160.168.000.000 (100%)

57.788.148.908  (36%)
23.003.996.216  (14%)
15.237.950.124   (9%)
14.100.359.119   (9%)
13.255.960.192   (8%)
...
38.000.000.000 (24%)







It's remarkable that just one single cable access (NIGELLA in Cornwall) provides almost one tenth of everything NSA collects from internet cables. This also means that besides a large number of small cables accesses, NSA seems to rely on just a few important cables for about 2/3 of it's collection from this type of source. 



> See also: NSA's largest cable tapping program: DANCINGOASIS




Links and Sources

- Documentary about the cable landing stations: The Secrets of Cornwall
- Golem.de: Die Abhörkette der Geheimdienste
- The recently disclosed documents about GCHQ cable tapping:
   - NetzPolitik.org: Cable Master List: Wir spiegeln die Snowden-Dokumente über angezapfte Glasfasern, auch von Vodafone
   - Sueddeutsche.de: Snowden-Leaks: How Vodafone-Subsidiary Cable & Wireless Aided GCHQ’s Spying Efforts
- ArsTechnica.com: New Snowden docs: GCHQ’s ties to telco gave spies global surveillance reach
- Sueddeutsche.de: Vodafone-Firma soll GCHQ und NSA beim Spähen geholfen haben
- WDR.de: Neue Snowden-Dokumente enthüllen Ausmaß der Zusammenarbeit von Geheimdiensten und Telekommunikationsunternehmen
- TheRegister.co.uk: REVEALED: GCHQ's BEYOND TOP SECRET Middle Eastern INTERNET SPY BASE
- Weblog about Uk Submarine Cable Landings & Cable Stations
- Article about Explaining submarine system terminology – Part 1

- Thanks also to Henrik Moltke, who did most of the research for the German press reports

More reactions on Hacker News and Schneier's Blog







Geplaatst door



P/K




op

23:37











Email ThisBlogThis!Share to TwitterShare to FacebookShare to Pinterest




Labels:
GCHQ,
NSA Partnerships










13 comments:






Anonymous
said...



So, since the program discards traffic such as peer to peer downloads, a person could use that as a means of communication by imbedding messages in files that are sent by that method, as long as the IP addresses of the source and destination were not on the list of addresses of interest.





November 30, 2014 at 5:33 PM












Anonymous
said...



I thought in years past they did this. After all you could easily embed encrypted code into a movie, and supply the key in it as well.





November 30, 2014 at 6:19 PM












Anonymous
said...



Well, they say "high volume P2P" so they are probably looking for some meaningful number of users in the swarm before discarding it.





December 1, 2014 at 2:37 PM












Anonymous
said...



Wouldn't NSA just tap FA1 at it's USA landing point?  Why would they need to tap it on the UK end?





December 1, 2014 at 3:42 PM












Anonymous
said...



^^^ Because tapping US citizens on US soil is an altogether different legal problem.  And US constitution protects US persons against tapping by US government(s), not against tapping by UK which is then shared with US.  Most all of the complexity exists to dance around legal requirements.





December 1, 2014 at 7:58 PM












Anonymous
said...



> Wouldn't NSA just tap FA1 at it's USA landing point? Why would they need to tap it on the UK end?My first guess for why they'd tap in the UK rather than the US is that US privacy laws may not apply to information collected in the UK. This would be an obvious way to sidestep US privacy laws.





December 1, 2014 at 8:56 PM












Anonymous
said...



> My first guess for why they'd tap in the UK rather than the US is that US privacy laws may not apply to information collected in the UK.AFAIK, anything crossing the border can be collected anywhere without legal distinction.  It is the overseas origin or destination that matters, not the point of collection.





December 2, 2014 at 1:24 AM












Anonymous
said...



Exactly.The "Five Eyes", often abbreviated as "FVEY", refer to an intelligence alliance comprising Australia, Canada, New Zealand, the United Kingdom, and the United States. These countries are bound by the multilateral UKUSA Agreement, a treaty for joint cooperation in signals intelligence.http://en.m.wikipedia.org/wiki/Five_Eyes





December 2, 2014 at 3:32 AM












Anonymous
said...



FYI As of yesterday google have taken away the front entrance to the skewjack farm facility from the google maps streetview. It used to show a security Guard at the main entrance.





December 9, 2014 at 2:10 PM












Anonymous
said...



Exactly, the point of collection determines the level of legal protection on offer for US persons.  That's why the taps are in the UK and not the US. See this paper: http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2460462





December 22, 2014 at 7:58 PM












Anonymous
said...



And what is wrong with intelligence agencies listening in or being able to see your Instagram? Most of the traffic circumnavigating the internet is total drivel, of no interest to anyone. Second is undoubtedly porn, we all love it; whether or not we admit it. GCHQ et al would be remiss if they were NOT doing this. We live in dangerous times: never has it been easier for violent ideologists to operate covertly and utilise encrypted comms in the planning of atrocities. Whatsapp is a notable example. I sincerely hope the whizz kids have developed a key, or the authorities can force Facebook to allow access by the intelligence community to whatsapp. Civil liberties must unfortunately play second fiddle to security - to disagree is naive and idealistic.





October 22, 2017 at 10:47 AM












Anonymous
said...



Those who would trade any amount of their liberties, for a greater state of security deserve the shackles and chains of a master. You could learn from those who have lived under tyranny. Naive........ Are you describing your state of mind when you were writing your post?   





January 29, 2018 at 6:38 PM












Unknown
said...



Her the U.S. if ores it's on rules and laws.





February 17, 2021 at 5:54 PM











Post a Comment







Newer Post


Older Post

Home




Subscribe to:
Post Comments (Atom)





► In Dutch: Meer over het wetsvoorstel voor de Tijdelijke wet cyberoperaties

Some older articles on this weblog that are of current interest:
• The highly classified documents found at Trump's residence Mar-a-Lago

• The Snowden files: where are they and where should they end up?

















Welcome!


Here you can read about:- Signals Intelligence,- Communications Security,- Top Level Telecommunications,which means the equipment, from past and present, that makes that civilian and military leaders can safely communicate.► INDEX of all posts on this blogThe main focus will be on the United States and its National Security Agency (NSA), but attention will also be paid to other countries, like Germany and the Netherlands.Any comments, additions, corrections, questions or suggestions will be very appreciated! There's no login or registration required for commenting. twitter.com/electrospaces
 mastodon.social/@Electrospaces
 electrospaces.bsky.social
 info (at) electrospaces.net










Recent Posts

Safe and Free: comparing national legislation on electronic surveillance
Laatste kans voor duidelijkheid over de Tijdelijke wet cyberoperaties [NL]
The NSA's new organizational designators
Some new snippets from the Snowden documents On the 10th anniversary of the Snowden revelations
New details about the Pentagon Leak





"Years of the most fascinating overviews of government security practices, and even-handed reviews of Snowden docs." — SwiftOnSecurity




Pages



Home


INDEX


Abbreviations and Acronyms


NSA Nicknames and Codewords


NSA's TAO Division Codewords


NSA's organizational designations


NSA's Legal Authorities


NSA Glossary


The US classification system


SIGINT Activity Designators (SIGADs)


CIA Codewords and Abbreviations


GCHQ Codewords and Abbreviations


CSE Codewords and Abbreviations


BND Codewords and Abbreviations


Telephony Abbreviations


Internet abbreviations


Links


Books


About





Total Pageviews










Popular Posts



The US Classification System


How Obama's BlackBerry got secured


New phones aboard Air Force One


INCENSER, or how NSA and GCHQ are tapping internet cables


Danish military intelligence uses XKEYSCORE to tap cables in cooperation with the NSA


The British classification marking STRAP







"It's actually straight up interesting but also weird how weirdly, wonderfully detailed this blog about hyper secure communications is." — Gizmodo.com




Labels


Air Force One
(1)


Austria
(2)


BlackBerry
(1)


BND-Selectors
(2)


Boeing
(1)


BoundlessInformant
(9)


Brazil
(1)


Britain
(1)


Canada
(1)


Classification
(13)


Club de Berne
(1)


Cryptography
(2)


CSEC
(2)


Cyber
(1)


Denmark
(4)


Eikonal
(4)


ELINT
(1)


FBI
(2)


France
(3)


GCHQ
(6)


General Dynamics
(1)


Germany
(21)


Gold Phone
(1)


GSM
(2)


Hotline
(9)


ISAF
(1)


Israel
(2)


IST
(4)


Kremlin
(2)


Main Pages
(4)


Metadata
(6)


Netherlands
(10)


New Zealand
(1)


Non-Snowden-leaks
(5)


North Korea
(2)


NSA
(47)


NSA Partnerships
(25)


Obama
(4)


POTUS
(18)


PRISM
(8)


Red Phone
(6)


Russia
(3)


SatCom
(2)


Section 215
(4)


Sectra
(1)


Secure voice
(8)


Situation Room
(2)


Snowden
(6)


STE
(4)


STU-II
(1)


STU-III
(1)


Switzerland
(2)


Trump
(7)


Ukraine
(1)


UMTS
(2)


US
(2)


USA
(4)


USSR
(2)


Vatican
(1)


VoIP
(1)


White House
(11)


Wireless
(7)


XKeyscore
(2)






"I admire your fine-grained work on this subject and read it religiously. Thanks for all the close analysis over these years." — Barton Gellman




Search This Blog




















Blog Archive








        ► 
      



2024

(1)





        ► 
      



February

(1)









        ► 
      



2023

(8)





        ► 
      



December

(1)







        ► 
      



October

(1)







        ► 
      



September

(1)







        ► 
      



June

(1)







        ► 
      



May

(1)







        ► 
      



April

(1)







        ► 
      



March

(1)







        ► 
      



January

(1)









        ► 
      



2022

(5)





        ► 
      



October

(2)







        ► 
      



September

(1)







        ► 
      



March

(1)







        ► 
      



February

(1)









        ► 
      



2021

(7)





        ► 
      



December

(2)







        ► 
      



November

(1)







        ► 
      



May

(1)







        ► 
      



April

(1)







        ► 
      



March

(1)







        ► 
      



January

(1)









        ► 
      



2020

(12)





        ► 
      



December

(1)







        ► 
      



November

(1)







        ► 
      



October

(1)







        ► 
      



September

(1)







        ► 
      



August

(1)







        ► 
      



July

(1)







        ► 
      



June

(2)







        ► 
      



May

(1)







        ► 
      



March

(1)







        ► 
      



February

(1)







        ► 
      



January

(1)









        ► 
      



2019

(10)





        ► 
      



December

(1)







        ► 
      



November

(2)







        ► 
      



October

(1)







        ► 
      



September

(2)







        ► 
      



June

(1)







        ► 
      



May

(1)







        ► 
      



April

(1)







        ► 
      



March

(1)









        ► 
      



2018

(5)





        ► 
      



November

(1)







        ► 
      



October

(1)







        ► 
      



September

(1)







        ► 
      



July

(1)







        ► 
      



February

(1)









        ► 
      



2017

(12)





        ► 
      



December

(1)







        ► 
      



November

(1)







        ► 
      



October

(1)







        ► 
      



September

(1)







        ► 
      



August

(1)







        ► 
      



July

(1)







        ► 
      



June

(1)







        ► 
      



May

(1)







        ► 
      



April

(1)







        ► 
      



February

(1)







        ► 
      



January

(2)









        ► 
      



2016

(14)





        ► 
      



December

(3)







        ► 
      



November

(1)







        ► 
      



October

(1)







        ► 
      



September

(1)







        ► 
      



August

(1)







        ► 
      



June

(1)







        ► 
      



May

(1)







        ► 
      



March

(2)







        ► 
      



February

(2)







        ► 
      



January

(1)









        ► 
      



2015

(20)





        ► 
      



December

(2)







        ► 
      



November

(2)







        ► 
      



September

(2)







        ► 
      



August

(1)







        ► 
      



July

(1)







        ► 
      



June

(2)







        ► 
      



May

(2)







        ► 
      



April

(2)







        ► 
      



March

(2)







        ► 
      



February

(2)







        ► 
      



January

(2)









        ▼ 
      



2014

(30)





        ► 
      



December

(2)







        ▼ 
      



November

(3)

INCENSER, or how NSA and GCHQ are tapping internet...
German investigation of the cooperation between NS...
The phones of the Dutch Prime Minister








        ► 
      



October

(1)







        ► 
      



September

(3)







        ► 
      



August

(2)







        ► 
      



July

(4)







        ► 
      



June

(2)







        ► 
      



May

(2)







        ► 
      



April

(1)







        ► 
      



March

(3)







        ► 
      



February

(5)







        ► 
      



January

(2)









        ► 
      



2013

(32)





        ► 
      



December

(4)







        ► 
      



November

(3)







        ► 
      



October

(5)







        ► 
      



September

(3)







        ► 
      



August

(3)







        ► 
      



July

(2)







        ► 
      



June

(3)







        ► 
      



May

(1)







        ► 
      



April

(2)







        ► 
      



February

(3)







        ► 
      



January

(3)









        ► 
      



2012

(10)





        ► 
      



December

(1)







        ► 
      



November

(2)







        ► 
      



October

(1)







        ► 
      



June

(2)







        ► 
      



May

(2)







        ► 
      



February

(1)







        ► 
      



January

(1)











"Consistently interesting (and strangely, calming/uplifting) content" — Ryan Lackey




US Red Phones





Sequence of the real Red Phones, not for the Washington-Moscow Hotline, but for the US Defense Red Switch Network (DRSN). The phones shown here were in use from the early eighties up to the present day and most of them were made by Electrospace Systems Inc. They will be discussed on this weblog later.

For the record, you see:
- Electrospace MLP-1
- Electrospace MLP-1A (since 1983)
- Electrospace MLP-2
- Raytheon IST (since 1992)
- Telecore IST-2 (since 2003)




US Classification Levels


Color codes for the classification levels used by the government and the armed forces of the Unites States:





These color codes are used to mark the classification level of (digital) documents and files and also of the communication devices used for their transmission.





Subscribe to this weblog!







Posts










                  Atom
                










Posts












Comments










                  Atom
                










Comments











Hotlinks

- Electrospaces @ Medium.com- The Dutch virtual Crypto Museum- European intelligence: About Intel
- Bruce Schneier on Security- The weblog emptywheel- Weblog of Matthijs R. Koot- Leaked documents: IC Off the record- Der Spiegel's 53 & 36 documents- The Intercept: SIDtoday newsletters
- Parsons' SIGINT Summaries
- The Snowden Archive
- The Investigatory Powers Act 2016 
- Surveillance norms: Safe and Free
- The Canadian Citizenlab- The Cryptome> Many more links



Contact


For questions, suggestions and other remarks about this weblog in general or any related issues, please use the following e-mail address: info (at) electrospaces.net
(we don't accept paid or guests posts)For sending an encrypted e-mail message, you can use the PGP Public Key under this ID: B4515E04 (fingerprint: ECEC FF63 D036 F415 A0BF  A436 661A AC96 B451 5E04)






The header photo of this weblog shows the watch floor of the NSA/CSS Threat Operations Center (NTOC) in 2006. The URL of this weblog recalls Electrospace Systems Inc., the company which made most of the top level communications equipment for the US Government. All information on this weblog is obtained from unclassified or publicly available sources.QW5kIGZpbmFsbHksIHRoaXMgaXMgd2hhdCBhIHRleHQgbG9va3MgbGlrZSwgd2hlbiBpdCdzIG9ubHkgZW5jb2RlZCB3aXRoIHRoZSBzdGFuZGFyZCBCYXNlNjQgc3lzdGVtLiBHdWVzcyBob3cgY29tcGxpY2F0ZWQgaXQgbXVzdCBiZSB3aGVuIGEgcmVhbCBzdHJvbmcgYWxnb3JpdGhtIHdhcyB1c2VkLg==



















































Powered by Blogger.



























