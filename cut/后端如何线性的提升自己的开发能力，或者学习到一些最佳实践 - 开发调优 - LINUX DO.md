# 后端如何线性的提升自己的开发能力，或者学习到一些最佳实践 - 开发调优 - LINUX DO
 后端如何线性的提升自己的开发能力，或者学习到一些最佳实践 - 开发调优 - LINUX DO                                         

[跳到主要内容](#main-container)

 [![](https://linux.do/uploads/default/original/3X/b/4/b4fa45d8b03df61f5d011e173c0adf8497028b16.png)](/) 

*   ​
*    ![](https://linux.do/letter_avatar_proxy/v4/letter/n/58f4c7/96.png)
       [ 1 ](# "1 个未读通知") 

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

[后端如何线性的提升自己的开发能力，或者学习到一些最佳实践](/t/topic/496862)


=================================================

[开发调优](/c/develop/4)

[软件开发](/tag/软件开发)

您已选择 **0** 个帖子。

全选

取消选择

​

[![](https://linux.do/user_avatar/linux.do/mos6/96/282718_2.png)
](/u/mos6)

[mos](/u/mos6)

[mos6](/u/mos6)文化宣导员 ![](https://linux.do/images/emoji/twemoji/goggles.png?v=14) 

[25 分钟](/t/topic/496862?u=niyan2025 "发布日期")

最近刷到一个排 bug 的博主，发现有些坑自己也是踩过的，想提升一下，避免踩一些前人踩过的坑，有什么比较系统的项目或者课程吗，目标是能到一个五年经验的水平  
譬如下面的一些问题，是我遇到的，但是不知道怎么设计是比较合理且符合规范的

```


`项目分一期二期，均是 springBoot 单体项目，共用同一个数据库。一期中需要用到二期的功能，二期也需要调用一期的功能。
不考虑微服务，设计之初应该如何架构（重复的业务放公共模块？）
现在的情况是两个项目都有重复的 Dao 层查数据库，明显错误的设计。
现有的情况下又该如何改进。

基础业务（用户信息），字段较多，分主表、详情表。
问题 1：详情表的信息是包在对象里面作为主表 VO 的一个属性返，还是把字段拷一份到主表的 VO 中。
问题 2：在不同业务需要展示的字段不同（比如个人资料界面需要返回所有字段，订单界面只需要返回姓名字段，可能有十多种情况）。
应该按业务分不同接口，还是所有业务调同一个接口返回所有数据（即使大部分用不上）。
如果分不同的接口，所有接口用同一个 VO 还是不同的 VO 。` 
```

上面的问题已经通过 AI 解决了，但是还可能有其他问题是自己没遇到的（什么情况选择哪个设计模式、不同业务项目应该采用什么架构、数据库的拆分、什么字段该冗余这些），所以想找找覆盖面比较广项目或者课程学习一下  
找了几个课程看了基本也都是直接告诉你怎么做，没有背后的思考，为什么要这么设计

  

​ ​ 回复

29 浏览量

### 此话题将在最后一个回复的1 个月后关闭。

分享 加入书签 举报

回复

已取消置顶

​

此话题已对您取消置顶；它将以常规顺序显示

常规 您会在别人 @ 您或回复您时收到通知。

  

*   推荐
*   相关

### 新话题和未读话题

话题列表，带有按钮的列标题可以排序。
| 话题 | 回复 | 浏览量 | 活动 |
| --- | --- | --- | --- |
| [\[Cursor\] 最稳定的自动更新禁用方案](/t/topic/297886/103)

 [33](/t/topic/297886/103 "您在此话题中有 33 个未读帖子")

[开发调优](/c/develop/4)

[配置优化](/tag/配置优化)





 | [131](/t/topic/297886/1) | 8.3k | [19 小时](/t/topic/297886/135) |
| [Chrome冷启动CPU占用高且某一进程无响应](/t/topic/479020/29)

 [6](/t/topic/479020/29 "您在此话题中有 6 个未读帖子")

[开发调优](/c/develop/4)

[快问快答](/tag/快问快答)

,[配置优化](/tag/配置优化)





 | [33](/t/topic/479020/1) | 237 | [9 天](/t/topic/479020/34) |
| [【已发布到 Github Marketplace】Github 快速搭建博客/文档网站：保持专注于内容创作](/t/topic/353423/31)

 [7](/t/topic/353423/31 "您在此话题中有 7 个未读帖子")

[开发调优](/c/develop/4)

[配置优化](/tag/配置优化)

,[博客](/tag/博客)





 | [34](/t/topic/353423/1) | 747 | [1月 27 日](/t/topic/353423/37) |
| [【OWB】思路打开，方案自来](/t/topic/496898)

  [github.com](https://github.com/wozulong/open-wegram-bot)

[开发调优](/c/develop/4)

[Telegram](/tag/telegram)





 | [5](/t/topic/496898/1) | 24 | [1 分钟](/t/topic/496898/6) |
| [You.com无法上传文件!](/t/topic/496829)

[开发调优](/c/develop/4)

[快问快答](/tag/快问快答)





 | [5](/t/topic/496829/1) | 66 | [1 分钟](/t/topic/496829/6) |

### 有 [26 个未读](/unread)

话题 和 [138 个新](/new)

话题， 或浏览[开发调优](/c/develop/4)

中的其他话题

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