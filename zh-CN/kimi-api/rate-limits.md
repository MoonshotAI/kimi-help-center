---
title: "速率限制与提速"
slug: "api-rate-limits"
order: 5
extract_headings: true
preview: true
preview_content: "API 速率限制的衡量方式、计算逻辑、429 处理与申请提速方法。"
---

<SeoMeta
  title="Kimi API 速率限制说明 - Kimi 帮助中心"
  description="了解 Kimi API 请求速率限制的衡量方式、并发/RPM/TPM/TPD 规则、计算逻辑以及遇到 429 错误时的处理方法。"
/>

# 速率限制与提速

Kimi API 对请求频率和并发数设有速率限制，以确保平台稳定性和公平使用。速率限制等级与账户的累计充值金额挂钩。

## 速率限制的衡量方式

速率限制通过 4 种方式衡量：

- **并发**：同时处理的请求数量。
- **RPM**（Requests Per Minute，每分钟请求数）。
- **TPM**（Tokens Per Minute，每分钟 Token 数）。
- **TPD**（Tokens Per Day，每天 Token 数）。

速率限制可能会在任何一种选项中达到，取决于哪个先发生。例如，你可能向 Chat Completions 发送了 20 个请求，每个请求只有 100 个 Token，那么你就达到了 RPM 限制（如果 RPM 限制是 20），即使你在这些 20 个请求中没有发满 200k 个 Token（假设 TPM 限制是 200k）。

## 速率限制的计算逻辑

对网关，出于方便考虑，我们会基于请求中的 `max_completion_tokens` 参数来计算速率限制：

- 如果你的请求中包含了 `max_completion_tokens` 参数，我们会使用这个参数来计算速率限制。
- 如果你的请求中没有包含 `max_completion_tokens` 参数，我们会使用默认的 `max_completion_tokens` 参数来计算速率限制。

当你发出请求后，我们会基于你请求的 token 数量加上你 `max_completion_tokens` 参数的数量来判断你是否达到了速率限制，而不考虑实际生成的 token 数量。

在计费环节中，我们会基于你请求的 token 数量加上实际生成的 token 数量来计算费用。

<Callout type="info">
- 速率限制是在用户级别而非密钥级别上实施的。
- 目前我们在所有模型中共享速率限制。
</Callout>

## 速率限制分级

API 速率限制基于账户的**累计充值金额**进行分级，充值金额越高，可用的速率限制越高。具体分级标准和对应的 RPM、TPM、TPD 限制，请参考 [platform.kimi.com](https://platform.kimi.com/) 控制台中的说明。

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

更详细的 429 排查方法，请参考 [API 调用常见问题](https://platform.kimi.com/docs/troubleshooting/api-troubleshooting)。

## 申请更高速率限制

如果业务需求超出当前速率限制：

- **充值提速**：增加累计充值金额，系统将自动提升速率限制等级。
- **联系客服**：如有特殊需求，可联系平台客服或通过 [platform.kimi.com/contact-sales](https://platform.kimi.com/contact-sales) 联系销售团队，申请定制化的速率配额。
