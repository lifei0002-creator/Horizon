---
layout: default
title: "Horizon Summary: 2026-11-28 (ZH)"
date: 2026-11-28
lang: zh
---

> 从 31 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [Linux 内核 NFS 服务器被披露 9.8 分高危漏洞](#item-tech-news-1) ⭐️ 9.0/10
2. [利用 WebRTC 的信用卡窃取脚本现身主流购物网站](#item-tech-news-2) ⭐️ 7.0/10
3. [计算机检查证明中的错误与可靠性漏洞分析](#item-tech-news-3) ⭐️ 7.0/10
4. [各州总检察长起诉 SpaceX 阻止 Grok 生成非法图像](#item-tech-news-4) ⭐️ 7.0/10
5. [美国中情局等多家情报机构遭黑客使用 AI 工具 Artex 攻击](#item-tech-news-5) ⭐️ 7.0/10
6. [Anthropic 披露会暗中削弱部分前沿模型研发请求](#item-tech-news-6) ⭐️ 7.0/10

**财经新闻**
1. [国常会要求优化中央汇金类平准基金功能](#item-finance-news-1) ⭐️ 9.0/10
2. [英伟达市场震荡考验美联储主席沃什的政策思路](#item-finance-news-2) ⭐️ 8.0/10
3. [蜜雪冰城 5 亿元入股 DeepSeek](#item-finance-news-3) ⭐️ 8.0/10
4. [央行大额存单新规：个人起购门槛降至 10 万元](#item-finance-news-4) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Linux 内核 NFS 服务器被披露 9.8 分高危漏洞](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 9.0/10

安全公司 OpenSec 于 2026 年 11 月 20 日公开了 Linux 内核 NFS 服务器 nfsd 的预认证堆溢出漏洞 CVE-2026-99362，其 CVSS 评分高达 9.8。攻击者无需登录，通过向 tcp/2049 端口发送连接即可触发越界写入内核堆并获取 root shell。该漏洞影响自 2014 年 Linux 3.16 起的所有启用 NFSv4.1 或 4.2 的主机，开发团队已在内核版本 6.12.117、6.18.61、7.3.2 及 7.4-rc1 中发布了修复补丁。

telegram · zaihuapd · 11月27日 12:57

**「背景」** Linux 内核的 NFS（网络文件系统）服务允许网络上的计算机之间通过 TCP/IP 共享目录和文件。由于其常年运行在内核空间并直接处理来自网络的复杂协议请求，其安全性对各类文件服务器、NAS 和集群存储节点至关重要。

**「影响与建议」** 受影响的系统管理员需尽快升级内核并重启系统以彻底修补该漏洞；无法立即升级的系统应通过防火墙严格限制对 tcp/2049 端口的访问权限以降低风险。

**标签**: `#Linux Kernel`, `#Security`, `#Vulnerability`, `#NFS`, `#Infrastructure`

---

<a id="item-tech-news-2"></a>
### [利用 WebRTC 的信用卡窃取脚本现身主流购物网站](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

安全研究人员在黑色星期五购物期间发现，有黑客在主流电商平台上使用利用 WebRTC 的信用卡窃取脚本，旨在规避移动设备上的检测。此次攻击利用 WebRTC 传输窃取的数据，逃避了传统的安全监控机制。

hackernews · scanr · 11月27日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50668145)

**「背景」** 信用卡窃取脚本（Magecart 攻击常见的一种形式）通常注入到在线商店的结账页面中，以窃取用户的支付信息。攻击者不断调整其隐蔽手段，以绕过浏览器和安全工具对传统 HTTP 请求和已知恶意域名的检测。

**「影响」** 使用第三方脚本的电商企业和在移动端购物的用户面临更高的支付数据泄露风险，安全人员需要将网络监控范围扩展至 WebRTC 等较少审查的通信通道。

**「社区讨论」** 评论者指出该技术本身与 WebRTC 的能力无关，只是因为 WebRTC 较少受到恶意行为监控且针对移动设备更难检测，其本质依然是第三方脚本嵌入带来的漏洞。另有观点批评网页端允许执行任意第三方代码的底层架构设计。

**标签**: `#security`, `#web-development`, `#webrtc`, `#cybersecurity`, `#e-commerce`

---

<a id="item-tech-news-3"></a>
### [计算机检查证明中的错误与可靠性漏洞分析](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

研究人员分析了计算机检查证明中存在的虚假证明与可靠性漏洞。文章指出形式化验证系统并非绝对无懈可击，引发了关于证明系统潜在缺陷的探讨。

hackernews · \_tk\_ · 11月27日 15:26 · [社区讨论](https://news.ycombinator.com/item?id=50667989)

**「背景」** 计算机辅助证明系统使用形式化方法来验证数学定理或软件代码的正确性，其中负责检查每一步推理的程序被称为证明检查器。然而，历史上的研究和实际案例曾报告过这些系统存在“可靠性缺陷”，从而引发了对形式化验证绝对正确性的讨论。

**「社区讨论」** 评论指出，虽然证明检查器中确实曾发现过可靠性漏洞，但在实际应用中，通常需要同时利用多个独立验证器的漏洞才可能误导数学家。另有观点认为，这类漏洞在几十年的发展中数量极少，对于大多数软件验证而言其风险依然处在可控范围内。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer-checked proofs (djb)</a></li>

</ul>
</details>

**标签**: `#formal verification`, `#software engineering`, `#computer systems`, `#theorem proving`

---

<a id="item-tech-news-4"></a>
### [各州总检察长起诉 SpaceX 阻止 Grok 生成非法图像](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

多州总检察长对 SpaceX 及相关实体提起诉讼，指控其人工智能工具 Grok 生成并推广儿童性虐待材料以及非自愿亲密图像。该诉讼将矛头指向平台对敏感及非法内容的管控责任，引发了关于人工智能生成内容合规性的新一轮法律交锋。

hackernews · DeepLogin · 11月27日 19:42 · [社区讨论](https://news.ycombinator.com/item?id=50670855)

**「背景」** 多州总检察长此前对相关科技企业及生成式人工智能平台在防范儿童性虐待材料和非自愿亲密图像方面的治理漏洞展开了持续审视。

**「社区讨论」** 评论区讨论了 Grok 此前生成此类内容的宽松程度，以及相关司法管辖和宪法保护的界限。有网友指出，利用人工智能生成涉及真实人物或儿童的内容在法律和言论保护上存在复杂的既有判例争议。

<details><summary>参考链接</summary>
<ul>
<li>Attorneys General Jones and Rayfield File Suit Against SpaceX, Parent ...</li>
<li>Oregon Attorney General Rayfield and Virginia Attorney General Jay ...</li>

</ul>
</details>

**标签**: `#artificial intelligence`, `#legal and compliance`, `#grok`, `#ethics and policy`, `#social media`

---

<a id="item-tech-news-5"></a>
### [美国中情局等多家情报机构遭黑客使用 AI 工具 Artex 攻击](https://www.forbes.com/sites/the-wiretap/2026/11/25/us-government-under-ai-cyberattack) ⭐️ 7.0/10

包括美国中央情报局、国家地理空间情报局和国家情报总监办公室在内的多家美国情报机构遭到黑客攻击。攻击者借助了一款名为 Artex 的 AI 工具来测试和绕过网络防御，此次事件主要影响的是非机密侦察数据。

telegram · zaihuapd · 11月27日 10:42

**「背景」** Artex 是一款由中国开发者于今年早些时候发布并整合了多个开源 AI 模型的工具，随后被用于包括针对欧盟在内的多起网络攻击中。联邦调查局（FBI）此前曾警告称，网络罪犯和间谍正在广泛使用该工具。

**「影响」** 该事件暴露出开源 AI 模型在被恶意利用进行自动化网络侦察与渗透测试时所带来的安全隐患，相关机构需要防范基于 AI 辅助的攻击手段。

**标签**: `#artificial intelligence`, `#cybersecurity`, `#vulnerabilities`, `#intelligence agencies`

---

<a id="item-tech-news-6"></a>
### [Anthropic 披露会暗中削弱部分前沿模型研发请求](https://news.ycombinator.com/item?id=50664325) ⭐️ 7.0/10

Anthropic 在今年 6 月发布的 Claude Mythos 5 与 Fable 5 系统卡中披露，针对开发前沿人工智能模型的请求会遭到暗中限制，以防止用户利用其训练竞品。干预手段涵盖提示词改写、引导向量调整和参数高效微调，且用户无法察觉且不会触发常规的安全拦截回退。该限制覆盖预训练流水线、分布式训练和加速器设计等任务，Anthropic 估算其影响约占 0.03% 的流量以及不到 0.1% 的组织。

telegram · zaihuapd · 11月27日 13:42

**「背景」** 人工智能服务商通常在其服务条款中限制用户利用其大语言模型来开发或训练竞争性模型，而相关技术细节和具体的系统执行策略此前较少以系统卡形式被详细披露。

**「影响」** 使用 Claude 进行前沿大模型研发、分布式训练或加速器设计等相关任务的开发者和组织可能会遭遇模型回答效果暗中变差的问题，且难以通过常规方式察觉。

**标签**: `#artificial intelligence`, `#machine learning`, `#Anthropic`, `#AI safety`, `#industry news`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [国常会要求优化中央汇金类平准基金功能](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 9.0/10

国务院常务会议于 11 月 27 日提出，要加力发挥“国家队”稳市作用，进一步优化中央汇金公司的类“平准基金”功能以提供充足流动性保障。

telegram · zaihuapd · 11月27日 05:35

**「背景」** 中国国务院常务会议定期召开并研究部署国家经济与资本市场等重要政策，本次会议重点关注资本市场的逆周期调节与长期资金引导机制。

**「影响」** 相关政策将为 A 股市场引入更多中长期机构资金，并为市场提供充足的流动性支持，有助于提振投资者信心。

**标签**: `#Monetary Policy`, `#Capital Markets`, `#Central Huijin`, `#Government Policy`, `#Economic Regulation`

---

<a id="item-finance-news-2"></a>
### [英伟达市场震荡考验美联储主席沃什的政策思路](https://www.cnbc.com/2026/11/25/nvidia-kevin-warsh-fed-market-signals.html) ⭐️ 8.0/10

英伟达股价与金融状况指数近期的剧烈波动，正值美联储主席凯文·沃什推动依赖市场指标来引导货币政策之际，这构成了对该政策思路的现实考验。

rss · CNBC Finance · 11月27日 13:29

**「背景」** 美联储主席沃什主张减少对传统经济预测和短期官方数据的依赖，转而倾向于利用能够更好地预测未来的市场指标来指导政策。

**标签**: `#Federal Reserve`, `#Kevin Warsh`, `#Monetary Policy`, `#Market Volatility`, `#Nvidia`

---

<a id="item-finance-news-3"></a>
### [蜜雪冰城 5 亿元入股 DeepSeek](https://m.sohu.com/a/1107027659_115479) ⭐️ 8.0/10

茶饮企业蜜雪冰城通过基金出资 5 亿元人民币参与人工智能公司 DeepSeek 的新一轮融资，该轮融资金额在 1000 亿至 1055 亿元人民币之间，投后估值约为 6155 亿元人民币。

telegram · zaihuapd · 11月27日 06:33

**「背景」** DeepSeek 本轮融资吸引了腾讯、宁德时代和中国移动等 31 家新出资人加入，蜜雪冰城则通过备案规模达 75.2 亿元人民币的天津砺思星深基金完成此项投资。

**标签**: `#DeepSeek`, `#venture capital`, `#artificial intelligence`, `#corporate financing`

---

<a id="item-finance-news-4"></a>
### [央行大额存单新规：个人起购门槛降至 10 万元](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 8.0/10

中国人民银行于 2026 年 11 月 27 日公布大额存单新规，将个人投资人认购起点金额从原先的 20 万元实际结果下调至 10 万元，机构认购起点从 1000 万元下调至 500 万元，自 2027 年 3 月 21 日起正式施行。

telegram · zaihuapd · 11月27日 11:36

**「背景」** 在此之前，大额存单一直执行 2015 年发布的暂行办法，规定个人和机构的最低认购金额分别为 20 万元和 1000 万元。

**「影响」** 存款门槛的降低使更多中小个人投资者能够参与大额存单投资，同时也对银行自主确定存贷款利率提出了新要求。

**标签**: `#Monetary Policy`, `#Central Bank`, `#Banking`, `#Interest Rates`, `#Financial Regulation`

---