---
title: "Kimi Agent 概述"
slug: "agent-overview"
order: 1
extract_headings: false
preview: true
preview_content: "了解 Kimi Agent 的工作方式、使用入口与适用场景。"
---

<SeoMeta
  title="Kimi Agent 是什么？功能介绍与使用入口 - Kimi 帮助中心"
  description="了解 Kimi Agent 的工作原理、核心能力与适用场景。Kimi Agent 通过多轮推理和 20 多种工具自主完成复杂任务，支持文档生成、代码开发、数据分析等全栈工作流。"
/>

# Kimi Agent 介绍

## Kimi Agent 发展历程

- **2025.09** Kimi K2 发布，作为原生 Agent 奠定通用能力基础；随后推出首个 Agent 产品「OK Computer」，无需预设工作流即可自主规划并完成复杂任务。
- **2026.01** Kimi K2.5：办公场景端到端输出（Word、PDF、Excel、PPT），并引入 Agent 集群（Agent Swarm）。
- **2026.02** Kimi Claw 公测：零部署云端 AI 代理，无需服务器或 Docker，浏览器一键运行持续在线的自动化任务。
- **2026.04** Kimi K2.6 开源：行业领先的代码与长程任务执行能力；Agent 集群升级，支持 300 个子代理并行完成 4000 个协作步骤。
- **2026.07** Kimi K3：全球首个开放式 3T 级模型，2.8 万亿参数、原生视觉、100 万 token 上下文，全面驱动对话、Agent 与集群；完整模型权重于 2026 年 7 月 27 日开放下载。

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
- 手机/平板：打开 Kimi App，在对话框上方的模型切换按钮中选择 K3 或 K3 集群模型

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
