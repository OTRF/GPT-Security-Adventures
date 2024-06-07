
Report 1

Summary:
The threat actor PKPLUG, also known as Palo Alto, has been active since 2016, with the latest source modification in August 2021. Operating from China, PKPLUG has targeted government and healthcare sectors in countries such as China, Indonesia, Mongolia, Myanmar, Taiwan, Tibet, and Vietnam. Their motivation is information theft and espionage. PKPLUG is known for using a mix of publicly available and custom malware, including tools like 9002 RAT, Farseer, HenBox, PlugX, Poison Ivy, THOR, and Zupdax. One of their notable operations in 2021 involved deploying a previously unseen PlugX variant during Microsoft Exchange Server attacks. The threat actor's capability lies in their use of novel tools and techniques, such as delivering PlugX malware inside ZIP archive files.





Report 2

Summary:
The threat actor known as PKPLUG, a Chinese cyber espionage group, has been active for at least six years targeting victims mainly in Southeast Asia, particularly in countries like Myanmar, Taiwan, Vietnam, and Indonesia. The group uses a mix of publicly available and custom malware, including PlugX, HenBox, Farseer, and the 9002 Trojan. PKPLUG's ultimate objectives are not entirely clear, but they focus on installing backdoor Trojan implants on victim systems, including mobile devices, to track victims and gather information. The threat actor's use of novel techniques like DLL side-loading and social engineering, as well as the targeting of regions involved in the Belt and Road Initiative and South China Sea disputes, demonstrate their advanced capabilities and strategic objectives. The threat actor's activities have been tracked and documented by Unit 42, with indicators of compromise shared with the Cyber Threat Alliance for protection of customers.





Report 3

Summary:
The threat actor PKPLUG, also known as Mustang Panda, deployed a previously unseen PlugX variant named THOR during Microsoft Exchange Server attacks in March 2021. This variant contained changes to its core source code, replacing "PLUG" with "THOR." The earliest THOR sample was from August 2019, showing new features like enhanced payload delivery mechanisms and abuse of trusted binaries. PlugX, discovered in 2008, is a second-stage implant used by Chinese cyberespionage groups. The PKPLUG group has been involved in high-profile attacks, including the U.S. Government Office of Personnel Management breach in 2015. The variant used techniques like DLL side loading and communicated with C2 servers over HTTP. Palo Alto Networks customers are protected from PlugX with specific security subscriptions. The report provides indicators of compromise and a tool developed by Unit 42 to handle payload decryption. The report also highlights overlaps between PKPLUG infrastructure and the new THOR variant. The report concludes that PlugX remains a persistent threat, and Unit 42 will continue to monitor for new samples and variants associated with this threat actor.


