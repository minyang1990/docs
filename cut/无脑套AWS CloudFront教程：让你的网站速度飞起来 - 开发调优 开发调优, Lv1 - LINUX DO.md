# 无脑套AWS CloudFront教程：让你的网站速度飞起来 - 开发调优 / 开发调优, Lv1 - LINUX DO
 无脑套AWS CloudFront教程：让你的网站速度飞起来 - 开发调优 / 开发调优, Lv1 - LINUX DO                                                

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

[无脑套AWS CloudFront教程：让你的网站速度飞起来](/t/topic/399977)


===================================================

[开发调优](/c/develop/4)

[开发调优, Lv1](/c/develop/develop-lv1/20)

[配置优化](/tag/配置优化)

您已选择 **0** 个帖子。

全选

取消选择

​

[1月 29 日](/t/topic/399977/1 "跳到第一个帖子")

1 / 34

1月 29 日

返回

[14 天 前](/t/topic/399977/35)

​

[![](https://linux.do/user_avatar/linux.do/chengtx/96/367608_2.png)
](/u/chengtx)

[天哥在写bug](/u/chengtx)

[chengtx](/u/chengtx)文化宣导员

1

[1月 29 日](/t/topic/399977?u=niyan2025 "发布日期")

### [](#p-3702261-cft1taws-1)CFT虽快，但每个月只有1T免费流量，注意别被AWS反薅了

[](#p-3702261-h-0-2)0.登录
========================

打开[AWS](https://aws.amazon.com/)

，右上角点登录  

[![](https://linux.do/uploads/default/optimized/4X/1/f/4/1f47880fe5567f5233f94b95568a9d30ceaced4d_2_690x473.jpeg)

image1920×1317 146 KB

](https://linux.do/uploads/default/original/4X/1/f/4/1f47880fe5567f5233f94b95568a9d30ceaced4d.jpeg "image")

  

[![](https://linux.do/uploads/default/optimized/4X/b/3/c/b3c6ed5c842a49ebcd78cf43db6202820707a0b5_2_690x473.jpeg)

image1920×1317 140 KB

](https://linux.do/uploads/default/original/4X/b/3/c/b3c6ed5c842a49ebcd78cf43db6202820707a0b5.jpeg "image")

  
**注册aws账号在此不再赘述，照着步骤一步步来就好啦**  
**需要邮箱+手机号+信用卡验证 ~绝对不是懒得写~**

[](#p-3702261-h-1cft-3)1.进入cft控制台
=================================

登录完成后，在左上角搜索框输入`cloudfront`后点击进入cft控制台  

[![](https://linux.do/uploads/default/optimized/4X/3/1/c/31c548b0527ee4e24b5b77a2399c2425a059e14f_2_690x473.png)

image2178×1494 314 KB

](https://linux.do/uploads/default/original/4X/3/1/c/31c548b0527ee4e24b5b77a2399c2425a059e14f.png "image")

[](#p-3702261-h-2-4)2.创建分配
==========================

进入cft控制台后点击右侧的橙色按钮创建分配，再按照图片里的步骤设置  

[![](https://linux.do/uploads/default/optimized/4X/d/1/0/d10069daa608acece7b589272b76f15b71f6b6ef_2_690x473.png)

image2178×1494 327 KB

](https://linux.do/uploads/default/original/4X/d/1/0/d10069daa608acece7b589272b76f15b71f6b6ef.png "image")

  

[![](https://linux.do/uploads/default/optimized/4X/5/9/7/59703158018aaf4f7f8936d97974673e8c859ce4_2_690x473.png)

image2178×1494 192 KB

](https://linux.do/uploads/default/original/4X/5/9/7/59703158018aaf4f7f8936d97974673e8c859ce4.png "image")

  

[![](https://linux.do/uploads/default/optimized/4X/f/e/4/fe482b855f68402abe292e9d5ecc25202df7672a_2_690x473.png)

image2178×1494 199 KB

](https://linux.do/uploads/default/original/4X/f/e/4/fe482b855f68402abe292e9d5ecc25202df7672a.png "image")

  

[![](https://linux.do/uploads/default/optimized/4X/9/8/3/983df703ef8cd77bbaed463402629ef69c03a0df_2_690x473.png)

image2178×1494 208 KB

](https://linux.do/uploads/default/original/4X/9/8/3/983df703ef8cd77bbaed463402629ef69c03a0df.png "image")

  

[![](https://linux.do/uploads/default/optimized/4X/c/a/9/ca93417afca89e4f353d8e421942ff3af52d8961_2_690x474.png)

image2185×1502 226 KB

](https://linux.do/uploads/default/original/4X/c/a/9/ca93417afca89e4f353d8e421942ff3af52d8961.png "image")

  
按照以上设置完成后划到最底下点击橙色按钮创建分配即可

[](#p-3702261-h-3-5)3.测试并使用
===========================

耐心等待部署完成（“上次修改时间”一栏显示具体时间时说明部署完成，需要几分钟）  

[![](https://linux.do/uploads/default/optimized/4X/c/a/7/ca7a06d620b75dfc25ec068e5b221ccd2ebd86ee_2_690x175.png)

image2130×543 40.7 KB

](https://linux.do/uploads/default/original/4X/c/a/7/ca7a06d620b75dfc25ec068e5b221ccd2ebd86ee.png "image")

  
部署完成后点击ID进入面板并测试分配的域名是否正常使用  

[![](https://linux.do/uploads/default/optimized/4X/6/6/7/667cbb124c667ba40e676ff81475e135ab1cd28e_2_690x220.png)

image1662×532 42 KB

](https://linux.do/uploads/default/original/4X/6/6/7/667cbb124c667ba40e676ff81475e135ab1cd28e.png "image")

  
、  

[![](https://linux.do/uploads/default/optimized/4X/8/5/8/8584f27f4b341cf51aff18bbb20fb58e2ba00460_2_690x444.png)

image2155×1388 192 KB

](https://linux.do/uploads/default/original/4X/8/5/8/8584f27f4b341cf51aff18bbb20fb58e2ba00460.png "image")

  
可以看到我加速的是在hf部署的owu，可以正常使用  
如果你没有自己的域名且没有自定义域名的需求，那么直接用分配域名就ok了  
主教程到此完结，Congratulations​![](https://linux.do/images/emoji/twemoji/tada.png?v=12)

[](#p-3702261-h-6)进阶教程：自定义域名
============================

先点击面板右侧的“编辑”进入设置并添加自己的域名  

[![](https://linux.do/uploads/default/optimized/4X/3/6/0/3602bece3fdbbb79015c1f3c5987e1dc01e272a3_2_690x444.png)

image2155×1388 187 KB

](https://linux.do/uploads/default/original/4X/3/6/0/3602bece3fdbbb79015c1f3c5987e1dc01e272a3.png "image")

  

[![](https://linux.do/uploads/default/optimized/4X/a/c/8/ac891ae5897603964c86a56f7a99477b274e25f2_2_592x500.png)

image1054×890 126 KB

](https://linux.do/uploads/default/original/4X/a/c/8/ac891ae5897603964c86a56f7a99477b274e25f2.png "image")

  
进入ACM创建免费证书并进行dns验证  

[![](https://linux.do/uploads/default/optimized/4X/5/5/3/553c538bcc8061fdee5d22d101375cbd70e38f50_2_690x444.png)

image2155×1388 109 KB

](https://linux.do/uploads/default/original/4X/5/5/3/553c538bcc8061fdee5d22d101375cbd70e38f50.png "image")

  

[![](https://linux.do/uploads/default/optimized/4X/8/5/d/85d2725830ed5676b295a69b91424ab5c05ccbe0_2_669x500.png)

image1729×1291 145 KB

](https://linux.do/uploads/default/original/4X/8/5/d/85d2725830ed5676b295a69b91424ab5c05ccbe0.png "image")

  

[![](https://linux.do/uploads/default/optimized/4X/f/5/b/f5b9873a9ad172b4c44214f5ee3e5b659f1d2db8_2_628x500.png)

image1712×1363 162 KB

](https://linux.do/uploads/default/original/4X/f/5/b/f5b9873a9ad172b4c44214f5ee3e5b659f1d2db8.png "image")

  
接着前往你的域名dns管理面板添加对应的cname值，以cf举例：  

[![](https://linux.do/uploads/default/optimized/4X/b/8/d/b8d1f008f3d9091e2f4f092b55af0ea879c7cfd8_2_690x321.png)

image2519×1173 362 KB

](https://linux.do/uploads/default/original/4X/b/8/d/b8d1f008f3d9091e2f4f092b55af0ea879c7cfd8.png "image")

  
添加完记录后稍等一会便可在ACM看到证书颁发成功  

[![](https://linux.do/uploads/default/optimized/4X/3/3/6/3365103ac319743953406505b1385c3dbe6943a9_2_690x283.png)

image2008×826 45.3 KB

](https://linux.do/uploads/default/original/4X/3/3/6/3365103ac319743953406505b1385c3dbe6943a9.png "image")

  
接着返回CloudFront，选用刚刚颁发的证书  

[![](https://linux.do/uploads/default/optimized/4X/d/e/b/deb0df8185e517314ad4ca6fdf2c4556a5527af5_2_503x500.png)

image1478×1467 158 KB

](https://linux.do/uploads/default/original/4X/d/e/b/deb0df8185e517314ad4ca6fdf2c4556a5527af5.png "image")

  
然后划到最底下点击橙色按钮保存更改  
最后设置一个cname把你的自定义域名指向分配域名，依然以cf举例：  

[![](https://linux.do/uploads/default/optimized/4X/7/0/0/7005d2f952c9f1f52204fb561ca2b5c2620647a8_2_690x356.png)

image2035×1052 133 KB

](https://linux.do/uploads/default/original/4X/7/0/0/7005d2f952c9f1f52204fb561ca2b5c2620647a8.png "image")

  

[![](https://linux.do/uploads/default/optimized/4X/8/9/7/897075e8aa5f0f364e9f0fb99fbb31846ce7b4fa_2_690x239.png)

image1789×620 46.8 KB

](https://linux.do/uploads/default/original/4X/8/9/7/897075e8aa5f0f364e9f0fb99fbb31846ce7b4fa.png "image")

稍等一会，就可以用自定义域名访问了！  
来张对比图  

[![](https://linux.do/uploads/default/optimized/4X/1/f/8/1f8cbf95ece80f43f3361c54e05e2dd22fd47a99_2_690x366.png)

image1035×549 73.2 KB

](https://linux.do/uploads/default/original/4X/1/f/8/1f8cbf95ece80f43f3361c54e05e2dd22fd47a99.png "image")

  

[![](https://linux.do/uploads/default/optimized/4X/1/4/2/1423446dae6cddf4e248c59ff8c4fbd85300d970_2_690x368.png)

image1035×553 71 KB

](https://linux.do/uploads/default/original/4X/1/4/2/1423446dae6cddf4e248c59ff8c4fbd85300d970.png "image")

  

1 个回复

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

+1

39

​ ​ 回复

*   [亚马逊CFT的速度简直吊打CF](https://linux.do/t/topic/399627/54)
    
*   [【教程】受够了cf反代hf站点的龟速？来用自己的cdn吧！](https://linux.do/t/topic/400565/3)
    

751 浏览量 41 赞 4 链接 27 用户

 [![](https://linux.do/user_avatar/linux.do/chengtx/96/367608_2.png)
 5](/u/chengtx "chengtx")

 [![](https://linux.do/user_avatar/linux.do/88666/96/474564_2.png)
 2](/u/88666 "88666")

 [![](https://linux.do/user_avatar/linux.do/snicoe/96/117170_2.png)
 2](/u/snicoe "snicoe") 

 [![](https://linux.do/user_avatar/linux.do/yuyuyang/96/307311_2.png)
 2](/u/yuyuyang "yuyuyang")

 [![](https://linux.do/letter_avatar_proxy/v4/letter/b/dfb087/96.png)](/u/bkjyyy "bkjyyy") 

[![](https://linux.do/user_avatar/linux.do/6512345/96/306815_2.png)
](/u/6512345)

[65](/u/6512345)

[6512345](/u/6512345)文化宣导员 ![](https://linux.do/images/emoji/twemoji/innocent.png?v=14) 

[1月 29 日](/t/topic/399977/2?u=niyan2025 "发布日期")

太强了！

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/yinhono/96/325749_2.png)
](/u/Yinhono)

[Yinhono](/u/Yinhono)

大预言家

[1月 29 日](/t/topic/399977/3?u=niyan2025 "发布日期")

好绿，太强了！

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/zhouyi/96/493911_2.png)
](/u/zhouyi)

[周一](/u/zhouyi)

[zhouyi](/u/zhouyi)一元复始

[1月 29 日](/t/topic/399977/4?u=niyan2025 "发布日期")

精华 感谢佬友

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/zhong_little/96/310552_2.png)
](/u/zhong_little)

[Megasoft](/u/zhong_little)

[zhong\_little](/u/zhong_little)解决方案机构 ![](https://linux.do/images/emoji/twemoji/dolphin.png?v=14) 

[1月 29 日](/t/topic/399977/5?u=niyan2025 "发布日期")

有没有被反薅的风险

  

1 个回复

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/yuyuyang/96/307311_2.png)
](/u/yuyuyang)

[羽于羊](/u/yuyuyang)

[yuyuyang](/u/yuyuyang)一元复始 ![](https://linux.do/images/emoji/twemoji/man_technologist.png?v=14) 

 ![](https://linux.do/user_avatar/linux.do/zhong_little/48/310552_2.png)
 Megasoft

[1月 29 日](/t/topic/399977/6?u=niyan2025 "发布日期")

风险很大，免费流量就1t

  

1 个回复

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/xiaohui/96/371767_2.png)
](/u/xiaohui)

[xiaohui](/u/xiaohui)

文化宣导员 ![](https://linux.do/images/emoji/twemoji/100.png?v=14) 

 ![](https://linux.do/user_avatar/linux.do/yuyuyang/48/307311_2.png)
 羽于羊

[1月 29 日](/t/topic/399977/7?u=niyan2025 "发布日期")

一般根本也用不完吧

  

1 个回复

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/sixsixsix/96/3759_2.png)
](/u/sixsixsix)

[666](/u/sixsixsix)

[sixsixsix](/u/sixsixsix)一元复始 ![](https://linux.do/images/emoji/twemoji/crossed_swords.png?v=14) 

[1月 29 日](/t/topic/399977/8?u=niyan2025 "发布日期")

mark

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/shannon1024/96/292112_2.png)
](/u/shannon1024)

[林青枫](/u/shannon1024)

[shannon1024](/u/shannon1024)

[1月 29 日](/t/topic/399977/9?u=niyan2025 "发布日期")

开启cloudfront，又不开WAF防火墙，只能说确保自己别被人盯上吧

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/yuyuyang/96/307311_2.png)
](/u/yuyuyang)

[羽于羊](/u/yuyuyang)

[yuyuyang](/u/yuyuyang)一元复始 ![](https://linux.do/images/emoji/twemoji/man_technologist.png?v=14) 

 ![](https://linux.do/user_avatar/linux.do/xiaohui/48/371767_2.png)
 xiaohui

[1月 29 日](/t/topic/399977/10?u=niyan2025 "发布日期")

给你点ddos震撼你就知道了

  

1 个回复

​ ​ 回复

上次访问

[![](https://linux.do/user_avatar/linux.do/snicoe/96/117170_2.png)
](/u/snicoe)

[snicoe](/u/snicoe)

[1月 29 日](/t/topic/399977/11?u=niyan2025 "发布日期")

出AWS免费1t，用户->AWS->源站是要收钱的，d一下就老实了，请求数+流量让你账单飞起来![](https://linux.do/images/emoji/twemoji/rofl.png?v=12)

  

2 个回复

2

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/handsome/96/477777_2.png)
](/u/handsome)

[大帅哥](/u/handsome)

[handsome](/u/handsome)种子用户 ![](https://linux.do/images/emoji/twemoji/rage.png?v=14) 

[1月 29 日](/t/topic/399977/12?u=niyan2025 "发布日期")

感谢大佬教程！

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/chengtx/96/367608_2.png)
](/u/chengtx)

[天哥在写bug](/u/chengtx)

[chengtx](/u/chengtx)文化宣导员

 ![](https://linux.do/user_avatar/linux.do/yuyuyang/48/307311_2.png)
 羽于羊

[1月 29 日](/t/topic/399977/13?u=niyan2025 "发布日期")

可不可以CF套个5秒盾 ![](https://linux.do/uploads/default/original/3X/2/e/2e09f3a3c7b27eacbabe9e9614b06b88d5b06343.png?v=12)

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/zgm/96/411408_2.png)
](/u/ZGM)

[赵公明](/u/ZGM)

[ZGM](/u/ZGM)一元复始

[1月 30 日](/t/topic/399977/14?u=niyan2025 "发布日期")

这个可以玩玩

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/chengtx/96/367608_2.png)
](/u/chengtx)

[天哥在写bug](/u/chengtx)

[chengtx](/u/chengtx)文化宣导员

 ![](https://linux.do/user_avatar/linux.do/snicoe/48/117170_2.png)
 snicoe

[1月 30 日](/t/topic/399977/15?u=niyan2025 "发布日期")

[不良林发布的帖子 - YouTube](https://www.youtube.com/channel/UCbCCUH8S3yhlm7__rhxR2QQ/community?lb=UgkxPrlVOXsi-IkFKtvXkoQNGLpJ8YbaOmjX)

  
yt上有讨论过，如果纯自用搭个小站点还好  
不过aws扣费真的玄学

  

1 个回复

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/lisakhan/96/112_2.png)
](/u/lisakhan)

[Lisakhan](/u/lisakhan)

蛇来运转

[1月 30 日](/t/topic/399977/16?u=niyan2025 "发布日期")

大年初二，学习不止，谢谢

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/endercat/96/200825_2.png)
](/u/endercat)

[暁美 ほむら Advanced](/u/endercat)

[endercat](/u/endercat)蛇来运转

[1月 30 日](/t/topic/399977/17?u=niyan2025 "发布日期")

等被打就是你的钱飞起来了XD

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/snicoe/96/117170_2.png)
](/u/snicoe)

[snicoe](/u/snicoe)

 ![](https://linux.do/user_avatar/linux.do/chengtx/48/367608_2.png)
 天哥在写bug

[1月 30 日](/t/topic/399977/18?u=niyan2025 "发布日期")

你能保证你的站点只有你一个人访问吗？先不说各种乱七八糟的爬虫，如果不能被打了或者爬炸了就是天价账单，客服免一次，第二次可免不了，当然你也可以选择跑路![](https://linux.do/images/emoji/twemoji/rofl.png?v=12)

  

1 个回复

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/fii/96/363145_2.png)
](/u/Fii)

[NeoFii](/u/Fii)

[Fii](/u/Fii)文化宣导员

[1月 30 日](/t/topic/399977/19?u=niyan2025 "发布日期")

太强了佬

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/chengtx/96/367608_2.png)
](/u/chengtx)

[天哥在写bug](/u/chengtx)

[chengtx](/u/chengtx)文化宣导员

 ![](https://linux.do/user_avatar/linux.do/snicoe/48/117170_2.png)
 snicoe

[1月 30 日](/t/topic/399977/20?u=niyan2025 "发布日期")

卡里面只有一刀，跑就跑了吧 ![](https://linux.do/uploads/default/original/3X/b/f/bf37f2afe0dc15f69b179ec74fbfe4b9545eeed0.png?v=12)

  

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

VertiTab