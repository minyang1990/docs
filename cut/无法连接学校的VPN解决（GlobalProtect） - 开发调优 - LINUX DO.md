# 无法连接学校的VPN解决（GlobalProtect） - 开发调优 - LINUX DO
 无法连接学校的VPN解决（GlobalProtect） - 开发调优 - LINUX DO                                              

[跳到主要内容](#main-container)

 [![](https://linux.do/uploads/default/original/3X/9/d/9dd49731091ce8656e94433a26a3ef36062b3994.png)](/) 

[无法连接学校的VPN解决（GlobalProtect）](/t/topic/218449)
==============================================

[开发调优](/c/develop/4)

[计算机网络](/tag/计算机网络)

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

[无法连接学校的VPN解决（GlobalProtect）](/t/topic/218449)
==============================================

[开发调优](/c/develop/4)

[计算机网络](/tag/计算机网络)

您已选择 **0** 个帖子。

全选

取消选择

​

[2024 年 9月](/t/topic/218449/1 "跳到第一个帖子")

1 / 33

2024 年 9月

[2024 年 12月](/t/topic/218449/34)

[![](https://linux.do/user_avatar/linux.do/zcw/96/333203_2.png)
](/u/zcw)

[欲天](/u/zcw)[zcw](/u/zcw)一元复始

3

[2024 年 9月](/t/topic/218449?u=niyan2025 "发布日期")

_**仅限于GlobalProtect**_  
GlobalProtect连接之后，IP还是没有改变那么有可能是网关优先级的问题。  
win是bat运行需要管理员权限  
mac是sh运行需要管理员权限  
切记只要您更换了网络就需要重新运行（也可能是我电脑的问题）  

[![](https://linux.do/uploads/default/optimized/3X/4/d/4dd6155e79d5a9c32654b47498f91964714f1d74_2_690x492.png)

image869×620 87.9 KB

](https://linux.do/uploads/default/original/3X/4/d/4dd6155e79d5a9c32654b47498f91964714f1d74.png "image")

软件连接成功之后再运行以下代码  
_**win系统代码**_  
_注：可以输入多个IP如果您有多个学校的话需要加个空格_

```


`@echo off

:: 设置多个网关，使用空格分隔
set gateways=替换成您的IPV4 如果有多个VPN

set success=0
for %%i in (%gateways%) do (
    if %success% equ 0 (
        route delete 0.0.0.0 mask 0.0.0.0
        route add 0.0.0.0 mask 0.0.0.0 %%i metric 1
        if not errorlevel 1 (
            set success=1
        )
    )
)` 
```

_**mac代码**_  
_注：理论上和win系统一样但是没有尝试，自行解决_

```


`#!/bin/bash

# 设置多个网关，使用空格分隔
gateways=("替换成您的IPV4" "如果有多个VPN")

success=0

for gateway in "${gateways[@]}"; do
    if [ "$success" -eq 0 ]; then
        # 删除默认路由
        sudo route -n delete default &> /dev/null
        
        # 添加新的默认路由
        sudo route -n add default "$gateway" &> /dev/null
        
        # 检查命令是否成功
        if [ $? -eq 0 ]; then
            success=1
        fi
    fi
done` 
```

  

1 个回复

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

+1

47

​ ​

*   [昨天的一个VPN](https://linux.do/t/topic/218851)
*   [可以申请的学校（edu）与一些福利（论坛帖子）](https://linux.do/t/topic/225548)
*   [【教育无国界】打破edu垄断 0基础一起上大学教程 (美国篇）](https://linux.do/t/topic/223009)
*   [【求助】如何连接GlobalProtect vpn。](https://linux.do/t/topic/375976/14)

2.0k 浏览量 67 赞 4 链接 11 用户

 [![](https://linux.do/user_avatar/linux.do/zcw/96/333203_2.png)
 14](/u/zcw "zcw") 

 [![](https://linux.do/letter_avatar_proxy/v4/letter/g/d26b3c/96.png)
 5](/u/gyxzhao "gyxzhao")

 [![](https://linux.do/letter_avatar_proxy/v4/letter/l/50afbb/96.png)
 2](/u/lovexl "lovexl") 

 [![](https://linux.do/letter_avatar_proxy/v4/letter/t/ba8739/96.png)
 2](/u/tylorgao "tylorgao")

 [![](https://linux.do/letter_avatar_proxy/v4/letter/b/d26b3c/96.png)
 2](/u/bbb "bbb")

[![](https://linux.do/letter_avatar_proxy/v4/letter/b/d26b3c/96.png)
](/u/bbb)

[bbb](/u/bbb)无所不知

[2024 年 9月](/t/topic/218449/2?u=niyan2025 "发布日期")

学校没VPN怎么办 ![](https://linux.do/uploads/default/original/3X/2/e/2e09f3a3c7b27eacbabe9e9614b06b88d5b06343.png?v=12)

  

1 个回复

1

​ ​

[![](https://linux.do/user_avatar/linux.do/han_luoke/96/122483_2.png)
](/u/han_luoke)

[roosevelt](/u/han_luoke)[han\_luoke](/u/han_luoke)活跃用户

[2024 年 9月](/t/topic/218449/3?u=niyan2025 "发布日期")

顶顶顶，怪不得我电脑上连了ip没有变

  

2

​ ​

[![](https://linux.do/user_avatar/linux.do/han_luoke/96/122483_2.png)
](/u/han_luoke)

[roosevelt](/u/han_luoke)[han\_luoke](/u/han_luoke)活跃用户

 ![](https://linux.do/letter_avatar_proxy/v4/letter/b/d26b3c/48.png)
 bbb

[2024 年 9月](/t/topic/218449/4?u=niyan2025 "发布日期")

学校基本都有吧![](https://linux.do/images/emoji/twemoji/face_with_thermometer.png?v=12)

  

1 个回复

1

​ ​

[![](https://linux.do/letter_avatar_proxy/v4/letter/b/d26b3c/96.png)
](/u/bbb)

[bbb](/u/bbb)无所不知

 ![](https://linux.do/user_avatar/linux.do/han_luoke/48/122483_2.png)
 roosevelt

[2024 年 9月](/t/topic/218449/5?u=niyan2025 "发布日期")

社区学院没见过几个有的 ![](https://linux.do/uploads/default/original/3X/2/e/2e09f3a3c7b27eacbabe9e9614b06b88d5b06343.png?v=12)

  

1 个回复

2

​ ​

[![](https://linux.do/user_avatar/linux.do/zcw/96/333203_2.png)
](/u/zcw)

[欲天](/u/zcw)[zcw](/u/zcw)一元复始

 ![](https://linux.do/letter_avatar_proxy/v4/letter/b/d26b3c/48.png)
 bbb

[2024 年 9月](/t/topic/218449/6?u=niyan2025 "发布日期")

![](https://linux.do/images/emoji/twemoji/rage.png?v=12)
 ![](https://linux.do/images/emoji/twemoji/rage.png?v=12)
 ![](https://linux.do/images/emoji/twemoji/rage.png?v=12)
是时候上学了

  

3

​ ​

[![](https://linux.do/letter_avatar_proxy/v4/letter/t/ba8739/96.png)
](/u/tylorgao)

[tylorgao](/u/tylorgao)一元复始

[2024 年 9月](/t/topic/218449/7?u=niyan2025 "发布日期")

我是先v2ray连接的美国vps，再登录的vpn。  
这时Ping0.cc显示的是美国vps的IP地址。  
此时我关闭v2ray，vpn没有断开，此时就显示了vpn后的地址了。

  

1 个回复

2

​ ​

[![](https://linux.do/user_avatar/linux.do/zcw/96/333203_2.png)
](/u/zcw)

[欲天](/u/zcw)[zcw](/u/zcw)一元复始

 ![](https://linux.do/letter_avatar_proxy/v4/letter/t/ba8739/48.png)
 tylorgao

[2024 年 9月](/t/topic/218449/8?u=niyan2025 "发布日期")

啊？有点没懂。您的VPS可以连接学校的VPN？  
我想弄但是不咋会

  

1 个回复

​ ​

[![](https://linux.do/letter_avatar_proxy/v4/letter/t/ba8739/96.png)
](/u/tylorgao)

[tylorgao](/u/tylorgao)一元复始

 ![](https://linux.do/user_avatar/linux.do/zcw/48/333203_2.png)
 欲天

[2024 年 9月](/t/topic/218449/9?u=niyan2025 "发布日期")

就是找个美国的节点，先翻出去，再vpn登录的。

  

1 个回复

​ ​

[![](https://linux.do/user_avatar/linux.do/zcw/96/333203_2.png)
](/u/zcw)

[欲天](/u/zcw)[zcw](/u/zcw)一元复始

 ![](https://linux.do/letter_avatar_proxy/v4/letter/t/ba8739/48.png)
 tylorgao

[2024 年 9月](/t/topic/218449/10?u=niyan2025 "发布日期")

我去尝试了一下，可能我们遇到的问题不一样吧，连接 _**GlobalProtect**_ 之后没有更改IP是因为网关优先级的问题（没有更改的时候一直使用的是默认网关就是本地IP），但是更改网关优先级之后默认网关就是GlobalProtect使用的就是学校的代理IP。  
和您说的先翻墙再VPN登入，这样还是无法使用学校的代理（因为本地的网关的优先级一直高于GlobalProtect的网关）。

  

2 个回复

​ ​

[![](https://linux.do/letter_avatar_proxy/v4/letter/l/50afbb/96.png)
](/u/lovexl)

[lovexl](/u/lovexl)

 ![](https://linux.do/user_avatar/linux.do/zcw/48/333203_2.png)
 欲天

[2024 年 9月](/t/topic/218449/11?u=niyan2025 "发布日期")

技术佬，很实用

  

​ ​

[![](https://linux.do/letter_avatar_proxy/v4/letter/l/50afbb/96.png)
](/u/lovexl)

[lovexl](/u/lovexl)

 ![](https://linux.do/user_avatar/linux.do/zcw/48/333203_2.png)
 欲天

[2024 年 9月](/t/topic/218449/12?u=niyan2025 "发布日期")

手机上是不是g了，没法操作了

  

2 个回复

5

​ ​

[![](https://linux.do/user_avatar/linux.do/zcw/96/333203_2.png)
](/u/zcw)

[欲天](/u/zcw)[zcw](/u/zcw)一元复始

 ![](https://linux.do/letter_avatar_proxy/v4/letter/l/50afbb/48.png)
 lovexl

[2024 年 9月](/t/topic/218449/13?u=niyan2025 "发布日期")

手机端没试过，我没装这个软件

  

1

​ ​

[![](https://linux.do/user_avatar/linux.do/zcw/96/333203_2.png)
](/u/zcw)

[欲天](/u/zcw)[zcw](/u/zcw)一元复始

 ![](https://linux.do/letter_avatar_proxy/v4/letter/l/50afbb/48.png)
 lovexl

[2024 年 9月](/t/topic/218449/14?u=niyan2025 "发布日期")

手机端理论上是可以的，但是需要root太麻烦了

  

​ ​

[![](https://linux.do/user_avatar/linux.do/handsome/96/477777_2.png)
](/u/handsome)

[大帅哥](/u/handsome)[handsome](/u/handsome)种子用户 ![](https://linux.do/images/emoji/twemoji/rage.png?v=14) 

[2024 年 9月](/t/topic/218449/15?u=niyan2025 "发布日期")

太强了吧宝贝！

  

​ ​

[![](https://linux.do/user_avatar/linux.do/tanwan/96/183128_2.png)
](/u/tanwan)

[艾青](/u/tanwan)[tanwan](/u/tanwan)浴火重生 ![](https://linux.do/images/emoji/twemoji/speech_balloon.png?v=14) 

[2024 年 10月](/t/topic/218449/16?u=niyan2025 "发布日期")

唯一入学的u佬的 csuf有vpn但是vpn连不上，被拒绝了

  

​ ​

[![](https://linux.do/letter_avatar_proxy/v4/letter/k/eada6e/96.png)
](/u/kilnlger12)

[kilnlger12](/u/kilnlger12)一元复始

[2024 年 10月](/t/topic/218449/17?u=niyan2025 "发布日期")

请问 重启电脑后就恢复原来的优先级了吗？需要重新再输入一次吗

  

1 个回复

​ ​

[![](https://linux.do/user_avatar/linux.do/zcw/96/333203_2.png)
](/u/zcw)

[欲天](/u/zcw)[zcw](/u/zcw)一元复始

 ![](https://linux.do/letter_avatar_proxy/v4/letter/k/eada6e/48.png)
 kilnlger12

[2024 年 10月](/t/topic/218449/18?u=niyan2025 "发布日期")

如果连接VPN，IP没有改变，就是要再运行一次

  

​ ​

11 天后

[![](https://linux.do/letter_avatar_proxy/v4/letter/g/d26b3c/96.png)
](/u/gyxzhao)

[gyxzhao](/u/gyxzhao) ![](https://linux.do/images/emoji/twemoji/ninja.png?v=14) 

[2024 年 10月](/t/topic/218449/19?u=niyan2025 "发布日期")

佬，网关地址填哪里啊？

```


`@echo off

set gateways=myvpn.***.edu

set success=0
for %%i in (%gateways%) do (
    if %success% equ 0 (
        route delete 0.0.0.0 mask 0.0.0.0
        route add 0.0.0.0 mask 0.0.0.0 %%i metric 1
        if not errorlevel 1 (
            set success=1
        )
    )
)` 
```

这样吗

  

2 个回复

​ ​

[![](https://linux.do/user_avatar/linux.do/zcw/96/333203_2.png)
](/u/zcw)

[欲天](/u/zcw)[zcw](/u/zcw)一元复始

 ![](https://linux.do/letter_avatar_proxy/v4/letter/g/d26b3c/48.png)
 gyxzhao

[2024 年 10月](/t/topic/218449/20?u=niyan2025 "发布日期")

你先要打开软件

  

​ ​

Invalid date Invalid date

↑↓⇔⇧⇩