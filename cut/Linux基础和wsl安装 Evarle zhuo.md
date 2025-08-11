# Linux基础和wsl安装 | Evarle zhuo
[Linux基础和wsl安装 | Evarle zhuo](https://evarle.top/post/2023/10/14/Linux-and-wsl/) 

       Linux基础和wsl安装 | Evarle zhuo

Constants loaded at 2025-08-11T15:12:48.151Z

[Evarle](/)

[Home](/)

[Tags](/tags/)

[Links](/links/)

[About](https://evarle.top/about/)

Search

[Home](/)

[Tags](/tags/)

[Links](/links/)

[About](https://evarle.top/about/)

Search

[笔记](/tags/%E7%AC%94%E8%AE%B0/)

Linux基础和wsl安装
=============

Linux Windows子系统 SSH

Evarle

2023-10-14

19 min

Linux作为一个开源的操作系统，已经成为计算领域的瑰宝。从服务器到个人电脑，再到嵌入式系统，Linux的广泛应用和灵活性使其在当今的数字时代中不可或缺。

* * *

[#](#linux基础) Linux基础
---------------------

Linux 是一种开源操作系统内核，它是基于类 Unix 操作系统的一个重要组成部分。Linux 内核最初由芬兰程序员 Linus Torvalds 在1991年创建，并在之后由全球各地的开发者和社区不断开发和维护。Linux 内核的开源性质意味着任何人都可以查看、修改和分发它的源代码，这使得 Linux 成为一个非常灵活、可定制和强大的操作系统。

> 完整的 Linux 操作系统通常被称为 "**GNU/Linux**"，这是一个更准确和全面的称呼。GNU/Linux 包括了 Linux 内核以及 GNU 项目的工具和软件，以形成一个完整的操作系统。GNU 项目的工具包括 shell、文本编辑器、编译器、文件管理器等，它们为 Linux 操作系统提供了用户界面和基本的系统工具。

### [#](#linux操作系统的特点有) Linux操作系统的特点有：

1.  开源：Linux 内核以及大部分与之关联的软件都是开源的，这意味着用户可以自由地访问、修改和分发代码。社区资源丰富，生态好。
    
2.  多样化的发行版：Linux 有许多不同的发行版（Distribution），每个发行版在 Linux 内核的基础上添加了不同的软件包和工具，以满足不同用户需求。一些知名的 Linux 发行版包括 Ubuntu、Fedora、Debian、CentOS 等。
    
3.  高性能和稳定性：Linux 在多种硬件平台上运行，并且具有出色的性能和可伸缩性。这使得它适用于各种不同的服务器工作负载，从Web服务器到数据库服务器和虚拟化服务器。Linux的服务器发行版专门设计用于在服务器环境中提供稳定性、性能和安全性。
    
4.  安全性高：由于其开源性质，Linux 受到广泛审查，从而可以更快地发现和修复潜在的安全漏洞。此外，Linux 拥有强大的权限管理系统，可以帮助保护服务器免受未经授权的访问
    
5.  可移植性：Linux 内核可以在各种硬件平台上运行，从个人计算机到嵌入式系统和超级计算机。
    

### [#](#linux常用命令) Linux常用命令

`uname -a`显示系统信息。

`free -h`显示内存使用情况。

`df -h`显示文件系统磁盘空间使用情况。

`du -sh /path/to/directory`：显示目录的总磁盘使用情况。

`du -h --max-depth=1 /path/to/directory`：限制查看目录的深度，并显示各个一级子目录的磁盘使用情况。

`du -h --max-depth=1 /path/to/directory | sort -h`：按磁盘使用情况排序并显示各个一级子目录的磁盘使用情况。

`lsof` 是一个用于列出打开文件（Open Files）和套接字（Open Sockets）的命令行工具，它用于显示当前系统上正在使用的文件、目录和网络连接的信息。

`lsof /path/to/directory` 显示目录下被打开的文件。

`lsof /path/to/file` 显示特点文件的打开者。

`lsof -i`显示网络连接。

`lsof -i -sTCP:LISTEN` 显示监听的网络连接。

`lsof -i :80` 显示哪个进程在使用80端口。

**软件包管理**`apt update -y && apt upgrade -y` 自动更新系统的软件包和操作系统，确保系统中的所有软件都是最新的。

**网络工具** ifconfig：查看和配置网络接口。 netstat -tul ：查看所有监听的端口

*   `ss`（Socket Statistics）命令用于显示套接字信息，包括网络连接、路由表、接口统计等。它是一个非常强大的工具，用于网络配置和故障排除。
    
    `ss -t/-u/-l/-r` 查询所有tcp连接/udp连接/监听状态/路由表
    
*   `ip` 命令是一个用于管理网络接口、地址和路由的多功能工具，它是 ifconfig 和 route 命令的现代替代品。
    
    `ip a` 显示所有网络接口 `ip route` 显示路由表信息
    

**权限更改 chmod**`chmod 770 file.txt`改变文件或者目录权限。

三个数字按顺序表示，文件所有者文件、所属组和其他用户的权限。 每个数字由三位二进制数字组成，分别代表读（r）、写（w）、执行（x）权限。

*   r（读权限）对应于数字 4。
*   w（写权限）对应于数字 2。
*   x（执行权限）对应于数字 1。

7为最高权限，0为没有权限。

**管道符号 |**

将“ | ”符号前面命令执行的结果作为后面一条命令的标准输入

`cat /etc/config|grep`

**文本搜索匹配 grep**

`grep [选项] 模式 文件名`，通常配合管道符号使用

**文本处理 awk**

`awk 'pattern { action }'`

其中：

*   `'pattern'` 是一个模式，用于匹配文本中的行。
*   `{ action }` 是在模式匹配的行上执行的动作。
*   `input-file` 是要处理的输入文件。

`awk` 会逐行读取输入文件，然后根据模式匹配来决定是否执行相应的动作。如果模式匹配成功，就会执行相应的动作。如果没有提供模式，则会默认匹配所有行。

`awk` 的核心思想是将每一行分割成字段，然后可以通过 `$1`、`$2` 等变量来访问字段的内容，以及使用内置函数来进行操作。

[#](#windous子系统wsl) windous子系统wsl
---------------------------------

### [#](#什么是wsl) 什么是wsl

WSL (Windows Subsystem for Linux) 是一种由微软开发的技术，它允许在 Windows 操作系统上运行 Linux 发行版。WSL 的目标是提供一个完整的 Linux 内核和用户空间环境，以便开发人员可以在 Windows 上使用类似于 Linux 的命令行工具和应用程序，而无需双启动或虚拟机。

### [#](#安装wsl) 安装wsl

1.  搜索“功能”，打开“启用或关闭Windows功能”，或者在设置，应用，可选功能，拉到最下面更多Windows功能。
2.  勾选以下功能。
    *   虚拟机平台
    *   适用于 Linux 的 Windows 子系统
3.  等到安装完成后重新启动电脑。
4.  安装Linux发行版，打开商店安装需要的Linux发行版（如 Ubuntu、Debian、Arch Linux 等）。
5.  初始化 Linux 发行版，打开安装的Linux发行版，创建用户名和密码，等到出现Linux的命令行提示符就成功了。

> 常见问题：
> 
> 若出现Error：WSL 2 ?????????????? https://aka.ms/wsl2Kernel。说明是wsl内核没更新，打开PowerShell，输入`wsl --update`更新wsl内核，重启wsl `wsl --shutdown`就可以了。

### [#](#wsl基本命令) WSL基本命令

> *   `wsl --list --online` 查看可通过在线商店获得的 Linux 发行版列表。 此命令也可输入为：`wsl -l -o`。
> *   `wsl -l -v` 查看安装在 Windows 计算机上的 Linux 发行版列表，包括状态和 WSL 版本。
> *   `wsl --set-default <Distribution Name>` 设置默认 Linux 发行版。
> *   `wsl --update`更新WSL。
> *   `wsl --status`查看有关 WSL 配置的常规信息，例如默认发行版类型、默认发行版和内核版本。

### [#](#配合vs-code使用) 配合VS Code使用

1.  在VScode中安装WSL拓展
    
2.  使用`CTRL+SHIFT+P` 调出命令面板，输入wsl选择连接到wsl，连接成功后左下角会显示Linux发行版名称。或者直接在wsl命令行的目录下输入`code .`直接在vscode中打开该文件夹。
    

[#](#在wsl中安装miniconda) 在wsl中安装miniconda
---------------------------------------

### [#](#什么是miniconda) 什么是Miniconda

Miniconda 是一个轻量级的软件包管理系统，用于管理和部署 **Python** 和其他编程语言的软件包和环境。它是 Anaconda 的精简版，Anaconda 是一个更大的数据科学和机器学习工具集，包括了大量的数据科学库和工具。Miniconda 的目标是提供一个更小、更灵活的安装选项，允许用户自己选择要安装的软件包，而不是像 Anaconda 那样一次性安装大量的软件包。

Miniconda 允许用户创建和管理独立的 Python 环境，每个环境都可以有自己的软件包依赖关系，从而隔离不同项目的依赖。对于不同项目需要不同的Python环境，或者需要维护一个旧版本Python的项目来说非常好用，相当于一个虚拟环境。

### [#](#在wsl的ubuntu中安装miniconda) 在WSL的ubuntu中安装miniconda

1.  在[Miniconda](https://docs.conda.io/projects/miniconda/en/latest/)官网，选择最新的miniconda的Linux版本下载
2.  将.sh文件复制到ubuntu中
3.  执行`bash Miniconda3-latest-Linux-x86_64.sh`安装下载的miniconda。

或者使用命令行快速安装

> These four commands quickly and quietly install the latest 64-bit version of the installer and then clean up after themselves. To install a different version or architecture of Miniconda for Linux, change the name of the `.sh` installer in the `wget` command.
> 
> ```
> mkdir -p ~/miniconda3
> wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
> bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
> rm -rf ~/miniconda3/miniconda.sh 
> ```
> 
> After installing, initialize your newly-installed Miniconda. The following commands initialize for bash and zsh shells:
> 
> ```
> ~/miniconda3/bin/conda init bash
> ~/miniconda3/bin/conda init zsh 
> ```

安装完成后打开新的终端窗口，执行conda有出现conda命令说明安装成功，输入`conda config --set auto_activate_base false`可以去掉命令行前面的（base），取消默认启动base环境。

#### [#](#配置conda国内镜像) 配置conda国内镜像

这里以阿里云镜像为例，在阿里云镜像网站搜索anaconda

*   Linux用户可以通过修改用户目录下的 `.condarc` 文件，添加下面代码。
    
    ```
    channels:
      - defaults
    show_channel_urls: true
    default_channels:
      - http://mirrors.aliyun.com/anaconda/pkgs/main
      - http://mirrors.aliyun.com/anaconda/pkgs/r
      - http://mirrors.aliyun.com/anaconda/pkgs/msys2
    custom_channels:
      conda-forge: http://mirrors.aliyun.com/anaconda/cloud
      msys2: http://mirrors.aliyun.com/anaconda/cloud
      bioconda: http://mirrors.aliyun.com/anaconda/cloud
      menpo: http://mirrors.aliyun.com/anaconda/cloud
      pytorch: http://mirrors.aliyun.com/anaconda/cloud
      simpleitk: http://mirrors.aliyun.com/anaconda/cloud 
    ```
    
    即可添加 Anaconda Python 免费仓库。
    
    配置完成可运行 `conda clean -i` 清除索引缓存。
    
    #### [#](#conda命令) conda命令
    
    *   `conda env list`列出所有的conda环境
    *   `conda create --name env_name python=3.10` 创建名为env\_name的python3.10环境
    *   `conda remove --name env_name --all`删除conda环境env\_name
    *   `conda update conda`更新conda到最新版本
    *   `conda activate env_name` 激活conda环境
    *   `conda deactivate` 退出conda环境

[#](#在ubuntu中安装zsh) 在ubuntu中安装zsh
---------------------------------

### [#](#什么是zsh) 什么是zsh

[Zsh](https://www.zsh.org/)是一种命令行壳（shell），用于在计算机上与操作系统进行交互。它是 Bourne shell（sh）的扩展，提供了许多增强的功能和用户友好的命令行体验。

**zsh** 是一个兼容 bash 的 shell，相较 bash 具有以下优点：

*   Tab 补全功能强大：命令、命令参数、文件路径均可以补全。

*   插件和主题丰富：快速输入以前使用过的命令、快速跳转文件夹、显示系统负载这些都可以通过插件实现。
*   可扩展性高：Zsh 允许用户编写自定义函数、别名和脚本，以满足特定需求，从而将命令行工具集成到日常工作流程中。

### [#](#安装zsh) 安装zsh

*   在ubuntu命令行中执行`sudo apt-get install zsh`安装zsh。
    
*   输入`cat /etc/shells` 查看系统可用的shell
    
*   使用 `chsh -s /bin/zsh` 命令将 zsh 设置为系统默认 shell。打开一个新的终端，就可以开始使用 zsh 了。
    

#### [#](#安装oh-my-zsh) 安装oh-my-zsh

使用 curl 下载脚本并安装：

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" 
```

或者使用 wget 下载脚本并安装：

```
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)" 
```

**使用国内gitee镜像安装**：

```
sh -c "$(wget wget https://gitee.com/mirrors/oh-my-zsh/raw/master/tools/install.sh -O -)" 
```

#### [#](#修改oh-my-zsh主题) 修改oh-my-zsh主题

在 https://github.com/ohmyzsh/ohmyzsh/wiki/Themes 中查看内置的主题样式和对应的主题名，所有当前主题都可以在`~/.oh-my-zsh/themes`目录中找到。

如果要启用主题，在 `~/.zshrc` 中设置 `ZSH_THEME=主题的名称`，如果不希望启用任何主题，只需设置为： `ZSH_THEME=""`，使用robbyrussell主题 `ZSH_THEME=robbyrussell`。

除了内置主题外还能其他第三方开源主题，下载主题放到`~/.oh-my-zsh/themes`目录下就行。

这里推荐[powerlevel10k](https://github.com/romkatv/powerlevel10k)主题:

> 1.  Clone the repository:
>     
>     ```
>     git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k 
>     ```
>     
>     Users in China can use the official mirror on gitee.com for faster download. 中国用户可以使用 gitee.com 上的官方镜像加速下载.
>     
>     ```
>     git clone --depth=1 https://gitee.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k 
>     ```
>     
> 2.  Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`.
>     
> 3.  然后执行 `source ~/.zshrc` 配置生效，这时会提示对主题进行配置，按照提示进行即可.
>     
> 
> _如果想重新配置主题，执行`p10k configure`重新引导配置。_

oh-my-zsh还内置了很多插件，内置插件可以在 `~/.oh-my-zsh/plugins` 中查看，或者在https://github.com/unixorn/awesome-zsh-plugins里面查看更多插件。

[#](#设置网络代理) 设置网络代理
-------------------

wsl和windows是两个独立的系统环境，它们是在同一计算机上的不同系统，所以wsl无法直接使用系统代理，可以使用代理工具里的局域网代理。

*   代理工具开启允许局域网代理
*   wsl2的windows系统ip地址存在/etc/resolv.conf 文件中，运行以下命令来获取主机的 IP 地址：`cat /etc/resolv.conf`nameserver就是windows的ip地址，或者执行`ip route`也能看到。

```
# 设置代理
export https_proxy="http://${hostip}:${http_hostport}"
export http_proxy="http://${hostip}:${http_hostport}"
export ALL_PROXY="socks5://${hostip}:${socks_hostport}"
export all_proxy="socks5://${hostip}:${socks_hostport}" 
```

验证代理是否成功

```
# 使用以下命令，若返回代理服务器ip地址则表示代理成功，如果卡住表示失败
curl https://api.ipify.org?format=json
或者 
curl -v https://ip.jackjyq.com/ 
```

添加自动设置脚本到 ~/.bashrc 底部，执行`vi ~/.bashrc`，在末尾添加这段代码：

```
# add proxy
export hostip=$(cat /etc/resolv.conf|grep nameserver|awk '{print $2}')
export socks_hostport=代理端口
export http_hostport=代理端口
alias proxy='
    export https_proxy="http://${hostip}:${http_hostport}"
    export http_proxy="http://${hostip}:${http_hostport}"
    export ALL_PROXY="socks5://${hostip}:${socks_hostport}"
    export all_proxy="socks5://${hostip}:${socks_hostport}"
'
alias unproxy='
    unset ALL_PROXY
    unset https_proxy
    unset http_proxy
    unset all_proxy
'
alias echoproxy='
    echo $ALL_PROXY
    echo $all_proxy
    echo $https_proxy
    echo $http_proxy
'
#end proxy 
```

然后执行`source ~/.bashrc`使修改生效

执行proxy设置代理，执行unproxy取消代理，执行echoproxy查看代理。

[#](#ssh远程连接) SSH远程连接
---------------------

SSH（Secure Shell）是一种网络协议和加密技术，用于安全地连接到远程计算机或服务器，并在安全通道上进行远程管理和数据传输。SSH 旨在提供数据传输的机密性和身份验证，以确保通信的隐私和完整性。

SSH 具有以下主要功能和特点：

*   加密通信：保护数据传输的隐私和完整性，防止未经授权的访问者拦截或窃听通信内容。
*   身份验证：要求用户提供身份验证凭证，通常是用户名和密码或公钥/私钥，以确认其合法性。
*   远程管理：允许远程管理服务器，执行命令、传输文件和设置配置。
*   端口转发：支持创建加密隧道，使远程服务器上的服务可以通过本地计算机访问。
*   多种实现：有多种 SSH 客户端和服务器的实现，如OpenSSH、Terminal、MobaXterm、PuTTY、XShell、FinalShell等等。

### [#](#使用vscode远程连接linux服务器) 使用VScode远程连接Linux服务器

可以参考一下官方文章：[Remote SSH: Tips and Tricks](https://code.visualstudio.com/blogs/2019/10/03/remote-ssh-tips-and-tricks)

#### [#](#安装remote-ssh插件) 安装Remote-SSH插件

安装后，在vscode左侧边栏会心脏一个电脑显示器的图标，选择SSH旁边设置，编辑config文件进行远程连接相关设置。 内容如下：

```
Host 主机名称 
  HostName 服务器ip地址
  User 登录的用户名
  Port SSH端口
 
Host mylinux
  HostName 192.168.1.102
  User root
  Port 22 
```

配置完成后选择服务器连接，第一次连接需要安装服务比较慢，需要等待一下，连接成功后左下会显示主机名。

#### [#](#proxycommand) ProxyCommand

对于远程访问的vps在国外的话，直接连接可能很慢，ssh还容易断连，可以选择添加代理。 只需要在ssh配置后面添加`ProxyCommand connect.exe -H 127.0.0.1:10809 %h %p`,connect.exe服务来源于Git，需要提前安装。127.0.0.1:10809是本地代理。

```
Host vps
  HostName ip地址
  User root
  Port 22
  ProxyCommand D:\Git\mingw64\bin\connect.exe -H 127.0.0.1:10809 %h %p 
```

或者你的vscode已经配置了全局代理了，就不需要额外配置ProxyCommand了。 按`F1`或者`shift+ctrl+p`搜索默认设置，打开默认设置(JSON),在vscode设置的配置文件添加：

```
"http.proxy": "http://your-proxy-server:port",
"https.proxy": "https://your-proxy-server:port" 
```

设置本地代理。

#### [#](#在远程vps上添加本地公钥) 在远程VPS上添加本地公钥

不建议用用户名和密码登录vps，直接让远程的vps信任本地的主机就行。 windows用户在终端中输入`ssh-keygen -t ed25519 -C "your_email@example.com"`生成ed25519编码的ssh公钥私钥，后面的邮箱可以不用。

> 注意：如果你使用的是不支持 Ed25519 算法的旧系统，请使用以下命令：`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

成功后在用户文件夹,ssh中会有两个文件，`id_ed25519`私钥和`id_ed25519.pub`公钥，将.ssh文件夹中的id\_ed25519.pub公钥的内容

> 一般长这样:ssh-ed25519 ABCDEFGKSAfjksjafkjsaLJfakjJ...

复制到vps的`/home/.ssh`文件夹的`authorized_keys`文件中。如果没有.ssh文件夹和authorized\_keys文件可以自己创建，然后执行`sudo service sshd restart`重启ssh服务。

这样本机就能之间连接远程服务器不需要密码了， 命令行输入`ssh -p 22 root@hostname`直接ssh连接vps服务器。

### [#](#释放wsl2的硬盘空间) 释放WSL2的硬盘空间

WSL2 使用虚拟硬盘 (VHD) 来存储 Linux 文件，它会自动扩展，但不会自动收缩。所以，即使你删除了Linux里面的文件，VHD 的大小也不会变小。所以要如何释放没用到的磁盘呢。

> 关于WSL磁盘空间问题，可以参考微软官方这篇文章[如何管理 WSL 磁盘空间](https://learn.microsoft.com/zh-cn/windows/wsl/disk-space)。

*   WSL2的磁盘一般挂载在`C:\Users\User\AppData\Local\Packages\CanonicalGroupLimited.UbuntuonWindows_79rhkp1fndgsc\LocalState\ext4.vhdx`。
*   首先，使用 `wsl.exe --shutdown` 命令终止所有WSL实例。
*   然后在管理员模式下打开 Windows 命令提示符，输入 `diskpart` 命令。在 `DISKPART>` 提示符下，输入 `select vdisk file="<pathToVHD>"`选择虚拟磁盘文件，其中 `<pathToVHD>` 是刚刚找的vhd磁盘路径。
*   使用`detail vdisk` 查看 VHD 的当前大小和可用空间。
*   压缩文件 `compact vdisk`。
*   压缩完毕后卸载磁盘 `detach vdisk`。

[Edit this page on GitHub](https://github.com/Mrzhuo2022/Mrzhuo2022.github.io/edit/main/blog/posts/2023-10-14-Linux-and-wsl.md)

Last Updated: 1/18/2024, 5:20:57 AM

[Previous  
Git与GitHub工作流](/post/2023/09/03/git-and-github/)[Next  
使用so-vits-svc进行语音模型训练](/post/2023/11/30/so-vits-svc-doc/)

*   Linux基础
*   Linux操作系统的特点有：
*   Linux常用命令
*   windous子系统wsl
*   什么是wsl
*   安装wsl
*   WSL基本命令
*   配合VS Code使用
*   在wsl中安装miniconda
*   什么是Miniconda
*   在WSL的ubuntu中安装miniconda
*   配置conda国内镜像
*   conda命令
*   在ubuntu中安装zsh
*   什么是zsh
*   安装zsh
*   安装oh-my-zsh
*   修改oh-my-zsh主题
*   设置网络代理
*   SSH远程连接
*   使用VScode远程连接Linux服务器
*   安装Remote-SSH插件
*   ProxyCommand
*   在远程VPS上添加本地公钥
*   释放WSL2的硬盘空间

90%

©2023 [Evarle](#)  
Powered by [VuePress](https://v2.vuepress.vuejs.org) & [Gungnir](https://github.com/Renovamen/vuepress-theme-gungnir)

↑↓⇔⇧⇩