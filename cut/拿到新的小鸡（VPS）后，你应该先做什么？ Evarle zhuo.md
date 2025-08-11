# 拿到新的小鸡（VPS）后，你应该先做什么？ | Evarle zhuo
[拿到新的小鸡（VPS）后，你应该先做什么？ | Evarle zhuo](https://evarle.top/post/2025/07/18/new-VPS-guide/) 

       拿到新的小鸡（VPS）后，你应该先做什么？ | Evarle zhuo

Constants loaded at 2025-08-11T15:12:44.293Z

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

[Linux](/tags/linux/)[docker](/tags/docker/)

拿到新的小鸡（VPS）后，你应该先做什么？
=====================

Linux VPS Docker

Evarle

2025-07-18

20 min

如果你拿到了一个新的VPS不知道要先做什么，或者你有闲置的小鸡不知道干什么，这篇文章或许会给你不错的建议或者参考。

* * *

[#](#拿到新的小鸡-vps-后-你应该先做什么) 拿到新的小鸡（VPS）后，你应该先做什么？
------------------------------------------------

恭喜你拥有了一台属于自己的云服务器（VPS）！这是一片充满无限可能的数字天地。但在你开始部署网站、搭建应用之前，务必先花上15-30分钟，完成一些至关重要的基础设置。这不仅能保护你的服务器免受最常见的网络攻击，还能为你未来的管理工作提供便利。

本文将以一台全新的、基于Ubuntu系统的VPS为例，手把手带你完成从登录到基础加固的全过程。

### [#](#准备工作) 准备工作

在开始之前，你需要从你的VPS提供商那里获取三个关键信息：

*   **服务器的IP地址** (例如: `192.0.2.1`)
*   **初始用户名** (通常是 `root`)
*   **初始密码**

你还需要一个SSH客户端工具。如果你使用的是macOS或Linux，可以直接使用系统自带的“终端”(Terminal)。如果你使用的是Windows，推荐使用 [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701) (内置SSH) 或经典的 [PuTTY](https://www.putty.org/) 。或者VSCode的[Remote-SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)。

### [#](#首次登录与更新系统) 首次登录与更新系统

首先，我们以`root`用户身份登录到服务器。`root`是Linux系统中的超级管理员，拥有最高权限。

```
ssh root@你的服务器IP地址 
```

连接过程中，系统可能会询问你是否信任该主机的指纹，输入`yes`并回车。接着，输入你的**初始密码**。成功登录后，你将看到服务器的命令行欢迎信息。

```
# 查看系统基本信息
uname -a 
```

**登录后的首要任务是更新系统。**  这可以确保所有已安装的软件包都打上了最新的安全补丁。

```
# 更新软件包列表信息
sudo apt update

# 升级所有已安装的软件包
sudo apt upgrade -y 
```

这里的 `-y` 参数会自动确认所有升级提示，节省时间。

### [#](#创建新用户并授予管理员权限) 创建新用户并授予管理员权限

一直使用`root`用户操作服务器是一个非常危险的习惯。任何误操作都可能对系统造成毁灭性打击，并且它也是黑客们最喜欢攻击的目标。因此，我们需要创建一个新的日常使用账户，并赋予它`sudo`权限（即在需要时临时获取管理员权限）。

1.  **创建一个新用户** (将 `your_username` 替换为你想要的用户名):
    
    ```
    adduser your_username 
    ```
    
    系统会提示你设置新用户的密码和一些可选的个人信息（可以直接回车跳过）。请务必设置一个**强密码**。
    
2.  **授予`sudo`权限**:
    
    ```
    usermod -aG sudo your_username 
    ```
    
    这条命令将新创建的用户添加到了`sudo`用户组，使其能够执行管理员命令。
    
3.  **验证新用户**: 现在，退出`root`登录 (`exit`)，然后用你的新用户名重新登录：
    
    ```
    ssh your_username@你的服务器IP地址 
    ```
    
    登录后，尝试执行一个需要`sudo`的命令来验证权限是否生效，比如更新软件包列表：
    
    ```
    sudo apt update 
    ```
    
    系统会要求你输入你自己的密码（而不是root密码）。如果命令成功执行，说明权限配置正确。
    

### [#](#加固ssh服务-提升安全性) 加固SSH服务，提升安全性

SSH是我们远程管理服务器的唯一入口，保护好它至关重要。

1.  **禁用`root`用户远程登录**: 既然我们已经有了`sudo`用户，就应该禁止`root`直接通过SSH登录。 用你喜欢的文本编辑器（如 `nano` 或 `vim`）打开SSH配置文件。`nano`对新手更友好。
    
    ```
    sudo nano /etc/ssh/sshd_config 
    ```
    
    在文件中找到 `PermitRootLogin` 这一行，修改为 `no`：
    
    ```
    PermitRootLogin no 
    ```
    
    如果这一行前面有 `#`，请将 `#` 删除。
    
2.  **(强烈推荐) 更改默认SSH端口**: SSH默认使用22端口，这使得它成为自动化扫描和攻击的首要目标。通过更改端口，可以有效避开大部分的自动攻击。 在同一个配置文件 (`/etc/ssh/sshd_config`) 中，找到 `#Port 22` 这一行。首先去掉 `#`，然后将 `22` 改成一个不常用的端口号（范围建议在 1024-65535 之间，例如 `2255`）。
    
    ```
    Port 2255 
    ```
    
    **重要提示**: 在修改端口后，请务必先配置好防火墙（下一步）并允许新端口通过，否则你可能会将自己锁在服务器外面！
    
3.  **应用更改**: 保存文件并退出 (`nano`中按 `Ctrl+X`, 然后按 `Y`, 最后按回车)。接着，重启SSH服务让配置生效。
    
    ```
    sudo systemctl restart sshd 
    ```
    
    **不要立即关闭当前的SSH连接！** 打开一个新的终端窗口，尝试用**新的端口**和**新的用户名**登录，确保一切正常。
    
    Bash
    
    ```
    ssh -p 新端口号 your_username@你的服务器IP地址
    # 示例: ssh -p 2255 your_username@192.0.2.1 
    ```
    
    确认新连接成功后，再关闭旧的连接。
    

### [#](#配置基础防火墙) 配置基础防火墙

防火墙是服务器的第一道防线。UFW (Uncomplicated Firewall) 是一个非常易于使用的防火墙管理工具，使用系统底层的`iptables`进行设置。

1.  **安装UFW** (通常已预装):
    
    ```
    sudo apt install ufw 
    ```
    
2.  **设置默认规则**: 先禁止所有传入连接，允许所有传出连接。这是一个安全的基准。
    
    ```
    sudo ufw default deny incoming
    sudo ufw default allow outgoing 
    ```
    
3.  **允许必要的连接**: 我们需要允许SSH、HTTP和HTTPS的流量进入。
    
    *   如果你没有改SSH端口：
        
        ```
        sudo ufw allow ssh # 22端口 
        ```
        
    *   如果你改了SSH端口 (例如 `2233`)：
        
        ```
        sudo ufw allow 2233/tcp 
        ```
        
    *   如果你计划部署网站，也需要允许HTTP和HTTPS：
        
        ```
        sudo ufw allow http  # 80端口
        sudo ufw allow https # 443端口 
        ```
        
4.  **启用防火墙**:
    
    ```
    sudo ufw enable 
    ```
    
    系统会警告你这可能会中断现有连接，输入`y`确认。因为我们已经允许了SSH端口，所以连接不会中断。
    
5.  **检查防火墙状态**:
    
    ```
    sudo ufw status verbose 
    ```
    
    这将显示所有规则和防火墙的当前状态。
    

### [#](#安装fail2ban防御工具) 安装Fail2ban防御工具

[Fail2ban](https://fail2ban.readthedocs.io/en/latest/)，顾名思义是防止后台暴力扫描的软件，通过分析系统日志中的异常行为（如多次登录失败），自动封禁可疑 IP 地址，有效抵御暴力破解攻击。推荐安装

安装`Fail2ban`：

```
sudo apt update && sudo apt install fail2ban 
```

### [#](#配置-fail2ban) **配置 Fail2ban**

1.  **创建自定义配置** 复制默认配置文件：
    
    ```
    sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local 
    ```
    
2.  **编辑配置文件**
    
    ```
    sudo nano /etc/fail2ban/jail.local 
    ```
    
    常见配置参数：
    
    ```
    [DEFAULT]
    ignoreip = 127.0.0.1/8  # 白名单IP
    bantime = 3600          # 封禁时长（秒）
    findtime = 600          # 检测时间段（秒）
    maxretry = 5            # 最大尝试次数
    
    [sshd]                  # SSH服务配置
    enabled = true          # 启用监控 
    ```
    
3.  **重启服务**
    
    ```
    sudo systemctl restart fail2ban
    sudo systemctl enable fail2ban  # 开机自启 
    ```
    

查看一下状态：

```
sudo fail2ban-client status 
```

检查封禁列表：

```
sudo fail2ban-client status sshd 
```

### [#](#设置系统时间) 设置系统时间

将系统时间设置为北京时间，推荐使用 `timedatectl` 命令。

北京时间的正确时区标识符是 Asia/Shanghai。您看到的错误消息是因为该工具要求使用较旧、不太常见的 POSIX 格式，但现代系统使用 Area/Location 格式。

这是大多数现代 Linux 发行版（如 Ubuntu、Debian、CentOS 和 Fedora）的标准系统范围方法。

1.  设置时区
    
    在您的终端中运行以下命令。您可能需要 sudo 权限。
    
    ```
    sudo timedatectl set-timezone Asia/Shanghai 
    ```
    
2.  验证更改
    
    您可以通过运行以下任一命令来检查更改是否成功：
    
    ```
    timedatectl 
    ```
    
    这将向您显示本地时间、世界标准时间 (UTC) 和当前设置的时区。
    
    或者简单地：
    
    ```
    date 
    ```
    
    输出现在应该显示 CST（中国标准时间）和正确的时间。
    

* * *

### [#](#使用ssh密钥登录) 使用SSH密钥登录

远程管理服务器的**标准做法**，它比密码登录更安全、更便捷。下面是一份详尽的指南，将带你完成从生成密钥到实现免密登录的全过程。

这个过程分为两个主要步骤：

1.  **在你的本地电脑（客户端）上生成密钥对**。
2.  **将公钥上传到你的服务器（服务端）**。

* * *

#### [#](#_1、在你的本地电脑上生成ssh密钥对) 1、在你的本地电脑上生成SSH密钥对

你需要先在自己的电脑（而不是服务器）上操作。密钥对由一个**私钥**和一个**公钥**组成：

*   **私钥 (`id_ed25519`)**: 必须严格保密，留存在你的本地电脑上，相当于你的“身份证明”。
*   **公钥 (`id_ed25519.pub`)**: 可以安全地分享，需要被放置在你想登录的服务器上，相当于一把“锁”。

1.  **打开终端**
    
    *   **macOS / Linux**: 打开“终端” (Terminal) 应用。
    *   **Windows**: 打开 [Windows Terminal](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701), PowerShell, 或 Git Bash。
2.  运行密钥生成命令
    
    我们使用 ssh-keygen 命令来生成密钥。推荐使用现代且安全的 Ed25519 算法。
    
    Bash
    
    ```
    ssh-keygen -t ed25519 -C "your_email@example.com" 
    ```
    
    *   `-t ed25519`: 指定密钥类型为 Ed25519。如果你的系统很老不支持，可以换成 `rsa -b 4096`。
    *   `-C "your_email@example.com"`: 添加一段注释，通常用邮箱来标识这个密钥是谁的、用在哪台电脑上，方便管理。
3.  根据提示操作
    
    运行命令后，系统会问你几个问题：
    
    *   Enter file in which to save the key (...):
        
        提示你保存密钥的位置。直接按回车即可，它会使用默认路径（通常是 ~/.ssh/id\_ed25519）。
        
    *   Enter passphrase (empty for no passphrase)::
        
        提示你为私钥设置一个密码（Passphrase）。这是一个非常重要的安全层！
        
        *   **强烈建议设置密码**: 即使你的电脑被盗，私钥文件泄露，没有这个密码，别人也无法使用它。
        *   **不设置密码**: 直接按回车。登录时会更方便，但安全性稍低。
    *   Enter same passphrase again::
        
        再次输入你设置的密码进行确认。
        
    
    完成后，你会在 `~/.ssh` 目录下看到两个新文件：`id_ed25519` (私钥) 和 `id_ed25519.pub` (公钥)。
    

#### [#](#_2、将你的公钥复制到服务器) 2、将你的公钥复制到服务器

要实现免密登录，你需要把刚刚生成的**公钥** (`id_ed25519.pub`) 的内容，添加到服务器上你希望登录的那个用户的 `~/.ssh/authorized_keys` 文件中。

以下介绍两种方法，**强烈推荐使用方法A**。

#### [#](#方法-1-使用-ssh-copy-id-最简单、最推荐) 方法 1：使用 `ssh-copy-id` (最简单、最推荐)

这个命令会自动完成所有操作，包括在服务器上创建目录、设置文件和修正权限，能有效避免手动操作的失误。

1.  执行命令
    
    将 your\_username 替换成你在服务器上的用户名，server\_ip 替换成服务器的IP地址。
    
    Bash
    
    ```
    ssh-copy-id your_username@server_ip 
    ```
    
    *   如果你修改过SSH端口，可以使用 `-p` 参数：`ssh-copy-id -p 端口号 your_username@server_ip`
    *   如果你的密钥不在默认路径，可以使用 `-i` 参数：`ssh-copy-id -i ~/.ssh/my_other_key.pub your_username@server_ip`
2.  输入服务器密码
    
    系统会提示你输入 your\_username 这个用户在服务器上的密码。这是你最后一次需要用密码登录。
    
    输入密码后，命令会自动将你的公钥内容追加到服务器的 `~/.ssh/authorized_keys` 文件中。
    

#### [#](#方法-2-手动复制粘贴-当没有ssh-copy-id时) 方法 2：手动复制粘贴 (当没有`ssh-copy-id`时)

如果你的本地电脑（比如某些Windows环境）没有 `ssh-copy-id` 命令，就需要手动操作。

1.  **在本地电脑上，显示并复制公钥内容**
    
    ```
    cat ~/.ssh/id_ed25519.pub 
    ```
    
    终端会显示一长串以 `ssh-ed25519 ...` 开头的文本。**完整地复制这一整行**。
    
2.  **用密码登录到你的服务器**
    
    ```
    ssh your_username@server_ip 
    ```
    
3.  在服务器上，将公钥写入 authorized\_keys 文件
    
    登录服务器后，执行以下命令：
    
    ```
    # 确保 .ssh 目录存在
    mkdir -p ~/.ssh
    
    # 将你复制的公钥内容粘贴到这里，然后回车
    echo "在这里粘贴你的公钥内容" >> ~/.ssh/authorized_keys
    
    # 修正关键的目录和文件权限，这一步至关重要！
    chmod 700 ~/.ssh
    chmod 600 ~/.ssh/authorized_keys 
    ```
    
    **注意**: 如果权限不正确（例如过于开放），SSH为了安全会拒绝使用密钥登录。`700`意味着只有你自己能读、写、执行该目录，`600`意味着只有你自己能读、写该文件。
    

还可以使用一些SSH客户端（如[XShell](https://www.xshell.com/en/xshell/)、[MobaXterm](https://mobaxterm.mobatek.net/)）能直接在客户端里面生成本地的密钥对，生成后能直接一键导入到服务器中，也是非常方便。 像 [Termius](https://termius.com/) 这样能够云端同步的SSH客户端能够让你在不同设备上使用同一套密钥对，每次换不同设备，都不再需要重新生成密钥并添加到服务器里，有着极大的便利性还能集中管理多个和VPS和密钥信息。不过_**如果你的账号验证信息被泄露，那么你的全部密钥都遭殃，VPS也都能被访问**_。

#### [#](#_3、测试与收尾) 3、测试与收尾

1.  测试免密登录
    
    退出服务器 ，然后再次尝试登录：
    
    ```
    ssh your_username@server_ip 
    ```
    
    如果一切顺利，系统会直接让你登录，而不会再询问密码。如果你设置了密钥的密码（Passphrase），此时会提示你输入该密码。
    
2.  (重要) 禁用密码登录
    
    确认密钥登录成功后，为了达到最高的安全性，应该在服务器上禁用密码登录，只允许密钥登录。
    
    *   在服务器上编辑SSH配置文件：
        
        ```
        sudo nano /etc/ssh/sshd_config 
        ```
        
    *   找到 `PasswordAuthentication` 这一行，去掉前面的 `#`，并把值改为 `no`。
        
        ```
        PasswordAuthentication no 
        ```
        
    *   同时，可以确认 `PubkeyAuthentication` 是 `yes` (通常默认就是)。
        
    *   保存文件 (`Ctrl+X`, `Y`, `Enter`) 并重启SSH服务。
        
        ```
        sudo systemctl restart sshd 
        ```
        

**警告**：在执行这一步之前，**务必确保你的密钥登录已经测试成功**。否则，一旦禁用密码登录，你将无法再登入你的服务器！

现在，你的服务器就配置好了高度安全的密钥登录方式。

### [#](#安装docker和docker-compose服务) 安装docker和docker compose服务

使用官方的一键安装[脚本](https://github.com/docker/docker-install)安装。

安装脚本的目的是为了方便在受支持的 Linux 发行版上快速安装最新的 Docker-CE 版本。不建议依赖此脚本来部署到生产系统。有关在受支持的发行版上安装的更详细说明，请参阅[安装说明](https://docs.docker.com/engine/install/)。

你只需运行以下两条命令，即可完成所有安装。

```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh 
```

脚本运行完毕后，Docker 和 Docker Compose 就安装好了。

测试下自己的VPS有没有安装好Docker了：

```
which docker # /usr/bin/docker 
```

为了能不加 `sudo` 直接运行 Docker 命令，你仍需要执行一次用户权限设置：

```
# 将当前用户添加到 docker 用户组
sudo usermod -aG docker $USER 
```

最后，看一下`docker`和`docker compose`的版本：

```
docker --version # Docker version 28.3.2, build 578ccf6
docker compose version # Docker Compose version v2.38.2 
```

好了，大部分人使用VPS来部署服务都是使用docker来部署，比如WordPress等等，但是使用docker部署完，一般都是“IP+端口号”的方式来访问，这种方式不仅暴露了服务器的内部细节，显得不专业，还存在安全隐患。所以使用Nginx反向代理是必不可少的一步。通过将所有服务流量统一由Nginx进行转发，我们可以极大地提升部署的专业性、安全性与灵活性。我们只需要开一个端口，就能访问所有的VPS服务进程。

这里我们用NPM（[Nginx Proxy Manager](https://nginxproxymanager.com/)）来统一管理Nginx代理配置、Let’s Encrypt的SSL证书自动申请和续期。

1、首先我们创建安装目录

```
# 创建并进入目录
mkdir ~/docker/npm && cd ~/docker/npm 
```

2、创建`compose.yml`文件

```
# 创建compose文件
nano compose.yml 
```

3、复制内容下面内容并粘贴到文件中，这个81端口是NPM的默认后台端口，建议修改为你自己想要的。

```
services:
  app:
    image: 'jc21/nginx-proxy-manager:latest'
    restart: unless-stopped
    ports:
      - '80:80'
      - '81〈这个就是你要暴露到公网上的端口〉:81'
      - '443:443'
    volumes:
      - ./data:/data
      - ./letsencrypt:/etc/letsencrypt 
```

4、后台运行docker compose启动容器

```
docker compose up -d 
```

访问你的公网IP地址，会显示一个NPM的祝贺成功页面，代表安装Nginx成功了。访问公网IP:81进入网页，进行初始化。

接下来你需要有一个域名，我的在域名托管在Cloudflare上，其它域名服务商应该也是类似的。在Cloudflare上对域名进行DNS解析，自定义一个三级域名比如npm用来访问NPM后台页面，npm.domain.com指向你的服务器IP地址。然后我们让NPM反向代理自己，当访问npm.domain.com域名时，NPM会转发流量到内部网络进行访问。

我们创建Let’s Encrypt的SSL证书，打开NPM后台页面，点击SSL Certificates，add SSL Certificate -> Let’s Encrypt -> 然后添加三级域名 `*.domain.com`和二级域名`domain.com` -> Use a DNS Challenge然后选择你的DNS提供商填入域名密钥保存就行。申请成功后添加代理的时候就能在SSL那里选择证书了。

**默认配置下，Docker的暴露的端口规则会与UFW的规则冲突**。它们通过直接修改底层的`iptables`规则来暴露端口，所以docker创建的端口不被UFW防火墙所限制。如果你会使用iptables就不需要使用UFW，直接用iptables进行防火墙配置。通过修改iptables也能进行让docker所暴露的端口受UFW所限制，但是我们这里使用一种更简单的方法，就是让NPM通过访问不同docker容器的内部IP来进行代理，我们创建docker容器的时候不需要暴露到公网，只需要让NPM与其他容器在同一docker网络下就行。

这里我们用Portainer来进行演示，将 Portainer 加入了 `npm_default` 网络，通过同样连接到这个网络的反向代理NPM来访问 Portainer 的 Web 界面。

1、首先我们创建安装目录

```
mkdir ~/docker/portainer && cd ~/docker/portainer 
```

2、创建如下`compose.yml`文件，然后后台运行compose。这里不需要添加端口映射关系，容器使用NPM创建的默认网络`npm_default`。

```
services:
  portainer:
    image: portainer/portainer-ce:latest
    container_name: portainer
    restart: always
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - ./portainer_data:/data
    networks:
      - npm_default 
networks:
  npm_default:
    external: true 
```

查看的容器的名称或ID：

```
docker ps 
```

然后，使用 `inspect` 命令。假设容器名叫 `portainer`：

```
docker inspect portainer 
```

这会输出一大段JSON格式的信息。您需要滚动到最下面的 `Networks` 部分，在那里可以看到它在不同网络中的IP地址。

可以使用 `--format` 标志来只提取IP地址，这样更清晰。

```
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' portainer 
```

这样就获取到了容器的内部IP了，于是我们可以在NPM中对IP进行代理，我们使用portainer.domain.com来访问页面，Scheme使用http，IP输入刚刚获取的容器IP比如`172.18.0.3`，端口输入9000。SSL选择刚刚的证书`*.domain.com`，选择Force SSL进行强制SSL访问然后保存。这样就可以通过域名来访问Portainer后台了。

通过下面命令来查看`npm_default`网络下的全部信息。

```
docker network inspect npm_default 
```

这样其他的docker服务都可以按照这个方法通过NPM来反向代理进行访问了。

[Edit this page on GitHub](https://github.com/Mrzhuo2022/Mrzhuo2022.github.io/edit/main/blog/posts/2025-07-18-new-VPS-guide.md)

Last Updated: 7/26/2025, 7:07:32 AM

[Previous  
使用so-vits-svc进行语音模型训练](/post/2023/11/30/so-vits-svc-doc/)[Next  
关系型数据库三巨头：PostgreSQL、MySQL和SQLite全方位深度解析](/post/2025/08/08/postgresql-mysql-sqlite-rdb/)

*   拿到新的小鸡（VPS）后，你应该先做什么？
*   准备工作
*   首次登录与更新系统
*   创建新用户并授予管理员权限
*   加固SSH服务，提升安全性
*   配置基础防火墙
*   安装Fail2ban防御工具
*   配置 Fail2ban
*   设置系统时间
*   使用SSH密钥登录
*   1、在你的本地电脑上生成SSH密钥对
*   2、将你的公钥复制到服务器
*   方法 1：使用 ssh-copy-id (最简单、最推荐)
*   方法 2：手动复制粘贴 (当没有ssh-copy-id时)
*   3、测试与收尾
*   安装docker和docker compose服务

1%

©2023 [Evarle](#)  
Powered by [VuePress](https://v2.vuepress.vuejs.org) & [Gungnir](https://github.com/Renovamen/vuepress-theme-gungnir)

↑↓⇔⇧⇩