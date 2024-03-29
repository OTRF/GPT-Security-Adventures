
Report 1

Summary:
In March 2023, a previously unknown APT campaign named CloudWizard was uncovered in the region of the Russo-Ukrainian conflict, targeting victims in Donetsk, Lugansk, Crimea, central, and western Ukraine. The threat actor behind this campaign used a modular framework that included features like taking screenshots, microphone recording, and keylogging. The campaign involved sophisticated malicious activities and targeted individuals, diplomatic, and research organizations. The CloudWizard framework had a rich history dating back to 2008 and showed similarities with previously known APT campaigns like Prikormka and Operation Groundbait. The threat actor behind CloudWizard continued to develop their cyberespionage toolset for over 15 years. The campaign utilized novel techniques and tools, including faulty RC5 encryption implementation and a modular framework for malicious activities. The threat actor's capability and persistence were evident in the campaign's targeting and operational history. The report provides indicators of compromise for detection and mitigation.





Report 2

Summary:
The threat actor known as Bad Magic, RedStinger, or CloudWizard has been active since at least 2020, targeting government, agriculture, and transportation organizations in the Donetsk, Lugansk, and Crimea regions of Ukraine. The initial compromise vector appears to involve spear phishing or similar methods, leading victims to a malicious ZIP archive hosted on a web server. The threat actor's motivation is information theft and espionage. They have been observed using tools like CommonMagic and PowerMagic. The novelty of their techniques and tools has been documented in reports dating back to 2020, with ongoing operations reported as recently as May 2023. The threat actor's country of origin remains unknown.





Report 3

Summary:
- Threat actor "Bad Magic, RedStinger" targeted administrative organizations in the Russo-Ukrainian conflict area, specifically in Donetsk, Lugansk, and Crimea regions.
- The attack involved spear phishing tactics, with victims being directed to a malicious ZIP archive containing a decoy document and a malicious LNK file.
- The LNK file triggered the infection chain, leading to the deployment of the CommonMagic framework and the PowerMagic backdoor.
- CommonMagic is a modular framework with various executable modules stored in the directory C:\ProgramData\CommonCommand, communicating via named pipes.
- PowerMagic is a PowerShell backdoor that creates a mutex, communicates with a C&C server, and uses OneDrive and Dropbox for transport.
- The threat actor behind this campaign remains unidentified, with no direct links to known actors, and the investigation is ongoing.
- The tools and techniques used by the threat actor are novel and effective, with no direct relation to any known campaigns.
- The campaign was active as of October 2022, and further discoveries may reveal additional information about the threat actor and malware used.





Report 4

Summary:
The threat actor known as RedStinger, operating in Eastern Europe since 2020, has conducted APT cyber operations targeting entities in Ukraine, including military, transportation, critical infrastructure, and those involved in the East Ukraine referendums. The group remained undetected for at least three years and used distinctive tactics, techniques, and procedures (TTPs). They utilized novel tools and techniques such as DBoxShell, SolarTools, and vs_secpack.msi for exfiltration. The group targeted both Ukraine-aligned and Russia-aligned entities, with a focus on surveillance and data gathering. The victims included military targets, officers in critical infrastructure, and individuals involved in elections. The threat actor's operations involved reconnaissance, exfiltration, and testing on their own machines. The attribution of the attack to a specific country remains challenging. The report provides indicators of compromise for various operations conducted by RedStinger. The investigation started in September 2022 and revealed detailed insights into the group's activities and victimology.


