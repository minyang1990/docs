# 如何约束大模型严格输出指定内容？引导解码器 Guided Decoder 原理讲解 & 实战演示 - 开发调优 - LINUX DO
[如何约束大模型严格输出指定内容？引导解码器 Guided Decoder 原理讲解 & 实战演示 - 开发调优 - LINUX DO](https://linux.do/t/topic/813639/3) 

  如何约束大模型严格输出指定内容？引导解码器 Guided Decoder 原理讲解 & 实战演示 - 开发调优 - LINUX DO                                                 

[跳到主要内容](#main-container)

子系统

*   [Connect](https://connect.linux.do "LINUX DO Connect 账号连接系统。")
*   [Webmail](https://webmail.linux.do/ "LINUX DO Mail 系统。")

元宇宙

*   [导航站](https://nav.linux.do "LINUX DO 相关服务导航站。")
*   [Wiki站](https://wiki.linux.do "LINUX DO Wiki 系统。")
*   [分发站](https://cdk.linux.do "LINUX DO 分发站，福利多多。")

其他

*   [2048](https://2048.linux.do "一起来挑战、打榜经典2048小游戏。")
*   [T-Shirt](https://shanwaiyoushan.taobao.com "LINUX DO元气T+POLO：社交新名片。")

 [![](https://linux.do/uploads/default/original/3X/9/d/9dd49731091ce8656e94433a26a3ef36062b3994.png)](/) 

[如何约束大模型严格输出指定内容？引导解码器 Guided Decoder 原理讲解 & 实战演示](/t/topic/813639)
===================================================================

[开发调优](/c/develop/4)

[人工智能](/tag/人工智能),[ChatGPT](/tag/chatgpt),[软件开发](/tag/软件开发),[OpenAI](/tag/openai)

*   ​

*    ![](https://linux.do/letter_avatar/niyan2025/96/5_d44a9b381edc88181525e3c8350177ca.png)
       [ 3 ](# "3 个未读通知") 

*   [话题](/latest "所有话题")
*   [我的帖子](/u/niyan2025/activity/drafts "我的未发布草稿")
*   [我的消息](/u/niyan2025/messages "我的个人信息")
*   [关于](/about "关于此网站的更多详细信息")
*   [近期活动](/upcoming-events "近期活动")
*   更多

类别

*   [开发调优](/c/develop/4 "此版块包含开发、测试、调试、部署、优化、安全等方面的内容")
*   [资源荟萃](/c/resource/14 "包括软件分享、开源仓库、视频课程、书籍等分享")
*   [文档共建](/c/wiki/42 "佬友化身翰林学士，一起来编书了。")
*   [非我莫属](/c/job/27 "学成文武艺，货与帝王家。招聘/求职分类，只能发此类信息。")
*   [读书成诗](/c/reading/32 "跟着佬友们一起在论坛读完一本书是什么体验？")
*   [扬帆起航](/c/startup/46 "扬帆起航，目标是星辰大海！")
*   [前沿快讯](/c/news/34 "前沿快讯，不出门能知天下事。")
*   [网络记忆](/c/feeds/92 "网络是有记忆的，确信！")
*   [福利羊毛](/c/welfare/36 "正经人谁花那个钱啊～ 此版块供羊毛、抽奖等福利使用。")
*   [搞七捻三](/c/gossip/11 "闲聊吹水的板块。不得讨论政治、色情等违规内容。")
*   [运营反馈](/c/feedback/2 "有关此网站、其组织、运作方式以及如何改进的讨论。")
*   [深海幽域](/c/muted/45 "冰山下的深海。帖子不会上信息流、不会被论坛搜索。")
*   [所有类别](/categories)

标签

*   [人工智能](/tag/%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD)
*   [公告](/tag/%E5%85%AC%E5%91%8A)
*   [快问快答](/tag/%E5%BF%AB%E9%97%AE%E5%BF%AB%E7%AD%94)
*   [抽奖](/tag/%E6%8A%BD%E5%A5%96)
*   [精华神帖](/tag/%E7%B2%BE%E5%8D%8E%E7%A5%9E%E5%B8%96)
*   [所有标签](/tags)

*   [我的消息串](/chat/threads "我的消息串")

频道

*   [常规频道](/chat/c/general/2 "🈲 禁止在聊天频道里发送 打卡 等无意义信息，被举报会喜提 禁言1小时 。")

直接消息

*    [![](https://linux.do/user_avatar/linux.do/xronus/48/130867_2.png)  𝒜𝓃𝒾𝓋𝒾𝓍](/chat/c/%F0%9D%92%9C%F0%9D%93%83%F0%9D%92%BE%F0%9D%93%8B%F0%9D%92%BE%F0%9D%93%8D/32458 "与 𝒜𝓃𝒾𝓋𝒾𝓍 聊天") 
*    [![](https://linux.do/user_avatar/linux.do/huan/48/293194_2.png)  焕昭君](/chat/c/%E7%84%95%E6%98%AD%E5%90%9B/43057 "与 焕昭君 聊天") 
*    [![](https://linux.do/user_avatar/linux.do/wenjuhe/48/672301_2.png)  奇妙进化小河马🦛   ![](https://linux.do/images/emoji/twemoji/hippopotamus.png?v=14)](/chat/c/%E5%A5%87%E5%A6%99%E8%BF%9B%E5%8C%96%E5%B0%8F%E6%B2%B3%E9%A9%AC%F0%9F%A6%9B/45968 "与 奇妙进化小河马🦛 聊天") 

聊天

Default

​ ​ ​

**真诚**、**友善**、**团结**、**专业**，共建你我引以为荣之社区。[《常见问题解答》](/faq)

[如何约束大模型严格输出指定内容？引导解码器 Guided Decoder 原理讲解 & 实战演示](/t/topic/813639)
===================================================================

[开发调优](/c/develop/4)

[人工智能](/tag/人工智能),[ChatGPT](/tag/chatgpt),[软件开发](/tag/软件开发),[OpenAI](/tag/openai)

您已选择 **0** 个帖子。

全选

取消选择

​

[7月 24 日](/t/topic/813639/1 "跳到第一个帖子")

3 / 44

7月 23 日

[22 分钟](/t/topic/813639/44)

​

[![](https://linux.do/user_avatar/linux.do/lstm-kirigaya/96/701709_2.png)
](/u/LSTM-Kirigaya)

[锦恢](/u/LSTM-Kirigaya)[LSTM-Kirigaya](/u/LSTM-Kirigaya)

7

[17 小时](/t/topic/813639?u=niyan2025 "发布日期")

[![](https://linux.do/uploads/default/optimized/4X/6/1/b/61b6b740a3f880730d9a622242cba2a7d81c58cd_2_666x500.jpeg)

14a2f0a03e53c29005aef575285dac0f1440×1080 286 KB

](https://linux.do/uploads/default/original/4X/6/1/b/61b6b740a3f880730d9a622242cba2a7d81c58cd.jpeg "14a2f0a03e53c29005aef575285dac0f")

[](#p-7456625-h-1)前言
--------------------

相信大家在开发 AI Agent 的时候一定遇到过这样的情况：我希望让大模型严格只输出 yes 或者 no，这样我就可以写一个这样的程序来决定 Agent 后续的走向了：

```


`if result == 'yes':
    # 执行下一步
    execute_next_step()
elif result == 'no':
    # 执行退出操作
    execute_exit()` 
```

> 当然，有时候我们还会遇到更加复杂的需求，比如，想要大模型严格按照一个规范返回 json，甚至是某种更加抽象的形式语言。比如锦恢制作的一个 i18n 翻译插件中，就希望大模型严格按照一个数据结构返回指定的 json 内容，这样，我就可以通过剩下的程序来把这部分内容同步到软件的其他地方去了。

这时候，看过锦恢前几篇教程的你，一定会兴奋地说：“这还不简单，用 prompt 大法不就解决了？” 然后你非常自信地写出了如下的演示代码：

```


`prompt = """
你是一个聪明的 Agent，我会在下面询问你几个事实性的问题

你只需要回答 yes 或者 no 就行

请问初音未来是真实的人类吗？
"""
outputs = llm.generate(prompts=prompt)` 
```

此处使用了 [Qwen2.5-3B-Instruct](https://huggingface.co/Qwen/Qwen2.5-3B-Instruct) 这个模型，它的回答是：

```


`'不 是\n好的，我知道了 请继续 提供帮助\n\n接下来我'` 
```

可以看到，结果是对的，初音未来确实不是真实的人类，但是我希望它返回的是 yes 或者 no，但是事实上，大模型除了一开始的并非是英文 no 的回复外，还返回了一堆乱七八糟的结果。

这时候你又要反驳了，那我继续写后处理的函数不就行了！我会去除所有的空格，然后通过硬编码来规约结果。好吧，好吧，可是，你又如何保证这样一定可行呢？你真的知道大模型是如何输出下一个字符的吗？

哈哈，看来，我们真的有必要在不伤害彼此感情的前提下让阁下了解一下大模型是如何运作的了。

放心，我会写的简明扼要，通俗易懂的。下面这个章节，保证小刻都能读懂。

[](#p-7456625-h-2)大模型是如何工作的？
----------------------------

我其实在之前无数的文章中说过，大模型的本质是一个自回归模型，所谓自回归，一个最为通俗的解释就是“自产自销”，自回归模型会自己消耗自己生成的东西。

比如我们现在往大模型内输入了一句话：

```


`今天还没吃饭，现在好` 
```

输入大模型后，它可能的输出结果是：

```


`饿` 
```

然后，原本的输入和此时输出的“饿”会被加入到输入的结尾，然后重新拼出一句话“今天还没吃饭，现在好饿”。然后这句话会被继续扔到大模型里面，继续输出后续的文本，直到生成一个特殊的字符 “EOS” 的时候，大模型就会停止生成。

所以你能看到，每一次的循环，输出的字符都会加入输入的字符，然后继续生成，这种“自产自销”的模型，就被我们称为自回归模型。大模型就是一种典型的自回归模型。

那么大模型是如何确定要生成哪个字符的呢？其实大模型的输出是一个向量，这个向量被我们称为 logits，我们往往采用 logits 最大的那个值的索引位置对应的字符。比如上述的例子的一个基本的示意图如下：

[![](https://linux.do/uploads/default/optimized/4X/c/c/f/ccfa2f6c326d58dbb5620c1f72b9a5852bf15990_2_690x295.png)

8bf8adf2e1e1f50831a33f20f6f101ed2258×966 119 KB

](https://linux.do/uploads/default/original/4X/c/c/f/ccfa2f6c326d58dbb5620c1f72b9a5852bf15990.png "8bf8adf2e1e1f50831a33f20f6f101ed")

如果用程序表达上面步骤的话，大概是这样（为了尽可能简单地解释，我忽略了分词器的编解码部分，还请轻喷）：

```


`class LLM:
    # token 到 token id 的映射
    token2id: dict
    # token id 到 token 的映射
    id2token: dict

    # 实现推理的函数，这部分是真实的大模型本体的参数
    def forward(self):
        ...

    # 用户层面调用的进行推理的函数
    def generate(self, prompts: str) -> str:
        llm_input = prompts
        while True:
            logits = self.forward(llm_input)
            predict_token_id = logits.argmax()

            # 遇到 EOS 了（end of sentence，代表一句话的结束）
            # 那么就结束生成
            if predict_token_id === self.eos_token_id:
                break

            predict_token = self.id2token[predict_token_id]
            llm_input += predict_token

        # 只返回新生成的部分，这部分算是大模型的 “回答”
        return llm_input[len(prompts):]` 
```

聪明的小伙伴估计会问了，那么这样的方式不是很愚蠢吗？每次都要重新计算之前已经计算过的文字前缀，有没有什么优化的策略呢？唔姆，**有的兄弟有的**，这个策略就叫作 KV Cache，在大模型厂商的 API 文档上往往会说「缓存命中」和「缓存没有命中」的不同定价，这个缓存指的就是 KV Cache。

关于详细的大模型的运作原理和产生的 KV Cache 优化机制，我是极力推荐这篇文章的：[大模型推理加速：看图学KV Cache](https://zhuanlan.zhihu.com/p/662498827) 。你要是能消化完这篇文章，大模型算法的门你也就算入了。

[](#p-7456625-h-3)如何确保大模型只生成指定的文本
---------------------------------

在了解了大模型如何工作的原理后，我们回到最初的那个问题：如何让大模型返回指定的文本，比如只返回 yes 或者 no 呢？

我们不妨把最初的那个例子装载到我们演示大模型工作的流程图中一探究竟：

[![](https://linux.do/uploads/default/optimized/4X/7/4/1/74123f8dc50ff587ec30ec0a4d1a5828fbe8d116_2_690x291.png)

1440×609 82.3 KB

](https://linux.do/uploads/default/original/4X/7/4/1/74123f8dc50ff587ec30ec0a4d1a5828fbe8d116.png)

来，请问，在已知我们只想要输出 yes 或者 no 的情况下，我们怎么做才能保证大模型输出的文本一定只能是 yes 或者 no ？

相信聪明的小朋友已经发现了，我们只需要把输出的 logits 中所有不是 yes 或者 no 的 logits 数值设置为一个很低很低的数值（比如负无穷），保 证后续程序只会在 yes 或者 no 这两个 token 中选择最大的那个即可。

这样，就能保证大模型输出的一定是 yes 或者 no 了：

[![](https://linux.do/uploads/default/optimized/4X/5/9/5/595f335f333a59121088d83efba1f800169e937d_2_690x268.png)

1440×561 74 KB

](https://linux.do/uploads/default/original/4X/5/9/5/595f335f333a59121088d83efba1f800169e937d.png)

那么如何再复杂一点，我们要求输出的一定是满足一个特定数据结构的呢？比如我们强制要求大模型输出一个代表用户本身的数据结构：

```


`{
    "username": "kirigaya",
    "password": "12345678"
}` 
```

这在生成调试前后端的 mook 数据时会经常遇到。

相信学习过编译原理的小朋友此时已经对答案呼之欲出了：我们完全可以将用户要求的结构化输出转换成完全等价的“有限状态机”（简称 FSM），这样大模型每一次输出 logits 时，我们就可以利用 FSM 来获取当前有效的 token，所有无效的 token 的 logits 全部设置为负无穷即可。

是的，这就是结构化输出 guided decoder 的基本实现原理，当然，咱们不需要把这件事作为你的编译原理课作业，因为已经有人实现好了，这就是目前进行结构化解码的 FSM 生成最有名的一个开源项目 [xgrammar](https://github.com/mlc-ai/xgrammar)，目前知名的大模型部署框架 [vLLM](https://github.com/vllm-project/vllm), [SGLang](https://github.com/sgl-project/sglang), [TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM) 等，他们的 guided decoder 都是采用了 xgrammar 作为的后端。大家只需要知道基本的原理，就足以让你应付大部分的 Agent 岗位的面试了。

接下来，就让我们看看，如何在 vllm 中使用 guided decoder，来输出严格约束的结构化文本内容吧！

[](#p-7456625-vllm-4)vllm 中使用结构化输出
----------------------------------

先根据你的 cuda 版本安装基本的库，比如我的 cuda 版本就是 12.4，所以安装：

```


`pip install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu124
pip install vllm --extra-index-url https://download.pytorch.org/whl/cu124` 
```

教程中推荐使用 jupyter notebook 作为 python 的编辑器和运行时容器，先创建一个基本的大模型：

```


`from enum import Enum
from pydantic import BaseModel
from vllm import LLM, SamplingParams
from vllm.sampling_params import GuidedDecodingParams

# 创建大模型
llm = LLM(model="Qwen/Qwen2.5-3B-Instruct", max_model_len=100)` 
```

vllm 提供了四种基本类型的引导解码器配置，你可以通过如下代码进行创建

```


`param = GuidedDecodingParams( ... )` 
```

GuidedDecodingParams 的参数对应的引导模式分别为：

1.  choice: 配置枚举类型，也就是只给几个选项，让大模型做选择题。
2.  regex: 配置正则表达式，让大模型输出的字符串严格符合正则表达式。
3.  json: 配置 json schema，让大模型输出的 json 一定符合 json schema，function calling 就是基于这个选项实现的。
4.  grammar: 配置巴斯克范式（简写为 BNF），利用这个可以让大模型输出的字符串严格符合BNF代表的形式语言。比如配置 python 的BNF，那么大模型输出的字符串一定严格符合 python 的语法。

接下来，我们来一个个看看效果。

### [](#p-7456625-choice-5)choice

choice 选项允许我们让大模型做选择题，这正好和我们刚才的例子相吻合，我们就希望 AI 输出 yes 或者 no，所以我们可以如此构造这个引导参数

```


`# 申明状态机规则/参数
params = GuidedDecodingParams(choice=['yes', 'no'])
# 根据状态机规则创建采样器
sampler = SamplingParams(guided_decoding=params)` 
```

然后我们把生成的采样器扔到 vllm 的推理函数中，就能完成引导解码啦！

```


`prompt = """
你是一个聪明的 Agent，我会在下面询问你几个事实性的问题

你只需要回答 yes 或者 no 就行

请问初音未来是真实的人类吗？
"""

outputs = llm.generate(prompts=prompt, sampling_params=sampler)
text = outputs[0].outputs[0].text
text` 
```

输出结果：

```


`no` 
```

非常完美！这下子，我们就可以在后续通过 if else 或者别的硬编码来实现后续的业务逻辑了。

### [](#p-7456625-regex-6)regex

正则表达式在表单验证和语法高亮中用得非常非常多，如果想要让大模型的输出结果满足某种上下文无关的语法特性，那么选择正则表达式就对了。

比如我们现在希望大模型的随机生成一些邮箱，一般都满足 `xxx@xxx.com` 这样的格式，那么就可以如此实现：

```


`params = GuidedDecodingParams(regex=r"\w+@\w+\.com\n")

# 遇到第一个回车就停止生成
sampler = SamplingParams(guided_decoding=params, stop=['\n'])

prompt = """
你是一个聪明的 Agent，请帮我生成一段邮箱
"""

outputs = llm.generate(prompts=prompt, sampling_params=sampler)
text = outputs[0].outputs[0].text
text` 
```

输出效果：

```


`Arya@Blacksmith.com` 
```

### [](#p-7456625-json-7)json

json 模式可以让大模型严格按照 json schema 输出，大模型符合 openai 规范的 function calling，也就是 tool\_calls 字段（[详情请看](https://kirigaya.cn/openmcp/zh/plugin-tutorial/concept.html#tool-calls-%E5%AD%97%E6%AE%B5)）

我们此时可以利用 vllm 的 json 模式来实现这一点，请看解码器生成函数：

```


`from typing import List, Dict, Any
import json

from vllm import SamplingParams
from vllm.sampling_params import GuidedDecodingParams

def create_guided_decoder(function_templates: List[Dict[str, Any]]) -> SamplingParams:
    tool_schemas = []
    for template in function_templates:
        tool_schemas.append({
            "type": "object",
            "properties": {
                "name": {"type": "string", "const": template["function"]["name"]},
                "description": {"type": "string", "const": template["function"]["description"]},
                "parameters": template["function"]["parameters"]
            },
            "required": ["name", "parameters"]
        })
    
    full_schema = {
        "type": "object",
        "properties": {
            "content": {"type": "string"},
            "tool_calls": {
                "type": "array",
                "items": {
                    "anyOf": tool_schemas
                }
            }
        },
        "required": ["content"]
    }
    
    return SamplingParams(
        guided_decoding=GuidedDecodingParams(json=full_schema),
        temperature=0.3,
        max_tokens=500
    )` 
```

然后任意的 mcp 客户端都会遵循 mcp 协议来自动生成 function calling 对应的 json schema，比如打开 openmcp 的交互对话，就能在下面的工具选择中找到当前激活工具的 json schema：

[![](https://linux.do/uploads/default/optimized/4X/b/b/e/bbe3b01ef44c0640063cd6140554a3b7cddeb054_2_690x386.png)

1440×806 117 KB

](https://linux.do/uploads/default/original/4X/b/b/e/bbe3b01ef44c0640063cd6140554a3b7cddeb054.png)

> 没有安装 openmcp 的朋友可以移步 [安装 OpenMCP](https://kirigaya.cn/openmcp/zh/plugin-tutorial/quick-start/acquire-openmcp.html)

我们点击复制，然后粘贴到下面这个变量 `...` 这里：

```


`input_json_schema = ...` 
```

然后，我们就可以让大模型进行 function calling 了，需要主要的是，因为实验用的是很小的 qwen 模型，它的 Hallucination (自治力，代表大模型调用工具的主动性，我很快会发表一篇论文讲解 Agent 的一系列我提出的通用指标) 比较小，所以需要加上额外的引导词，比如 “请通过调用工具解决这个问题”，大一点的模型就没有这个问题。代码如下：

```


`sampler = create_guided_decoder(input_json_schema)

prompt = """
今天杭州天气如何？你应该通过调用工具来解决这个问题
"""

outputs = llm.generate(prompts=prompt, sampling_params=sampler)
json_string = outputs[0].outputs[0].text
output_data = json.loads(json_string)
print(json.dumps(output_data, ensure_ascii=False, indent=2))` 
```

输出结果：

```


`{
  "content": "今天杭州天气如何？",
  "tool_calls": [
    {
      "name": "weather",
      "parameters": {
        "city_code": 101010100
      }
    }
  ]
}` 
```

可以看到完美输出了 content 和 tool\_calls 这两个字段，这样，mcp 客户端就会自动根据 tool\_calls 进行工具调用了。于是，我们优雅地实现了大模型中台的 function calling。

### [](#p-7456625-grammar-8)grammar

grammar 允许我们输入BNF，学过编译原理的朋友都知道，编程语言本身的语法都可以通过巴斯克表达来完全等价的进行表示。

我们开发编译器可以基于标准委员会制定出的镌刻着几百页BNF的标准手册来开发和测试的。

因此，理论上，你完全可以通过这个选项来让大模型输出 100% 符合词法和上下文无关语法的编程语言，但是实际上编写BNF是非常劳神费力的事情，所以这个板块仅仅是演示用法。

最后一个例子源于 vllm 官方给出的例子，代码如下，用于规范大模型生成的 sql 查询语句：

```


`simplified_sql_grammar = """
root ::= select_statement
select_statement ::= "SELECT " column " from " table " where " condition
column ::= "col_1 " | "col_2 "
table ::= "table_1 " | "table_2 "
condition ::= column "= " number
number ::= "1 " | "2 "
"""

param = GuidedDecodingParams(grammar=simplified_sql_grammar)
sampler = SamplingParams(
    guided_decoding=param,
    temperature=0.3,
    max_tokens=500
)

prompt = "Generate an SQL query to show the 'username' and 'email'from the 'users' table."
outputs = llm.generate(prompts=prompt, sampling_params=sampler)
text = outputs[0].outputs[0].text
text` 
```

输出结果：

```


`SELECT col_1  from table_1  where col_2 = 1` 
```

[](#p-7456625-h-9)大模型厂商提供的结构化输出方法
---------------------------------

上面都是讲的本地部署的大模型进行结构化输出的方法，那么对于线上部署的，我们一般直接调用的大模型，能不能做到结构化输出呢？

答案是可以，但是自由度没有这么高。

如果大家经常翻阅大模型厂商的官方文档，比如 deepseek，有时候能看到这样的特性：

[![](https://linux.do/uploads/default/optimized/4X/0/9/5/095c22b3d3580648401fe6edd1d625a1ab45c7b9_2_690x334.jpeg)

1440×698 122 KB

](https://linux.do/uploads/default/original/4X/0/9/5/095c22b3d3580648401fe6edd1d625a1ab45c7b9.jpeg)

比如 deepseek 可以支持 json 输出，如果你看懂了上面的内容，就应该知道这个特性大概是如何实现的了。

当然，这部分并不保证通用性，因为有的厂商支持，有的可能不支持。因为 fim 和 json output 并不在 openai 的协议规范中。

但是有一个参数几乎是所有厂商都支持的，那就是 openai 协议中的 `logit_bias` 参数。通过这个参数，可以引导大模型输出的 token 偏好。

### [](#p-7456625-logit_bias-10)通过 logit\_bias 设置大模型的输出偏好

比如，我们想要让大模型“尽量只输出 yes 或者 no”，那么可以如此设置 `logit_bias`

```


`logit_bias = {
    'yes': 100,
    'no': 100,
}` 
```

完整代码如下：

```


`import os
from openai import OpenAI

# 初始化客户端
client = OpenAI(
    api_key=os.environ['DEEPSEEK_API_TOKEN'],
    base_url='https://api.deepseek.com'
)

def get_yes_no_answer(question: str) -> str:
    logit_bias = {
        'yes': 100,
        'no': 100,
    }
    
    response = client.chat.completions.create(
        model="deepseek-chat",
        messages=[
            {"role": "user", "content": question}
        ],
        max_tokens=1,
        logit_bias=logit_bias,
        temperature=0.1
    )
    
    return response.choices[0].message.content.lower()

# 示例使用
if __name__ == "__main__":
    questions = [
        "Is water wet?",
        "Can birds fly?",
        "Is Python better than JavaScript?",
        "Is the sky green?"
    ]

    valid_answer = ['yes', 'no']
    
    for q in questions:
        answer = get_yes_no_answer(q)
        if answer not in valid_answer:
            print(f"Q: {q}\nA: I dont't know\n")
        else:
            print(f"Q: {q}\nA: {answer}\n")` 
```

输出如下：

```


`Q: Is water wet?
A: I dont't know

Q: Can birds fly?
A: yes

Q: Is Python better than JavaScript?
A: I dont't know

Q: Is the sky green?
A: no` 
```

[](#p-7456625-h-11)结语
---------------------

这次教程，锦恢介绍了一下结构化生成这个问题本身，以及如何从根本了解大模型的生成方法，从而推演出可能的解决方案。

最终也是通过 vllm 实现了这件事，希望大家也能在平时自己开发 Agent 的时候用到这件事。

对了，manus 之前不是发了一篇博客来着吗？里面提到的 tool mask 技巧其实就是基于 guided decoder 实现的，有兴趣的话，大家可以在读懂这篇博客后去看看 manus 那篇文章：

![](https://linux.do/uploads/default/original/4X/b/3/2/b325303aed1aed42283ab184da2634d584606d3d.png)
 [manus.im](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus)

![](https://linux.do/uploads/default/optimized/4X/0/f/c/0fc00931c2c855f5d75e92d45d38754cd036ac05_2_690x388.webp)

### [Context Engineering for AI Agents: Lessons from Building Manus](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus)

This post shares the local optima Manus arrived at through our own "SGD". If you're building your own AI agent, we hope these principles help you converge faster.

这里是正在秋招和赶论文的锦恢，如喜欢这篇文章的话，还希望多多转发，最后的最后，请帮我的 openmcp 点个免费的 star，谢谢：

[github.com](https://github.com/LSTM-Kirigaya/openmcp-client/)

![](https://linux.do/uploads/default/optimized/4X/d/5/2/d52cd5488db3936cd7961992c9b069be60926ce3_2_690x344.png)

### [GitHub - LSTM-Kirigaya/openmcp-client: All in one vscode plugin for mcp developer](https://github.com/LSTM-Kirigaya/openmcp-client/)

All in one vscode plugin for mcp developer

如果想要加群和我聊天，可以看看 openmcp 这个项目的 readme。

* * *

更新一下，关于结构化输出后结果是否在语义层面精度会下降，这里援引一下我朋友的一项工作，来为诸位答疑解惑：

正好趁机宣传一下我们最新的multilingual+interpretability的工作：从可解释性的角度分析LLM跨语言事实不一致的原因

![](https://linux.do/images/emoji/twemoji/pushpin.png?v=14)
 我们聚焦于多语言LLM在处理不同语言但语义相同的问题时出现事实不一致的现象。比如模型能用英文正确回答“加拿大的首都是哪里”是“渥太华”，但用中文却回答“多伦多”。

![](https://linux.do/images/emoji/twemoji/magnifying_glass_tilted_left.png?v=14)
 核心发现  
我们从模型内部结构出发，发现：

*   多语言LLM大多数层使用的是“语言无关”的概念空间(concept space)；
    
*   在靠近输出层时，模型会尝试将这个“概念”翻译回目标语言；
    
*   很多出错的情况就出现在这个“语言转换”阶段；
    
*   为此，我们提出了一种轻量级的线性shortcut方法，绕过出错的转换步骤，显著提升了模型的预测准确性和跨语言一致性。
    

![](https://linux.do/images/emoji/twemoji/test_tube.png?v=14)
 我们还构建了一个新的多语言知识评估数据集 KLAR（支持17种语言），以及相关代码工具，即将开源，欢迎交流使用！

![](https://linux.do/images/emoji/twemoji/bookmark_tabs.png?v=14)
论文链接：[\[2504.04264\] Lost in Multilinguality: Dissecting Cross-lingual Factual Inconsistency in Transformer Language Models](https://www.arxiv.org/abs/2504.04264)

  

4 个回复

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

+1

![](https://linux.do/images/emoji/twemoji/open_mouth.png?v=14)

open\_mouth

61

​ ​ 回复

451 浏览量 67 赞 9 链接 31 用户

 [![](https://linux.do/user_avatar/linux.do/apparition/96/802222_2.png)
 4](/u/apparition "apparition") 

 [![](https://linux.do/user_avatar/linux.do/lstm-kirigaya/96/701709_2.png)
 4](/u/LSTM-Kirigaya "LSTM-Kirigaya") 

 [![](https://linux.do/letter_avatar/nameliu/96/5_d44a9b381edc88181525e3c8350177ca.png)
 3](/u/nameliu "nameliu")

 [![](https://linux.do/user_avatar/linux.do/jl_xxx/96/662859_2.png)
 3](/u/JL_Xxx "JL_Xxx")

 [![](https://linux.do/user_avatar/linux.do/greatmola/96/538143_2.png)
 2](/u/GreatMOLA "GreatMOLA")

阅读时间 5 分钟

总结

[![](https://linux.do/user_avatar/linux.do/haleclipse/96/606178_2.png)
](/u/Haleclipse)

[哈雷彗星](/u/Haleclipse)[Haleclipse](/u/Haleclipse)无所不知 ![](https://linux.do/images/emoji/twemoji/dizzy.png?v=14) 

[17 小时](/t/topic/813639/2?u=niyan2025 "发布日期")

是吃的 ！ 好干！

（干货啊）

  

1 个回复

1

​ ​ 回复

[![](https://linux.do/letter_avatar/qq727474430/96/5_d44a9b381edc88181525e3c8350177ca.png)
](/u/qq727474430)

[雨下不停](/u/qq727474430)[qq727474430](/u/qq727474430)

[16 小时](/t/topic/813639/3?u=niyan2025 "发布日期")

干货，学到了

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/lstm-kirigaya/96/701709_2.png)
](/u/LSTM-Kirigaya)

[锦恢](/u/LSTM-Kirigaya)[LSTM-Kirigaya](/u/LSTM-Kirigaya)

 ![](https://linux.do/user_avatar/linux.do/haleclipse/48/606178_2.png)
 哈雷彗星

[16 小时](/t/topic/813639/4?u=niyan2025 "发布日期")

这次算是我久违地输出一次干货了，主要是因为现在大部分人对大模型系统缺乏一个基本的认知，这让我痛心疾首的同时，也大大增加了沟通成本。和某些朋友聊大模型技术时，上下文不对齐的太多了，很难受。

  

1 个回复

![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

+1

![](https://linux.do/images/emoji/twemoji/heart.png?v=14)

heart

2

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/joegodwanggod/96/600929_2.png)
](/u/joegodwanggod)

[善解人意屬實有點害羞](/u/joegodwanggod)[joegodwanggod](/u/joegodwanggod)Guidance Counsellor ![](https://linux.do/uploads/default/original/3X/e/3/e35691b7018d583648978ad24ec7f6ad01f56c44.png?v=14) 

[16 小时](/t/topic/813639/5?u=niyan2025 "发布日期")

![](https://linux.do/user_avatar/linux.do/lstm-kirigaya/48/701709_2.png)
 锦恢:

> 小刻

他是誰阿

  

1 个回复

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/vimcoder/96/807005_2.png)
](/u/VimCoder)

[VimCoder](/u/VimCoder)文化宣导员

[16 小时](/t/topic/813639/6?u=niyan2025 "发布日期")

满满的干货，学习了 ![](https://linux.do/images/emoji/twemoji/grinning_face.png?v=14)

  

​ ​ 回复

[![](https://linux.do/letter_avatar/lotty18/96/5_d44a9b381edc88181525e3c8350177ca.png)
](/u/lotty18)

[lotty18](/u/lotty18)

[16 小时](/t/topic/813639/7?u=niyan2025 "发布日期")

干货！感谢楼主分享

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/jl_xxx/96/662859_2.png)
](/u/JL_Xxx)

[Shift](/u/JL_Xxx)[JL\_Xxx](/u/JL_Xxx)文化宣导员

[16 小时](/t/topic/813639/8?u=niyan2025 "发布日期")

![](https://linux.do/user_avatar/linux.do/lstm-kirigaya/48/701709_2.png)
 锦恢:

> 然后，原本的输入和此时输出的“饿”会被加入到输入的结尾，然后重新拼出一句话“今天还没吃饭，现在好饿”。然后这句话会被继续扔到大模型里面，继续输出后续的文本，直到生成一个特殊的字符 “EOS” 的时候，大模型就会停止生成。
> 
> 所以你能看到，每一次的循环，输出的字符都会加入输入的字符，然后继续生成，这种“自产自销”的模型，就被我们称为自回归模型。大模型就是一种典型的自回归模型。

佬，这里输入输出就看的有点迷糊，是不是指的它内部还会进行多次输入输出再会给用户响应内容

  

2 个回复

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/oscar/96/437936_2.png)
](/u/Oscar)

[Oscar](/u/Oscar)一元复始

[16 小时](/t/topic/813639/9?u=niyan2025 "发布日期")

可以试试 fewshot，给出一个或者多个示例，现在的模型对于 json 选择题等格式遵循效果都比较好

  

1 个回复

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/apparition/96/802222_2.png)
](/u/apparition)

[apparition](/u/apparition)

1

 ![](https://linux.do/user_avatar/linux.do/oscar/48/437936_2.png)
 Oscar

[16 小时](/t/topic/813639/10?u=niyan2025 "发布日期")

json用结构化生成就好了  
结构化做不到你就算弄成full shot也没用  
few‑shot 的问题点在于会增加不稳定的程度  
很吃测试的经验  
如果 json 又有什么特殊要求会更麻烦  
所以一开始直接上是最实际的方案

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/apparition/96/802222_2.png)
](/u/apparition)

[apparition](/u/apparition)

1

 ![](https://linux.do/user_avatar/linux.do/jl_xxx/48/662859_2.png)
 Shift

[16 小时](/t/topic/813639/11?u=niyan2025 "发布日期")

节录

```


`自回归模型透过测量先前依序的输入来自动预测序列中的下一个组成
假设时间序列的目前值是过去值的其中一个函数
模型用类似的数学技术来确定序列中元素之间的概率相关性
接着使用衍生的知识来猜测未知序列中的下一个元素
例如，在训练期间，自回归模型处理了数个英语句子，确定「is」总是接在「there」的后面
模型就会生成一个「there is」一起出现的新序列` 
```

就是用你提供的上下文去推导后续该接什么字元  
每次生成字元的时候都会查表一次  
直到出现 EOS 停止

  

1 个回复

![](https://linux.do/images/emoji/twemoji/open_mouth.png?v=14)

open\_mouth

1

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/jl_xxx/96/662859_2.png)
](/u/JL_Xxx)

[Shift](/u/JL_Xxx)[JL\_Xxx](/u/JL_Xxx)文化宣导员

 ![](https://linux.do/user_avatar/linux.do/apparition/48/802222_2.png)
 apparition

[16 小时](/t/topic/813639/12?u=niyan2025 "发布日期")

学习一下，感谢佬友

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/yqyan/96/576335_2.png)
](/u/yqyan)

[Grogu](/u/yqyan)[yqyan](/u/yqyan)

[16 小时](/t/topic/813639/13?u=niyan2025 "发布日期")

真干货 ![](https://linux.do/images/emoji/twemoji/+1.png?v=14)
，佬友太强了 ![](https://linux.do/images/emoji/twemoji/+1.png?v=14)

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/handsome/96/736205_2.png)
](/u/handsome)

[大帅哥](/u/handsome)[handsome](/u/handsome)种子用户 ![](https://linux.do/images/emoji/twemoji/rage.png?v=14) 

[16 小时](/t/topic/813639/14?u=niyan2025 "发布日期")

太强了，大佬

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/lstm-kirigaya/96/701709_2.png)
](/u/LSTM-Kirigaya)

[锦恢](/u/LSTM-Kirigaya)[LSTM-Kirigaya](/u/LSTM-Kirigaya)

 ![](https://linux.do/user_avatar/linux.do/joegodwanggod/48/600929_2.png)
 善解人意屬實有點害羞

[16 小时](/t/topic/813639/15?u=niyan2025 "发布日期")

明日方舟的一个角色，可以搜一下

  

1 个回复

​ ​ 回复

[![](https://linux.do/letter_avatar/yuyi233/96/5_d44a9b381edc88181525e3c8350177ca.png)
](/u/yuyi233)

[yuyi233](/u/yuyi233)

[16 小时](/t/topic/813639/16?u=niyan2025 "发布日期")

学到了，感谢分享

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/leioukupo/96/1226_2.png)
](/u/leioukupo)

[leioukupo](/u/leioukupo)浴火重生

[16 小时](/t/topic/813639/17?u=niyan2025 "发布日期")

那么请问，逆向的api该怎么办？

  

1 个回复

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/gibbersto1977/96/702050_2.png)
](/u/Gibbersto1977)

[BlackCat](/u/Gibbersto1977)[Gibbersto1977](/u/Gibbersto1977)

[16 小时](/t/topic/813639/18?u=niyan2025 "发布日期")

太赞了，第一次了解到logit这个参数

  

1

​ ​ 回复

[![](https://linux.do/letter_avatar/nameliu/96/5_d44a9b381edc88181525e3c8350177ca.png)
](/u/nameliu)

[nameliu](/u/nameliu)蛇来运转

 ![](https://linux.do/user_avatar/linux.do/leioukupo/48/1226_2.png)
 leioukupo

[15 小时](/t/topic/813639/19?u=niyan2025 "发布日期")

逆向的无法传参数，只能在prompt里做文章了。  
效果大概不如指定sampler效果好，比如你让它返回json格式，它可能给你用

```


` ```json``` ` 
```

给包起来。

楼上有说的：

![](https://linux.do/user_avatar/linux.do/oscar/48/437936_2.png)

[如何约束大模型严格输出指定内容？引导解码器 Guided Decoder 原理讲解 & 实战演示](https://linux.do/t/topic/813639/9) [开发调优](/c/develop/4)

> 可以试试 fewshot，给出一个或者多个示例，现在的模型对于 json 选择题等格式遵循效果都比较好

![](https://linux.do/user_avatar/linux.do/apparition/48/802222_2.png)

[如何约束大模型严格输出指定内容？引导解码器 Guided Decoder 原理讲解 & 实战演示](https://linux.do/t/topic/813639/10) [开发调优](/c/develop/4)

> json用结构化生成就好了 结构化做不到你就算弄成full shot也没用 few‑shot 的问题点在于会增加不稳定的程度 很吃测试的经验 如果 json 又有什么特殊要求会更麻烦 所以一开始直接上是最实际的方案

  

​ ​ 回复

[![](https://linux.do/user_avatar/linux.do/leokk/96/839286_2.png)
](/u/leokk)

[康康](/u/leokk)[leokk](/u/leokk)

[15 小时](/t/topic/813639/20?u=niyan2025 "发布日期")

干货，但是我不想看，让给其他佬看

  

​ ​ 回复

Invalid date Invalid date

↑↓⇔⇧⇩