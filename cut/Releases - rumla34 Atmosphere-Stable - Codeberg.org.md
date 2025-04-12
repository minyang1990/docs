# Releases - rumla34/Atmosphere-Stable - Codeberg.org
[Releases - rumla34/Atmosphere-Stable - Codeberg.org](https://codeberg.org/rumla34/Atmosphere-stable/releases) 

  Releases - rumla34/Atmosphere-Stable - Codeberg.org                   

 [![](https://design.codeberg.org/logo-kit/icon_inverted.svg)](/) 

[Explore](/explore/repos) [About](https://docs.codeberg.org/getting-started/what-is-codeberg/#what-is-codeberg-e.v.%3F) [FAQ](https://docs.codeberg.org/getting-started/faq/) [Help](https://docs.codeberg.org) [Donate](https://donate.codeberg.org)

[Register](/user/cbrgp/1GJ61ty) [Sign in](/user/login?redirect_to=%2frumla34%2fAtmosphere-stable%2freleases)

[rumla34](/rumla34)/[Atmosphere-Stable](/rumla34/Atmosphere-Stable)

Template

[](/rumla34/Atmosphere-Stable.rss)

Watch [2](/rumla34/Atmosphere-Stable/watchers)

Star [1](/rumla34/Atmosphere-Stable/stars)

Fork

You've already forked Atmosphere-Stable

[0](/rumla34/Atmosphere-Stable/forks)

[Code](/rumla34/Atmosphere-Stable) [Pull requests](/rumla34/Atmosphere-Stable/pulls) [Projects](/rumla34/Atmosphere-Stable/projects) [Releases1](/rumla34/Atmosphere-Stable/releases) [Packages](/rumla34/Atmosphere-Stable/packages) [Wiki](/rumla34/Atmosphere-Stable/wiki) [Activity](/rumla34/Atmosphere-Stable/activity)

[1 release](/rumla34/Atmosphere-Stable/releases) [4 tags](/rumla34/Atmosphere-Stable/tags)
------------------------------------------------------------------------------------------

 

[RSS feed](/rumla34/Atmosphere-Stable/releases.rss)

*   [1.8.0](/rumla34/Atmosphere-Stable/src/tag/1.8.0) [dd1f1b11da](/rumla34/Atmosphere-Stable/src/commit/dd1f1b11da7be0d71a7eee83927813bccbc46146)
    
    Compare
    
    No results found.
    
    #### [AMS1.8.0-Stable-v250408](/rumla34/Atmosphere-Stable/releases/tag/1.8.0) Stable
    
     ![](https://codeberg.org/avatars/1c7494701add2d04e601d5e304bb150a52b33a2a707606fa3756b850922ed8a5?size=40)
     [rumla34](/rumla34)  released this  | [**48** commits](/rumla34/Atmosphere-Stable/compare/1.8.0...main) to main since this release
    
    大气层1.8.0整合包系统稳定版（更新时间：2025.04.08）  
    大气层1.8.0最高支持NX-19.0.1系统。如果你一直使用我发布的包，以后的更新中没有特别的提醒，都是直接覆盖就完成大气层文件的升级。
    
    2025.04.08更新Checkpoint.nro--v3.8.2（无需重新制作前端NSP），NX-Activity-Log.nro--v1.5.5（和checkpoint一样必须以前端模式进），更新DBI同文件夹下DBI.nro.ru是俄文版DBI779。
    
    大气层整合包系统稳定版下载地址  
    原主页github.com/rumla34作废，改地址为github.com/rumla3434，另一个主页codeberg.org/rumla34不变。  
    [https://github.com/rumla3434/Atmosphere-stable/releases](https://github.com/rumla3434/Atmosphere-stable/releases)  
    [https://codeberg.org/rumla34/Atmosphere-stable/releases](https://codeberg.org/rumla34/Atmosphere-stable/releases)  
    离线升级固件下载地址  
    [https://github.com/rumla3434/NX\_Firmware/releases](https://github.com/rumla3434/NX_Firmware/releases)  
    [https://codeberg.org/rumla34/NX-Firmware/releases](https://codeberg.org/rumla34/NX-Firmware/releases)
    
    【一、初衷】  
    （1）我很早就看着大佬们的贴子去学习整合方法以及测试各种整合包，每次更换不同的大气层整合包，都是保留Nintendo、Emummc、jksv和switch/checkpoint/saves/4个目录，然后把SD卡上其它所有数据删除，再复制新的大气层文件上去，重启破解开机，所有整合包只要是出自大佬们的手，基本不会有问题，整合过程其实也是非常非常的简单。  
    （2）像大佬所讲的：整合包大气层就像搭积木一样。但是整合包里的插件和软件太多的话，会影响大气层系统的稳定运行，也确实如大佬讲的，只有大气层三件套的纯净包是最稳定的，但是还是需要一些基本的工具软件满足需求。对于第一次玩Switch破解的新手来说，只要不影响你玩破解游戏，使用金手指，备份游戏存档，查看游戏日志等基本功能，其它诸如底座转换模式插件、帧数插件、蓝牙手柄插件、模拟amiibo插件、主题插件等其实都是些中看不中用的插件，这些插件反而容易造成你在系统升级、大气层更新过程中出错，因为它们时刻占着系统资源，还要不断升级适配。  
    所以我就想着也发布一款以系统稳定为优先的大气层整合包，尤其在系统稳定和各种额外的扩展功能之间选择前者，推荐新手玩家使用。  
    如果你不想追求系统的稳定，而是想折腾各种插件和软件的老玩家，请去下载别人发布的各式各样的整合包，但是出问题请找别人，不要来问我，因为你又菜又爱作！  
    （3）大气层整合包、Switch系统离线升级固件这两样都是通用的，不区分Switch的机器型号和破解芯片，最新的大气层整合包向下兼容Switch系统。  
    硬破的直接按主机的电源键开机。  
    软破的需要先短接，然后注入根目录的payload.bin文件，注入方法有电脑端注入，手机端注入，注入器注入等多种方法，结果都是一样的，没区别。
    
    【二、整合包的特点】  
    （1）首次使用大气层整合包系统稳定版  
    之前不管你使用的是谁发布的大气层整合包，都可以随时换成我发布的大气层整合包系统稳定版，版本最新，向下兼容。  
    更换大气层整合包推荐“一键清理contents的旧插件和删主题20250228更新”，根据需要选择del-sysmodules.bat或del-atmosphere.bat文件，在windows电脑读取SD卡文件，执行一次，备份存档、金手指和游戏mod都比较方便。  
    （2）如果你一直使用我发布的包，以后的更新中没有特别的提醒，都是直接覆盖就完成大气层文件的升级。  
    但是假如你后来添加过在contents目录中存在sysmodule插件，未来大气层、SW系统升级的时候，这些插件如果不兼容会导致报错，只能在Deepsea工具箱中关闭它或删掉，除非这些插件有更新。另外更新大气层文件和升级switch系统是两件事，先更新大气层文件，再去下载最新的Switch系统离线升级包，去相册里找到Daybreak刷新的系统。  
    （3）整合包只带ultrahand的Tesla基本组件、超频插件和金手指插件，基本够用，也不妨碍大家额外去添加。  
    2024.10.03更换成ultrahand的Tesla，占内存少，功能丰富，使用方便。而且是同名文件替换，所以继续可以覆盖升级。  
    Tesla修改为L+Ddown开启，但tesla都是默认不启动，这样确保系统非常稳定。所以各位想用Tesla的，可以在第一次的时候进相册的deepsea toolbox中打开background service，把Tesla的OFF变成ON，然后按B键返回上一层，再按home键保存退出后就可生效。其它插件也是同样方法启动，但是其它插件的生效需要重启一次主机。  
    （4）其实极限超频EOS和普通超频sys-clk主要区别是loader.kip，等于解锁系统限制的硬件频率。所以极限超频EOS只要改动下面两个地方，就变成普通超频。1.删除atmosphere/kips/loader.kip。2.修改bootloader/hekate\_ipl.ini，删除里面的“kip1=atmosphere/kips/loader.kip”字段。  
    从2024.10.19更新开始，朗姆把EOS同名替换了sys-clk，只需要覆盖就可以启动EOS极限超频的设置，如果是续航和OLED的才建议覆盖启动，非续航和Lite就不要覆盖了。  
    极限超频：最大值CPU=1963Mhz，GPU=1228Mhz，Memory=1996Mhz  
    普通超频：最大值CPU=1785Mhz，GPU=921Mhz，Memory=1600Mhz  
    非续航和Lite的GPU不要超768Mhz，一般建议GPU=614Mhz。  
    续航和OLED，CPU=1785Mhz，GPU=921Mhz，Memory=1996Mhz，但也不要长时间极限超频。  
    （5）启动联网保护措施，虚拟系统也可以联网，可以使用wiliwili看B站视频，强烈建议新手新建一个虚拟系统，所有破解游戏都装在虚拟系统里。虚拟系统的联网保护措施绝对不能解除，除非你打算主动的BAN机。  
    真实系统如果不装破解游戏的话是可以解除联网保护，可以边用金手指或超频等插件边联机，也有被BAN的风险，建议进真实正版系统在没有插件的情况下玩联机正版游戏。真实系统解除联网保护的方法是：编辑根目录文件exosphere.ini，修改为blank\_prodinfo\_sysmmc=0保存退出，之后可以删除atmosphere/hosts/sysmmc.txt文件，重启主机生效。  
    （6）SD卡根目录有SxGear的BOOT.DAT和Hekate改名的PAYLOAD.BIN，所以不管软破硬破还是OLED，原装还是国产芯片，TX注入器还是大气层注入器，开机都进Hekate主页。默认Hekate汉化组件，如需还原英文版Hekate，可在Bootloader/sys/删汉化的nyx.bin，把nyx.bin.en重命名nyx.bin后重启开机。  
    （7）整合包里的NRO软件按路径存放，只保留基本的软件，列表在下面。  
    金手指工具是Edizon，有相册里的edizon.nro和Tesla的edizon两个，连电视的时候建议进相册的edizon  
    存档备份工具有三个：JKSV、Checkpoint和DBI，JKSV的备份功能最好用，Checkpoint需要前端才能正常使用。  
    游戏安装工具有三个：Awoo-installer、DBI、Tinfoil，DBI最好用，电脑有ns-usbloader端，awoo安装速度最快，Tinfoil也有DBI一样的功能。  
    玩某些破解游戏需要关联任天堂账号，虚拟系统只会设1个本机账号，请用linkalho关联一次，需要重启主机。  
    国行机的虚拟系统，建议使用Tencent-switcher-GUI对其转换成国际系统，这样玩破解游戏不太会出问题，但用在国行的正版系统是有BAN机的风险。  
    （8）根目录有支持FW-19.0.0后的万能前端hbmenu.nsp，建议只用在虚拟系统安装它，可以删除旧的重新安装，安装后可运行NRO软件不出现APPLE提示，Checkpoint也可以正常使用，包括wiliwili.nro，tinfoil.nro等。
    
    【三、开机启动设置】  
    点击launch（启动）  
    CFW-SYSNAND：真实破解系统，Hekate的FSS0引导，可以正版修改，新手不推荐进真实破解系统。  
    CFW-EMUNAND：虚拟破解系统，Hekate的FSS0引导，可以破解游戏，平时新手进这个系统（强烈推荐）  
    OFW-SYSNAND：真实正版系统，Hekate的FSS0引导，可以正版联机，新手可进这里玩正版游戏。  
    点击more configs（更多设置）  
    Atmosphere：大气层原版Fusee引导，根据emummc.ini自动识别真实和虚拟系统  
    Lakka-l4t：是新的lakka模拟器，兼容mariko/oled，目前新lakka只能支持fat32格式的sd卡  
    ubuntu-l4t：是新的ubuntu系统，兼容mariko/oled，目前新ubuntu只能支持fat32格式的sd卡  
    点击payloads（有效载荷）  
    commonproblemresolver.bin：主机启动修复软件，可一键关闭所有contents启动插件和删除主题  
    Lockpick\_RCM.bin：主机Keys提取软件  
    TegraExplorer.bin：主机文件管理软件  
    fusee.bin：大气层引导文件，等于cfw(auto)大气层原版Fusee引导  
    hwfly\_toolbox.bin：hwfly芯片的固件刷新程序，mariko型号玩Lakka、Ubuntu等先刷sdloader才行。
    
    【四、整合包组件版本】  
    （1）大气层三件套组件  
    （1-1）atmosphere-1.8.0-prerelease-c6014b533+hbl-2.4.4+hbmenu-3.6.0  
    [https://github.com/Atmosphere-NX/Atmosphere/releases](https://github.com/Atmosphere-NX/Atmosphere/releases)  
    （1-2）hekate\_ctcaer\_6.2.2\_Nyx\_1.6.4  
    引导核心，破解的引导开机程序  
    [https://github.com/CTCaer/hekate/releases](https://github.com/CTCaer/hekate/releases)  
    以下两位大佬分别分享的汉化nyx.bin文件，任选一个nyx.bin文件覆盖bootloader/sys/  
    [https://github.com/easyworld/hekate/releases](https://github.com/easyworld/hekate/releases)  
    [https://www.tekqart.com/thread-222735-1-1.html](https://www.tekqart.com/thread-222735-1-1.html)  
    （1-3）Sigpatches for Atmosphere 1.8.0（最高支持SW19.0.1）  
    有多个渠道可以下载签名补丁sigpatch  
    [https://gbatemp.net/threads/sigpatches-for-atmosphere-hekate-fss0-fusee-package3.571543/](https://gbatemp.net/threads/sigpatches-for-atmosphere-hekate-fss0-fusee-package3.571543/)  
    [https://hackintendo.com/download/sigpatches/](https://hackintendo.com/download/sigpatches/)  
    签名补丁的制作工具IPS\_Patch\_Creator  
    [https://gbatemp.net/download/ips-patch-creator-1-5-9.38850](https://gbatemp.net/download/ips-patch-creator-1-5-9.38850)  
    在atmosphere/contents启动的sys-patch插件也可以替代以上那种IPS格式的签名补丁。  
    [https://gbatemp.net/download/sys-patch-sysmodule.38874](https://gbatemp.net/download/sys-patch-sysmodule.38874)  
    （2）Tesla插件  
    （2-1）Tesla基本组件（已经替换成ultrahand，同名替换ovlloader，ovlmenu）  
    ovlloader-Tesla启动器-2025.02.11  
    [https://github.com/ppkantorski/nx-ovlloader/releases](https://github.com/ppkantorski/nx-ovlloader/releases)  
    ovlmenu-Tesla菜单-2025.02.11  
    [https://github.com/ppkantorski/Ultrahand-Overlay/releases](https://github.com/ppkantorski/Ultrahand-Overlay/releases)  
    ovlsysmodules-Tesla系统管理-2025.02.11  
    [https://www.tekqart.com/thread-222735-1-1.html](https://www.tekqart.com/thread-222735-1-1.html)  
    （2-2）EdiZon.ovl-2025.02.11  
    金手指游戏修改  
    [https://github.com/ppkantorski/EdiZon-Overlay/releases](https://github.com/ppkantorski/EdiZon-Overlay/releases)  
    （2-3）sys-clk-EOS.ovl-1.5.1  
    超频插件，不建议非续航和Lite启动极限超频  
    [https://github.com/halop/OC\_Toolkit\_SC\_EOS/releases](https://github.com/halop/OC_Toolkit_SC_EOS/releases)  
    （2-4）StatusMonitor.ovl-2025.02.11  
    实时监控信息，插件按LSTICK+RSTICK退出  
    [https://github.com/ppkantorski/Status-Monitor-Overlay/releases](https://github.com/ppkantorski/Status-Monitor-Overlay/releases)  
    （3）相册NRO软件，在Switch/  
    （3-1）Awoo-Installer.nro--v1.4.1-0330310  
    游戏安装工具，前端进  
    [https://github.com/dragonflylee/Awoo-Installer/releases](https://github.com/dragonflylee/Awoo-Installer/releases)  
    配合电脑上的ns-usbloader，安装速度比DBI快  
    [https://github.com/developersu/ns-usbloader/releases](https://github.com/developersu/ns-usbloader/releases)  
    （3-2）Checkpoint.nro--v3.8.2  
    游戏存档管理工具  
    [https://github.com/FlagBrew/Checkpoint/releases](https://github.com/FlagBrew/Checkpoint/releases)  
    （3-3）DBI.nro--v658英文版（同文件夹下重命名DBI.nro.cn是汉化版DBI647，DBI.nro.ru是俄文版DBI779）  
    游戏安装，存档管理和文件传输工具，  
    [https://github.com/rashevskyv/dbi/releases](https://github.com/rashevskyv/dbi/releases)  
    （3-4）DeepSea-Toolbox.nro--v6.0.0  
    深海工具箱，插件管理，实际是Hekate-toolbox--v4.0.3，支持Mariko型主机重启  
    [https://github.com/WerWolv/Hekate-Toolbox/releases](https://github.com/WerWolv/Hekate-Toolbox/releases)  
    [https://github.com/Team-Neptune/DeepSea-Toolbox/releases](https://github.com/Team-Neptune/DeepSea-Toolbox/releases)  
    （3-5）Edizon-SE.nro--v3.8.37  
    金手指游戏修改工具  
    [https://github.com/tomvita/EdiZon-SE/releases](https://github.com/tomvita/EdiZon-SE/releases)  
    （3-6）Goldleaf.nro--v1.0.0  
    文件管理工具，还可以安装NSP，提取系统离线升级固件，解除账号认证等  
    [https://github.com/XorTroll/Goldleaf/releases](https://github.com/XorTroll/Goldleaf/releases)  
    （3-7）JKSV.nro--11.05.2024  
    游戏存档管理工具  
    [https://github.com/J-D-K/JKSV/releases](https://github.com/J-D-K/JKSV/releases)  
    （3-8）linkalho.nro--v2.0.1-2a980d69  
    模拟关联任天堂账号工具  
    [https://gbatemp.net/download/linkalho.38822/](https://gbatemp.net/download/linkalho.38822/)  
    （3-9）N-Xplorer--v0.7.1  
    文本编辑文件管理器  
    [https://github.com/CompSciOrBust/N-Xplorer/releases](https://github.com/CompSciOrBust/N-Xplorer/releases)  
    （3-10）NX-Activity-Log.nro--v1.5.5  
    游戏游玩时间记录工具  
    [https://github.com/zdm65477730/NX-Activity-Log/releases](https://github.com/zdm65477730/NX-Activity-Log/releases)  
    （3-11）switchtime.nro--v0.1.5  
    联网校准时钟，90dns的破解系统也可用，先打开系统联网更新时间的功能  
    [https://github.com/3096/switch-time/releases](https://github.com/3096/switch-time/releases)  
    （3-12）Tencent-switcher-GUI.nro--v0.1.2  
    国行和非国行系统切换工具  
    [https://github.com/CaiMiao/Tencent-switcher-GUI/releases](https://github.com/CaiMiao/Tencent-switcher-GUI/releases)  
    （3-13）Tinfoil.nro--v19.1  
    游戏安装、文件管理等综合工具，有DBI类似的MTP功能，自动安装前端，只推荐在虚拟系统里使用  
    [https://tinfoil.media/Download#download](https://tinfoil.media/Download#download)  
    [https://tinfoil.io/Download#download](https://tinfoil.io/Download#download)  
    （3-14）wiliwili.nro--v1.5.1  
    哔哩哔哩播放器，需要联网并校对系统时间，自动安装前端，只推荐在虚拟系统里使用  
    [https://github.com/xfangfang/wiliwili/releases](https://github.com/xfangfang/wiliwili/releases)  
    （4）Hekate下的加载payload文件，在Bootloader/payloads/  
    （4-1）CommonProblemResolver.bin--v0.3.5  
    Hekate下删除主题和关闭插件自动启动，OLED可用  
    进去1是关闭插件自启动，2是删除安装的主题，有效解决进不去HOS系统的故障  
    [https://github.com/zdm65477730/CommonProblemResolver/releases](https://github.com/zdm65477730/CommonProblemResolver/releases)  
    （4-2）Lockpick\_RCM.bin--v1.9.13  
    主机系统的密钥提取工具，OLED可用  
    提取的prod.key在SD卡Switch/  
    [https://gbatemp.net/download/lockpick\_rcm-1-9-13-fw-19-zoria.38848](https://gbatemp.net/download/lockpick_rcm-1-9-13-fw-19-zoria.38848)  
    （4-3）TegraExplorer.bin--v4.2.0  
    Hekate下的文件管理工具，OLED可用  
    [https://github.com/suchmememanyskill/TegraExplorer/releases](https://github.com/suchmememanyskill/TegraExplorer/releases)  
    有用的Tegraexplorer程序脚本  
    [https://github.com/suchmememanyskill/TegraScript](https://github.com/suchmememanyskill/TegraScript)  
    [https://github.com/JeffVi/Prodinfo-Restore-TegraScript](https://github.com/JeffVi/Prodinfo-Restore-TegraScript)  
    （4-4）hwfly\_toolbox.bin--v1.1.1  
    hwfly工具箱，硬破专用，支持不可更新固件的hwfly芯片免拆机更新sdloader  
    玩Lakka，Ubuntu和Android必备  
    升级正版系统后需再刷sdloader.enc一次，升级虚拟系统不影响  
    [https://github.com/hwfly-nx/hwfly-toolbox/releases](https://github.com/hwfly-nx/hwfly-toolbox/releases)  
    刷完sdloader.enc后支持不插SD卡，开机后按音量+和-进正版系统  
    解压缩后复制sdloader.enc到SD卡根目录  
    [https://github.com/hwfly-nx/firmware/releases](https://github.com/hwfly-nx/firmware/releases)  
    （4-5）picofly\_toolbox.bin--v0.2  
    树莓派rp2040工具箱，硬破专用，和hwfly工具箱通用更新sdloader，但不通用firmware固件  
    树莓派固件下载后命名update.bin放在根目录后可在Hekate加载picofly\_toolbox.bin升级  
    [https://gbatemp.net/threads/picofly-a-hwfly-switch-modchip.622701/page-78#post-10090767](https://gbatemp.net/threads/picofly-a-hwfly-switch-modchip.622701/page-78#post-10090767)  
    [https://github.com/rehius/usk/releases](https://github.com/rehius/usk/releases)
    
    【五、整合包更新日志】  
    2025.04.08更新Checkpoint.nro--v3.8.2（无需重新制作前端NSP），NX-Activity-Log.nro--v1.5.5（和checkpoint一样必须以前端模式进），更新DBI同文件夹下DBI.nro.ru是俄文版DBI779。  
    2025.02.28更新wiliwili.nro--v1.5.1，更新DBI同文件夹下DBI.nro.ru是俄文版DBI763，一键清理contents的旧插件和删主题20250228更新。  
    2025.02.12更新z大佬发布的Tesla基本组件，Edizon和StatusMonitor，更新DBI同文件夹下DBI.nro.ru是俄文版DBI756。  
    2025.01.16更新sys-clk-EOS.ovl-1.5.1，新增DBI同文件夹下重命名DBI.nro.ru是俄文版DBI750，想替换英文版DBI658或共存都可以参考「分享」新人必看的Switch破解游戏安装教程。  
    2024.12.09更新Z大的ovlsysmodules，EdiZon，StatusMonitor，更新NX-Activity-Log.nro--v1.5.4，Tinfoil.nro--v19.1（自带前端，支持19.0.0+）。  
    2024.11.11更新Z大的ovlloader，ultrahand，ovlsysmodules，EdiZon，StatusMonitor，NX-Activity-Log.nro，更新linkalho.nro。  
    2024.11.08更新JKSV.nro--11.05.2024。  
    2024.10.29更新Z大的ovlmenu-ultrahand。Switch新系统19.0.1，大气层1.8.0继续支持，无需更新。  
    2024.10.25更新Z大的ovlloader，ovlmenu-ultrahand，ovlsysmodules，edizon和StatusMonitor.ovl，更新wiliwili.nro--v1.5.0支持19.0.0自动安装前端不会报错。  
    2024.10.21更新sigpatch在原来ES、FS、Loader和NFIM基础上新增nim patch，这个nim patch适合使用代理服务器在虚拟系统使用隐藏序列号玩黑商店，youtube等防BAN。更新ovlmenu-1.7.9，StatusMonitor.ovl-v1.1.4+。  
    2024.10.19更新ovlloader-Tesla启动器-1.0.9+，更新sys-clk-EOS.ovl-1.5.0支持大气层1.8.0或以上，只要不覆盖启动设置，这个极限超频只能当普通超频插件使用。更新EdiZon.ovl-1.0.9。虽目前大气层1.8.0还是prerelease，但经过一段时间的测试，和正式版没区别，而且运行nro转nsp前端的工具并不是sigpatch的问题，而是需要新版本的转换工具制作：Menu0.12beta-nro2nsp-FW19。  
    2024.10.16更新atmosphere-1.8.0-prerelease-c6014b533，更新此版大气层的loader patch（ips和patches.ini），fusee.bin取自gbatemp论坛编译版，支持fusee引导的fs/loader的ips补丁。  
    2024.10.15更新支持19.0.0万能前端hbmenu.nsp，先删旧的桌面图标再安装新的，更新applet版的tinfoil.nro，进入方式和wiliwili.nro一样。由于极限超频插件EOS未更新支持大气层1.8.0pre，如果SD卡上已经有覆盖过朗姆之前发的极限超频插件EOS，建议删除atmosphere/kips/loader.kip后再覆盖大气层1.8.0pre整合包完成升级。  
    2024.10.13上午更新内置sigpatch的fusee.bin，更新fss0的patches.ini，恢复显示大气层原版fusee引导，fss0和fusee引导的sigpatch都最高支持19.0.0系统，真实或虚拟破解系统都可以升级19.0.0后玩NSP/XCI等破解游戏，但是暂时不支持前端NSP软件，比如wiliwili解决方法可通过按住R键打开游戏进hbmenu再打开wiliwili.nro，更新StatusMonitor.ovl-v1.1.4。  
    2024.10.13凌晨，更新atmosphere-1.8.0-prerelease-5717ea6c0，hekate\_ctcaer\_6.2.2\_Nyx\_1.6.4，由于sigpatch最高只能支持SW18.1.0，所以不能在19.0.0系统里玩破解游戏，只能玩正版游戏，要daybreak降级到18.1.0才可以玩破解游戏，暂时屏蔽大气层原版fusee引导（更多-大气层自动识别，大气层1.7.0以后不支持fusee引导玩破解游戏），更新Lockpick\_RCM.bin--v1.9.13。  
    2024.10.03更新替换Tesla（ovlloader+ovlmenu已同名替换成ultrahand，此次也一样可以覆盖升级，和Tesla一样启动键L+Ddown），更新StatusMonitor.ovl-v1.1.3英文，switchtime.nro--v0.1.5，更新极限超频EOS1.4.4。  
    由于替换ultrahand和StatusMonitor.ovl-v1.1.3英文，所以SD卡原config/Tesla-Menu，switch/.overlays/lang/Tesla-Menu，switch/.overlays/lang/StatusMonitor这三个文件夹可删除，不删也没关系。  
    2024.08.07更新JKSV.nro--08.06.2024。  
    2024.07.24更新JKSV.nro--07.18.2024，TegraExplorer.bin--v4.2.0。  
    2024.07.06更新Z大发布的StatusMonitor.ovl-2024.7.4，更新wiliwili.nro--v1.4.1（相册重进一次wiliwili.nro安装前端搞定升级）。  
    2024.07.03更新hekate6.2.1汉化版，更新极限超频EOS1.3.2（已解除掌机不充电的GPU限制）。  
    2024.06.19更新Z大的“StatusMonitor.ovl”插件，更新极限超频EOS1.3.1。  
    2024.06.17更新lsp199308编译的atmosphere-1.7.1-master-e85bc4db0-dirty，sigpatch已内置，替换atmosphere/package3，atmosphere/stratosphere.romfs，bootloader/payloads/fusee.bin这三个文件即可。重新显示“更多设置”中的“大气层自动识别（fusee引导）”。  
    2024.06.14更新Hekate6.2.0-v4汉化版。暂时屏蔽更多设置中的“大气层-自动识别（fusee引导）”，等大佬编译内置sigpatch的大气层1.7.1后再显示该引导项。  
    2024.06.11更新原版Atmosphere1.7.1，Hekate6.2.0-v3汉化版，Sigpatch，Z大的Tesla插件edizon和StatusMonitor.ovl，更新极限超频插件EOS1.3.0适配18.1.0系统。  
    2024.06.09更新EdiZon.ovl和nro-2024.6.9，更新极限超频EOS1.2.7，但loader.kip依旧锁RAM最大1996。  
    2024.06.04更新Tinfoil.nro--v18.1。  
    2024.05.10更新Z大发布的ovlmenu.ovl和ovl-sysmodules.ovl。  
    2024.05.01更新wiliwili.nro--v1.4.0。  
    2024.04.25更新18.0.1的nfim\_ctest补丁，新增N-Xplorer--v0.7.1文本编辑文件管理器，替换Zdm大佬的完整汉化Hekate的nyx.bin。  
    2024.04.15更新Z大的Tesla插件，sys-clk超频插件，edizon金手指等。  
    2024.04.09更新lsp199308编译的atmosphere-1.7.0-master-35d93a7c4-dirty，sigpatch已内置，替换atmosphere/package3，atmosphere/stratosphere.romfs，bootloader/payloads/fusee.bin这三个文件即可。这样大气层自动识别（原版Fusee引导）也能正常玩破解游戏不受影响，更新EOS1.1（文件路径一样，OC2.2.0）极限超频插件代替原来的OC1.9.2，支持大气层1.7.0和SW18.0.0系统。  
    2024.03.31更新atmosphere-1.7.0-prerelease-35d93a7c4，hekate\_ctcaer\_6.1.1\_Nyx\_1.6.1，sigpatch，lockpick。大气层1.7.0开始，fusee自动识别引导不允许加载KIP patch，会导致FS和Loader的sigpatch不能被加载，建议FSS0引导的真实破解系统，虚拟破解系统或者真实正版系统。sigpatch的问题，如果想用fusee引导又要sigpatch玩破解游戏，就下载18.0.0系统的sys-patch兼容版替代sigpatch的插件，或者用大佬重新编译的大气层package3和stratosphere.romfs的两个内置sigpatch的组件替换原版的大气层文件。极限超频插件覆盖包用于替换稳定包自带的是标准超频插件，非续航和Lite两类机型不建议使用极限超频插件，极限超频插件暂时不支持18.0.0系统，目前能用普通超频插件，主要是loader.kip加载问题。  
    2024.02.23更新hekate\_ctcaer\_6.1.0\_Nyx\_1.6.0，Switch/DBI/DBI.nro是658英文版（同文件夹下重命名DBI.nro.cn是汉化版DBI647，可自行更名替换，原来DBI.nro.en是DBI658，现在可以删除它）。  
    2024.01.30更新Z大佬的StatusMonitor.ovl。  
    2024.01.18更新Z大佬的StatusMonitor.ovl和ovlsysmodules，更新wiliwili.nro--v1.3.0。  
    2024.01.11更新Z大佬的StatusMonitorOverlay v1.0.3a2和NX-Activity-Log.nro  
    2024.01.05更新Z大佬的更新StatusMonitorOverlay v1.0.3a，更新DBI658，新加Hekate可加载的树莓派工具箱picofly\_toolbox.bin。  
    2024.01.02更新Z大佬修复的StatusMonitor.ovl插件。  
    2023.12.31更新Z大佬的Tesla-Menu、超频插件、金手指、Hekate汉化版nyx.bin文件，但没更新Z大佬的StatusMonitor.ovl，因为有字体显示不全的bug，更新DBI.nro--v657。
    
    Downloads
    
    *   [Source code (ZIP)](/rumla34/Atmosphere-Stable/archive/1.8.0.zip)
        
        259 downloads
        
    *   [Source code (TAR.GZ)](/rumla34/Atmosphere-Stable/archive/1.8.0.tar.gz)
        
        102 downloads
        
    
    * * *
    
    *   [AMS1.8.0-Stable-v250408.rar](https://codeberg.org/rumla34/Atmosphere-Stable/releases/download/1.8.0/AMS1.8.0-Stable-v250408.rar)
        
        689 downloads · 83 MiB
        
    

![](https://design.codeberg.org/logo-kit/icon_inverted.svg)

**Codeberg**

*   [Documentation](https://docs.codeberg.org)
*   [Community Issues](/Codeberg/Community/issues)
*   [Contributing](/Codeberg/Contributing)
*   [Report Abuse](https://docs.codeberg.org/contact/#abuse)

**Association**

*   [Who are we?](https://docs.codeberg.org/getting-started/what-is-codeberg/#what-is-codeberg-e.v.%3F)
*   [Bylaws / Satzung](/codeberg/org/src/en/bylaws.md)
*   [Donate](https://docs.codeberg.org/improving-codeberg/donate/)
*   [Join / Support](https://join.codeberg.org)
*   [Contact](https://docs.codeberg.org/contact/)

**Service**

*   [Codeberg Pages](https://codeberg.page)
*   [Weblate Translations](https://translate.codeberg.org)
*   [Woodpecker CI](https://docs.codeberg.org/ci/#using-codeberg's-instance-of-woodpecker-ci)
*   [Forgejo API](/api/swagger)
*   [Status Page](https://status.codeberg.eu)

**Legal**

*   [Imprint / Impressum](/codeberg/org/src/Imprint.md)
*   [Privacy Policy](/codeberg/org/src/PrivacyPolicy.md)
*   [Licenses](/assets/licenses.txt)
*   [Terms of Use](/codeberg/org/src/TermsOfUse.md)

[Blog](https://blog.codeberg.org) | [Mastodon](https://social.anoxinon.de/@Codeberg) | [Matrix Space](https://matrix.to/#/#codeberg-space:matrix.org) | [Powered by Forgejo](/Codeberg-Infrastructure/forgejo)

English

Bahasa Indonesia Deutsch English Español Esperanto Filipino Français Italiano Latviešu Magyar nyelv Nederlands Plattdüütsch Polski Português de Portugal Português do Brasil Slovenščina Suomi Svenska Türkçe Čeština Ελληνικά Български Русский Українська فارسی 日本語 简体中文 繁體中文（台灣） 繁體中文（香港） 한국어

↑↓⇔⇧⇩