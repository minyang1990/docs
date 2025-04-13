# 记一次处理win10的“System”进程异常高占用 - 开发调优 - LINUX DO
[记一次处理win10的“System”进程异常高占用 - 开发调优 - LINUX DO](https://linux.do/t/topic/555856) 

 不知道又抽了什么风，从昨天开始即使我的电脑什么事都不干，cpu风扇转的声音吵得很，打开一看任务管理器发现cpu占用一直在30%，我认为可能又是微软推送了什么更新补丁，于是就挂机慢慢等没太注意。直到今天我才发现，这事情怎么不太对劲阿，咋是windows内核占用这么高。怀疑是英伟达驱动又给我更新出问题了，于是ddu卸载了英伟达驱动并且重启重新安装，并没有效果。

[![](https://cdn.ldstatic.com/original/4X/6/2/8/62859b5718e9d82f65f3510950e0e38f9930d2b7.png)
](https://cdn.ldstatic.com/original/4X/6/2/8/62859b5718e9d82f65f3510950e0e38f9930d2b7.png "任务管理器")

感觉不对劲，我毕竟都重启了。于是打开process hacker查看，这占用的就是内核本身，跟dwm或者显卡驱动貌似并没有关系。看来是我错怪英伟达了。

[![](https://cdn.ldstatic.com/original/4X/9/1/5/915bd554e015b1337976d53c270ccca5845e75b4.png)
](https://cdn.ldstatic.com/original/4X/9/1/5/915bd554e015b1337976d53c270ccca5845e75b4.png "process hacker")

查看线程信息，发现不对劲阿，这个IntelCAS是那个傲腾加速卡的驱动进程，现在电脑啥也没干，傲腾和机械盘占用都是0，咋驱动一直在占用cpu。

[![](https://cdn.ldstatic.com/original/4X/d/5/9/d59956f7353dfe36db9d423bbbb34655357f0aac.png)
](https://cdn.ldstatic.com/original/4X/d/5/9/d59956f7353dfe36db9d423bbbb34655357f0aac.png "prop")

打开CAS控制面板一看，这好像也没问题，不管了，先停止缓存试试。再不行大不了就重新安装CAS。

[![](https://cdn.ldstatic.com/original/4X/4/1/0/410075e5ce2bafbaaff255d744af832bcbc1cf23.png)
](https://cdn.ldstatic.com/original/4X/4/1/0/410075e5ce2bafbaaff255d744af832bcbc1cf23.png "IntelCAS")

我去，这就莫名奇妙的解决了？重新启动缓存也没有异常cpu占用了。解决这个bug真的是不明不白的，重启还能保持的bug也太离谱了。

[![](https://cdn.ldstatic.com/original/4X/b/b/d/bbd101297581783aa518a4144366386dd14ea980.png)
](https://cdn.ldstatic.com/original/4X/b/b/d/bbd101297581783aa518a4144366386dd14ea980.png "process hacker")

毕竟英特尔都抛弃了自己的傲腾产品线了。CAS也不更新了，是2017年的远古驱动了，英特尔可能都不记得自己还开发过CAS这个东西。8年的高龄驱动放到现在的win10那bug肯定少不了。

点击停止缓存，那cpu风扇立马停转，就离谱。