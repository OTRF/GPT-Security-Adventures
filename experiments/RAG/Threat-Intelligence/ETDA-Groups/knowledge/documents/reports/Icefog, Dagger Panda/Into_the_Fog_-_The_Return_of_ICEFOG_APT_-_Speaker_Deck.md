# Reference for threat actor for "Icefog, Dagger Panda"

**Title**: Into the Fog - The Return of ICEFOG APT - Speaker Deck

**Source**: https://speakerdeck.com/ashley920/into-the-fog-the-return-of-icefog-apt

## Content






Into the Fog - The Return of ICEFOG APT - Speaker Deck





































Upgrade to Pro — share decks privately, control downloads, hide ads and more …






 Speaker Deck
 





                Features
 


Speaker Deck
PRO
 


                Sign in
 


                Sign up for free
 









Search










Search






















 





        Into the Fog - The Return of ICEFOG APT
      




Search































                ashley920
              


              June 03, 2019
            








 Research
 



 1


 7.5k













Into the Fog - The Return of ICEFOG APT

In 2013, a public report reveals a group of actors conducted targeted attacks leverage a malware dubbed ICEFOG against mainly government organizations and defense industry of South Korea and Japan. Little has been published on the activities of ICEFOG malwares since the report was released more than six years ago. However, despite a pause and a decrease in sample number were observed, the attacks leveraging the ICEFOG malware did not entirely stop after the exposure. In the past few years, we observed different attacks which the malware delivered and exploit with different tactic, techniques and procedure (TTP) compare with the campaign reported in 2013. In the recent attack, a new variant of the ICEFOG samples were also discovered. In this talk, I will introduce our finding among different samples discovered across these years and highlight the evolved TTPs that actor applied to evade detection in the new campaign. In addition, I will also introduce and clarify the potential connections between ICEFOG operator and other APT groups.









ashley920


              June 03, 2019
          






 Tweet
          

 Share
          











More Decks by ashley920



              See All by ashley920 
 














            從 WanaCry 看世界資安趨勢
          





                ashley920
              


 1
            

 170







Other Decks in Research



              See All in Research 
 














            フルリモートワークでのスクラムのスケール
          





                kmorita1111
              


 1
            

 770
















            学習指導法の効果を検証する研究デザインに関する方法論的研究 ―方法論的プラグマティズムを基盤にした多面的な検証方法の提案―
          





                unzaih
              


 0
            

 190
















            論文紹介: Generating News-Centric Crossword Puzzles As A Constraint Satisfaction and Optimization Problem
          





                upura
              


 0
            

 110
















            脳卒中患者・家族からみた循環器病対策推進基本計画の進捗に関する調査
          





                japanstrokeassociation
              


 0
            

 450
















            NeurIPS-23 参加報告 + DPO 解説
          





                akifumi_wachi
              


 3
            

 910
















            Julia Tokyo #11 トーク: 「Juliaで歩く自動微分」
          





                abap34
              


 1
            

 960
















            Trust, Accountability, and Autonomy in Knowledge Graph-based AI for Self-determination
          





                kirrane
              


 0
            

 240
















            Target trial emulationの概要
          





                shuntaros
              


 2
            

 980
















            コミュニティ、人、関係性 / Community, The Inner World, Relationships
          





                spring_aki
              
 PRO



 1
            

 730
















            Schrödinger Bridge問題に基づく拡散生成モデル学習
          





                takeshi_koshizuka
              


 0
            

 430
















            第59回名古屋CV・PRMU勉強会：ICCV2023論文紹介（自己教師あり学習）
          





                naok615
              


 0
            

 260
















            V&V of Systems Engineering Models and Modeling Languages
          





                ftsrg
              


 0
            

 210







Featured



              See All Featured 
 














            Building Your Own Lightsaber
          





                phodgson
              


 97
            

 5.5k
















            Bash Introduction
          





                62gerente
              


 604
            

 210k
















            Adopting Sorbet at Scale
          





                ufuk
              


 66
            

 8.4k
















            Six Lessons from altMBA
          





                skipperchong
              


 18
            

 2.8k
















            10 Git Anti Patterns You Should be Aware of
          





                lemiorhan
              


 645
            

 57k
















            JavaScript: Past, Present, and Future - NDC Porto 2020
          





                reverentgeek
              


 39
            

 4.2k
















            ParisWeb 2013: Learning to Love: Crash Course in Emotional UX Design
          





                dotmariusz
              


 101
            

 6.5k
















            Building Flexible Design Systems
          





                yeseniaperezcruz
              


 317
            

 36k
















            How To Stay Up To Date on Web Technology
          





                chriscoyier
              


 781
            

 250k
















            From Idea to $5000 a Month in 5 Months
          





                shpigford
              


 376
            

 45k
















            Product Roadmaps are Hard
          





                iamctodd
              


 43
            

 9.4k
















            Building Effective Engineering Teams - LeadDev
          





                addyosmani
              


 25
            

 1.4k








Transcript



