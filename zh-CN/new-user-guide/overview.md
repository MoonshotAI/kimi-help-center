---
title: "Kimi 概述"
slug: "overview"
order: 1
extract_headings: false
preview: true
preview_content: "Kimi 是什么？了解 Kimi 的核心功能、支持平台与产品矩阵。"
---
<SeoMeta
  title="Kimi 新手入门指南 - Kimi 帮助中心"
  description="从零开始使用 Kimi：了解产品核心功能、注册登录方法、对话技巧和常用功能入口，快速上手 AI 智能助手。"
/>

# Kimi 概述

Kimi 是由 Moonshot 自主研发的 AI 智能助手，支持联网搜索、深度思考、多模态推理和超长文本对话。

访问 [Kimi.com](https://www.kimi.com/) 或下载 Kimi App，即可开始聊天、创作、研究和构建应用。开发者可前往 [Kimi 开放平台](https://platform.kimi.ai/) 获取 API 与工具，将 Kimi 能力集成到自己的应用中。

## 会话模式

- **联网搜索**：连接网络获取实时信息，支持搜索网络信息。
- **快速模式**：快速回答相关信息。
- **思考模式**：支持更深入的多轮思考与搜索——非常适合编码、逻辑或分析任务。

<Callout type="tip">
**提示**：对于简单的基于文档的问答，可将联网模式、思考模式都关闭。
</Callout>

## Agent 智能代理

Kimi 不仅是对话助手，更是能自主执行任务的 AI Agent：

- **[通用 Agent](https://www.kimi.com/agent)**：自动规划并完成任务，支持网站生成、PPT 制作、深度研究、文档和表格处理等。
- **[Agent 集群](https://www.kimi.com/agent-swarm)**：支持高达 1500 次并行工具调用，可以自主调度多达 100+ 子智能体（Sub-agents）并行处理任务，适用海量搜索、长文写作、批量处理任务。
- **[Kimi Code](https://www.kimi.com/code?from=kfc_overview_topbar)**：面向开发者的编程助手套件，包括命令行工具（CLI）、VS Code 插件。
- **[Kimi Claw](https://www.kimi.com/bot)**：零部署云端自动化平台，无需服务器或 Docker，30 秒内即可启动持续运行的 AI 代理。内置 5,000+ 技能库（ClawHub），支持链式组合调用与多步骤自主规划，轻松完成复杂调研与数据分析流程。

## 其他核心功能

- **特色功能**：拍照解题、语音通话、翻译、写作。
- **文件处理**：支持 PDF、Word、Excel、PPT、图片、TXT、视频（单个不超过 100M），最多支持 50 个文件。
- **常用语**：添加你常用的快速提示，适合把高质量、可复用的提示词设置为常用语。

<ColumnsContent
  columns={[
    {
      title: "基础会话",
      description: "会话是一切的起点，支持提问、上传文件、切换模型与 Agent 模式。",
      pageUrl: "/help/new-user-guide/agentic-chat",
      type: "comment",
    },
    {
      title: "搜索",
      description: "搜索是模型的实时知识库，用于获取即时、可信、可溯源信息。",
      pageUrl: "/help/new-user-guide/search",
      type: "browser",
    },
    {
      title: "记忆空间",
      description: "长期保存你的偏好，并在后续对话中参考过往聊天记录。",
      pageUrl: "/help/new-user-guide/memory-space",
      type: "setting",
    },
    {
      title: "Agent 智能代理",
      description: "自主执行任务，只需要你说出目标，建站、文档、数据分析、PPT 都可以。",
      pageUrl: "/help/agent/agent-overview",
      type: "okcomputer",
    },
  ]}
/>

## 界面介绍

### 网页版

<Frames
  src="./images/overview/overview-01.png"
  alt="image"
/>

- **[网页版](https://www.kimi.com/)**：直接在浏览器中使用 Kimi，无需下载安装。

<Frames
  src="./images/overview/overview-02.png"
  alt="image"
/>
- **[网页版](https://www.kimi.com/)**：点击「+」，可以选择上传文件、图片，选择常用语、选择专业数据库、技能（Skill）、联网。

<Frames
  src="./images/overview/overview-02-1.png"
  alt="image"
/>
- **[网页版](https://www.kimi.com/)**：左下角，点击个人头像，可以进入「设置页」，可以再次找到更多关于Kimi的信息：
  - 点击会员计划：可以进入会员页面，你可以在里面找到不同会员订阅档位的价格、权益，并在「我的订阅」中找到会员权益使用明细、对已经支付订单进行开票；
  - 关于我们：在关于我们，可以找到Kimi已经发布的模型信息，最新研究，以及博客；
  - 语言设置：点击Language，可以切换产品界面的中英文信息；
  - 用户反馈：对于Kimi的建议和想法，可以点此反馈；
  - 设置：进入个人设置页面；

### 手机/平板

#### 切换模型/Agent任务

<Frames
  src="./images/overview/overview-03.png"
  alt="image"
/>
- 在移动商店下载APP后，打开APP，点击上方可以切换至**最新模型**，点击输入框上方的Taskbar，可以开启Agent任务。

#### 输入框

<Frames
  src="./images/overview/overview-03-01.png"
  alt="image"
/>
- 在手机端下方，为输入框，点击「+」，可以选择上传文件、照片、本地文件、微信文件，点击语音符号，可以选择语音输入。

#### 个人设置页

<Frames
  src="./images/overview/overview-04.png"
  alt="image"
/>
- 在手机端上方，点击侧边栏，进入个人设置页与查看历史对话。

#### doodle

<Frames
  src="./images/overview/overview-04-01.png"
  alt="image"
/>
- 在节假日、大事件、纪念日，Kimi会随机上新doodle，祝你也快乐。
