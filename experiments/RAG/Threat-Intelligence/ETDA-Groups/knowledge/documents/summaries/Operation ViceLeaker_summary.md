
Report 1

Summary:
Operation ViceLeaker, first seen in 2018, targeted dozens of mobile Android devices belonging to Israeli citizens. The spyware program exfiltrated accessible information, with Kaspersky and Bitdefender researchers uncovering the operation. The threat actor's capability was evidenced by the original spyware program embedded in the APK. The operation's novelty was highlighted by the use of unique tools and techniques, prompting Kaspersky to release a private report and develop YARA rules to detect more samples. The threat actor's motivation was information theft and espionage, with victims operating in the citizen sector in Israel. The threat actor's country of origin remains unknown. 

##################





Report 2

Summary:
The threat actor behind "Operation ViceLeaker" targeted mobile espionage in the Middle East, specifically focusing on Android devices belonging to Israeli citizens. The operation involved the use of original spyware programs designed to exfiltrate various types of information. The threat actor utilized Smali injection techniques to backdoor legitimate applications, allowing for commands such as exfiltrating SMS messages, call logs, and other data, as well as taking over the camera and recording audio. The malware communicated with a command and control server using HTTP and handled 16 different commands. The operation began in 2018, with the main infection vector being the spread of Trojanized applications via Telegram and WhatsApp messengers. Additionally, the threat actor modified open-source applications like Conversations for potential internal communication purposes. The operation is ongoing, and Kaspersky detects and blocks samples using the verdict Trojan-Spy.AndroidOS.ViceLeaker. The threat actor's wider capabilities and objectives are being investigated, including a potential large-scale web-oriented attack in 2018. The threat actor's C2 server infrastructure and attribution clues are being analyzed for further insights.


