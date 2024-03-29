
Report 1

The 8220 Gang, also known as the 8220 Mining Group, has been active since 2017 and is based in China. They target vulnerable applications in cloud and container environments, focusing on Oracle WebLogic, Apache Log4j, Atlassian Confluence vulnerabilities, and misconfigured Docker containers to deploy cryptocurrency miners on Linux and Windows hosts. The threat actor has been observed using Tsunami malware, XMRIG cryptominer, masscan, and spirit in their campaigns. They have been linked to hacking operations such as the recent use of Custom Miner and Botnet, expanding their cloud botnet to 30,000 infected hosts, and targeting misconfigured cloud workloads. The 8220 Gang's motivation is financial gain, and they continue to evolve with new strategies in each new campaign. Their activities have been documented by various cybersecurity research firms since 2021.





Report 2

Summary:
The threat actor "8220 Gang" has been targeting misconfigured cloud workloads globally, primarily through outdated or misconfigured versions of Docker, Apache, WebLogic, and Log4J services. The gang has expanded its cloud service botnet to an estimated 30,000 hosts and continues to distribute cryptocurrency mining malware. They identify vulnerable hosts through scanning and use SSH brute force attacks for lateral movement. The gang leverages the PureCrypter Malware-as-a-service for loader services and has shifted infrastructure multiple times. They exploit vulnerabilities like CVE-2019-2725 and use Discord URLs for downloading illicit miners. The gang's use of amateur tooling and known scripts indicates a bottom-feeder approach to targeting vulnerable systems. The threat actor's evolving tactics and infrastructure indicate a continuous effort to grow their botnet and evade detection. The report was published on October 13, 2022, by SentinelOne.





Report 3

Summary:
The threat actor group known as "8220 Gang" has been active since 2017 and continues to target vulnerable applications in cloud and container environments. They have been observed targeting Oracle WebLogic, Apache Log4j, Atlassian Confluence vulnerabilities, and misconfigured Docker containers to deploy cryptocurrency miners on Linux and Windows hosts. The group has used tools like Tsunami malware, XMRIG cryptominer, masscan, and spirit in their campaigns. Recently, they exploited the Oracle WebLogic vulnerability CVE-2017-3506 to execute arbitrary commands remotely. The threat actor group has evolved by targeting Windows systems, using new file and C&C servers to evade detection. Despite being described as "low-level script kiddies," the group poses a significant threat, and organizations need to update their security systems to defend against their attacks. Trend Micro solutions like Cloud One™ - Endpoint Security and Workload Security can help protect against such threats.





Report 4

Summary:
The threat actor known as "8220 Gang" has been recently observed using a custom cryptocurrency miner and an IRC bot in a cluster of malicious activities since 2019. The gang has been associated with various campaigns targeting hosts primarily through common cloud services. The custom "PwnRig" miner conceals its configuration details and uses a mining proxy to prevent monitoring of its pool details. The Tsunami IRC bot is also deployed on victim machines. The gang's infrastructure and attribution findings suggest a moderate confidence association with the 8220 Gang, operating since at least 2017. The gang targets vulnerabilities in services like Apache Struts, Redis, Docker, Hadoop, WebLogic, and JBoss. The victims are estimated to range from 1500 to 2000 hosts, with geolocation data showing origins from India, Iran, Brazil, and China. The gang's use of IP filtering and mining proxies for concealment is a novel technique not commonly observed in cryptojacking campaigns. The report provides detailed technical analysis of the gang's tools and techniques, including command line arguments, encryption methods, and infrastructure details. The report also includes indicators of compromise for further investigation. The gang's activities demonstrate a sophisticated and persistent threat to cloud security.





Report 5

The 8220 Gang, a crimeware group, has recently expanded their cloud botnet to 30,000 infected hosts globally through the use of Linux and common cloud application vulnerabilities. The group operates by infecting vulnerable and misconfigured Linux applications and services on cloud networks, targeting victims using SSH brute forcing post-infection for spreading attempts. The group has been observed using a new version of the IRC botnet, PwnRig cryptocurrency miner, and a generic infection script. The 8220 Gang is believed to be a Chinese-speaking threat actor and has been active since 2018, targeting victims globally without geographical discrimination. The group's infection script lacks detection evasion but is highly effective at infecting targets. The group has made recent changes to expand their botnet, with the infection script being updated multiple times a month. The PwnRig miner used by the group has also been updated, with fake pool requests for government domains being a notable feature. The group's tools and techniques are simple yet effective, with the infection script being continuously modified for experimentation. The threat actor's capability is evidenced by the large number of infected hosts and the use of novel techniques such as fake pool requests. The report was published on July 18, 2022.





Report 6

Summary:
- Threat actor: 8220 Gang
- Region: Global, with recent attacks observed in the United States, South Africa, Spain, Columbia, and Mexico
- Operating sector: Targeted healthcare, telecommunications, and financial services
- Type of company: Not specified
- Capability: Utilizes evolving TTPs, targets Windows and Linux web servers with cryptojacking malware, exploits vulnerabilities in Oracle WebLogic Server, and uses custom tools written in Python
- Novelty of tools and techniques: Leveraged CVE-2021-44228, CVE-2017-3506, and CVE-2020-14883 for malware deployment, uses gadget chains to execute commands on OS, and infects hosts with known malware variants
- Date: Activities detected as of Dec 14, 2023
- Imperva Mitigation: Imperva Cloud WAF and on-prem WAF mitigates known vulnerabilities leveraged by the 8220 Gang
- Conclusion: Despite lack of sophistication, enterprises should promptly patch applications and implement security measures to safeguard against such threat actors. Imperva Threat Research continues to monitor activities for security purposes.





Report 7

Summary:
The threat actor known as the "8220 Gang" has been targeting cloud providers, as reported by Radware. The threat actor has demonstrated advanced capabilities in conducting DDoS attacks. The victims of these attacks are companies in the cloud provider sector. The tools and techniques used by the threat actor are considered novel and sophisticated. The report does not specify a specific date or operation time window for the attacks.


