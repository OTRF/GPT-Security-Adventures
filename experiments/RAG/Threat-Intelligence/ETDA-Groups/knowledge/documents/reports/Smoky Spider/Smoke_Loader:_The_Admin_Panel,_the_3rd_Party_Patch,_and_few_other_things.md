# Reference for threat actor for "Smoky Spider"

**Title**: Smoke Loader: The Admin Panel, the 3rd Party Patch, and few other things

**Source**: https://blog.netlab.360.com/smoke-loader-the-core-files-the-admin-panel-the-plugins-and-the-3rd-party-patch/

## Content



Smoke Loader: The Admin Panel, the 3rd Party Patch, and few other things



























































Botnet
DNSMon
DDoS
PassiveDNS
Mirai
DTA
















360 Netlab Blog - Network Security Research Lab at 360


—
Smoke Loader: The Admin Panel, the 3rd Party Patch, and few other things

Share this 




 

 












Import 2022-11-30 11:16


Smoke Loader: The Admin Panel, the 3rd Party Patch, and few other things










jinye

Feb 18, 2019
• 9 min read






Smoke Loader is a botnet software that is publicly available since 2011 on the black market. It is old but still active, just in the last six months we have seen more than 1,500 active samples.Although it has been repeatedly exposed by different security researchers in recent years, the public available documents we have seen are all missing an important part of this botnet software, the admin panel. We are not quite sure why no one seems to have talked about it except citing screenshot shared by the possible malware author in the underground forum.We also noticed the existence of a bunch of special modified samples, these samples also caught attention by other researchers. There is a theory that the original author did this as an effort to hide the C2 to make it more difficult to be taken down. We have a different thought, we think that there are 3rd party out there who do not want to pay the original author fees to update C2 so they released these patched versions.So here are some details:Smoke Loader KitThe file structure in the kit is shown in the following figure,Core File, Loader_new_Cyberbunker.exe, working payload to be injected to the processes of the infected hosts.Web Console, this is the Admin PanelPlugins, including panel/mods and panel/keylogger, etc.Mysql database build script smoke_1.sql, where plugin rules are storedSmoke Loader Feature Introduction, smoke_features.txtInstallation NotesFigure 1. Smoke Loader's Panel Kit File StructureAdmin panelAfter deploying it, we get a web control interface, which is the Smoke Loader’s admin panel. It just looks very similar to the screenshots security researchers found from the underground market.The admin panel supports the following 12 modules (For details, refer to the smoke_features.txt) file comes with the kit:STEALERFORM GRABPASS SNIFFAKE DNSFILE SEARCHPROCMONDDOS attackKEYLOGGERHIDDEN TV(team viewer)MINEREMAIL GRABUser-defined programThe modules’ storage location and execution are different:The first eight functions, from ” STEALER” to “KEYLOGGER” refers to Panel/mods/plugins, this single file is actually a collection of 16 plug-ins. The 16 executables can be loaded by injecting into seperate explorer.exe process on victim hosts.Hidden TeamViewer and MINER: under path Panel/mods/tv and Panel/mods/minerXX correspondingly. (Both can be loaded by downloading the corresponding plugin then be injected as subprocess.)User-defined program: User can load any malicious program that he likes, either directly from the console or downloaded from a user specified URL. The execution process is also flexible,( it can be executed directly, or be loaded as a dll, or even directly be injected in the process.)Figure 2. Smoke Loader's Admin panel, Web InterfaceFigure 3. Smoke Loader Comes With a feature Introduction FileFigure 4. Smoke Loader User-Defined Function InterfacePluginSmoke Loader’s plugin system is very flexible. When it first launches, it tries to download all the built-in plug-ins and their execution rules. Customers can also add their own plug-ins and plug-in rules.A total of 16 plug-ins have been disassembled by decrypting the plugin file, some of which have the same function but are adapted to different versions of the operating system. When running on our test machine, we can see that it creates 9 subprocesses, each running a plugin. Note that although these process names are seemingly harmless as explorer.exe, they have been injected with plug-in payloads and are malicious. For details of the specific injection method, see Reference [1].Figure 5. The Console Retrieves the Plugin Rules from the Database for the BotsFigure 6. Plugins That Are Already Running in the Test MachineMore plugin details include:Mining plugin : It downloads the corresponding miner program (process wauuclt.exe) with the startup parameters to perform the mining task when it receives the mining instruction from C2.DDoS plugin : Many common DDoS attack types, such as http get flood, http post flood, download flood, udp flood, syn flood, tcp flood, https get flood, http slowloris floodForm Information Stealing Plugin : Supports common browsers including IE, Firefox, Chrom, Opera, Chromium, Yandex browser, Amigo browser, QQ browser, outlook, ThunderbirdFigure 7. Example of a Mining PluginFigure 8. Types of Attacks Supported by the DDoS Attack PluginFigure 9. List of Browsers Supported by the Form Stealing Plugin"Deception" or "Piracy" ?It has been reported that the recent Smoke Loader has an updated version [2] to defer security researchers’ effort to extract its’ C2s, we have also observed a similar set of samples but we have a different theory.We believe that this version of the changes came from a third party rather than the original author, the purpose is to break the limitations of the original author’s rule which requires extra fee to update C2 after purchase.Smoke Loader is available for about $850 in the black market. The author uses a license sales model to release a customized system for each buyer, including Loader+Panel. It’s worth noting that if buyer wants to change C2 he need to regenerate the Loader, and each rebuild of a Loader costs $10.With the above background info, let’s go back to these special samples we have, all together there are 88 samples. And one thing in common is that all of them have two “extra” residual C2 URLs that are not valid:hxxp://185.35.137.147/mlp/hxxp://185.35.137.147/mlp/With this information, we looked into our samples pool and have associated other original samples that only used these “extra” C2 as the only valid C2.Here are some highlights between the original version and the modified version:Residual C2 URLs : all modified versions share the exact same residual C2 URLs, suggesting that this set of samples have the same root;C2 configuration : the original samples encrypt the C2 configuration, and the modified samples store it in plaintext;Active and standby C2 mechanism : The original samples have backup C2 mechanism, but not in the modified samples;C2 verification mechanism : The original samples determine whether to install the startup item and whether to load the plug-in by verifying the CRC32 values of the two C2 first. The modified version directly overwrites the verification code with the NOP assembly empty instruction, and skips the verification mechanism all together.The modified version circumvents the limitation set by the author, but it comes with a price, only one valid hard-coded C2 is supported. The network behavior of the samples and our statistics both confirm this.Three Key Patch Codes in the Modified VersionThere are three key patches in the modified version:Patch 1 : to replaces the decryption function for the C2 configuration information, the C2 is written plaintext in the code. When the decryption function is called, C2 address is returned directly. As can be seen from the figure below, the C2 returned by each decryption function call is a direct “hxxp://jsoc8492.us/jd/” ;Patch 2 : to overwrite the code that verifies the first C2. The original sample is supposed to calculate the CRC value of the first C2, and then compare it with the encryption key. If it is mismatched, the plugin will not be loaded;Patch 3 : similar to above, just to work on the second C2;Figure 10. Patch 1, Replaces the Decryption Function of C2 Configuration InformationFigure 11. Patch 2, Using NOP Null Command Override to Skip the First C2 Authentication MechanismFigure 12. Patch 3, Using NOP Null Command Override to Skip the Second C2 Authentication MechanismOther Interesting DetailsLoaderThe Loader consists of an injector and a payload. The injector is responsible for some basic anti-sandbox and anti-reverse engineering tasks, and eventually injects the payload into the explorer process. The payload is the real working code.The 2018 version of the injector uses the PROPagate's packed injection solution, which is mentioned in Talos' documentation. Typically, buyers of Smoke Loader adds their own packaging scheme to pack Loader before spreading malicious programs through various channels. Therefore, the popular samples normally have two to three shells.Figure 13. The Popular Smoke Loader Sample Usually Has Two or Three Layers of Shells.Registration Packet and C2 Command Communication FormatAfter the sample launches, it sends a packet to register with the controller. We have yet to see a public document which details the data structure of the 2018 version, but with the files on hand we were able to easily figure it out.Figure 14. The Decrypted PackageFigure 15. The Registration Packet Data Structure Defined in the Console CodeHere is the register packet's format:Figure 16. Smoke Loader Online Package FormatHere are several fields' description:AFFID : Also called Seller ID, this is to ID the distribution channel, it is hard coded into the sample by the author. The most common values are Good, cece and new1, and about 15% of the samples only have an empty field here;BOT_WINVER : The target host OS version. It seems that all current Windows Personal Edition systems from WinXP to Win10 are supported. See the figure below;Figure 17. OS Version of the Host
BOT_RES : Smoke Loader has two sub version, the non-resident version only runs one time and then removes itself from the victim. Another resident version stays on the victim. This tag is used to distinguish it;

