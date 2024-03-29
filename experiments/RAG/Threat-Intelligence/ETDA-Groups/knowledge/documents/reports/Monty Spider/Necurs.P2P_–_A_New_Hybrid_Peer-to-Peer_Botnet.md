# Reference for threat actor for "Monty Spider"

**Title**: Necurs.P2P – A New Hybrid Peer-to-Peer Botnet

**Source**: https://www.malwaretech.com/2016/02/necursp2p-hybrid-peer-to-peer-necurs.html

## Content












Necurs.P2P – A New Hybrid Peer-to-Peer Botnet


























































































Search for Blog






















Menu



Home

Speaking
Discord
About Me
Contact











Home

Speaking
Discord
About Me
Contact





















Feb 22, 2016


Malware Analysis
Threat Intelligence


Necurs.P2P &#8211; A New Hybrid Peer-to-Peer Botnet



Marcus Hutchins




Last week I received a tip about a sample displaying some indication that it could be peer-to-peer (a large amount of UDP traffic being sent to residential IPs), after a couple days of analysis I was able to confirm that not only was it peer-to-peer but also currently active. The person who tipped me off was friend and researcher R136a1 who seems to be on a roll lately (not only did he find this, but was also the one who found ZeroAccess3 as well as the identities of the authors), you should definitely follow him if you haven’t already.After a bit of searching I was able to find a SANS blog post from May 2015 about a Necurs sample with similarities to ours; however, there was no mention of what the UDP traffic was for. I was also able to find a much older post by blue coat from September 2013 which detailed a Necurs variant using .bit (Namecoin) domains for the C&C. I’m not 100% certain, but I believe this to be a variant of the original Necurs, that is, before the rootkit was sold to groups like the one behind Zeus GameOver.
Installation Process
Upon install…

…nevermind.
After a quick check we can see that the cause of the BSOD is anti-virtualization code embedded with the malware, though the way it’s caused is strange. Upon detection of a virtual environment, the malware begins injecting all processes with a simple routine which sets up an exception handler and executes the VMCPUID. What’s interesting is the VMCPUID instruction is only implemented on some virtual machines and will return the VM’s CPUID, if unimplemented it will generate an invalid instruction exception which will need to be caught by an exception handler. When the function is injected into every process it is unable to set up a correct exception handler because the exception context is stored in the .rdata section of the bot’s process and isn’t copied along with the function; as a result, if the system is detected as a VM but doesn’t implement VMCPUID every process will crash and the system will BSOD. My guess is the coders were trying to implement some kind of injectable VM check but it kept crashing the VM, so they just left it as an obscure anti-virtualization measure (though it shouldn’t crash any VMs that implement the VMCPUID instruction).
Upon successful execution the bot elevates itself using CVE-2010-4398 then copies it’s executable to C:Installers{BotGUID}syshost.exe and driver to C:Drivers{RandomName}.sys. The executable is set as an auto-start service and the driver is set as a boot device (if required, the bot will enable TESTSIGNING mode to allow loading of unsigned drivers), afterwards the system is rebooted.
After reboot the bot will attempt to use the netsh.exe to whitelist it’s own process in the firewall (on Windows XP it will just disable the firewall completely).
|  |
|—|
| Attempting to whitelist itself using netsh.exe |
Peer-to-Peer Communication
This C&C structure is something referred to as “hybrid P2P” because commands are sent from centralized C&C servers just like in a regular botnet; however, because new C&C server addresses can be pushed to all bots via the peer-to-peer network at any time, the botnet maintains the usability of a traditional botnet, but with the resilience of a peer-to-peer one.In order to enable P2P communication a random port number is generated and stored into the registry; this port is then bound on both the UDP and TCP protocol allowing P2P communication to work over either, though udp is the most dominant. The bot has over 1000 IP and port combinations stored within the initial config which will be contacted one by one at a rate of one per second until a reply is received, after that the rate is adjusted to one per minute. Strangely before every request a random number from 0 to 4 is chosen: if the number is 0 the bot will attempt to connect to the remote host over TCP, otherwise it will fire off a UDP packet, resulting in a UDP:TCP ratio of around 4:1 (I’m unsure as to what the purpose of this is).
|  |
|—|
| P2P protocol handling routine |
All peers reply to requests with a payload signed by the botmaster’s 2048-bit RSA key (preventing anyone other than them from introducing new response payloads).
P2P payloads can contain any or all of 3 block types:

