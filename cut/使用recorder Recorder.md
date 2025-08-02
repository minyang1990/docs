# 使用recorder | Recorder
[使用recorder | Recorder](https://recorder.tokenroll.ai/zh-Hans/docs/vscode/usage) 

   使用recorder | Recorder    

[跳到主要内容](#__docusaurus_skipToContent_fallback)

[

![](https://recorder.tokenroll.ai/zh-Hans/img/logo.svg)

**Recorder**](/zh-Hans/)[教程](/zh-Hans/docs/intro)[Blog](/zh-Hans/blog)

[简体中文](#)

*   [English](/docs/vscode/usage)
*   [简体中文](/zh-Hans/docs/vscode/usage)

[GitHub](https://github.com/TokenRollAI/recorder)

*   [介绍](/zh-Hans/docs/intro)
*   [前置](/zh-Hans/docs/prerequisites)
*   [VS Code](#)
    
    *   [安装](/zh-Hans/docs/vscode/installation)
    *   [使用recorder](/zh-Hans/docs/vscode/usage)
*   [JetBrains](#)
    
    *   [安装](/zh-Hans/docs/jetbrains/installation)
    *   [使用recorder](/zh-Hans/docs/jetbrains/usage)
*   [Just Do Once](/zh-Hans/docs/just-do-once)
*   [Examples](#)
    
    *   [Go-Zero 添加新API](/zh-Hans/docs/example/go-zero-new-api)
*   [在线SOP生成器](/zh-Hans/docs/online-sop-generator)
*   [QA](#)
    

*   VS Code
*   使用recorder

本页总览

使用recorder
==========

### 注意!!![​](#注意 "注意!!!的直接链接")

1.  recorder依赖git的使用, 所以您必须保证所在的项目是通过git进行版本管理
2.  如果想要得到最好的效果, 建议在一个全新的的,没有任何stash change的分支进行录制, 这样可以得到最干净的改动

### 开始录制[​](#开始录制 "开始录制的直接链接")

你绝对想不到使用recorder有多么的简单, 只需要点击左下角的 `Start Recording` 就够了.

![](https://recorder.tokenroll.ai/zh-Hans/assets/images/click_recording-b23d3b04d98c9b28844db21048f7a65f.png)

### 编写代码[​](#编写代码 "编写代码的直接链接")

就像你日常工作一样, 完成你的任务, recorder会完全无侵入的记录你的操作

### 结束录制[​](#结束录制 "结束录制的直接链接")

没有什么难度, 再点击一次`Stop` ![](https://recorder.tokenroll.ai/zh-Hans/assets/images/click_stop_recording-6c510f6c4b49d87965e11184dba21e97.png)

如果能够正常的完整录制, 那么在您的项目的根目录下会有一个 `opetion.json` ![](https://recorder.tokenroll.ai/zh-Hans/assets/images/operation_json_position-430a7b0142f4cae8fc049877e26ae5e7.png)

### 生成SOP-SPEC[​](#生成sop-spec "生成SOP-SPEC的直接链接")

打开你使用的AI IDE的chat框, 然后选择一个有写权限的模式(例如Cursor/AugmentCode的Agent模式)

然后输入: `call generate_operation_md and follow the instruscion`

等待AI的执行, 最终会在`.spec`目录下, 生成一个对应的md文件

参考: ![](https://recorder.tokenroll.ai/zh-Hans/assets/images/sop_spec-7b535139ef6df865b931d4203d62ade0.png)

[编辑此页](https://github.com/facebook/docusaurus/tree/main/packages/create-docusaurus/templates/shared/docs/vscode/usage.mdx)

[

上一页

安装

](/zh-Hans/docs/vscode/installation)[

下一页

安装

](/zh-Hans/docs/jetbrains/installation)

*   [注意!!!](#注意)
*   [开始录制](#开始录制)
*   [编写代码](#编写代码)
*   [结束录制](#结束录制)
*   [生成SOP-SPEC](#生成sop-spec)

Docs

*   [Tutorial](/zh-Hans/docs/intro)

Community

*   [X](https://x.com/DisDjj4797)

More

*   [Blog](/zh-Hans/blog)
*   [GitHub](https://github.com/TokenRollAI/recorder)

Copyright © 2025 My Project, Inc. Built with Docusaurus.

↑↓⇔⇧⇩