BOT_CMD : The instruction number, there are 15 instructions defined by the console, as shown in the figure below.Figure 18. Instruction Types Supported by Smoke Loader4. IoC StatisticsHere is some basic statistics for the samples we collected in the past six months:Samples: 1656C2: 296Affid: 42Number related to modified version:Original version vs modified version: 1568 vs 88Number of C2 URLs in modified version: 27Domain names involved in the C2 URLs: 15Grouped by Affid (Seller ID), the sample statistics are as follows. Among them, Good, Cece, and new1 are the top 3 channels, accounts for 88%. NA is the case where the Affid is empty:affid   count   %  
Good    826     49.9%  
cece    395     23.9%  
[NA]    238     14.4%
new1    77      4.7%  
1501    21      1.3%  
0       13      0.8%  
Pitt    12      0.7%  
1301    9       0.5%  
sel1    7       0.4%  
Form    5       0.3%  
OTHER   52      3.1%  
5. IoCMalware Sample md5s in last 6 months The whole list has more than 1,500 entries and can be downloaded here. The first ten records are listed below:001dacf6608df69d485514a172fff05d  
00521a5e800a85de875b703e9bc1f507  
00891f91904955fb69fad4488f96741a  
008d5eb400e41fcb87ef64db276013dc  
009e213b63a4830adf5df372261ae6b0  
00b8a47bdf14880ebeba6bebc3ea7dbc  
00c5063e13752357b35c097c4c0f7059  
00eef71e18381a537b1750c7f2983025  
01162c00d54b976536d692173ef3e039  
013748c007f80fb7cc2c42ca424e4733  
Malware C2 in last 6 months The complete list has more than 250 C2 entries, and can be downloaded here , and below are the first ten records. The format is as follows.version : version numberreq_key : rc4 encryption key for sending datares_key : rc4 decryption key for receiving dataremaining_c2 : the residual C2 in the modified versionaffid : Seller IDMd5 count : how many independent samples contain this C2Some details about the C2 list:Most of the samples have 2 to 5 C2s, but there are a few samples containing a much larger number such as 75 C2;Some samples change their reqkey, reskey when they get upgraded;#           NA                                             C2                   version  req_key  res_key          remaining_c2_if_exists                            affid md5_count
0                                                          http://makak.bit/2/  2018  0xe5400000  0xa6b397e0                                                         Good  826  
1                                                          http://mytter.ru/2/  2018  0xe5400000  0xa6b397e0                                                         Good  826  
2                                                       http://svoloch.club/2/  2018  0xe5400000  0xa6b397e0                                                         Good  826  
3                                                            http://d3s1.me/2/  2018  0x3b22e540  0xa6b397e0                                                         cece  395  
4                                                       http://kiyanka.club/2/  2018  0x3b22e540  0xa6b397e0                                                         cece  395  
5                                                      http://proxy-exe.bit/2/  2018  0x3b22e540  0xa6b397e0                                                         cece  395  
6                                                     http://5gssghhs2w.org/2/  2018  0xe5400000  0xa6b397e0                                                         new1   77  
7                                                          http://dvhwzq.ru/2/  2018  0xe5400000  0xa6b397e0                                                         new1   77  
8                                                          http://hdxaet.ru/2/  2018  0xe5400000  0xa6b397e0                                                         new1   77  
9                                                      http://hghwwgh6.info/2/  2018  0xe5400000  0xa6b397e0                                                         new1   77  
Contact UsReaders are always welcomed to reach us on twitter, WeChat 360Netlab or email to netlab at 360 dot cn.Reference[1] https://blog.talosintelligence.com/2018/07/smoking-guns-smoke-loader-learned-new.html[2] https://int0xcc.svbtle.com/a-taste-of-our-own-medicine-how-smokeloader-is-deceiving-dynamic-configuration-extraction-by-using-binary-code-as-bait[3] https://www.cert.pl/en/news/single/dissecting-smoke-loader/










