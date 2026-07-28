---
title: "Kimi API 介绍"
slug: "api-overview"
order: 1
extract_headings: true
preview: true
preview_content: "Kimi API 开放平台介绍、核心概念、发送请求与处理响应指南。"
---

<SeoMeta
  title="Kimi API 产品概览与快速入门 - Kimi 帮助中心"
  description="了解 Kimi API 的核心概念、模型能力、接入方式与响应处理。Kimi API 提供强大的大语言模型调用服务，支持对话、工具调用、文件解析等功能。"
/>

# Kimi API 介绍

Kimi API 开放平台为开发者提供强大的大语言模型能力接入，帮助你快速将 AI 能力集成到自己的产品和服务中。

## 平台概述

Kimi API 基于 Moonshot 自研大语言模型，提供文本生成、多轮对话、文件解析、联网搜索等核心能力。平台兼容 OpenAI API 格式，开发者可以低成本迁移和接入。

**平台地址**：[platform.kimi.com](https://platform.kimi.com/)

## 主要概念

### 文本与多模态模型

`kimi-k3` 是 Kimi 的旗舰模型，面向长程编程与端到端知识工作，原生支持视觉理解；`kimi-k2.6` 支持文本、图片和视频输入、思考与非思考模式切换，适用于对话、代码生成、视觉理解和 Agent 任务。对模型的输入通常称为 "prompt"，提供清晰的指令和必要示例，是获得稳定输出的关键。平台也提供其他模型，详见 [模型列表](https://platform.kimi.com/docs/models)。

### 语言模型推理服务

语言模型推理服务是一个基于 Moonshot AI 开发和训练的预训练模型的 API 服务。当前平台对外主要提供 Chat Completions 接口，用于对话、代码生成、视觉理解和 Agent 任务。模型本身默认不直接访问网络、数据库等外部资源，但你可以结合官方工具或自定义工具调用能力扩展模型的执行范围。

### Token

文本生成模型以 Token 为基本单位来处理文本。Token 代表常见的字符序列。例如，单个汉字"夔"可能会被分解为若干 Token 的组合，而像"中国"这样短且常见的短语则可能会使用单个 Token。大致来说，对于一段通常的中文文本，1 个 Token 大约相当于 1.5-2 个汉字。

需要注意的是，Input 和 Output 的总和长度不能超过所选模型的最大上下文长度。例如 `kimi-k3` 支持最高 1M token 上下文窗口，其他模型的上下文长度请参考 [模型列表](https://platform.kimi.com/docs/models)。

## 适用人群

- **独立开发者**：快速构建 AI 驱动的个人项目或工具。
- **企业技术团队**：将 AI 能力嵌入企业产品，提升用户体验和业务效率。
- **创业公司**：以低成本获取顶尖 AI 能力，加速产品迭代。

## 主要应用场景

- **智能客服**：基于上下文理解的自动问答，提升客服效率和用户满意度。
- **内容生成**：文章撰写、营销文案、代码生成等创作场景。
- **数据分析**：文档解读、报表分析、知识提取与总结。
- **知识问答**：基于私有文档库的智能检索和问答系统。

## 发送请求

你可以使用 Chat Completions API 来发送请求。你需要提供一个 API 密钥和一个模型名称。你可以选择是否使用默认的 `max_completion_tokens` 参数，或者自定义 `max_completion_tokens` 参数。可以参考 [API 文档](https://platform.kimi.com/docs/api/chat) 中的调用方法。

## 处理响应

通常，我们会设置一个 2 小时的超时时间。如果单个请求超过了这个时间，我们会返回一个 504 错误。如果你的请求超过了速率限制，我们会返回一个 429 错误。如果你的请求成功了，我们会返回一个 JSON 格式的响应。

如果是为了快速处理一些任务，你可以使用 Chat Completions API 的非 streaming 模式。这种模式下，我们会在一次请求中返回所有的生成文本。如果你需要更多的控制，你可以使用 streaming 模式。在这种模式下，我们会返回一个 SSE 流，你可以在这个流中获取生成的文本，这样用户体验可能会更好，并且你也可以在任何时候中断请求，而不会浪费资源。

## 与 Kimi 其他产品对比

<Callout type="info">
Kimi API 开放平台是按量计费模式、无订阅制方案，与 Kimi 会员、Kimi Code 等产品不同，请注意区分。
</Callout>

| 产品 | 简介 | 付费模式 |
| --- | --- | --- |
| Kimi API 开放平台（platform.kimi.com） | 面向开发者和企业用户，提供易用、稳定、高性价比的大模型 API 服务，助力 AI 应用快速开发、部署与规模化落地。 | 方式一：按量付费（注册登录后创建 API key 即可使用），计费说明见 [产品定价](https://platform.kimi.com/docs/pricing/chat) 页面。<br>方式二：企业方案（填写 [该表单](https://platform.kimi.com/contact-sales) 咨询销售人员）。 |
| Kimi Business | 专为企业团队打造的智能办公解决方案，适合有团队协作需求的中小型企业。详情见 [Kimi Business 介绍](https://www.kimi.com/zh-cn/help/kimi-business/kimi-business)。 | 按年度订阅付费，5 座起售。具体价格以 [该页面](https://www.kimi.com/zh-cn/help/kimi-business/kimi-business) 为准。 |
| Kimi 会员 | Kimi 提供四档会员订阅套餐，满足从个人日常到专业重度使用的不同需求。详情见 [Kimi 会员介绍](https://www.kimi.com/zh-cn/help/membership/membership-overview)。注意：Kimi 会员目前包含 [Kimi Code](https://www.kimi.com/code/docs/) 相关权益，Kimi Code API 与本平台提供的 API 服务相互独立。 | 按月/年订阅付费，具体价格以 [该页面](https://www.kimi.com/membership/pricing) 为准。 |

## 快速开始

1. 访问 [platform.kimi.com](https://platform.kimi.com/) 注册开发者账号。
2. 在控制台创建 API Key。
3. 参考 API 文档完成首次调用。
4. 根据业务需求选择合适的模型和参数。
