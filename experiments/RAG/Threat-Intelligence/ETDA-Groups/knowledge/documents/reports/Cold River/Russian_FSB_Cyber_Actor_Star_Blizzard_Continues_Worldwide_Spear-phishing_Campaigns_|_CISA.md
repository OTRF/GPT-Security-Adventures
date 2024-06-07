# Reference for threat actor for "Cold River"

**Title**: Russian FSB Cyber Actor Star Blizzard Continues Worldwide Spear-phishing Campaigns | CISA

**Source**: https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-341a

## Content















Russian FSB Cyber Actor Star Blizzard Continues Worldwide Spear-phishing Campaigns | CISA





































Skip to main content





 





An official website of the United States government
Here’s how you know

Here’s how you know









Official websites use .gov
 A .gov website belongs to an official government organization in the United States.
              






Secure .gov websites use HTTPS
 A lock (LockA locked padlock) or https:// means you’ve safely connected to the .gov website. Share sensitive information only on official, secure websites.
              













Cybersecurity & Infrastructure Security Agency
 America's Cyber Defense Agency



Search



 


Menu






Close


 




Topics



Topics





Cybersecurity Best Practices






Cyber Threats and Advisories






Critical Infrastructure Security and Resilience






Election Security






Emergency Communications






Industrial Control Systems






Information and Communications Technology Supply Chain Security






Partnerships and Collaboration






Physical Security






Risk Management






        How can we help?
       
GovernmentEducational InstitutionsIndustryState, Local, Tribal, and TerritorialIndividuals and FamiliesSmall and Medium BusinessesFind Help LocallyFaith-Based CommunityExecutives





Spotlight




Resources & Tools



Resources & Tools





All Resources & Tools






Services






Programs






Resources






Training






Groups








News & Events



News & Events





News






Events






Cybersecurity Alerts & Advisories






Directives






Request a CISA Speaker






Congressional Testimony








Careers



Careers





Benefits & Perks






HireVue Applicant Reasonable Accommodations Process






Hiring






Resume & Application Tips






Students & Recent Graduates






Veteran and Military Spouses






Work @ CISA








About



About





Culture






Divisions & Offices






Regions






Leadership






Doing Business with CISA






Site Links






Reporting Employee and Contractor Misconduct






CISA GitHub






2023 Year In Review






Contact Us 







Report a Cyber Issue





America's Cyber Defense Agency






Breadcrumb


Home


News & Events


Cybersecurity Advisories


Cybersecurity Advisory







Share:





































Cybersecurity Advisory

Russian FSB Cyber Actor Star Blizzard Continues Worldwide Spear-phishing Campaigns



Release DateDecember 07, 2023

Alert CodeAA23-341A


 Related topics: 

Nation-State Cyber Actors,                                                                                 Cyber Threats and Advisories,                                                                                 Malware, Phishing, and Ransomware 