— 360 Netlab Blog - Network Security Research Lab at 360 —
Import 2022-11-30 11:16





快讯：使用21个漏洞传播的DDoS家族WSzero已经发展到第4个版本
P2P Botnets: Review - Status - Continuous Monitoring
P2P 僵尸网络：回顾·现状·持续监测



See all 249 posts →







DDoS


          FBot 新进展
        

【更新：2019年12月4日】近期我们多次收到针对本blog的询问。我们决定将一些事实补充列出如下：


——Kenneth Crurrin Schuchman，绰号 Nexus-Zeta，一名21岁的年轻人，已经于2019年9月3日向美国阿拉斯加区域法庭认罪。Schuchman的认罪书表明，Schuchman及其同谋者通过感染大批设备，创建了一系列僵尸网络，包括 Satori，Okiru，Masuta，Tsunami，Fbot，并利用这些僵尸网络的DDoS破坏力牟利；

——本 Blog 中涉及到的脆弱性并非发生在 Hisilicon。通过后续分析以及安全社区交流，我们确认该脆弱性发生在华为海思的供应链下游厂商。为了保护最终客户的利益，我们决定不公开脆弱性细节、攻击者使用的载荷或者具体厂商名字；

——华为 PSIRT 对我们披露的安全事件，作出了负责任的响应；


