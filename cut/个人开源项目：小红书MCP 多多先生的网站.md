# 个人开源项目：小红书MCP | 多多先生的网站
[个人开源项目：小红书MCP | 多多先生的网站](https://www.haha.ai/xiaohongshu-mcp) 

 个人开源项目：小红书MCP | 多多先生的网站

Constants loaded at 2025-09-04T04:34:16.159Z

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F8b7bcc12-ac64-4b23-bcbe-3f647b01c342%2Favatar.jpg?table=collection&id=ad77e944-ddc1-4f0f-b114-815ae60b209f&t=ad77e944-ddc1-4f0f-b114-815ae60b209f&width=1080&cache=v2)

多多先生的网站

[首页](/)

我的项目

*   [ 满分简历](https://cvmax.cn/)
*   [Product Hunt 每日热榜](https://product-daily.haha.ai/)

[关于我](/about)

zouying | 您好，世界！
================

41

![](https://www.notion.so/images/page-cover/rijksmuseum_mignons_1660.jpg)

技术分享

[

思考

](/tag/%E6%80%9D%E8%80%83)[

技术笔记

](/tag/%E6%8A%80%E6%9C%AF%E7%AC%94%E8%AE%B0)

🔥个人开源项目：小红书MCP

字数 604阅读时长≈ 2 分钟

[2025-8-10](/archive#2025-08)

2025-8-17

### 

[](#24bea16ee26a80059dbefa19c2205bce "1. 项目初衷")1\. 项目初衷

一直在使用 Claude Code 作为开发工具，后来跟同事聊，一致觉得 Claude Code 更是一个通用的个人助手。（可以关注大佬的小红书）。

![](https://www.notion.so/image/attachment%3Af92685f9-19be-4853-b5e2-178938f228f8%3ACleanShot_2025-08-10_at_18.18.322x.png?table=block&id=24bea16e-e26a-803b-a18e-e1909c7cc1c2&t=24bea16e-e26a-803b-a18e-e1909c7cc1c2)

小红书的流量也比较有价值，也有助于打造个人IP，所以就想尝试一下能不能让 Claude Code 把小红书自动化运营起来，并且能够吸引一部分流量。

为此，就做了这个开源小项目：[

xiaohongshu-mcp

Github

xiaohongshu-mcp

Owner

xpzouying

Updated

Aug 18, 2025

![](https://img.shields.io/github/stars/xpzouying/xiaohongshu-mcp?logo=github)
![](https://img.shields.io/github/last-commit/xpzouying/xiaohongshu-mcp)






](https://github.com/xpzouying/xiaohongshu-mcp)

![](https://www.notion.so/image/attachment%3Acb2ad02d-7d1c-49bb-9195-79975f4daae9%3Aimage.png?table=block&id=24bea16e-e26a-807c-a2fb-ffdc0146d1e3&t=24bea16e-e26a-807c-a2fb-ffdc0146d1e3)

[](#24bea16ee26a80bbb01dfa5219b46b45 "2. 小红书MCP")2\. 小红书MCP
-------------------------------------------------------------

基本思路实际上很简单：

1.  获取内容或者让 Claude Code 自己调研。Claude Code 很强，很多东西可以自动就完成。

2.  让 Claude Code 调用 xiaohongshu-mcp 完成发布。

下面演示 Claude Code 调用 xiaohongshu-mcp 的发布。

### 

[](#24bea16ee26a8071b4cfe8b34a0d5d11 "2.1. Claude Code 调度")2.1. Claude Code 调度

发布结果：

![](https://www.notion.so/image/attachment%3A0023c1e9-68bc-4e4a-82ec-e6e6f72572f9%3APicsew_20250810170022.jpeg?table=block&id=24bea16e-e26a-8036-a69c-efb1cb822621&t=24bea16e-e26a-8036-a69c-efb1cb822621)

测试账号的结果

是不是很简单。。。

**0818补充：** 

搜索示例：

### plain

```


`帮我使用 xiaohongshu-mcp 搜索一下：Claude MCP，告诉我点赞数最高的帖子的信息。`
```

Plain text

Copy

### 

[](#24bea16ee26a8007aeaaedfb08db47e7 "2.2. 一周左右的小红书流量效果")2.2. 一周左右的小红书流量效果

使用一个新的账号，自动化测试了差不多一周左右，90%+ 是自动化运行。

![](https://www.notion.so/image/attachment%3Ad2e10b2a-61fb-44be-bfa7-4d65fa56bdbe%3Aimage.png?table=block&id=24dea16e-e26a-800d-874f-ddedd23d428b&t=24dea16e-e26a-800d-874f-ddedd23d428b)

我是 996

#### 

[](#24bea16ee26a8009b7e7ed2f68f040e1 "a. 第一天：千赞完成")a. 第一天：千赞完成

第一天就完成了千赞的成就。

![](https://www.notion.so/image/attachment%3A7e3dd7e0-8f19-4601-80c8-a1694d66b20f%3ACleanShot_2025-08-10_at_18.53.382x.png?table=block&id=24bea16e-e26a-8020-84c2-f6b0e9064de0&t=24bea16e-e26a-8020-84c2-f6b0e9064de0)

#### 

[](#24bea16ee26a8092a5d1ed0193640acc "b. 一周左右总成果")b. 一周左右总成果

![](https://www.notion.so/image/attachment%3A1a2a9cad-88a1-42f7-a111-4b4d664a9183%3Aimage.png?table=block&id=24bea16e-e26a-8004-b939-d7f9996aeaae&t=24bea16e-e26a-8004-b939-d7f9996aeaae)

我就是无情的搬运工

*   总共 6000+ 赞+收藏。感觉这种自动化的流程差不多跑通了。

*   前几天效果比较好，每天差不多 1000 左右的赞+收藏。不过感觉流量不太稳定，有可能是某一篇文章突然就爆发了，很受欢迎。

*   白嫖小红书流量有风险，发布的内容有可能会被标记为 “疑似AI生成”，导致没有流量。

### 

[](#24dea16ee26a803f9a55de8f4954ac17 "2.3. （更新）小红书的创作者周报")2.3. （更新）小红书的创作者周报

![](https://www.notion.so/image/attachment%3A72891c96-cdeb-4332-9e18-757af3312231%3Aimage.png?table=block&id=24dea16e-e26a-8069-9c0f-ed23e7b546da&t=24dea16e-e26a-8069-9c0f-ed23e7b546da)

![](https://www.notion.so/image/attachment%3Af0f0cb0d-54e9-4671-9d72-f2b4b225a18d%3Aimage.png?table=block&id=24dea16e-e26a-8068-bf55-d3931940ddbc&t=24dea16e-e26a-8068-bf55-d3931940ddbc)

连续测试了两周，第二周实际上有点放缓，不过依然发帖超越了 100% 的同城作者（我只是无情的搬运工）。

**暂时停掉了全自动化运营的流程，寻找其他的好玩的小工具。** 

[](#24bea16ee26a809b87f3dabcf1e45078 "3. xiaohongshu-mcp")3\. xiaohongshu-mcp
-------------------------------------------------------------------------------

目前主要是辅助我完成小红书自动化运营，所以 MCP 的功能主要集中在：

登录

图文发布

小红书搜索

刷 feed 流

其他类型的发布

[

上一篇

注册 Hetzner

](/register-hetzner)[

下一篇

Caddy 使用泛域名证书

](/caddy-tls)

[

下一篇

* * *

Caddy 使用泛域名证书

](/caddy-tls)

微信扫码分享

*   **作者:**[zouying](/about)
*   **链接:**[https://www.haha.ai/xiaohongshu-mcp](https://www.haha.ai/xiaohongshu-mcp)
*   **声明:**本文采用 CC BY-NC-SA 4.0 许可协议，转载请注明出处。

相关文章

[

安装配置 Coolify

![](https://images.unsplash.com/photo-1649783465020-1e0c6f9ced0e?ixlib=rb-4.1.0&q=50&fm=webp&crop=entropy&cs=srgb&t=251ea16e-e26a-804c-9bce-ee6210e270f8&width=1080&fmt=webp)



](/install-coolify "安装配置 Coolify")[

注册 Hetzner

![](https://images.unsplash.com/photo-1544197150-b99a580bb7a8?ixlib=rb-4.1.0&q=50&fm=webp&crop=entropy&cs=srgb&t=24fea16e-e26a-80bb-83ed-fb6255ff75e3&width=1080&fmt=webp)



](/register-hetzner "注册 Hetzner")[

Caddy 使用泛域名证书

![](https://images.unsplash.com/photo-1471899236350-e3016bf1e69e?ixlib=rb-4.1.0&q=50&fm=webp&crop=entropy&cs=srgb&t=179ea16e-e26a-8084-92cf-d79668d94ffd&width=1080&fmt=webp)



](/caddy-tls "Caddy 使用泛域名证书")[

\[论文翻译\] - 如何阅读一篇论文 / How to Read a Paper

![](https://images.unsplash.com/photo-1520004434532-668416a08753?ixlib=rb-4.0.3&q=50&fm=webp&crop=entropy&cs=srgb&t=d057773c-827e-49ae-ba56-7975286b1ba5&width=1080&fmt=webp)



](/how-to-read-a-paper "[论文翻译] - 如何阅读一篇论文 / How to Read a Paper")[

Go 项目模板 （整洁架构版）

![](https://www.notion.so/images/page-cover/gradients_8.png)



](/go-clean-code-template "Go 项目模板 （整洁架构版）")[

实现微信支付接入

![](https://images.unsplash.com/photo-1556741533-411cf82e4e2d?ixlib=rb-4.0.3&q=50&fm=webp&crop=entropy&cs=srgb&t=650b5fcc-cc20-4af5-b281-3911442c6e2e&width=1080&fmt=webp)



](/how-to-use-wepay "实现微信支付接入")

* * *

评论

*   Twikoo

昵称

邮箱

网址

0/500

*   OωO
*   |´・ω・)ノ
*   ヾ(≧∇≦\*)ゝ
*   (☆ω☆)
*   （╯‵□′）╯︵┴─┴
*   ￣﹃￣
*   (/ω＼)
*   ∠( ᐛ 」∠)＿
*   (๑•̀ㅁ•́ฅ)
*   →\_→
*   ୧(๑•̀⌄•́๑)૭
*   ٩(ˊᗜˋ\*)و
*   (ノ°ο°)ノ
*   (´இ皿இ｀)
*   ⌇●﹏●⌇
*   (ฅ´ω\`ฅ)
*   (╯°A°)╯︵○○○
*   φ(￣∇￣o)
*   ヾ(´･ ･｀｡)ノ"
*   ( ง ᵒ̌皿ᵒ̌)ง⁼³₌₃
*   (ó﹏ò｡)
*   Σ(っ °Д °;)っ
*   ( ,,´･ω･)ﾉ"(´っω･｀｡)
*   ╮(╯▽╰)╭
*   o(\*////▽////\*)q
*   ＞﹏＜
*   ( ๑´•ω•) "(ㆆᴗㆆ)

*   😂
*   😀
*   😅
*   😊
*   🙂
*   🙃
*   😌
*   😍
*   😘
*   😜
*   😝
*   😏
*   😒
*   🙄
*   😳
*   😡
*   😔
*   😫
*   😱
*   😭
*   💩
*   👻
*   🙌
*   🖕
*   👍
*   👫
*   👬
*   👭
*   🌚
*   🌝
*   🙈
*   💊
*   😶
*   🙏
*   🍦
*   🍉
*   😣

*   ![](https://owo.imaegoo.com/bilibili/6ea59c827c414b4a2955fe79e0f6fd3dcd515e24.png)
    
*   ![](https://owo.imaegoo.com/bilibili/a8111ad55953ef5e3be3327ef94eb4a39d535d06.png)
    
*   ![](https://owo.imaegoo.com/bilibili/bb690d4107620f1c15cff29509db529a73aee261.png)
    
*   ![](https://owo.imaegoo.com/bilibili/180129b8ea851044ce71caf55cc8ce44bd4a4fc8.png)
    
*   ![](https://owo.imaegoo.com/bilibili/b9cbc755c2b3ee43be07ca13de84e5b699a3f101.png)
    
*   ![](https://owo.imaegoo.com/bilibili/34ba3cd204d5b05fec70ce08fa9fa0dd612409ff.png)
    
*   ![](https://owo.imaegoo.com/bilibili/34db290afd2963723c6eb3c4560667db7253a21a.png)
    
*   ![](https://owo.imaegoo.com/bilibili/9e55fd9b500ac4b96613539f1ce2f9499e314ed9.png)
    
*   ![](https://owo.imaegoo.com/bilibili/09dd16a7aa59b77baa1155d47484409624470c77.png)
    
*   ![](https://owo.imaegoo.com/bilibili/fe1179ebaa191569b0d31cecafe7a2cd1c951c9d.png)
    
*   ![](https://owo.imaegoo.com/bilibili/9f996894a39e282ccf5e66856af49483f81870f3.png)
    
*   ![](https://owo.imaegoo.com/bilibili/241ee304e44c0af029adceb294399391e4737ef2.png)
    
*   ![](https://owo.imaegoo.com/bilibili/1f0b87f731a671079842116e0991c91c2c88645a.png)
    
*   ![](https://owo.imaegoo.com/bilibili/093c1e2c490161aca397afc45573c877cdead616.png)
    
*   ![](https://owo.imaegoo.com/bilibili/23269aeb35f99daee28dda129676f6e9ea87934f.png)
    
*   ![](https://owo.imaegoo.com/bilibili/d04dba7b5465779e9755d2ab6f0a897b9b33bb77.png)
    
*   ![](https://owo.imaegoo.com/bilibili/a37683fb5642fa3ddfc7f4e5525fd13e42a2bdb1.png)
    
*   ![](https://owo.imaegoo.com/bilibili/7cfa62dafc59798a3d3fb262d421eeeff166cfa4.png)
    
*   ![](https://owo.imaegoo.com/bilibili/70dc5c7b56f93eb61bddba11e28fb1d18fddcd4c.png)
    
*   ![](https://owo.imaegoo.com/bilibili/90cf159733e558137ed20aa04d09964436f618a1.png)
    
*   ![](https://owo.imaegoo.com/bilibili/0d15c7e2ee58e935adc6a7193ee042388adc22af.png)
    

*   颜文字
*   Emoji
*   Bilibili

[](https://guides.github.com/features/mastering-markdown/)预览 发送

2 条评论

![](https://weavatar.com/avatar/8051e512b6af15648f4ad8f9b9688486?d=initials&name=TTSSHH)

**TTSSHH** 1 天前

[](#)[1](#)

会被封禁吗？

 macOS 15.5.0

 Chrome 139.0.0.0

![](https://weavatar.com/avatar/a03479d1995b24d43366b30f3d957f2c?d=initials&name=ZY)

[**ZY**](https://haha.ai) 1 天前

回复 [@TTSSHH](#4bf4d2ccd7884592b5132c309a6a58f1) :

从账号自动化的角度上说，不太会。  
这套流程我已经在内部跑了一年多了，很稳定。  
我改造成 MCP 服务后，也已经稳定运行数周。

从爬虫的检测技术角度来说，小红书肯定会有多角度来审核你的账号或者内容，比如：  
如果你账号一分钟刷新成千上万次，就很容易被检测出来，这个可以通过 账号/IP 访问的频次来推测是否是爬虫。

但是如果你发帖的话，大概率不会，小红书一天也只让你发送50篇文章，量级根本达不到检测阈值。

 macOS 15.6.1

 Chrome 139.0.0.0

![](https://weavatar.com/avatar/a03479d1995b24d43366b30f3d957f2c?d=initials&name=ZY)

[**ZY**](https://haha.ai) 2025-08-16

测试一下
====

 macOS 15.6.0

 Chrome 139.0.0.0

Powered by [Twikoo](https://twikoo.js.org) v1.6.44

[](#)

Twikoo 评论管理

密码

登录

目录

[1\. 项目初衷](#24bea16ee26a80059dbefa19c2205bce)[2\. 小红书MCP](#24bea16ee26a80bbb01dfa5219b46b45)[2.1. Claude Code 调度](#24bea16ee26a8071b4cfe8b34a0d5d11)[2.2. 一周左右的小红书流量效果](#24bea16ee26a8007aeaaedfb08db47e7)[a. 第一天：千赞完成](#24bea16ee26a8009b7e7ed2f68f040e1)[b. 一周左右总成果](#24bea16ee26a8092a5d1ed0193640acc)[2.3. （更新）小红书的创作者周报](#24dea16ee26a803f9a55de8f4954ac17)[3\. xiaohongshu-mcp](#24bea16ee26a809b87f3dabcf1e45078)

你好！我是 ZOUYING

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F8b7bcc12-ac64-4b23-bcbe-3f647b01c342%2Favatar.jpg?table=collection&id=ad77e944-ddc1-4f0f-b114-815ae60b209f&t=ad77e944-ddc1-4f0f-b114-815ae60b209f&width=1080&cache=v2)

zouying
-------

**🎉个人项目🎉**

**[\[满分简历\]](https://cvmax.cn)**

**[\[Product Hunt 日报\]](https://product-daily.haha.ai/)**

**🎉个人博客🎉**

**\--- 生活 ---**

分享好用的工具

**\--- 工作 ---**

分享工作的经验

**\--- 学习 ---**

记录个人学习的记录

[

了解更多



](https://www.tangly1024.com)

目录

[1\. 项目初衷](#24bea16ee26a80059dbefa19c2205bce)[2\. 小红书MCP](#24bea16ee26a80bbb01dfa5219b46b45)[2.1. Claude Code 调度](#24bea16ee26a8071b4cfe8b34a0d5d11)[2.2. 一周左右的小红书流量效果](#24bea16ee26a8007aeaaedfb08db47e7)[a. 第一天：千赞完成](#24bea16ee26a8009b7e7ed2f68f040e1)[b. 一周左右总成果](#24bea16ee26a8092a5d1ed0193640acc)[2.3. （更新）小红书的创作者周报](#24dea16ee26a803f9a55de8f4954ac17)[3\. xiaohongshu-mcp](#24bea16ee26a809b87f3dabcf1e45078)

交流频道
----

### 加入我们的社群讨论分享

[

点击加入社群

](https://docs.tangly1024.com/article/how-to-question)

最新发布

[

![](https://images.unsplash.com/photo-1676299081847-824916de030a?ixlib=rb-4.1.0&q=50&fm=webp&crop=entropy&cs=srgb&t=0fe8d9a0-5047-4f16-ac73-98b38bf16ca5&width=1080&fmt=webp)

使用苹果内购开通 ChatGPT Plus

2025-8-24





](/chatgpt-plus-by-apple "使用苹果内购开通 ChatGPT Plus")[

![](https://images.unsplash.com/photo-1649783465020-1e0c6f9ced0e?ixlib=rb-4.1.0&q=50&fm=webp&crop=entropy&cs=srgb&t=251ea16e-e26a-804c-9bce-ee6210e270f8&width=1080&fmt=webp)

安装配置 Coolify

2025-8-24





](/install-coolify "安装配置 Coolify")[

![](https://images.unsplash.com/photo-1544197150-b99a580bb7a8?ixlib=rb-4.1.0&q=50&fm=webp&crop=entropy&cs=srgb&t=24fea16e-e26a-80bb-83ed-fb6255ff75e3&width=1080&fmt=webp)

注册 Hetzner

2025-8-24





](/register-hetzner "注册 Hetzner")[

![](https://images.unsplash.com/photo-1621768216002-5ac171876625?ixlib=rb-4.1.0&q=50&fm=webp&crop=entropy&cs=srgb&t=256ea16e-e26a-8037-ba76-e50b9bd5d38c&width=1080&fmt=webp)

苹果美区礼品卡购买方式

2025-8-21





](/apple-us-gift-card "苹果美区礼品卡购买方式")[

![](https://images.unsplash.com/photo-1504194104404-433180773017?ixlib=rb-4.0.3&q=50&fm=webp&crop=entropy&cs=tinysrgb&t=002afff7-a3fd-4c4d-8939-0f698810d54c&width=1080&fmt=webp)

搭建家庭的科学上网方案

2025-8-18





](/guide-to-home-network "搭建家庭的科学上网方案")[

![](https://www.notion.so/images/page-cover/rijksmuseum_mignons_1660.jpg)

个人开源项目：小红书MCP

2025-8-17





](/xiaohongshu-mcp "个人开源项目：小红书MCP")

[

技术笔记

20

](/tag/%E6%8A%80%E6%9C%AF%E7%AC%94%E8%AE%B0)[

生活

6

](/tag/%E7%94%9F%E6%B4%BB)[

系统架构

3

](/tag/%E7%B3%BB%E7%BB%9F%E6%9E%B6%E6%9E%84)[

思考

2

](/tag/%E6%80%9D%E8%80%83)

* * *

文章数:

27

建站天数:

891 天

访问量:

访客数:

  

Powered by[NotionNext 4.9.0](https://github.com/tangly1024/NotionNext).

2023-2025[zouying](/about) | 您好，世界！

↑↓⇔⇧⇩