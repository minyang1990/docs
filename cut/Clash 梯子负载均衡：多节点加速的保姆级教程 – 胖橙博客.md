# Clash 梯子负载均衡：多节点加速的保姆级教程 – 胖橙博客
[Clash 梯子负载均衡：多节点加速的保姆级教程 – 胖橙博客](https://js2panda.com/clash-load-balance) 

 Clash 梯子负载均衡：多节点加速的保姆级教程 – 胖橙博客   

Constants loaded at 2025-08-10T06:29:41.020Z

[跳至内容](#wp--skip-link--target)

[胖橙博客](https://js2panda.com)
============================

*   [所有文章](https://jiasupanda.com/category/blog "所有文章")
    *   [ShadowSocks 配置指南ShadowSocks 配置指南](https://jiasupanda.com/vultr-ss "ShadowSocks 配置指南")
    *   [Trojan-Go 配置教程ShadowSocks 配置指南](https://jiasupanda.com/vultr-trojan "ShadowSocks 配置指南")
    *   [Vmess 新手教程ShadowSocks 配置指南](https://jiasupanda.com/vmess-vultr "ShadowSocks 配置指南")
    *   [X-UI 面板配置指南ShadowSocks 配置指南](https://jiasupanda.com/x-ui "ShadowSocks 配置指南")
    *   [VLess + XTLS 配置指南VLess + XTLS 配置指南](https://jiasupanda.com/vless "VLess + XTLS 配置指南")
*   [AI 相关](https://jiasupanda.com/tag/ai "AI 相关内容")
    *   [国内注册 ChatGPT国内注册 ChatGPT](https://jiasupanda.com/chatgpt-register "国内注册 ChatGPT")
    *   [RMB 购买 USDTRMB 购买 USDT](https://jiasupanda.com/rmb-buy-usdt "RMB 购买 USDT")
    *   [OpenAI 账号被拒怎么办OpenAI 账号被拒怎么办](https://jiasupanda.com/chatgpt-rejected "OpenAI 账号被拒怎么办")
    *   [海外手机号申请海外手机号申请](https://jiasupanda.com/oversea-sim "海外手机号申请")
*   [联系博主联系博主](https://jiasupanda.com/about "联系博主")

![](https://jiasupanda.com/wp-content/uploads/2023/06/1686297329-image.png)

Clash 梯子负载均衡：多节点加速的保姆级教程
========================

2023年9月19日

之前我在已经写过了配置单节点服务器的教程（[SS](https://js2panda.com/vultr-ss) 和 [Trojan-go](https://js2panda.com/vultr-trojan)）。在这些教程中我没有提到的是单节点其实有一个很大弊端——就是**魔法（科学）上网效果会受到当前节点服务器的节制**。

因为是单节点、无论你使用系统代理还是 TUN 代理模式，流量只能走这唯一的节点。如果这个节点有带宽限制、或者 IP 被墙、又或是服务器超载，都会导致你扶墙速度慢、甚至扶墙失败。

所以这时候你就需要使用多节点，并在多节点之间使用负载均衡来实现最佳扶墙效果！

**新手推荐**：[Clash 新手完美使用指南 \[史上最强外网加速器\]](https://js2panda.com/clash-how-to)；已经会了的继续往下看！

本教程就带着大家解决两个问题：

*   彻底抛弃单节点，直接使用多节点进行科学扶墙。
*   如何在多节点之间进行负载均衡，将节点服务器性能最大化。

重点是在第二个问题上，废话不多说，我们直接开始。

**内容** [隐藏](#)

[1 一些基础概念的解释](#yi_xie_ji_chu_gai_nian_de_jie_shi)

[2 准备工作](#zhun_bei_gong_zuo)

[3 从节点供应商购买多节点服务](#cong_jie_dian_gong_ying_shang_gou_mai_duo_jie_dian_fu_wu)

[4 下载 Clash 并将节点地址导入至 Clash](#xia_zai_Clash_bing_jiang_jie_dian_de_zhi_dao_ru_zhi_Clash)

[5 配置 Clash 的 parsers（预处理）实现负载均衡](#pei_zhi_Clash_de_parsers_yu_chu_li_shi_xian_fu_zai_jun_heng)

[6 重启 Clash 并选择对应规则](#zhong_qi_Clash_bing_xuan_ze_dui_ying_gui_ze)

[7 速度测试](#su_du_ce_shi)

[7.1 散列模式和轮询模式的说明](#san_lie_mo_shi_he_lun_xun_mo_shi_de_shuo_ming)

[8 结语](#jie_yu)

[8.1 相关软件工具下载](#xiang_guan_ruan_jian_gong_ju_xia_zai)

[9 学习资料](#xue_xi_zi_liao)

一些基础概念的解释
---------

**什么是单节点？什么是多节点？**新手可以可以理解为单节点就是单台服务器、单 IP；多节点就是多台服务器、多 IP。虽然这么解释不是特别严格，但是小白这么理解就可以。

_**博主说明**：其实一台服务器是可以配置多个节点协议的。但是大多数节点供应商，例如 [灯塔Cloud](https://pandalinks.cc/dt/reg2) 会提供多个服务器。所以上方才会说解释并不严格。但是并不妨碍大家的理解。_

**什么是负载均衡？**就是将流量的访问压力分散到多个节点服务器上（雨露均沾）。即使一台服务器暂时不好用，第二台就可以自动顶上，无需手动操作（东边不亮，西边亮）。

准备工作
----

*   [一个免费的 VPN](https://pandalinks.cc/aha/2)（主要是用于工具下载用的）
*   Clash 客户端（下方有官方地址、以及备用载点）
*   一个多节点的服务商（本文使用 [灯塔Cloud](https://pandalinks.cc/dt/reg2)【推荐】 节点服务商进行演示。如果你有钱也可以选择 [JustMySocks](https://pandalinks.cc/jms) 的服务）

关于客户端，建议阅读下面两个教程：

*   [客户端对比：Clash vs. V2rayN](https://js2panda.com/v2rayn-clash)
*   [Clash for Windows 汉化教程](https://js2panda.com/clash-zh)

从节点供应商购买多节点服务
-------------

[灯塔 Cloud 官网](https://pandalinks.cc/dt/reg2) << 通过左侧链接点击注册账号。有多个邮箱可以提供使用。其他节点服务器商的操作流程基本相同。如果是第一次做尝试，那么可以和我一样使用灯塔 Cloud。

 [![](https://js2panda.com/wp-content/uploads/2023/02/1677561714-image.png.webp)](https://js2panda.com/wp-content/uploads/2023/02/1677561714-image.png) 

注册界面

注册并登陆后，在左侧【购买订阅】中选择购买一个合适的服务。最开始建议直接选择最便宜的那个（29元/月）。买一个月先做测试，觉得效果好再选择续费。如果是已经使用过，那么就直接选择年付的269元套餐（最划算）就可以。

 [![](https://js2panda.com/wp-content/uploads/2023/02/1677561986-image.png.webp)](https://js2panda.com/wp-content/uploads/2023/02/1677561986-image.png) 

价格概览

购买完成后，左侧选择【仪表盘】，就可以看到**当前套餐剩余的流量以及时间**。在下方就是各种客户端需要的**订阅地址**以及**教程、**

 [![](https://js2panda.com/wp-content/uploads/2023/02/1677562361-image-1024x564.png.webp)](https://js2panda.com/wp-content/uploads/2023/02/1677562361-image.png) 

仪表盘界面

下载 Clash 并将节点地址导入至 Clash
------------------------

首先你需要下载并安装 Clash。Win 系统用的就是 Clash for Windows（CFW）。本文演示，使用的也是 CFW。其他设备请自行测试，基本操作相同。不熟悉英文的朋友可以选择[安装 CFW 汉化补丁](https://js2panda.com/clash-zh)。这里就不赘述了。

下面就讲两种节点导入客户端的方式：

**直接点击导入**——打开 Clash、然后打开灯塔 Cloud 的仪表盘，然后最下方选择【一键订阅】。然后选择【导入到 Clash for Windows】即可。这种方法只是用于 PC端，如果是手机端需要通过订阅地址导入。

**通过订阅地址导入**——然后打开灯塔 Cloud 的仪表盘，然后最下方选择【一键订阅】。然后选择【复制订阅地址】。打开 Clash，将订阅地址复制到左侧【配置】上方的URL栏里，然后点击【下载】即可。

无论通过哪种方式，出现如下选项就代表导入成功：

 [![](https://js2panda.com/wp-content/uploads/2023/02/1677562902-image.png.webp)](https://js2panda.com/wp-content/uploads/2023/02/1677562902-image.png) 

订阅地址导入成功

到此其实就可以在左侧【代理】中选择单个节点进行科学上网了。但是为了实现更好的加速效果，你还得…

注意：此时可能会有 invalid mode: redir-host \[Could not switch to this profile\] 报错

这个是因为 灯塔 Cloud 机场订阅默认的 `enhanced-mode` 设置是 `redir-host` 模式。所以要进行修改。建议大家先看完本教程，然后再[阅读如何修复这个问题的教程](https://js2panda.com/clash-redir-host-error)。

在问题修复指南中，我也附带了 **负载均衡+修复报错** 的**完整预处理脚本代码**。可以直接复制粘贴使用。

配置 Clash 的 parsers（预处理）实现负载均衡
-----------------------------

在刚才我们已近导入了所有的节点，大约有20组这样。现在我们要利用 Clash 的 parsers 预处理配置功能实现节点的负载均衡。简单说就是让所有节点雨露均沾，不浪费任何一个带宽，提升我们的魔法上网体验。

打开 Clash，左侧选择【设置】，并在右侧选择【配置】

 [![](https://js2panda.com/wp-content/uploads/2023/02/1677564686-image.png.webp)](https://js2panda.com/wp-content/uploads/2023/02/1677564686-image.png) 

在【预处理配置（parsers）】后面点击【编辑】：

 [![](https://js2panda.com/wp-content/uploads/2023/02/1677564764-image.png.webp)](https://js2panda.com/wp-content/uploads/2023/02/1677564764-image.png) 

将下方代码完整的放入编辑文件中，然后 Ctrl+S 、或者点击右小角按钮保存：

```
parsers:
  - reg: 'slbable$'
    yaml:
      append-proxy-groups:
        - name: ⚖️ 负载均衡-散列
          type: load-balance
          url: 'http://www.google.com/generate_204'
          interval: 300
          strategy: consistent-hashing
        - name: ⚖️ 负载均衡-轮询
          type: load-balance
          url: 'http://www.google.com/generate_204'
          interval: 300
          strategy: round-robin
      commands:
        - proxy-groups.⚖️ 负载均衡-散列.proxies=[]proxyNames
        - proxy-groups.0.proxies.0+⚖️ 负载均衡-散列
        - proxy-groups.⚖️ 负载均衡-轮询.proxies=[]proxyNames
        - proxy-groups.0.proxies.0+⚖️ 负载均衡-轮询
```

_**博主鸣谢**：代码 Shout out to **不良林** 老师（[YouTube](https://www.youtube.com/@bulianglin)）_

再次点击编辑，出现的应该是如下这样的界面：

 [![](https://js2panda.com/wp-content/uploads/2023/02/1677565047-image.png.webp)](https://js2panda.com/wp-content/uploads/2023/02/1677565047-image.png) 

Clash 的 负载均衡（散列+轮询）配置代码

回到左侧【配置】，选择之前出现的灯塔 Cloud选项，右击选择【设置】。此时应该会出现之前复制过的灯塔 Cloud 的订阅地址。你需要在订阅地址之后加上【#slbable】：

 [![](https://js2panda.com/wp-content/uploads/2023/02/1677565310-image.png.webp)](https://js2panda.com/wp-content/uploads/2023/02/1677565310-image.png) 

在订阅地址后面手动输入：#slbable

点击确定回到【配置】界面，右击灯塔 Cloud 选择【预处理配置】。如果出现如下界面，就代表负载均衡规则已加载成功：

 [![](https://js2panda.com/wp-content/uploads/2023/02/1677565438-image.png.webp)](https://js2panda.com/wp-content/uploads/2023/02/1677565438-image.png) 

出现 reg(slbable$) 代表负载均衡规则加载成功

此时，你的 Clash 已经配置好的节点之间的负载均衡规则。在【代理】-【规则】中出现了【负载均衡-散列】和【负载均衡-轮询】的选项：

 [![](https://js2panda.com/wp-content/uploads/2023/02/1677565625-image.png.webp)](https://js2panda.com/wp-content/uploads/2023/02/1677565625-image.png) 

新增的【负载均衡-散列】和【负载均衡-轮询】选项卡

在只需要重启 Clash 并选择好代理，就可以实现负载均衡效果。

重启 Clash 并选择对应规则
----------------

重启之后，打开【代理】-【规则】，并点击选择【负载均衡-轮询模式】。然后右击窗口右下角的Clash小蓝猫图标，像右侧图片这样选择。选择【系统代理】、然后代理模式选择【规则】。

 [![](https://js2panda.com/wp-content/uploads/2023/02/1677565792-image.png.webp)](https://js2panda.com/wp-content/uploads/2023/02/1677565792-image.png) 

关于系统代理、TUN模式、混合配置这些，**新手可以这么理解**：

*   **系统代理**：就是浏览页面、看视频之类的走代理（魔法上网）。游戏、应用之类的不会走代理（虽然不是绝对）。
*   **TUN 模式**：就是无论网页、游戏、应用还是什么全部按照规则走代理（魔法上网）。
*   **混合模式**：就是上面两个混一起用。

关于全局、规则、直连、脚本，这些我就不解释了。正常选择【规则】模式（类似其他绕过大陆或 PAC 模式）就对了。

到此你就可以愉快的扶墙看 YouTube 了。博主的体会是：**学习任何新知识，有 YouTube 足以。国内除了 B 站能看之外，其余的都是垃圾。** 

速度测试
----

如果你想测试负载均衡的效果，可以在 Clash 界面左侧，选择【链接】，然后打开 Google 网站进行检测：

 ![](https://js2panda.com/wp-content/uploads/2023/02/1677567313-image.png.webp) 

因为我是用的是【轮询】模式，可以看到上方不同的请求，使用的节点都不一样。即使有一个节点速度慢，只会导致其中一个请求失效或加载慢、而不会影响到整体效果。

_**博主提示**：如果要测试负载均衡的下载效果可以通过 [speedtest.net](https://www.speedtest.net/) 进行测试。记得测试前将 Clash 切换到全局模式。_

这时有人要问：如果大部分节点都失效怎么办？雨露均沾大部分不就没用了？这个不必担心，预处理规则中会隔一段时间就检测节点有效性。**负载均衡也只会在有效的节点中进行**。

在上方 parsers（预处理）代码中，有一个 interval 的属性，就是查询有效性的时间间隔。`interval: 300` 其实就代表，每隔 300 秒就查询一次节点有效性。

### 散列模式和轮询模式的说明

我在上面使用的是轮询模式，关于轮询和散列模式在具体使用中感觉并不是特别的大。新手可以这么理解这两个模式（并不准确，但足够你理解）：

*   **轮询模式**：按照节点顺序，挨个匹配请求。
*   **散列模式**：按照随机规律（hash 随机），匹配请求。

结语
--

负载均衡的好处就是可以规避单节点失效导致无法科学上网的问题。同时在多请求时，可以通过给不同的请求分配不同的节点，将科学上网体验、速度最大化。

利用 Clash 客户端的 parsers（预处理）功能，可以完美的实现这个功能。再拉跨的节点，只要数量够多，都可以实现带宽叠加，网速叠加的效果。

推荐阅读：[Clash 新手完美使用指南 \[史上最强外网加速器\]](https://js2panda.com/clash-how-to)

**来自博主的建议：** 

如果你只是为了能够稳定的科学上网，其实没必要自己配置节点服务器。毕竟需要考虑的东西很多，同时个人配置成本算是比较高的。就拿 Vultr 服务器举例子，最低也得 $6（大概40块）每月，而且只有一条线路，如果崩了还得手动重新配置并更换。与其这样，不如每月花费个20元左右，直接买一组（5-20条线路）稳定的节点会更好一些。

其中👑[万城加速器](https://panda2go.com/go/vcity)👑（性价比贼高）、👑[小鸡快跑](https://panda2go.com/go/chicken)👑(香港，台湾地区贼快)、👑[灯塔Cloud](https://panda2go.com/go/ind-dt-JZOytIR9)👑 和👑[银河云机场](https://panda2go.com/go/galaxy)👑（支持终生购买） 以及 [JustMysocks](https://panda2go.com/go/just-my-socks)（老牌稳定） 的服务都很不错。其中灯塔Cloud和Faston相对会便宜一些，同时线路也很多，支持多个[客户端](https://jiasupanda.com/v2rayn-clash)，非常适合个人、学生党使用。JustMysocks算是时间比较老的，名气稍微大一点，适合游戏主播、外贸公司等使用。

PS：因为多节点还可以[通过 Clash 做负载均衡](https://jiasupanda.com/clash-load-balance)，大大的提升了科学上网的体验。所以博主建议自建节点学学就可以了，还是用别人建好的更舒服一些。

### 相关软件工具下载

下载注意事项：这些工具均上传到了 pCloud。可以直接点击链接下载。如果下载失效，或者下载速度过慢可以考虑先使用[免费的 VPN 工具](https://pandalinks.cc/aha/2)进行下载，然后再按照教程进行配置。

| 1 | [Clash for Windows（v0.20.16）](https://u.pcloud.link/publink/show?code=XZCfFgVZDz9y6d3SclSufgJ2gD9ijVNwIXV7) |
| 2 | [Clash fow Windows 中文汉化补丁 app.asar 文件（v0.20.16）](https://u.pcloud.link/publink/show?code=XZPfFgVZawJmWcOeCw7Tqwp9Pxv0TFCNRtiX) |

学习资料
----

提前说明：部分资料在特定地区无法打开，如果你需要提前观看这些资料，请使用[免费的 VPN 工具](https://pandalinks.cc/aha/2)打开学习。

| 1 | [其他 Clash for Windows 版本](https://github.com/Fndroid/clash_for_windows_pkg/releases/tag/0.20.16)（Github） |
| 2 | [不良林：Clash 负载均衡](https://www.youtube.com/watch?v=dxYdec9csl4)（YouTube） |
| 3 | [Clash 安卓版](https://github.com/Kr328/ClashForAndroid)（Github） |

标签：

[机场客户端](https://js2panda.com/tag/client), [科学上网](https://js2panda.com/tag/kxsw)

分类：

[所有博文](https://js2panda.com/category/blog)

![](https://js2panda.com/wp-content/litespeed/avatar/13525151fccf0aa1c83668391b2b09eb.jpg?ver=1754546700)

博主·作者

胖橙

我是胖橙子（技术宅、诗人），91年出生在种花家。现在在海外打工，欢迎来到我的个人博客。我喜欢钻研各种网络技术、通讯技术。并将整个过程分享到自己的博客。你可以在[联系作者](https://jiasupanda.com/about)中看我写的诗。

### 《 “Clash 梯子负载均衡：多节点加速的保姆级教程” 》 有 37 条评论

1.  【无废话】Clash for Windows（CFW）如何配置中文 附 Clash 中文补丁下载地址 – 胖橙博客
    
    [2023年2月28日](https://js2panda.com/clash-load-balance#comment-41)
    
    \[…\] Clash 负载均衡：多节点带宽叠加 \[…\]
    
2.  【2023年】V2rayN 和 Clash 客户端哪个好用？机场小白应该如何选择？ – 胖橙博客
    
    [2023年2月28日](https://js2panda.com/clash-load-balance#comment-42)
    
    \[…\] 还支持 parsers 功能，可以轻易的实现节点之间的负载均衡。关于 \[…\]
    
3.  Clash 报错 invalid mode: redir-host \[Could not switch to this profile\] – 胖橙博客
    
    [2023年3月18日](https://js2panda.com/clash-load-balance#comment-84)
    
    \[…\] 灯塔Cloud 配置 Clash 负载均衡的时候出现了这个错误提示：\[Could not switch to this profile\] nvalid mode: \[…\]
    
4.  如何解决 Windows11 无法登录 Microsoft Account 的问题？ – 胖橙博客
    
    [2023年3月18日](https://js2panda.com/clash-load-balance#comment-87)
    
    \[…\] + 灯塔 Cloud + 负载均衡新手直接用 AHA 加速器 \[…\]
    
5.  ![](https://js2panda.com/wp-content/litespeed/avatar/3643bd6924072701f5263dc53d1d6e5a.jpg?ver=1754549859)
    
    Jackie Zack
    
    [2023年4月9日](https://js2panda.com/clash-load-balance#comment-126)
    
    配置好之后，预处理也显示了，但是配置那里没出现负载均衡的标签，还是跟原来一样是一大堆节点
    
    1.  ![](https://js2panda.com/wp-content/litespeed/avatar/51ca037d08d9fafce17b2bc1f842b2df.jpg?ver=1754549810)
        
        胖橙
        
        [2023年4月11日](https://js2panda.com/clash-load-balance#comment-133)
        
        应该是没加载出来，我用的同样的代码。
        
        1.  ![](https://js2panda.com/wp-content/litespeed/avatar/0d484e47b9831ffa71dde75a6cd1fe8f.jpg?ver=1754549859)
            
            kkk
            
            [2023年8月15日](https://js2panda.com/clash-load-balance#comment-261)
            
            重新reload一下就行了， 在配置那里 刷新一下
            
6.  ![](https://js2panda.com/wp-content/litespeed/avatar/7acd30f7fa87329125d613df0e00bf50.jpg?ver=1754549858)
    
    Echo
    
    [2023年5月5日](https://js2panda.com/clash-load-balance#comment-162)
    
    配置好负载均衡后，为什么在【代理】-【规则】中看不到【负载均衡-散列】和【负载均衡-轮询】选项？
    
    1.  ![](https://js2panda.com/wp-content/litespeed/avatar/51ca037d08d9fafce17b2bc1f842b2df.jpg?ver=1754549810)
        
        胖橙
        
        [2023年5月6日](https://js2panda.com/clash-load-balance#comment-164)
        
        右击梯子，选择 parsers，是否出现 parsers 对应的生效提示？如果没有，代表 parsers 并未生效。同时记得预处理之后，需要重启下 Clash
        
        1.  ![](https://js2panda.com/wp-content/litespeed/avatar/8f88f81cc2ad63b0ebb5229fb1381378.jpg?ver=1754549201)
            
            星海
            
            [2024年7月22日](https://js2panda.com/clash-load-balance#comment-1174)
            
            我的有生效提示，重启还是没有负载均衡的两个选项。这是否与我买来的节点是被分好组的有关？一组一组的，什么Auto-fast/proxy/video/netflix……
            
7.  ![](https://js2panda.com/wp-content/litespeed/avatar/6c6ab9a2847371b36b19ee3f1b8d24f2.jpg?ver=1754549857)
    
    john
    
    [2023年5月17日](https://js2panda.com/clash-load-balance#comment-185)
    
    0.20.23版本无效
    
8.  ![](https://js2panda.com/wp-content/litespeed/avatar/6c6ab9a2847371b36b19ee3f1b8d24f2.jpg?ver=1754549857)
    
    john
    
    [2023年5月17日](https://js2panda.com/clash-load-balance#comment-186)
    
    0.20.21版本无效
    
    1.  ![](https://js2panda.com/wp-content/litespeed/avatar/51ca037d08d9fafce17b2bc1f842b2df.jpg?ver=1754549810)
        
        胖橙
        
        [2023年5月18日](https://js2panda.com/clash-load-balance#comment-188)
        
        换个版本咯，GitHub里版本都是全的
        
9.  ![](https://js2panda.com/wp-content/litespeed/avatar/da1a1f1866bcd24995f0371ef39adc22.jpg?ver=1754549857)
    
    Fzlclp
    
    [2023年5月27日](https://js2panda.com/clash-load-balance#comment-196)
    
    大佬你好，配置好负载均衡后，轮询的延迟比下面其他节点都要高很多是什么情况，配置负载均衡一定会比没配置更快嘛，求解
    
    1.  ![](https://js2panda.com/wp-content/litespeed/avatar/51ca037d08d9fafce17b2bc1f842b2df.jpg?ver=1754549810)
        
        胖橙
        
        [2023年5月27日](https://js2panda.com/clash-load-balance#comment-197)
        
        延迟（就是显示的数值。并非真实延迟）和负载均很本生没什么关系。只是显示时效性的问题。
        
10.  ![](https://js2panda.com/wp-content/litespeed/avatar/fac4c7da3031658cb1361e13102eb31d.jpg?ver=1754549857)
    
    Jx1a0
    
    [2023年7月12日](https://js2panda.com/clash-load-balance#comment-238)
    
    一直想用clash实现类似代理池的效果，0.20.28完美实现，感谢师傅。
    
11.  ![](https://js2panda.com/wp-content/litespeed/avatar/fac4c7da3031658cb1361e13102eb31d.jpg?ver=1754549857)
    
    Jx1a0
    
    [2023年7月12日](https://js2panda.com/clash-load-balance#comment-239)
    
    nice
    
12.  ![](https://js2panda.com/wp-content/litespeed/avatar/3f91f2521593f511084fa5ef7dd01926.jpg?ver=1754549856)
    
    hasto
    
    [2023年7月21日](https://js2panda.com/clash-load-balance#comment-246)
    
    为什么我开了轮询速度变慢了，不如直接选择一个延时低的节点速度快
    
13.  ![](https://js2panda.com/wp-content/litespeed/avatar/3f91f2521593f511084fa5ef7dd01926.jpg?ver=1754549856)
    
    hasto
    
    [2023年7月21日](https://js2panda.com/clash-load-balance#comment-247)
    
    为什么我开了轮询网速变慢了，不如直接选择一个延时低的节点速度快
    
    1.  ![](https://js2panda.com/wp-content/litespeed/avatar/51ca037d08d9fafce17b2bc1f842b2df.jpg?ver=1754549810)
        
        胖橙
        
        [2023年7月28日](https://js2panda.com/clash-load-balance#comment-251)
        
        按照实际情况来，不是说开了一定会快，要考虑实际影响
        
14.  ![](https://js2panda.com/wp-content/litespeed/avatar/8fabebac43f551828404d58bc72653aa.jpg?ver=1754549856)
    
    teng xiaoxuan
    
    [2023年8月4日](https://js2panda.com/clash-load-balance#comment-252)
    
    为啥我直接用灯塔的客户端还要快点，开了clash卡的要死
    
15.  ![](https://js2panda.com/wp-content/litespeed/avatar/8fabebac43f551828404d58bc72653aa.jpg?ver=1754549856)
    
    Kkkkk
    
    [2023年8月4日](https://js2panda.com/clash-load-balance#comment-253)
    
    为啥我直接用灯塔的客户端还要快点，开了clash卡的要死
    
    1.  ![](https://js2panda.com/wp-content/litespeed/avatar/51ca037d08d9fafce17b2bc1f842b2df.jpg?ver=1754549810)
        
        胖橙
        
        [2023年8月11日](https://js2panda.com/clash-load-balance#comment-260)
        
        哪个快用哪个
        
16.  小飞机加速器免费下载·扫盲·评测·使用指南\[科学上网新手必看科普\] – 胖橙博客
    
    [2023年9月14日](https://js2panda.com/clash-load-balance#comment-304)
    
    \[…\] Clash 梯子负载均衡：多节点加速的保姆级教程 \[…\]
    
17.  Clash 新手完美使用指南 \[史上最强外网加速器\] – 胖橙博客
    
    [2023年9月19日](https://js2panda.com/clash-load-balance#comment-309)
    
    \[…\] 面向高级用户：你还可以通过 Clash 实现负载均衡。让外网加速效果最大化。 \[…\]
    
18.  ![](https://js2panda.com/wp-content/litespeed/avatar/bcc66aa02058de62d39111fcc0355a0f.jpg?ver=1754549855)
    
    yufeng
    
    [2023年9月25日](https://js2panda.com/clash-load-balance#comment-538)
    
    支持多个代理同时使用吗？比如我用灯塔负载均衡设置成功，但是其他代理并不显示配置
    
    1.  ![](https://js2panda.com/wp-content/litespeed/avatar/51ca037d08d9fafce17b2bc1f842b2df.jpg?ver=1754549810)
        
        胖橙
        
        [2023年9月25日](https://js2panda.com/clash-load-balance#comment-541)
        
        理论是可以，但是需要配置代码
        
19.  ![](https://js2panda.com/wp-content/litespeed/avatar/77326a2a1e82a94bbd46959615b47e64.jpg?ver=1754549855)
    
    jdassd
    
    [2023年10月7日](https://js2panda.com/clash-load-balance#comment-561)
    
    安卓手机上是否可以也进行多节点的加速操作？
    
    1.  ![](https://js2panda.com/wp-content/litespeed/avatar/51ca037d08d9fafce17b2bc1f842b2df.jpg?ver=1754549810)
        
        胖橙
        
        [2023年10月7日](https://js2panda.com/clash-load-balance#comment-562)
        
        可以试试，理论是可以的
        
20.  ![](https://js2panda.com/wp-content/litespeed/avatar/77eabdae647edd8623d04548119b3b7d.jpg?ver=1754549810)
    
    Jeffery Liu
    
    [2023年11月3日](https://js2panda.com/clash-load-balance#comment-600)
    
    我的proxies有四个组，auto、proxy、散列、轮询，但是我选择不了轮询，我的proxy组里面没有散列和轮询给我选择请问是为什么呢？
    
21.  ![](https://js2panda.com/wp-content/litespeed/avatar/db2d81e60d6b9ce0a0fead8eae109c8d.jpg?ver=1754549809)
    
    Jeffery Liu
    
    [2023年11月3日](https://js2panda.com/clash-load-balance#comment-601)
    
    轮询和散列没有进入到我规则模式里proxy组里，一直在auto完全无法锁定选择这个怎么解决呢？
    
22.  ![](https://js2panda.com/wp-content/litespeed/avatar/09b78a9d8cdba7b7e8ae7ad5f600e382.jpg?ver=1754549809)
    
    alex
    
    [2024年3月9日](https://js2panda.com/clash-load-balance#comment-792)
    
    感谢！学会了很多东西
    
23.  ![](https://js2panda.com/wp-content/litespeed/avatar/6f59806d2308351e71bd7e47358b9515.jpg?ver=1754549808)
    
    11111
    
    [2024年3月10日](https://js2panda.com/clash-load-balance#comment-793)
    
    你好，博主，我按照你的设置设置后，只有负载均衡-散列，没有负载均衡-轮询，请问是什么原因呢？
    
24.  ![](https://js2panda.com/wp-content/litespeed/avatar/aaf0a536d1fc4609dccc92c43ef25780.jpg?ver=1754549808)
    
    哈哈哈哈
    
    [2024年5月7日](https://js2panda.com/clash-load-balance#comment-975)
    
    是否会导致流量的增加呢？毕竟一个网页会通过多节点请求
    
    1.  ![](https://js2panda.com/wp-content/litespeed/avatar/51ca037d08d9fafce17b2bc1f842b2df.jpg?ver=1754549810)
        
        胖橙
        
        [2024年5月13日](https://js2panda.com/clash-load-balance#comment-995)
        
        不会，因为请求量是一定的。
        
25.  ![](https://js2panda.com/wp-content/litespeed/avatar/e0cc6f7502bb16ad21f95247981a521a.jpg?ver=1754546599)
    
    Rhine\_JTG
    
    [2024年12月11日](https://js2panda.com/clash-load-balance#comment-1267)
    
    好用，均衡负载可以跑到千兆
    
26.  Clash 报错 invalid mode: redir-host \[Could not switch to this profile\] – 胖橙博客
    
    [2025年3月13日](https://js2panda.com/clash-load-balance#comment-1328)
    
    \[…\] 灯塔Cloud 配置 Clash 负载均衡的时候出现了这个错误提示：\[Could not switch to this profile\] nvalid mode: \[…\]
    

[如何在 Vultr 上一键部署 ShadowSocks 实现科学上网？](https://js2panda.com/vultr-ss)

[【2024年】V2rayN 和 Clash 客户端哪个好用？机场小白应该如何选择？](https://js2panda.com/v2rayn-clash)

Copyright © 2019-2023 [胖橙的个人博客](https://jiasupanda.com/)

↑↓⇔⇧⇩