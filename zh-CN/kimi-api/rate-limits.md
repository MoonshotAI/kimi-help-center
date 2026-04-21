---
title: "速率限制与提速"
slug: "api-rate-limits"
order: 5
extract_headings: false
preview: true
preview_content: "API 速率限制分级规则、429 处理与申请提速方法。"
---
<SeoMeta
  title="Kimi API 速率限制说明 - Kimi 帮助中心"
  description="了解 Kimi API 的请求速率限制（RPM/TPM）规则、不同套餐的限额差异以及遇到 429 错误时的处理方法。"
/>

# 速率限制与提速

Kimi API 对请求频率和并发数设有速率限制，以确保平台稳定性和公平使用。速率限制等级与账户的累计充值金额挂钩。

## 速率限制分级

API 速率限制基于账户的**累计充值金额**进行分级，充值金额越高，可用的速率限制越高。具体分级标准和对应的 RPM（每分钟请求数）、TPM（每分钟 token 数）限制，请参考 [platform.kimi.ai](https://platform.kimi.ai) 控制台中的说明。

## 如何查看当前限制

- 登录 API 控制台即可查看当前账户所在的速率限制等级。
- API 响应头中也会包含速率限制相关信息：
  - `X-RateLimit-Limit`：当前速率限制上限
  - `X-RateLimit-Remaining`：剩余可用次数
  - `X-RateLimit-Reset`：限制重置时间

## 遇到 429 错误怎么办

当请求频率超出限制时，API 将返回 429 状态码。建议：

1. **实施指数退避重试**：首次等待 1 秒，之后每次翻倍（2s、4s、8s...）。
2. **控制并发数**：使用请求队列或信号量限制同时发出的请求数量。
3. **批量处理**：将多个小请求合并为较少的大请求。

## 申请更高速率限制

如果业务需求超出当前速率限制：

- **充值提速**：增加累计充值金额，系统将自动提升速率限制等级。
- **联系客服**：如有特殊需求，可联系平台客服或通过 [platform.kimi.ai/contact-sales](https://platform.kimi.ai/contact-sales) 联系销售团队，申请定制化的速率配额。
