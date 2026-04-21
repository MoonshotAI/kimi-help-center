---
title: "API 计费说明"
slug: "api-pricing"
order: 3
extract_headings: false
preview: true
preview_content: "Kimi API 计费逻辑、Token 价格与成本优化建议。"
---
<SeoMeta
  title="Kimi API 定价与计费说明 - Kimi 帮助中心"
  description="查看 Kimi API 各模型的调用价格、Token 计费规则与账单说明。了解输入/输出 Token 定价，合理预估 API 使用成本。"
/>
# API 计费说明

Kimi API 按 token 消耗量计费，不同模型和功能的价格有所不同。

## 计费基础

- **按 token 计费**：每次 API 调用根据输入 token 和输出 token 分别计费。
- **token 单位**：1M = 1,000,000 tokens。
- **不同模型价格不同**：更高能力的模型单价更高，请根据业务需求选择合适的模型。

## 附加功能计费

- **联网搜索**：每次调用联网搜索功能额外收费 **¥0.03**，独立于 token 消耗。

## Context Caching

Context Caching 功能允许你缓存常用的上下文内容（如系统提示词、参考文档等），缓存命中部分的 token 将按优惠价格计费，有效降低重复上下文的使用成本。

详细的 Context Caching 定价请参考官方文档。

## 计费详情

完整的模型价格表和计费规则，请访问：

[platform.kimi.ai/docs/pricing/chat](https://platform.kimi.ai/docs/pricing/chat)

## 费用优化建议

- 合理设置 `max_tokens` 参数，避免生成过长的无用内容。
- 使用 Context Caching 缓存重复的系统提示词和上下文。
- 根据任务复杂度选择合适的模型，简单任务使用轻量模型即可。
- 精简 prompt 设计，减少不必要的输入 token。