DNS Block – A list of Namecoin DNS servers which will allow the bot to use Namecoin’s .bit domains to resolve C&C servers.
C&C Block – A list of C&C server IPs.
Update Block – Allows updates to be sent over the P2P network (likely only used in the case that all other C&C methods are offline).

Notably there is no peer exchange functionality in the P2P protocol, which is because instead of trusting peers to share peer information among themselves, the botmasters have opted to generate peer lists themselves and publish them via the C&C server. By distributing peers this way it is easier to prevent poisoning attacks as the list can be checked for IPs belonging to datacenters or security companies which would likely harm the botnet. The main drawback of this specific implementation is the botmasters send out a huge peer list with ~2000 IPs to replace the previous one each time, so rather than keeping track of online IPs the bots just iterate the peer list until they find an online peer, which generates a lot of failed connections and is a good indicator of infection. If the bot is unable to connect to any peers within 5 minutes of booting up, it begins the DGA routine and starts spamming DNS requests (in my tests it took at least 15 minutes to successfully connect to a peer, so DGA always began execution).
Payloads Storage
Anything downloaded from the C&C or P2P network gets stored in the temp folder with a UUID for the file name and .tmp for the extension; the UUID is generated by SHA1 hashing the bot identifier with a static 64-bit integer (used to identify the content of the file).
|  |
|—|
| File name generator |
Files are encrypted with RC4 using a key derived with the same function as above, except a randomly generated variables is hashed alongside the data and then stored at the end of the file, making generating file signatures impossible.



Share this article



LinkedIn


Facebook






Show Comments




Please enable JavaScript to view the
  comments powered by Disqus.





Stay Informed




Subscribe to my newsletter to get notified of new posts.



Email address

Subscribe











Marcus Hutchins
Threat intelligence analyst, programmer, ex-hacker.

















































Featured Posts





Feb 13, 2024

Bypassing EDRs With EDR-Preloading






Dec 27, 2023

Silly EDR Bypasses and Where To Find Them






Dec 25, 2023

An Introduction to Bypassing User Mode EDR Hooks






Sep 20, 2023

It might Be Time to Rethink Phishing Awareness






Feb 21, 2023

A Realistic Look at Implications of ChatGPT for Cybercrime






Dec 31, 2020

How I Found My First Ever ZeroDay (In RDP)






Mar 19, 2018

Best Languages to Learn for Malware Analysis






May 13, 2017

How to Accidentally Stop a Global Cyber Attacks






Apr 13, 2015

Hard Disk Firmware Hacking (Part 1)





Explore Topics


Explainers14
Malware15
Windows Internals9
Hacking11
Vulnerability Research10
News10
Analysis9
Malware Analysis16
Programming4
Threat Intelligence13
Opinions10
Stories3
WannaCry2
Videos3








You may also like








Jan 9, 2019

Malware Analysis
Threat Intelligence



Tracking the Hide and Seek Botnet














Mar 19, 2018

Malware Analysis
Opinions



Best Languages to Learn for Malware Analysis













Nov 13, 2017

Threat Intelligence



Investigating Command and Control Infrastructure (Emotet)


















Menu



Home

Speaking
Discord
About Me
Contact






Recent Posts





Feb 13, 2024

Bypassing EDRs With EDR-Preloading






Dec 27, 2023

Silly EDR Bypasses and Where To Find Them







Stay Informed

Subscribe to my newsletter to get notified of new posts.



Email address

Subscribe







2024 © MalwareTech




























































