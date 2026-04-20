---
title: "模型选择与性能对比"
slug: "api-model-selection"
order: 6
extract_headings: false
preview: true
preview_content: "Kimi API 模型选型指南：性能维度与 Vision 计费。"
---
<SeoMeta
  title="如何选择合适的 Kimi API 模型？ - Kimi 帮助中心"
  description="根据你的业务需求选择最适合的 Kimi API 模型。本文对比各模型的性能、价格与适用场景，帮你做出最优选择。"
  pageUrl="https://www.kimi.com/help/kimi-api/api-model-selection"
/>

# 模型选择与性能对比

Kimi API 提供多种模型供开发者选择，不同模型在能力、速度和价格上各有侧重。

## 可用模型

请访问 [platform.kimi.ai/docs/introduction](https://platform.kimi.ai/docs/introduction) 查看完整的模型列表和详细参数。

选择模型时，建议根据以下维度评估：

- **上下文长度**：不同模型支持的最大上下文窗口不同，长文档处理需选择大上下文模型。
- **响应速度**：轻量模型响应更快，适合对延迟敏感的场景。
- **生成质量**：高阶模型在复杂推理、创作等任务上表现更好。
- **价格**：根据预算和调用量选择性价比最优的模型。

## Vision 模型（图片理解）

Vision 模型支持图片输入，可用于图片描述、OCR、图表解读等场景：

- 每张图片按固定 **1024 tokens** 计费，无论图片尺寸和分辨率。
- 支持常见图片格式（JPEG、PNG、WebP 等）。
- 图片可通过 URL 或 Base64 编码方式传入。

## 当前不支持的能力

- **视频多模态**：暂不支持视频文件的直接输入和理解。
- **PPT 生成 API**：PPT 生成功能暂未开放 API 接口。
- **深度研究 API**：深度研究功能暂未开放 API 接口。

如需以上能力，请关注平台公告获取最新动态。
