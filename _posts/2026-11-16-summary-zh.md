---
layout: default
title: "Horizon Summary: 2026-11-16 (ZH)"
date: 2026-11-16
lang: zh
---

> 从 36 条内容中筛选出 8 条重要资讯。

---

**科技新闻**
1. [Meta FAIR 与 NYU 研究表明多模态模型视觉编码器预训练可选但独立视觉参数必不可少](#item-tech-news-1) ⭐️ 8.0/10
2. [开发者推出针对 B300 GPU 的 cudaMemcpy 加速工具](#item-tech-news-2) ⭐️ 8.0/10
3. [美团开源 1.6 万亿参数智能体模型 LongCat-2.5](#item-tech-news-3) ⭐️ 8.0/10
4. [理解现代大型语言模型中的位置编码](#item-tech-news-4) ⭐️ 7.0/10
5. [Protomaps 让开发者能够以低成本轻松自托管地图瓦片](#item-tech-news-5) ⭐️ 7.0/10

**财经新闻**
1. [中美俄领导人将在深圳举行首次三方会晤](#item-finance-news-1) ⭐️ 8.0/10
2. [部分电动自行车认证暂停导致上牌受阻](#item-finance-news-2) ⭐️ 7.0/10
3. [美法官驳回美光三星等 DRAM 价格操纵案撤诉动议](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Meta FAIR 与 NYU 研究表明多模态模型视觉编码器预训练可选但独立视觉参数必不可少](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

来自 Meta FAIR 和纽约大学（NYU）的研究人员通过从头训练 200 多个多模态大语言模型，系统评估了视觉编码器预 training、参数分配和放置位置等设计选择。研究发现，采用对比学习、自监督或图像描述等四种目标进行单独预训练的视觉编码器，其效果在同等计算预算下最多只能与从头训练的编码器持平，表明视觉编码器预训练是可选的。然而，模型评估显示没有视觉参数的编码器方案在各个尺寸上均落后，且需要约 3 倍的计算量才能追赶，证明专用的视觉参数不可或缺。此外，将视觉权重作为“In-fusion”注入大语言模型前 8 层的方法表现与独立编码器相当，并将首字延迟降低了约 13%，证明将视觉组件置于大语言模型之前也是可选的。

reddit · r/MachineLearning · /u/trungh98 · 11月15日 17:38

**「背景」** 当前不同实验室在多模态大语言模型的视觉编码器架构设计上存在分歧，部分模型放弃了独立编码器，部分模型从头训练，还有部分模型则重新引入了预训练编码器。由于已发布模型的训练数据、计算资源及各项设计存在差异，业界此前一直难以通过公开模型直接厘清视觉编码器预训练与独立参数的具体作用。

**标签**: `#artificial intelligence`, `#machine learning`, `#multimodal models`, `#computer vision`, `#research`

---

<a id="item-tech-news-2"></a>
### [开发者推出针对 B300 GPU 的 cudaMemcpy 加速工具](https://www.reddit.com/r/MachineLearning/comments/1xx2n25/making_cudamemcpy_5x_faster_on_a_b300_p/) ⭐️ 8.0/10

一名开发者开发了一款全新的调优工具，能够在 B300 GPU 上将 cudaMemcpy 的可分页内存传输速度提升 5 倍。实测在复制 1GB 张量时，传输带宽从默认的 10.2 GB/s 提高到了 51.5 GB/s。该工具目前已开源并发布了配套博客与代码实现。

reddit · r/MachineLearning · /u/makneeee · 11月15日 18:20

**「背景」** 在 CUDA 编程中，cudaMemcpy 负责在主机内存与 GPU 显存之间复制数据。默认情况下，针对可分页内存（pageable memory）的传输往往受到 PCIe 带宽和系统开销的限制，难以达到硬件的潜在性能上限。

**「影响」** 使用该工具的开发者和机器学习工程师可以显著减少将非固定主机内存（pageable memory）传输到 B300 GPU 时的等待时间，从而缓解数据传输瓶颈。

**标签**: `#CUDA`, `#GPU`, `#Hardware`, `#Machine Learning Systems`, `#Performance Optimization`

---

<a id="item-tech-news-3"></a>
### [美团开源 1.6 万亿参数智能体模型 LongCat-2.5](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

美团旗下的 LongCat 团队开源了 1.6 万亿参数的智能体模型 LongCat-2.5 及其权重，采用 MIT 许可证支持商用。官方称该模型在训练过程中全程使用中国产的华为升腾加速卡，未使用任何英伟达 GPU。该模型专为多步骤自主任务（尤其是编程任务）设计，每个 token 激活约 480 亿参数，支持文本、图像与视频输入，在 Terminal Bench v2.1 上取得了 88.4 的得分。

telegram · zaihuapd · 11月15日 11:08

**「背景」** 近年来，大语言模型与智能体系统的训练高度依赖英伟达的 GPU 硬件生态。随着供应链限制和技术发展，国内科技企业正积极探索使用本土 AI 芯片进行大规模模型训练的可行性。

**「影响」** 该模型的开源证明了完全依赖国产芯片训练超大规模、多模态智能体模型的可行性，为开发者和企业在构建 AI 应用时提供了脱离英伟达硬件生态的新选择。

**标签**: `#artificial intelligence`, `#open source`, `#hardware`, `#machine learning`, `#ai agents`

---

<a id="item-tech-news-4"></a>
### [理解现代大型语言模型中的位置编码](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 7.0/10

Sebastian Raschka 发布了一篇关于现代大型语言模型中位置编码实现与应用的技术解析文章。文章详细探讨了位置编码在各类大模型架构中的工作原理及其具体用法。该技术对于帮助模型理解文本中的词序至关重要。

hackernews · vismit2000 · 11月15日 12:14 · [社区讨论](https://news.ycombinator.com/item?id=50506376)

**「背景」** 由于 Transformer 架构本身具有排列不变性，无法天然感知输入序列中词语的前后顺序，因此必须引入位置编码来为模型提供序列的相对或绝对位置信息。

**「社区讨论」** 有评论指出，该文章主要侧重于代码实现层面，若要彻底理解位置编码，还需深入群论等底层数学理论，例如将旋转位置编码视为平移群的表示。

**标签**: `#artificial intelligence`, `#machine learning`, `#large language models`, `#deep learning`

---

<a id="item-tech-news-5"></a>
### [Protomaps 让开发者能够以低成本轻松自托管地图瓦片](https://bruceroettgers.eu/blog/protomaps/) ⭐️ 7.0/10

博客文章探讨了 Protomaps 如何使开发者能够以实惠且切实可行的方式自托管地图瓦片。相比传统的商业地图服务，该方案显著降低了基础设施成本和运维门槛。

hackernews · bcye · 11月15日 19:26 · [社区讨论](https://news.ycombinator.com/item?id=50509837)

**「背景」** Protomaps 采用将全球地图打包为单一静态文件（PMTiles 格式）的方案，允许开发者将其部署在云存储上，从而摆脱了传统的自定义切片后端或第三方地图服务商的依赖。

**「影响」** 开发者和小型项目团队可以利用自托管地图方案摆脱高昂的商业地图 API 费用，并更好地掌控隐私与访问控制。

**「社区讨论」** 评论者指出基础底图体积较小、适合低成本存储和托管，但高分辨率卫星影像的存储和带宽成本在较高缩放级别下仍会急剧上升。此外，部分讨论还提到了 OpenFreeMap 等可供免费使用的类似替代项目。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://protomaps.com/">Protomaps - The open source map in a file</a></li>
<li><a href="https://github.com/protomaps/PMTiles">GitHub - protomaps/PMTiles: Pyramids of map tiles in a single ...</a></li>
<li><a href="https://docs.protomaps.com/pmtiles/">PMTiles Concepts | Protomaps Docs</a></li>

</ul>
</details>

**标签**: `#mapping`, `#self-hosting`, `#open-source`, `#web-development`, `#infrastructure`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [中美俄领导人将在深圳举行首次三方会晤](https://apnews.com/article/trump-xi-putin-summit-china-5fe92253ef38100bae913834a9b74d72) ⭐️ 8.0/10

中国外交部发言人宣布，中国、美国和俄罗斯三国领导人计划于 11 月 19 日在深圳亚太经合组织（APEC）峰会场边举行首次专门的三方会晤。

telegram · zaihuapd · 11月16日 01:38

**「背景」** 此次会晤在亚太经合组织（APEC，促进亚太地区经济增长和合作的政府间论坛）峰会期间举行，并不属于该峰会的正式议程。

**「影响」** 全球市场和国际关系投资者及观察人士正密切关注这场历史性会晤，以评估其对大国地缘政治格局的潜在影响。

**标签**: `#Geopolitics`, `#APEC`, `#US-China-Russia`, `#International Relations`

---

<a id="item-finance-news-2"></a>
### [部分电动自行车认证暂停导致上牌受阻](https://www.peopleapp.com/column/30053564254-500007786629) ⭐️ 7.0/10

广州和武汉等地的消费者购买九号、雅迪等品牌的电动自行车后，因车辆的 3C 认证证书被暂停而无法办理上牌登记。市场监管总局此前检查发现相关企业存在更换关键部件和预留解限空间等问题，各品牌客服表示目前尚无证书恢复时间表。

telegram · zaihuapd · 11月15日 06:08

**「背景」** 3C 认证是指中国强制性产品认证制度，是保障消费者安全的重要产品合规审查。自 9 月底起多地认证数据出现异常，随着 11 月 1 日新版规则实施，“一车一池一充一码”的证后监管进一步收紧。

**「影响」** 购买了涉事品牌电动自行车的消费者面临无法正常上牌上路的困境，部分门店也因拒绝退货引发消费纠纷。

**标签**: `#Electric Bicycles`, `#Regulatory Compliance`, `#Consumer Protection`, `#Market Regulation`

---

<a id="item-finance-news-3"></a>
### [美法官驳回美光三星等 DRAM 价格操纵案撤诉动议](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 7.0/10

美国法官驳回了美光、三星和 SK 海力士要求撤销 DRAM（动态随机存取存储器，一种常见的计算机内存芯片）价格操纵集体诉讼的动议，认为原告关于供应受限和串通的证据合理。

telegram · zaihuapd · 11月15日 16:39

**「背景」** 原告为 17 名个人与小企业，指控这三家内存芯片制造商在一年内四次采取平行行动限制供应，导致芯片价格上涨多达 500%。

**「影响」** 随着法院驳回撤诉动议，美光、三星和 SK 海力士等芯片制造商面临进一步的法律诉讼与合规压力。

**标签**: `#antitrust`, `#semiconductors`, `#DRAM`, `#legal`, `#tech industry`

---