读者在继续阅读本blog时，应当明确blog和样本中出现的 Hisilicon字样，源自Schuchman及其同谋者的错误判断。实际上整个IoT产业链条庞杂，其体量远超攻击者或者任何单一从业人员能够理解的范围。只有产业界





            Genshen Ye
          






            Hui Wang
          






            RootKiter
          





Feb 20, 2019
8 min read








Botnet


          Smoke Loader:主体、控制台、插件，以及盗版之殇
        

Smoke Loader 是一个在黑市上公开销售的僵尸网络软件。其活动时间可以追溯到2011年，虽然近年来已经被多次曝光，但保持持续升级，非常活跃。在我们统计中，仅最近半年活跃的样本就超过 1,500 个。

我们在跟踪这一家族的过程中，捕获了一套完整的恶意程序套件，包括其主体Loader、控制台Panel，以及控制台中包含的插件。对这套样本的分析使我们对其运行机制有了更深入的了解，这将是本文的主要内容之一。

分析过程中，我们还遇到一组被修改过的特例样本。虽然有人认为这组样本是作者在对抗安全研究人员提取C2主控域名，但仔细分析后，我们认为这是第三方做“盗版”。这部分的分析和研判过程，是本文的主要内容之二。

Smoke Loader相关的分析文档已经很多，本文不会涉及已经被公开的部分。相关内容，读者可以参阅文末参考部分。


Smoke Loader 套件分析

套件中的文件结构见后图，说明如下：

 * 本体，Loader_new_Cyberbunker.exe
 * Web控制台，Panel ，使用未加密的PHP语言编写
 * 插件，包括 Panel/mods 和





            jinye
          





Feb 3, 2019
13 min read









360 Netlab Blog - Network Security Research Lab at 360 © 2024
Powered by Ghost








