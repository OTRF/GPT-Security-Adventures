
Report 1

Summary:
The threat actor "ChChes" targeted organizations in Japan's domestic sector with targeted emails containing ZIP files with malicious executables disguised as Word documents. The malware communicates with a C&C server using HTTP to receive commands and modules, expanding its functionality. ChChes uses a unique method of communication using Cookie headers for encryption. The malware is capable of executing shell commands, uploading and downloading files, loading DLLs, and listing bot commands. ChChes employs AES encryption for communication, making it a relatively new and sophisticated malware discovered around October 2016. JPCERT/CC continues to monitor ChChes and its potential use in targeted attacks. The report includes details on the malware's communication methods, capabilities, and indicators of compromise. (Date: 2017-01-26)





Report 2

Snake Wine is a threat actor group first seen in 2016, with a focus on targeting Japanese companies and individuals in the education, government, and commerce sectors. The group, also known as Cylance, has shown adaptability in adopting new tactics to infiltrate victim environments. Their motivation is information theft and espionage, with observed tools including ChChes and Tofu Backdoor. The group's operations have been linked to China, and their attack infrastructure suggests a continued interest in Japanese targets. The novelty of their techniques and tools sets them apart from other threat actors. (Report last modified on 2020-04-15)





Report 3

The threat actor known as 'Snake Wine' has been identified as a Japanese-centric group targeting Japanese companies and individuals since August 2016. The group uses spear phishing attacks with well-crafted LNK files containing PowerShell commands to download and execute payloads. The malware used, such as 'The Ham Backdoor' and 'Tofu Backdoor', shows advanced capabilities in modular platform functions and communication with C2 servers. The threat actor employs obfuscation techniques and novel methods like using stolen code-signing certificates to evade detection. The group's infrastructure includes dark or unused domains and Dynamic DNS domains mimicking legitimate sites. The Snake Wine group has shown adaptability and interest in Japanese government, education, and commerce sectors. The attribution of the group is obscured through various tactics, including IP crossover with known CN-APT groups. The threat actor's tactics continue to evolve, posing a challenge for defenders. The report provides Yara rules for detection and emphasizes the importance of proactive defense against emerging threats. Date: August 2016 - Present.


