---
title: "模型选择与性能对比"
slug: "api-model-selection"
order: 6
extract_headings: true
preview: true
preview_content: "Kimi API 模型选型指南：kimi-k3、kimi-k2.6 能力对比与 Vision 计费。"
---

<SeoMeta
  title="如何选择合适的 Kimi API 模型？ - Kimi 帮助中心"
  description="根据业务需求选择最适合的 Kimi API 模型。本文对比 kimi-k3、kimi-k2.6 等模型的能力、性能、价格与适用场景。"
/>

# 模型选择与性能对比

Kimi API 提供多种模型供开发者选择，不同模型在能力、速度和价格上各有侧重。

## 主要模型

### kimi-k3

`kimi-k3` 是 Kimi 的旗舰模型，面向长程编程与端到端知识工作，原生支持视觉理解。K3 始终开启思考模式，可通过请求顶层 `reasoning_effort` 设置思考力度（支持 `low`、`high`、`max`，默认 `max`），最大支持 1M token 上下文窗口。

### kimi-k2.6

`kimi-k2.6` 支持文本、图片和视频输入，支持思考与非思考模式切换，适用于对话、代码生成、视觉理解和 Agent 任务。最大支持 256k token 上下文窗口。

平台还提供其他模型，请访问 [platform.kimi.com/docs/introduction](https://platform.kimi.com/docs/introduction) 查看完整的模型列表和详细参数。

## 选择维度

选择模型时，建议根据以下维度评估：

- **上下文长度**：不同模型支持的最大上下文窗口不同，长文档处理需选择大上下文模型。
- **响应速度**：轻量模型响应更快，适合对延迟敏感的场景。
- **生成质量**：高阶模型在复杂推理、创作等任务上表现更好。
- **价格**：根据预算和调用量选择性价比最优的模型。
- **思考模式**：需要深度推理时选择 kimi-k3；需要灵活切换思考与非思考模式时选择 kimi-k2.6。

## Vision 模型（图片理解）

Vision 模型支持图片输入，可用于图片描述、OCR、图表解读等场景：

- 每张图片按固定 **1024 tokens** 计费，无论图片尺寸和分辨率。
- 支持常见图片格式（JPEG、PNG、WebP 等）。
- 图片可通过 URL 或 Base64 编码方式传入。

## 当前不支持的能力

- **PPT 生成 API**：PPT 生成功能暂未开放 API 接口。
- **深度研究 API**：深度研究功能暂未开放 API 接口。

如需以上能力，请关注平台公告获取最新动态。
