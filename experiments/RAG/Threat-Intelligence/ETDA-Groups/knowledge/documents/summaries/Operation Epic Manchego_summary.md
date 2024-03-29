
Report 1

Summary:
The threat actor behind "Operation Epic Manchego" was detected by NVISO Labs in July 2020 targeting victims with malicious Excel documents delivering malware through VBA-activated spreadsheets. The threat actor used a unique technique to create macro-laden Excel workbooks without using Microsoft Office, resulting in lower detection rates. The campaign is assessed to be delivered by a single threat actor focusing on infostealers to harvest passwords. The threat actor's capability is evidenced by the evolution of payloads and obfuscation techniques. The tools and techniques used, such as EPPlus library for creating malicious documents, show novelty in the threat actor's approach. The operation targeted victims in various sectors, including medical equipment, aluminum, facility management, and custom press machines vendors. The threat actor primarily used legitimate corporate email accounts for phishing campaigns. The geographical distribution of targeted regions included the United States, Czech Republic, France, Germany, and China. The threat actor's constant evolution and experimentation with new methods indicate a potential escalation of operations. NVISO recommends filtering email attachments, implementing endpoint detection and response defenses, and conducting phishing awareness training. The YARA rule provided can help in detecting similar malicious documents. The report provides indicators of compromise and MITRE ATT&CK mapping for further analysis. The threat actor's capability and use of novel techniques make them a significant concern in the cybersecurity landscape.





Report 2

Summary:
Operation Epic Manchego, also known as NVISO, was first detected in July 2020 targeting victims in various countries including Bulgaria, Canada, China, and the USA. The threat actor used malicious Excel documents to deliver malware through VBA-activated spreadsheets, with a unique technique that lowered detection rates. The motivation behind the attacks was information theft and espionage. The threat actor utilized tools such as Agent Tesla, AZORult, and Formbook. The novelty of the tools and techniques used by Operation Epic Manchego lies in the specific way in which the Excel documents were created without using Microsoft Office. The threat actor's capabilities and widespread targeting across multiple sectors and countries indicate a sophisticated and persistent threat. (Malformed report)


