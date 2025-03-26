# iframe 跨域之间共享localStorage,sessionStorage_iframe localstorage-CSDN博客
[iframe 跨域之间共享localStorage,sessionStorage_iframe localstorage-CSDN博客](https://blog.csdn.net/m0_65730686/article/details/126667136) 

              iframe 跨域之间共享localStorage,sessionStorage\_iframe localstorage-CSDN博客        

[![](https://img-home.csdnimg.cn/images/20201124032511.png)
](https://www.csdn.net/)

*   [博客](https://blog.csdn.net/)
*   [下载](https://download.csdn.net/)
*   [学习](https://edu.csdn.net?utm_source=zhuzhantoolbar)
*   [社区](https://devpress.csdn.net/)
*   [![](https://img-home.csdnimg.cn/images/20241022035258.png)
    C知道 ![](https://i-operation.csdnimg.cn/images/82668ada3dd441f5908f6bf63de9d02f.png)](https://so.csdn.net/chat?utm_source=vip_chatgpt_common_pc_toolbar) 
*   [![](https://img-home.csdnimg.cn/images/20240829093757.png)
    GitCode](https://link.csdn.net?target=https%3A%2F%2Fgitcode.com%3Futm_source%3Dcsdn_toolbar) 
*   [InsCodeAI](https://models.csdn.net?utm_source=260232576)
*   [会议](https://summit.csdn.net/)

搜索 

登录

[会员中心 ![](https://img-home.csdnimg.cn/images/20210918025138.gif)](https://mall.csdn.net/vip) 

[消息](https://i.csdn.net/#/msg/index)

[历史](https://i.csdn.net/#/user-center/history)

[创作中心](https://mpbeta.csdn.net "创作中心")

[![](https://img-home.csdnimg.cn/images/20230825101811.png)
](https://mp.csdn.net/edit) ![](https://img-home.csdnimg.cn/images/20230815023238.png)

[创作](https://mpbeta.csdn.net/edit)

  

iframe 跨域之间共享localStorage,sessionStorage
========================================

最新推荐文章于 2025-02-14 16:57:32 发布

![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

[老胡说前端](https://blog.csdn.net/m0_65730686 "老胡说前端") ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newCurrentTime2.png)
 于 2022-09-02 17:07:50 发布

![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes2.png)
 阅读量1w ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect2.png)
 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollectionActive2.png)
 收藏  4 

![](https://csdnimg.cn/release/blogv2/dist/pc/img/newHeart2023Active.png)
 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newHeart2023Black.png)
 点赞数 1 

分类专栏： [iframe](https://blog.csdn.net/m0_65730686/category_11994569.html) 文章标签： [javascript](https://so.csdn.net/so/search/s.do?q=javascript&t=all&o=vip&s=&l=&f=&viparticle=&from_tracking_code=tag_word&from_code=app_blog_art) [html](https://so.csdn.net/so/search/s.do?q=html&t=all&o=vip&s=&l=&f=&viparticle=&from_tracking_code=tag_word&from_code=app_blog_art)

版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

本文链接：[https://blog.csdn.net/m0\_65730686/article/details/126667136](https://blog.csdn.net/m0_65730686/article/details/126667136)

版权

 [![](https://devpress.csdnimg.cn/489fad64a62648818eaaebc28e5c8659.jpg)
   华为开发者空间 该内容已被华为云开发者联盟社区收录](javascript:; "华为开发者空间") 

加入社区

 [![](https://i-blog.csdnimg.cn/columns/default/20201014180756916.png?x-oss-process=image/resize,m_fixed,h_224,w_224)
   iframe 专栏收录该内容](https://blog.csdn.net/m0_65730686/category_11994569.html "iframe") 

1 篇文章

订阅专栏

 

如：aaa.com 中读取bbb.com的localStorage

9-1 实现原理:

1-1.在aaa.com的页面中，在页面中嵌入一个src为bbb.com的[iframe](https://so.csdn.net/so/search?q=iframe&spm=1001.2101.3001.7020)，此时这个iframe里可以调用bbb.com的localStorage。

1-2.用[postMessage](https://so.csdn.net/so/search?q=postMessage&spm=1001.2101.3001.7020)方法实现页面与iframe之间的通信。

综合1、2便可以实现aaa.com中调用bbb.com的localStorage

9-2优化iframe:

2-1我们可以在bbb.com中写一个专门负责共享localStorage的页面，例如叫做page1.html，这样可以防止无用的资源加载到iframe中。

9-3 示例:

3-1 以在aaa.com中读取bbb.com中的localStorage的item1为例，写同理：

bbb.com中page1.html，监听aaa.com通过postMessage传来的信息，读取localStorage，然后再使用postMessage方法传给aaa.com的接收者。

<!DOCTYPE html>

<html lang="en-US">

<head>

<script type="text/javascript">

window.addEventListener('message', function(event) {

if (event.origin === 'https://aaa.com') {

const { key } = event.data;

const value = localStorage.getItem(key);

event.source.postMessage({wallets: wallets}, event.origin);

}

}, false);

</script>

</head>

<body>

This page is for sharing localstorage.

</body>

</html>

3-2 在aaa.com的页面中加入一个src为bbb.com/page1.html隐藏的iframe。

<iframe id="bbb-iframe" src="https://bbb.com/page1.html" style="display:none;"></iframe>

3-3 在aaa.com的页面中加入下面script标签。在页面加载完毕时通过postMessage告诉iframe中监听者，读取item1。监听bbb.com传回的item1的值并输出。

<script type="text/javascript">

window.onload = function() {

const bbbIframe = document.getElementById('bbb-iframe');

bbbIframe.contentWindow.postMessage({key: 'item1'}, 'https://bbb.com');

}

window.addEventListener('message', function(event) {

if (event.origin === 'https://bbb.com') {

console.log(event.data);

}

}, false);

</script>

![](https://csdnimg.cn/release/blogv2/dist/pc/img/vip-limited-close-newWhite.png)

确定要放弃本次机会？

福利倒计时

_:_ _:_

![](https://csdnimg.cn/release/blogv2/dist/pc/img/vip-limited-close-roup.png)
 立减 ¥ 

普通VIP年卡可用

[立即使用](https://mall.csdn.net/vip)

 [![](https://profile-avatar.csdnimg.cn/8fbd2df72ed24a5fa0c7e57f08d3daf6_m0_65730686.jpg!1)
  老胡说前端](https://blog.csdn.net/m0_65730686) 

[关注](javascript:;) 关注

*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarThumbUpactive.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/like-active.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/like.png)
      1 
    
    点赞
    
*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/unlike-active.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/unlike.png) 
    
    踩
    
*    [![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/collect-active.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/collect.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newCollectActive.png)
      4](javascript:;) 
    
    收藏
    
    觉得还不错? 一键收藏 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/collectionCloseWhite.png)
    
*    [![](https://csdnimg.cn/release/blogv2/dist/pc/img/toolbar/comment.png)
      1](#commentBox) 
    
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

![](https://kunyu.csdn.net/1.png?p=58&adBlockFlag=0&adId=1066861&a=1066861&c=2535449&k=iframe 跨域之间共享localStorage,sessionStorage&spm=1001.2101.3001.5002&articleId=126667136&d=1&t=3&u=eff7175aaaad4bbf8a1e2b044e807778)

[

_iframe_\-_localstorage_

](https://download.csdn.net/download/weixin_42127775/19513670)

06-09

[

_iframe_\-_localStorage_ 实际上不可能从嵌套在不同域中的 _iframe_ 元素中的页面使用功能（考虑到父框架域）。 为了解决这个限制，我编写了这个简单的库，它使用功能也可以在_跨域_框架中使用 _localStorage_。 为了使用它，在父窗口中包含 parent.js 文件和在嵌套窗口中包含 _iframe_.js 文件就足够了。 _iframe_.js 文件覆盖 localtStorage setItem 、 getItem和removeItem方法，并提供延迟接口等待结果。 代码示例 在嵌套页面中包含 _iframe_.js 后，您可以将 _localStorage_ 方法与经典接口一起使用。 _localStorage_ . setItem ( 'test' , 5 ) ; _localStorage_ . getItem ( 'test' ) . done ( function

](https://download.csdn.net/download/weixin_42127775/19513670)

1 条评论 您还未登录，请先 登录 后发表或查看评论

[

_iframe_嵌套网站,不让网站使用_localstorage_等存数据\__iframe_ sandbox可以...

](https://blog.csdn.net/weixin_43817709/article/details/109625747)

3-2

[

本文介绍了如何在_iframe_中嵌套网站并阻止其使用_localStorage_等存储数据的方法。通过设置_iframe_的sandbox属性,可以对嵌入的内容施加额外的限制。例如,\`sandbox="allow-scripts"\` 允许运行_JavaScript_但阻止数据存储。详细讨论了sandbox属性的不同配置选项。 摘要由CSDN通过智能技术生成 ...

](https://blog.csdn.net/weixin_43817709/article/details/109625747)

[

_iframe__跨域_问题解决办法\__iframe_ contentwindow _跨域_

](https://blog.csdn.net/a250758092/article/details/84026235)

3-15

[

注意,这种方法只适用于 Cookie 和_iframe_窗口,_LocalStorage_ 和 IndexDB 无法通过这种方法,规避同源政策,而要使用下文介绍的PostMessage API。 另外,服务器也可以在设置Cookie的时候,指定Cookie的所属域名为一级域名,比如.example.com。 Set-Cookie: key=value;domain=.example.com; path=/ ...

](https://blog.csdn.net/a250758092/article/details/84026235)

[

_iframe_嵌套在不同源的页面，储存的_localstorage_无法_共享_到与_iframe_同源的网页中

](https://blog.csdn.net/fooopppcccvvv/article/details/144689451)

[fooopppcccvvv的博客](https://blog.csdn.net/fooopppcccvvv)

12-24 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1003 

[

先生成一个不可见的_iframe_层，然后再_iframe_中设置_localstorage_，但是打开_iframe_的同源页面时，我发_共享_到_localstorage_，这个怎么解决？// 如果页面url包含消息发送的origin。

](https://blog.csdn.net/fooopppcccvvv/article/details/144689451)

[

_iframe_嵌入_localstorage_数据不_共享_解决方案

最新发布

](https://blog.csdn.net/qq_35556763/article/details/145636881)

[qq\_35556763的博客](https://blog.csdn.net/qq_35556763)

02-14 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 290 

[

_iframe_嵌入_localstorage_数据不_共享_解决方案

](https://blog.csdn.net/qq_35556763/article/details/145636881)

[

_跨域_:利用_iframe_实现_跨域_DOM互访的四种方式\__iframe_ _跨域_

](https://blog.csdn.net/qq_68163788/article/details/134341594)

3-26

[

使用postmessage读取其他窗口的_localstorage_(普通款) 使用postmessage读取其他窗口的_localstorage_(加强版本): 实验验证环境配置: 我们一共需要配置五个虚拟主机,即需要使用五个域名 www.aaa.com、www.bbb.com、master.security.com、slave.security.com、www.security.com ...

](https://blog.csdn.net/qq_68163788/article/details/134341594)

[

前端基础(三十八):_iframe_通信、浏览器跨窗口通信\_前端_iframe_通信-CSDN...

](https://blog.csdn.net/weixin_43526371/article/details/135748516)

3-24

[

<labelfor="input"><span>本地存储实现 - _localStorage_:</span><inputid="input"type="text"oninput="handleInput(this.value)"/></label><script>constinput=document.getElementById('input');// 初始化表单数据input.value=_localStorage_.getItem('value')||'';// 监听表单输入(保存通信数据到本地存储中...

](https://blog.csdn.net/weixin_43526371/article/details/135748516)

[

_iframe_ 页面中获取父级页面的 _localStorage_ 或者 _sessionStorage_数据

](https://blog.csdn.net/jiangjunyuan168/article/details/135816042)

[jiangjunyuan168的博客](https://blog.csdn.net/jiangjunyuan168)

01-24 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 5821 

[

在开发的过程中遇到需要在 _iframe_ 页面中获取父级页面系统所存储的本地数据的需求。由于浏览器的安全策略，是不允许 _iframe_ 页面直接获取系统的存储数据的，那么要如何解决呢？

](https://blog.csdn.net/jiangjunyuan168/article/details/135816042)

[

cookie和_localstorage_在_iframe_中的应用

](https://blog.csdn.net/u010895423/article/details/129185795)

[u010895423的博客](https://blog.csdn.net/u010895423)

02-23 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 4614 

[

cookie和_localstorage_在_iframe_中的应用

](https://blog.csdn.net/u010895423/article/details/129185795)

[

简单通过_iframe_+postMessage+_localstorage_实现_跨域_通信存储

](https://blog.csdn.net/sassssiii/article/details/129809876)

[sassssiii的博客](https://blog.csdn.net/sassssiii)

03-28 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1446 

[

通过以上的代码我们就可以在我们新打开页面中的_localStorage_中查看到我们需要的token。这个方式我们可以实现我们在工作上出现的单点登录的问题，或者_跨域_传递信息的解决方案。下面的这个是http://localhost:8080里面的代码。下面的这个是http://localhost:8081里面的代码。在vue中也可以使用以上的方法进行实现。

](https://blog.csdn.net/sassssiii/article/details/129809876)

[

面试宝典之前端技术

](https://blog.csdn.net/weixin_59196705/article/details/124542851)

[weixin\_59196705的博客](https://blog.csdn.net/weixin_59196705)

05-02 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1006 

[

1\. 标签上 title 与 alt 属性的区别是什么？ alt 是给搜索引擎识别，在图像无法显示时的替代文本； title 是关于元素的注释信息，主要是给用户解读。当鼠标放到文字或是图 片上时有 title 文字显示。（因为 IE 不标准）在 IE 浏览器中 alt 起到了 title 的作用，变成文字提示。在定义 img 对象时，将 alt 和 title 属性写全，可以保证在各种浏览器中都能正常使用。&和&&的区别。 2. DIV+CSS 布局较 table 有什么优势？

](https://blog.csdn.net/weixin_59196705/article/details/124542851)

[

js 实现_iframe_ _之间_传值

](https://download.csdn.net/download/zslqy051/5741267)

07-12

[

然而，由于\`_iframe_\`本质上是独立的窗口，因此在不同\`_iframe_\`_之间_传递数据可能会遇到_跨域_问题。本篇文章将详细介绍如何使用_JavaScript_来实现在\`_iframe_\`_之间_传递值。 1. 同源策略与_跨域_限制： _JavaScript_遵循同源...

](https://download.csdn.net/download/zslqy051/5741267)

[

页面中_iframe_相互传值传参

](https://download.csdn.net/download/weixin_38741075/13071497)

10-29

[

例如，可以使用storage事件，当一方修改了_localStorage_或_sessionStorage_时，另一方可以通过监听storage事件来获得通知并进行响应。这种方法不需要直接调用对方的函数，而是通过事件驱动的方式实现间接通信。 总结来...

](https://download.csdn.net/download/weixin_38741075/13071497)

[

Laya和_iframe_通信.zip

](https://download.csdn.net/download/ju__ju/47383154)

11-23

[

除此之外，还可以利用URL查询参数、存储机制（如_localStorage_或_sessionStorage_）以及自定义的事件机制（如轮询检查或WebSocket）来实现在Laya和_iframe_间的通信。不过需要注意的是，这些方法都受限于浏览器的安全策略...

](https://download.csdn.net/download/ju__ju/47383154)

[

safari,opera嵌入_iframe_页面cookie读取问题解决方法

](https://download.csdn.net/download/weixin_38626179/12818199)

09-05

[

在现代网络开发中，_跨域_通信和数据_共享_是常见的需求，而\`_iframe_\`元素常用于实现这样的功能。然而，由于浏览器的安全策略，特别是对于第三方cookie的处理，开发者可能会遇到在特定浏览器如Safari、Opera以及某些使用...

](https://download.csdn.net/download/weixin_38626179/12818199)

[

_iframe_ _跨域_访问session

](https://download.csdn.net/download/fdipzone/8402515)

01-28

[

_iframe_ _跨域_访问session问题解决方法

](https://download.csdn.net/download/fdipzone/8402515)

[

_iframe_ 子父界面 传值.zip

](https://download.csdn.net/download/Sensation_cyq/15448761)

02-24

[

\`postMessage\` API 是现代浏览器支持的一种安全的_跨域_通信方式，\`_iframe_\`与父页面_之间_可以通过这个API传递消息。发送方使用\`postMessage\`方法发送消息，接收方监听\`message\`事件接收消息。 \*\*子页面发送消息：\*\* \`...

](https://download.csdn.net/download/Sensation_cyq/15448761)

[

_iframe_页面Storage数据_共享_

](https://blog.csdn.net/forgiveForever/article/details/143400580)

[forgiveForever的博客](https://blog.csdn.net/forgiveForever)

10-31 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 854 

[

同一个浏览器窗口下，多个_iframe_页面，同域下，Storage 是_共享_（即 _sessionStorage_ 和 _localStorage_）,_iframe_ 页面相互影响。最近开发使用了_iframe_做跨系统，跨页面交互,当前页面存在多个_iframe_页面，并且每个_iframe_链接，同域。有些_iframe_ 页面会有报错提示。使用 http-server 启动 端口 3201。_iframe_（vue页面）具体加载逻辑，

](https://blog.csdn.net/forgiveForever/article/details/143400580)

[

_iframe_与宿主页面的通信问题

](https://blog.csdn.net/ChangerJJLee/article/details/103833413)

[JaysenLeo](https://blog.csdn.net/ChangerJJLee)

01-04 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1192 

[

1\. 利用 _sessionStorage_ 进行相对安全的通信（_localStorage_） 保存数据语法： _sessionStorage_.setItem("key", "value"); 读取数据语法： var lastname = _sessionStorage_.getItem("key"); 删除指定键的数据语法： _sessionStorage_.removeItem("key");...

](https://blog.csdn.net/ChangerJJLee/article/details/103833413)

[

ifame_共享_session的解决方法

](https://blog.csdn.net/ykdsg/article/details/2797817)

[ykdsg的专栏](https://blog.csdn.net/ykdsg)

08-19 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 5601 

[

       在开发中碰到的问题，同事做的一个页面中的_iframe_要调到我这边地址，并且url后附着验证码，而我验证时要取得他session中的登陆信息。结果是_iframe_对第一个action可以相应，但我的页面包含的另外的_iframe_中的action却调不到session中的值。发现是调不到最外面那个页面的session        解决方案，在第一次相应的action中加一个header

](https://blog.csdn.net/ykdsg/article/details/2797817)

[

前端内嵌_iframe_网页单点登录的三种方式

](https://qianduoduo.blog.csdn.net/article/details/138734342)

[大雾起了清晨](https://blog.csdn.net/qq_59747594)

05-12 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 3975 

[

方法一：_共享__sessionStorage_或_localStorage_方法二：设置内嵌_iframe_的url参数方法三：通过父子页面通信postMessage扩展：同源网页

](https://qianduoduo.blog.csdn.net/article/details/138734342)

[

_iframe_获取父页面数据

](https://blog.csdn.net/zltAlma/article/details/91489304)

[zlt的博客](https://blog.csdn.net/zltAlma)

06-12 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 3295 

[

frame\_FSUPLD为_iframe_的ID sendContent1为_iframe_子页面的元素ID。 js: parent.document.getElementById(“frame\_FSUPLD”).contentWindow.document.getElementById(“sendContent1”).inner_HTML_; jquery: $(window.parent.document...

](https://blog.csdn.net/zltAlma/article/details/91489304)

[

h5离线存储的原理，怎么使用；cookie，_sessionstorage_，_localstorage_的区别、_Iframe_的缺点

](https://blog.csdn.net/JEFF_luyiduan/article/details/104854384)

[JEFF\_xieyuzhi的博客](https://blog.csdn.net/JEFF_luyiduan)

03-14 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1208 

[

文章目录h5离线存储的原理，怎么使用cookie，_sessionstorage_，_localstorage_的区别_Iframe_ h5离线存储的原理，怎么使用 个人总结： 原理：h5的离线存储是基于一个.appcache文件来缓存的，它不是存储技术，我们通过.appcache这个文件来解析离线存储资源，这些资源会被浏览器存储起来，当你电脑没有网的时候，浏览器回通过你存储起来的数据对页面进行展示。 使用：...

](https://blog.csdn.net/JEFF_luyiduan/article/details/104854384)

[

_localStorage_和_sessionStorage_的_跨域_

](https://wenku.csdn.net/answer/3t0ooy8107)

09-21

[

_localStorage_和_sessionStorage_都是在浏览器端进行数据存储的机制。它们的主要区别在于作用域和生命周期。_localStorage_的作用域是在整个浏览器中，而_sessionStorage_的作用域是在当前会话（session）中。_localStorage_的生命周期是永久的，即除非用户主动清除_localStorage_信息，否则数据将一直存在。而_sessionStorage_的生命周期是在当前会话中，一旦会话结束或浏览器关闭，数据将被清除。 关于_跨域_问题，_localStorage_和_sessionStorage_的_跨域_策略是相同的。它们遵循同源策略，即只能在同一个域名下_共享_数据。如果不同域名_之间_需要_共享_数据，可以使用以下方法之一： . 使用_iframe_标签嵌入同一个域名下的页面，并通过postMessage()方法进行_跨域_通信。 2. 使用_跨域_资源_共享_（CORS）机制，在服务器端设置Access-Control-Allow-Origin头部来允许_跨域_访问。 3. 在服务器端设置代理，通过服务器端来获取数据并转发给前端页面。

](https://wenku.csdn.net/answer/3t0ooy8107)

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

 [![](https://profile-avatar.csdnimg.cn/8fbd2df72ed24a5fa0c7e57f08d3daf6_m0_65730686.jpg!1)](https://blog.csdn.net/m0_65730686) 

[老胡说前端](https://blog.csdn.net/m0_65730686 "老胡说前端")

博客等级 ![](https://csdnimg.cn/identity/blog5.png)

码龄3年

[

299

原创

](https://blog.csdn.net/m0_65730686)

631

点赞

621

收藏

674

粉丝

关注

[私信](https://im.csdn.net/chat/m0_65730686)

 [![](https://i-operation.csdnimg.cn/images/2dd892a9769b4cce9c086db94eab887f.png)](https://ai.csdn.net/) 

![](https://kunyu.csdn.net/1.png?p=56&adId=1066629&adBlockFlag=0&a=1066629&c=0&k=iframe 跨域之间共享localStorage,sessionStorage&spm=1001.2101.3001.5000&articleId=126667136&d=1&t=3&u=e71f6b3f3f78437d953b412cd82c4651)

### 热门文章

*   [iframe 跨域之间共享localStorage,sessionStorage ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     10711](https://blog.csdn.net/m0_65730686/article/details/126667136) 
*   [vue3 h 函数 添加style,class,click等等 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     5236](https://blog.csdn.net/m0_65730686/article/details/130972947) 
*   [uniapp中 onReady, onLoad, onShow区别 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     5134](https://blog.csdn.net/m0_65730686/article/details/128382436) 
*   [css 绘制 上，下，右，左箭头 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     4310](https://blog.csdn.net/m0_65730686/article/details/126727162) 
*   [vue2 中this.$emit(“update:xx“,value)和xx.sync的用法 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     4291](https://blog.csdn.net/m0_65730686/article/details/127809215) 

### 分类专栏

*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756923.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      vue3](https://blog.csdn.net/m0_65730686/category_12001220.html) 22篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756926.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      vue](https://blog.csdn.net/m0_65730686/category_11904630.html) 64篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756918.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      css](https://blog.csdn.net/m0_65730686/category_11964610.html) 9篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756724.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      js](https://blog.csdn.net/m0_65730686/category_11906127.html) 67篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756738.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      javascript](https://blog.csdn.net/m0_65730686/category_11906126.html) 33篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756738.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      es6](https://blog.csdn.net/m0_65730686/category_11917742.html) 29篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756757.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      elementUI](https://blog.csdn.net/m0_65730686/category_11979516.html) 3篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756930.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      html5](https://blog.csdn.net/m0_65730686/category_11999491.html) 6篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756922.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      jeecgBoot](https://blog.csdn.net/m0_65730686/category_12098048.html) 4篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756724.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      vue面试](https://blog.csdn.net/m0_65730686/category_12295199.html) 4篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756916.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      兼容性](https://blog.csdn.net/m0_65730686/category_11924313.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756780.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      html](https://blog.csdn.net/m0_65730686/category_11983467.html) 12篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756923.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      uni-app](https://blog.csdn.net/m0_65730686/category_11985268.html) 17篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756757.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      微信小程序](https://blog.csdn.net/m0_65730686/category_11967164.html) 9篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756916.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      nvm](https://blog.csdn.net/m0_65730686/category_12015401.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756913.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      node](https://blog.csdn.net/m0_65730686/category_12015402.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756916.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      map](https://blog.csdn.net/m0_65730686/category_12010569.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756930.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      mock](https://blog.csdn.net/m0_65730686/category_12009267.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756923.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      bootstrap](https://blog.csdn.net/m0_65730686/category_11997812.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756916.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      iframe](https://blog.csdn.net/m0_65730686/category_11994569.html) 1篇

![](https://csdnimg.cn/release/blogv2/dist/pc/img/arrowDownWhite.png)

### 最新评论

*   [ant design vue动态循环生成表单以及自定义校验规则](https://blog.csdn.net/m0_65730686/article/details/142211814#comments_34652480)
    
    [CSDN-Ada助手:](https://blog.csdn.net/community_717) 不知道 Vue入门 技能树是否可以帮到你：https://edu.csdn.net/skill/vue?utm\_source=AI\_act\_vue
    
*   [vue3 elementPlus 设置树形报错时 setCheckedKeys of undefined](https://blog.csdn.net/m0_65730686/article/details/136873901#comments_31999382)
    
    [CSDN-Ada助手:](https://blog.csdn.net/community_717) Vue入门 技能树或许可以帮到你：https://edu.csdn.net/skill/vue?utm\_source=AI\_act\_vue
    
*   [vue2 element-ui select下拉框 选择传递多个参数](https://blog.csdn.net/m0_65730686/article/details/134811398#comments_30685437)
    
    [CSDN-Ada助手:](https://blog.csdn.net/community_717) Vue入门 技能树或许可以帮到你：https://edu.csdn.net/skill/vue?utm\_source=AI\_act\_vue
    
*   [iframe 跨域之间共享localStorage,sessionStorage](https://blog.csdn.net/m0_65730686/article/details/126667136#comments_29272543)
    
    [孙可爱.:](https://blog.csdn.net/weixin_44383533) 你好 浏览器更新了117版本后 b页面取不到local了
    
*   [uniapp APP首次下载启动时，获取各种权限，应用市场审核不通过情况](https://blog.csdn.net/m0_65730686/article/details/127072687#comments_28114812)
    
    [老胡说前端:](https://blog.csdn.net/m0_65730686) 看看api 是否有改动
    

### 大家在看

*   [企业本地 AI 解决方案：全面分析 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     284](https://blog.csdn.net/m0_50657013/article/details/146452794) 
*   [解析可视化大屏 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     573](https://blog.csdn.net/T_iAn_T/article/details/146450987) 
*   [深度学习查漏补缺：3.从 Sigmoid 到 GELU](https://blog.csdn.net/qq_53529450/article/details/146519209)
*   [2025年毕设ssm小区垃圾回收信息管理系统论文+源码 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     722](https://blog.csdn.net/sheji1071/article/details/146162192) 
*   [Ubuntu 22 Linux上部署DeepSeek R1保姆式操作详解（ollama方式） ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     683](https://blog.csdn.net/daobaqin/article/details/146504677) 

### 最新文章

*   [css white-space: pre-line； 用处大](https://blog.csdn.net/m0_65730686/article/details/146443729)
*   [vue2 Vue.set||this.$set 不起作用使用强制更新](https://blog.csdn.net/m0_65730686/article/details/146443677)
*   [vue2 清空 elemnetUi 表单校验内容 resetFields](https://blog.csdn.net/m0_65730686/article/details/146283153)

[2025年6篇](https://blog.csdn.net/m0_65730686?type=blog&year=2025&month=03)

[2024年70篇](https://blog.csdn.net/m0_65730686?type=blog&year=2024&month=11)

[2023年77篇](https://blog.csdn.net/m0_65730686?type=blog&year=2023&month=12)

[2022年150篇](https://blog.csdn.net/m0_65730686?type=blog&year=2022&month=12)

![](https://kunyu.csdn.net/1.png?p=57&adBlockFlag=0&adId=1066902&a=1066902&c=2540695&k=iframe 跨域之间共享localStorage,sessionStorage&spm=1001.2101.3001.5001&articleId=126667136&d=1&t=3&u=e5eb937dd0da4d4e939b215c2e97ed0d)

![](https://kunyu.csdn.net/1.png?p=530&adBlockFlag=0&adId=1066860&a=1066860&c=2535048&k=iframe 跨域之间共享localStorage,sessionStorage&spm=1001.2101.3001.4647&articleId=126667136&d=1&t=3&u=05c78d8b24b6441699d6923aa401cc9b)

![](https://kunyu.csdn.net/1.png?p=479&adId=1049278&adBlockFlag=0&a=1049278&c=0&k=iframe 跨域之间共享localStorage,sessionStorage&spm=1001.2101.3001.4834&articleId=126667136&d=1&t=3&u=03e580e1bbd5499d9bfe8d9d896bd51c)

### 分类专栏

*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756923.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      vue3](https://blog.csdn.net/m0_65730686/category_12001220.html) 22篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756926.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      vue](https://blog.csdn.net/m0_65730686/category_11904630.html) 64篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756918.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      css](https://blog.csdn.net/m0_65730686/category_11964610.html) 9篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756724.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      js](https://blog.csdn.net/m0_65730686/category_11906127.html) 67篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756738.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      javascript](https://blog.csdn.net/m0_65730686/category_11906126.html) 33篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756738.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      es6](https://blog.csdn.net/m0_65730686/category_11917742.html) 29篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756757.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      elementUI](https://blog.csdn.net/m0_65730686/category_11979516.html) 3篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756930.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      html5](https://blog.csdn.net/m0_65730686/category_11999491.html) 6篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756922.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      jeecgBoot](https://blog.csdn.net/m0_65730686/category_12098048.html) 4篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756724.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      vue面试](https://blog.csdn.net/m0_65730686/category_12295199.html) 4篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756916.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      兼容性](https://blog.csdn.net/m0_65730686/category_11924313.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756780.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      html](https://blog.csdn.net/m0_65730686/category_11983467.html) 12篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756923.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      uni-app](https://blog.csdn.net/m0_65730686/category_11985268.html) 17篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756757.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      微信小程序](https://blog.csdn.net/m0_65730686/category_11967164.html) 9篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756916.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      nvm](https://blog.csdn.net/m0_65730686/category_12015401.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756913.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      node](https://blog.csdn.net/m0_65730686/category_12015402.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756916.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      map](https://blog.csdn.net/m0_65730686/category_12010569.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756930.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      mock](https://blog.csdn.net/m0_65730686/category_12009267.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756923.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      bootstrap](https://blog.csdn.net/m0_65730686/category_11997812.html) 1篇
*    [![](https://i-blog.csdnimg.cn/columns/default/20201014180756916.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      iframe](https://blog.csdn.net/m0_65730686/category_11994569.html) 1篇

评论 1

![](https://csdnimg.cn/release/blogv2/dist/pc/img/closeBt.png)

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
DeepSeekR1满血版](https://so.csdn.net/chat?c_tab=chat&c_model=ds&utm_source=vip_chatgpt_common_blog_detail&spm=1001.2101.3001.10583)![](https://g.csdnimg.cn/side-toolbar/3.6/images/mobile.png)

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