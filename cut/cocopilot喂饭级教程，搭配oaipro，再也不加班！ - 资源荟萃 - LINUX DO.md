# cocopilot喂饭级教程，搭配oaipro，再也不加班！ - 资源荟萃 - LINUX DO
 cocopilot喂饭级教程，搭配oaipro，再也不加班！ - 资源荟萃 - LINUX DO                                                

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
*   [网络记忆](/c/feeds/92 "网络是有记忆的，确信！")
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

[cocopilot喂饭级教程，搭配oaipro，再也不加班！](/t/topic/182313)


===================================================

[资源荟萃](/c/resource/14)

[人工智能](/tag/人工智能)

,[Copilot](/tag/copilot)

,[精华神帖](/tag/精华神帖)

您已选择 **0** 个帖子。

全选

取消选择

​

[2024 年 8月](/t/topic/182313/1 "跳到第一个帖子")

1 / 347

2024 年 8月

[3 天 前](/t/topic/182313/354)

热门回复 ​

[![](https://linux.do/user_avatar/linux.do/hashnode/96/15_2.png)
](/u/hashnode)

[浪里小白条](/u/hashnode)

[hashnode](/u/hashnode)一元复始

6

[2024 年 8月](/t/topic/182313?u=niyan2025 "发布日期")

[](#p-1516667-h-1-1)1 克隆项目
==========================

```


`git clone https://github.com/linux-do/override.git` 
```

[](#p-1516667-h-2-2)2 部署方式
==========================

cocoliot支持docker部署、本地部署，linux、window都可以使用。

[](#p-1516667-h-21-docker-3)2.1 方式一 docker部署(推荐)
------------------------------------------------

### [](#p-1516667-h-211-configjson-4)2.1.1 设置 config.json

复制config.json.example为config.json  

[![](https://linux.do/uploads/default/optimized/3X/9/9/99626afb5faf3b6c065ba58bad37673e677cba05_2_690x406.png)

image1057×623 38.7 KB

](https://linux.do/uploads/default/original/3X/9/9/99626afb5faf3b6c065ba58bad37673e677cba05.png "image")

编辑config.json

```


`{
 "bind": "0.0.0.0:8181",
  "proxy_url": "",
  "timeout": 600,
  "codex_api_base": "https://api.oaipro.com/v1",
  "codex_api_key": "sk-xxx替换成自己的key",
  "codex_api_organization": "",
  "codex_api_project": "",
  "codex_max_tokens": 500,
  "code_instruct_model": "gpt-3.5-turbo-instruct",
  "chat_api_base": "https://api.oaipro.com/v1",
  "chat_api_key": "sk-xxx替换成自己的key",
  "chat_api_organization": "",
  "chat_api_project": "",
  "chat_max_tokens": 4096,
  "chat_model_default": "gpt-4o-mini",
  "chat_model_map": {},
  "chat_locale": "zh_CN",
  "auth_token": ""
}` 
```

上面的codex\_api\_key和chat\_api\_key 从 [New API](https://api.oaipro.com/token)

获取。建议这里使用oaipro，使用deepseek速度太慢，影响编程体验。  
如果你想使用deepseek的代码补全和聊天，可以使用如下配置：

```


`{
 "bind": "0.0.0.0:8181",
 "proxy_url": "",
 "timeout": 600,
 "codex_api_base": "https://api.deepseek.com/beta/v1",
 "codex_api_key": "sk-你自己的deepseek key",
 "codex_api_organization": "",
 "codex_api_project": "",
 "codex_max_tokens": 500,
 "code_instruct_model": "deepseek-coder",
 "chat_api_base": "https://api.deepseek.com/beta/v1",
 "chat_api_key": "sk-你自己的deepseek key",
 "chat_api_organization": "",
 "chat_api_project": "",
 "chat_max_tokens": 4096,
 "chat_model_default": "deepseek-coder",
 "chat_model_map": {},
 "chat_locale": "zh_CN",
 "auth_token": ""
}` 
```

> 注意：上面的auth\_token不建议设置

### [](#p-1516667-h-212-docker-compose-5)2.1.2 docker compose

1.  修改 docker-compose.yaml 的配置文件路径
    
    ```
    
    
    `services:
      override-app:
        image: linux-do/override:latest
        container_name: override-app
        restart: always
        build:
            context: .
            dockerfile: Dockerfile
        volumes:
          - ./config.json:/app/config.json
        ports:
            - "8181:8181"` 
    ```
    
2.  部署项目
    
    ```
    
    
    `docker compose up -d
    
    docker  ps` 
    ```
    
3.  完成 override 部署  
    ![](https://linux.do/uploads/default/original/3X/9/2/92f71ac55a4a011cf2d8ec54a9ae7a843ccd3768.png)
    
4.  访问ip:端口
    

[![](https://linux.do/uploads/default/original/3X/d/1/d103e5c2784fe4379bead04239e961081f1b4fb0.png)

image602×166 3.44 KB

](https://linux.do/uploads/default/original/3X/d/1/d103e5c2784fe4379bead04239e961081f1b4fb0.png "image")

出现上图所示，表示部署成功。

[](#p-1516667-h-22-6)2.2 方式二 本地编译部署
-----------------------------------

支持所有平台 (Windows、Linux、Mac)，下面使用Windows说明

1.  准备工作，系统需要安装 golang >= 1.21 (低于该版本需要修改 go.mod)
    
2.  克隆 `override` 到本地
    
3.  编译
    
    ```
    
    
    `override` 
    ```
    
    ```
    
    
    `cd override
    go mod tidy
    go build .` 
    ```
    
4.  编译完成后，会在override目录下生成一个可执行文件 `override.exe`
    
5.  新建配置文件 `config.json`，放在override目录下
    
6.  双击启动 override.exe 即可
    

[](#p-1516667-h-23-gui-7)2.3 方式三 本地GUI部署
----------------------------------------

### [](#p-1516667-h-231-windows-8)2.3.1 windows系统安装

地址： [Release Override-Gui · xifan2333/override-gui · GitHub](https://github.com/xifan2333/override-gui/releases/tag/v0.0.1)

[![](https://linux.do/uploads/default/original/3X/7/e/7ed35d1efba55e0e2a0fe6b1c8fcd6b4c2a17f9a.png)

image686×500 19.1 KB

](https://linux.do/uploads/default/original/3X/7/e/7ed35d1efba55e0e2a0fe6b1c8fcd6b4c2a17f9a.png "image")

使用方法

启动 exe，填入api-key，复制 vscode 配置到 setting.json，立即使用。

### [](#p-1516667-h-232-mac-9)2.3.2 mac系统安装

[github.com](https://github.com/duolabmeng6/overrideManager)

![](https://linux.do/uploads/default/optimized/4X/b/d/d/bdd17046b15c0098fa402227258501f52f470f7f_2_690x344.png)

### [GitHub - duolabmeng6/overrideManager](https://github.com/duolabmeng6/overrideManager)

通过在 GitHub 上创建帐户来为 duolabmeng6/overrideManager 开发做出贡献。

[![](https://linux.do/uploads/default/original/3X/b/7/b7b26cffabb8f71df8d3e72276bdd7db991bf90c.png)

image557×500 28.8 KB

](https://linux.do/uploads/default/original/3X/b/7/b7b26cffabb8f71df8d3e72276bdd7db991bf90c.png "image")

[](#p-1516667-h-3-jetbrains-copilot-10)3 JetBrains 安装copilot
============================================================

[](#p-1516667-h-31-copilot-11)3.1 下载copilot
-------------------------------------------

注意：Github Copilot 插件版本为 **<=1.5.8.5775**

插件下载地址：

![](https://linux.do/uploads/default/original/3X/8/2/8212b601a3d0a1c57f0929a5117b8b03a5723125.png)
 [JetBrains Marketplace](https://plugins.jetbrains.com/plugin/17718-github-copilot/versions)

![](https://linux.do/uploads/default/original/4X/b/3/f/b3f7966efdafd0f9d2349b4e35fad60c9a1a4841.png)

### [GitHub Copilot - IntelliJ IDEs Plugin | Marketplace](https://plugins.jetbrains.com/plugin/17718-github-copilot/versions)

What’s GitHub CopilotGitHub Copilot is your AI-powered coding assistant, offering assistance throughout your software development journey. Leveraging large language...

[![](https://linux.do/uploads/default/optimized/3X/b/2/b27b99178cb75c7621944eac0c89cfb6d33a279d_2_690x409.png)

image1585×941 69.5 KB

](https://linux.do/uploads/default/original/3X/b/2/b27b99178cb75c7621944eac0c89cfb6d33a279d.png "image")

[](#p-1516667-h-32-copilot-12)3.2 手动安装copilot
---------------------------------------------

[![](https://linux.do/uploads/default/optimized/3X/e/b/ebda3fd3314b5a0e20e80ad7095573e88735d3fc_2_690x481.png)

image1275×889 93.3 KB

](https://linux.do/uploads/default/original/3X/e/b/ebda3fd3314b5a0e20e80ad7095573e88735d3fc.png "image")

[](#p-1516667-h-33-authentication-provider-13)3.3 设置 Authentication Provider
----------------------------------------------------------------------------

安装完成后设置github的Authentication Provider 为 [cocopilot.org](http://cocopilot.org)

[![](https://linux.do/uploads/default/optimized/3X/e/a/ea05b983a8d3bcf148811f812d34bc9320f345bb_2_690x484.png)

image1267×890 72.5 KB

](https://linux.do/uploads/default/original/3X/e/a/ea05b983a8d3bcf148811f812d34bc9320f345bb.png "image")

[](#p-1516667-h-34-env-14)3.4 设置env
-----------------------------------

### [](#p-1516667-h-341-env-15)3.4.1 使用脚本设置env

[![](https://linux.do/uploads/default/optimized/3X/f/c/fc1a34d303e2b7acae8e6a4023d7bbc418dfe7ed_2_690x317.png)

image1058×487 30.9 KB

](https://linux.do/uploads/default/original/3X/f/c/fc1a34d303e2b7acae8e6a4023d7bbc418dfe7ed.png "image")

如果使用的windows系统，打开install-all-users.vbs,设置baseUrl为你自己部署的url(其他系统也类似)

[![](https://linux.do/uploads/default/optimized/3X/0/5/05483a344865600d76d2bcc1b0af069007f40639_2_690x272.png)

image1594×629 30.8 KB

](https://linux.do/uploads/default/original/3X/0/5/05483a344865600d76d2bcc1b0af069007f40639.png "image")

运行脚本

[![](https://linux.do/uploads/default/original/3X/e/2/e2499bd0ae4a4b89a7482bb67a60b08fddbaccc2.png)

image379×188 2.76 KB

](https://linux.do/uploads/default/original/3X/e/2/e2499bd0ae4a4b89a7482bb67a60b08fddbaccc2.png "image")

出现Done说明设置成功

[![](https://linux.do/uploads/default/original/3X/f/1/f19a92e4d21844fb447460b965a8d803b91a02e3.png)

image130×150 676 Bytes

](https://linux.do/uploads/default/original/3X/f/1/f19a92e4d21844fb447460b965a8d803b91a02e3.png "image")

在JetBrains中愉快使用吧(windows中 alt + \\ 生成提示)

[![](https://linux.do/uploads/default/optimized/3X/7/6/76017e497f916c594bab5e7aed36c920a9621817_2_690x448.png)

image901×585 46.4 KB

](https://linux.do/uploads/default/original/3X/7/6/76017e497f916c594bab5e7aed36c920a9621817.png "image")

### [](#p-1516667-h-342-env-16)3.4.2 使用插件设置env(未验证)

![](https://linux.do/user_avatar/linux.do/neo/48/12_2.png)
 [plugin-env：为了这点醋才包的这顿饺子](https://linux.do/t/topic/95672)

[开发调优](/c/develop/4)

> 大家应该都知道了，昨天我又撅了 GitHub Copilot 一次：[CoCopilot 重大更新](https://linux.do/t/topic/94939)
> 
> 不过根据佬友们的反馈，由于 JetBrains 系列IDE需要设置环境变量，而使用脚本设置根据平台不同还有所区别。总之非常麻烦还可能没生效。 所以我就为了这点醋包了顿饺子，连忙搓了个 ja-netfilter 插件：plugin-env 这下使用 ja-netfilter 的佬友再也不用为环…

[](#p-1516667-h-4-vscodecopilot-17)4 VSCode中安装使用Copilot
=======================================================

[](#p-1516667-h-41-vscode-copilot-18)4.1 劫持VSCode Copilot插件：
------------------------------------------------------------

**1\. 打开Copilot插件设置——>扩展设置**

[![](https://linux.do/uploads/default/original/3X/1/6/16893e622ef87b353d376237570010822e93a6a2.png)

image679×212 18.1 KB

](https://linux.do/uploads/default/original/3X/1/6/16893e622ef87b353d376237570010822e93a6a2.png "image")

**2\. 在json文件中编辑：** 

[![](https://linux.do/uploads/default/original/3X/e/1/e15096821aeb6f245917c2bafebadba238ae3e2c.png)

image682×424 19.4 KB

](https://linux.do/uploads/default/original/3X/e/1/e15096821aeb6f245917c2bafebadba238ae3e2c.png "image")

对应部分的配置内容如下(自行换成自己部署的url)：

```


 `"github.copilot.advanced": {
    "debug.overrideCAPIUrl": "http://127.0.0.1:8181/v1",
    "debug.overrideProxyUrl": "http://127.0.0.1:8181",
    "debug.chatOverrideProxyUrl": "http://127.0.0.1:8181/v1/chat/completions",
    "authProvider": "github-enterprise"
  },
  "github-enterprise.uri": "https://cocopilot.org"` 
```

保存后重启VSCode

**3\. 登录Copilot插件：** 

[![](https://linux.do/uploads/default/original/3X/c/a/cadf5d89050da4240e0bb473405ec0ee97bb14a7.png)

image779×435 26.8 KB

](https://linux.do/uploads/default/original/3X/c/a/cadf5d89050da4240e0bb473405ec0ee97bb14a7.png "image")

复制并访问Github

[![](https://linux.do/uploads/default/original/3X/2/6/26afa08843b8b1d472fa8efdf6c9c1fef77fab01.png)

image598×219 13 KB

](https://linux.do/uploads/default/original/3X/2/6/26afa08843b8b1d472fa8efdf6c9c1fef77fab01.png "image")

浏览器中直接粘贴刚刚的代码

[![](https://linux.do/uploads/default/original/3X/7/c/7cb4f163164349e75cf993edc288d2a16bdb7880.png)

image590×557 15.1 KB

](https://linux.do/uploads/default/original/3X/7/c/7cb4f163164349e75cf993edc288d2a16bdb7880.png "image")

点击Continue即可跳转Linux Do的授权页面，点击授权就可以登录成功。  
同样的，Copilot Chat 插件也会自动提示，再按照上面的步骤登录一遍即可。然后就可以和你的DeepSeek愉快的玩耍了。

> 参考链接
> 
> [Override 搭配 DeepSeek Coder 详细搭建过程，Docker、本地编译方式 - 在线辅导解答](https://linux.do/t/topic/160633)
> 
> [【保姆级】经过几个小时的学习和折腾终于用上了DeepSeek版的Override](https://linux.do/t/topic/160845)
> 
> [plugin-env：为了这点醋才包的这顿饺子](https://linux.do/t/topic/95672)
> 
> [override-gui | 填上api-key，立即使用 deepseek 版 cocopilot](https://linux.do/t/topic/168827/1)
> 
> [override-gui | 填上api-key，立即使用 deepseek 版 cocopilot - #57，来自 duolabmeng6](https://linux.do/t/topic/168827/57)
> 
> [override-gui | 填上api-key，立即使用 deepseek 版 cocopilot - #57，来自 duolabmeng6](https://linux.do/t/topic/168827/57)

  

1 个回复

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

+1

![](https://linux.do/images/emoji/twemoji/clap.png?v=14)

clap

910

​ ​ 回复

*   [jetbrain全家桶还是不能用新版的copilot搭配始皇的override使用吗](https://linux.do/t/topic/184494/4)
    
*   [copilot 付费车 6人一车 已稳定两个月 10元/月](https://linux.do/t/topic/194574/18)
    
*   [cocopilot服务端部署好了 visual studio如何用啊](https://linux.do/t/topic/185012)
    
*   [【长期帖】来推荐你心目中的精华神帖吧](https://linux.do/t/topic/188854/31)
    
*   [oai补全不了哎，deepseek正常](https://linux.do/t/topic/201320)
    
*   其他 6 个

20.0k 浏览量 2.0k 赞 28 链接 261 用户

 [![](https://linux.do/user_avatar/linux.do/hashnode/96/15_2.png)
 17](/u/hashnode "hashnode") 

 [![](https://linux.do/letter_avatar_proxy/v4/letter/q/5f8ce5/96.png)
 5](/u/qinyang "qinyang") 

 [![](https://linux.do/letter_avatar_proxy/v4/letter/d/aca169/96.png)
 5](/u/douhao "douhao") 

 [![](https://linux.do/user_avatar/linux.do/dewey/96/122881_2.png)
 5](/u/Dewey "Dewey") 

 [![](https://linux.do/user_avatar/linux.do/7li7li/96/319449_2.png)
 5](/u/7li7li "7li7li")

阅读时间 24 分钟

热门回复

[![](https://linux.do/user_avatar/linux.do/handsome/96/477777_2.png)
](/u/handsome)

[大帅哥](/u/handsome)

[handsome](/u/handsome)种子用户 ![](https://linux.do/images/emoji/twemoji/rage.png?v=14) 

[2024 年 8月](/t/topic/182313/2?u=niyan2025 "发布日期")

太强了大佬！先赞再看

  

1 个回复

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

+1

14

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/kaffirlily/96/311107_2.png)
](/u/KaffirLily)

[爱夏·格雷拉特](/u/KaffirLily)

[KaffirLily](/u/KaffirLily)蛇来运转 ![](https://linux.do/uploads/default/original/3X/a/e/aebe2e5d3f82c286d8395f8bd9326f2feea15a7a.png?v=14) 

[2024 年 8月](/t/topic/182313/3?u=niyan2025 "发布日期")

前排围观支持一下

  

6

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/neo/96/12_2.png)
](/u/neo)

[Neo](/u/neo)

岂曰无衣？ ![](https://linux.do/images/emoji/twemoji/lollipop.png?v=14) 

[2024 年 8月](/t/topic/182313/4?u=niyan2025 "发布日期")

补全的模型还是推荐 deepseek-coder fim

  

3 个回复

34

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/camelliacode/96/48419_2.png)
](/u/CamelliaCode)

[CamelliaCode](/u/CamelliaCode)

活跃用户 ![](https://linux.do/images/emoji/twemoji/kissing_cat.png?v=14) 

[2024 年 8月](/t/topic/182313/5?u=niyan2025 "发布日期")

先赞再看 养成习惯

  

7

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/unique/96/321026_2.png)
](/u/unique)

[Unique](/u/unique)

大预言家 ![](https://linux.do/uploads/default/original/3X/f/c/fcb760df48754f55cd9030370300880cddc30aeb.png?v=14) 

[2024 年 8月](/t/topic/182313/6?u=niyan2025 "发布日期")

真的喂饭教程了，有时间捣鼓一下

  

4

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/hashnode/96/15_2.png)
](/u/hashnode)

[浪里小白条](/u/hashnode)

[hashnode](/u/hashnode)一元复始

 ![](https://linux.do/user_avatar/linux.do/neo/48/12_2.png)
 Neo

[2024 年 8月](/t/topic/182313/7?u=niyan2025 "发布日期")

我试了，但是感觉补全速度没有oaipro快，没有oaipro体验好

  

1 个回复

5

​ ​ 回复

[![](https://linux.do/letter_avatar_proxy/v4/letter/u/e9bcb4/96.png)
](/u/user135)

[ungzs](/u/user135)

[user135](/u/user135)大预言家 ![](https://linux.do/images/emoji/twemoji/headphones.png?v=14) 

 ![](https://linux.do/user_avatar/linux.do/neo/48/12_2.png)
 Neo

[2024 年 8月](/t/topic/182313/8?u=niyan2025 "发布日期")

用下来的话, deepseek-coder 和 gpt-4o 哪个舒服呢?

  

1 个回复

2

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/neo/96/12_2.png)
](/u/neo)

[Neo](/u/neo)

岂曰无衣？ ![](https://linux.do/images/emoji/twemoji/lollipop.png?v=14) 

 ![](https://linux.do/letter_avatar_proxy/v4/letter/u/e9bcb4/48.png)
 ungzs

[2024 年 8月](/t/topic/182313/9?u=niyan2025 "发布日期")

coder用来补全，4o用来对话

  

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

+1

20

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/dpbug/96/20486_2.png)
](/u/dpbug)

[Eternity](/u/dpbug)

[dpbug](/u/dpbug)

[2024 年 8月](/t/topic/182313/10?u=niyan2025 "发布日期")

真喂饭，出的教程都好实用啊

  

4

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/whaleincoldsky/96/96952_2.png)
](/u/WhaleInColdSky)

[WhaleInColdSky](/u/WhaleInColdSky)

 ![](https://linux.do/images/emoji/twemoji/innocent.png?v=14) 

[2024 年 8月](/t/topic/182313/11?u=niyan2025 "发布日期")

gpt-4o强，deepseek-coder便宜  
说实话我都一直用的deepseek，token便宜50倍要啥自行车 ![](https://linux.do/images/emoji/twemoji/crazy_face.png?v=12)

  

1 个回复

3

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/gpl/96/49231_2.png)
](/u/gpl)

[gpl](/u/gpl)

一元复始

[2024 年 8月](/t/topic/182313/12?u=niyan2025 "发布日期")

多谢，收藏了

  

3

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/thenextsupersun/96/22092_2.png)
](/u/Thenextsupersun)

[Mike white](/u/Thenextsupersun)

[Thenextsupersun](/u/Thenextsupersun)

[2024 年 8月](/t/topic/182313/13?u=niyan2025 "发布日期")

谢谢你喂饭侠

  

1

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/jomi/96/1064_2.png)
](/u/Jomi)

[Jomi Wang](/u/Jomi)

[Jomi](/u/Jomi)龙行龘龘 ![](https://linux.do/images/emoji/twemoji/cat2.png?v=14) 

[2024 年 8月](/t/topic/182313/14?u=niyan2025 "发布日期")

在N1上跑的，Docker构建太慢了，还是直接在release下载了

  

4

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/otron/96/212828_2.png)
](/u/otron)

[otron](/u/otron)

大预言家

[2024 年 8月](/t/topic/182313/15?u=niyan2025 "发布日期")

感谢佬友喂饭 ![](https://linux.do/uploads/default/original/3X/e/1/e1aad11157b14d04bc8056573ecb23b5a219d260.png?v=12)

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/bigbigbigsnowman/96/307425_2.png)
](/u/BigBigBigSnowMan)

[大大大雪人](/u/BigBigBigSnowMan)

[BigBigBigSnowMan](/u/BigBigBigSnowMan)活跃用户 ![](https://linux.do/images/emoji/twemoji/snowman_with_snow.png?v=14) 

[2024 年 8月](/t/topic/182313/16?u=niyan2025 "发布日期")

先用 DS，DeepSeek 搞不定的问题再去 4o 问。 ![](https://linux.do/uploads/default/original/3X/2/1/21158038759f6a8630df8507f782a45a6caee004.png?v=12)

  

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

+1

14

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/lonleyhapi/96/309065_2.png)
](/u/lonleyhapi)

[lonleyhapi](/u/lonleyhapi)

海纳百川

[2024 年 8月](/t/topic/182313/17?u=niyan2025 "发布日期")

太强了大佬！先赞再看

  

4

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/youngchany/96/16361_2.png)
](/u/YoungChany)

[YoungChany](/u/YoungChany)

圆圆满满

[2024 年 8月](/t/topic/182313/18?u=niyan2025 "发布日期")

太细了太强了 ![](https://linux.do/uploads/default/original/3X/e/1/e1aad11157b14d04bc8056573ecb23b5a219d260.png?v=12)

  

3

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/cabbage/96/90641_2.png)
](/u/cabbage)

[salad](/u/cabbage)

[cabbage](/u/cabbage)Regular ![](https://linux.do/images/emoji/twemoji/cloud_with_rain.png?v=14) 

[2024 年 8月](/t/topic/182313/19?u=niyan2025 "发布日期")

强啊，收藏一下等待启用

  

6

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/xk2024/96/11895_2.png)
](/u/xk2024)

[xk2024](/u/xk2024)

种子用户 ![](https://linux.do/images/emoji/twemoji/grinning.png?v=14) 

[2024 年 8月](/t/topic/182313/20?u=niyan2025 "发布日期")

先赞  
![](https://linux.do/uploads/default/original/1X/482edd236606257e0614c191390a00d95fc08605.png)
  
再看，养成习惯

  

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