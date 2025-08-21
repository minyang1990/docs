# 独立开发穷鬼套餐(Web实践篇)
[独立开发穷鬼套餐(Web实践篇)](https://guangzhengli.com/blog/zh/indie-hacker-poor-stack) 

 独立开发穷鬼套餐(Web实践篇)

Constants loaded at 2025-08-21T03:38:06.643Z

Toggle menu[![](https://guangzhengli.com/favicon.png)
](/ "Home")

*   [文章](/blog)
*   [课程](/courses)
*   [模板🔥](/blog/zh/build-nextjs-template)

独立开发穷鬼套餐(Web实践篇)
================

2025年7月28日 · 7114 字

我在 2024 年 4 月的时候，写了一篇 [独立开发技术栈 2024](https://nextdevkit.com/blog/zh/indie-hacker-tech-stack-2024/) 的文章，里面详细介绍了独立开发应该选择的技术栈和一些平台，随着时间的推移，推荐的一些技术栈已经成为了目前最流行和 AI 写的最好的技术栈。

之后一段时间里，还会陆陆续续有小伙伴问我应该推荐使用哪些技术栈和平台更好，很多小伙伴因为刚开始独立开发，对于成本还是比较敏感的，加上国外大部分平台都是使用信用卡，每月的账单有时候并不在控制范围内。所以一直处于观望状态。

加上之前那篇博客时间有些久了，推荐的一些技术栈和平台有些变动，今天专门写一篇博客分享一下独立开发，如何进行穷鬼开发之路。面向的是对于成本敏感的用户，对于成熟的独立开发者们，可以直接跳转到最后。

最新技术栈的选择
--------

首先我需要明确的是，本篇文章主要面向的是 Web 端的全栈开发技术栈和平台选择。关于移动端、后端和浏览器插件开发，感兴趣可以点点赞和关注，可以后续分享。

首先分享一下我最新的 Web 端独立开发全栈的技术栈选择。

首先是整个生态的选择问题，全栈开发的技术栈选择有很多，例如 Next.js，Nuxt，Laravel，Django，.Net Core，Ruby on Rails 等。

虽然 Next.js 14 和 15 有很多的特性和写法我并不满意，但是到目前为止，Next.js 还是我个人唯一推荐的全栈开发框架库。

原因就是 Next.js 继承了 React 生态，整个生态的活跃度还是最好的，有大量国内外的开源库和平台对 Next.js 是第一优先级支持的，这意味着两个巨大的优势。

一是你无论选择什么平台，或者是有什么需求，去寻找相关的开源库和平台文档支持都是最方便的。二是对于 AI 和 AI IDE 来讲，生态好，平台的文档全，意味着 AI 写的代码更加符合要求和 bug 少。

> 生态垄断的效应感觉在 AI 时代会更加明显，新的框架会比以前更难出头。

Next.js 对于不同的需求也非常友好，支持 SSR、SSG、ISR 等模式，可以满足大多数业务需求。

所以下面分享一下我具体的 Next.js 技术选型，虽然大部分技术选型和成本没什么大的关系，但有些技术栈对于你部署的平台有限制要求。

例如你想要添加发送邮件的功能到你的项目，你选择了 nodemailer 这个库，但这个库在很多 Edge 平台是不支持的，例如 Cloudflare 的 Workers。

所以在我踩了很多坑后，分享推荐一份通用的 Next.js 技术选型，经过测试基本可以部署在任何平台上。而且涵盖了大多数 SaaS 需求：

*   数据库: [Drizzle ORM](https://orm.drizzle.team/)
*   鉴权: [Better Auth](https://better-auth.com/)
*   支付: [Stripe](https://stripe.com/) (支付处理平台) + [Creem](https://creem.io/) (新兴支付平台)
*   邮件: [React Email](https://react.email/) + [Resend](https://resend.com/) (邮件发送服务)
*   对象存储: [S3](https://aws.amazon.com/s3/) / [R2](https://www.cloudflare.com/r2/)
*   博客: [MDX](https://mdxjs.com/) support with [Fumadocs MDX](https://fumadocs.dev/docs/mdx)
*   文档: [Fumadocs](https://fumadocs.dev/) with search
*   国际化: [Next-intl](https://next-intl.dev/)
*   暗色主题: [Next-themes](https://github.com/pacocoursey/next-themes)
*   Analytics: [vanilla-cookieconsent](https://github.com/orestbida/cookieconsent) + [GA](https://analytics.google.com/) + [umami](https://umami.is/) (开源网站分析) + [plausible](https://plausible.io/) (隐私友好分析)
*   UI/UX: [Tailwind CSS](https://tailwindcss.com/) + [Shadcn/UI](https://ui.shadcn.com/) + [Radix UI](https://www.radix-ui.com/) + [Framer Motion](https://www.framer.com/motion/)
*   State: [Zustand](https://github.com/pmndrs/zustand) + [TanStack Query](https://tanstack.com/query/latest) + [React Hook Form](https://react-hook-form.com/)
*   Type Safety: Full [TypeScript](https://www.typescriptlang.org/) + [Zod](https://zod.dev/) validation
*   Lint & Formatter: [Biome](https://biomejs.dev/)

首先稍微解释一下一些和成本无关的技术选型：

*   数据库 [Drizzle ORM](https://orm.drizzle.team/) 是一个非常**轻量级**的 ORM 库，类型友好，而且支持多种数据库，例如 PostgreSQL，MySQL，SQLite 等。最重要的是性能比 [Prisma](https://www.prisma.io/) 好，在 Edge 这类平台更有优势。
*   鉴权 [Better Auth](https://better-auth.com/) 是一个非常**全面**的鉴权库，不仅支持多种鉴权方式，例如 Email/Password，Social Login 等，还有各式各类的插件，例如 Admin 插件等，文档写的也比 [Auth.js](https://authjs.dev/) 更好。
*   博客和文档选择 [Fumadocs](https://fumadocs.dev/) ，熟悉我[开源博客项目](https://github.com/guangzhengli/nextjs-blog-template) 的都知道，我一般是使用 [content-collections](https://www.content-collections.dev/docs) 来作为 MDX 的管理和渲染。但是 [Fumadocs](https://fumadocs.dev/) 项目又支持文档功能，例如搜索，主题，渲染等，又支持 MDX 的管理渲染等，所以为了减少依赖和统一技术栈，我已经慢慢迁移到 [Fumadocs](https://fumadocs.dev/) 了。
*   Lint 和 Formatter 选择 [Biome](https://biomejs.dev/) ，没有选择默认的 EsLint + Prettier 组合，是因为使用 [Biome](https://biomejs.dev/) 使用 Rust 性能确实更好，并且因为 [Biome](https://biomejs.dev/) 合二为一，配置起来更加简单。

明确你的需求和成本
---------

首先我要明确的是独立开发穷鬼套餐面向的是盈利或者是准备盈利的产品，而不是个人项目或者是兴趣项目。

如果你是个人项目，供自己和朋友使用，那么其实无所谓，选择自己喜欢的技术栈和平台即可。毕竟大部分的平台使用额度还算是大的，例如 Vercel + Neon，如果你是搭建一个类似 Chatbot 这类项目自己使用，其实很难达到 Vercel 的免费额度上限。

如果你是准备开发一个盈利项目，或者是靠免费的产品来打出名气，转化部分客户到付费产品，那么你就需要考虑你的成本了。

在讲具体的各项成本之前，我们先讲一下如果是要选择穷鬼套餐进行 Web 开发的话，大致有三种大方向可以选择：

*   1.  使用各大云平台的免费额度，例如 [Supabase](https://supabase.com/) (后端即服务平台)，[Neon](https://neon.com/) (Serverless PostgreSQL)，[Railway](https://railway.com?referralCode=SDfuE1) (PaaS 部署平台)，[Flyio](https://fly.io/) (应用部署平台), [Zeabur](https://zeabur.com/referral?referralCode=guangzhengli) (PaaS 部署平台) 等。
    
    *   优点：完全 0 成本开启，无需自己维护服务器和备份，完全可以满足未来的增长和突发流量。
    *   缺点：免费额度有限，超出后需要付费，部分平台可能需要信用卡验证，并且只要超出免费后，大部分平台都收费挺贵的。还有部分平台免费额度不支持商业项目使用，例如 [Vercel](https://vercel.com/) (Next.js 部署平台) 的 free plan 明确不支持商业项目使用。
*   2.  完全利用 Cloudflare 平台。
    
    *   优点：Cloudflare 被国内开发者称之为赛博菩萨，免费 CDN，各种计算，存储，日志等服务便宜量大。每月 `$5`，然后几乎不需要为流量和成本担心。
*   缺点：如果要开启的话，至少需要每月 `$5` 的支出，免费额度提供的服务不够健壮和限制多。社区支持不够，坑很多，需要自己慢慢摸索。
*   3.  自托管部署，找一个便宜的 VPS 或者 VM 开启独立开发，再选择优秀的开源项目进行部署等，例如 [Dokploy](https://dokploy.com/) (自托管 PaaS 平台)，[Coolify](https://coolify.io/) (开源部署平台) 等自托管 PaaS 平台。
    
    *   优点：完全自定义，自由度高，成本低。除了自己的服务，还可以部署数据库 PostgreSQL，数据分析平台 Umami (开源网站分析工具)，邮件发送平台 [Unsend](https://github.com/unsend-dev/unsend) (开源邮件服务) 等，一站式搞定所有成本。
    *   缺点：需要自己维护服务器，时间成本高，需要考虑服务的稳定性和安全性，并且要考虑备份，监控，日志等。对于服务的增长和流量等也需要自己考虑扩容方案等。

云平台方式
-----

如果你想要选择真正的 0 成本开启，那么有且仅有选择各大云平台的免费额度，或者是参加 AWS，Azure，Google Cloud 的初创计划，会送你一大笔云资源额度，这里不讲初创公司计划。

下面是一些平台组合建议，可以参考一下。

### 平台组合建议

**入门级组合（完全免费）：** 

*   部署：Vercel（非商业项目）
*   数据库：Supabase 或 Neon
*   认证：Clerk (身份认证服务) 或 Better-Auth 自己实现
*   存储：Cloudflare R2
*   邮件：Resend
*   月成本：`$0`（在免费额度内）

**稳定运营组合（小型商业项目）：** 

*   部署：Vercel Pro
*   数据库：Neon
*   认证：Clerk Pro
*   存储：Cloudflare R2
*   邮件：Resend Pro
*   支付：Stripe 或者 Creem
*   预估月成本：`$25-100`

下面是一些云平台的免费计划的一些额度，可以参考一下。

### 部署平台

**[Vercel](https://vercel.com/)**

*   免费额度：
    *   100GB 带宽/月
    *   4 CPU-hrs/月
    *   1M 边缘网络请求/月
    *   自定义域名支持
*   付费计划：Pro `$20`/月
*   优点：Next.js 官方支持，部署速度快，全球 CDN，开发体验好，最标准的 Next.js 部署平台。
*   缺点：免费额度**不支持商业项目使用**，收费策略复杂，不注意优化容易收到“天价账单”。

**[Zeabur](https://zeabur.com/referral?referralCode=guangzhengli)**

*   免费额度：
    *   `$5` 体验额度
*   付费计划：Pro `$5`/月起
*   优点：按量付费，起步便宜，容器部署，后续流量大也可以直接在平台上购买服务器托管，享受相同服务，还可以部署数据库，Redis，Next.js 项目等，也可以直接托管自己的服务器。

**[Railway](https://railway.com?referralCode=SDfuE1)**

*   免费额度：每月 `$5` 信用额度（试用期），老用户每月 `$5` 免费，之后完全按使用付费
*   价格：按资源使用量付费，大约 `$0.000463/GB-hour`（内存），`$0.000231/vCPU-hour`，`$0.000000047683716/KB` 带宽。
*   优点：一个灵活的 PaaS 平台，支持多种语言和框架，可以部署 PostgreSQL 数据库和 Docker 容器，简单易用。
*   缺点：价格对于小项目可能偏高，流量大了后，成本上升也快。

**[Fly.io](https://fly.io/)**

*   免费政策：月账单低于 `$5` 免收费用（非官方承诺）
*   价格：shared-1x 256MB 约 `$1.94`/月，performance CPU 更贵
*   计费项目：计算时间、内存、存储、带宽
*   优点：一个支持全球部署应用的 PaaS 平台，支持多种语言和 Docker 容器。
*   缺点：小额免费政策可能随时取消

### 数据库平台

**Supabase**

*   数据库免费额度：
    *   500MB 数据库存储
    *   最大 2 个项目
    *   5GB 带宽
*   付费计划：Pro `$25`/月（包含 8GB 数据库，100GB 带宽）
*   优点：一个开源的 Backend-as-a-Service (BaaS) 平台，提供 PostgreSQL 数据库、实时功能、内置身份认证和文件存储。
*   缺点：免费版数据库存储限制较小，复杂查询可能影响性能

**Neon**

*   数据库免费额度：
    *   0.5 GiB 存储
    *   10 个项目
    *   10 个分支
    *   190 小时计算时间/月
*   付费计划：Launch `$19`/月，Scale `$69`/月
*   优点：Serverless PostgreSQL，分支功能，快速扩容
*   缺点：免费版存储限制小，计算时间限制

**Upstash (Serverless Redis/Kafka 服务)**

*   缓存免费额度：
    *   10,000 请求/天
    *   256MB 内存
*   付费计划：Pay-as-you-go `$0.2`/10万请求，固定计划 `$10-280`/月
*   优点：Serverless Redis/Kafka 服务，全球边缘部署，按需付费
*   缺点：免费版请求限制，固定计划对小项目较贵

#### 身份认证平台

**Clerk**

*   免费额度：
    *   10,000 monthly active users
    *   所有认证方式（邮箱、社交登录等）
    *   基础用户管理功能
*   付费计划：Pro `$25`/月（50,000 MAU），Enterprise 定制
*   优点：开发体验好，UI 组件丰富，多种认证方式
*   缺点：价格相对较高，依赖第三方服务

### 对象存储平台

### 对象存储平台

**[Cloudflare R2](https://developers.cloudflare.com/r2/platform/pricing/)**

*   免费额度：
    *   10GB 存储/月
    *   1,000,000 A类操作（写入）/月
    *   10,000,000 B类操作（读取）/月
    *   无带宽流量费用
*   付费价格：`$4.50` / million requests A 类操作，`$0.015` / GB 存储
*   优点：无流量费用，S3 兼容 API，价格便宜，支持全球 CDN。
*   缺点：国内访问较慢，国外无缺点。

### 邮件服务平台

**Resend**

*   免费额度：
    *   3,000 邮件/月
    *   100 邮件/天
    *   API 和 SDK 支持
*   付费计划：Pro `$20`/月（50,000 邮件），Scale `$85`/月（100,000 邮件）
*   优点：开发者友好，现代 API，模板系统，投递率高
*   缺点：免费额度相对较少，新平台稳定性待验证。

### 小结

选择云平台的免费额度开启自己的独立开发项目的优缺点很明显，无需自己去想办法和花时间实现各种功能，例如构建 newsletter 功能，邮件发送，登录注册功能等。也无需去维护服务器之类的，直接选择现成的稳定服务，然后专注于产品本身。

缺点就是一旦流量上升，超出免费额度，那么成本就会快速上升。例如使用 Vercel 每月被收成百上千刀的费用在 reddit 上吐槽也比比皆是。

选择这种模式，一定要在开始阶段就对流量和成本的计算有清晰的认知，有计划好的商业模式和盈利计划，并且做好规划。否则一个成本压过收入的独立开发项目，很难坚持下去。

当然其实我个人觉得，没有必要太担心很多人在意的流量和成本上升的问题，因为很现实的一点是，大部分的独立开发项目，在最开始很长一段时间都没有用户和流量。

只要是你的产品有人付费，控制免费用户的功能，加上做好 Next.js 的优化，例如多使用 Edge Function 和少用 Image Optimization 等，那么选择上面的云平台模式，构建一个收入大于成本的项目还是比较简单的。

对于这种模式我个人还是比较推荐的，专注产品功能，花更多时间去营销和推广，花费更少的时间精力在这些第三方服务和技术上，更加符合独立开发的哲学理念。

完全利用 Cloudflare 平台
------------------

第二种方式是完全完全利用 Cloudflare 平台，这种模式适合三种情况：

1.  一是有技术基础，愿意稍微花费时间折腾的小伙伴。
    
2.  二是适合高流量无收入的项目，想要通过免费项目和免费工具来给自己打出名气和寻找转化客户的项目。
    
3.  三是不想要担心流量和成本上升，找一个最具性价比的平台的小伙伴。
    

我认为这三种都挺适合 ALL In Cloudflare 平台，Cloudflare 的免费套餐对于商业项目来讲，还是不够稳定，特别是 workers 的 CPU 时间限制，但是它的每月 5 刀套餐包含了很多的服务，例如 Workers + KV + D1 + R2 + 等等。对于一个 Saas 或者是内容站来讲，

下面是一些 Cloudflare 平台的服务和功能，可以参考一下。

### Workers 计算平台

**[Cloudflare Workers](https://developers.cloudflare.com/workers/platform/pricing/)**

*   免费额度：
    *   100,000 per day
    *   10ms CPU time
*   付费计划 `$5` 套餐内包含 ：
    *   10 million per month, +`$0.30` per additional million
    *   30 million CPU ms per month, +`$0.02` per additional million CPU ms
*   优点：无带宽和流量费用，无需担心扩容需求，便宜
*   缺点：CPU 时间限制，非标准的 node.js 环境，某些场景需要注意技术实现

### D1 数据库

**[Cloudflare D1](https://developers.cloudflare.com/d1/platform/pricing/)**

*   免费额度：
    *   5GB 存储/月
    *   读操作：5 million / day
    *   写操作：100,000 / day
*   付费计划 `$5` 套餐内包含 ：
    *   读操作：First 25 billion / month included + `$0.001` / million rows
    *   写操作：First 50 million / month included + `$1.00` / million rows
*   优点：便宜，无带宽和流量费用，速度快，支持各类 ORM 框架
*   缺点：D1 由 SQLite 实现，在大流量的写操作业务场景中，还是选择 PostgreSQL 数据库更合适。

### KV 存储平台

**[Cloudflare KV](https://developers.cloudflare.com/kv/platform/pricing/)**

*   免费额度：
    *   读操作：100,000 / day
    *   写操作：1,000 / day
    *   1 GB
*   付费计划 `$5` 套餐内包含 ：
    *   读操作：10 million/month, + `$0.50`/million
    *   写操作：1 million/month, + `$5.00`/million
    *   1 GB, + `$0.50`/ GB-month
*   优点：便宜，无带宽和流量费用，速度快
*   缺点：KV 存储平台，适合小项目，不适合大项目。

### 对象存储平台

**[Cloudflare R2](https://developers.cloudflare.com/r2/platform/pricing/)**

*   免费额度：
    *   10GB 存储/月
    *   1,000,000 A类操作（写入）/月
    *   10,000,000 B类操作（读取）/月
    *   无带宽流量费用
*   付费价格：`$4.50` / million requests A 类操作，`$0.015` / GB 存储
*   优点：无流量费用，S3 兼容 API，价格便宜，支持全球 CDN。
*   缺点：国内访问较慢，国外无缺点。

### 小结

完全利用 Cloudflare 的模式也是我目前很多项目选择的方案，我几个项目部署在 Cloudflare 上加起来目前每月是大概几十万的访问，例如你当前访问的博客和 [NextDevKit](https://nextdevkit.com/) 项目。目前还没有超出 Cloudflare 的每月 `$5` 套餐。

并且感谢 [OpenNext Cloudflare](https://opennext.js.org/cloudflare) 项目，在 Cloudflare 上构建一个全栈的 Next.js 项目现在已经非常简单了，无缝集成 Cloudflare 的各类服务，像上面提到的 D1, KV, R2 等等服务。

并且因为 Cloudflare 的 CDN 是少有的全球免费的 CDN 服务，虽然只有国内的访问速度不快，但是对于一些面向海外的高流量项目，加上缓存策略等，是一个非常合适的选择。

### 自托管部署

第三种就是购买 VPS 或者 VM 进行自托管所有的服务，自托管的部署模式的优缺点也很明显。

优点是完全自定义，自由度高，可以完全控制自己的服务和数据。一台 VM 既可以部署自己的项目，也可以托管数据库，邮件服务，日志服务等，数据分析服务等。一站式搞定所有的成本，无需依赖第三方服务，也不用担心涨价和第三方限制。

缺点也很明显，需要自己维护服务器，时间成本高，需要考虑服务的稳定性和安全性，并且要考虑备份，监控，日志等。和前面两种模式不同的是，一旦流量上涨，需要自己考虑扩容方案，例如购买更大容量，迁移服务等。并且需要考虑服务器的稳定性，例如 DDOS 攻击，流量攻击等。

当然你可以选择一些开源的自托管 PaaS 平台来简化自己的一些工作，例如 [Dokploy](https://dokploy.com/)，[Coolify](https://coolify.io/) 等，这些项目都提供了非常多开箱即用功能。

例如 [Dokploy](https://dokploy.com/) 项目，在 VM 部署上后，它提供了非常多的开箱即用功能，例如一键部署开源模板，CICD 容器自动部署，创建 SSL 证书，自动备份，扩容等。

下面是我在 [Dokploy 模板](https://docs.dokploy.com/docs/core/templates) 上常用的一些容器服务，可以参考一下。

*   数据分析服务：Plausible (隐私友好的网站分析) + Umami (开源、隐私友好的网站分析工具)
*   邮件服务：Unsend (Resend 的开源替代品，用于自托管邮件发送)
*   数据库：PostgreSQL + Redis
*   监控服务：Uptime Kuma (开源服务监控工具)
*   备份服务：Cloudflare R2
*   自动化服务：n8n (开源工作流自动化工具，类似 Zapier)

这种模式的成本在于你的服务器成本，你可以选择稳定的大厂虚拟机，也可以找便宜的 VM 服务商。

其它成本
----

除了部署的成本外，还有一些其它的成本需要考虑，可以参考一下我下面的一些建议。

### 域名

对于一个独立开发项目，域名是必不可少的，你不可能顶着云服务提供的免费域名去宣传，例如 vercel.app 等，这不可能被 Google 等搜索引擎或者 SEO 策略优待，并且对于用户来说，也不可能信任这么一个域名去付费。

你可以通过 [tldx](https://github.com/brandonyoungdev/tldx) (域名搜索工具) 这个开源项目，搜索一个合适的域名来符合你的产品。

然后通过 [Cloudflare Domains](https://domains.cloudflare.com) 购买一个域名，`.com` 后缀的价格在 10 刀左右。

如果你要选择更便宜的购买平台，可以选择例如 [Spaceship](https://spaceship.com/) (域名注册商) 或者 [regery](https://regery.com) (域名注册商) 等平台，这些平台对于某些域名的第一年普遍要更便宜。

我个人更建议直接在 Cloudflare 上购买域名，价格每年没有什么大的波动，不会出现第一年和第二年价格相差很多的情况，而且 Cloudflare 的域名解析速度非常快，再加上需要 Cloudflare CDN 和 Cache 等功能，直接选择 Cloudflare 的域名不折腾。

### 邮件服务

邮件服务不是必须的，如果你的登录注册功能已经选择了第三方服务例如 Clerk 或者是只开启社交登录，那么邮件服务可以不考虑。

如果你需要 newsletter 功能或者邮件营销，那么可以选择像 [Resend](https://resend.com/) 或者是 [plunk](https://www.useplunk.com/) (邮件营销平台) 这样的邮件服务，集成非常方便。

虽然这些服务看起来不便宜，但是实际使用下来，邮件发送的单价其实还可以，实际上发送的邮件并没有我想象的多，并且邮件发送的稳定性也非常高，不会出现像 自己托管发送那样被封禁的情况。

如果你是重度依赖邮件服务的系统，那么就只能考虑使用 AWS SES 这样的服务，价格相对要低很多，但是需要自己处理各种情况。

或者使用自托管部署，可以考虑使用 [Unsend](https://github.com/unsend-dev/unsend) 这个开源项目 + AWS SES (邮件发送服务)，它是 Resend 的开源替代品。

### 支付平台

对于独立开发者来讲，支付平台是必须要有的，毕竟不收费还如何继续开发和支付服务器费用呢。

虽然像 [Creem.io](https://creem.io/) 和 [Lemon Squeezy](https://www.lemonsqueezy.com/) (支付处理平台) 这样的支付平台最近很出名，对于国内的独立开发者来讲很诱惑，因为不需要开国外的公司和处理各样的税务，但是我还是想要先推荐像 [Stripe](https://stripe.com/) 和 [Paddle](https://paddle.com/) (支付处理平台) 这样的成熟稳定支付平台。

像 [Stripe](https://stripe.com/) 这样的平台更加成熟，生态更加完善，各种提现和结算更加方便，只要你一旦成功使用了 Stripe 这样的成熟平台，后续几乎不需要考虑更换或者折腾。

但是我也知道对于很多独立开发的小伙伴来讲，产品还没开始建立和推广，还没有确定是否有收入，就要投入钱和时间去国外开公司，处理税务，处理各种麻烦事，确实是一个很大的负担。

所以如果你是这种情况，选择像 [Creem.io](https://creem.io/) 这样的平台也不错，就是这些平台刚起步，稳定性和社区还不是很完善，需要自己慢慢摸索。

原来博客推荐的 [Lemon Squeezy](https://www.lemonsqueezy.com/) 被 stripe 收购后，已经很长时间不接受新的用户了。

Creem 目前我知道还是有独立开发者不开公司就跑通了收款和提现的。有一些坑需要你额外注意：

一是不同于 Stripe 的坑是宽进严出，基本没有前期审核。在 Creem 中，不要随意的写你要出售的产品信息和定价。他们的审核会较为严格确保接入的作品合法合规，一旦审核失败，账户可能会被封禁，因此建议在审核前先仔细检查，如果你的产品还没有打算投入生产，切勿提交Payout Account审核。

需要按照[官方提供的清单](https://docs.creem.io/faq/account-reviews/account-reviews)，严格的查看自己的产品和提交的详细。检查你自己的产品是否符合规定，是否属于禁售的产品。只要你的产品合法合规，并且按照上述的清单打磨好你的网站和描述，是很容易能够通过的。

二是提现的时候，虽然 Creem 支持通过支付宝提现，但是支付宝需要你证明这笔收入的来源。目前通过 creem 的证明是无法通过的支付宝审核的，所以建议你申请一个 wise (国际汇款服务) 或者香港银行的卡进行提现。这个成本还是比开一个公司要低的。

最后
--

最后，本篇文章写给的是独立开发的新手，想要尝试一下能否能够成功开启独立开发之旅的小伙伴。

其实我最开始是比较讨厌穷鬼套餐这些名词的，因为这种词汇和技术实践容易把人带入到无穷的折腾中，一直在对比不同平台的价格，然后将精力和时间投入到了各种平台的学习和折腾中。

这种折腾和独立开发的精神是背道而驰的，独立开发的精神是快速迭代，快速试错，快速找到用户需求，快速找到产品市场，快速找到产品盈利模式和开启付费，需要将大把的时间投入到营销和市场中。而不是将精力和时间花费在对比不同平台的价格和学习各种技术中。

但另一方面，在和一些小伙伴聊了后，加上我自己也是小农经济思维，成本对于大部分人来说，都是比较关心的，毕竟大部分人都不想要倒贴很多💰去独立开发。

所以花费了大量的时间写下了这篇博客。

但是如果你有试错的经济能力，那么我还是强烈推荐你使用标准的一套技术栈和对应的平台，不要折腾和将时间成本花费在不需要的地方，将更多的精力花费在产品和营销上！

所以我最新的项目 [NextDevKit](https://nextdevkit.com/) 目标就是能够帮助独立开发的小伙伴，快速搭建一个完整的 Next.js 项目，并且能够快速部署到不同平台上， 例如 NextDevKit 支持三种不同的模板，可以一键部署到 Vercel，Cloudflare，Dokploy，AWS 等平台上。

让大家将精力和时间花费在产品和营销上，而不是技术和平台上。

最近两周也支持了像 [Creem.io](https://creem.io/) 支付平台和 Admin 管理后台 + 中文文档功能等，希望 NextDevKit 能够帮助到更多的小伙伴。

另外 NextDevKit 暂时不会投入时间在构建更多功能上，而是后续会写一些教程和优化文档，帮助大家快速上手熟悉 Next.js 和 NextDevKit 项目。让大家快速通过 AI 搭建自己的独立开发项目。五折优惠本来已经用完，还是决定额外放出少量名额 `NEXTDEVKIT50X`，感兴趣的小伙伴抓紧上车了。

最后，欢迎大家在下方的评论区留言，分享你的独立开发技术栈和云服务商的选择，让我们一起交流学习。本文写的时间过于仓促，难免有错误和遗漏，欢迎大家指正和补充。

*   [最新技术栈的选择](#最新技术栈的选择)
*   [明确你的需求和成本](#明确你的需求和成本)
*   [云平台方式](#云平台方式)
    *   [平台组合建议](#平台组合建议)
    *   [部署平台](#部署平台)
    *   [数据库平台](#数据库平台)
    *   [对象存储平台](#对象存储平台)
    *   [对象存储平台](#对象存储平台-1)
    *   [邮件服务平台](#邮件服务平台)
    *   [小结](#小结)
*   [完全利用 Cloudflare 平台](#完全利用-cloudflare-平台)
    *   [Workers 计算平台](#workers-计算平台)
    *   [D1 数据库](#d1-数据库)
    *   [KV 存储平台](#kv-存储平台)
    *   [对象存储平台](#对象存储平台-2)
    *   [小结](#小结-1)
    *   [自托管部署](#自托管部署)
*   [其它成本](#其它成本)
    *   [域名](#域名)
    *   [邮件服务](#邮件服务)
    *   [支付平台](#支付平台)
*   [最后](#最后)

© 2025 guangzhengli Powered by [Nextjs Blog](https://github.com/guangzhengli/nextjs-blog-template)

↑↓⇔⇧⇩