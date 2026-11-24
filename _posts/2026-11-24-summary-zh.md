---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 39 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [Zhipu 发布 GLM-5.4，采用全新循环 Transformer 架构](#item-tech-news-1) ⭐️ 8.0/10
2. [Codex2api 遭遇供应链投毒，受影响版本存在后门与密钥泄露](#item-tech-news-2) ⭐️ 8.0/10
3. [Anthropic 称内部 Claude 模型发现 VP≠VNP 并公开 Lean 4 证明](#item-tech-news-3) ⭐️ 8.0/10
4. [鸿蒙终端设备量突破 1 亿台，应用服务超 46 万项](#item-tech-news-4) ⭐️ 7.0/10

**科技博客**
1. [vLLM 插件化部署与 ERNIE 5.5 Flash 推理加速方案](#item-tech-blog-1) ⭐️ 8.0/10

**财经新闻**
1. [英伟达董事会通过全票决定让黄仁勋复任首席执行官](#item-finance-news-1) ⭐️ 9.0/10
2. [美联储官员威廉姆斯称随时间推移或需进一步加息以遏制通胀](#item-finance-news-2) ⭐️ 8.0/10
3. [AI 股抛售潮冲击中国初创企业上市计划](#item-finance-news-3) ⭐️ 8.0/10
4. [上海地铁票价时隔 21 年首次调整](#item-finance-news-4) ⭐️ 7.0/10
5. [马斯克承认 SpaceX 的 AI 落后并转租算力](#item-finance-news-5) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Zhipu 发布 GLM-5.4，采用全新循环 Transformer 架构](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

中国人工智能实验室智谱（Z.ai）于 2026 年 11 月发布了 GLM-5.4 模型，主打面向广义编程的增强能力。这是该实验室首款采用循环 Transformer（Loop Transformer）架构的模型，该架构通过让一组共享权重的层运行多次来迭代精炼隐藏状态，从而在不增加参数量的情况下实现更深的网络。截至发布时，GLM-5.4 尚未以开源权重形式提供，且无法通过普通 API 访问，用户必须订阅专属的 Coding Plan 才能通过兼容 OpenAI 格式的 Responses API 调用该模型。

hackernews · foohis · 11月23日 10:06 · [社区讨论](https://news.ycombinator.com/item?id=50609685)

**「背景信息」** 传统 Transformer 模型在每次前向传递中仅顺序运行每一层一次。循环 Transformer 的出现代表了近期业界对优化大语言模型推理效率与推理深度的尝试，此前 Thinking Machines Lab 也曾于 2024 年 11 月 20 日发布采用类似机制的 Inkling 2 Mini 模型。

**「影响与兼容性」** 想要通过 API 试用 GLM-5.4 的开发者必须注册并使用 Z.ai 的 Coding Plan 订阅，其获取的 API 密钥可直接接入原有的 OpenAI 兼容端点。此外，由于生态工具更新滞后，开发者可能需要临时使用自定义或更新的命令行插件来支持该新模型。

**「社区讨论」** 社区用户对智谱公开模型技术细节的做法表示赞赏，认为循环 Transformer 是解决推理时内存带宽瓶颈和模拟类似循环结构的重要方向。不过，也有开发者指出，部分中国模型的超长思考过程虽然有利于跑分，但在处理简单任务时会显著增加完成时间。

**标签**: `#artificial intelligence`, `#machine learning`, `#large language models`, `#software engineering`, `#open source`

---

<a id="item-tech-news-2"></a>
### [Codex2api 遭遇供应链投毒，受影响版本存在后门与密钥泄露](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 8.0/10

Codex2api 仓库遭到供应链攻击，攻击者通过被黑的作者账号绕过主分支推送标签，导致 v3.1.10 至 v3.1.12 的发布版本包含后门。其中 v3.1.11 版本去掉了鉴权功能，相当于引入了无密码远程执行命令的漏洞，同时有工作流将仓库的 16 个 GitHub Actions 密钥外传，波及该账号下的至少 21 个仓库。已安装或更新过上述受影响版本的用户需立刻停用并退回至 v3.1.9 版本，同时轮换 GitHub 令牌、SSH 密钥、数据库及 DeepSeek 等所有相关密钥。

telegram · zaihuapd · 11月23日 11:21

**「背景」** 软件供应链攻击通常通过攻陷开发者账号或第三方依赖环节，在构建或发布阶段植入恶意代码，从而绕过常规代码审查。GitHub Actions 密钥与发布标签管理若缺乏严格的多因素认证或分支保护，极易成为攻击者横向渗透和窃取敏感凭证的突破口。

**「影响与建议」** 受影响仓库的维护者和使用者面临远程代码执行和敏感凭证外泄的严重安全风险，必须立即排查构建产物并撤销所有关联凭据。

**标签**: `#supply chain security`, `#software engineering`, `#github actions`, `#vulnerability`, `#incident response`

---

<a id="item-tech-news-3"></a>
### [Anthropic 称内部 Claude 模型发现 VP≠VNP 并公开 Lean 4 证明](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 8.0/10

Anthropic 于 2026 年 11 月 24 日公开了题为《VP ≠ VNP over every field》的论文及 Lean 4 形式化证明，仓库称该结果由内部研究用的 Claude 模型发现，且论文与代码均由 AI 撰写。该工作给出了哈密顿圈多项式的超多项式算术电路下界并推出 VP 是 VNP 的真子类，若经证实则可解决 Valiant 在 1979 年提出的代数复杂度猜想，但该结果仅针对算术电路且不涉及经典的 P 与 NP 问题。目前该证明已通过三条标准公理审计与独立内核 nanoda 复核（除预留文件外无 sorry），但尚无人类数学家通读，Lean 也无法自动确认形式化陈述与声称命题完全一致，附录 Q 已列出相关出入并等待独立审阅。

telegram · zaihuapd · 11月24日 06:02

**「背景」** VP 与 VNP 是代数复杂度理论中对应 P 与 NP 的核心复杂度类，由 Valiant 于 1979 年提出，旨在研究计算多项式所需的算术电路规模。Lean 4 是一种交互式定理证明器，常用于对数学定理进行机器可检查的形式化验证。

**「影响」** 如果该证明在经过人类数学家全面同行评议后被证实无误，将宣告解决困扰计算机科学界数十年的代数复杂度猜想，并标志着大语言模型在尖端数学自动推理与形式化证明领域取得重大突破。

**标签**: `#Artificial Intelligence`, `#Automated Reasoning`, `#Computer Science`, `#Mathematics`, `#Open Source`

---

<a id="item-tech-news-4"></a>
### [鸿蒙终端设备量突破 1 亿台，应用服务超 46 万项](https://www.xinhuanet.com/20261124/68842538167d4e59a875056d5eb885ad/c.html) ⭐️ 7.0/10

华为终端有限公司宣布，搭载 HarmonyOS 5、6、7 的手机、平板和电脑设备数量已突破 1 亿台。目前该系统可获取的应用和服务超过 46 万项，注册开发者超过 1200 万人，开源鸿蒙也已汇聚 1.4 万余名贡献者并形成 120 余个行业发行版。

telegram · zaihuapd · 11月24日 01:46

**「背景」** 鸿蒙操作系统自 2019 年首次发布以来，于 2024 年 10 月推出了原生鸿蒙版本，并在随后的发展中逐步构建起包含设备终端、开发者生态与行业发行版的完整体系。

**「影响」** 设备数量突破 1 亿台标志着鸿蒙生态在终端用户规模和应用服务供给上达到了新的阶段，开发者和合作伙伴的持续加入将进一步推动相关应用与功能的集成调用。

**标签**: `#HarmonyOS`, `#Operating Systems`, `#Mobile Development`, `#Industry News`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [vLLM 插件化部署与 ERNIE 5.5 Flash 推理加速方案](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 8.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** 百度 ERNIE 团队与 vLLM 团队合作，针对拥有 280B 总参数及 14B 激活参数的稀疏混合专家模型 ERNIE 5.5 Flash Preview 实现了 Day-0 支持。该模型支持百万级上下文、长程 Agent 任务及思考能力，但其复杂的注意力机制与稀疏 MoE 结构若采用常规、分步的算子实现，会带来严重的内存带宽瓶颈与中间张量开销。

**「方案」** 该方案通过独立的 vLLM-ERNIE 插件与一系列极致的算子融合实现了高效推理加速。作者针对 VHA 跨头混合、Multi-Router Latent MoE、MultiMax 输出头以及门控注意力等新结构设计了专用融合内核，并于加载时将参数进行预折叠，使内核运行速度比朴素实现快 1.55 倍至 6.53 倍。同时，方案引入了通过动态头路由降低计算开销的 FlashIndexer 加速、采用量化感知训练的 MXFP4 \(W4A8\) 专家量化，以及能实现较高接受率的多阶段 DSpark 投机解码。整个插件通过标准 entrypoint 动态注册至 vLLM 中，在无需修改官方核心代码或维护繁琐分支的前提下，保留了前缀缓存和 OpenAI 兼容服务器等全部原生特性。

**「启示」** 该研究表明，利用独立的 Python 插件与深度定制的算子融合技术，可以在不破坏主流服务框架架构的前提下，为超大规模稀疏 MoE 模型提供灵活且高效的 Day-0 生产级推理支持。

**标签**: `#vLLM`, `#Model Serving`, `#MoE`, `#Kernel Fusion`, `#Speculative Decoding`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [英伟达董事会通过全票决定让黄仁勋复任首席执行官](https://www.cnbc.com/amp/2026/11/23/trump-nvidia-jensen-huang.html) ⭐️ 9.0/10

据彭博社报道，在收到美国总统特朗普的政治压力后，英伟达董事会在未咨询高管层的情况下于 11 月 22 日决定让黄仁勋复任总裁兼首席执行官。英伟达官方随后宣布董事会已全票通过该任命，临时首席执行官科莱特·克雷斯将继续担任首席财务官。

telegram · zaihuapd · 11月23日 17:59

**「背景」** 黄仁勋此前于 11 月 12 日离职，引发了市场抛售并导致标普 500 指数等主要股指在此后跌入回调区间。

**「影响」** 黄仁勋的复职消息带动美国股市主要平均指数在周一出现反弹，暂时缓解了投资者的抛售压力。

**标签**: `#Nvidia`, `#Jensen Huang`, `#Corporate Governance`, `#US Politics`

---

<a id="item-finance-news-2"></a>
### [美联储官员威廉姆斯称随时间推移或需进一步加息以遏制通胀](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 8.0/10

纽约联邦储备银行行长约翰·威廉姆斯（John Williams）于 2026 年 11 月表示，随着经济持续增长， policymakers（政策制定者）未来可能需要采取进一步的利率调整行动，以将通胀率可持续地降至 2%的官方目标。

rss · CNBC Finance · 11月23日 21:02

**「背景」** 美联储通常通过调整基准利率（即金融机构之间的短期借贷成本）来控制通货膨胀和促进就业，而目前的利率目标区间在 3.75%至 4%之间。

**标签**: `#Federal Reserve`, `#Interest Rates`, `#Inflation`, `#Monetary Policy`, `#John Williams`

---

<a id="item-finance-news-3"></a>
### [AI 股抛售潮冲击中国初创企业上市计划](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

受 Anthropic 创纪录上市引发的全球科技股抛售潮影响，中国 AI 初创企业 DeepSeek、月之暗面和阶跃星辰的上市计划与估值蒙上阴影；其中中国科技股自 6 月底以来累计蒸发 1.7 万亿美元，智谱从 6 月高点跌超 85%。

telegram · zaihuapd · 11月23日 09:31

**「背景」** Anthropic 完成了 1195 亿美元的首次公开募股（IPO，即公司首次向公众发行股票募集资金），成为本轮全球科技股剧烈震荡的导火索。

**标签**: `#Artificial Intelligence`, `#IPO`, `#Stock Market`, `#Venture Capital`, `#Technology`

---

<a id="item-finance-news-4"></a>
### [上海地铁票价时隔 21 年首次调整](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

新华社报道称，上海地铁将于 2026 年 12 月 1 日起实施时隔 21 年的首次票价调整，引入按里程计价的新方案并推出计次票与满额九折等优惠举措。

telegram · zaihuapd · 11月23日 10:45

**「背景」** 上海轨道交通上一次调整票价是在 21 年前，此次新方案将起乘价定为 3 元（0 至 4 公里），并针对高频出行人群推出了多档计次票和当月消费满 90 元享 9 折的优惠。

**「影响」** 此次票价及优惠政策的调整将直接影响上海地铁的日常通勤乘客，并借助计次票和阶梯折扣减轻高频出行人群的经济负担。

**标签**: `#Transportation`, `#Public Policy`, `#Shanghai`, `#Consumer Prices`, `#Infrastructure`

---

<a id="item-finance-news-5"></a>
### [马斯克承认 SpaceX 的 AI 落后并转租算力](https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html) ⭐️ 7.0/10

据《纽约时报》11 月 23 日报道，马斯克承认 SpaceX 的人工智能（AI，让计算机模拟人类智能的技术）研发落后，该公司自今年 5 月起将数据中心的大量算力（处理数据的计算能力）出租给 Anthropic 和 Google 等公司，实现每月数十亿美元的收入。

telegram · zaihuapd · 11月24日 02:06

**「背景」** 在人工智能技术快速发展的背景下，部分企业因自研进展不及预期，转向通过出租闲置或富余的硬件资源来获取商业回报。

**「影响」** 算力租赁业务为 SpaceX 带来巨额月度收入，同时也为 Anthropic 和 Google 等竞争对手提供了发展人工智能所需的计算资源支持。

**标签**: `#SpaceX`, `#Artificial Intelligence`, `#Cloud Computing`, `#Elon Musk`, `#Anthropic`

---