The Russia-based actor is targeting organizations and individuals in the UK and other geographical areas of interest.
OVERVIEW
The Russia-based actor Star Blizzard (formerly known as SEABORGIUM, also known as Callisto Group/TA446/COLDRIVER/TAG-53/BlueCharlie) continues to successfully use spear-phishing attacks against targeted organizations and individuals in the UK, and other geographical areas of interest, for information-gathering activity.
The UK National Cyber Security Centre (NCSC), the US Cybersecurity and Infrastructure Security Agency (CISA), the US Federal Bureau of Investigation (FBI), the US National Security Agency (NSA), the US Cyber National Mission Force (CNMF), the Australian Signals Directorate’s Australian Cyber Security Centre (ASD’s ACSC), the Canadian Centre for Cyber Security (CCCS), and the New Zealand National Cyber Security Centre (NCSC-NZ) assess that Star Blizzard is almost certainly subordinate to the Russian Federal Security Service (FSB) Centre 18.
Industry has previously published details of Star Blizzard. This advisory draws on that body of information.
This advisory raises awareness of the spear-phishing techniques Star Blizzard uses to target individuals and organizations. This activity is continuing through 2023.
To download a PDF version of this advisory, see Russian FSB Cyber Actor Star Blizzard Continues Worldwide Spear-phishing Campaigns.
TARGETING PROFILE
Since 2019, Star Blizzard has targeted sectors including academia, defense, governmental organizations, NGOs, think tanks and politicians.
Targets in the UK and US appear to have been most affected by Star Blizzard activity, however activity has also been observed against targets in other NATO countries, and countries neighboring Russia.
During 2022, Star Blizzard activity appeared to expand further, to include defense-industrial targets, as well as US Department of Energy facilities.
OUTLINE OF THE ATTACKS
The activity is typical of spear-phishing campaigns, where an actor targets a specific individual or group using information known to be of interest to the targets. In a spear-phishing campaign, an actor perceives their target to have direct access to information of interest, be an access vector to another target, or both.
Research and Preparation
Using open-source resources to conduct reconnaissance, including social media and professional networking platforms, Star Blizzard identifies hooks to engage their target. They take the time to research their interests and identify their real-world social or professional contacts [T1589], [T1593].
Star Blizzard creates email accounts impersonating known contacts of their targets to help appear legitimate. They also create fake social media or networking profiles that impersonate respected experts [T1585.001] and have used supposed conference or event invitations as lures.
Star Blizzard uses webmail addresses from different providers, including Outlook, Gmail, Yahoo and Proton mail in their initial approach [T1585.002], impersonating known contacts of the target or well-known names in the target’s field of interest or sector.
To appear authentic, the actor also creates malicious domains resembling legitimate organizations [T1583.001].
Microsoft Threat Intelligence Center (MSTIC) provides a list of observed Indicators of Compromise (IOCs) in their SEABORGIUM blog, but this is not exhaustive.
Preference for Personal Email Addresses
Star Blizzard has predominantly sent spear-phishing emails to targets’ personal email addresses, although they have also used targets’ corporate or business email addresses. The actors may intentionally use personal emails to circumvent security controls in place on corporate networks.
Building a Rapport
Having taken the time to research their targets’ interests and contacts to create a believable approach, Star Blizzard now starts to build trust. They often begin by establishing benign contact on a topic they hope will engage their targets. There is often some correspondence between attacker and target, sometimes over an extended period, as the attacker builds rapport.
Delivery of Malicious Link
Once trust is established, the attacker uses typical phishing tradecraft and shares a link [T1566.002], apparently to a document or website of interest. This leads the target to an actor-controlled server, prompting the target to enter account credentials.
The malicious link may be a URL in an email message, or the actor may embed a link in a document [T1566.001] on OneDrive, Google Drive, or other file-sharing platforms.
Star Blizzard uses the open-source framework EvilGinx in their spear- phishing activity, which allows them to harvest credentials and session cookies to successfully bypass the use of two-factor authentication [T1539], [T1550.004].
Exploitation and Further Activity
Whichever delivery method is used, once the target clicks on the malicious URL, they are directed to an actor-controlled server that mirrors the sign-in page for a legitimate service. Any credentials entered at this point are now compromised.
Star Blizzard then uses the stolen credentials to log in to a target’s email account [T1078], where they are known to access and steal emails and attachments from the victim’s inbox [T1114.002]. They have also set up mail- forwarding rules, giving them ongoing visibility of victim correspondence [T1114.003].
The actor has also used their access to a victim email account to access mailing-list data and a victim’s contacts list, which they then use for follow- on targeting. They have also used compromised email accounts for further phishing activity [T1586.002].
CONCLUSION
Spear-phishing is an established technique used by many actors, and Star Blizzard uses it successfully, evolving the technique to maintain their success.
Individuals and organizations from previously targeted sectors should be vigilant of the techniques described in this advisory.
In the UK you can report related suspicious activity to the NCSC.
Information on effective defense against spear-phishing is included in the Mitigations section below.
MITRE ATT&CK®
This report has been compiled with respect to the MITRE ATT&CK® framework, a globally accessible knowledge base of adversary tactics and techniques based on real-world observations.

Tactic


ID


Technique


Procedure


Reconnaissance


T1593


Search Open Websites/Domains


Star Blizzard uses open-source research and social media to identify information about victims to use in targeting.


Reconnaissance


T1589


Gather Victim Identity Information


Star Blizzard uses online data sets and open-source resources to gather information about their targets.


Resource Development


T1585.001


Establish Accounts: Social Media Accounts


Star Blizzard has been observed establishing fraudulent profiles on professional networking sites to conduct reconnaissance.


Resource Development


T1585.002


Establish Accounts: Email Accounts


Star Blizzard registers consumer email accounts matching the names of individuals they are impersonating to conduct spear-phishing activity.


Resource Development


T1583.001


Acquire Infrastructure: Domains


Star Blizzard registers domains to host their phishing framework.


Resource Development


T1586.002


Compromise Accounts: Email Accounts


Star Blizzard has been observed using compromised victim email accounts to conduct spear-phishing activity against contacts of the original victim.


Initial Access


T1078


Valid Accounts


Star Blizzard uses compromised credentials, captured from fake log- in pages, to log in to valid victim user accounts.


Initial Access


T1566.001


