---
radar: app-radar
window: 2026-10-21 至 2026-10-28
doc: https://claude.ai/artifact/E9KDjXdiS9aAMMoXbKLeiQ
created: 2026-11-04
backfilled: true
---

# Claude 行业应用雷达 · 2026-10-21 至 2026-10-28

Oct 28, 2026 · @yangjie

## 本期概览

这一周能核实的第三方生产部署很少，收进来的三个案例（金融投顾、生命科学、政务）都来自 Anthropic 自己的页面，成效数字多为厂商或合作方自述，没有一条能算“生产在用并有独立证据”。

覆盖范围：Anthropic 官方新闻、博客、客户案例列表和研究页，以及按法律、金融、医疗、保险、客服、制造、SRE、会计、电商、咨询等行业做的媒体搜索和 AI-Weekly 周报。没有深入的是 GitHub、Hacker News 和中文社区，只做了轻量检索；客户案例列表多数没有日期，难以归入具体窗口。

剔除与存疑共 7 条，另有 4 个 Anthropic 自家产品只作背景。窗口外值得一提的一条：Barclays（[FF News](https://ffnews.com/news/barclays-scales-claude-to-upgrade-operations-and-improve-client-experience-15560521)，10 月 2 日）称其内部知识助手覆盖 16,000 多名员工，留给对应那一期再核实。

## 金融：投顾场景的连接器与技能（Claude for Financial Advisors、Invesco 连接器）

这是一套面向投资顾问的现成方案，流程设计披露得最具体，但公开材料里没有采用数据，Invesco 连接器的措辞也还是将来时，所以只能算“已发布、落地未证实”。

- **披露日期**：[Claude for Financial Advisors](https://claude.com/resources/articles/claude-for-financial-advisors) 页面标注 10 月 27 日，页脚称原文发布于 9 月 14 日、后来补充了连接器，所以按“新进展”收。Invesco 同日发布连接器公告，我读到的是 [unite.ai 的转述](https://www.unite.ai/invesco-and-anthropic-connect-portfolio-tools-for-advisors-in-claude/)。
- **业务场景**：注册投顾（RIA）做客户会前准备、会后纪要与跟进、再平衡复核、遗产与税务简报，以及对外话术的合规检查。
- **怎么搭的**：连接器加技能（skills）加一个捆绑插件，在 Cowork 的插件浏览器里安装，安装时自选启用哪些连接器；[官方页面](https://claude.com/resources/articles/claude-for-financial-advisors)列了二十多家合作方，如 Schwab 的托管数据、Addepar、Orion、SS&C Black Diamond、Wealthbox。技能放在 GitHub 仓库，可原样用或自己改。页面没有提到 Agent SDK。Claude 只起草简报，CRM 更新和客户沟通先暂存，等顾问批准；合规技能按 SEC Marketing Rule 检查对外措辞；页面建议 RIA 选带审计日志的 Enterprise 方案。
- **规模与成效**：Anthropic 页面没有给采用数字，也没有实测成效，合作方的评价是定性的（如节省时间）。Invesco 自己强调连接器仅供教育用途、不构成投资或税务建议，输出可能不准确，需要独立复核（[unite.ai](https://www.unite.ai/invesco-and-anthropic-connect-portfolio-tools-for-advisors-in-claude/)）。
- **业务真实性**：产品已发布（据 Anthropic）；实际采用情况未披露；Invesco 稿件对连接器用的是将来时，上线状态不明。
- **对你可借鉴**：页面明确写出了三个做法，可以直接参考：写动作一律先暂存、人批准后才执行；合规检查做成可单独调用的技能；审计日志作为方案的一部分提供。
- **证据等级**：读过 Anthropic 官方页（一手，厂商立场）；Invesco 部分是媒体转述。

## 生命科学：Anthropic 与六家药物研发机构的早期合作

这是研究合作，不是生产系统：Anthropic 自己说明这些工作大多仍在临床前阶段，只有个别环节更接近企业流程。

- **披露日期**：10 月 27 日，Anthropic 生命科学团队发布的 [Early progress on accelerating drug development with Claude](https://www.anthropic.com/research/early-progress-drug-development)，涉及 Generate Biomedicines、Divergence Labs、BigHat Biosciences、Enveda、The Column Group（Pleiades）和 Bristol Myers Squibb。
- **业务场景**：最像企业流程的两条是 Enveda 和 BMS。Enveda 让 Claude 读生产文档、标出质量问题并起草监管文件；BMS 用 Claude 评估早期临床试验方案并估计成功概率，页面说这条较新，计划 2027 年扩展。
- **怎么搭的**：页面提到 Claude Code、与实验室数据系统和文档系统的连接，以及一个 Claude skill。Agent 架构、SDK 或 API 用法、人工复核如何编排，页面未披露，只说明有科学家和审核人员参与，例如 Enveda 的人工审核员与 Claude 的发现做了对照。
- **规模与成效**：以下数字均是 Anthropic 页面所述，合作方的技术报告在页面里有链接，我没有打开，所以都属未核实。Enveda：Claude 找出了人工审核发现的全部 11 个问题，另外多找出 7 个，审核时间减少 89%；一份监管文件草稿用时 4 小时，人工约需 3 个月。BigHat：约 10 周内测试约 1,010 个变体，最佳版本结合力提升超过 10 倍。
- **业务真实性**：研究合作与早期试点，主要是临床前，不能当作生产在用。
- **对你可借鉴**：Enveda 的做法是让人工审核员与 Claude 对同一批文件独立审，再比较命中数、额外发现和耗时，这为自建业务 agent 提供了一个现成的评测骨架。这是我根据页面描述的归纳，页面本身没有展开评测方法。
- **证据等级**：读过官方页（一手，厂商立场），未读合作方报告。

## 政务：Anthropic 与 GSA 扩大合作与 Utah 试点

这是一份采购协议加案例汇总，不是某个系统的落地证据；能核对到第三方的细节，主要来自 Utah 的试点。

- **披露日期**：10 月 27 日，[Expanding our partnership with GSA](https://www.anthropic.com/news/expanding-partnership-gsa)。政府合作方可按 40% 折扣采购 Claude Enterprise、Claude for Government 和 API，无最低消费，范围含州、地方、部落与属地政府。
- **合规路径**：公告称 Claude for Government 为 FedRAMP High；通过 Amazon Bedrock 和 Google Vertex AI 使用的 Claude 也获 FedRAMP High 授权；Claude Enterprise 的 FedRAMP Moderate 仍在流程中。
- **点名的案例**：只有 Utah。该州技术服务部在 2026 年初做了为期四周的试点，向 10 个行政部门的 34 名开发者提供 Claude Code。80% 在 30 分钟内搭好可用环境，71% 称四周内至少省下 20 小时。这些数字来自开发者问卷与自我估计，由 Utah 官员转述，原文是 Anthropic 赞助的 [Axios 内容](https://www.axios.com/sponsored/how-claude-code-could-help-reshape-utah-government)（8 月 13 日），不是独立测量。公告里其余案例（勒索软件事件 8 分钟响应、约 900 个 API 方法两天迁移等）都没有点名，无法核实。
- **治理做法**：Utah 官员提到的是 AI 政策与培训、统一项目走向生产的“AI factory”，以及与数据隐私和安全办公室协调的风险评估（[Axios](https://www.axios.com/sponsored/how-claude-code-could-help-reshape-utah-government)）。
- **业务真实性**：Utah 是开发者场景的试点，不是面向公众的业务系统；GSA 条款是商业协议。公告称约 500 个政府机构在用、联邦文职机构用量一年增长约 20 倍，均为 Anthropic 自述，未核实。
- **对你可借鉴**：如果你的客户有政务或强监管背景，可参考两点：授权可以走云厂商通道；先试点、再用统一流程推向生产，治理先于规模化。
- **证据等级**：读过官方公告和 Axios 赞助页（均为一手或厂商立场），数字未独立核实。

## 本期共通的做法

三个案例里重复出现三种做法，但它们全部来自厂商页面，反映的是厂商选择披露的部分，不代表全貌。

- **写操作先暂存，人批准后执行**：金融投顾方案里，CRM 更新和客户沟通都先暂存等顾问批准。
- **用人工结果做评测基线**：Enveda 让人工审核员与 Claude 对照，比较发现的问题数和耗时。
- **治理先于规模化**：投顾方案配审计日志和合规技能，Utah 先做政策、培训和风险评估，再谈推向生产。

## 最值得深读的 3 个

本期案例少，这三条按“对后端业务服务的参考价值”排序，并不意味着它们已被证明有效。

1. [Claude for Financial Advisors](https://claude.com/resources/articles/claude-for-financial-advisors)：流程设计披露得最具体（审批暂存、合规技能、审计日志），也最接近你要做的业务服务。注意它没有采用数据。
2. [药物研发早期进展](https://www.anthropic.com/research/early-progress-drug-development)：Enveda 的对照评测值得看，但数字出自 Anthropic，建议去读合作方的技术报告再引用。
3. [GSA 合作公告](https://www.anthropic.com/news/expanding-partnership-gsa)加 [Utah 的 Axios 赞助页](https://www.axios.com/sponsored/how-claude-code-could-help-reshape-utah-government)：值得读的是数字的来源怎么交代、治理怎么排序，而不是成效本身。

## 被剔除与存疑

- HCLTech 加入 Claude Partner Network（10 月 21 日，[官方稿](https://claude.com/resources/articles/hcltech-joins-claude-partner-network)）：只有计划与合作层级，没有点名客户，也没有运行中的部署或数字。
- Alloy（10 月 23 日，[新闻稿](https://finance.yahoo.com/technology/ai/articles/alloy-joins-anthropics-claude-partner-160000159.html)）：付费新闻稿，未点名客户，无成效。
- Intapp 行业 agent（[转述页](https://letsdatascience.com/news/intapp-builds-industry-agents-with-claude-9f921233)）：页面只写“2 月 24 日”、没有年份，用的是将来时，日期也不在本窗口。
- DXC 保险理赔（[客户案例页](https://claude.com/customers/dxc)）：内容详实，写到了动作日志、权限分级和人工检查点，但页面没有发布日期，无法归入本窗口，留待日期核实后放进对应一期。
- Factory 的 Droids 与 COBOL 迁移（10 月 23 日）：只在 [AI-Weekly 周报](https://ai-weekly.ai/newsletter-10-27-2026)的摘要里出现，原视频我没有打开，且属于开发者工具。
- HUB International 的 Claude 部署：页面抓取失败，没能核实。
- Claude for Nonprofits（10 月 26 日）、Claude Security 持续扫描（10 月 21 日）、Claude Enterprise 的聊天与 Cowork 合并（10 月 23 日）、Claude Duet（10 月 21 日）：Anthropic 自家产品，按范围只作背景，条目见 [claude.com 博客列表](https://claude.com/blog)。

## 来源

以下是实际打开过的页面。

- [Claude for Financial Advisors](https://claude.com/resources/articles/claude-for-financial-advisors)
- [Invesco 与 Anthropic 连接器（unite.ai）](https://www.unite.ai/invesco-and-anthropic-connect-portfolio-tools-for-advisors-in-claude/)
- [Early progress on accelerating drug development with Claude](https://www.anthropic.com/research/early-progress-drug-development)
- [Expanding our partnership with GSA](https://www.anthropic.com/news/expanding-partnership-gsa)
- [Axios 赞助内容：Utah](https://www.axios.com/sponsored/how-claude-code-could-help-reshape-utah-government)
- [HCLTech 加入 Claude Partner Network](https://claude.com/resources/articles/hcltech-joins-claude-partner-network)
- [Alloy 新闻稿（Yahoo Finance）](https://finance.yahoo.com/technology/ai/articles/alloy-joins-anthropics-claude-partner-160000159.html)
- [Intapp 转述页（Let's Data Science）](https://letsdatascience.com/news/intapp-builds-industry-agents-with-claude-9f921233)
- [DXC 客户案例](https://claude.com/customers/dxc)
- [Barclays（FF News）](https://ffnews.com/news/barclays-scales-claude-to-upgrade-operations-and-improve-client-experience-15560521)
- [TCS（Coverager）](https://coverager.com/tcs-to-deploy-claude-across-insurance-banking-and-healthcare/)
- [Hanson Bridgett 新闻稿](https://www.hansonbridgett.com/press-release/hanson-bridgett-launches-claude-ai-across-legal-and-business-operations)
- [Bloomberg Law：Anthropic 法律行业新工具](https://news.bloomberglaw.com/litigation/anthropic-expands-push-into-legal-industry-with-new-ai-tools)
- [AI-Weekly 10-27](https://ai-weekly.ai/newsletter-10-27-2026)
- [anthropic.com/news](https://www.anthropic.com/news)、[claude.com/blog](https://claude.com/blog)、[claude.com/customers](https://claude.com/customers)
