# 年轻人的第一台 VPS 代理服务器 - 资源荟萃 / 资源荟萃, Lv1 - LINUX DO
 年轻人的第一台 VPS 代理服务器 - 资源荟萃 / 资源荟萃, Lv1 - LINUX DO                                            

[跳到主要内容](#main-container)

 [![](https://linux.do/uploads/default/original/3X/b/4/b4fa45d8b03df61f5d011e173c0adf8497028b16.png)](/) 

*   ​
*    ![](https://linux.do/letter_avatar_proxy/v4/letter/n/58f4c7/96.png)
       [ 2 ](# "2 个未读通知") 

*   [话题](/latest "所有话题")
*   [我的帖子](/u/niyan2025/activity "我最近的话题活动")
*   [关于](/about "关于此网站的更多详细信息")
*   [即将到来的活动](/upcoming-events "即将到来的活动")
*   [文档](/docs "探索文档话题")
*   更多

外部链接

*   [Status](https://status.linux.do)
*   [Connect](https://connect.linux.do)
*   [Webmail](https://webmail.linux.do)
*   [Channel](https://t.me/linux_do_channel)
*   [Telegram](https://t.me/ja_netfilter_group)

类别

*   [开发调优](/c/develop/4 "此版块包含开发、测试、调试、部署、优化、安全等方面的内容")
*   [资源荟萃](/c/resource/14 "包括软件分享、开源仓库、视频课程、书籍等分享")
*   [文档共建](/c/wiki/42 "佬友化身翰林学士，一起来编书了。")
*   [跳蚤市场](/c/trade/10 "交易相关的版块，包含实体和虚拟物品供求、拼车等等")
*   [非我莫属](/c/job/27 "学成文武艺，货与帝王家。招聘/求职分类，只能发此类信息。")
*   [读书成诗](/c/reading/32 "跟着佬友们一起在论坛读完一本书是什么体验？")
*   [扬帆起航](/c/startup/46 "扬帆起航，目标是星辰大海！")
*   [前沿快讯](/c/news/34 "前沿快讯，不出门能知天下事。")
*   [福利羊毛](/c/welfare/36 "正经人谁花那个钱啊～ 此版块供羊毛、抽奖等福利使用。")
*   [搞七捻三](/c/gossip/11 "闲聊吹水的板块。不得讨论政治、色情等违规内容。")
*   [运营反馈](/c/feedback/2 "有关此站点、其组织、运作方式以及如何改进的讨论。")
*   [深海幽域](/c/muted/45 "冰山下的深海。帖子不会上信息流、不会被论坛搜索。")
*   [所有类别](/categories)

标签

*   [人工智能](/tag/%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD)
*   [公告](/tag/%E5%85%AC%E5%91%8A)
*   [快问快答](/tag/%E5%BF%AB%E9%97%AE%E5%BF%AB%E7%AD%94)
*   [抽奖](/tag/%E6%8A%BD%E5%A5%96)
*   [精华神帖](/tag/%E7%B2%BE%E5%8D%8E%E7%A5%9E%E5%B8%96)
*   [所有标签](/tags)

消息

*   [收件箱](/u/niyan2025/messages)

*   [我的消息串](/chat/threads "我的消息串")

频道

*   [常规频道](/chat/c/general/2 "🈲 禁止在聊天频道里发送 打卡 等无意义信息，被举报会喜提 禁言1小时 。")

直接消息

*    [![](https://linux.do/user_avatar/linux.do/xronus/48/130867_2.png)  Anivix](/chat/c/anivix/32458 "与 Anivix 聊天") 

聊天

Default

​ ​ ​

**真诚**、**友善**、**团结**、**专业**，共建你我引以为荣之社区。[《常见问题解答》](/faq)

[

❤️ 再忍不住，也不要做这种事啊 ❤️

](https://linux.do/t/topic/482293)

[年轻人的第一台 VPS 代理服务器](/t/topic/333976)


======================================

[资源荟萃](/c/resource/14)

[资源荟萃, Lv1](/c/resource/resource-lv1/83)

[软件开发](/tag/软件开发)

,[精华神帖](/tag/精华神帖)

您已选择 **0** 个帖子。

全选

取消选择

*   [免责声明](#p-3237872-h-1)

*   [实现的功能](#p-3237872-h-2)

*   [前期准备](#p-3237872-h-3)
    *   [购买域名](#p-3237872-h-4)
    *   [DNS 解析](#p-3237872-dns-5)
    *   [购买 VPS](#p-3237872-vps-6)
    *   [安装终端软件](#p-3237872-h-7)

*   [方案选择](#p-3237872-h-8)

*   [服务器购买](#p-3237872-h-9)

*   [整体框架](#p-3237872-h-10)

*   [服务器搭建](#p-3237872-h-11)
    *   [服务器 ssh 服务安全加固](#p-3237872-ssh-12)
        *   [安装常用软件](#p-3237872-h-13)
        *   [建立【非 root】的新用户](#p-3237872-root-14)
        *   [修改 ssh 登陆端口](#p-3237872-ssh-15)
        *   [禁用 root 用户 SSH 远程登录](#p-3237872-root-ssh-16)
        *   [SSH 启用 RSA 密钥验证登录](#p-3237872-ssh-rsa-17)
    *   [为你的域名申请 TLS 证书](#p-3237872-tls-18)
        *   [Cloudflare API](#p-3237872-cloudflare-api-19)
            *   [获取 Zone ID, Account ID](#p-3237872-zone-id-account-id-20)
            *   [获取 API Token](#p-3237872-api-token-21)
        *   [安装脚本](#p-3237872-h-22)
            *   [安装后的设置](#p-3237872-h-23)
        *   [使用 Cloudflare DNS 验证签发证书](#p-3237872-cloudflare-dns-24)
            *   [将 CA 服务器改成 Let’s Encrypt](#p-3237872-ca-lets-encrypt-25)
            *   [开始签发证书](#p-3237872-h-26)
            *   [验证自动续签](#p-3237872-h-27)
        *   [使用](#p-3237872-h-28)

*   [节点搭建](#p-3237872-h-29)
    *   [搭建和配置 hysteria2](#p-3237872-hysteria2-30)
        *   [官网脚本安装](#p-3237872-h-31)
        *   [非面板搭建的配置](#p-3237872-h-32)
            *   [服务器配置文件](#p-3237872-h-33)
            *   [端口跳跃](#p-3237872-h-34)
            *   [使用端配置](#p-3237872-h-37)
            *   [常用指令](#p-3237872-h-38)
            *   [流量统计 API](#p-3237872-api-39)
    *   [搭建缓解 TIT 特征的 vless+vision+tls](#p-3237872-tit-vlessvisiontls-40)
        *   [安装 x-ui 面板](#p-3237872-x-ui-41)
        *   [x-ui 面板](#p-3237872-x-ui-42)
        *   [x-ui 搭建配置](#p-3237872-x-ui-43)
        *   [使用端配置](#p-3237872-h-44)

*   [订阅服务搭建](#p-3237872-h-45)
    *   [安装组件](#p-3237872-h-46)
        *   [安装 FNM - Node 版本管理器](#p-3237872-fnm-node-47)
        *   [FNM 安装 Node](#p-3237872-fnm-node-48)
        *   [安装 PNPM 软件包管理器](#p-3237872-pnpm-49)
    *   [安装 Sub-Store](#p-3237872-sub-store-50)
        *   [创建文件夹并拉取项目](#p-3237872-h-51)
        *   [拉取项目并解压](#p-3237872-h-52)
        *   [创建系统服务](#p-3237872-h-53)

*   [Nginx](#p-3237872-nginx-54)
    *   [安装 Nginx](#p-3237872-nginx-55)
    *   [配置分流](#p-3237872-h-56)
    *   [配置 nginx stream 分流和 nginx server](#p-3237872-nginx-stream-nginx-server-57)
    *   [启动 nginx](#p-3237872-nginx-58)
    *   [访问服务](#p-3237872-h-59)
        *   [访问 SubStore](#p-3237872-substore-60)
        *   [访问 xui](#p-3237872-xui-61)
        *   [访问其他网址](#p-3237872-h-62)

*   [sub-store 的使用](#p-3237872-sub-store-63)

跳至结尾

时间线

​

[1月 9 日](/t/topic/333976/1 "跳到第一个帖子")

1 / 263

1月 9 日

返回

[4 天](/t/topic/333976/265)

热门回复 ​

时间线

[![](https://linux.do/user_avatar/linux.do/linglong/96/361243_2.png)
](/u/linglong)

[灵龙](/u/linglong)

[linglong](/u/linglong)一元复始

8

[1月 9 日](/t/topic/333976?u=niyan2025 "发布日期")

[](#p-3237872-h-1)免责声明
----------------------

本文涉及的任何解锁和解密分析脚本仅用于资源共享和学习研究，不能保证其合法性，准确性，完整性和有效性，请根据情况自行判断。

间接使用脚本的任何用户，包括但不限于建立VPS或在某些行为违反国家/地区法律或相关法规的情况下进行传播, 本文作者对于由此引起的任何隐私泄漏或其他后果概不负责。

请勿将本文内的任何内容用于商业或非法目的，否则后果自负。

如果任何单位或个人认为该项目的脚本可能涉嫌侵犯其权利，则应及时通知并提供身份证明，所有权证明，我将在收到认证文件后删除相关脚本。

对任何本文中包含的脚本在使用中可能出现的问题概不负责，包括但不限于由任何脚本错误导致的任何损失或损害．

您必须在下载后的24小时内从计算机或手机中完全删除以上内容。

任何以任何方式查看此项目的人或直接或间接使用该项目的任何脚本的使用者都应仔细阅读此声明。本文作者保留随时更改或补充此免责声明的权利。一旦使用并复制了任何本文相关脚本或其他内容，则视为您已接受此免责声明。

[](#p-3237872-h-2)实现的功能
-----------------------

1.  搭建一个稳定的代理服务器。
2.  提供便捷的订阅转换服务，便于分享节点信息。可供 3-4 人使用。
3.  能够访问 ChatGPT，VPS 的 IP 最好是原生 IP，访问一些特殊网站时不会被 block。
4.  提供的对外服务要够安全。例如，xray 面板需要以 TLS 加密访问，不能 http 裸奔在公网、SSH 服务更改端口，限制 root 用户登陆、节点使用当前较为安全的的协议等。
5.  有 IPV6，平时有使用 BT、 PT 的需求。

基于上述功能，本教程搭建的 VPS 有如下特点：

1.  选用原生 IP 的 VPS 提供商，价格在 20 刀一年左右。能解锁 GPT。
2.  购买域名，使用 cloudflare 解析 DNS，申请 TLS 证书，使得域名能够提供 https 安全访问。
3.  使用 nginx 分流、反代本服务器上的代理服务、订阅服务、伪装服务。
4.  使用 x-ui 面板搭建 vless+tls+vision 节点；搭建 hysteria2 节点。
5.  搭建 sub-store，提供前后端订阅转换、分享服务，提供第三方网盘、glist 同步服务。

本教程并非面向纯小白用户，如果你对基础的 Linux 命令不懂，对简单计算机网络知识不懂，建议不要尝试。如果你真的想尝试，并且愿意花时间学习，可以先购买机场，完成科学上网第一步。

在 youtube 上学习科学上网基本知识，推荐不良林：[www.youtube.com/@bulianglin](https://www.youtube.com/@bulianglin)

再结合 [Project X](https://xtls.github.io/)

项目的文档 [小小白白话文](https://xtls.github.io/document/level-0/ch01-preface.html)

对照阅读。遇到不明白的知识去问 GPT，大概率能得到一个清晰的答案；或者 google 搜索对应知识。

**本教程在 Linux 系统下完成。** 

[](#p-3237872-h-3)前期准备
----------------------

### [](#p-3237872-h-4)购买域名

域名一般都推荐 namesilo，购买一些便宜点的域名，例如 top，一年只要不到 2 美金，续费基本在 5 美金左右。如果嫌续费贵，大可以在到期以后，重新买一个便宜域名，然后再更新 DNS 解析，和节点信息。

[![](https://linux.do/uploads/default/optimized/4X/4/7/f/47fc1d922636e35f86e9133a04d8536e9c7a4a80_2_690x230.png)

image2030×677 64.9 KB

](https://linux.do/uploads/default/original/4X/4/7/f/47fc1d922636e35f86e9133a04d8536e9c7a4a80.png "image")

购买后需要将 DNS 服务换成 Cloudflare，参考：[Namesilo/Cloudflare 域名注册和解析设置教程](https://sarakale.top/blog/posts/3a730d01/)

，便于后续申请 TLS 证书。申请合法的 TLS 证书非常重要，避免你的 VPS 用 http 访问，数据裸奔在公网，指不定哪天就被黑了。

### [](#p-3237872-dns-5)DNS 解析

当你购买域名，并按照上述参考将域名解析托管到 clouflare 后，就可以设置 DNS 解析了。你可以设置无限多的三级域名，解析到不同的 IP，用作不同的用途。

需要注意，这里有一个代理状态栏，如果开启代理，则解析 DNS 时，会解析到 cloudflare 的 CDN IP，而不是自己设置的服务器 IP。该 CDN 会转发请求到服务器，但默认只会转发 443 端口的内容，不过你可以设置 Origin Rules 在 CDN 转发时，转发到服务器指定的端口上。

后续的节点搭建会要求设置不同的三级域名，解析到服务器 IP，以识别不同的服务。有一些不需要设置代理，有一些则需要设置代理以提高服务的安全性。

[![](https://linux.do/uploads/default/optimized/4X/a/c/7/ac728e159139c99892dc5bd95e2fb87d2b92138a_2_690x316.png)

image2340×1075 222 KB

](https://linux.do/uploads/default/original/4X/a/c/7/ac728e159139c99892dc5bd95e2fb87d2b92138a.png "image")

### [](#p-3237872-vps-6)购买 VPS

经典的 VPS 推荐环节，但由于咱们的情况特殊，一旦有人推荐一些好用的 VPS，或者可以薅羊毛的 VPS，不出多久，就会有大量的用户滥用，导致原有的用户体验下降，或者 IP 段被 GFW 特殊照顾。因此，不给出目前自用的 VPS 推荐。也不给 VPS **长期**购买建议。

补充：这个网站 [vpsIs](https://vpsls.com/docs/%E9%A6%96%E9%A1%B5/)

罗列了许多VPS 厂家，以及其目前的订购费用，可以按需自选。

此处仅仅列出一些目前比较有名的境外 VPS 厂家：

1.  BandwagonHost，板瓦工，国内出名的厂家，用的人很多，所以普通线路的质量可能会差点（没用过，仅供参考），C2N 线路的据说速度很快。IP 被封可以给钱换机器。普通机器 50​![](https://linux.do/images/emoji/twemoji/heavy_dollar_sign.png?v=12)
     一年，对于个人用户来说小贵。
2.  VULTR，小时计费，速度一般，可以用来练手，ip 被封可以直接删除实例，重开一台其他地方的机器。便宜的大概 6​![](https://linux.do/images/emoji/twemoji/heavy_dollar_sign.png?v=12)
    一月，也有 3、4​![](https://linux.do/images/emoji/twemoji/heavy_dollar_sign.png?v=12)
    一月的，但几乎买不到。
3.  RackNerd，最近两年好像很火，也属于便宜的那一档。
4.  CloudCone，了解不多。
5.  DMIT，了解不多。

除了费用、网络质量外，我们还需要关心：是否有 ipv6、是否支持 GPT 访问（网页端、移动端）。

IPV6 一般都会提供，不需要额外费用。

但是否支持 GPT 则是看 IP 是否“安全”。主要指的是 风控值，例如之前我在 vultr 购买的波兰服务器

[![](https://linux.do/uploads/default/optimized/4X/2/1/e/21e23102ea63261d01c2f625bc065e22d4dc3c0c_2_690x371.png)

image1506×810 54.3 KB

](https://linux.do/uploads/default/original/4X/2/1/e/21e23102ea63261d01c2f625bc065e22d4dc3c0c.png "image")

现在使用的机器

[![](https://linux.do/uploads/default/optimized/4X/8/e/c/8ec0a659e1ec9fb4c8e2e9157e9f8ee027354a2e_2_690x139.png)

image1467×296 17.1 KB

](https://linux.do/uploads/default/original/4X/8/e/c/8ec0a659e1ec9fb4c8e2e9157e9f8ee027354a2e.png "image")

所以，vultr 的波兰 VPS 只支持网页端访问，还会经常弹出 cloudflare 的人机验证。而现在的机器直接可以支持 app 访问。当然 GPT 是否能访问也根据地区有关，我没有仔细测试过，只是说明，在挑选 VPS 的时候尽可能的在网上搜索看看是否支持 GPT 的访问。

当然，如果你购买的机器不支持，也可以通过 warp 等手段解锁。

### [](#p-3237872-h-7)安装终端软件

如果你也用 Linux，可以略过这一步。

使用 windows 的用户推荐安装 termius（全平台可用），免费功能足够了。ssh 登陆，sftp 传输文件非常方便，并且 UI 很好看。其也有移动端 app，我有时会通过手机端登陆上服务器看看情况。

官网地址：[termius.com/](https://termius.com/)

[](#p-3237872-h-8)方案选择
----------------------

经过对目前主流的代理协议调查，决定同时搭建两种协议：hysteria2、vless+vision。前者基于 udp 传输、伪装成 http3 流量；后者则是为了解决 tls in tls 问题而推出的一种缓解该特征的方式。只能保证当前时刻，两者用来代理是稳定的。声明：没有最好的协议，只有最适合自己的协议。

在搭建上述两种协议时，涉及到 x-ui 面版和 nginx 的使用。为了使服务尽可能的稳定，x-ui 面板启用 https，而 hysteria2 需要在 80 和 443 端口进行伪装，所以要用 nginx 在 443 端口对 x-ui 流量和 hysteria2 的伪装流量分流。

除了代理服务，还有订阅服务。目前网络上主要两种：sub converter 和 sub-store。

sub converter 的官方支持较慢，例如：clash 原版删除跑路后，clash.meta 继续维护，但改动较大，截止目前 sub converter 官方版本仍未支持 meta 内核的新协议；在 hysteria2 出现 1 年后，其支持才被合并到官方主枝。但即使如此，并不影响其作为一款优秀的订阅转换工具，因为上述的兼容问题，有各种魔改版本来解决，比如 meta 内核官方自己基于 sub converter 开发了支持 meta 协议版本（[github.com/MetaCubeX/subconverter](https://github.com/MetaCubeX/subconverter)

）。还有一个重要的原因是，clash 系列、sing-box 等部分软件，配置文件不仅仅需要节点信息，还需要软件配置信息才能正常运行，sub converter 在转换时，可以同时给出配置信息。大部分的机场订阅都是使用 sub converter。例如，曾经使用的一个机场就是用免费的订阅转换工具 [sub.v1.mk](https://sub.v1.mk/)

来转换其搭建的 v2ray 节点。这里要注意：所有的订阅工具，都可以在后台看到你使用的节点转换信息。所以不能保证所有的搭建者都不去浏览抓换的节点信息。

sub-store 则更新维护比较及时，也有前后端界面，区别在于，sub-store 转换节点信息比较方便，但要转换 clash 系列、sing-box 等部分软件时麻烦一些。好处是 sub-store 有更为完善的数据保存同步功能，你可以把你的配置同步到 glist。

本教程采用 sub-store 来管理订阅。sub converter 我也做过尝试，但因为其订阅管理不够方便，仍然需要搭配 sub-store 来使用、转换 hysteria2 还有 passwd 不兼容问题，最终作罢。

下面是这些服务共存在一台服务器上时，使用 nginx 进行端口分流时拓扑图。

[![](https://linux.do/uploads/default/optimized/4X/a/8/e/a8e50f5f30f23e309c154f6511f4cff51629a9cb_2_690x349.png)

image852×432 29.8 KB

](https://linux.do/uploads/default/original/4X/a/8/e/a8e50f5f30f23e309c154f6511f4cff51629a9cb.png "image")

[](#p-3237872-h-9)服务器购买
-----------------------

当前服务器 20 ![](https://linux.do/images/emoji/twemoji/heavy_dollar_sign.png?v=12)
一年，原生 ip，支持 gpt 网页和移动端，不支持 Netflix 非自制剧。

使用 debian 12系统，ubuntu 的操作应该也类似。

[](#p-3237872-h-10)整体框架
-----------------------

搭建步骤分为几步：

1.  防火墙设置
2.  申请域名证书
3.  节点搭建-hysteria2
4.  节点搭建-vless+vision
5.  搭建 sub-store 服务
6.  Nginx 分流隐藏服务

[](#p-3237872-h-11)服务器搭建
------------------------

### [](#p-3237872-ssh-12)服务器 ssh 服务安全加固

购买服务器后，供应商会给 root 用户和密码，或者让你上传 ssh key，然后通过 ssh 访问服务器。

ssh 连接到服务器后，就可以对服务器的基础安全性进行加固。

#### [](#p-3237872-h-13)安装常用软件

```


`apt update && apt-get install -y curl vim ufw` 
```

后续会使用 curl 下载各种脚本，vim 编辑文件（不熟悉的可以替换为 nano），iptables-persistent 管理网络防火墙。  
注：部分 vps 提供商有自己的防火墙管理面板，仅仅在 vps 中更改可能不生效。吐槽一下甲骨文的 vps 面板是真的难用，试用了一下直接劝退。

#### [](#p-3237872-root-14)建立【非 root】的新用户

```


`apt list --upgradable apt update && apt-get install -y sudo
getent group 1001|| groupadd -g 1001 vps \
    && getent passwd username || useradd -ms /bin/bash -u 1001 -g 1001 -G sudo username \
    && echo "username:passwd" | chpasswd

echo "username ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers` 
```

上述命令的含义为：1. 安装 sudo，管理 root 权限。 2. 创建用户名为 username 的用户，密码为 passwd；并将其加入到 root 用户组，且使用 sudo 时不需要输入密码。

设置好后，另起一个终端，使用用户 username 登陆尝试一下是否建立成功。

注：上述用户名和密码请自行替换为自己的。后续同理。

#### [](#p-3237872-ssh-15)修改 ssh 登陆端口

注意命令执行顺序，先放行 ssh，再启动 ufw，并未验证 ufw 的默认配置会不会放行 ssh（虽说应该会考虑到），千万别把自己也挡在防火墙外了。

```


`sudo apt-get install ufw
sudo ufw allow ssh
sudo ufw enable

sudo ufw allow 1111
sudo vim /etc/ssh/sshd_config # 修改 PORT 为1111
sudo systemctl restart ssh` 
```

上述命令，编辑 ssh 配置文档 `/etc/ssh/sshd_config` 修改其访问端口为 1111，并使用 ufw 管理防火墙，放行 1111 端口。

注：自行修改为自己想用的端口。

#### [](#p-3237872-root-ssh-16)禁用 root 用户 SSH 远程登录

```


`vim /etc/ssh/sshd_config # PermitRootLogin yes 改为 no` 
```

#### [](#p-3237872-ssh-rsa-17)SSH 启用 RSA 密钥验证登录

参考：[使用-rsa-密钥登录并禁用密码登录](https://xtls.github.io/document/level-0/ch04-security.html#_4-7-%E4%BD%BF%E7%94%A8-rsa-%E5%AF%86%E9%92%A5%E7%99%BB%E5%BD%95%E5%B9%B6%E7%A6%81%E7%94%A8%E5%AF%86%E7%A0%81%E7%99%BB%E5%BD%95)

在**本机**上单独开启一个终端，执行下列操作，允许 VPS 服务器接受本机的 ssh 密钥登陆请求。

```


`ssh-keygen # 一路回车，在 ~/.ssh 目录下生成公钥和私钥
ssh-copy-id -p 1111 useranem@ip # 上传公钥到服务器` 
```

完成上述全部操作后，登陆 VPS，并禁用 22 端口

```


`ssh -p 1111 username@ip
sudo ufw deny 22` 
```

### [](#p-3237872-tls-18)为你的域名申请 TLS 证书

参考：[使用 acme.sh DNS 验证的方式签发 Let'sEncrypt 证书](https://blog.uuphy.com/posts/%E9%85%8D%E7%BD%AE-acme.sh-%E5%85%8D%E8%B4%B9%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%8F%91%E6%B3%9B%E5%9F%9F%E5%90%8D%E8%AF%81%E4%B9%A6/)

本教程后续依赖于有 tls 证书验证的域名，务必完成。

[acme.sh](https://acme.sh)

是一个用来自动获取和管理 SSL/TLS 证书的开源脚本，可以从 Let’s Encrypt 等多个 CA 获取免费的证书。结合使用 Cloudflare DNS 验证的模式申请泛域名证书，并自动续签。

在前面购买域名后，已经使用过 Cloudflare 解析域名到 VPS 服务器的 IP 地址了。下面还需要用 Cloudflare 帮助验证域名的有效性，结合 Let’sEncrypt 自动申请和续签证书。

#### [](#p-3237872-cloudflare-api-19)Cloudflare API

使用 Cloudflare DNS 模式需要准备:

1.  Zone ID
2.  Account ID
3.  API Token

##### [](#p-3237872-zone-id-account-id-20)获取 Zone ID, Account ID

这两种 ID 直接在 Overview 页就能找到。

[![](https://linux.do/uploads/default/optimized/4X/2/e/d/2edb816d28456e59ad4da2b02c3ff69450847554_2_690x370.png)

image2102×1130 171 KB

](https://linux.do/uploads/default/original/4X/2/e/d/2edb816d28456e59ad4da2b02c3ff69450847554.png "image")

##### [](#p-3237872-api-token-21)获取 API Token

Overview 页点击 `获取您的 API 令牌` 进入 API Tokens 页。

点击 API Tokens 项旁边 `创建令牌` 按钮，接着选择 `编辑区域 DNS` 的模板，点击 `使用模板`。

[![](https://linux.do/uploads/default/optimized/4X/e/1/5/e15d8a0a1de821faab5355e610b581016975b974_2_690x265.png)

image2093×805 60.6 KB

](https://linux.do/uploads/default/original/4X/e/1/5/e15d8a0a1de821faab5355e610b581016975b974.png "image")

[![](https://linux.do/uploads/default/optimized/4X/4/2/f/42f87595d27a6fb3ed1fe329934517f5416920c6_2_690x210.png)

image1623×495 43.8 KB

](https://linux.do/uploads/default/original/4X/4/2/f/42f87595d27a6fb3ed1fe329934517f5416920c6.png "image")

`区域资源` 里选择需要签发的域名

在 `客户端 IP 地址筛选` 里建议写下 acme.sh 所在的主机做为白名单，需要注意，如果服务器有 ipv6 地址，则也需要添加，因为有可能会 ipv6 优先访问。

击 `继续以显示摘要`, 确认没问题后最后点击 `创建令牌`。

[![](https://linux.do/uploads/default/optimized/4X/e/8/8/e88966d6049c27c31c632f9471ec1b79be287b59_2_510x499.png)

image1258×1231 87.4 KB

](https://linux.do/uploads/default/original/4X/e/8/8/e88966d6049c27c31c632f9471ec1b79be287b59.png "image")

此时就会出现一个 Token,，即 CF\_Token，拷贝备用。

[![](https://linux.do/uploads/default/optimized/4X/c/a/6/ca6093ea6bf83325809ea6179d4239ae2c9818cc_2_690x404.png)

image1061×622 46 KB

](https://linux.do/uploads/default/original/4X/c/a/6/ca6093ea6bf83325809ea6179d4239ae2c9818cc.png "image")

#### [](#p-3237872-h-22)安装脚本

后续申请证书的命令，都是在 root 用户下执行的，请先使用 `su` 切换到 root 用户。

安装脚本，设置 letsencrypt 为默认认证服务商，并设置邮箱用来接受 Let’s Encrypt 的邮件通知。安装时，acme 会自动的启动 cron 任务，每天检查是否需要续签证书。

```


`su # 进入root用户
curl https://get.acme.sh | sh -s email=name@gmail.com; apt install socat -y; ~/.acme.sh/acme.sh --set-default-ca --server letsencrypt` 
```

##### [](#p-3237872-h-23)安装后的设置

安装完毕后重新加载 bash，自动启用 acme 设置的环境变量，可以直接输入 acme.sh 而无需输入路径。

```


`source ~/.bashrc` 
```

开启自动更新

```


`acme.sh --upgrade --auto-upgrade` 
```

设置环境变量, 也就是准备的那三样, 可以准备好在一个文本编辑器里, 拷贝粘贴依次执行:

```


`export CF_Token="<拷贝的 API Token>"
export CF_Account_ID="<拷贝的 Account ID>"
export CF_Zone_ID="<拷贝的 Zone ID>"` 
```

#### [](#p-3237872-cloudflare-dns-24)使用 Cloudflare DNS 验证签发证书

##### [](#p-3237872-ca-lets-encrypt-25)将 CA 服务器改成 Let’s Encrypt

```


`acme.sh --set-default-ca --server letsencrypt` 
```

##### [](#p-3237872-h-26)开始签发证书

使用 DNS 的方式申请不需要放行 80 443 端口。

这里以 [hyperdns.com](http://hyperdns.com)

为例，-d 后面接上域名, 可以签发多个，这里签了二级域名(`hyperdns.com`) 和所有三级域名(`*.hyperdns.com`)

```


`acme.sh --issue --dns dns_cf -d hyperdns.com -d *.hyperdns.com` 
```

需要注意，如果出现错误，需要找到错误原因后，再进行下一步，否则错误次数过多，会触发 letsencrypt 速率限制，一段时间内将无法继续验证。（请注意，完整替换域名，这里演示的 .com 的一级域名，如果只改了一级域名，二级域名不对，将会一直验证，不会成功获取证书。一般的验证5分钟以内就可以完成，如果长时间都不成功，可能就是没有完整替换域名为你自己的域名）。

成功后，会给出证书的位置，一般位于 `~/.acme.sh/域名_ecc/`

```


`-----END CERTIFICATE-----
[Wed Dec 18 10:07:05 PM CST 2024] Your cert is in: /root/.acme.sh/hyperdns.com_ecc/hyperdns.com.cer
[Wed Dec 18 10:07:05 PM CST 2024] Your cert key is in: /root/.acme.sh/hyperdns.com_ecc/hyperdns.com.key
[Wed Dec 18 10:07:05 PM CST 2024] The intermediate CA cert is in: /root/.acme.sh/hyperdns.com_ecc/ca.cer
[Wed Dec 18 10:07:05 PM CST 2024] And the full-chain cert is in: /root/.acme.sh/hyperdns.com_ecc/fullchain.cer` 
```

也可以加上以下参数，指定生成的位置。

```


`acme.sh --issue --dns dns_cf -d hyperdns.com -d *.hyperdns.com          \
--cert-file      /path/to/certfile/in/apache/cert.pem             \
--key-file       /path/to/keyfile/in/apache/key.pem               \
--fullchain-file /path/to/fullchain/certfile/apache/fullchain.pem \` 
```

##### [](#p-3237872-h-27)验证自动续签

```


`$ crontab -l
23 9 * * * "/root/.acme.sh"/acme.sh --cron --home "/root/.acme.sh" > /dev/null` 
```

表示每天的上午9:23执行一次。检查是否需要更新证书。

手动执行：

```


`$ acme.sh --cron --home /root/.acme.sh
[Thu Dec 19 09:51:00 AM CST 2024] ===Starting cron===
[Thu Dec 19 09:51:00 AM CST 2024] Renewing: 'hex.hyperdns.com'
[Thu Dec 19 09:51:00 AM CST 2024] Renewing using Le_API=https://acme-v02.api.letsencrypt.org/directory
[Thu Dec 19 09:51:00 AM CST 2024] Skipping. Next renewal time is: 2025-02-08T09:00:33Z
[Thu Dec 19 09:51:00 AM CST 2024] Add '--force' to force renewal.
[Thu Dec 19 09:51:00 AM CST 2024] Skipped hex.hyperdns.com_ecc
[Thu Dec 19 09:51:00 AM CST 2024] Renewing: 'hyperdns.com'
[Thu Dec 19 09:51:00 AM CST 2024] Renewing using Le_API=https://acme-v02.api.letsencrypt.org/directory
[Thu Dec 19 09:51:00 AM CST 2024] Skipping. Next renewal time is: 2025-02-15T14:07:05Z
[Thu Dec 19 09:51:00 AM CST 2024] Add '--force' to force renewal.
[Thu Dec 19 09:51:00 AM CST 2024] Skipped hyperdns.com_ecc
[Thu Dec 19 09:51:00 AM CST 2024] ===End cron===` 
```

#### [](#p-3237872-h-28)使用

使用时，往往会要求填入证书和秘钥，这里注意，生成证书时，会有三种，在上述例子中，

*   **hyperdns.com.cer**：只有域名的叶子证书。
*   **ca.cer**：中间证书，用来构建完整的信任链。
*   **fullchain.cer**：由域名证书与中间证书组合而成的完整证书链文件，配置服务器时常用此文件以确保客户端能正确验证证书链。

通常，采用 **fullchain.cer** 作为网站证书的配置。密钥只有一个，例如：**hyperdns.com.key**，对应域名证书的私钥，直接输入就行。

该证书会作为 hysteria2、x-ui、nginx使用。

由于目前在 root 用户下操作，证书文件的权限仅 root 用户访问，因此需要修改。

```


`cp /root/.acme.sh/hyperdns.com_ecc/hyperdns.com.key /home/username/hyperdns.com.key
cp /root/.acme.sh/hyperdns.com_ecc/fullchain.cer /home/username/fullchain.cer
sudo chmod 644 /home/username/hyperdns.com.key
sudo chmod 644 /home/username/fullchain.cer` 
```

[](#p-3237872-h-29)节点搭建
-----------------------

**注意**：后续所有节点均使用的是三级域名，在 cloudflare 解析 DNS 时，都不勾选 代理。因为 hysteria2 和 vless+vision 都不支持 cdn。全部都是直连。但提供订阅或者面板访问的域名，需要打开代理，提高一些安全性。

### [](#p-3237872-hysteria2-30)搭建和配置 hysteria2

同样在root权限下完成。命令 `su`

#### [](#p-3237872-h-31)官网脚本安装

官网地址：[v2.hysteria.network/zh/](https://v2.hysteria.network/zh/)

，可查看其配置说明。

```


`bash <(curl -fsSL https://get.hy2.sh/)` 
```

如果出现

```


`$ bash <(curl -fsSL https://get.hy2.sh/)
Checking for installed version ... v2.6.0
Checking for latest version ... v2.6.0
Install /etc/hysteria/config.yaml ... exists
Creating user hysteria ... /dev/fd/63: line 1021: useradd: command not found` 
```

则是系统的 PATH 环境出现问题，可以执行 `export PATH=$PATH:/usr/sbin` 暂时缓解，如果希望永久解决，可以将 /usr/sbin 添加到 PATH 中，在系统的 shell 配置文件（例如 ~/.bashrc 或 ~/.profile）中加入如下行：

```


`export PATH=$PATH:/usr/sbin
# 然后执行以下命令来使更改生效：
source ~/.bashrc` 
```

**若域名没有 SSL 证书**，则可生成自签证书（但不推荐，相当于你没有任何验证，容易被中间人攻击）。或者购买域名（namesilo 域名购买 和 cloudflare 托管解析）。但如果经过前面的设置，就无需担心，已经拥有了正规的 SSL 证书。

自签证书申请（不建议使用）

注：需要切换到 root 用户

```


`su
openssl req -x509 -nodes -newkey ec:<(openssl ecparam -name prime256v1) -keyout /etc/hysteria/server.key -out /etc/hysteria/server.crt -subj "/CN=bing.com" -days 36500 && sudo chown hysteria /etc/hysteria/server.key && sudo chown hysteria /etc/hysteria/server.crt` 
```

#### [](#p-3237872-h-32)非面板搭建的配置

如果不使用面板搭建，则需要手动设置配置文件。

##### [](#p-3237872-h-33)服务器配置文件

hysteria2 支持 acme 通过 dns 方式申请证书，同样需要 `cloudflare_api_token`，但为了方便续签和其他服务使用证书，不采用这种方式。当然，即便你采用这种方式，也不会产生任何冲突和影响。

自行修改下面的配置中用户密码、trafficStats 端口/密码。

简单解释这个配置的含义：

1.  监听 8443 端口，该端口是建立 hysteria2 服务的基础。可以修改，但需要同时允许防火墙通过端口、修改客户端配置。
2.  tls 认证，配置自有域名的证书，以防止安全攻击。可以使用自签证书，但理论上并不安全，虽然大多数的小白教程都直接使用。如果完成本文前面的证书申请步骤，则这一步填入已有的证书即可。
3.  auth，权限验证，验证通过，才能够正常提供服务。支持多用户认证，每个用户使用 用户名+密码 的方式进行验证，适合小规模多用户使用。**需要注意：用户名不能含有大写字母。使用大写字母会连不上，目前已经确认这是一个 bug，后续版本会修复。Hysteria2 版本为 v2.6.0。** 
4.  masquerade，伪装，服务器像普通网站服务器一样真的响应 HTTP 请求，假装自己就是一个正常的网页服务器。
5.  trafficStats，流量统计接口
6.  bandwidth，带宽设置，不宜设置过大，造成流量浪费。

```


`cat << EOF > /etc/hysteria/config.yaml
listen: :8443 #监听端口

#使用 acme 证书，如果用cloudflare解析dns，并开启代理，则不需要申请，只填写域名即可
#acme:
#  domains:
#    - a.com #你的域名，需要先解析到服务器ip
#  email: test@sharklasers.com
#使用 acme 申请 CA 证书
#acme:
#  domains:
#    - "*.hyperdns.com"
#  email: your_email_address
#  type: dns
#  dns:
#    name: cloudflare
#    config:
#      cloudflare_api_token: your_api_token

#使用自签证书 或者已有 ca 证书
#ca 证书
tls:
  cert: /home/username/fullchain.cer
  key: /home/username/hyperdns.com.key
#使用自签证书
#tls:
#  cert: /etc/hysteria/server.crt
#  key: /etc/hysteria/server.key

auth:
  # 设置多用户
  type: userpass
  userpass:
    usr1: 8374393j4d
    usr2: t2rt9shd92

masquerade:
  type: proxy
  proxy:
    url: https://bing.com #伪装网址
    rewriteHost: true
  listenHTTP: :80
  listenHTTPS: :8443

trafficStats:
  listen: :22222
  secret: trafficStats_passwd

bandwidth:
  up: 20 mbps
  down: 50 mbps

EOF` 
```

最后，服务器端需要启动 hysteria2 server，并设置开机自启。

```


`systemctl enable hysteria-server.service --now` 
```

并运行命令：`systemctl status hysteria-server.service` 查看 hysteria 日志，观察是否启动成功。

如果没有启动成功，请查看具体的报错信息，并解决。可以查看 hysteria2 官网：[故障排除](https://v2.hysteria.network/zh/docs/advanced/Troubleshooting/)

。

##### [](#p-3237872-h-34)端口跳跃

参考：[hysteria2 端口跳跃](https://v2.hysteria.network/zh/docs/advanced/Port-Hopping/#__tabbed_1_1)

、[meta hysteria2配置](https://wiki.metacubex.one/config/proxies/hysteria2/)

运营商可能会阻断或限速 UDP 连接。表现为突然无法使用，或者网速慢，但几分钟（十几分钟）后又恢复。不过，这些限制往往仅限单个端口。端口跳跃可用作此情况的解决方法。

Hysteria 服务端并不能同时监听多个端口，因此不能在服务器端使用上面的格式作为监听地址。**建议配合 iptables 或 nftables 的 DNAT 将端口转发到服务器的监听端口。** 

```


`# IPv4
iptables -t nat -A PREROUTING -i eth0 -p udp --dport 20000:50000 -j REDIRECT --to-ports 443
# IPv6
ip6tables -t nat -A PREROUTING -i eth0 -p udp --dport 20000:50000 -j REDIRECT --to-ports 443` 
```

在这个示例中，服务器监听 443 端口，但客户端可以通过 20000-50000 范围内的任何端口连接。

对于本示例来说，没有放行这么多端口，只放行部分（端口号需要在 1000-65535），供参考：

```


`ufw allow 50220:50959/udp
ufw allow 60133:60968/udp
iptables -t nat -A PREROUTING -i eth0 -p udp --dport 50220:50959 -j REDIRECT --to-ports 8443
iptables -t nat -A PREROUTING -i eth0 -p udp --dport 60133:60968 -j REDIRECT --to-ports 8443
ip6tables -t nat -A PREROUTING -i eth0 -p udp --dport 50220:50959 -j REDIRECT --to-ports 8443
ip6tables -t nat -A PREROUTING -i eth0 -p udp --dport 60133:60968 -j REDIRECT --to-ports 8443` 
```

注意：有的 vps 中默认的网口并不是 eth0，请使用 `ifconfig` 或者 `ip addr` 找出真实的网卡名。

如果添加出错，需要删除规则，则可以参考：

###### [](#p-3237872-ufw-35)删除 ufw 规则

```


`ufw status numbered # 查看规则的编号
ufw delete 3 # 删除想删除的规则的编号` 
```

###### [](#p-3237872-iptables-36)删除改 iptables

列出当前的规则并找到规则的编号。使用以下命令列出规则：

```


`sudo iptables -L -v -n --line-numbers
sudo iptables -L -v -n -t nat # 查看添加的 nat 规则` 
```

这会输出规则列表，并在每个规则前面显示一个编号。假设你要删除编号为 2 的规则，可以执行：

```


`sudo iptables -D <链名> <规则编号>` 
```

例如，要删除 nat 表中的 PREROUTING 链上的第 2 条规则：

```


`sudo iptables -t nat -D PREROUTING 2` 
```

##### [](#p-3237872-h-37)使用端配置

clash.meta 为例，在配置文件中按照如下方式填写，yaml 格式。

```


`proxies:
  - name: "🇺🇸 Hysteria" # Hysteria2 不支持套用 CDN
    server: your_ip
    port: 8443
    ports: 50220-50959/60133-60968
    type: hysteria2
    password: usr1:8374393j4d # 多用户配置 用户名:密码
    up: 20
    down: 50
    sni: www.hyperdns.com
    skip-cert-verify: false` 
```

将上述节点信息，添加到已有的 clash 配置文件中，就可以看到节点，如果检测不通，则说明信息填写错误，请仔细检查，并确认 hysteria 服务器端成功启动。节点信息配置出错，或者与服务端不匹配，则无法连通。

填写参考：

server 填写服务器 ip 或者没有开启代理的域名。 hysteria 不支持cdn，开启代理会导致无法正常使用。如果使用域名，有可能会发生不稳定的情况，这时改回 ip 即可。

port 监听端口要和服务器一致。

ports 端口跳跃端口也要和服务器上开放的端口一致，保证服务器防火墙放行对应端口，并设置端口转发到监听端口。

密码 password 要正确，多用户需要注意格式要求，用户名和密码中间必须要有 `:` 但不能有空格。

sni 认证网址也要正确，需要和证书提供的一致。但这仅限于 tls 认证，只要该域名是证书中包含的域名即可。

##### [](#p-3237872-h-38)常用指令

```


`#启动Hysteria2
systemctl start hysteria-server.service
#重启Hysteria2
systemctl restart hysteria-server.service
#查看Hysteria2状态
systemctl status hysteria-server.service
#停止Hysteria2
systemctl stop hysteria-server.service
#设置开机自启
systemctl enable hysteria-server.service
#查看日志
journalctl -u hysteria-server.service` 
```

##### [](#p-3237872-api-39)流量统计 API

在服务端配置 `trafficStats` 后，可通过 HTTP API 查询服务器的==流量==统计信息，以及踢用户下线。

注：下述 api 都是 http，不安全。在后续使用 nginx 反代时，会更新为 https 访问方式。

```


`curl -H 'Authorization: trafficStats_passwd' http://ip_address:22222/traffic` 
```

bash 脚本

```


`#!/bin/bash
green='\033[0;32m'
cyan='\033[0;36m'
NC='\033[0m' # No Color

# 显示在线用户
echo "在线用户："
curl -H 'Authorization: trafficStats_passwd' http://ip_address:22222/online
echo
# 函数：将字节转换为可读格式
bytes_to_readable() {
    local bytes=$1
    if (( bytes < 1024 )); then
        printf "%d B" "$bytes"
    elif (( bytes < 1024**2 )); then
        printf "%.2f KB" "$(echo "scale=2; $bytes / 1024" | bc)"
    elif (( bytes < 1024**3 )); then
        printf "%.2f MB" "$(echo "scale=2; $bytes / (1024^2)" | bc)"
    else
        printf "%.2f GB" "$(echo "scale=2; $bytes / (1024^3)" | bc)"
    fi
}

# 设置URL和头部
URL="http://ip_address:22222/traffic"
AUTH_HEADER="Authorization: trafficStats_passwd"

# 发送GET请求并获取响应
response=$(curl -s -w "HTTPSTATUS:%{http_code}" -H "$AUTH_HEADER" "$URL")

# 提取body和状态码
body=$(echo "$response" | sed -e 's/HTTPSTATUS\:.*//g')
status_code=$(echo "$response" | tr -d '\n' | sed -e 's/.*HTTPSTATUS://')

if [ "$status_code" -eq 200 ]; then
    # 使用 jq 解析 JSON 并遍历每个键
    echo "$body" | jq -r 'to_entries[] | "\(.key) \(.value.tx) \(.value.rx)"' | while read -r key tx rx; do
        readable_tx=$(bytes_to_readable "$tx")
        readable_rx=$(bytes_to_readable "$rx")
        echo -e "$key: 上传 ${green}${readable_tx}${NC}, 下载${cyan}${readable_rx}${NC}"
    done
else
    echo "请求失败，状态码：$status_code"
fi` 
```

### [](#p-3237872-tit-vlessvisiontls-40)搭建缓解 TIT 特征的 vless+vision+tls

TIT 特征 TLS in TLS 是一种 TIS 传输 TLS 的特征，可能在某些地区能够被精确的识别和封禁。目前可以通过一些搭建方式来缓解。比如 naive 和 vision 通过字节填充来缓解 TIT。

参考：[搭建 VISION 节点](https://www.youtube.com/watch?v=SpxTFes1B8U&t=923s)

、[TIT 问题及解决方式](https://www.youtube.com/watch?v=Z_URro3bZqM&t=660s)

使用 x-ui 面板搭建节点，x-ui 是一个前端项目，负责通过 UI 界面配置节点参数，最终使用 xray 来搭建节点。

#### [](#p-3237872-x-ui-41)安装 x-ui 面板

x-ui 虽然提供了 docker 镜像，但是没有更新，且不好使用。还是直接安装比较合适。

```


`bash <(curl -Ls https://raw.githubusercontent.com/FranzKafkaYu/x-ui/956bf85bbac978d56c0e319c5fac2d6db7df9564/install.sh) 0.3.4.4` 
```

安装时，建议修改端口和账号用户与密码。

[![](https://linux.do/uploads/default/optimized/4X/0/b/2/0b243f11f9c9eb75e805ba86465db5d9c5422874_2_690x474.png)

image1167×802 129 KB

](https://linux.do/uploads/default/original/4X/0/b/2/0b243f11f9c9eb75e805ba86465db5d9c5422874.png "image")

需要防火墙放行自己设定的端口，假设设置的是 11080 端口。

安装后输入命令 `x-ui` 可以查看使用方式。

```


`root@LA:~# x-ui

  x-ui 面板管理脚本
  0. 退出脚本
————————————————
  1. 安装 x-ui
  2. 更新 x-ui
  3. 卸载 x-ui
————————————————
  4. 重置用户名密码
  5. 重置面板设置
  6. 设置面板端口
  7. 查看当前面板信息
————————————————
  8. 启动 x-ui
  9. 停止 x-ui
  10. 重启 x-ui
  11. 查看 x-ui 状态
  12. 查看 x-ui 日志
————————————————
  13. 设置 x-ui 开机自启
  14. 取消 x-ui 开机自启
————————————————
  15. 一键安装 bbr (最新内核)
  16. 一键申请SSL证书(acme申请)
  17. 配置x-ui定时任务
 
面板状态: 已运行
是否开机自启: 是
xray 状态: 运行

请输入选择 [0-17],查看面板登录信息请输入数字7:0` 
```

#### [](#p-3237872-x-ui-42)x-ui 面板

安装成功后，需要登陆面板进行操作。鉴于目前对 http 访问的安全风险很重视，在初次没有配置好 https 时，需要先用 ssh 隧道进行访问。

在本机上输入下列命令，让本机的 11080 端口和服务器的 11080 端口建立 ssh 隧道。

```


`ssh -L 11080:localhost:11080 user@serverip` 
```

在浏览器中输入 `http://localhost:port` 登陆 x-ui 面板，第一次登陆以后，点击面板设置，会自动更改根路径，后续登陆需要输入 `http://localhost:port/新根路径` 才能正常登陆。其中 port 在安装时由自己设置，本例子中为 11080。

```


`http://localhost:port/5I1Q/xui/` 
```

[![](https://linux.do/uploads/default/optimized/4X/7/f/8/7f895217f162927c0ca6e6e6c759461a21074647_2_690x401.png)

image1243×723 66.9 KB

](https://linux.do/uploads/default/original/4X/7/f/8/7f895217f162927c0ca6e6e6c759461a21074647.png "image")

但这种方式不要长期使用，当我们登入面板后，就应该立即去设置中，将 http 明文访问，升级为 https。

此处，填写已经申请到的 fullchain 证书，和密钥。保存后重启面板即可通过下面的网址访问

```


`https://ip:port/5I1Q` 
```

但这样访问，浏览器会提示不安全，因为 ip 并不符合证书中所认证的域名。所以，还需要在 cloudflare 中为 xui 面板单独设置一个三级域名单独用于访问 xui 面板，并且需要和后续的 nginx 分流配合起来，让访问 xui 域名的流量由 443 正确的分到 xui 端口。

否则就需要在 cloudflare 中配置 Origin Rules 将 cloudflare 前端代理的 443 端口流量自动的分流到服务器的对应端口，服务器也因此要开放 xui 端口，有暴露服务的风险。

#### [](#p-3237872-x-ui-43)x-ui 搭建配置

在面板添加节点。

[![](https://linux.do/uploads/default/optimized/4X/c/e/0/ce00ef2a75ef738235a2af1208185f36f3f1ae8e_2_690x456.png)

image1491×987 94.7 KB

](https://linux.do/uploads/default/original/4X/c/e/0/ce00ef2a75ef738235a2af1208185f36f3f1ae8e.png "image")

注：flow 在打开 4 和 5 后才会显示。

[![](https://linux.do/uploads/default/optimized/4X/7/4/7/747704caf61d70cde34876a48f85a79f2f4bfd6e_2_214x500.png)

image585×1361 107 KB

](https://linux.do/uploads/default/original/4X/7/4/7/747704caf61d70cde34876a48f85a79f2f4bfd6e.png "image")

还**需要防火墙放行 xray 的端口**。

其中**域名需要解析到服务器的ip地址**，**且 cloudflare 解析时，不能打开代理**。

#### [](#p-3237872-h-44)使用端配置

直接复制面板中提供的链接可以导入到小火箭，但是不能导入到 clash，clash 需要手动配置，或者用 sub-store 转换。这里还没有搭建 sub-store，则手动填写。

clash 端

```


`proxies:
  - name: "🇺🇸 vless"
    type: vless
    server: hvl.hyperdns.com # 解析到真实ip，不套用 CDN
    port: 58505
    udp: true
    uuid: c19119d6-796d-4c4b-add6-8392jeusisk
    flow: xtls-rprx-vision
    packet-encoding: xudp
    tls: true
    servername: hvl.hyperdns.com
    alpn:
      - h2
      - http/1.1
    client-fingerprint: chrome
    skip-cert-verify: false
    network: tcp
    smux:
      enabled: false` 
```

上述节点导入后就可以正常访问了。

[](#p-3237872-h-45)订阅服务搭建
-------------------------

参考：[通过VPS架设Sub-Store(新版)](https://surge.tel/08/2930/)

、[SubStore 部署](https://wiki.repcz.link/substore/install/#_1)

Sub-Store 项目分为前后端，前后端是分离的，部署在 VPS 上则需要前后端都部署，并且需要在前端访问之前套一个 Nginx，否则传输的都是 http 流量，不安全。部署后，可以在任意前端设置后端 api，即可使用。因此，在 mihomo-party 中，可以输入后端 api，以支持节点分享。

### [](#p-3237872-h-46)安装组件

同样先进入 `su`。

```


`apt update -y && apt install unzip curl wget git -y` 
```

#### [](#p-3237872-fnm-node-47)安装 FNM - Node 版本管理器

```


`$ curl -fsSL https://fnm.vercel.app/install | bash
...
In order to apply the changes, open a new terminal or run the following command:
  source /root/.bashrc` 
```

按照回显的图示，运行命令保存生效

```


`source /root/.bashrc  #请按照你的回显提示命令进行输入` 
```

#### [](#p-3237872-fnm-node-48)FNM 安装 Node

```


`fnm install v20.18.0` 
```

可以安装其他版本，但是后续服务配置文件需要同步修改版本。

#### [](#p-3237872-pnpm-49)安装 PNPM 软件包管理器

```


`curl -fsSL https://get.pnpm.io/install.sh | sh -` 
```

按照回显的图示，运行命令

```


`source /root/.bashrc` 
```

### [](#p-3237872-sub-store-50)安装 Sub-Store

#### [](#p-3237872-h-51)创建文件夹并拉取项目

```


`mkdir -p /root/sub-store  #在 root 目录下面创建 sub-store 文件夹
cd /root/sub-store   #进入 sub-store 文件夹` 
```

#### [](#p-3237872-h-52)拉取项目并解压

```


`# 拉取后端项目
curl -fsSL https://github.com/sub-store-org/Sub-Store/releases/latest/download/sub-store.bundle.js -o sub-store.bundle.js
 
# 拉取前端项目
curl -fsSL https://github.com/sub-store-org/Sub-Store-Front-End/releases/latest/download/dist.zip -o dist.zip` 
```

解压前端文件，并改名为 frontend，而后删除源压缩文件

```


`unzip dist.zip && mv dist frontend && rm dist.zip` 
```

#### [](#p-3237872-h-53)创建系统服务

pm2 的启动方式会有 BUG，所以我们采用服务进程的方式来启动

进入 VPS 目录 `/etc/systemd/system/`，在里面创建一个文件 `sub-store.service`，

`vim /etc/systemd/system/sub-store.service`

写入以下服务信息

```


`[Unit]
Description=Sub-Store
After=network-online.target
Wants=network-online.target systemd-networkd-wait-online.service
 
[Service]
LimitNOFILE=32767
Type=simple
Environment="SUB_STORE_FRONTEND_BACKEND_PATH=/2cXaAxRGfddmGz2yx1wA"
Environment="SUB_STORE_BACKEND_CRON=0 0 * * *"
Environment="SUB_STORE_FRONTEND_PATH=/root/sub-store/frontend"
Environment="SUB_STORE_FRONTEND_HOST=0.0.0.0"
Environment="SUB_STORE_FRONTEND_PORT=3001"
Environment="SUB_STORE_DATA_BASE_PATH=/root/sub-store"
Environment="SUB_STORE_BACKEND_API_HOST=127.0.0.1"
Environment="SUB_STORE_BACKEND_API_PORT=3000"
ExecStart=/root/.local/share/fnm/fnm exec --using v20.18.0 node /root/sub-store/sub-store.bundle.js
User=root
Group=root
Restart=on-failure
RestartSec=5s
ExecStartPre=/bin/sh -c ulimit -n 51200
StandardOutput=journal
StandardError=journal
 
[Install]
WantedBy=multi-user.target` 
```

上面服务代码中的 `2cXaAxRGfddmGz2yx1wA` 为API请求密钥，请自行修改，推荐自动生成地址：[点击访问](https://1password.com/zh-cn/password-generator)

启动服务，并设置开机自启。如果前面 fnm 安装 nodo 时，不是版本 v20.18.0，这里需要同步修改，否则执行不成功。

```


`systemctl enable sub-store.service --now` 
```

后端服务相关命令

```


`systemctl start sub-store.service     #启动服务
systemctl enable sub-store.service    #设置为开机自启
systemctl status sub-store.service    #查看服务状态
systemctl stop sub-store.service      #停止服务
systemctl restart sub-store.service   #重启服务` 
```

正常情况下，运行服务状态，应该类似下图：（ `active:running` ）

[![](https://linux.do/uploads/default/optimized/4X/4/e/1/4e1db5a1dc5d952406e6c0c1d1707b7dee1ce2ac_2_690x132.png)

image1315×253 46.9 KB

](https://linux.do/uploads/default/original/4X/4/e/1/4e1db5a1dc5d952406e6c0c1d1707b7dee1ce2ac.png "image")

[](#p-3237872-nginx-54)Nginx
----------------------------

前面搭建面板、订阅服务时，都需要在访问时，加上对应的端口号，如果暴露在公网，有安全风险。可以通过搭建 Nginx 服务，对外只暴露 443 80 端口，将 443 加密流量在 Nginx 内部分流到不同的本地端口，本地端口不需要暴露。就解决了这个问题。

### [](#p-3237872-nginx-55)安装 Nginx

```


`sudo apt install libnginx-mod-stream nginx -y` 
```

### [](#p-3237872-h-56)配置分流

在我的主机上，同时存在 `x-ui面板`、`hysteria2`，因此，希望 `sub-store` 可以和其他两个服务共存。且 `hysteria2` 伪装需要监听 80 443 端口，普通的 https 网络访问，也需要直接访问 443 端口。

在拥有一个有 ssl 认证的域名，一台可用服务器时，有两种解决方式：

1.  通过 Cloudfalre 设置 Origin Rules，根据不同的 访问域名，将服务转发到不同的端口。例如：`hysteria2` 仍然监听 80，443端口，`x-ui面板` 设置访问端口 81，`sub-store`设置访问端口 82。然后 Cloudfalre 中将访问 [sub.name.com](http://sub.name.com)
    
    的 https 流量转发到服务器的 82 端口，访问 [xui.name.com](http://xui.name.com)
    
    的 https 流量转发到服务器的 81 端口，普通流量不管，自动转发到服务器的 80，443。但由于 sub-store 不支持 https 流量，所以还是需要设置 nginx 服务器，将 https 流量解析并代理成 http 流量到 sub-store 端口。
    
2.  设置 nginx 反代服务，开放 443，80，8443端口。xui、sub-store 的网络访问都走 443，hysteria 监听 80 和 8443，hysteria 代理端口也为 8443。ngnix 将流量从 443 分流到 xui、sub-store、hysteria各自的端口上。当通过 https 协议访问 443 时，xui、sub-store分流到各自端口，其余流量全部分流到 8443，这部分流量被重定向到伪装站，而符合 hysteria 代理流量会直接访问 8443，不走 nginx 分流。
    
    示意图如下：
    

[![](https://linux.do/uploads/default/optimized/4X/a/8/e/a8e50f5f30f23e309c154f6511f4cff51629a9cb_2_690x349.png)

image852×432 29.8 KB

](https://linux.do/uploads/default/original/4X/a/8/e/a8e50f5f30f23e309c154f6511f4cff51629a9cb.png "image")

因为一定需要 nginx 作反代，所以，采用第二种方式。

### [](#p-3237872-nginx-stream-nginx-server-57)配置 nginx stream 分流和 nginx server

在 `/etc/nginx/nginx.conf` 中的 http 块外部分，也就是顶层配置下，加入 `include /etc/nginx/vps.conf;`，并删除 `/etc/nginx/sites-enabled` 下的基础配置。

```


`# /etc/nginx/nginx.conf
user www-data;
worker_processes auto;
pid /run/nginx.pid;
error_log /var/log/nginx/error.log;
include /etc/nginx/modules-enabled/*.conf;

events {
	worker_connections 768;
	# multi_accept on;
}

http {
	sendfile on;
	tcp_nopush on;
	types_hash_max_size 2048;

	include /etc/nginx/mime.types;
	default_type application/octet-stream;

	ssl_protocols TLSv1 TLSv1.1 TLSv1.2 TLSv1.3; # Dropping SSLv3, ref: POODLE
	ssl_prefer_server_ciphers on;

	access_log /var/log/nginx/access.log;
	gzip on;

	include /etc/nginx/conf.d/*.conf;
	include /etc/nginx/sites-enabled/*;
}

include /etc/nginx/vps.conf;` 
```

在 `/etc/nginx` 下创建文件 `vps.conf`，并填入下列分流规则：

1.  根据域名分流将 443 端口的 https 流量分流到不同的后端。其中 xui 本身支持 https，不需要对 https 解密再转发。而 substore 目前只支持 http，所以需要将 sub 流量转发到 nginx server，由 nginx server 解密再转发到 sub 的端口。除此之外的流量，都转发到 hysteria 的伪装端口。
2.  后续会在 /etc/nginx/sites-enabled/vps.conf 中为 substore 配置一个 nginx 反代服务，其监听的是 8444 端口，因此这里需要将 sub 对应的流量分流至 8444。
3.  xui 端口为 11080，这在 xui 面板搭建一节中提到过，是用户安装时自行设置的。
4.  hysteria 则是在配置文件中设置了伪装服务端口为 8443。

```


`# /etc/nginx/vps.conf

stream {
    # 定义一个映射，将 SNI 中的服务器名映射到后端标识符
    map $ssl_preread_server_name $backend {
        hostnames;
        sub.xyz.top sub;
        xui.xyz.top xui;
        default hysteria;  # 默认后端
    }

    # 定义各个后端的上游服务器
    upstream sub {
        server 127.0.0.1:8444;  # sub.xyz.top 对应的后端，对接的是 nginx server
    }

    upstream xui {
        server 127.0.0.1:11080;  # xui.xyz.top 对应的后端
    }

    upstream hysteria {
        server 127.0.0.1:8443;  # 默认后端
    }

    # 定义一个服务器块，监听指定端口并根据 SNI 分发流量
    server {
        listen 443;
        listen [::]:443;
        proxy_pass $backend;
        ssl_preread on;
    }
}` 
```

然后需要设置 sub-store 的 server 反代并部署 SSL 证书用于 tls 认证，解密 https 流量。

```


`# /etc/nginx/sites-enabled/vps.conf

server {
    listen 8444 ssl http2;
    listen [::]:8444 ssl http2;
    server_name sub.xyz.top;
 
    ssl_certificate /root/.acme.sh/xyz.top_ecc/fullchain.cer;
    ssl_certificate_key /root/.acme.sh/xyz.top_ecc/xyz.top.key;
 
    location / {
        proxy_pass http://127.0.0.1:3001;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}` 
```

### [](#p-3237872-nginx-58)启动 nginx

移除默认的配置文件：`sudo rm /etc/nginx/sites-enabled/default`。如果 `/etc/nginx/sites-enabled` 有其他的配置文件，都会被 nginx 启动，因此为了防止冲突，需要移除。

```


`sudo nginx -t # 检测配置是否正确
sudo systemctl restart nginx
sudo nginx -s reload # 重新启动 nginx` 
```

如果出现下列错误 `unknown directive "stream"`，则是缺少 stream 的支持库，安装即可 `sudo apt install libnginx-mod-stream`。这可能是由于 nginx v20.18.0 版本较低，v22.13.0 版本没有该问题。

```


`$ sudo nginx -t
2024/12/19 16:53:58 [emerg] 1424878#1424878: unknown directive "stream" in /etc/nginx/vps.conf:2
nginx: configuration file /etc/nginx/nginx.conf test failed` 
```

### [](#p-3237872-h-59)访问服务

在搭建好 nginx 反代后，就可以通过域名直接用 https 访问对应的服务了，不需要像之前一样，输入 ip+端口号的形式来访问。大大提高了安全性和易用性。

#### [](#p-3237872-substore-60)访问 SubStore

设置好后，SubStore 地址为：`https://sub.xyz.top`

其后端 API 为（可以在 mihomo-party 中添加），也可以直接在前端的设置中填入。

```


`https://sub.xyz.top/2cXaAxRGfddmGz2yx1wA` 
```

浏览器访问带有后端功能的前端，输入

```


`https://sub.xyz.top?api=https://sub.xyz.top/2cXaAxRGfddmGz2yx1wA` 
```

或者访问前端，在设置中，保存后端的 api。

#### [](#p-3237872-xui-61)访问 xui

首先在 cloudflare 中，设置一个三级域名，并解析到服务器 ip，且关闭代理。

假设三级域名是：[xui.hyperds.com](http://xui.hyperds.com)

，则现在可以通过

```


`https://xui.hyperds.com/5I1Q` 
```

直接访问。

#### [](#p-3237872-h-62)访问其他网址

除了上述 xui、sub以外的域名，都会被发送到 hysteria 伪装端口，返回的就是伪装的网站。

[](#p-3237872-sub-store-63)sub-store 的使用
----------------------------------------

我在另一个贴子中有详细介绍：[节点的订阅管理\\分享-我的方案](https://linux.do/t/topic/333959/3)

  

9 个回复

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

+1

![](https://linux.do/images/emoji/twemoji/clap.png?v=14)

clap

![](https://linux.do/images/emoji/twemoji/open_mouth.png?v=14)

open\_mouth

![](https://linux.do/images/emoji/twemoji/hugs.png?v=14)

hugs

![](https://linux.do/images/emoji/twemoji/laughing.png?v=14)

laughing

565

​ ​ 回复

*   [claw7刀年抛![](https://linux.do/images/emoji/twemoji/chicken.png?v=14)
    很香](https://linux.do/t/topic/334031/106)
    
*   [年轻人的第一台VPS：Reality 节点搭建](https://linux.do/t/topic/357522)
    
*   [佬们 推荐个机场![](https://linux.do/images/emoji/twemoji/airplane.png?v=14)
    ](https://linux.do/t/topic/469964/20)
    
*   [请问下CF挂载的域名怎么开启https访问](https://linux.do/t/topic/399942/8)
    
*   [这段时间，连国外dns都不让用了](https://linux.do/t/topic/470895)
    
*   其他 1 个

9.3k 浏览量 766 赞 34 链接 199 用户

 [![](https://linux.do/user_avatar/linux.do/linglong/96/361243_2.png)
 36](/u/linglong "linglong") 

 [![](https://linux.do/user_avatar/linux.do/janzhang/96/303594_2.png)
 10](/u/JanZhang "JanZhang")

 [![](https://linux.do/user_avatar/linux.do/ajun0/96/366485_2.png)
 6](/u/ajun0 "ajun0") 

 [![](https://linux.do/user_avatar/linux.do/leileio/96/401878_2.png)
 4](/u/leileio "leileio")

 [![](https://linux.do/user_avatar/linux.do/carlxu/96/23722_2.png)
 3](/u/carlxu "carlxu")

阅读时间 18 分钟

热门回复

总结

[![](https://linux.do/user_avatar/linux.do/idkbungle/96/127267_2.png)
](/u/idkbungle)

[IDK bungle](/u/idkbungle)

指导顾问 ![](https://linux.do/images/emoji/twemoji/innocent.png?v=14) 

[1月 9 日](/t/topic/333976/2?u=niyan2025 "发布日期")

tql ![](https://linux.do/images/emoji/twemoji/clap.png?v=12)

  

1 个回复

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

+1

18

​ ​ 回复

*   [节点的订阅管理\\分享-我的方案](https://linux.do/t/topic/333959/11)
    

[![](https://linux.do/user_avatar/linux.do/master2/96/306197_2.png)
](/u/Master2)

[Master2](/u/Master2)

圆圆满满 ![](https://linux.do/uploads/default/original/3X/7/a/7aef4ea958cf8bca18d453f2fbc3094911a61014.png?v=14) 

[1月 9 日](/t/topic/333976/3?u=niyan2025 "发布日期")

你这基本上，一套组合拳，够小白琢磨半个月的 ![](https://linux.do/images/emoji/twemoji/rofl.png?v=12)

  

1 个回复

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

+1

![](https://linux.do/images/emoji/twemoji/laughing.png?v=14)

laughing

19

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/linglong/96/361243_2.png)
](/u/linglong)

[灵龙](/u/linglong)

[linglong](/u/linglong)一元复始

 ![](https://linux.do/user_avatar/linux.do/master2/48/306197_2.png)
 Master2

[1月 9 日](/t/topic/333976/4?u=niyan2025 "发布日期")

哈哈，我自己也是琢磨了一段时间，学了很多知识。觉得应该分享一下，要不然东拼西凑的，也很麻烦

  

1 个回复

9

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/master2/96/306197_2.png)
](/u/Master2)

[Master2](/u/Master2)

圆圆满满 ![](https://linux.do/uploads/default/original/3X/7/a/7aef4ea958cf8bca18d453f2fbc3094911a61014.png?v=14) 

 ![](https://linux.do/user_avatar/linux.do/linglong/48/361243_2.png)
 灵龙

[1月 9 日](/t/topic/333976/6?u=niyan2025 "发布日期")

不良林，几年前我也是看他的视频学的 ![](https://linux.do/uploads/default/original/3X/2/e/2e09f3a3c7b27eacbabe9e9614b06b88d5b06343.png?v=12)
，几年后，还是他， ![](https://linux.do/images/emoji/twemoji/rofl.png?v=12)
，真:人生导师了 ![](https://linux.do/uploads/default/original/3X/1/1/112287dceadcb6ce1cf59a17989b159a87c754df.png?v=12)

  

2 个回复

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://linux.do/images/emoji/twemoji/laughing.png?v=14)

laughing

11

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/kkzeroc/96/349893_2.png)
](/u/kkzeroc)

[莫欧](/u/kkzeroc)

[kkzeroc](/u/kkzeroc)

[1月 9 日](/t/topic/333976/7?u=niyan2025 "发布日期")

强啊强啊，只是码这么多字就已经很强了

  

7

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/wwow/96/343939_2.png)
](/u/wwow)

[樱悦](/u/wwow)

[wwow](/u/wwow)文化宣导员 ![](https://linux.do/images/emoji/twemoji/heartpulse.png?v=14) 

[1月 9 日](/t/topic/333976/8?u=niyan2025 "发布日期")

好长啊，我慢慢看

  

8

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/ehzyil/96/46547_2.png)
](/u/ehzyil)

[ehzyil](/u/ehzyil)

浴火重生

[1月 9 日](/t/topic/333976/9?u=niyan2025 "发布日期")

感谢大佬分享 地铁上看了三分之一 mark一下

  

2 个回复

8

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/_dianavavaava/96/9927_2.png)
](/u/_DianAvavaAvA)

[蒲君瑶](/u/_DianAvavaAvA)

[\_DianAvavaAvA](/u/_DianAvavaAvA)大预言家 ![](https://linux.do/uploads/default/original/3X/5/9/596da26825d2a806bd1952b5231f24d212866c1b.png?v=14) 

[1月 9 日](/t/topic/333976/10?u=niyan2025 "发布日期")

666666666666666666666666眼都不演了

  

6

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/linglong/96/361243_2.png)
](/u/linglong)

[灵龙](/u/linglong)

[linglong](/u/linglong)一元复始

 ![](https://linux.do/user_avatar/linux.do/master2/48/306197_2.png)
 Master2

[1月 9 日](/t/topic/333976/11?u=niyan2025 "发布日期")

是啊，不过他的教程比较简单，学习基础知识是可以的。再往上折腾，就很难找到比较好的教程了

  

7

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/linglong/96/361243_2.png)
](/u/linglong)

[灵龙](/u/linglong)

[linglong](/u/linglong)一元复始

 ![](https://linux.do/user_avatar/linux.do/ehzyil/48/46547_2.png)
 ehzyil

[1月 9 日](/t/topic/333976/12?u=niyan2025 "发布日期")

哈哈，很高兴被认可。有任何问题都可以提出来，我再修改

  

7

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/handsome/96/477777_2.png)
](/u/handsome)

[大帅哥](/u/handsome)

[handsome](/u/handsome)种子用户 ![](https://linux.do/images/emoji/twemoji/rage.png?v=14) 

[1月 9 日](/t/topic/333976/13?u=niyan2025 "发布日期")

太强了！

  

10

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/ptnxzh_laii/96/325972_2.png)
](/u/Ptnxzh_Laii)

[Ptnxzh\_Laii](/u/Ptnxzh_Laii)

种子用户 ![](https://linux.do/images/emoji/twemoji/sandwich.png?v=14) 

[1月 9 日](/t/topic/333976/14?u=niyan2025 "发布日期")

非常有用的喂饭教程 ![](https://linux.do/uploads/default/original/3X/5/1/512220c3e65ba0f1f7334cfa5aac923a2d9e95e4.png?v=12)

  

7

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/hnres/96/398754_2.png)
](/u/hnres)

[mew](/u/hnres)

[hnres](/u/hnres)

[1月 9 日](/t/topic/333976/15?u=niyan2025 "发布日期")

![](https://linux.do/user_avatar/linux.do/linglong/48/361243_2.png)
 灵龙:

> 都会被发送到 hysteria 伪装端口，返回的就

这么长的没

  

7

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/pengzhile/96/305997_2.png)
](/u/pengzhile)

[卡尔 · 马克思](/u/pengzhile)

[pengzhile](/u/pengzhile)解决方案机构

[1月 9 日](/t/topic/333976/16?u=niyan2025 "发布日期")

大家都是不良林入门的

  

8

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/normal/96/36086_2.png)
](/u/normal)

[平平无奇的菜鸡](/u/normal)

[normal](/u/normal)浴火重生 ![](https://linux.do/uploads/default/original/3X/2/e/2e09f3a3c7b27eacbabe9e9614b06b88d5b06343.png?v=14) 

[1月 9 日](/t/topic/333976/17?u=niyan2025 "发布日期")

太专业了佬

  

6

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/longuet/96/18124_2.png)
](/u/Longuet)

[Josh](/u/Longuet)

[Longuet](/u/Longuet)种子用户

[1月 9 日](/t/topic/333976/18?u=niyan2025 "发布日期")

![](https://linux.do/user_avatar/linux.do/linglong/48/361243_2.png)
 灵龙:

> 推荐 namesoil

错别字啦佬友  
内容好评

  

1 个回复

6

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/k452b/96/52426_2.png)
](/u/k452b)

[干啥啥不行](/u/k452b)

[k452b](/u/k452b)浴火重生 ![](https://linux.do/images/emoji/twemoji/medal_military.png?v=14) 

[1月 9 日](/t/topic/333976/19?u=niyan2025 "发布日期")

哥们， 你这写的也太详细了。

  

6

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/linglong/96/361243_2.png)
](/u/linglong)

[灵龙](/u/linglong)

[linglong](/u/linglong)一元复始

 ![](https://linux.do/user_avatar/linux.do/longuet/48/18124_2.png)
 Josh

[1月 9 日](/t/topic/333976/20?u=niyan2025 "发布日期")

马上改！

  

5

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/4396/96/305781_2.png)
](/u/4396)

[4396](/u/4396)

指导顾问

[1月 9 日](/t/topic/333976/21?u=niyan2025 "发布日期")

20刀 什么配置啊  
另外，建议插入一个目录

  

1 个回复

5

​ ​ 回复

Invalid date Invalid date

Settings
========

🏷️ UTags - Add usertags to links

Other Extensions
----------------

[🔗 Links Helper](https://greasyfork.org/en/scripts/464541-links-helper)

[V2EX.REP - 专注提升 V2EX 主题回复浏览体验](https://greasyfork.org/en/scripts/466589-v2ex-rep-%E4%B8%93%E6%B3%A8%E6%8F%90%E5%8D%87-v2ex-%E4%B8%BB%E9%A2%98%E5%9B%9E%E5%A4%8D%E6%B5%8F%E8%A7%88%E4%BD%93%E9%AA%8C)

[v2ex.min - V2EX Minimalist (极简风格)](https://greasyfork.org/en/scripts/463552-v2ex-min-v2ex-%E6%9E%81%E7%AE%80%E9%A3%8E%E6%A0%BC)

[Replace Ugly Avatars](https://greasyfork.org/en/scripts/472616-replace-ugly-avatars)

↑↓⇔⇧⇩