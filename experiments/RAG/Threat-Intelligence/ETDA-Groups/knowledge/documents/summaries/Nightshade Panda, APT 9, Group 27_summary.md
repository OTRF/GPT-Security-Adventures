
Report 1

Nightshade Panda, also known as APT 9 or Group 27, targeted the U.S. government and a European media company in May 2015 using the '3102' malware variant of the '9002' Trojan. The threat actors utilized spear-phishing emails to deliver a weaponized Excel document exploiting CVE-2012-0158 to install the malware. The '3102' payload heavily relies on plugins for functionality and shares similarities with the Evilgrab payload used in a watering hole attack in Myanmar. The threat actor's C2 infrastructure was linked to individuals in China active in online hacking forums. The malware communicated with its C2 server using a custom protocol and HTTP POST requests. The '3102' Trojan is modular and requires external plugins for capabilities, which were loaded in various ways during the attacks. The threat actor behind these attacks is likely Chinese-based and shows a lack of operational security in their coding practices. The use of a common digital certificate and infrastructure suggests a common threat group behind the attacks. The malware used in the attacks was classified as malicious by WildFire, and users of Palo Alto Networks Traps were protected from the exploitation. The threat actor's ties to the Chinese hacking community indicate a contractor-based operation. The report was published on September 23, 2015, by Unit 42 from Palo Alto Networks.





Report 2

Nightshade Panda, also known as APT 9 or Group 27, has been active since 2013, with the latest evidence of their activities reported in 2020. The threat actor has been linked to a new Remote Access Trojan (RAT) called Trochilus, which was part of their malware portfolio known as the Seven Pointed Dagger. This collection of malware included various RAT versions and other malicious tools used for information theft and espionage.

Nightshade Panda has targeted victims in sectors such as Energy, Government, Media, and Utilities, operating in countries like Myanmar, Thailand, USA, and Europe. The threat actor has been observed using a variety of tools, including PlugX, Poison Ivy, and Trochilus RAT, in their hacking operations. Notably, in 2015, they conducted Operation "Seven Pointed Dagger," using watering hole attacks on official Myanmar government websites to distribute malware.

The threat actor's capability to develop new and undetectable malware, as well as their use of sophisticated techniques like hosting malware on legitimate websites, demonstrates their advanced tactics. Counter operations against Nightshade Panda have been reported, but the threat actor continues to pose a significant risk to organizations targeted for cyber espionage.





Report 3

Summary:
- Threat actor group used Trochilus RAT and MoonWind RAT to target organizations in Thailand, including a utility organization, from September 2016 to late November 2016.
- MoonWind RAT was newly identified and named based on debugging strings and compiler used.
- Attackers compromised legitimate Thai websites to host the malware.
- MoonWind RAT compiled with a Chinese compiler known as BlackMoon, different from BlackMoon banking Trojan.
- MoonWind RAT had keylogging functionality, remote hosts for communication, and encrypted data communication.
- Trochilus and MoonWind RATs were stored on compromised websites, with MoonWind samples stored as RAR files in September and executables in November.
- MoonWind had 73 possible commands, including keylogging, file manipulation, and network communication.
- Threat actor group responsible for Trochilus and MoonWind RATs has ties to targeted Southeast Asia activity since 2013.
- Palo Alto Networks customers are protected from this threat.
- Date of report: March 30, 2017.


