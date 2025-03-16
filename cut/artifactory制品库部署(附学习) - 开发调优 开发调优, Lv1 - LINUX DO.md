# artifactory制品库部署(附学习) - 开发调优 / 开发调优, Lv1 - LINUX DO
 artifactory制品库部署(附学习) - 开发调优 / 开发调优, Lv1 - LINUX DO                                               

[跳到主要内容](#main-container)

 [![](https://linux.do/uploads/default/original/3X/b/4/b4fa45d8b03df61f5d011e173c0adf8497028b16.png)](/) 

*   ​
*    ![](https://linux.do/letter_avatar_proxy/v4/letter/n/58f4c7/96.png) 

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

[artifactory制品库部署(附学习)](/t/topic/490791)


==========================================

[开发调优](/c/develop/4)

[开发调优, Lv1](/c/develop/develop-lv1/20)

[VPS](/tag/vps)

您已选择 **0** 个帖子。

全选

取消选择

​

[3月 13 日](/t/topic/490791/1 "跳到第一个帖子")

1 / 2

3月 13 日

[3 天](/t/topic/490791/2)

​

[![](https://linux.do/user_avatar/linux.do/dalamud/96/449770_2.png)
](/u/dalamud)

[dalamud](/u/dalamud)

[3 天](/t/topic/490791?u=niyan2025 "发布日期")

#### [](#p-4528350-artifactory-1)什么是artifactory

JFrog Artifactory 是用于存储和管理整个软件供应链中使用的所有制品、二进制文件、软件包、元数据、容器镜像和开源组件的唯一解决方案。JFrog Artifactory 可作为您的 DevOps 平台枢纽，与您的软件工具和流程无缝集成以提高自动化程度和完整性，并在此过程中融入最佳实践

简而言之，市面上常见二进制文件和大部分包管理器都支持，并实现 DevOps 流程的自动化，跟它类似的竞品是Sonatype Nexus Repository

#### [](#p-4528350-h-2)准备工作

关于桥接网络可以查看[podman](https://linux.do/t/topic/479114#p-4413311-h-11)

部署了解

| 桥接网络 | 内部 | 备注 |
| --- | --- | --- |
| traefik-internal | 是 |  |
| traefik-external | 否 |  |

postgres数据库

其他数据请访问[官方知识库](https://jfrog.com/help/r/jfrog-installation-setup-documentation/database-configuration)

了解详情

```


`CREATE USER artifactory WITH PASSWORD 'password';
CREATE DATABASE artifactory WITH OWNER=artifactory ENCODING='UTF8';
GRANT ALL PRIVILEGES ON DATABASE artifactory TO artifactory;` 
```

#### [](#p-4528350-artifactory-3)artifactory部署

> 注意：  
> 1\. 版本间无法简单替换版本进行降级，所以谨慎升级  
> 2\. 版本7.90.x以上，授权破解情况下，访问管理页面安全选项下密钥管理和Vault会报forbiden、日志报license非法信息，但实际不影响使用，强迫症请保持在7.84.23不要升级，部分新功能和仓库不支持，比如抱抱脸ML模型和新UI等  
> 3\. 如果使用非postgres数据库，请启动一次容器，自动生成默认配置后，编辑数据挂载目录下`artifactory_data/etc/system.yaml`文件，修改配置如下后重启容器，即可使用非postgres数据库

```


`shared:
    database:
        allowNonPostgresql: true` 
```

> 4\. nginx容器是为了做URL重写，实现个人需求，最后再套一层traefik，可以根据自身需求要不要部署，我主要是为了去掉7.x版本以上访问仓库要带路径artifactory的问题，使用nginx可以实现以下需求  
> 普通仓库URL重写，仓库名为debian  
> [https://reg.example.com/artifactory/debian/](https://reg.example.com/artifactory/debian/)
> 
> \=> [https://reg.example.com/debian/](https://reg.example.com/debian/)
> 
>   
> 容器仓库URL重写，仓库名为cr  
> [https://reg.example.com/artifactory/cr/library/nginx:latest](https://reg.example.com/artifactory/cr/library/nginx:latest)
> 
> \=> [https://reg.example.com/cr/nginx:latest](https://reg.example.com/cr/nginx:latest)
> 
>   
> [https://reg.example.com/artifactory/cr/linuxserver/plex:latest](https://reg.example.com/artifactory/cr/linuxserver/plex:latest)
> 
> \=> [https://reg.example.com/cr/linuxserver/plex:latest](https://reg.example.com/cr/linuxserver/plex:latest)
> 
>   
> 还有对于ui、docker api的重写这里不过多介绍  
> 如果你要用nginx配置，第一次启动请先将artifactory两个端口暴露出来，登录`http://SERVER_HOSTNAME:8082/ui/`后导航到`Administration`→`General Management`→`Settings`修改`Custom Base URL`为反代后的域名，导航到`Administration`→`Artifactory Settings`→`HTTP Settings`将`Docker Access Method`改为`Port`然后保存，再重启nginx容器，能正常用域名访问后关掉容器，注释之前暴露的端口配置，然后重新启动  
> 5\. 想要学习请访问[仓库](https://github.com/Lama3L9R/ArtifactoryKeygen)
> 
> ，下载对应`.jar`包，并修改compose文件`EXTRA_JAVA_OPTIONS`，示例配置将`.jar`包放到数据挂载目录下就行，请不要商用！请不要商用！请不要商用！  
> 6\. 关于数据库jdbc驱动，下载后请手动创建`./artifactory_data/bootstrap/artifactory/tomcat/lib`目录，将驱动放到该目录下，会自动识别，确保挂载目录属主属组为1030

podman-compose.yaml

```


`services:
  nginx:
    image: nginx:alpine
    container_name: artifactory-nginx
    volumes:
      - /data/podman/core/artifactory_nginx/conf.d:/etc/nginx/conf.d
      - /etc/localtime:/etc/localtime:ro
    networks:
      - traefik-external
    depend_on: artifactory
    # ports:
    #   - "443:443"
    expose:
      - 443
    restart: unless-stopped
    ulimits:
      nproc: 65535
      nofile:
        soft: 32000
        hard: 40000

  artifactory:
    image: releases-docker.jfrog.io/jfrog/artifactory-pro:7.104.10
    #image: releases-docker.jfrog.io/jfrog/artifactory-pro:7.84.23
    container_name: artifactory
    volumes:
      - ./artifactory_data:/var/opt/jfrog/artifactory
      - /etc/localtime:/etc/localtime:ro
    networks:
      - traefik-internal
      - traefik-external
    restart: unless-stopped
    ulimits:
      nproc: 65535
      nofile:
        soft: 32000
        hard: 40000
    environment:
      - ENABLE_MIGRATION=y
      # The following must match the POSTGRES_USER and POSTGRES_PASSWORD values passed to PostgreSQL
      - JF_SHARED_DATABASE_TYPE=postgresql
      - JF_SHARED_DATABASE_USERNAME=artifactory
      - JF_SHARED_DATABASE_PASSWORD=password
      - JF_SHARED_DATABASE_DRIVER=org.postgresql.Driver
      - JF_SHARED_DATABASE_URL=jdbc:postgresql://postgres:5432/artifactory
      #- JF_SHARED_DATABASE_TYPE=mariadb
      #- JF_SHARED_DATABASE_USERNAME=admin
      #- JF_SHARED_DATABASE_PASSWORD=password
      #- JF_SHARED_DATABASE_DRIVER=org.mariadb.jdbc.Driver
      #- JF_SHARED_DATABASE_URL=jdbc:mariadb://mariadb:3306/jfrog?characterEncoding=UTF-8&elideSetAutoCommits=true&useSSL=false&useMysqlMetadata=true
      - EXTRA_JAVA_OPTIONS=-javaagent:/opt/jfrog/artifactory/var/ArtifactoryAgent-1.0-790fix-SNAPSHOT-all.jar #7.90.x以上版本
      #- EXTRA_JAVA_OPTIONS=-javaagent:/opt/jfrog/artifactory/var/ArtifactoryAgent-1.0-SNAPSHOT-all.jar #7.84.23以下版本
      - JF_SHARED_NODE_IP=127.0.0.1
      - JF_SHARED_NODE_ID=reg.example.com
      - JF_SHARED_NODE_NAME=reg.example.com
      - JF_ROUTER_ENTRYPOINTS_EXTERNALPORT=8082
    # ports:
    # - 8082:8082 # router通信端口
    # - 8081:8081 # artifactory通信端口

networks:
  traefik-internal:
    external: true
  traefik-external:
    external: true` 
```

#### [](#p-4528350-h-4)配置文件

##### [](#p-4528350-artifactory-5)artifactory配置

`./artifactory_data/etc/system.yaml` #无特殊需求修改上文中数据库限制配置即可，其他配置请参考同级目录下的`system.full-template.yaml`有全部配置项和详细注释

`./artifactory_data/etc/artifactory/binarystore.xml` #可修改二进制文件存储类型，占用空间很大，以下配置示例简单修改了存放目录，该目录要求持久化，当然也支持别的存储，根据自己情况进行修改，详细配置请访问[官方仓库](https://jfrog.com/help/r/jfrog-installation-setup-documentation/filestore-configuration?tocId=hS3UwondOI4%7E%7Eh69gAdHiw)

```


`<config version="v1">   
       <chain template="file-system"/>
       <provider id="file-system" type="file-system">
               <baseDataDir>/data/binaries</baseDataDir> 
       </provider>
</config>` 
```

##### [](#p-4528350-nginx-6)nginx配置

```


`upstream artifact {
    server artifactory:8081;
    }
upstream artifact-router {
    server artifactory:8082;
    }

server {
    listen 80;
    server_name reg.example.com;
    index index.html index.htm;

    if ($http_x_forwarded_proto = '') {
        set $http_x_forwarded_proto $scheme;
         }

    rewrite ^/$ /ui/ redirect;
    rewrite ^/ui$ /ui/ redirect;
    rewrite ^/(v1|v2)/(.*) /artifactory/api/docker/cr/$1/$2 last;
    rewrite ^/api/docker/(.*)/(v1|v2)/$ /artifactory/api/repositories/$1 last;
    rewrite ^/([^/]+:[^/]+)$ /library/$1 last;

    chunked_transfer_encoding on;
    client_max_body_size 0;
    proxy_request_buffering off;
    proxy_max_temp_file_size 0;
    proxy_http_version 1.1;
    proxy_read_timeout 2400s;
    proxy_pass_header Server;
    proxy_cookie_path ~*^/.* /;
    proxy_buffer_size 128k;
    proxy_buffers 40 128k;
    proxy_busy_buffers_size 128k;

    proxy_set_header X-JFrog-Override-Base-Url $http_x_forwarded_proto://$host;
    proxy_set_header X-Forwarded-Port $server_port;
    proxy_set_header X-Forwarded-Proto $http_x_forwarded_proto;
    proxy_set_header Host $http_host;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

    # Artifactory 微服务
    #location ~ ^/(ui|router|access|metadata|replicator|event)/ {
    #    proxy_pass http://artifact-router;
    #    }
    # xray
    #location /xray/ {
    #    proxy_pass http://artifact-router;
    #    }
    # distribution
    location /distribution/ {
        proxy_pass http://artifact-router;
        }
    # insight/mc 服务
    #location ~ ^/(mc|insight|insight-scheduler|insight-executor|elasticsearch)/ {
    #     proxy_pass http://artifact-router;
    #      }

    # Artifactory
    location /artifactory/ {
        proxy_pass http://artifact;
    }

 # Artifactory
    location / {
        proxy_set_header X-JFrog-Override-Base-Url "";
        proxy_set_header X-Artifactory-Override-Base-Url $http_x_forwarded_proto://$host;
        proxy_pass http://artifact/artifactory$request_uri;
        }
}` 
```

> 注意：由于artifactory启动比较慢，所以等启动完成后访问不了，请重启nginx

#### [](#p-4528350-license-7)license生成

登录到容器中，在容器中执行以下命令

```


`/opt/jfrog/artifactory/app/third-party/java/bin/java -jar /opt/jfrog/artifactory/var/ArtifactoryKeygen-1.0-SNAPSHOT-all.jar genkey  #生成密钥对
/opt/jfrog/artifactory/app/third-party/java/bin/java -jar /opt/jfrog/artifactory/var/ArtifactoryKeygen-1.0-SNAPSHOT-all.jar gen     #生成license，根据提示生成后复制，登录到web页面，导航到Administration→General Management→Licenses进行注册` 
```

#### [](#p-4528350-artifactory-8)artifactory使用

按我个人来讲，我只把它当作我的私人仓库和仓库代理使用，所以不涉及devops相关内容，请自行找相关教程。

基本流程：创建local类型仓库，起名为`local-a`，使得能够部署本地开发的包到该仓库，如果有代理仓库需求，创建remote类型仓库，起名为`remote-a`，最后再创建virtual类型的仓库，起名为`a`，并将virtual类型的仓库的`Repositories`中包含`remote-a`，将`Default Deployment Repository`设置为创建的`local-a`，完成这些操作后，你就有了一个包含本地和远程混合包的仓库`a`，他的地址一般为`https://reg.example.com/artifactory/a/`(使用本教程nginx反代则为`https://reg.example.com/a/`)，后续部署本地的包到该仓库，会自动将部署的包放到`local-a`中，而日常使用缓存的包会在`remote-a-cache`(该仓库用来缓存本地请求的远程数据)仓库中，如果本地有请求到相同数据则会直接使用缓存的数据。

需要密钥的相关仓库，比如debian、alpine等，得先导航到`Administration`→`Security`→`Keys Management`→`Signing Keys`上传签名密钥对，然后在创建相关`virtual`仓库时选择对应的key。

  

6

​ ​ 回复

*   [自用All In Boom各种服务部署分享](https://linux.do/t/topic/478651)
    

67 浏览量

[![](https://linux.do/user_avatar/linux.do/handsome/96/477777_2.png)
](/u/handsome)

[大帅哥](/u/handsome)

[handsome](/u/handsome)种子用户 ![](https://linux.do/images/emoji/twemoji/rage.png?v=14) 

[3 天](/t/topic/490791/2?u=niyan2025 "发布日期")

感谢大佬！

  

​ ​ 回复

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
| [cursor 体验脚本](/t/topic/359608/500)

 [73](/t/topic/359608/500 "您在此话题中有 73 个未读帖子")

[开发调优, Lv1](/c/develop/develop-lv1/20)

[人工智能](/tag/人工智能)

,[精华神帖](/tag/精华神帖)





 | [561](/t/topic/359608/1) | 16.3k | [3 小时](/t/topic/359608/572) |
| [Cursor Pool 更新说明](/t/topic/435717/42)

 [174](/t/topic/435717/42 "您在此话题中有 174 个未读帖子")

[开发调优, Lv1](/c/develop/develop-lv1/20)

[人工智能](/tag/人工智能)

,[Cursor](/tag/cursor)





 | [212](/t/topic/435717/1) | 8.2k | [14 小时](/t/topic/435717/215) |
| [送给佬友的新年礼物：Cursor 0.45.x 全网最新限制解除方案（macOS、Windows、Linux）](/t/topic/404221/150)

 [42](/t/topic/404221/150 "您在此话题中有 42 个未读帖子")

[开发调优, Lv1](/c/develop/develop-lv1/20)

[人工智能](/tag/人工智能)

,[Cursor](/tag/cursor)





 | [188](/t/topic/404221/1) | 5.8k | [1 天](/t/topic/404221/191) |
| [【原创】我是如何请黑客老哥吃上了牢饭](/t/topic/387565/34)

 [287](/t/topic/387565/34 "您在此话题中有 287 个未读帖子")

[开发调优, Lv1](/c/develop/develop-lv1/20)

[网络安全](/tag/网络安全)

,[精华神帖](/tag/精华神帖)





 | [318](/t/topic/387565/1) | 6.7k | [3 天](/t/topic/387565/320) |
| [无脑套AWS CloudFront教程：让你的网站速度飞起来](/t/topic/399977/11)

 [25](/t/topic/399977/11 "您在此话题中有 25 个未读帖子")

[开发调优, Lv1](/c/develop/develop-lv1/20)

[配置优化](/tag/配置优化)





 | [33](/t/topic/399977/1) | 758 | [17 天](/t/topic/399977/35) |

### 有 [25 个未读](/unread)

话题 和 [144 个新](/new)

话题， 或浏览[开发调优, Lv1](/c/develop/develop-lv1/20)

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

VertiTab

↑↓⇔⇧⇩