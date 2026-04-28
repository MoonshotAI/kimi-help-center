---
title: "Agent 模式概述"
slug: "agent-overview"
order: 1
extract_headings: false
preview: true
preview_content: "了解 Kimi Agent 模式的工作方式、使用入口与适用场景。"
---

<SeoMeta
  title="Kimi Agent 模式是什么？功能介绍与使用入口 - Kimi 帮助中心"
  description="了解 Kimi Agent 模式的工作原理、核心能力与适用场景。Kimi Agent 通过多轮推理和 20 多种工具自主完成复杂任务，支持文档生成、代码开发、数据分析等全栈工作流。"
/>

# Kimi Agent 模式介绍

## Kimi Agent 发展历程

2025年9月5日，Moonshot AI发布了Kimi K2，这是一款先进的混合专家模型，拥有320亿激活参数和1万亿总参数（详情请见官网：[Kimi K2](https://www.kimi.com/blog/kimi-k2)）。Kimi K2在自主编程（Agentic Coding）、工具调用（Tool Use）和数学推理（Math & Reasoning）三大核心能力维度的基准性能测试中表现出色，成为构建通用Agent能力的坚实基础。

秉承“**模型即产品**”的理念，Kimi通过端到端强化学习技术，将Kimi K2训练为原生Agent，赋予其对20多种工具的熟练使用能力，包括文件系统、浏览器、终端、代码生成、图片生成、音频生成等。

2025年9月26日，Kimi发布了首个Agent 产品模式——「OK Computer」。与传统的人工设计流程和预设任务工作流不同，Kimi的Agent模式通过自主构建“如何完成一项复杂任务”的内在知识体系，还能够根据不同情境实时调整，自动选择最合适的工具和策略，以确保复杂任务的高效执行。

在Agent模式下，Kimi通过多轮推理和多次工具调用，自主规划并完成从需求调研、产品方案、交互设计、前端开发到最终交付的全过程。Kimi Agent帮助用户成为全栈知识工作者，处理更为复杂的任务。无论是技术开发、产品设计，还是日常办公任务，Kimi Agent都能提供高效的智能支持。

2026年1月27日，Moonshot AI正式发布了Kimi K2.5，Kimi K2.5是迄今为止功能最强大的开源模型，进一步扩展了Agent模式的应用。基准测评表明，Kimi K2.5在办公场景下的实际输出质量和工具调用效率显著提升，特别是在结构化输出（如Word文档、Excel表格、幻灯片设计）方面展现了端到端的处理能力。Kimi Agent学会了使用Office软件的核心技能，并支持端到端输出文件：

- Word智能排版与修改审阅；
- PDF视觉设计与图文混排；
- Excel数据分析与金融建模；
- PPT自动生成与视觉叙事。

2026年4月20日，Moonshot AI发布并开源 Kimi K2.6 模型，带来行业领先（state-of-the-art）的代码、长程任务执行和 Agent 集群能力。

Kimi K2.6 的通用 Agent、代码、视觉理解等综合能力得到全面提升，其中在博士级难度的完整版人类最后的考试（Humanity's Last Exam）、在考察模型真实软件工程能力的 SWE-Bench Pro、评估 Agent 深度检索能力的 DeepSearchQA 等基准测试中均取得行业领先的成绩，持平或优于 GPT-5.4、Claude Opus 4.6 和 Gemini 3.1 Pro等闭源模型。

Kimi K2.6 是我们迄今最强的代码模型，其长程编码能力也得到显著提升，在测试中可以不间断编码 13 小时，编写或修改超过 4000 行代码，完成复杂系统的开发和优化。通过将代码与视觉能力的深度融合，K2.6 将代码驱动的设计能力提升到了新高度，可以交付极具设计创意的专业级 Web 应用。

Kimi K2.6 大幅增强了 Agent 自主化执行能力，帮助我们进一步扩展 Agent 的能力范围。由 K2.6 模型驱动的「Agent 集群」架构迎来一次大升级，现在支持 300 个子 Agent 并行完成 4000 个协作步骤，实现更大规模的并行化，同时任务完成度和交付质量相比于 K2.5 有显著提升；针对 OpenClaw、Hermes Agent 等主动式 Agent 框架，K2.6 展现出极强的自动化任务处理能力，支持长达 5 天的持续自主运行。与传统单体Agent不同，Agent Swarm可以：
- 自动生成并协调最多300个子代理（sub-agents）并行协作处理复杂任务；
- 支持超过4,000次工具调用（Tool Use）；
- 通过并行执行策略，比单体Agent任务完成时间快约4.5倍。

这种技术的核心不在于堆叠更大的模型，而在于让模型理解任务分解与协作，由内部控制器在运行时自动创建和分配子代理执行不同子任务。
2026年2月中旬，Moonshot AI发布了Kimi Claw公测版（Beta），这是一个OpenClaw AI Agent平台，旨在让用户无需本地服务器、终端、Docker等复杂环境，就能一键在浏览器中部署并运行一个持续在线的AI代理（OpenClaw）。Kimi Claw内置长期记忆、可配置人格和社区技能库（如5,000+ ClawHub技能），能够在后台持续执行自动化任务，进一步增强了Agent模式的功能和灵活性。
- 用户通过Web浏览器即可访问和使用，无需本地设备托管或编程环境；
- 提供云存储（如40GB）和长期在线的Agent能力，能够融合Kimi K2.6的模型能力执行各种任务，满足不同用户的需求。
通过Kimi Claw，用户可以体验到更加灵活且持续在线的Agent服务，进一步推动智能自动化的普及与应用。

Kimi Agent 致力于在调研、编程、办公等实际专业场景中提供强大的智能支持，提升用户的工作效率和生产力，帮助用户在各种复杂任务中实现自动化和智能化。Kimi已经拥有多个AI产品线，包括：
- 网站生成（Websites）：自动生成并优化响应式网站，构建并部署高质量的在线网站与应用APP；
- 文档处理（Docs）：提供智能文档编辑、撰写和格式化功能，支持输出Word、PDF、Markdown、TxT等多种格式；
- 表格分析（Sheets）：帮助用户分析和处理数据，自动生成报表，支持输出Excel、CSV多种格式，并有透视、复杂数据处理能力；
- PPT制作（Slides）：自动化PPT设计，提供智能模板，从框架到内容，一站式生成；
- 深度研究（Deep Research）：支持深入的市场调研，通过复杂搜索、多步推理、AI编程，生成万字高质量的研究和可视化报告；
- Agent集群（Agent Swarm）：自动生成并协调最多300个子代理（sub-agents）并行协作处理复杂任务，支持超过4,000次工具调用（Tool Use），适用于海量搜索、长文写作、批量处理任务；
- Kimi Claw：零部署云端自动化平台，无需服务器或Docker，30秒内即可启动持续运行的AI代理。内置5,000+技能库（ClawHub），支持链式组合调用与多步骤自主规划，轻松完成复杂调研与数据分析流程。

## Agent 如何工作？
Kimi Agent 采用了基于强化学习训练的自主决策系统，能够在没有预设工作流的情况下动态处理复杂任务。

<Frames
  src="./images/agent-overview/overview-00.png"
  alt="Agent产品入口"
/>

当你向 Agent 提交一个需求时，通用 Agent经历以下步骤：
- 任务规划：接收用户指令后，识别关键信息，自动拆解为多个子任务，生成清晰的执行计划，并实时动态展示；
- 工具调用：内置 20 多种工具，涵盖代码编写、终端操作、网页浏览、图片生成、音频生成、专业财经数据接入、网站部署等，按需灵活调用；
- 自主执行：按需启动包括产品经理、设计师、数据分析师、内容策划、前端工程师在内的 AI 协作角色，自主完成调研、规划、分析、设计、开发与部署；
- 异常处理：执行过程中遭遇错误时，模型会主动识别问题、调整方案并重新执行，无需用户介入；
- 成果交付：任务完成后，输出高质量的产出物，例如，可以直接下载、编辑的Excel、Word、PPT的办公文件，部署好的在线网页和可交互的APP，可复制保存为PDF/Word的万字报告等。

## 产品入口

<Frames
  src="./images/agent-overview/overview-01.png"
  alt="Agent产品入口"
/>

- 网页版：[https://www.kimi.com/agent](https://www.kimi.com/agent)
- 手机/平板：打开 Kimi App → 工具栏（Taskbar）→ 切换至 Agent 模式

## 操作步骤
1. 向 Agent 清晰地描述你的任务需求并发送。例如：“帮我创建一个在线投票工具的网站代码”、“分析 2025 年 AI 芯片行业的竞争格局”等。系统进入自动执行阶段，实时查看任务执行进展

<Frames
  src="./images/agent-overview/overview-02.png"
  alt="Agent用户任务输入"
/>

2. 系统将在后台自动执行任务，你可以实时看到：
   - 推理和决策的逻辑链路
   - 调用的工具类型和执行步骤
   - 访问的网址和信息来源
   - 代码生成或分析的中间过程

<Frames
  src="./images/agent-overview/overview-03.png"
  alt="Agent任务过程"
/>

3. 任务完成后，获取专业级别的交付成果
4. 根据任务类型，Agent 会生成相应的输出：

<Frames
  src="./images/agent-overview/overview-04.png"
  alt="Agent产出物示意"
/>

   - 代码项目：完整可运行的网站代码、应用程序等（包含 HTML、CSS、JavaScript）
   - 文件夹：任务执行过程中的所有过程文件
   - 数据分析：图表、趋势分析、关键指标的表格
   - 办公文档：Word 文档、PDF文档、Markdown文档、PPT 演示文稿等
5. 预览、下载或分享产出成果

## 适用场景

<Frames
  src="./images/agent-overview/overview-06.png"
  alt="Agent适用场景"
/>

- 网站开发：零代码基础，也可以做出一个多功能的网站原型。通用 Agent 会深入理解业务需求，规划结构与流程，逐步实现 Web 应用原型，并支持直接部署到云端，生成可分享的链接。
- 内容生成：编写儿童故事并配套绘本与音频均可支持。通用 Agent 能自动搜索素材、整理内容、遵循视觉规范，产出物可编辑，支持多种格式。
- 文档处理：多版合同比对： 快速识别 100 页合同条款差异，精准标注风险点；超长文档翻译：将 50 页英文 PDF 翻译，并转为中文或中英双语 PDF
- 数据分析：无论是百万行级别的多源Excel 报表汇总录入，还是需要从专业平台实时抓取的数据，通用 Agent 均可自动完成清洗、分析、策略回测，并生成可交互的表格，可支持整理 1000 行Excel
- PPT生成：智能模版、内容生成，制作高品质 PPT
- 文档互转：PDF/Word速转PPT：从 3 万字学术论文中提炼核心论点，生成 20 页逻辑严密的答辩 PPT

<ColumnsContent
  columns={[
    {
      title: "网站生成",
      description: "零代码基础，也可以做出一个多功能的网站原型并部署上线。",
      pageUrl: "/websites/websites-overview",
      type: "browser",
    },
    {
      title: "PPT 制作",
      description: "智能模版、内容生成，从框架到内容一站式生成高品质 PPT。",
      pageUrl: "/ppt",
      type: "ppt",
    },
    {
      title: "文档与表格",
      description: "智能文档编辑、数据分析，支持 Word、Excel、PDF 等多种格式。",
      pageUrl: "/docs-and-sheets",
      type: "document",
    },
    {
      title: "深度研究",
      description: "通过复杂搜索、多步推理，生成万字高质量研究报告。",
      pageUrl: "/deep-research",
      type: "microscope",
    },
  ]}
/>
