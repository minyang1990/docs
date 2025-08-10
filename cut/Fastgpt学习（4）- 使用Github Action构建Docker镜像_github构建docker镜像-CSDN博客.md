# Fastgpt学习（4）- 使用Github Action构建Docker镜像_github构建docker镜像-CSDN博客
[Fastgpt学习（4）- 使用Github Action构建Docker镜像_github构建docker镜像-CSDN博客](https://blog.csdn.net/m0_37827702/article/details/143209607) 

              Fastgpt学习（4）- 使用Github Action构建Docker镜像\_github构建docker镜像-CSDN博客        

Constants loaded at 2025-08-10T21:46:16.596Z

[![](https://img-home.csdnimg.cn/images/20201124032511.png)
](https://www.csdn.net/)

*   [博客](https://blog.csdn.net/)
*   [下载](https://download.csdn.net/)
*   [学习](https://edu.csdn.net?utm_source=zhuzhantoolbar)
*   [社区](https://devpress.csdn.net/)
*   [![](https://img-home.csdnimg.cn/images/20240829093757.png)
    GitCode](https://link.csdn.net?target=https%3A%2F%2Fgitcode.com%3Futm_source%3Dcsdn_toolbar) 
*   [InsCodeAI](https://inscode.csdn.net?utm_source=260232576)
*   [会议](https://summit.csdn.net/)

 

搜索

AI 搜索

登录

登录后您可以：

*   复制代码和一键运行
*   与博主大V深度互动
*   解锁海量精选资源
*   获取前沿技术资讯

立即登录

[会员中心 ![](https://i-operation.csdnimg.cn/images/e33926db17a747889dca351180f92ecf.gif)](https://mall.csdn.net/vip) 

[消息](https://i.csdn.net/#/msg/index)

[历史](https://i.csdn.net/#/user-center/history)

[创作中心](https://mp.csdn.net "创作中心")

[![](https://img-home.csdnimg.cn/images/20230825101811.png)
](https://mp.csdn.net/edit) ![](https://img-home.csdnimg.cn/images/20230815023238.png)

[创作](https://mp.csdn.net/edit)

  

Fastgpt学习（4）- 使用Github Action构建Docker镜像
=======================================

最新推荐文章于 2025-06-23 20:56:37 发布

原创 [![](https://csdnimg.cn/release/blogv2/dist/pc/img/identityVipNew.png)
](https://mall.csdn.net/vip) 于 2024-10-24 15:23:16 发布 · 1.3k 阅读

· ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newHeart2023Active.png)
 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newHeart2023Black.png)
 30 

· ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect2.png)
 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollectionActive2.png)
  12   ·

CC 4.0 BY-SA版权

版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

文章标签：

[#1024程序员节](https://so.csdn.net/so/search/s.do?q=1024%E7%A8%8B%E5%BA%8F%E5%91%98%E8%8A%82&t=all&o=vip&s=&l=&f=&viparticle=&from_tracking_code=tag_word&from_code=app_blog_art) [#FastGPT](https://so.csdn.net/so/search/s.do?q=FastGPT&t=all&o=vip&s=&l=&f=&viparticle=&from_tracking_code=tag_word&from_code=app_blog_art) [#docker](https://so.csdn.net/so/search/s.do?q=docker&t=all&o=vip&s=&l=&f=&viparticle=&from_tracking_code=tag_word&from_code=app_blog_art) [#容器](https://so.csdn.net/so/search/s.do?q=%E5%AE%B9%E5%99%A8&t=all&o=vip&s=&l=&f=&viparticle=&from_tracking_code=tag_word&from_code=app_blog_art) [#github](https://so.csdn.net/so/search/s.do?q=github&t=all&o=vip&s=&l=&f=&viparticle=&from_tracking_code=tag_word&from_code=app_blog_art)

 

### 1\. 背景

本地开发修改代码后需要构建适用于不用[系统架构](https://so.csdn.net/so/search?q=%E7%B3%BB%E7%BB%9F%E6%9E%B6%E6%9E%84&spm=1001.2101.3001.7020)的Docker镜像，在本地MacOS (m1) 上一直报错，无法完成镜像构建，遂转使用Github Action构建镜像。

> 报错信息：`failed to compute cache key: "/app/projects/app/.next/standalone" not found: not found`  
> **尝试解决方案：**   
> 1.本地重新运行`pnpm build`  
> 2\. 修改DockerFile 文件中的 `ENV NODE_OPTIONS="--max-old-space-size=4096"`的值  
> **参考issue：** 
> 
> 1.  https://github.com/labring/FastGPT/issues/1457
> 2.  https://github.com/labring/FastGPT/issues/1468
> 
> **Mac打包可能存在的问题：**   
> ![](https://i-blog.csdnimg.cn/direct/a3775e34de714143be11caa94ad83679.png)

### 2\. 操作步骤

#### 2.1 fork仓库 & 配置仓库信息

[FastGPT- github仓库](https://github.com/labring/FastGPT)

Github Action工作流的相关文件存储在 ![](https://i-blog.csdnimg.cn/direct/2612eaa460ca45f08ca111ca41218a0d.png)
  
`.github -> workflows` 文件夹下，构建[docker镜像](https://so.csdn.net/so/search?q=docker%E9%95%9C%E5%83%8F&spm=1001.2101.3001.7020)的有两个文件`build-sandbox-image.yml`和`fastgpt-image.yml`  
![](https://i-blog.csdnimg.cn/direct/fad7863e17c0488b83fce2c938fab091.png)
  
**配置仓库信息**  
通过查看上述两个文件，发现有几个变量需要根据自身情况进行配置  
![](https://i-blog.csdnimg.cn/direct/681a7292fe2748aa958c1cbaca183348.png)
  
以具体的dockerhub仓库为例  
![](https://i-blog.csdnimg.cn/direct/b7f4adf94a604120a64a010aab562537.png)
  
`GH_PAT`是个人访问令牌：  
登录到你的 GitHub 账户。转到 **Settings**（设置） > **Developer settings**（开发者设置） > **Personal access tokens**（个人访问令牌）。如果你还没有令牌，可以点击 **Generate new token**（生成新令牌）。如果已有令牌，点击它以编辑权限。  
![](https://i-blog.csdnimg.cn/direct/49d4c39af7964f7c8dfe9d5cc0df40d6.png)
  
![](https://i-blog.csdnimg.cn/direct/ece1e0686c794086bd254aa4a8ac4613.png)

#### 2.2 修改配置文件

`fastgpt-image.yml`和`build-sandbox-images.yml`文件修改：删除所有`Ali Hub`相关的代码

```
`#   fastgpt-image.yml文件
name: Build FastGPT images and copy image to docker hub
on:
  workflow_dispatch:
  push:
    paths:
      - 'projects/app/**'
      - 'packages/**'
    tags:
      - 'v*'
jobs:
  build-fastgpt-images:
    runs-on: ubuntu-20.04
    steps:
      # install env
      - name: Checkout
        uses: actions/checkout@v3
        with:
          fetch-depth: 1
      - name: Install Dependencies
        run: | sudo apt update && sudo apt install -y nodejs npm` 

AI写代码yml

![](https://csdnimg.cn/release/blogv2/dist/pc/img/runCode/icon-arrowwhite.png)

*   1
*   2
*   3
*   4
*   5
*   6
*   7
*   8
*   9
*   10
*   11
*   12
*   13
*   14
*   15
*   16
*   17
*   18
*   19
*   20
*   21
*   22


```

 

![](https://csdnimg.cn/release/blogv2/dist/pc/img/lock.png)
最低0.47元/天 解锁文章

200万优质内容无限畅学

![](https://csdnimg.cn/release/blogv2/dist/pc/img/vip-limited-close-newWhite.png)

确定要放弃本次机会？

福利倒计时

_:_ _:_

![](https://csdnimg.cn/release/blogv2/dist/pc/img/vip-limited-close-roup.png)
 立减 ¥ 

普通VIP年卡可用

[立即使用](https://mall.csdn.net/vip)

 [![](https://profile-avatar.csdnimg.cn/f941fb46a40b49b68fa8ddbb7d22e0d1_m0_37827702.jpg!1)
  努力的小Qin](https://blog.csdn.net/m0_37827702) 

[关注](javascript:;) 关注

*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarThumbUpactive.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/like-active.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/like.png)
      30 
    
    点赞
    
*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/unlike-active.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/unlike.png) 
    
    踩
    
*    [![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/collect-active.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/collect.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newCollectActive.png)
      12](javascript:;) 
    
    收藏
    
    觉得还不错? 一键收藏 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/collectionCloseWhite.png)
    
*    [![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/comment.png)
      0](#commentBox) 
    
    评论
    
*    [![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/share.png)
     分享](javascript:;) 
    
    复制链接
    
    分享到 QQ
    
    分享到新浪微博
    
    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/share/icon-wechat.png)
    扫一扫
    
*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/more.png) 
    
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/report.png)
     举报 
    
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/report.png)
     举报 
    

专栏目录

![](https://kunyu.csdn.net/1.png?p=58&adBlockFlag=0&adId=1072605&a=1072605&c=3162605&k=Fastgpt学习（4）- 使用Github Action构建Docker镜像&spm=1001.2101.3001.5002&articleId=143209607&d=1&t=3&u=c1ebc8bda0ba40aab6f4a538d7918ccb)

[

_使用__Github_ _Action_s自建_Docker__镜像_仓库

](https://eddy5x.blog.csdn.net/article/details/140220391)

[Eddy的博客](https://blog.csdn.net/u012107402)

07-05 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1240 

[

ALIYUN\_REGISTRY就是阿里云_容器__镜像_服务访问域名，每个区域的域名有所不同。HUAWEI\_REGISTRY就是华为_容器__镜像_服务访问域名，每个区域的域名有所不同。ALIYUN\_REGISTRY\_PASSWORD就是我们设置的固定密码。HUAWEI\_KEY就是我们设置的Access Key ID。ALIYUN\_REGISTRY\_USER就是我们阿里云账号。ALIYUN\_NAME\_SPACE就是阿里云命名空间名称。HUAWEI\_NAME\_SPACE就是华为云组织名称。以阿里云_容器__镜像_服务为例。

](https://eddy5x.blog.csdn.net/article/details/140220391)

参与评论 您还未登录，请先 登录 后发表或查看评论

[

用_GitHub_ _Action_s制作_Docker__镜像_\__github_ _docker_

](https://blog.csdn.net/2501_90404828/article/details/145393511)

7-23

[

_DOCKER_\_USERNAME: ${{secrets._DOCKER_\_USERNAME}} _DOCKER_\_PASSWORD: ${{secrets._DOCKER_\_PASSWORD}} 指定login命令登录hub._docker_.com,帐号和密码已经在_GitHub_网页中配置好了 run: | echo “${_DOCKER_\_PASSWORD}” | _docker_ login _\-__\-_username ${D

](https://blog.csdn.net/2501_90404828/article/details/145393511)

[

Springboot项目_Github_ _Action_生成_Docker__镜像_\__github_ _action_s java build...

](https://blog.csdn.net/Mr_Chenn/article/details/111301366)

7-29

[

Build_Docker_Image:这一步 _使用__docker_ build利用_Docker_file生成_docker__镜像_。 Publish to _Docker_ Repository:这一步将上一步打包生成的_docker__镜像_推送至指定的_镜像_仓库。 with下面的name是_镜像_仓库地址,username是_镜像_仓库登录的用户名,password是_镜像_仓库登录的密码。由于这些东西是比较隐秘的,这里用了_github_的secret。 项目的...

](https://blog.csdn.net/Mr_Chenn/article/details/111301366)

[

_GitHub_ _Action_s _构建_ _Docker_ _镜像_

](https://seasoft.blog.csdn.net/article/details/136209417)

[wjianwei666的专栏](https://blog.csdn.net/wjianwei666)

02-21 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 500 

[

让我们从创建一个新的_GitHub_存储库开始，它将保存我们的代码（在我们的例子中，实际上只需要一个_Docker_file）来_构建__镜像_。记住两件事：您在这里_使用_的标签名称将用作_Docker__镜像_的标签名称，一旦您单击“发布版本”按钮，工作流将启动。这很棒，因为否则就没有办法登录到第三方服务，如_Docker_ Hub，而不把你的密码或访问密钥放在仓库中，每个人都可以看到。不过，这里有一些新的东西，那就是我们正在_使用_的秘密。_GitHub_在每个存储库的设置中有一个部分，您可以在其中设置用于_GitHub_操作等的秘密。

](https://seasoft.blog.csdn.net/article/details/136209417)

[

用_GitHub_ _Action_s制作_Docker__镜像_

](https://xinchen.blog.csdn.net/article/details/115476859)

[程序员欣宸的博客](https://blog.csdn.net/boling_cavalry)

04-11 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 2299 

[

_GitHub_ _Action_s是_GitHub_的持续集成服务，大家一起体验白嫖微软服务器的快乐，才是真的快乐

](https://xinchen.blog.csdn.net/article/details/115476859)

[

_github_配置阿里云_镜像_库,加速_docker__镜像_下载\__使用_阿里云+_github__构建_镜...

](https://blog.csdn.net/givxd/article/details/140990585)

7-26

[

在_github_自己frok的仓库下,提交issues,issues的名称和内容直接填写需要的_镜像_,比如ultralytics/ultralytics:latest。 3.3 点击提交,_github_会_action_,自动拉取_镜像_到配置的阿里云仓库。拉取完成后会显示如下: 红色部分即为目标仓库的命名空间。 3._4_ 之后,就可以_使用_命令行直接拉取_镜像_了 sudo _docker_ pull registry.cn_\-_han...

](https://blog.csdn.net/givxd/article/details/140990585)

[

...教你通过_GitHub_项目_构建_自己的_镜像_仓库站!\__docker_hub

](https://blog.csdn.net/m0_61323675/article/details/130756529)

8-8

[

文章讲述了在无法访问_Docker_hub时,如何通过阿里云ARC_镜像_仓库站对接_GitHub_项目实现自动化_构建__镜像_的过程。作者在尝试部署kube_\-_state_\-_metrics时遇到_镜像_拉取问题,于是创建阿里云_镜像_仓库,并设置_GitHub_项目触发_构建_规则,包括Brach和Tag模式,成功_构建_并存储所需_镜像_。

](https://blog.csdn.net/m0_61323675/article/details/130756529)

[

_FastGPT_极速上手指南：_Docker__容器_化部署实战

最新发布

](https://asialee.blog.csdn.net/article/details/148616312)

[分享实践与思考](https://blog.csdn.net/asialee_bird)

06-23 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1363 

[

_使用_ _Docker_ Compose 快速部署 _FastGPT_ _4_.9.7版本

](https://asialee.blog.csdn.net/article/details/148616312)

[

_GitHub_ _Action_s_构建__Docker__镜像_

](https://blog.csdn.net/weixin_40046357/article/details/106184676)

[DevOps持续集成的博客](https://blog.csdn.net/weixin_40046357)

05-17 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 3440 

[

_GitHub_ _Action_s是为_GitHub_上的项目添加CI / CD工作流的自动化工具。注意：在本文中，我们将讨论将CI / CD工作流程集成到_使用__Docker_的项目中的各个步骤。在使...

](https://blog.csdn.net/weixin_40046357/article/details/106184676)

[

...功能_构建_workflow并且打包java程序_docker__镜像_,最后推送到阿里免费...

](https://blog.csdn.net/2301_80286384/article/details/142066921)

7-27

[

本篇博客为了解决_docker_ hub关闭,_镜像_无法拉取问题,_使用__github_ _Action_s功能_构建_workflow并且打包java程序_docker__镜像_,最后推送到阿里免费的_docker__镜像_仓库中。 第一步: 创建阿里云个人_镜像_仓库 进入阿里云官网,登入自己的阿里云账号,搜索框输入_容器__镜像_服务,进入该页面后创建个人实例 ...

](https://blog.csdn.net/2301_80286384/article/details/142066921)

[

_Github_ _Action_s 推送代码_构建_ _Docker_ _镜像_并 push 到仓库

](https://blog.csdn.net/qq_52397471/article/details/135538419)

7-17

[

_Github__Action_s 推送代码_构建_ _Docker_ _镜像_并 push 到_镜像_仓库 需要解决的问题 解决ci/cd 流程,在 推送代码到 _github_ 时,_github_ 的 _action_ 能够自动_构建_代码并发布到_镜像_仓库,之后运行_docker__\-_compose文件,启动项目访问。 问题前置分析 目前比较流行的 ci/cd 解决方案为: ...

](https://blog.csdn.net/qq_52397471/article/details/135538419)

[

_使用__Github_ _Action_将_Docker__镜像_转存到阿里云私有仓库，供国内服务器_使用_，免费易用

](https://blog.csdn.net/shdabai/article/details/144064644)

[争渡的博客](https://blog.csdn.net/shdabai)

11-27 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1703 

[

方法原视频非常有用，这几天，想_使用__镜像_来部署项目。试了很多方法在_镜像_官网，不能很好的pull _镜像_。这个视频中给出了一种中转方法。注意：：因为视频的时间较早，阿里云_使用_界面略有变化但是基本上，方法步骤是一样的。按照步骤操作，应该不会出问题。

](https://blog.csdn.net/shdabai/article/details/144064644)

[

_Docker__镜像_下载_\-__使用__github_ _action__\-_ 解决无法下载_docker__镜像_的问题

](https://blog.csdn.net/zhihu_0/article/details/142264100)

[小狐狸的博客](https://blog.csdn.net/zhihu_0)

09-14 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1267 

[

一种巧妙的方案，_使用__github_ _action_来解决无法下载_docker__镜像_的问题

](https://blog.csdn.net/zhihu_0/article/details/142264100)

[

在_github_上传_docker__镜像_\__github_ 上传_docker__镜像_

](https://blog.csdn.net/y1y_y1y/article/details/147878127)

8-8

[

先登录_GitHub_ 账号: gh auth login AI生成项目bash 1 选HTTPS,浏览器授权。_(_8位码可以在终端中看见,如下_)_ 3.然后给_镜像_打标签_(_tag_)_ echoyour\_token|_docker_ login ghcr.io _\-_u your\__github_\_username _\-__\-_password_\-_stdin AI生成项目bash 1 我的_GitHub_ 用户名是 y_\-_to,目标_镜像_名也叫 slam22.0_4_,命令: ...

](https://blog.csdn.net/y1y_y1y/article/details/147878127)

[

...minimap2/PROGENy的_docker__镜像__(_实操自用_)_\__github_ _docker__构建_ 访问_镜像_...

](https://blog.csdn.net/Meowbing/article/details/136993955)

8-5

[

在新仓库的根目录下,创建名为_Docker_file的文件,因为目的是创建minimap2的_容器_,因此可复制以下代码到_Docker_file文件_(_酌情修改_)_: FROM_Docker_hub上你想参考的_镜像_ RUNapt_\-_get update \\ &&apt_\-_get install _\-_y git \\ &&git clone https://_github_.com/lh3/minimap2\\ ...

](https://blog.csdn.net/Meowbing/article/details/136993955)

[

_使用__Github__Action__构建_蘑菇博客_镜像_提交_Docker_Hub

](https://blog.csdn.net/weixin_72525373/article/details/144013195)

[weixin\_72525373的博客](https://blog.csdn.net/weixin_72525373)

11-24 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 909 

[

这阵子_使用__Docker_Compose部署蘑菇博客， 但是还存在一些问题，就是每次我们需要下载源码，然后进行编译，打包，部署。而因为蘑菇博客还是前后端分离项目，因此为了完成这一系列的操作，就需要在环境中安装maven、node、git 等环境。

](https://blog.csdn.net/weixin_72525373/article/details/144013195)

[

_GitHub_热门推荐：_FastGPT_——零代码_构建_企业级知识库的AI神器

](https://devpress.csdn.net/v1/article/detail/147089642)

[pythonhy的博客](https://blog.csdn.net/pythonhy)

04-09 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1243 

[

今天推荐一个_GitHub_上斩获13.6K Star的明星项目——_FastGPT_，它不仅支持多模态文档解析、RAG增强生成，还能通过可视化工作流编排实现复杂业务场景的智能化升级。无论是初创团队还是大型企业，_FastGPT_都能让你的知识管理效率飙升！

](https://devpress.csdn.net/v1/article/detail/147089642)

[

_docker_ 关联 _github_ 自动化打_镜像_\__github_开源仓库打_docker__镜像_...

](https://blog.csdn.net/qq825193156/article/details/91586549)

8-5

[

本文详细介绍如何通过_Docker_和_GitHub_实现自动化_构建_流程,包括在_Docker_Hub中连接_GitHub_账户,配置自动化_构建_规则,以及如何在_Docker_file根目录下创建hooks以实现动态变量传递。 摘要生成于C知道,由 DeepSeek_\-_R1 满血版支持,前往体验 > _docker_关联_github_自动化打_镜像_ ...

](https://blog.csdn.net/qq825193156/article/details/91586549)

[

_使用_ _FastGPT_ 工作流搭建 _GitHub_ Issues 自动总结机器人

](https://blog.csdn.net/alex_yangchuansheng/article/details/143366633)

[云原生实验室](https://blog.csdn.net/alex_yangchuansheng)

10-30 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 992 

[

_GitHub_ 提供了强大的 API 让我们能够轻松获取 Issues 信息。这个接口默认返回最近的 30 条 Issues。可以参考_Github_ 的 API 文档以获得更多的信息。_FastGPT_ 是一个能让 AI 开发门槛大幅降低的工具。不管你是有技术背景的开发者，还是只是对 AI 感兴趣的小白，_FastGPT_ 都能帮你轻松入门，甚至可以让你在几分钟内_构建_出一个属于自己的 AI 应用。传统的 AI 开发，你需要掌握编程、算法、数据处理等复杂技能。

](https://blog.csdn.net/alex_yangchuansheng/article/details/143366633)

[

运行_fastGPT_ 第三步 打开_github_获取_fastGPT_最新版

](https://blog.csdn.net/weixin_46801290/article/details/145142998)

[weesky](https://blog.csdn.net/weixin_46801290)

01-14 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 2065 

[

简单看下，_fastGPT_的框架，它依赖两个库，还有一个叫oneapi的来管理与大模型的接口。部署的话，只要拿到_Docker_Compose文件即可，compose文件就是一个自动化脚本安装文件，里面有所有的配置信息，依赖，和一些_docker_的配置。对于个人用_fastGPT_，这种简单调用，没有并发的，小量的客服应用。

](https://blog.csdn.net/weixin_46801290/article/details/145142998)

[

【大模型实战（二）】_使用_ _FastGPT_ 工作流搭建 _GitHub_ Issues 自动总结机器人

](https://devpress.csdn.net/v1/article/detail/143589718)

[Androiddddd的博客](https://blog.csdn.net/Androiddddd)

11-07 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 2081 

[

为了生成高质量的摘要，我们_使用_大语言模型来处理和总结 Issues 内容。你是一个简洁高效的 _GitHub_ Issue 概述助手，专长于提炼核心问题并以清晰简洁的方式呈现。## 任务分析输入的多条 issue 信息，为每个 issue 创建一个简明扼要的概述。_使用_中文输出。## 输入格式JSON 数组，每项包含 title_(_标题_)_、body_(_内容_)_和 url_(_链接_)_。## 输出格式对每个 issue _使用_ Markdown 语法创建简洁的概述块。

](https://devpress.csdn.net/v1/article/detail/143589718)

[

_Docker_部署ChatGLM3、One API、_FastGPT_

](https://devpress.csdn.net/v1/article/detail/136665991)

[北海刘德华的博客](https://blog.csdn.net/qq_39935901)

03-12 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 2786 

[

Windows PowerShell，我是用 Git Bash Here, 两个都是一样的。创建两个文件 _docker__\-_compose.yml 和 config.json。运行成功了，可以_使用_ _docker_ ps 命令检查以下所有_容器_是否正常启动。在你自己喜欢的磁盘上创建_fastgpt_目录，我是 D:\\_fastgpt_。_(_其中挂载路径 D:\\one_\-_api 可以选择你自己喜欢的目录_)_改成你的IP，和刚才在 One API 中复制的令牌。测试一下刚刚创建的渠道。

](https://devpress.csdn.net/v1/article/detail/136665991)

[

保姆级教程：_FastGPT__构建_个人本地知识库_(__Docker_ compose快速部署_)_

热门推荐

](https://devpress.csdn.net/v1/article/detail/135733446)

[m0\_62536353的博客](https://blog.csdn.net/m0_62536353)

01-22 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 5万+ 

[

_FastGPT__构建_个人知识库，_使用__Docker_ compose部署

](https://devpress.csdn.net/v1/article/detail/135733446)

[

_FastGPT_编译前端界面，并将前端界面映射到_Docker__容器_中

](https://blog.csdn.net/lanyan90/article/details/138182466)

[盛世芳华](https://blog.csdn.net/lanyan90)

04-25 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1983 

[

具体原因不明，但前端实际上已经编译成功了，在projects/app目录下输入ll命令，能看到一个.next文件夹，这个文件夹存放的就是编译后的前端文件。注意：编译过程中会出现非常多的提示，但只要出现 ✓ Compiled successfully就说明已经编译成功。通过浏览器localhost:3000即可热修改，如果首次执行提示错误，则重新执行一下命令即可。此时会自动下载依赖包，这里如果执行npm install的话，会出现各种错误。_4_、前端代码都在projects/app目录下，修改即可。

](https://blog.csdn.net/lanyan90/article/details/138182466)

[

大模型应用\__FastGPT_

](https://devpress.csdn.net/v1/article/detail/134980709)

[谢彦的技术博客](https://blog.csdn.net/xieyan0811)

12-13 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1940 

[

_FastGPT_ 是一个基于 LLM 大语言模型的知识库问答系统，提供开箱即用的数据处理、模型调用等能力。同时可以通过 Flow 可视化进行工作流编排，从而实现复杂的问答场景！

](https://devpress.csdn.net/v1/article/detail/134980709)

[

大模型LLM | 从零开始带你基于 _FastGPT_ 搭建本地私有化知识库！看这一篇就够了！

](https://devpress.csdn.net/v1/article/detail/142816327)

[Code1994的博客](https://blog.csdn.net/Code1994)

10-10 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1385 

[

AI大模型作为人工智能领域的重要技术突破，正成为推动各行各业创新和转型的关键力量。抓住AI大模型的风口，掌握AI大模型的知识和技能将变得越来越重要。_学习_AI大模型是一个系统的过程，需要从基础开始，逐步深入到更高级的技术。这里给大家精心整理了一份全面的AI大模型_学习_资源，包括：AI大模型全套_学习_路线图（从入门到实战）、精品AI大模型_学习_书籍手册、视频教程、实战_学习_、面试题等，资料免费分享！

](https://devpress.csdn.net/v1/article/detail/142816327)

[

_Docker__镜像_自动化_构建_与推送至_GitHub_操作指南

](https://wenku.csdn.net/doc/3pbvt3eptj)

[

接着，_使用_\`mr_\-_smithers_\-_excellent/_docker__\-_build_\-_push\`这个_GitHub_ _Action_，可以直接在\`._github_/workflows.yml\`文件中定义工作流程，实现_构建_和推送_Docker__镜像_的自动化。 ### 知识点五：标签和压缩包子文件 #### ...

](https://wenku.csdn.net/doc/3pbvt3eptj)

*   [关于我们](//www.csdn.net/company/index.html#about)
*   [招贤纳士](//www.csdn.net/company/index.html#recruit)
*   [商务合作](https://fsc-p05.txscrm.com/T8PN8SFII7W)
*   [寻求报道](//marketing.csdn.net/questions/Q2202181748074189855)
*   ![](https://g.csdnimg.cn/common/csdn-footer/images/tel.png)
     400-660-0108
*   ![](https://g.csdnimg.cn/common/csdn-footer/images/email.png)
     [kefu@csdn.net](mailto:webmaster@csdn.net)
*   ![](https://g.csdnimg.cn/common/csdn-footer/images/cs.png)
     [在线客服](https://csdn.s2.udesk.cn/im_client/?web_plugin_id=29181)
*   工作时间 8:30-22:00

*   ![](https://g.csdnimg.cn/common/csdn-footer/images/badge.png)
    [公安备案号11010502030143](http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010502030143)
*   [京ICP备19004658号](http://beian.miit.gov.cn/publish/query/indexFirst.action)
*   [京网文〔2020〕1039-165号](https://csdnimg.cn/release/live_fe/culture_license.png)
*   [经营性网站备案信息](https://csdnimg.cn/cdn/content-toolbar/csdn-ICP.png)
*   [北京互联网违法和不良信息举报中心](http://www.bjjubao.org/)
*   [家长监护](https://download.csdn.net/tutelage/home)
*   [网络110报警服务](https://cyberpolice.mps.gov.cn/)
*   [中国互联网举报中心](http://www.12377.cn/)
*   [Chrome商店下载](https://chrome.google.com/webstore/detail/csdn%E5%BC%80%E5%8F%91%E8%80%85%E5%8A%A9%E6%89%8B/kfkdboecolemdjodhmhmcibjocfopejo?hl=zh-CN)
*   [账号管理规范](https://blog.csdn.net/blogdevteam/article/details/126135357)
*   [版权与免责声明](https://www.csdn.net/company/index.html#statement)
*   [版权申诉](https://blog.csdn.net/blogdevteam/article/details/90369522)
*   [出版物许可证](https://img-home.csdnimg.cn/images/20250103023206.png)
*   [营业执照](https://img-home.csdnimg.cn/images/20250103023201.png)
*   ©1999-2025北京创新乐知网络技术有限公司

 [![](https://profile-avatar.csdnimg.cn/f941fb46a40b49b68fa8ddbb7d22e0d1_m0_37827702.jpg!1)](https://blog.csdn.net/m0_37827702) 

[努力的小Qin](https://blog.csdn.net/m0_37827702 "努力的小Qin")

博客等级 ![](https://csdnimg.cn/identity/blog4.png)

码龄8年

[

48

原创

](https://blog.csdn.net/m0_37827702)

193

点赞

274

收藏

106

粉丝

关注

[私信](https://im.csdn.net/chat/m0_37827702)

 [![](https://i-operation.csdnimg.cn/images/bfc20af708654cc689adbb6361f6dc98.png)](https://mpbeta.csdn.net/edit?utm_source=blog) 

 [![](https://i-operation.csdnimg.cn/images/c6b71c951e9045f29a474f412131534a.jpeg)](https://blog.csdn.net/blogdevteam/article/details/149360986?utm_source=blog_zsst) 

 [![](https://i-operation.csdnimg.cn/images/bfc20af708654cc689adbb6361f6dc98.png)](https://mpbeta.csdn.net/edit?utm_source=blog) 

 [![](https://i-operation.csdnimg.cn/images/c6b71c951e9045f29a474f412131534a.jpeg)](https://blog.csdn.net/blogdevteam/article/details/149360986?utm_source=blog_zsst) 

![](https://kunyu.csdn.net/1.png?p=56&adBlockFlag=0&adId=1072555&a=1072555&c=3159296&k=Fastgpt学习（4）- 使用Github Action构建Docker镜像&spm=1001.2101.3001.5000&articleId=143209607&d=1&t=3&u=5da907199f2a4b0aa8b7e06bd35d5762)

### 热门文章

*   [活动中的 findViewById()方法总结以及Button按钮的使用 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     10015](https://blog.csdn.net/m0_37827702/article/details/77366269) 
*   [阿里iconfont使用方法 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     7904](https://blog.csdn.net/m0_37827702/article/details/122930773) 
*   [1002:方便记忆的电话号码 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     4741](https://blog.csdn.net/m0_37827702/article/details/78406142) 
*   [KMP算法之nextval数组 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     3942](https://blog.csdn.net/m0_37827702/article/details/82789406) 
*   [双链表--尾插法构造（c语言） ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     3509](https://blog.csdn.net/m0_37827702/article/details/82558389) 

### 分类专栏

*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756918.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      大模型](https://blog.csdn.net/m0_37827702/category_12809074.html) 8篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756724.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      数据库](https://blog.csdn.net/m0_37827702/category_12805839.html) 4篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756724.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      服务器](https://blog.csdn.net/m0_37827702/category_12898351.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756922.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      虚拟机](https://blog.csdn.net/m0_37827702/category_12809712.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756928.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      Docker](https://blog.csdn.net/m0_37827702/category_12807269.html) 3篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756930.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      Git](https://blog.csdn.net/m0_37827702/category_12804835.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756780.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      前端冲冲冲](https://blog.csdn.net/m0_37827702/category_11633339.html) 12篇

展开全部 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/arrowup-line-bot-White.png)
 收起 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/arrowup-line-top-White.png) 

上一篇：

[FastGPT学习（3）- Error：Operation \`users.findOne()\` buffering timed out after 10000ms 解决方案](https://blog.csdn.net/m0_37827702/article/details/143202217)

下一篇：

[曙光服务器安装centos8](https://blog.csdn.net/m0_37827702/article/details/145730401)

### 最新评论

*   [CentOS7安装Mysql5.7（ARM64架构）](https://blog.csdn.net/m0_37827702/article/details/142880727#comments_35292321)
    
    [PerfectOpening:](https://blog.csdn.net/PerfectOpening) 但是不是说离线吗，那怎么下，我这里是内网，没有网的
    
*   [CentOS7安装Mysql5.7（ARM64架构）](https://blog.csdn.net/m0_37827702/article/details/142880727#comments_35292188)
    
    [努力的小Qin:](https://blog.csdn.net/m0_37827702) 先百度一下错误信息吧，我猜可能是网络的问题需要切到国内源
    
*   [CentOS7安装Mysql5.7（ARM64架构）](https://blog.csdn.net/m0_37827702/article/details/142880727#comments_35292160)
    
    [PerfectOpening:](https://blog.csdn.net/PerfectOpening) 为啥我yum install libatomic 下载失败
    
*   [KMP算法之nextval数组](https://blog.csdn.net/m0_37827702/article/details/82789406#comments_8992051)
    
    [小人物大梦想:](https://blog.csdn.net/weixin_41858542) Any code of your own that you haven’t looked at for six or more months might as well have been written by someone else.诚信互关，让我们一起互相学习吧！来自一个不屈服命运的老菜鸟！
    

### 最新文章

*   [From Local to Global: A Graph RAG Approach to Query-Focused Summary 阅读笔记](https://blog.csdn.net/m0_37827702/article/details/149901175)
*   [配置ollama使用GPU](https://blog.csdn.net/m0_37827702/article/details/149782983)
*   [oneapi本地部署接口测试（curl命令方式+postman方式）](https://blog.csdn.net/m0_37827702/article/details/149752894)

[2025年7篇](https://blog.csdn.net/m0_37827702?type=blog&year=2025&month=08)

[2024年11篇](https://blog.csdn.net/m0_37827702?type=blog&year=2024&month=10)

[2022年12篇](https://blog.csdn.net/m0_37827702?type=blog&year=2022&month=04)

[2020年1篇](https://blog.csdn.net/m0_37827702?type=blog&year=2020&month=02)

[2018年7篇](https://blog.csdn.net/m0_37827702?type=blog&year=2018&month=09)

[2017年14篇](https://blog.csdn.net/m0_37827702?type=blog&year=2017&month=11)

![](https://kunyu.csdn.net/1.png?p=57&adBlockFlag=0&adId=1072038&a=1072038&c=3119018&k=Fastgpt学习（4）- 使用Github Action构建Docker镜像&spm=1001.2101.3001.5001&articleId=143209607&d=1&t=3&u=6aa99630576940b0b9f86c7f3783d898)

### 目录

1.  [1\. 背景](#t0)
2.  [2\. 操作步骤](#t1)
3.  1.  [2.1 fork仓库 & 配置仓库信息](#t2)
    2.  [2.2 修改配置文件](#t3)

展开全部 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/arrowup-line-bot-White.png)

收起 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/arrowup-line-top-White.png)

![](https://kunyu.csdn.net/1.png?p=530&adBlockFlag=0&adId=1072027&a=1072027&c=3035778&k=Fastgpt学习（4）- 使用Github Action构建Docker镜像&spm=1001.2101.3001.4647&articleId=143209607&d=1&t=3&u=d291c5aa38d840e6994cd14f267d20b0)

### 目录

1.  [1\. 背景](#t0)
2.  [2\. 操作步骤](#t1)
3.  1.  [2.1 fork仓库 & 配置仓库信息](#t2)
    2.  [2.2 修改配置文件](#t3)

展开全部 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/arrowup-line-bot-White.png)

收起 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/arrowup-line-top-White.png)

![](https://kunyu.csdn.net/1.png?p=479&adId=1071044&adBlockFlag=0&a=1071044&c=0&k=Fastgpt学习（4）- 使用Github Action构建Docker镜像&spm=1001.2101.3001.4834&articleId=143209607&d=1&t=3&u=06ac0fdb408e491bbbeef1db6ca7d3b8)

上一篇：

[FastGPT学习（3）- Error：Operation \`users.findOne()\` buffering timed out after 10000ms 解决方案](https://blog.csdn.net/m0_37827702/article/details/143202217)

下一篇：

[曙光服务器安装centos8](https://blog.csdn.net/m0_37827702/article/details/145730401)

### 分类专栏

*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756918.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      大模型](https://blog.csdn.net/m0_37827702/category_12809074.html) 8篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756724.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      数据库](https://blog.csdn.net/m0_37827702/category_12805839.html) 4篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756724.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      服务器](https://blog.csdn.net/m0_37827702/category_12898351.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756922.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      虚拟机](https://blog.csdn.net/m0_37827702/category_12809712.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756928.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      Docker](https://blog.csdn.net/m0_37827702/category_12807269.html) 3篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756930.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      Git](https://blog.csdn.net/m0_37827702/category_12804835.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756780.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      前端冲冲冲](https://blog.csdn.net/m0_37827702/category_11633339.html) 12篇

展开全部 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/arrowup-line-bot-White.png)
 收起 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/arrowup-line-top-White.png) 

登录后您可以享受以下权益：

*   ![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAAAXNSR0IArs4c6QAAAvRJREFUWEfVl+1P0lEUx79XDGNubZqJqCssk2zOHqyVgWTYQgm1rcWW2kt//gf9Ef0H4bss22y9yMdcSgqStqzmG582Agsf2Cy3pjYV+LV7lZ9AKOCgX51XwL33nM/5nnPPLgQiGxE5PkIAWltf5vO8/xEPvhKAIsFwiwRkiJCUh83Nd90B3wIADe7nfRMAMhMcONzdjxQiOReAEADM5hftPPj7SQ7O3BOQ5xx3r2H78449NncsJEH2vfJZbOFMueEA/N/IPhCjhTOx5IMV+D8BcnKycEZVgNGxCWxsbMYsYtwKpKfLcLOqnAV53T8iBLpTX4Xs7Ex09wyjtLQIaVIpBgZHsbb2a1+YuAAyMo7AUKMFhVhaWkZn11vmnH5vbDDC6/XhSdsrtocqsrq2jr4+G1ZWfu4JETNAjjwLer0aaWlSFpxmv7m5xRyXlJzGtfLzcDrdeDMwCqn0EKr1GgYRUMrj+R4RIiYA5Ylc6HRXkZoqgcs1j0HLe/h8PsFhrbESCsUxDFrG4HB8Y79LJBJU6a5AqcxjytC1uTl6w0MtKoCqSAmt9hIIIZiccsBu/wye370oMtlhNDUa4ffzTP6tLa8QgZ7RqC+iuPgkOzNsHcfsrCuEICoArS2ruWcZnZ3bNQ826rxCU4a5rwvo77dHlLm+Tge5/ChryGft3fEBqFQF0FaUbSsw6YD9XagCBoMW+XlyDA1/+CM7ekatvoCzxaeYAlbrOGbiVYDi0jrSetK6Ol3zsOz0AG3IB011AHi0Pe0Kuf/hPWCxjMF1kB4I6EU7Wn8r9BZQsMrrl+F2e9DbZxWkDb8FtDS0hJEsag8EHwqfA6ur6ygsPA6b7SOmpr8IW+tqbyR+DgS8B0/C6RknCpR5sI18gte72/3V1ZrkTMJ9Z+oBF+MqwQFj7HssEoC4DxLRn2SiP0ppwUR9liej0WLx+W/9MwomNps7enjAEEsW0fYQoJfjTLcj7dtTgUQCAOhp4UzGuACiZZWoddF74De0FoIwwHUb7wAAAABJRU5ErkJggg==)
    免费复制代码
*   ![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAAAXNSR0IArs4c6QAAApJJREFUWEfNl7tuE0EUhv+z5AGChZAwPEAiCnAKGmioIKLgIrLKAyRrJ6VdUtimJ6KK7YkfIFoiEooooaKBhiJAgZwXSCIhZPIAZg6awRt5zV5mxomEq5XnzH++c5nZswTHX6ezNQOSa3o7e9Vy+fmhixTZbup2w8JvpjqYVwFMDfcPQLR+ibi5tOT3bTSNAer1D1PXrv9cIXADQCHFSZ9BjZOjK61m8/7ABMQIQIg38wx+BWDWRBRAjyWqlYq/n2efCbCxsTkr2VOO5/OEUtb3PJK15eXFXtr+RABVZym5waCVkTo7MmBA4JbnUSOpP2IAhnV2BUnsjzMAhzq7gvQIVAuChT0lcAbQESGnKjK+6DVCycirgX058LVvE4CDy9O4o4z7p9gl4EEWBAPvC9N4pGx+neIzgLkke2MAAj4FgX9PibS6WyVPyoMsAAJKQeB/VTZChB8ZuDsRgLpoWcpSpbL4TQl1RLgN4EkKxE458J+qtXZ78xZ5nipd4kkzzoC+6oHtSuA/y8kCEzAXRd8W4VsCNMykGdAMBlkwjl4JWmXAIAtW0TsB5GTBKnpXgFgvCBHeZuj7wTp6Z4BxZ8MToeqpm20IpY5p7lvWugeiTh49Ecqh+j/q/JwjGjsMzgDjWYhUbaKfpATaHwHvgsCPXUZChDsMPM66JUfXJsmA1mGgdnL0/bV6Lt64+RKMF6bOEzMwfB2rKXfGQigaQNNmxCSpQwJV/3kdK0s1kBSLP1ZBVM8YPC34YqZ9MDePj6+ujw6s/9dINh6aHkrhrYHx0Clswr4HWbUeSsedOYxrsbErCz73xoo2Gw6sF/NhMhpBysieOXqfSwYS++PvRwvyPj4uBMCpKRM2GffAeTkc1/kDgiVyMIKxs7oAAAAASUVORK5CYII=)
    和博主大V互动
*   ![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAAAXNSR0IArs4c6QAAAYZJREFUWEftVbtOw0AQnEsRrIhP4NHnTyhS5ighBXchfAAdBR30oPgoQlqbLkL8SWok8gnIilNk0UkYodjxrZ3EbuLO8uzs7Mx5T6DmR9TcH2wBxoRnBDIAjhyiZwJCKdX94AzHFuCb4IvRPOk500oeb1sAcQgTjFaSNRwLZEl9E+wF7B3YO1CNAwU2XpG1ABDsIrvWWr7/L0ztgYIbr7AIreWJS8AngNNizGx0akWnHPiN4A1Ai03LA0YgSGcElms4DNqigRBAm8ftRE1piW6/L6eryLV3ge9PWmjMn0F04aTPAwgxxtIbaN2JsmDOy8iY4JKApxKRRCAaaH0+ztXHma5EJGstZ0ewCmRH4rC8tICkMCeSSAA3SslXjqsJxnkGssgyImFbvrEDCcFoNPIWi8OOfW82vye9Xm9eZPKNHCjTaF1NqQh2IsB/Ce9BdGsd3WaDDK4YQjzqq+6d/fbngG+CuILmiZ5YK+mtCrCH6GDH0+cIqC6CBYR4SEVQ0eSpNrX/BT/MdqghTZsnOgAAAABJRU5ErkJggg==)
    下载海量资源
*   ![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAAAXNSR0IArs4c6QAAAqVJREFUWEfFlktoE1EUhv+ThynioxV1KQq6URAUunDpQrAVLLZmTBHRlGQyYqlQ3LgIWuxCBDdBk8xMJCBVYRIXgrb42goKLgTRhSKI2k0RWkhJW5s5MsG0SazJncxIZjXMPed8/51z/zNDaPNFbebjvwhIp4295MVNMA4BmAFxdvr79htjY4eX6zfsugBVzUVAfAtAoA72bJ1/vi8cDi9UP3dNQDab7Vj6teE2wEP/aisBzwsF9I2OSsVKjCsCUqkHOz1e70MABwXO1IvpH9t6Ku1wLEDTcj0MngCwRQBeDmFQXJGD49Z9ywKYmXQ9F2fgCgCPKPxP3OeYLO1pWUAyea/L5/NPMNBrE1wJn43JUldLAlKZ/AGPaVr93tUi3EqbislSWbytFmiacY6BFIAOB/B5D5nd0Wjoo7CARGIyEAgUEiDIDsBW6ifTY/afj4TeC9tQVY0dIOQBdDuBE/CIGWdjMWlOeBCldeMIMe4D2OoAXiJQPBo9eZ2IWGgUWxbTMsZlMF1rwWLVjBk2aVBRgi8bTMfaJVU1NoNwF8BxB7u2Ul8v+0rBC0OD3xrVqXGBruf3m1y22G4ncAKlOzv5oiRJS83qrAjQtPw+hvkGwPpmSQ3Wi0ykKNGg9QaFrhUBqm5MgXFUKGutIMYXZrNfUULv7NRYFaAZlj022UmuxDLwOOD3nwmHT8zaza8W8JdFBIqZYL4qy9L4WhYTyF8dxapm2BNA+EnMp2X51FMRUFMb2hHAwFufxzsQiQx8dQK3cu23gDizWNw4PDLSu+gUXi+g1GTqLTBhWIlKd9wAV2pU2zAJLn/tvHUAyx2v2MQlRZE+uAmveQNuFxatZ+uHRLSonbiqUWw8cfCPZ4dpnfxJWZaO1bRA09oswNYWXAxu+xn4DRv63CEjK31nAAAAAElFTkSuQmCC)
    发动态/写文章/加入社区

×立即登录

评论 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/closeBt.png)

![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentArrowLeftWhite.png)
被折叠的  条评论 [为什么被折叠?](https://blogdev.blog.csdn.net/article/details/122245662) [ ![](https://csdnimg.cn/release/blogv2/dist/pc/img/iconPark.png)
到【灌水乐园】发言](https://bbs.csdn.net/forums/FreeZone)

查看更多评论![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentArrowDownWhite.png)

添加红包

祝福语

 

请填写红包祝福语或标题

红包数量

 个

红包个数最小为10个

红包总金额

 元

红包金额最低5元

余额支付

当前余额3.43元 [前往充值 >](https://i.csdn.net/#/wallet/balance/recharge)

需支付：10.00元

取消 确定

成就一亿技术人!

领取后你会自动成为博主和红包主的粉丝 [规则](https://blogdev.blog.csdn.net/article/details/128932621)

 ![](https://profile-avatar.csdnimg.cn/default.jpg!2) 

hope\_wisdom

发出的红包

实付元

[使用余额支付](javascript:;)

![](https://csdnimg.cn/release/blogv2/dist/pc/img/pay-time-out.png)
 点击重新获取

![](https://csdnimg.cn/release/blogv2/dist/pc/img/weixin.png)
![](https://csdnimg.cn/release/blogv2/dist/pc/img/zhifubao.png)
![](https://csdnimg.cn/release/blogv2/dist/pc/img/jingdong.png)
扫码支付

 钱包余额 0

![](https://csdnimg.cn/release/blogv2/dist/pc/img/pay-help.png)

抵扣说明：

1.余额是钱包充值的虚拟货币，按照1:1的比例进行支付金额的抵扣。  
2.余额无法直接购买下载，可以购买VIP、付费专栏及课程。

[![](https://csdnimg.cn/release/blogv2/dist/pc/img/recharge.png)
余额充值](https://i.csdn.net/#/wallet/balance/recharge)

 

确定取消![](https://csdnimg.cn/release/blogv2/dist/pc/img/closeBt.png)

举报

![](https://csdnimg.cn/release/blogv2/dist/pc/img/closeBlack.png)

选择你想要举报的内容（必选）

*   内容涉黄
*   政治相关
*   内容抄袭
*   涉嫌广告
*   内容侵权
*   侮辱谩骂
*   样式问题
*   其他

原文链接（必填）

请选择具体原因（必选）

*   包含不实信息
*   涉及个人隐私

请选择具体原因（必选）

*   侮辱谩骂
*   诽谤

请选择具体原因（必选）

*   搬家样式
*   博文样式

补充说明（选填）

取消

确定

 [![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/Group.png)
 点击体验  
DeepSeekR1满血版](https://ai.csdn.net?utm_source=cknow_pc_blogdetail&spm=1001.2101.3001.10583)![](https://g.csdnimg.cn/side-toolbar/3.6/images/mobile.png)

 下载APP

![](https://g.csdnimg.cn/side-toolbar/3.6/images/qr_app.png)

程序员都在用的中文IT技术交流社区

 公众号

![](https://g.csdnimg.cn/side-toolbar/3.6/images/qr_wechat.png)

专业的中文 IT 技术社区，与千万技术人共成长

 视频号

![](https://g.csdnimg.cn/side-toolbar/3.6/images/qr_video.png)

关注【CSDN】视频号，行业资讯、技术分享精彩不断，直播好礼送不停！

 ![](https://g.csdnimg.cn/side-toolbar/3.6/images/customer.png)
 客服 ![](https://g.csdnimg.cn/side-toolbar/3.6/images/totop.png)
 返回顶部 

↑↓⇔⇧⇩

 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/quoteClose1White.png) 

![](https://i-blog.csdnimg.cn/direct/a3775e34de714143be11caa94ad83679.png)

![](https://i-blog.csdnimg.cn/direct/2612eaa460ca45f08ca111ca41218a0d.png)

![](https://i-blog.csdnimg.cn/direct/fad7863e17c0488b83fce2c938fab091.png)

![](https://i-blog.csdnimg.cn/direct/681a7292fe2748aa958c1cbaca183348.png)

![](https://i-blog.csdnimg.cn/direct/b7f4adf94a604120a64a010aab562537.png)

![](https://i-blog.csdnimg.cn/direct/49d4c39af7964f7c8dfe9d5cc0df40d6.png)

![](https://i-blog.csdnimg.cn/direct/ece1e0686c794086bd254aa4a8ac4613.png)