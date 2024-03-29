
Report 1

Summary: The report details a malspam campaign that was highly personalized and made extensive use of hijacked domains. The spam emails contained personal information of the intended victims, including names, addresses, and phone numbers. The campaign utilized a series of hijacked domains to deliver the final payload, which was a .lnk file with a PowerShell command embedded in it. The spam emails originated from a mail server in Romania, and the domains used in the campaign were identified as being hijacked. The report highlights the use of valid SPF records to enhance the deliverability of the spam emails. The threat actor behind the campaign demonstrated the capability to harvest personal information and use it in a targeted malspam operation. The report was published on February 15, 2017, and provides insights into the novel techniques and tactics employed by the threat actor. The victims targeted by the campaign were not explicitly mentioned in the report.





Report 2

Summary:
The threat actor "TA554" targeted UK bank customers using a PowerShell script uploaded on VirusTotal on May 16, 2018. The script had the capability to take screenshots and exfiltrate data via HTTP requests. It created directories based on system UUID, probed URLs for payload downloads using BitsAdmin, and waited for completion. The script also gathered information on processes, network shares, and DNS resolver cache, focusing on UK bank domains. It communicated with a C2 server via HTTP requests and uploaded screenshots. The script operated in a loop with a sleep time of 600 seconds. The threat actor's novel use of PowerShell for exfiltration and reconnaissance poses a significant risk to the banking sector in the UK.





Report 3

TA554, also known as TH-163, is a threat actor primarily focused on financial crime. Since at least 2017, they have been observed using a new downloader called sLoad, which delivers Ramnit banker malware and includes reconnaissance features such as taking screenshots and checking DNS cache for specific domains. The campaigns by TA554 have targeted victims in the financial sector in Canada, Italy, and the UK. The threat actor has also been associated with the usage of various tools including DarkVNC, Godzilla, Gootkit, and Gozi ISFB. The novelty of sLoad and the actor's capability to conduct targeted attacks indicate a sophisticated level of operation. The last known modification of the source was on April 29, 2020.





Report 4

Summary:
The threat actor TA554 has been conducting sustained campaigns targeting victims in the UK, Italy, and Canada since at least 2017. The actor uses a downloader called sLoad, which delivers the Ramnit banker malware and includes reconnaissance features such as checking for running processes, Outlook presence, and Citrix-related files. The actor personalizes email messages with recipients' names and addresses, often using package delivery or order notification lures. Geofencing is employed at multiple points in the infection chain to target specific regions. sLoad communicates with its command and control server, takes screenshots, and checks the DNS cache for specific domains. The threat actor has been observed using various payloads including Ramnit, Gootkit, DarkVNC, Ursnif, and PsiXBot. The latest TTP observed on October 22, 2018, involved a victim-facing landing page for direct sLoad download. The actor's capabilities and use of novel techniques highlight the evolving nature of cyber threats.


