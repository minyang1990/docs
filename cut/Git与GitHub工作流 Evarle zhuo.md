# Git与GitHub工作流 | Evarle zhuo
[Git与GitHub工作流 | Evarle zhuo](https://evarle.top/post/2023/09/03/git-and-github/) 

       Git与GitHub工作流 | Evarle zhuo

Constants loaded at 2025-08-11T15:12:51.267Z

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

Git与GitHub工作流
=============

Git Github workflow 开源 互联网

Evarle

2023-09-03

42 min

Git的学习笔记，用Git工作和开发太舒服和高效了，配合远程仓库使用。Github的各项免费服务真不错，比如Github Actions。

* * *

[#](#什么是git) 什么是Git
-------------------

Git是一种分布式版本控制系统，用于跟踪和管理软件开发项目中的代码变化。它由Linus Torvalds在2005年创建，并广泛用于管理代码的版本控制、协作开发和代码托管。

Git的主要目标是提供一种轻量级、快速和灵活的版本控制系统，适用于各种规模的项目。与传统的集中式版本控制系统（如SVN）不同，Git是一种分布式系统，每个开发者都可以在本地拥有完整的代码仓库。

为什么是**Git**，以下是传统的集中式版本控制系统_Subversion_（SVN）与分布式版本控制系统_Git_的对比：

|  | SVN | Git |
| --- | --- | --- |
| 类型 | 集中式版本控制系统 | 分布式版本控制系统 |
| 分支和合并 | 较为复杂，需要中央服务器的支持 | 简单且灵活，支持本地分支和合并 |
| 存储方式 | 存储完整的文件副本 | 存储差异增量文件，节省存储空间 |
| 历史记录 | 记录整个项目的历史变化 | 每个本地仓库都具有完整的历史记录 |
| 远程访问 | 需要网络连接，并与中央服务器进行交互 | 可在本地操作，无需网络连接 |
| 性能 | 在处理大型项目和大量历史记录时性能较慢 | 处理速度快，尤其在本地操作和分支切换方面 |
| 分布式 | 不支持分布式开发 | 支持分布式开发，允许离线工作和并行开发 |
| 异地协作 | 需要依赖中央服务器，对网络连接依赖较高 | 可以独立工作，允许异地和离线协作 |
| 整体设计 | 相对较简单，容易上手 | 学习曲线较陡峭，需要一定的时间和经验 |
| 社区支持 | 较为成熟且广泛应用 | 非常活跃的社区支持，有大量的文档、工具和资源可用 |

Git之所以成为首选的版本控制系统，是因为它的分布式性质、高效性、强大的分支和合并支持，以及广泛的社区支持。这些特点使得Git能够满足现代软件开发的需求，提供协作、版本管理和代码控制的强大功能。

[#](#git的安装和使用) Git的安装和使用
-------------------------

Git的安装地址：https://git-scm.com/downloads

Git官方中文文档(Pro Git)：https://git-scm.com/book/zh/v2

Git菜鸟教程：https://www.runoob.com/git/git-tutorial.html

### [#](#git的结构组成) Git的结构组成

在Git中，有三个关键概念：工作区（Working Directory），暂存区（Staging Area）和版本库（Repository）。

![](https://evarle.top/img/in-post/2023-09-03/GitDiagram.png)

它们之间的关系可以描述如下：

1.  **工作区（Working Directory）**：工作区是你当前项目的目录，其中包含实际的代码文件和目录。你对工作区进行的所有修改（如添加、编辑和删除文件）都直接反映在工作区中。
2.  **暂存区（Staging Area）**：暂存区是一个中间区域，位于Git仓库内部。它是一个用于暂时存放修改的地方，你可以将工作区的文件添加到暂存区中，准备将它们作为一组更改提交到版本库。通过使用`git add`命令，你可以将工作区的修改添加到暂存区。
3.  **存储库（Repository）**：存储库是Git仓库的核心部分，它存储了项目的完整历史记录和元数据。存储库包含了所有的提交记录，每个提交都是代码更改的快照。当你执行`git commit`命令时，暂存区中的修改会被提交到存储库，创建一个新的提交。

你的本地仓库由 git 维护的三个部分组成。第一个是你的 `工作目录`，它持有实际文件，也就是你在电脑里看到的目录；第二个是 `暂存区（Index或者Stage）`，它像个缓存区域，临时保存你的改动，一般存放在 **.git** 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）；最后是`HEAD`，它是一个指针，它指向你最后一次提交的结果或者你所处分支的最后一次提交结果，表示当前工作树的位置。

### [#](#常用的git命令) 常用的Git命令

以下是一些常用的Git命令，可以帮助你在团队协作中使用Git：

*   **git init**：初始化（创建）一个新的Git仓库。
    
    > 初始化文件夹后，会生成一个.git文件，所有git相关的内容都在.git里面，包括添加操作记录、仓库信息、远程仓库等等。
    
*   **git clone \[repository\]**：从远程仓库克隆一个副本到本地。
    
    > 执行如下命令以创建一个本地仓库的克隆版本：
    > 
    > `git clone /path/to/repository`
    > 
    > 如果是远端服务器上的仓库：
    > 
    > `git clone username@host:/path/to/repository`
    > 
    > 或者是从云端远程仓库克隆：
    > 
    > `git clone https://github.com/user/repository.git`
    
*   **git config** --list：显示当前的git配置信息(.gitconfig文件)。
    
    > 编辑所有仓库配置文件：
    > 
    > `git config --global -e` # --global表示系统上所有仓库
    > 
    > 设置提交代码时的用户信息：
    > 
    > git config --global user.name "yourname"
    > 
    > git config --global user.email user@email.com
    
*   **git add \[file\]**：将文件添加到Git的暂存区。
    
    > 将当前目录下所有文件添加到暂存区:
    > 
    > `git add .`
    
*   **git commit -m \[message\]**：将暂存区的文件提交到本地仓库，并附上一条提交说明。
    
    > 在Git中，提交(commit)是将代码更改永久记录到版本控制历史中的操作。为了保持代码库的清晰和易于维护，使用[**规范化**](https://www.conventionalcommits.org/zh-hans/v1.0.0/)的提交风格是一个良好的实践。以下是一种常用的Git提交规范风格，称为"Conventional Commits"（常规提交）：
    > 
    > 每个提交消息由三个部分组成：类型(Type)、范围(Scope)和描述(Description)。
    > 
    > ```
    > <type>(<scope>): <description>
    > 
    > [可选的正文部分]
    > 
    > [可选的脚注部分] 
    > ```
    > 
    > 以下是每个部分的解释：
    > 
    > 1.  **类型(Type)**：表示提交的目的或种类。常见的类型包括：
    > 
    > *   `feat`：新功能（feature）
    > *   `fix`：修复Bug
    > *   `docs`：文档变更
    > *   `style`：代码风格调整（不影响代码功能）
    > *   `refactor`：代码重构（既不修复Bug也不添加新功能）
    > *   `test`：添加或修改测试
    > *   `chore`：构建过程或辅助工具的变动
    > 
    > 1.  **范围(Scope)**：表示提交的影响范围，可以是文件、模块、组件等。范围是可选的，但对于大型项目或多个团队成员协作开发的项目，指定范围能够更清楚地标识提交所涉及的部分。
    > 2.  **描述(Description)**：简明扼要地描述了提交所做的更改。描述应该清晰、具体，并使用现在时态。避免使用过于模糊的描述，要尽量准确传达提交的目的和意图。
    > 
    > 可选的正文部分和脚注部分可以用于提供更详细的信息，例如为什么进行了这个更改、解决了什么问题等。
    > 
    > 具体的提交规范风格可能因团队、项目或个人而有所不同。重要的是在团队内部达成一致，并坚持使用统一的风格。
    
*   **git remote -v**：显示Git远程仓库。
    
*   **git push**：将本地仓库的提交推送到远程仓库。
    
*   **git pull**：从远程仓库拉取最新的更改到本地仓库。
    
*   **git fetch**：获取远程仓库的最新提交和分支信息
    
*   **git branch**：列出所有分支，包括本地和远程分支。
    
    > 新建分支feature\_x：
    > 
    > `git branch feature_x`
    > 
    > 删除分支feature\_x：
    > 
    > `git branch -d feature_x`
    
*   **git checkout \[branch\]**：切换到指定的分支。
    
    > 创建并切换到新分支feature\_x：
    > 
    > `git checkout -b feature_x`
    > 
    > 切换回主分支：
    > 
    > `git checkout master`
    > 
    > 切换到某个commit id：
    > 
    > `git checkout commitid`
    > 
    > 另外新版本git强烈建议采用新的**switch**命令用来接替checkout的功能：
    > 
    > `git switch feature_x` # 切换到feature\_x分支
    > 
    > `git switch -c feature_x` # 创建并切换到feature\_x分支
    
*   **git merge \[branch\]**：将指定分支的更改合并到当前分支。
    
*   **git status**：显示仓库当前状态，显示有关已修改的文件、新增的文件、已删除的文件以及提交的状态信息。
    
    > `git status -s` # 输出简短的信息结果
    
*   **git diff**：显示当前分支与上一次提交之间的差异。
    
*   **git log**：显示版本库中的提交历史记录，按照时间顺序列出所有提交记录。
    
    > 默认情况下，`git log`会以以下方式显示每个提交记录的信息：
    > 
    > *   **提交哈希值**（Commit Hash）：每个提交都有一个唯一的哈希值（也就是commit id，用于标识该提交。
    > *   **作者**（Author）：提交的作者。
    > *   **提交日期**（Date）：提交的日期和时间。
    > *   **提交信息**（Commit Message）：对该次提交的描述信息。
    > 
    > `git log -n 5` # 显示最近的5个提交记录。
    > 
    > `git log --author="Evarle"` # 显示由"Evarle"提交的记录。
    > 
    > `git log --since="2023-07-01"` # 显示从"2023-07-01"开始的提交记录。
    > 
    > `git log --oneline` # 以简洁的单行格式显示提交记录。
    
*   **git tag**：用于管理和操作标签。
    
    > `git tag` # 列出所有标签
    > 
    > `git tag -a <tagname> -m "Tag message"` # 创建标签并打上注释
    > 
    > `git show <tagname>` # 查看特定标签的详细信息
    > 
    > `git tag -d <tagname>` # 删除标签
    
*   **git stash**：将当前的修改储藏起来，以便稍后恢复。
    
*   **git reset \[commit\]**：将HEAD指针指向指定的提交，并将之后的提交移除。
    
    > `git reset HEAD` # 撤销暂存区的修改，保持工作区不受影响（HEAD表示当前版本，HEAD~1表示上一个版本）
    > 
    > `git reset --hard HEAD` # 撤销暂存区和工作区中的所有修改，并回到最近一次提交的状态
    

_Git操作犯错了怎么办，可以查看这个有趣的文档：[OhShit,Git!?!](https://dangitgit.com/zh)_

Git学习小游戏：https://learngitbranching.js.org/?locale=zh\_CN

[#](#git工作流) Git工作流
-------------------

### [#](#git项目生命周期) Git项目生命周期

当涉及到团队协作和版本控制时，Git是一个非常强大和流行的工具。Git提供了一种灵活的工作流程，可以帮助团队有效地协同工作并跟踪代码的变化。

以下是一种常见的工作流程模型：

1.  **创建分支（Branching）**：团队成员从主分支（通常是`master`或`main`分支）创建新的分支来开展工作。这种方式可以让团队成员在不影响主分支的情况下进行独立的开发。
    
2.  **开发（Development）**：团队成员在各自的分支上进行开发工作。每个成员可以根据任务或特性在自己的分支上进行独立的编码工作。
    
3.  **合并（Merging）**：当一个成员完成了自己的开发工作，并确保代码没有错误，可以将自己的分支合并到主分支中。这可以通过执行合并命令来完成。
    
4.  **解决冲突（Resolving Conflicts）**：当两个分支的修改冲突时，需要手动解决冲突。Git会在合并操作中标识出冲突的文件，并提供工具来解决冲突。
    
5.  **代码审查（Code Review）**：在将分支合并到主分支之前，团队成员可以进行代码审查，以确保代码的质量和一致性。这可以通过查看差异、提出建议和讨论来完成。
    
6.  **部署（Deployment）**：一旦代码合并到主分支，可以将其部署到生产环境中进行测试和运行。
    

*   [**Git工作流程图**](https://ivanzz1001.github.io/records/post/tools/2018/01/27/git-workflow)：

![](https://evarle.top/img/in-post/2023-09-03/git_workflow.png)

### [#](#git-flow) Git Flow

在Git中，工作流程（Workflow）是指在项目开发过程中如何使用Git来管理代码的流程和组织方式。Git流（Git Flow）是一种常见的Git工作流程模型如下：

1.  **主分支（Master Branch）**：主分支通常被称为`master`或`main`，用于存储稳定、可部署的代码。在该分支上的代码应始终保持可用状态，并且应该仅包含已经完成并通过测试的代码。
2.  **开发分支（Develop Branch）**：从主分支派生的开发分支，通常被称为`develop`。开发分支是进行日常开发工作的主要分支。团队成员在该分支上进行功能开发、Bug修复和其他修改。
3.  **功能分支（Feature Branches）**：每个新功能或任务通常都会从开发分支创建一个单独的功能分支。功能分支通常根据任务的名称或功能的性质进行命名。开发人员在功能分支上独立进行开发，并在完成后将其合并回开发分支。
4.  **发布分支（Release Branches）**：当开发达到一定的里程碑或准备进行新的发布时，可以从开发分支创建一个发布分支。在发布分支上进行最后的测试、修复漏洞、准备文档等操作。一旦准备就绪，发布分支将合并回主分支，并在合并时创建一个标签（Tag）。
5.  **修复分支（Hotfix Branches）**：当在主分支上发现紧急Bug或需要立即修复的问题时，可以创建一个修复分支。修复分支通常从主分支派生，进行修复工作后，将其合并回主分支和开发分支。

下图展示了Git Flow工作流的典型图示：

```
 ┌─────────── Feature branches (New features)
       ↓
┌───── Develop branch (Integration and development)
│      ↓
│  ┌─── Release branches (Preparing for new releases)
│  ↓   ↓
│  ┌─── Master branch (Stable, production-ready code)
│  ↓
└─── Hotfix branches (Urgent bug fixes) 
```

*   [**Git Flow流程图**](https://fatindeed.gitbooks.io/knowledge-base/content/topic/workflow/git-work-flow.html)：

![](https://evarle.top/img/in-post/2023-09-03/cdraw.png)

请注意，Git Flow是一种常见的工作流程模型，但并不是唯一可行的方式。根据团队的需求和项目的特点，可以根据实际情况进行定制和调整。还有其他工作流程模型，如GitHub Flow、GitLab Flow等，也是非常流行和有效的。

选择适合团队和项目的工作流程模型，并确保团队成员熟悉并遵守所采用的工作流程，可以提高代码管理的效率和协作的质量。

[#](#git与github) Git与Github
---------------------------

### [#](#什么是github) 什么是github

GitHub是全球最大的~同性交友~开源代码托管平台，它是一个基于Git的代码托管平台和协作开发社区，为开发者提供了许多功能和工具，以支持代码管理、协作和项目管理，在全球范围内拥有庞大的用户群体和活跃的开发者社区，成为许多开发者首选的开源平台。

GitHub的官方文档：https://docs.github.com/zh

推荐阅读：[GitHub 漫游指南](https://github.phodal.com/#/chapter/Github%E6%BC%AB%E6%B8%B8%E6%8C%87%E5%8D%97)、[开源指北](https://oschina.gitee.io/opensource-guide/)

* * *

很多人可能会混淆 **Git** 和代码托管平台（如**GitHub**、GitLab、Gitee等）的概念。Git 是版本控制系统，开发者可以通过 Git 在本地工作空间建立项目仓库，可以拉取远程仓库来进行本地的工作，Git可以说是一款软件，它是一种工具用来进行代码的管理和操作。

而代码托管平台则是基于Git的平台，通过网络为用户提供Git仓库托管服务。它是一种服务，是Git的远程仓库，也是开发者用于协作的开发社区。

GitHub是一个基于Web的Git版本控制存储库托管服务。它提供了Git的所有分布式版本控制和源代码管理（SCM）功能。

|  | Git | GitHub |
| --- | --- | --- |
| 定义 | Git是一种分布式版本控制系统，用于跟踪和管理代码的变化 | GitHub是一个基于Git的代码托管平台和协作开发社区 |
| 类型 | 版本控制系统 | 代码托管平台和协作开发社区 |
| 功能 | 跟踪和管理代码的变化，包括分支、合并、提交等操作 | 提供Git代码仓库托管、版本控制、问题跟踪、协作和部署等功能 |
| 位置 | 本地计算机上安装和使用 | 通过网络访问，存储和管理远程Git仓库 |
| 协作 | 开发者可以通过手动共享Git仓库进行协作 | 提供协作开发功能，包括Pull Requests、评论和协作工具 |
| 可见性 | 代码仓库只能在本地或与其他开发者共享 | 通过GitHub平台可以公开或私有地共享代码仓库 |
| 社区 | 不涉及社区方面的功能 | 提供开发者社区、开源项目和合作机会 |

*   **Github的工作流程图：** 

![](https://evarle.top/img/in-post/2023-09-03/Version_Control.png)

### [#](#github作为git远程仓库) Github作为Git远程仓库

*   首先在你的GitHub上创建一个新的仓库，或者使用已存在的仓库。可以在GitHub的页面上点击"New"按钮来创建一个新仓库，并提供仓库的名称、描述和其他设置。
    
*   git设置系统代理：
    
    ```
    //http
    git config --global http.proxy 127.0.0.1:10101
    git config --global https.proxy 127.0.0.1:10101
    
    //sock5代理
    git config --global http.proxy socks5 127.0.0.1:10102
    git config --global http.proxy socks5 127.0.0.1:10102
    
    //查看代理
    git config --global -l
    
    //取消代理
    git config --global --unset http.proxy
    git config --global --unset https.proxy 
    ```
    
*   在你的本地环境中，使用`git clone`命令克隆GitHub上的仓库到本地计算机。
    
    ```
    git clone <github_repo_url> 
    ```
    
*   进入克隆到本地的仓库目录，并使用`git remote add`命令将GitHub仓库作为远程仓库添加到本地仓库。
    
    ```
    git remote add origin <github_repo_url> 
    ```
    
    > 这里的`origin`是你给远程仓库起的名称，你可以根据需要自定义。
    

由于你的本地 Git 仓库和 GitHub 仓库之间的传输是通过SSH加密的，所以我们需要配置验证信息：

> 关于GitHub的SSH身份验证，可以参考官方文档：[使用SSH进行连接](https://docs.github.com/zh/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

1.  首先在git bash里输入
    
    ```
    ssh-keygen -t ed25519 -C "your_email@example.com"    # 这将以你注册GitHub的邮箱地址为标签创建新SSH密钥 
    ```
    
2.  当系统提示您“Enter a file in which to save the key（输入要保存密钥的文件）”时，可以按 Enter 键接受默认文件位置。 请注意，如果以前创建了 SSH 密钥，则 ssh-keygen 可能会要求重写另一个密钥，在这种情况下，我们建议创建自定义命名的 SSH 密钥。 为此，请键入默认文件位置，并将 id\_ssh\_keyname 替换为自定义密钥名称。
    
    > Enter a file in which to save the key (/c/Users/YOU/.ssh/id\_ALGORITHM):\[Press enter\]
    
3.  成功后会在\*\*~/\*\* 下生成 **.ssh** 文件夹，进去，使用命令（或您命名的密钥）打开新创建的 .pub 密钥，复制里面的 **key**。
    
    ```
    cat ~/.ssh/id_ed25519.pub
    # 一般长这样：ssh-ed25519 ABCDEFGKSAfjksjafkjsaLJfakjJF your_github_account@example.com 
    ```
    
4.  回到你的github账号上，进入 Account Settings（账户配置），左边选择SSH Keys，Add SSH Key，填写你刚刚复制的key。
    
5.  验证是否连接成功，输入以下内容：
    
    ```
    $ ssh -T git@github.com
    # Attempts to ssh to GitHub 
    ```
    
    您可能会看到类似如下的警告：
    
    > The authenticity of host 'github.com (IP ADDRESS)' can't be established. ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU. Are you sure you want to continue connecting (yes/no)?
    
    验证所看到消息中的指纹是否与 [GitHub 的公钥指纹](https://docs.github.com/zh/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints)匹配。 如果是，则键入 `yes`：
    
    > Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access.
    

```
查看当前的远程仓库：
$ git remote
origin
$ git remote -v
origin    git@github.com:user/repo.git (fetch)
origin    git@github.com:user/repo.git (push) 
```

*   使用`git add`和`git commit`命令将更改的文件添加到暂存区，并提交到本地仓库。

```
git add <modified_files>
git commit -m "描述你的代码更改" 
```

*   将本地仓库中的更改推送到GitHub远程仓库。

```
git push origin <branch_name> 
```

这里的`branch_name`是你当前所在的分支名。

现在，你的代码更改将被推送到GitHub远程仓库，并在相应的分支上进行存储和管理。你可以在GitHub上查看提交记录、创建分支、发起Pull Request等。

* * *

一些远程操作命令：

默认情况下，提取、拉取和推送将在源存储库上运行。这将是您从中克隆或使用手动 `git branch --set-upstream-to <origin>` 设置的存储库。

`git branch -al`查看本地和远程的所有分支。

`git checkout <branch_name>` 切换分支。

`git pull`更新本地仓库。

*   执行 `git fetch origin master` 时，它的意思是从名为 **origin** 的远程上拉取名为 **master** 的分支到本地分支 **origin/master** 中。
*   执行 `git merge origin/master` 时，它的意思是合并名为 **origin/master** 的分支到当前所在分支。需要指定的是被合并的分支。
*   执行 `git push origin master` 时，它的意思是推送本地的 **master** 分支到远程 **origin**，涉及到远程以及分支，当然也得分开写了。
*   还可以一次性拉取多个分支的代码：`git fetch origin master stable oldstable`；
*   也还可以一次性合并多个分支的代码：`git merge origin/master hotfix-2275 hotfix-2276 hotfix-2290`；

### [#](#github-actions) Github Actions

GitHub官方提供了一项持续集成 (Continuous Integration, CI) 和持续部署 (Continuous Deployment, CD) 服务，它允许开发者在他们的 GitHub 存储库中设置自动化工作流程，以便在代码仓库中进行更轻松、更高效的软件开发。

> GitHub Actions 是一种持续集成和持续交付 (CI/CD) 平台，可用于自动执行生成、测试和部署管道。 您可以创建工作流程来构建和测试存储库的每个拉取请求，或将合并的拉取请求部署到生产环境。
> 
> GitHub Actions 不仅仅是 DevOps，还允许您在存储库中发生其他事件时运行工作流程。 例如，您可以运行工作流程，以便在有人在您的存储库中创建新问题时自动添加相应的标签。
> 
> GitHub 提供 Linux、Windows 和 macOS 虚拟机来运行工作流程，或者您可以在自己的数据中心或云基础架构中托管自己的自托管运行器。

GitHub提供了官方文档[GitHub Actions 文档](https://docs.github.com/zh/actions)

使用Github actions工作流进行自动化工作，工作流程在仓库的 `.github/workflows`文件夹中，在该目录创建一个 `.yml` 或者 `.yaml` 文件，Github就会在workflows目录下搜索事件的关联提交 SHA 或 Git 引用中存在的工作流文件。一个版本库可以有多个工作流，每个工作流可以执行一组不同的任务。例如，你可以有一个工作流来构建和测试拉取请求，另一个工作流在每次创建发布版本时部署应用程序，还有一个工作流在每次有人打开一个新问题时添加一个标签。

![](https://evarle.top/img/in-post/2023-09-03/reusable-workflows-ci-cd.webp)

*   一个简单的`workflow.yml`文件

```
name: # 工作流程名称

on: # 定义触发工作流程的事件
  push:  # 当代码提交到仓库时触发
    branches: [ main ] # 只有在主分支上的提交触发工作流程
  pull_request:
    branches: [ main ]

jobs: # 定义工作流程包含的工作（jobs）
  build: # 工作的名称
    runs-on: ubuntu-latest # 工作的运行环境

    env:
    	NODE_VERSION: '16'

    steps: # 定义工作包含的步骤
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v3 # 使用 GitHub 提供的 "checkout" 动作，将代码检出到工作环境
        with:
          fetch-depth: 0
          
      - name: Setup Node.js # 步骤的名称
        uses: actions/setup-node@v3
        with:
          node-version: ${{ env.NODE_VERSION }}

      - name: Install Dependencies
        run: npm install  # 在 Node.js 环境中运行 npm 安装项目依赖

      - name: Build Application
        run: npm build  # 在 Node.js 环境中运行构建应用程序的命令
		
	  - name: Deploy
        uses: peaceiris/actions-gh-pages@v3 # 把代码推送到gh-pages分支
        with:
          github_token: ${{ secrets.ACCESS_TOKEN }} # # 从GitHub仓库的Secrets中获取敏感信息，github的token令牌，使仓库有权限操作
          publish_dir: blog/.vuepress/dist
          cname: evarle.one
          
      - name: Deploy to Production
        if: github.event_name == 'push' && github.ref == 'refs/heads/main'  # 仅在代码推送到主分支时执行
        run:
           # 在此处添加部署到生产环境的命令，例如上传到服务器或云平台
           # 这个步骤只有在代码推送到主分支时才会运行 
```

当仓库被拉取或者推送时，自动按顺序执行此文件工作流程。

### [#](#你的第一个pull-request-pr) 你的第一个Pull Request(PR)

在GitHub上创建Pull Request的一般步骤：

1.  **Fork项目**：访问要贡献代码的项目页面，点击页面右上方的"Fork"按钮。这将在你的GitHub账号下创建一个该项目的副本。
    
2.  **克隆仓库**：在你的本地环境中，使用`git clone`命令克隆你在上一步中Fork的项目仓库到本地计算机。
    
    ```
    git clone <forked_repo_url> 
    ```
    
3.  **创建新分支**：进入克隆到本地的仓库目录，并创建一个新的分支用于你的代码更改。
    
    ```
    git checkout -b <branch_name> 
    ```
    
4.  **进行代码更改**：使用合适的代码编辑工具，对本地仓库中的代码进行修改和添加。
    
5.  **提交更改**：使用`git add`和`git commit`命令将更改的文件添加到暂存区，并提交到本地分支。
    
    ```
    git add <modified_files>
    git commit -m "描述你的代码更改" 
    ```
    
6.  **推送分支**：将本地分支推送到你Fork的远程仓库。
    
    ```
    git push origin <branch_name> 
    ```
    
7.  **创建Pull Request**：访问你Fork的项目页面，点击页面上方的"Pull requests"选项卡，然后点击"New pull request"按钮。在比较页面中选择你的分支和上游项目的主分支，然后点击"Create pull request"。
    
8.  **填写说明**：在Pull Request页面中，填写相关的说明、描述和其他必要的信息，解释你的代码更改的目的和内容。
    
9.  **等待审查和合并**：提交Pull Request后，项目原始仓库的维护者将会进行代码审查，并提供反馈。在讨论和修改的过程中，持续进行代码更改和提交。一旦审查通过，你的代码更改将会被合并到上游仓库的主分支中。
    

等待你的PR被合并后，你就成为该项目的贡献者之一了！

### [#](#git-with-vscode) Git with vscode

在vscode里面使用Git，安装完git和vscode，点击Ctrl+Shift+G打开源代码管理，可以直接初始化仓库，添加代码和提交代码。vscode将终端指令化的Git提供了图形化界面，可以直接在里面选择命令进行git操作。

![](https://evarle.top/img/in-post/2023-09-03/vscode-git.png)

GitGraph这个插件可以可视化Git的分支图和提交历史，还是很方便的。

![](https://evarle.top/img/in-post/2023-09-03/git-vscode.png)

我使用的vscode插件：

| 插件 | 说明 |
| --- | --- |
| Git Graph | 提供可视化的Git提交历史和分支图，使您可以更容易地查看和管理代码库的演化。 |
| GitHub Repositories | 与GitHub仓库的集成，允许您在VS Code中直接管理和操作GitHub上的代码库。 |
| gitignore | 自动生成`.gitignore`文件，根据您的项目类型和编程语言，以排除不必要的文件和文件夹。 |
| EditorConfig for VS Code | 根据项目的`EditorConfig`文件来配置编辑器，以确保代码风格和格式的一致性。 |
| DotENV | 用于在VS Code中编辑和管理`.env`文件，这对于存储环境变量和配置信息非常有用，尤其是在开发时。 |
| Remote Repositories | 允许您在VS Code中连接和管理远程代码库，如Git、GitHub、GitLab等，以便更轻松地协作和编写代码。 |

[#](#开放式分配工作方式) 开放式分配工作方式
-------------------------

![](https://evarle.top/img/in-post/2023-09-03/octocat-inclusion-advisory-council.webp)

在**GitHub**公司中，他们采用开放式工作分配的方式。每个员工可以自行解决自己的项目分配问题，选择自己想要做的项目，无需申请或经过管理层干预。这种分配方式建立在开放沟通的基础上，公司将目标和工作方式通过分布式的信息传递网络传达给员工，使得所有人都了解公司的目标和工作方式。员工被吸引到这种工作分配方式主要是因为他们喜欢自由选择与自己兴趣相关的项目，并与志同道合的人一起完成有意义的工作。开放分配意味着人们可以选择自己的工作内容。许多 GitHub 员工都是远程工作者，因此团队成员身份在某种程度上取决于员工所在的聊天室。

在 **Valve**公司，也就是V社中，员工的办公桌下面有轮子，使他们能够轻松地转移到另一个团队，这是 Valve 开放分配方法的象征性和实用性标志，并根据项目需求进行物理重组。

开放分配组织没有固定的领导力，任何项目的发起人都能成为一个领导者，当项目结束后，领导者又可能转移到另一个项目中当一个“跟随者”。

开放分配并非无拘无束。事实上，它增加了个人的责任感，因为没有人可以借口被安排在糟糕的项目上或者陷入一个糟糕的老板手下。如果你在一个开放分配的环境中无法产生影响力，那就是你自己的问题。你和其他人一样有同样的机会去取得成功。

开放分配让每个人的想法和观点都能得到尊重和倾听。它提供了一个平等和包容的工作环境，鼓励员工表达自己的意见，并将其纳入决策和任务分配的过程中。每个人都有机会参与项目和任务的决策过程。团队成员可以分享自己的观点、经验和专业知识，提出建议和改进建议。

开放式工作分配也有局限性，如公司仍需处理重要但无趣的任务、高管招聘困难以及难以解决人员是否有效工作的问题。然而，相对于传统的工作分配方式，开放式工作分配仍具有一些优势，例如减少浪费、加快创新和提高团队的自主性等等。

总的来说，开放式工作分配是一种有挑战性但有潜力的工作组织方式，可以激发员工的创造力和参与度，并推动组织的创新和发展。对于公司和组织来说，是否采用开放式工作分配需要根据具体情况进行权衡和尝试。随着组织对灵活性和创新的需求不断增加，开放分配工作模式将在未来的工作环境中扮演更重要的角色。

![](https://evarle.top/img/in-post/2023-09-03/1_xxCg9ZVW80r_hAmLOK57gw.webp)

> [Organise your venture like the best tech firms](https://medium.com/glu-laboratories/organise-your-venture-like-the-best-tech-firms-a-case-for-open-allocation-9bff7122aceb)

[#](#互联网开源精神) 互联网开源精神
---------------------

### [#](#开源-open-source) 开源（Open Source）

"开源"并不仅意味着东西是免费的。尽管开源软件通常是免费提供的，但开源的概念超越了费用问题，包括对软件或项目源代码的可用性和访问性。

开源是一种软件开发和分发模式，其中源代码是公开可见和可访问的。开源软件允许用户自由查看、使用、修改和分发其源代码。开源通常是在开源许可证下发布，例如GNU通用公共许可证（GPL）或MIT许可证。这些许可证赋予用户使用、修改和分发软件的权利，以及访问底层源代码的权限。

而开源并不只是开源软件，还包括"开源硬件"（Open Source Hardware）、"开放设计"（Open Design）和"开放文档"（Open Document）等。比如这篇博客，也可以说是开源的。

当涉及到分散的开发者之间的协作时，Git和代码托管平台发挥了重要作用。

Git是一个分布式版本控制系统，可以追踪源代码的修改历史，并允许开发者在本地进行分支管理、修改和合并代码。Git的分布式特性使得开发者可以独立地进行工作，并通过推送和拉取操作与其他开发者共享代码变更。

代码托管平台（如GitHub、GitLab、Gitee等）提供了一个集中的位置，开发者可以将他们的Git仓库存储在这些平台上。这些平台为开发者提供了许多协作功能，如问题跟踪、合并请求、代码审查等，以促进团队协作和代码贡献。

特别是GitHub的出现，为开源项目的协作提供了更简单、更有趣的方式。开发者可以在GitHub上浏览和发现各种开源项目，与项目贡献者交流，提交合并请求，并参与项目的发展和维护。

因此，Git和代码托管平台共同推动了开源的发展和全球开发者社区的形成。它们为开发者提供了有效的协作工具和平台，使得开源项目的协作和贡献更加容易和高效。

### [#](#开源软件-open-source-software) 开源软件（Open Source Software）

开源软件按照 [OSI 组织](https://opensource.org/associations)（Open Source Initiative Association）的 [OSD 定义](https://opensource.org/osd/)，开源不仅仅意味着可以访问源代码，开源软件的分发条款必须符合以下标准：

| 序号 | 条款 | 简单说明 |
| --- | --- | --- |
| 1 | Free Redistribution | 允许自由地再发布软件 |
| 2 | Source Code | 程序必须包含所有源代码 |
| 3 | Derived Works | 可以修改和派生新的软件 |
| 4 | Integrity of The Author's Source Code | 发布时保持软件源代码的完整性 |
| 5 | No Discrimination Against Persons or Groups | 不得歧视任何个人或团体 |
| 6 | No Discrimination Against Fields of Endeavor | 不得歧视任何应用领域（例如商业） |
| 7 | Distribution of License | 许可证的发布具有延续性 |
| 8 | License Must Not Be Specific to a Product | 许可证不能针对于某一个产品 |
| 9 | License Must Not Restrict Other Software | 许可证不能限制其他软件 |
| 10 | License Must Be Technology-Neutral | 许可证必须是技术中立的 |

> 表格来源：[开源指北：什么是开源](https://oschina.gitee.io/opensource-guide/guide/%E7%AC%AC%E4%B8%80%E9%83%A8%E5%88%86%EF%BC%9A%E5%88%9D%E8%AF%86%E5%BC%80%E6%BA%90/%E7%AC%AC%201%20%E5%B0%8F%E8%8A%82%EF%BC%9A%E4%BB%80%E4%B9%88%E6%98%AF%E5%BC%80%E6%BA%90/#%E5%BC%80%E6%BA%90%E8%BD%AF%E4%BB%B6)？

开源软件通常使用特定的**开源许可证**来确保其源代码的自由性。常见的开源许可证包括 GNU 通用公共许可证 (GPL)、MIT 许可证、Apache 许可证等。这些许可证规定了软件的使用、修改和分发条件。

开源许可证影响人们使用、研究、修改和分发软件的方式。一般来说，开放源码许可证允许计算机用户为任何目的使用开放源码软件。用户在使用开源软件时必须接受许可条款。

OSI的认可的开源许可证：https://opensource.org/licenses/

不同的开源许可证在保护软件的开源性和自由性方面有不同的要求和限制。选择适合的开源许可证取决于开发者对软件的使用和分发方式以及与其他项目的兼容性需求。选择合适的开源许可证对于保护自己的知识产权和项目的可持续发展十分重要，有助于确保项目能够在开源社区中蓬勃发展并得到广泛使用。

> 常见的开源许可证有以下几种：
> 
> 1.  GNU通用公共许可证（GNU General Public License，GPL）：GPL是最著名的开源许可证之一，要求在使用、修改和分发软件时，保持软件及其衍生作品的源代码公开，并要求将这些衍生作品同样以GPL协议发布。
> 2.  MIT许可证：MIT许可证是一种宽松的开源许可证，允许软件的自由使用、修改和分发，同时要求保留版权和许可声明。
> 3.  Apache许可证：Apache许可证也是一种广泛采用的开源许可证，允许自由使用、修改和分发软件，同时要求保留原始许可和版权声明。
> 4.  BSD许可证：BSD许可证是一系列开源许可证的总称，包括BSD 2-Clause License、BSD 3-Clause License等。BSD许可证具有灵活性和宽松性，允许自由使用、修改和分发软件，同时要求保留版权和许可声明。
> 5.  Mozilla公共许可证（Mozilla Public License，MPL）：MPL是一种特定于Mozilla项目的开源许可证，要求在使用、修改和分发软件时，保持源代码的可访问性，并要求将衍生作品同样以MPL协议发布。

**开源协议**是指在开源软件项目中所采用的共同规则和约定，以促进开发者之间的合作和协作。开源协议通常包含了代码贡献、社区参与、问题追踪、代码审查、版本控制等方面的规定。开源协议可以帮助确保开源软件项目的可持续性和开发者之间的良好合作。比如常见的[CC协议](https://creativecommons.org/licenses/by-sa/4.0/deed.zh)（Creative Commons License），它是一种开放的、灵活的版权许可协议，用于授权创作作品的使用和分发。本博客用的就是[CC-BY-NC-SA](https://creativecommons.org/licenses/by-sa/4.0/) 协议。

开源许可证主要关注于法律层面，确保开源软件的自由使用和分发，而开源协议则更加注重项目管理和开发者之间的合作规范。

#### [#](#开源操作系统linux) 开源操作系统Linux

知名的开源软件：**Linux**（操作系统），一个开源的操作系统，广泛用于服务器和嵌入式设备。1991 年，林纳斯·托瓦兹（Linus Torvalds）公开发布了一个类 UNIX 操作系统内核Linux，并接受了与版权（Copyright）相反的许可复制权（Copyleft）理念，从 Linux 0.12 版本起，Linux 内核开始采用 GPL 许可证的新版权声明。使用 Linux 内核并且大量使用 GNU 组件的操作系统发行版称为 GNU/Linux，简称Linux发行版（如Ubuntu、Debian）。

GNU代表“GNU's Not Unix”，它是一个自由软件项目，旨在创建一个完全自由和开放的操作系统。GNU项目始于1983年，由理查德·斯托曼（Richard Stallman）发起，他提出了“自由软件”（Free Software）的概念，强调用户应该有权利运行、复制、分发、研究、修改和改进软件。

Linux是操作系统的内核，由芬兰计算机科学家林纳斯·托瓦兹（Linus Torvalds）于1991年开发。Linux内核是一个典型的开源项目，它采用了GNU通用公共许可证（GPL）作为许可证，与GNU项目的理念相契合。Linux内核提供了操作系统的核心功能，包括进程管理、文件系统、设备驱动等。

GNU和Linux的结合产生了GNU/Linux操作系统，通常简称为Linux。它是一个典型的开源软件项目，由许多不同的组件和工具组成，包括GNU工具集（如GNU Bash、GCC等）、X Window系统、GNOME、KDE、各种应用程序和库等。这些组件和工具与Linux内核一起构成了一个完整的操作系统。

GNU/Linux操作系统在服务器、个人电脑、移动设备和嵌入式系统等领域广泛应用。它的开放性、安全性、灵活性和可定制性受到了许多用户和开发者的青睐。GNU/Linux也成为了开源软件运动的象征，推动了自由软件的发展和开源文化的传播。

* * *

关于开源软件可以看看这篇文章：[What is open source?](https://opensource.com/resources/what-open-source)

> 人们更喜欢使用开源软件而不是专有软件有以下几个原因：
> 
> 1.  控制（Control）：开源软件让用户拥有更多的控制权。他们可以检查代码，确保软件不会执行不希望的操作，并且可以自由修改和定制软件以满足自己的需求。
> 2.  学习（Training）：开源软件帮助用户提升编程技能。公开的源代码使得学生可以学习优秀的编程实践，并与他人分享和讨论自己的工作，从中获取反馈和改进。
> 3.  安全性（Security）：人们认为开源软件更安全和稳定。由于开源软件的源代码对公众可见，任何人都可以发现并修复潜在的安全漏洞，使得软件更加可靠和安全。
> 4.  稳定性（Stability）：对于长期重要的项目，人们更倾向于选择开源软件。开源软件的源代码公开，即使原始开发者停止维护，用户仍然能够继续使用、维护和改进软件，避免依赖某个特定的厂商或个人。
> 5.  社区（Community）：开源软件通常形成一个活跃的用户和开发者社区。这个社区不仅仅是用户群体，而是由生产、测试、使用和推广软件的人组成的共同体，他们对软件的发展和影响发挥着重要作用。

总的来说，开源软件给予用户更大的自由、灵活性和透明度，同时鼓励学习、协作和共享，因此人们更倾向于使用开源软件。

### [#](#互联网时代的开源项目) 互联网时代的开源项目

如今的互联网上，开源有着十分重要的作用，随着AI浪潮，现在出现了一大堆优秀的AI大语言模型，或者大规模的AI模型，而项目的开源就让原本工作量特别大的、训练量特别多的优秀项目能让更多人免费的使用，特别是小公司，可能能节省下特别多的开发和训练成本，而且开源项目的源代码也是开源的，可以为自己的项目的功能修改和添加代码，可能可以节省几百万行代码量，也能提供给开发者用于学习和部署。

开源项目比如[Stable Diffusion](https://github.com/Stability-AI/StableDiffusion)、[so-vits-svc](https://github.com/svc-develop-team/so-vits-svc)、[MiniGPT-4](https://github.com/Vision-CAIR/MiniGPT-4)、[Auto-GPT](https://github.com/Significant-Gravitas/Auto-GPT)等这种AI项目人人都能部署和使用。

还有[opencv](https://github.com/opencv/opencv)、[pytorch](https://github.com/pytorch/pytorch)和[keras](https://github.com/keras-team/keras)等等这种神经网络和机器学习这种开源项目，给如今很多新的AI创业公司提供了非常大的帮助，可能小公司写几十年代码都写不出像opencv这种计算机视觉框架，所以大公司的开源项目对于互联网发展非常重要，有利于项目可持续发展以及AI的发展。

[Edit this page on GitHub](https://github.com/Mrzhuo2022/Mrzhuo2022.github.io/edit/main/blog/posts/2023-09-03-git-and-github.md)

Last Updated: 12/3/2023, 1:20:14 AM

[Previous  
Jellyfin私人影音库](/post/2023/09/03/jellyfin-build/)[Next  
Linux基础和wsl安装](/post/2023/10/14/Linux-and-wsl/)

*   什么是Git
*   Git的安装和使用
*   Git的结构组成
*   常用的Git命令
*   Git工作流
*   Git项目生命周期
*   Git Flow
*   Git与Github
*   什么是github
*   Github作为Git远程仓库
*   Github Actions
*   你的第一个Pull Request(PR)
*   Git with vscode
*   开放式分配工作方式
*   互联网开源精神
*   开源（Open Source）
*   开源软件（Open Source Software）
*   开源操作系统Linux
*   互联网时代的开源项目

74%

©2023 [Evarle](#)  
Powered by [VuePress](https://v2.vuepress.vuejs.org) & [Gungnir](https://github.com/Renovamen/vuepress-theme-gungnir)

↑↓⇔⇧⇩