Phishing: Spear-phishing Attachment


Star Blizzard uses malicious links embedded in email attachments to direct victims to their credential-stealing sites.


Initial Access


T1566.002


Phishing: Spear-phishing Link


Star Blizzard sends spear-phishing emails with malicious links directly to credential-stealing sites, or to documents hosted on a file-sharing site, which then direct victims to credential-stealing sites.


Defense Evasion


T1550.004


Use Alternate Authentication Material: Web Session Cookie


Star Blizzard bypasses multi-factor authentication on victim email accounts by using session cookies stolen using EvilGinx.


Credential Access


T1539


Steal Web Session Cookie


Star Blizzard uses EvilGinx to steal the session cookies of victims directed to their fake log-in domains.


Collection


T1114.002


Email Collection: Remote Email Collection


Star Blizzard interacts directly with externally facing Exchange services, Office 365 and Google Workspace to access email and steal information using compromised credentials or access tokens.


Collection


T1114.003


Email Collection: Email Forwarding Rule


Star Blizzard abuses email- forwarding rules to monitor the activities of a victim, steal information, and maintain persistent access to victim's emails, even after compromised credentials are reset.

MITIGATIONS
A number of mitigations will be useful in defending against the activity described in this advisory.
Use strong passwords. Use a separate password for email accounts and avoid password re-use across multiple services. See NCSC guidance: Top Tips for Staying Secure Online.
Use multi-factor authentication (2-factor authentication/two-step authentication) to reduce the impact of password compromises. See NCSC guidance: Multi-factor Authentication for Online Services and Setting Up 2-Step Verification (2SV).
Protect your devices and networks by keeping them up to date: Use the latest supported versions, apply security updates promptly, use anti-virus and scan regularly to guard against known malware threats. See NCSC guidance: Device Security Guidance.
Exercise vigilance. Spear-phishing emails are tailored to avoid suspicion. You may recognize the sender’s name, but has the email come from an address that you recognize? Would you expect contact from this person’s webmail address rather than their corporate email address? Has the suspicious email come to your personal/webmail address rather than your corporate one? Can you verify that the email is legitimate via another means? See NCSC guidance: Phishing attacks: Defending Your Organization and Internet Crime Complaint Center(IC3) | Industry Alerts.
Enable your email providers’ automated email scanning features. These are turned on by default for consumer mail providers. See NCSC guidance: Telling Users to "Avoid Clicking Bad Links" Still Isn’t Working.
Disable mail-forwarding. Attackers have been observed to set up mail-forwarding rules to maintain visibility of target emails. If you cannot disable mail-forwarding, then monitor settings regularly to ensure that a forwarding rule has not been set up by an external malicious actor.
DISCLAIMER
This report draws on information derived from NCSC and industry sources. Any NCSC findings and recommendations made have not been provided with the intention of avoiding all risks and following the recommendations will not remove all such risk. Ownership of information risks remains with the relevant system owner at all times.
This information is exempt under the Freedom of Information Act 2000 (FOIA) and may be exempt under other UK information legislation.
Refer any FOIA queries to ncscinfoleg@ncsc.gov.uk.
All material is UK Crown Copyright©.






This product is provided subject to this Notification and this Privacy & Use policy.







Tags

TopicsNation-State Cyber Actors, Cyber Threats and Advisories, Malware, Phishing, and Ransomware











Please share your thoughts
We recently updated our anonymous product survey; we’d welcome your feedback.










Related Advisories






Feb 07, 2024

Cybersecurity Advisory | AA24-038A



PRC State-Sponsored Actors Compromise and Maintain Persistent Access to U.S. Critical Infrastructure
 







Jan 16, 2024

Cybersecurity Advisory | AA24-016A



Known Indicators of Compromise Associated with Androxgh0st Malware
 







Dec 19, 2023

Cybersecurity Advisory | AA23-353A



#StopRansomware: ALPHV Blackcat
 







Dec 18, 2023

Cybersecurity Advisory | AA23-352A



#StopRansomware: Play Ransomware
 














Return to top






Topics


Spotlight


Resources & Tools


News & Events


Careers


About









Cybersecurity & Infrastructure Security Agency
 



Facebook


Twitter


LinkedIn


YouTube


Instagram


RSS



CISA Central
888-282-0870
central@cisa.dhs.gov










DHS Seal

CISA.gov
An official website of the U.S. Department of Homeland Security




About CISA


Accessibility


Budget and Performance


DHS.gov


FOIA Requests


No FEAR Act


Office of Inspector General


Privacy Policy


Subscribe


The White House


USA.gov


Website Feedback









































