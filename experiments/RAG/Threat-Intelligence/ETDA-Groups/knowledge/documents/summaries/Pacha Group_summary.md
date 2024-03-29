
Report 1

Summary:
The threat actor "Pacha Group" has been targeting Linux servers since September 2018 and has recently expanded its operations to cloud-based environments, specifically competing against the "Rocke Group" in cryptocurrency mining. Pacha Group has implemented advanced evasion and persistence techniques, with low detection rates for its new Linux.GreedyAntd variants. The threat actor has shown efforts to detect and mitigate Rocke Group's implants, using a blacklist of miners and disabling cloud protection solutions. Pacha Group's infrastructure includes a user-mode rootkit and IP blacklisting techniques to disrupt routing processes. The threat actor's aggressive behavior towards Rocke Group in cloud environments indicates a growing trend of targeting cloud-native threats. The report provides IOCs and a YARA rule for detection, emphasizing the need for increased awareness and mitigation strategies against Linux-based malware targeting cloud infrastructure. The report was published on May 9, 2019, by Ignacio Sanmillan from Intezer.





Report 2

Summary:
Intezer has identified a new threat actor named Pacha Group, originating from China, deploying undetected cryptojacking campaigns on Linux servers since September 2018. The malware used by Pacha Group, Linux.GreedyAntd, showcases advanced evasion techniques uncommon in Linux threats, such as altering timestamps to avoid detection. This threat actor aggressively eliminates other miners on compromised servers to maximize profits. Pacha Group's operations involve compromising third-party servers to expand their infrastructure. The sophistication and novelty of the tools and techniques used by Pacha Group highlight their capability to evade detection and operate stealthily. The report was published on 28th February 2019 by Intezer.





Report 3

Summary:
The threat actor known as Pacha Group has been identified deploying undetected cryptojacking campaigns on Linux servers, with a focus on compromising third-party servers. The group utilizes unconventional techniques and shows sophistication in their operations, with evidence suggesting Chinese origin. The malware, labeled as Linux.GreedyAntd, includes a multi-stage architecture with persistence mechanisms and a XMRig variant miner client. Additionally, connections were found between Pacha Group's operations and the Chinese bot Linux.HelloBot. The threat actor's infrastructure is designed to evade detection and analysis, making it challenging to identify and mitigate their activities. The report was published on February 28, 2019, by Ignacio Sanmillan from Intezer. The victims targeted by Pacha Group are primarily Linux servers in various sectors, showcasing the threat actor's capability and novel use of tools and techniques.





Report 4

The threat actor Pacha Group, believed to be of Chinese origin, was first seen in 2018 and has been actively delivering newer campaigns deploying undetected components on compromised third-party Linux servers. The group's techniques are unconventional and sophisticated, with evidence of using tools such as Antd, DDG, Korkerds, and XMRig for financial gain through cryptomining operations. The Pacha Group has been observed targeting victims in various sectors and countries. Intezer has evidence of Pacha Group's cryptomining malware dating back to September 2018, and they have been competing against other threat actors for cryptocurrency mining foothold on the cloud. The group's use of novel tools and techniques sets them apart in the threat landscape.