*OUPUIF'PHm5IF3FUVSOPG *$&'0( "15Chi-en (Ashley) ShenSenior Researcher

View Slide



WHOIS• Chi En Shen (Ashley)• Senior Researcher at FireEye GlobalIntelligence Collection and Research Team.• Co-founder of HITCON GIRLS securitycommunity in Taiwan• Review board of Black Hat Asia, Blue HatShanghai, Hack in the Box• First time log in to Poland :D

View Slide



The Story Starts From• Tweetel! (Tweet + Intel)• Thanks for sharing JA Tweet…

View Slide



What is ICEFOG (aka Fucobha) ?• Kaspersky 2013 Report - The IcefogAPT: A Tale of Cloak and Three Daggers.• A malware used in the campaignstargeted US, JP, TW and KR between2011 – 2013.• Now ICEFOG is referred as a Malwarefamily, a report, sometimes referred as agroup. (is it?)

View Slide



The ICEFOG Campaign Return?• Last public report in 2013 and 2014.• No public reporting on the new ICEFOG campaignafter 2014. What happened between these 5years?• The samples discovered recently has changed thetarget scope. Is this the same group as in 2013?• Goal: find out what happened between these 5years and find out who are using ICEFOG.Release of ICEFOG reportBlog about Java version ICEFOG.2013 2014 2019??????????????????????????????????????????????????

View Slide



Why Do We Care?

View Slide



Why Do We Care?Know yourPokemon andknow yourself,you willalways bevictorious.- AshleyThreat Intelligence

View Slide



Let’s start HUNTING!• Tools:• Yara, signature detections on appliance,• Method:• Strings• Malware Functions• PDB & GUID• Exploit document template• Infrastructure pivoting, correlation.

View Slide



ICEFOG Variants (<2014)Old ICEFOG ICEFOG Type 1 ICEFOG Type 2 ICEFOGType 3 & 4(No sample)ICEFOG-NG ICEFOG OSX(aka Macfog)ICEFOG Java(aka Javafog)SupportplatformWindows Windows Windows(shellcode &standalone)Windows Windows Mac OSX JavaSupportFunctions• upload_• download_• Cmd_• code_• upload_• download_• Cmd_• code_• upload_• download_• Cmd_• Code_Unknown• Cmd• Download• Upload• sleep• upload_• download_• Cmd_• code_• upload_• cmd_UpdateDomain• cmd_CommunicationMethodCommunicatewith emailsCommunicate withC&C server with“.aspx” scriptsScript basedproxy serverC&C server withscripts named“view.asp”,“update.asp”,“upfile.asp”TCP connectionto port 5600Communicate withC&C server with“.aspx” scriptsCommunicatewith C&C serverwith “.aspx”scripts

View Slide



Common ICEFOG StringsCommunication TrafficICEFOG-Type2ICEFOG-Type1XOR KeysOld ICEFOG Mail

View Slide



Hunting Malware FunctionsICEFOG-NG CommunicationICEFOG-NG Encrypt FunctionICEFOG-Type 1 Encrypt FunctionICEFOG OSX Encrypt Function

View Slide



The CVE2017-11882 Exploit Template• Also, great research from Anomali.• https://www.anomali.com/blog/analyzing-digital-quartermasters-in-asia-do-chinese-and-indian-apts-have-a-shared-supply-chainShellcode decode routineOpen Document Encoded (0xFC) Dropper(8.t)Drops into%temp%Shellcodedecode &executeMalwareCan be hunted by the RTF ObjectDropper

View Slide



The Shared Exploit Builder• CVE 2017-11882 exploit template.• Actually, shared among at least 3 different groups. (APT40, Conimes team aka GoblinPanda, ICEFOG Operators)Threat Group Hash Malware Create Date AuthorTargetedRegionAPT40d5a7dd7441dc2b05464a21dd0c0871ffBEACON 2017-12-07 08:17:00 Windows User USATemp.CONIMESf223e4175649fa2e34271db8c968db12TEMPFUN 2018-01-15 14:47:00 Windows User LAOTemp.CONIMES07544892999b91ae2c9280d8ee3c663aTEMPFUN 2018-01-17 09:04:00 Windows User VNMTemp.CONIMES45a94b3b13101c932a72d89ff5eb715aTEMPFUN 2018-01-31 11:24:00 Windows User VNMICEFOG Operator46d91a91ecdf9c0abc7355c4e7cf08fcICEFOG 2018-02-22 20:07:00 T TURICEFOG Operator80883df4e89d5632fa72a85057773538ICEFOG 2018-02-22 20:07:00 T KZ, RU

View Slide



Two ICEFOG Variants (2014 - 2019)ICEFOG - P ICEFOG -MSupport platform Windows(x86 & x64)Windows(shellcode)First Seen 2014 2018CommunicationProtocolHTTP HTTPS (port 443)

View Slide



ICEFOG-P (New) Command Descriptioncmd_ Execute the command received from C&Cdownload_ Download file from specified URLfilelist_ Obtaining the list of files within specified folder.upload_ File loading from the server to computer.delete_ Delete specified filerename_ Move file to specified locationnewdir_ Create specified directorybeforecontinuefile_ Reset connection to the servercontinuefile_ Resume the file download from the server.exit_ Terminate Process.transover_ Termination of current thread.screen_ Send screenshot to C&C server.key_ Send keylogger’s log file to C&Cdisklist_ Setting monitored foldersdisklog_ Upload monitored folder’s datacode_ (removed) run code from file to memoryNew supported commandsGentle reminder for entering the main function20130505Check if system date < 20130505Anti-sandbox?

View Slide



ICEFOG-P (New)POST /upload.aspx?filepath=info&filename=_address>.jpg HTTP/1.1User-Agent: Internet ExplorerHost: foo.comContent-Length: 862Cache-Control: no-cacheHOST NAME:WINDOWS7USER NAME:userOS Version: Microsoft Windows 7 x86 Service Pack 1 (Build 7601)CPU: GenuineIntel Intel64 Family 6 Model 142 Stepping 9 0MHZPhysical memory: Total physical memory:1023MB,Availablememory:388MBWindows Directory: C:\\WindowsSystem Directory: C:\\Windows\\system32Hard Disk: C:\\ (NTFS)CD-ROM Disk: D:\\Disk space: Total disk space:39G,The remaining disk space:15GPOST/news/upload.aspx?filepath=ok&filename=stname>_.jpg HTTP/1.1Host: icefog.8.100911.comAccept: image/gif, image/x-xbitmap,image/jpeg, image/pjpeg, */*Accept-Language: en-usContent-Type: multipart/form-dataAccept-Encoding: gzip, deflateConnection: Keep-AliveCache-Control: no-cacheUser-Agent: MyAgentContent-Length: 0Traffic of ICEFOG-PTraffic of ICEFOG Type 1Adds physical machineinformation likely forfiltering out sandbox oranalysis environment

View Slide



ICEFOG-P (New)Use the code from fgdump projectHarvests Windows and browser credentialsSource code seems to download from internetLoading sqlite3 library for collecting Firefox credentialsMalware also embedded some of the functions

View Slide



ICEFOG-P (New)Monitor directory changes with ReadDirectoryChangesW API,logs save to fmonitor.dat Change log output formatdisklist_ save the directory list to filecfg_temp.dat _disklog send changes log to C2/upload.aspx?filepath=disklog/_Address>&filename=20131314.jpg

View Slide



ICEFOG-M (The latest)• Supports same functions as ICEFOG–P.• Communication changed to HTTPS viaport 443.• Payload became file-less (stored inregistry), applied a customized loaderlaunched by benign loader (DLLhijacking).• Loads an external sqlite3.dll library.Encrypted ICEFOG payload stored in registry

View Slide



PDB in ICEFOGPDBAssociated ICEFOGVariantE:\zc\HTTPS\HTTPS\86AuthenticateProxy\ExeLoader\Release\RasTls.pdb ICEFOG-PC:\Users\apper\Desktop\86AuthenticateProxy（copy）\ExeLoader\Release\RasTls.pdb ICEFOG-PC:\0426\86AuthenticateProxy\ExeLoader\Release\RasTls.pdb ICEFOG-PC:\Documents and Settings\Administrator\Desktop\86AuthenticateProxy（copy）\ExeLoader\Release\RasTls.pdbICEFOG-PD:\vvvvv\downloadccc0301\chen_http0301\source\Server\64\ExeLoader\x64\Release\linkinfo.pdb ICEFOG-PF:\worktmp\2014.11.05\ff\Server\86AuthenticateProxy\ExeLoader\Release\linkinfo.pdb ICEFOG-P• e:\jd4\myServer(RegRun)\release\jd4(reg).pdb• e:\jd4\myServer(RegRun)\release\jd4(reg).pdb• d:\jd\jd(RegRun)\release\jd3(reg).pdb• x:\jd(RegRun)\release\jd3(reg).pdb• d:\jd\jd(RegRun)\release\jd3(reg).pdb• e:\6.26\myServer\release\myServer.pdb• d:\jd\jd(RegRun)\release\jd3(reg).pdb• C:\Users\yang.zc\Desktop\代码片调用程序4\Release\UCCodePieceGo.pdb• D:\Undercurrent\服务端\代码片服务端\过UAC版本\专用代码片调用程序\Release\UCCodePieceGo.pdbICEFOG Type 1ICEFOG Type 2< 2013ICEFOG Samples > 2013More developers?

View Slide



MacOS X ICEFOG (aka MacFog)• Among all the samples we collected, some are theMacOS X MachO executable files.• The MacOS X ICEFOG was first distributed inChinese forums, forged as image processsoftware.• Newly uploaded old samples,having the same default C&Csetting.• Only one newsample with aprivate IPsetting(testing?).

View Slide



ICEFOG Variants Compiled Timestamp Timeline2011 2012 2013 2014 2015 2016 2017 2018 2019ICEFOG OldICEFOG Type 1ICEFOG Type 2ICEFOG-NGICEFOG-PICEFOG-M(loader)2013-06-20 2013-06-262014-11-18 2018-02-262018-12-102018-04-172011-06-19 2013-02-162011-03-16 2013-08-052011-07-22 2011-08-05

View Slide


View Slide



How to determine the timeframe of the sample?• When we found the sample after the campaign finished.• Consider:• PDNS time• Domain create date• Compile timestamp (dropper? Payload? Wrapper?)• Exploit document last saved time (template?)• Decoy document timestamp• Date sample was first seen in the wild• PDBSample Sample First Seenin the wildExploit DocLast saved dateDropped Malware CompileDateC&C Domain PassiveDNS First SeenDecoy File Last Modifed datec3ed6b34707e92f7aa35859a9647f0442017-08-0310:48:092014/04/110:00:002016-09-27 02:23:30 2017-08-032018-02-262017-08-02 19:17:00

View Slide


View Slide



Infrastructure Clustering• Connecting the dots with passiveDNS, registrant email• Tool: Maltego• Problems / difficulty• Incomplete PDNS data• Actor might have changed theinfrastructure entirely after the report.• Sinkholes filtering. (not all in db….)• Parking filtering.• Hosting server.

View Slide


View Slide


View Slide



• A lot of sinkhole connected to“sinkhole.yourtrap.com”• Usually 153.xxx.xxx.xxx in Japan registered byNTT.

View Slide



2014Samples TargetsKZ and RU2015Attack Target anAgriculture Company inEurope2016 2017 2019Campaign TimelineSample targetpotentially RussiaTOPNEWSCampaignAPPERCampaignSample targetTajikistanSampletargets KZ2018WATERFIGHTCampaignWATERFIGHTCampaign

View Slide



Attack targeted Agriculture Company in Europe (2015)• 64 bit ICEFOG-P found in the compromised environment.• Persistent attack started from 2011.• Actor mainly used SOGU and FUNRUN backdoor to gain initial access.• Also, found VICEROY backdoor, which has been used by APT9.• We also found malware connects to APT10 infrastructure.• The ICEFOG backdoor found at the scene was a customized version.

View Slide



Attack targeted Agriculture Company in Europe (2015)• Leveraged aspostexploitationtool.• Getting C&Cconfigurationfrom two filesand decodewith 0x99.

View Slide



• Campaign targets Mongolia and Russia, suspected media, finance and government.• Sample delivered by spear-phishing email.• The ICEFOG samples are all ICEFOG-P variant.• Some samples includes suspected campaign code information.HashCompileTimestampDrop by C&C PDB Campaign Codeeb2d297d099f3d39874efa3f89735a012015/03/1210:18:13f8cc15db9c85da19555a7232b543c726dnservers.itemdb.comrussion.dnsedc.comC:\Documents andSettings\Administrator\Desktop\86AuthenticateProxy（copy）\ExeLoader\Release\RasTls.pdb02-03c7d2c170482d17e2e76e6937bd8ab9a52015/05/145:11:42B3EFDA0E130373DAF6CB17801714B66F (rarsfx)bulgaa.sportsnewsa.netC:\0426\86AuthenticateProxy\ExeLoader\Release\RasTls.pdb1207dc1f0e60f11c456aa15cc3546716c172015/05/146:11:42e84b74f07ae803852f2ed19458a1539d (tsalin.docx.exe)74583d7355113ad3e58e355b003083e5 (winword.scr)zaluu.dellnewsup.netC:\0426\86AuthenticateProxy\ExeLoader\Release\RasTls.pdb10009d8f865bccfb239afab4f4f564081ff2016/09/273:23:3047713144ae08560ba939ea01620a0a2d (toot.docx .exe)zaluu.dellnewsup.netE:\zc\HTTPS\HTTPS\86AuthenticateProxy\ExeLoader\Release\RasTls.pdbb2015 TOPNEWS Campaign

View Slide



• Most ICEFOG payloads are dropped by RARSFX dropper.• Decoy uses government related content.ТӨРИЙН ТУСГАЙ АЛБАН ТУШААЛЫНЦАЛИНГИЙН СҮЛЖЭЭ” (Mongoliantranslation: SPECIAL OFFICES OFJURISDICTION)2015 TOPNEWS Campaign

View Slide



2015 TOPNEWS CampaignHash Malware Family Compile timestamp C&C Target664318c95c4a48debd3562ea602796b9TEMPFUN 2014-07-23 12:44:56 win.dellnewsup.neta489f2b4505b8f291804e3931cf16ed8TEMPFUN 2014-07-23 12:44:56 win.dellnewsup.net MN2e74505cc08c0d0d88146d46915f37afSOGU2015-02-06 02:56:28 mn.dellnewsup.netnews.dellnewsup.netMNa0389879ea435e647d29f6966b1d601fFUNRUN 2015-02-07 09:34:05 date.dellnewsup.net1a93c0257f52e2b1e8e4f52c033a61b3SOGU 2011-03-02 07:40:24 dwm.dnsedc.com RU• The domain “dellnewsup.net” has 13 sub-domains.• Pivoting these sub-domains, we found other malwares connected to theinfrastructure.• Campaign also leveraged SOGU, TEMPFUN and FUNRUN to attack Mongoliantargets from 2014 to 2015.

View Slide



2015 TOPNEWS Campaign• Domains registrantemail linked to theRoaming Tiger groupand rotten tomatocampaign.dellnewsup.netsportsnewsa.netdnsedc.comdnsqaz.comsystemupdate5.dtdns.nettransactiona.comgooglenewsup.netfuturesgolda.comgoogltrend.comfinancenewsu.netmicronewsup.netdellindustry.comnewsupdatea.net…… More[email protected]http://2014.zeronights.org/assets/files/slides/roaming_tiger_zeronights_2014.pdfRoaming TigerCampaign

View Slide



2016 APPER Campaign• In September 2015, KZCERT published ablog about an ICEFOG sample targetingKazakhstan.• The sample is an XLS embedded maliciousmacro that drops an RARSFX dropper, whichfurther deploys ICEFOG-P.PE embedded in macroDecoy lure

View Slide



2016 APPER Campaign• Pivoting the C&C infrastructure, wefound 8 related ICEFOG-P samplessuspected of being used in the samecampaign.• Same PDB strings in the samplessuggest a possible developer “apper”.HashCompileTimestampC&CCampaign codepdbaae3e322dbe5bb1894a412ca08afdf032016/05/2210:35:41ddns.epac.to cyexyC:\Users\apper\Desktop\86AuthenticateProxy（copy）\ExeLoader\Release\RasTls.pdbe28c2d68a6f13e81d321712888c89e522016/05/198:26:23ddns.epac.to(45.125.13.199)cyexyC:\Users\apper\Desktop\86AuthenticateProxy（copy）\ExeLoader\Release\RasTls.pdb0e25aa791c9119108af073bc9e9d0fa22016/05/109:24:3845.125.13.199dxxC:\Users\apper\Desktop\86AuthenticateProxy（copy）\ExeLoader\Release\RasTls.pdba4dc9763d296c45a846156f02479ecde2016/05/108:49:4545.125.13.199ghjC:\Users\apper\Desktop\86AuthenticateProxy（copy）\ExeLoader\Release\RasTls.pdba9ecf6d2674443cdac067b136b04c7d02016/03/214:20:25poff.wha.la soumsC:\Users\apper\Desktop\86AuthenticateProxy（copy）\ExeLoader\Release\RasTls.pdb404b1b78b4f34612e61d4af3bf5083f12016/03/214:20:25poff.wha.la soumsC:\Users\apper\Desktop\86AuthenticateProxy（copy）\ExeLoader\Release\RasTls.pdba78212faa38ef1078b300a492997fc022016/03/214:20:25poff.wha.la soums\Users\apper\Desktop\86AuthenticateProxy（copy）\ExeLoader\Release\RasTls.pdb118.193.228.32zorsoft.ns1.nametajikstantravel.dynamic-dns.netcospation.netpoff.wha.lamitian123.commocus.cospation.netcospation.net

View Slide



2018 The WATERFIGHT CAMPAIGNHash File name ExploitDefaultcodepageCreation DateLastModifiedAuthorLastmodify by9ca6d45643f89bf233f08b7d74910346Address Book 2018.doc CVE-2017-11882 Western European2018/02/2220:07:002018/02/2220:08:00T Td00a34baad19d40dcefbadb0942a2e4dWorkPlan.doc CVE-2017-11882 Western European2018/02/2220:07:002018/02/2220:08:00T T88d667cc01c4d8ee32e9de116f3bfdebAMU_SLA_Agreement_Final_Dt_20-Spr_14.docCVE-2017-11882 Simplified Chinese2018/02/2220:07:002018/03/1417:34:00T Administrator46d91a91ecdf9c0abc7355c4e7cf08fckatılımcılar listesi.doc CVE-2017-11882 Western European2018/02/2220:07:002018/02/2220:08:00T T80883df4e89d5632fa72a85057773538Внутренняя описьдокументов AGAT.docCVE-2017-11882 Western European2018/02/2220:07:002018/02/2220:08:00T T7fa8c07634f937a1fcef9180531dc2e4счет.docCVE-2017-11882 Simplified Chinese2017/05/2211:52:002017:05:2211:52:00Windows Windowse7c5307691772a058fa7d9e8ea426a59Задание.doc CVE-2017-11882 Simplified Chinese2017/05/2211:52:002017:05:2211:52:00Windows Windows63f9eaf7a80231480687b134b1915bd0Российский фигуриствыиграл зимниеОлимпийские игрыPyeongChang в ЮжнойКорее.docCVE-2017-11882 Simplified Chinese2017/05/2211:52:002017:05:2211:52:00Windows Windows• Campaign targeted suspected water source provider, banks and government.• Targeted countries include Turkey, India, Kazakhstan, Uzbekistan and Tajikistan.

View Slide



2018 The WATERFIGHT CAMPAIGNLeveraged the shared exploit template

View Slide



2018 The WATERFIGHT CAMPAIGN• Exploit document ICEFOG-P samples.• C&C domain and file name shows interest in a water sourcecompany in Uzbekistan.• Compiled a lot samples in 2 daysHash Compile date Drop by C&C Campaign code4178d9b22efe7044540043b5c770b6aa2018/02/24 5:20:16 9ca6d45643f89bf233f08b7d74910346 tele.zyns.com umde1c2d4c95c1b4e9d5193423719a7bb0752018/02/23 8:13:20 d00a34baad19d40dcefbadb0942a2e4d uzwatersource.dynamic-dns.net osbc71e5b89d5a804ddbe84fa4950bf97ac7 2018/02/26 11:58:57 88d667cc01c4d8ee32e9de116f3bfdeb trendiis.sixth.biz hgmpy6fffdb88292eeed0483b4030e58f401e 2018/02/23 8:13:20 46d91a91ecdf9c0abc7355c4e7cf08fc uzwatersource.dynamic-dns.net osbc6850e553445c0c9eac3206331eb0429b2018/02/23 9:44:25 80883df4e89d5632fa72a85057773538 laugh.toh.info jkmsyd5c67718e35bd1083dd50335ba9e89da2018/02/23 8:44:25 7fa8c07634f937a1fcef9180531dc2e4 laugh.toh.info jkmsy9344e542cc1916b9ddb587daa70f06522018/02/23 9:35:38 e7c5307691772a058fa7d9e8ea426a59 aries.epac.to gskvc2893fefcadbc7fed4fe74ea56133901 2018/02/23 14:49:58 63f9eaf7a80231480687b134b1915bd0 kastygost.compress.to msxdg

View Slide



2018 PHKIGHT Campaign• On April 26, 2018, our appliance detected ICEFOG traffic from out of thePhilippines.• We also found the traffic of ICEFOG from the scanned URL on a public scanningservice. The timestamp indicates that this campaign was likely still ongoing inJuly and October 2018:POST/Home/upload.aspx?filepath=*&filename=*HTTP/1.1User-Agent: Internet ExplorerHost: yahzee.eyellowarm.com:443Content-Length: 908Connection: Keep-AliveCache-Control: no-cache

View Slide



2018 PHKIGHT Campaign• Investigating the C&C domain “eyellowarm.com”, we found two other sub-domains:• news.eyellowarm.com• meal.eyellowarm.com• The domain “news.eyellowarm.com” is connected by an ENDCMD (aka(Hussarini, Sarhust) malware, which we have observed in APT15’s (aka SocialNetwork Team) campaign.Hash filename Malware Compile Timestamp C&Ce5bdc78c686e15dfeed6696bcd5989c3NvSmartMax.dll ENDCMD 2010-12-19 04:51:39 news.eyellowarm.comNote that although the sample has the compile timestamp in2010, it is observed in the wild in 2018 and the C&C remainsactive during our analysis in 2018.

View Slide



2018 PHKIGHT Campaign• Correlated (through passive DNS) infrastructure show strong interest in the Philippines.- www.benzerold.com- ph4.01transport.com- news.eyellowarm.com- durian.appleleveno.com- adove.benzerold.com- benzerold.com- mailback.benzerold.com- ph2.01transport.com- phldt.appleleveno.com- yahzee.eyellowarm.com- mecaf.benzerold.com- ipad.appleleveno.com- course.appleleveno.com- well.suverycool.com- pldt.benzerold.com- www.knightpal.com- banana.appleleveno.com- appleleveno.com- node-ph-mnl2.kyssrcd.pw- isafp.numnote.com- ph1vip.blue-vpn.net- news.numnote.com- news.kaboolyn.com- topic.numnote.com- dns01.comesafe.com- is01.knightpal.com- eyellowarm.com- news.yahzee.eyellowarm.com- kaboolyn.com- dns1.kaboolyn.com- yahzee.yahzee.eyellowarm.com- ds03.numnote.com- meal.eyellowarm.com- message.benzerold.com- pop3.numnote.com- afp1.kaboolyn.com- trans.numnote.com- usiszero.benzerold.com- numnote.com- pldt.knightpal.com- ph1.numnote.com- ns1.01transport.com- pldtcon.knightpal.com- afp1.knightpal.com- appdata.appleleveno.com- ns2.01transport.com- ns01.knightpal.com- ph.01transport.com- support.numnote.com- ph1.01transport.com- knightpal.com- pnoc1.numnote.com- 01transport.com

View Slide



2018 PHKIGHT CampaignHashMalwarefamilyfilename Compile Timestamp C&C PDB string4f11e00b015047642d8ddc306fc90da0ENDCMDNvSmartMax.dll2010-12-19 04:51:39 news.eyellowarm.comC:\Users\Sun\Desktop\new_test\NvSmart\Release\NvSmart.pdb1554900f889c9498c43c9f875eceea38MIRAGE netsh.exe 2013-06-28 09:27:57 pldtcon.knightpal.com7b8c955a0f1d6d37833277849a070e37ENDCMD Outllib.dll 2016-07-06 02:50:18 well.suverycool.com92853e0506ea16c6f17ac32f5ef8f3b3ENDCMD Outllib.dll 2015-08-27 07:52:36 ipad.appleleveno.com4f11e00b015047642d8ddc306fc90da0ENDCMD Outllib.dll 2015-08-27 07:52:36 durian.appleleveno.com86409708eb0c716858ea30ae15eb7d47ENDCMD N/A 2010-12-19 04:53:10 news.kaboolyn.comC:\Users\Sun\Desktop\new_test\NvSmart\Release\NvSmart.pdbMalware Connected to the Correlated Domains• ENDCMD and MIRAGE malware were exclusively observed used by APT15 (aka Social Network team).The targets, malware and TTP all align with the profile of APT15.

View Slide



2019 SKYLINE Campaign• Observed the ongoing campaign that likely targeted Turkey and Kazakhstan in2019.• The timestamp suggests the campaign might have started from 2018.• Leveraged CVE 2017-11882 shared exploit template with ICEFOG-M, nopayload timestamp.Hash filename Exploit Code Page Create DateLast modifydateAuthorLastmodifyby30528dc0c1e123dff51f40301cc03204 UnknownCVE-2018-0802WesternEuropean2018/04/231:01:002018/04/23 1:01:00T T4642e8712c8ada8d56bd36416abb4808doc.rtfCVE-2017-11882N/A N/A N/A N/A N/Ac65b73dde66184bae6ead97afd1b4c4bdoc20190301018.docCVE 2017-11882WesternEuropean2018/04/231:01:002018/04/23 1:01:00T T

View Slide



2019 SKYLINE Campaign• New ICEFOG attack vector – file-less payload (ICEFOG-M)Open Document Encoded (0xFC) Dropper(8.t)Drops into %temp%Shellcode in docdecode and execute8.T dropperShellcode write encryptedICEFOG-M payload to registryDLL hijacking loaderDropsRead, decryptand execute

View Slide



2019 SKYLINE CampaignThe Dropper’s workflowLoop to encryptthe payloadCustomized loaderread register key

View Slide



2019 SKYLINE Campaign• Two observed loadersHash Compile Timestamp Drop by Observed Connected C&C0b86cc8e56a400f1adeb1e7b6ebe6abe2018/12/10 14:31:47 4642e8712c8ada8d56bd36416abb4808nicodonald.accesscam.orgc6a73e29c770065b4911ef46285d65572018/04/27 3:49:31 30528dc0c1e123dff51f40301cc03204c65b73dde66184bae6ead97afd1b4c4bskylineqaz.crabdance.comxn— ylineqaz-y25ja.crabdance.comyouareexcellent.kozow.comxn--uareexcellent-or3qa.kozow.com

View Slide



ICEFOG-M (The latest)POST /upload.aspx?filepath=info&filename==_address> HTTP/1.1User-Agent: Internet ExplorerHost: foo.comContent-Length: 862Cache-Control: no-cacheHOST NAME:WINDOWS7USER NAME:userOS Version: Microsoft Windows 7 x86 Service Pack 1 (Build 7601)CPU: GenuineIntel Intel64 Family 6 Model 142 Stepping 9 0MHZPhysical memory: Total physical memory:1023MB,Availablememory:388MBWindows Directory: C:\\WindowsSystem Directory: C:\\Windows\\system32Hard Disk: C:\\ (NTFS)CD-ROM Disk: D:\\Disk space: Total disk space:39G,The remaining disk space:15GGroup : tttt1Added Group ID in traffic2013050520130601Updated the compared Date

View Slide



Who Are The Actor BehindThese Campaigns?

View Slide



2015TOPNEWS CampaignRoaming TigerCampaign2015Target Agriculture in EU2015Target KZ2018PHKNIGHTCampaignAPT15MalwareC&C OverlapTargetC&C Infra ConnectedRegistrant EmailTargetTTPAPT9Malware SampleFound in victim’senvironmentWeakMediumStrong

View Slide



Targeting Country: UZ, MN, MY, RU,BY, KZ, US, Tibet, UATargeting Industry: Gov, Oil and Gas,Aerospace, DefenseMalware: SOGU, GHOST, TEMPFUN,FIRSTBLOOD, PI.Roaming TigerTargeting Country: PH, VN, TW, US,UK, IT, PL, UN, SG, NATOTargeting Industry: Gov, Political partyMalware: ENFAL, ENDCMD,QUICKHEAL, SOGU, CYFREE, MIRAGE,NOISEMAKER, QUICKHEAL,SWALLOWFLYAPT15Targeting Country: HK, US, SG, MY, JP,IN, KR, TH, TWTargeting Industry: Aerospace,Agriculture, Construction, Energy,Healthcare, ,High Tech, Media,TransportationMalware:BIGJOLT,FUNRUN,GH0ST,HOMEUNIX,JIMA,PHOTO,POISONIVY,SKINNYGENE,SOGU,VICEROY,VIPSHELL,WETHEAD,XDOOR,ZXSHELLAPT9

View Slide



What About Other Campaigns?

View Slide



45.77.134.195youareexcellent.kozow.comICEFOG-P(0b86cc8e56a400f1adeb1e7b6ebe6abe)trendiis.sixth.bizICEFOG-P(71e5b89d5a804ddbe84fa4950bf97ac7)118.193.158.53tele.zyns.comICEFOG-P(4178d9b22efe7044540043b5c770b6aa)SKYLINE Campaign103.242.134.146tajikstantravel.dynamic-dns.netuzwatersource.dynamic-dns.neteagleoftajik.dynamic-dns.nettajikmusic.dynamic-dns.nethttps.ikwb.comTarget TajikistanWATERFIGHT campaignSOGU(defe397b41aa5219d2126304a42212d3)Let’s Start Connecting the Dots!Hint: links are either pdns or observed resolve

View Slide



eagleoftajik.dynamic-dns.netICEFOG-P(0c410d22265dece807193bf8a47fd91f )ICEFOG-P(e28c2d68a6f13e81d321712888c89e52)WATERFIGHTCampaignTargetTajikistan45.125.13.199APPER Campaign118.193.228.32zorsoft.ns1.nametajikstantravel.dynamic-dns.netpoff.wha.laSOGU(ee649cf2b4e40288cd1194c3da03edef )27.255.80.226 nitec.ns1.nameSOGU(d5e8b1f836a9199a9a176aee007efc65 )103.243.24.149 bluesky.zyns.commoonlight.compress.to103.242.134.140QUICKHEAL(5378d13965a3499ea83d6d0371b03794 )niteast.strangled.netwhitebirds.mefound.comgame.sexidude.comSOGU(d5e8b1f836a9199a9a176aee007efc65 )ICEFOG-P(be7ee5ae37dbf03df52c6bfda41c6194)QUICKHEAL(E34874c27161eb563cfbdc00ee1334a2)WHITEBIRD(fdfcd9347c1f6f6a4daaf3f50bc410c6)45.252.63.244 honoroftajik.dynamic-dns.netuzwatersource.dynamic-dns.netICEFOG-P(6fffdb88292eeed0483b4030e58f401e)WATERFIGHTCampaignwww.ddns.epac.toICEFOG-P(a9ecf6d2674443cdac067b136b04c7d0)

View Slide



2016 – 2017APPER Campaign2018WATERFIGHT Campaign2019SKYLINE Campaign2017SOGU & QUICKHEAL targets KZC&C Infra Connected(118.193.228.32)TargetTTPC&C Infra Connected(103.242.132.197)C&C Infra Connected(103.242.132.197)TargetTTPC&C Infra Connected(154.223.167.20,45.77.134.195)2015Targets TajikistanC&C Infra Connected(103.242.132.197)2014Target KZTargetC&C Infra ConnectedC&C Infra Connected(103.242.132.197)WeakMediumStrong

View Slide



2016 – 2017APPER Campaign2018WATERFIGHT Campaign2019SKYLINE Campaign2015TOPNEWS Campaign2017SOGU & QUICKHEAL targets KZC&C Infra Connected(118.193.228.32)TargetTTPC&C Infra Connected(103.242.132.197)C&C Infra Connected(103.242.132.197)TargetTTPC&C Infra Connected(154.223.167.20,45.77.134.195)2015Targets TajikistanC&C Infra Connected(103.242.132.197)Roaming TigerCampaign2015Target Agriculture in EUSame PDB string2015Target KZ2018PHKNIGHTCampaignAPT15MalwareC&C OverlapTargetC&C Infra ConnectedRegistrant EmailTargetTTPAPT9Malware SampleFound in victim’senvironment2014Target KZTargetC&C Infra ConnectedC&C Infra Connected(103.242.132.197)WeakMediumStrong

View Slide



Temp Group A• Active since (at least): 2014• Delivery method: Spear-phishing email• Exploitation method: Malicious macro,RARSFX, CVE 2017-11882, CVE 2012-0158• Target region: Russia, Kazakhstan,Tajikistan, Uzbekistan and Turkey• Malware: ICEFOG-P, ICEFOG-M, SOGU,QUICKHEAL• Connection to other group: Uses ICEFOG-Pwith the same PDB as Roaming Tiger.Targeting Country: Rum KZ, Tajikistan,UZ, TRTargeting Industry: Gov, NaturalresourceMalware: ICEFOG-P, ICEFOG-M,SOGU, QUICKHEAL???????

View Slide



Conclusion• ICEFOG is malware shared among Roaming Tiger, APT15, Temp Group A andsuspected APT9.• Shared malware is a pitfall for attribution, we should not do attribution onlybased on malware.• Temp Group A is aggressively using ICEFOG-P and ICEFOG-M to targetRussia, Kazakhstan, Tajikistan, Uzbekistan and Turkey.• With the file-less ICEFOG-M, host-based detection for payloads are moredifficult.• Continued development indicates there could be more attacks leveragingICEFOG in future campaigns, and possibly leveraged by more attackers.

View Slide



2"Chi-en (Ashley) ShenSenior Researcher@ashley_shen_920

View Slide











SpeakerDeck






Top Categories

Programming
Technology
Storyboards
Featured decks
Featured speakers





Use Cases

Storyboard Artists
Educators





Resources

Help Center
Blog
Compare Speaker Deck
Advertising





Features

Private URLs
Password Protection
Custom URLS
Scheduled publishing
Remove Branding
Restrict embedding
Notes






Copyright © 2024 Speaker Deck, LLC.
All slide content and descriptions are owned by their creators.

About
Terms
Privacy
DMCA
Accessibility Statement


















