---
title: "API 调用常见问题"
slug: "api-troubleshooting"
order: 8
extract_headings: true
preview: true
preview_content: "Kimi API 调用常见问题：429 限流、401 认证失败、输出截断、K3 使用、第三方工具配置等。"
---

<SeoMeta
  title="Kimi API 常见问题与故障排查 - Kimi 帮助中心"
  description="遇到 Kimi API 调用异常？本文汇总常见问题的排查步骤，涵盖认证失败、429 限流、余额扣费、Kimi K3、第三方工具配置等场景，帮你快速解决问题。"
/>

# API 调用常见问题

以下是开发者在使用 Kimi API 过程中最常遇到的问题及解决方案。

## Kimi API 开放平台、Kimi Code 和 Kimi 会员的余额与 API Key 互通吗？

不互通。Kimi API 开放平台、Kimi Code 和 Kimi 会员是相互独立的产品，付费方式、余额/权益和 API Key 均不通用：

- **Kimi API 开放平台**是按量付费模式、无订阅制。调用 Kimi API 请在开放平台控制台创建 API Key，并使用对应区域的端点，详见 [产品与付费方式](https://platform.kimi.com/docs/guide/product-plans)。
- **Kimi Code**是独立的编程产品，其 API Key 与开放平台不通用，请按照 [Kimi Code 文档](https://www.kimi.com/code/docs/) 创建和配置。
- **Kimi 会员**（订阅制）的权益不会转换为开放平台余额，开放平台充值余额也不能用于购买 Kimi 会员或 Kimi Code Plan。

如果把其他产品的 Key 填到开放平台端点，会出现 401 或 404 报错，排查思路见下方「为什么调用返回 401、404 或 permission denied？」。

## 为什么调用返回 401、404 或 permission denied？

请按以下顺序检查：

1. Key 是否来自你正在调用的产品：开放平台 API Key 与 Kimi Code Key 不通用。
2. Key 所属区域是否与调用端点一致：中国站（platform.kimi.com）与国际站（platform.kimi.ai）的账户、余额和 Key 相互隔离。
3. 账户是否有可用余额，代金券是否支持目标模型。
4. 使用同一个 Key 调用 `GET /v1/models`，确认目标模型是否在返回列表中。
5. 模型名是否与接入方式匹配：直接调用 API 和在 Codex 中使用 `kimi-k3`，在 Claude Code 中使用兼容别名 `kimi-k3[1m]`，请以对应接入教程为准。
6. 清理旧的环境变量、代理和 CC Switch 等本地路由中的旧配置，确认实际生效的 Key 与端点。

相关链接：[错误码说明](https://platform.kimi.com/docs/api/errors)、[在 Claude Code 中使用 Kimi](https://platform.kimi.com/docs/guide/claude-code-kimi)、[在 Codex 中使用 Kimi](https://platform.kimi.com/docs/guide/codex-kimi)。

## 为什么我在 platform.kimi.ai 平台申请的 key，不能用在 platform.kimi.com 平台？

Kimi 开放平台官方提供两个平台，中国境内建议使用 platform.kimi.com 平台，境外建议使用 platform.kimi.ai 平台。两个平台的账户和 key 完全独立，不能混用。

如果用错会出现 `401 invalid_authentication_error` 的报错，收到 401 报错请先检查是否平台的 key 使用错误。

- 国内开放平台 base_url: `https://api.moonshot.cn/v1`
- 境外开放平台 base_url: `https://api.moonshot.ai/v1`

## 为什么充值后仍然返回 429？

429 不是单一原因，请先查看响应中的 `error.type`：

- `engine_overloaded_error`：服务节点负载较高（如高峰期容量压力）。请按照响应中的 `Retry-After` 提示等待、降低并发并使用指数退避重试。该错误由服务端容量导致，充值或提升 Tier 不能直接消除。
- `rate_limit_reached_error`：触发组织级并发、RPM、TPM 或 TPD 限速。请降低调用频率，或参考 [充值与限速](https://platform.kimi.com/docs/pricing/limits) 提升用户等级。
- `exceeded_current_quota_error`：余额不足、欠费或代金券失效。请通过 [查询余额接口](https://platform.kimi.com/docs/api/balance) 确认 `available_balance` 后再充值。

另外请注意，OpenAI SDK 等客户端默认会自动重试，一次操作可能放大为多次请求并占用限速额度。排查时请查看实际请求次数和客户端日志。

因 429 错误中断的请求不会扣费。

## 报错信息显示的 TPM、RPM 限制与我的账户 Tier 等级不匹配

如果你在使用 Kimi API 的过程遇到了 `rate_limit_reached_error` 错误，例如：

```text
rate_limit_reached_error: Your account {uid}<{ak-id}> request reached TPM rate limit, current:{current_tpm}, limit:{max_tpm}
```

但报错信息中的 TPM 或 RPM 限制与你在后台查看的 TPM 与 RPM 并不匹配，请先排查是否正确使用了当前账户的 `api_key`。通常情况下 TPM、RPM 与预期不匹配的原因，是使用了错误的 `api_key`，例如误用了其他用户给予的 `api_key`，或个人拥有多个账号的情况下，混用了 `api_key`。

## 报错 `model_not_found`

请确保你在 SDK 中正确设置了 `base_url=https://api.moonshot.cn/v1`。通常情况下，`model_not_found` 错误产生的原因是，使用 OpenAI SDK 时，未设置 `base_url` 值，导致请求被发送至 OpenAI 服务器，OpenAI 返回了 `model_not_found` 错误。

## 为什么 Agent 没有显示结果，账户却产生了费用？

客户端没有显示结果，不代表 API 请求失败。当编程工具等待时间过短、代理连接断开或本地超时时，客户端可能停止展示，但服务端请求仍可能已完成并产生实际调用记录。

请依次检查：

1. 请求的 HTTP 状态码与 `request_id`。
2. API 响应中的 `usage` 字段。
3. 客户端是否自动重试、启动子 Agent 或循环调用工具。
4. 控制台的用量看板与计费明细。
5. 客户端日志中的超时和连接错误。

如果平台记录与客户端记录仍明显不一致，请携带组织 ID、项目、发生时间、`request_id`、模型、客户端版本、脱敏日志和账单明细，通过 [API 问题反馈表单](https://moonshot.feishu.cn/share/base/form/shrcnR8K8KP2GF3iaBEZK0rRWbh) 提交查询。

## 如何查看消费明细并反馈异常扣费？

请先在 [开放平台控制台](https://platform.kimi.com/console) 查看用量看板与计费明细，按时间、项目、模型和 `request_id`，与客户端日志、API 返回的 `usage` 逐条对照。

需要后台协助查询时，请准备以下材料：组织 ID、项目名称、发生时间（含时区）、`request_id`、模型名、客户端与版本、脱敏日志、相关账单或导出记录，并通过 [API 问题反馈表单](https://moonshot.feishu.cn/share/base/form/shrcnR8K8KP2GF3iaBEZK0rRWbh) 提交。

## 第三方 Agent 或 IDE 配置 Kimi 后仍然报错，如何定位问题？

建议先把链路拆成 Kimi API 与第三方工具两层：

1. 使用相同的 Key、端点和模型直接调用 Kimi API（cURL 示例见 [Kimi K3 快速开始](https://platform.kimi.com/docs/guide/kimi-k3-quickstart)）。
2. 如果直连失败，先解决余额、鉴权、模型权限或请求参数问题。
3. 如果直连成功但第三方工具仍失败，请查看第三方工具的日志，重点检查协议转换、流式响应、超时设置和自动重试。
4. 使用 [Claude Code](https://platform.kimi.com/docs/guide/claude-code-kimi)、[Codex](https://platform.kimi.com/docs/guide/codex-kimi)、[OpenCode](https://platform.kimi.com/docs/guide/open-code) 等工具时，请分别按照对应教程配置，模型名和配置方式可能不同。
5. 保留客户端版本、发生时间、`request_id`、实际请求端点和脱敏日志，便于进一步排查。

请注意，CC Switch、Trae 等第三方工具不由 Kimi 开放平台维护；直连 API 正常但第三方工具失败时，需要同时联系对应工具的支持渠道。

## 使用 Kimi K3 需要什么条件？

在开放平台完成充值（最低充值金额 10 元）后即可解锁调用 Kimi K3。新用户注册认证赠送的 15 元代金券不可用于 Kimi K3。

累计充值金额同时决定账户等级与速率限制，详见 [充值与限速](https://platform.kimi.com/docs/pricing/limits) 和 [Kimi K3 快速开始](https://platform.kimi.com/docs/guide/kimi-k3-quickstart)。

## Kimi K3 如何选择思考力度？

K3 始终开启思考模式，可通过请求顶层 `reasoning_effort` 设置思考力度，支持 `low`、`high`、`max` 三档，默认为 `max`。任务越复杂，建议选择越高档位；简单任务使用较低档位可以降低延迟和 Token 消耗。

详细用法与示例见 [思考力度](https://platform.kimi.com/docs/guide/use-thinking-effort)。

## Kimi K3 的思维链怎么关？

目前关不了，K3 始终开启思考模式。如果觉得思考过程太长，可以将 `reasoning_effort` 设置为 `low` 降低思考力度，详见 [思考力度](https://platform.kimi.com/docs/guide/use-thinking-effort)。

## 可以先体验模型，再决定是否充值吗？

可以先在 [Playground](https://platform.kimi.com/playground) 做最小化测试，确认模型和提示词是否适合你的场景；也可以在编码调试阶段使用 [MoonPalace 调试工具](https://platform.kimi.com/docs/guide/use-moonpalace) 捕获完整请求。可用模型与赠券适用范围以 Playground 和账户页面的实际显示为准。

## 为什么 API 返回的结果和 Kimi 智能助手返回的结果不一致？

Kimi API 和 Kimi 智能助手是不同的产品形态，实际使用的模型版本、System Prompt、上下文管理、工具配置和产品策略可能不同，因此即使输入相同，结果也不一定一致。

通过 API 调用时，请根据业务需求选择模型、设置 System Prompt、管理对话上下文，并在 `tools` 中声明所需工具。可用模型及参数差异请参阅 [模型列表](https://platform.kimi.com/docs/models) 和 [模型参数参考](https://platform.kimi.com/docs/api/models-overview)。

## Context Caching（上下文缓存）需要手动配置吗？

不需要。Kimi API 会对重复的初始上下文自动尝试缓存，无需手动创建 cache ID、设置 TTL 或添加额外请求参数。

保持 system prompt、工具定义和长文档等初始前缀稳定，有助于后续请求命中缓存；修改前缀内容可能降低缓存命中率。详见 [上下文缓存](https://platform.kimi.com/docs/guide/use-context-caching-feature-of-kimi-api)。

## 使用 `tool_calls` 时模型反复调用同一个工具，怎么办？

在使用工具调用 `tool_calls` 的过程中，模型可能会根据上下文连续发起多次工具调用。

如果你发现模型连续多次调用**同一个工具**，并且每次调用使用的 `function.name` 与 `function.arguments` 完全相同，且工具返回结果没有带来新的有效信息，可以将其视为重复工具调用。

在处理这类问题时，我们建议先排查消息布局是否正确：

1. 当 Kimi API 返回 `finish_reason=tool_calls` 时，是否已将返回的 `choice.message` 原封不动地添加到 `messages` 列表。
2. 每个 `tool_call` 是否都有一条对应的 `role=tool` 消息。
3. `role=tool` 消息中的 `tool_call_id` 是否与对应的 `tool_call.id` 完全一致。
4. 如果你使用流式输出 `stream=True`，是否已正确拼接分片返回的 `tool_calls`，尤其是 `function.arguments` 字段。

如果上述消息布局没有问题，但模型仍然重复调用同一个工具和同一组参数，可以在业务侧增加重复调用检测，并在下一轮请求的系统提示词 system prompt 中追加提醒。

当同一个工具和同一组参数连续重复 3 次时，可以追加：

```text
<system-reminder>
You are repeating the exact same tool call with identical parameters. Please carefully analyze the previous result. If the task is not yet complete, try a different method or parameters instead of repeating the same call.
</system-reminder>
```

当重复调用达到 5 次时，可以追加更明确的提示，并包含工具名、重复次数和参数：

```text
<system-reminder>
You have repeatedly called the same tool with identical parameters many times.
Repeated tool call detected:
- tool: {tool_name}
- repeated_times: {repeat_count}
- arguments: {tool_arguments}
The previous repeated calls did not make progress. Do not call this exact same tool with the exact same arguments again.
Carefully inspect the latest tool result and choose a different next action, different parameters, or finish the task if enough evidence has been gathered.
</system-reminder>
```

如果同一个工具和同一组参数连续重复达到 8 次，建议再次追加上述提示。

需要注意的是，`<system-reminder>` 只是一个提示词示例，不是 Kimi API 的特殊字段。你可以将其中内容合并到下一轮请求的 `role=system` 消息中，也可以按照自己的消息管理方式写入系统提示词。为了避免误判，建议仅在"同一个工具、同一组参数、连续多次重复、工具结果没有新进展"同时成立时触发这类提示。

## Kimi API 是否拥有 Kimi 智能助手的"上网冲浪"功能？

<Callout type="warning">
联网搜索（`web_search`）正在更新升级中，近期不建议使用该功能，当前文档已经过时，请关注后续内容更新。
</Callout>

支持。Kimi API 提供内置联网搜索工具 `$web_search`。使用时需要在请求的 `tools` 中将其声明为 `builtin_function`，并按照标准 `tool_calls` 流程处理模型返回的调用结果；联网搜索不会在每个 API 请求中默认开启。

具体声明方式和完整示例请参阅 [使用 Kimi API 的联网搜索功能](https://platform.kimi.com/docs/guide/use-web-search)。如果需要接入自建或第三方搜索服务，请参阅 [使用 Kimi API 完成工具调用](https://platform.kimi.com/docs/guide/use-kimi-api-to-complete-tool-calls)。

## 联网搜索的来源是什么？

Kimi API 的联网搜索功能会实时检索互联网公开信息，搜索结果来源于主流搜索引擎索引的网页内容。每次联网搜索额外收费 ¥0.03。

## Kimi API 返回的内容不完整或被截断

如果你发现 Kimi API 返回的内容不完整、被截断或长度不符合预期，你可以先检查响应体中的 `choice.finish_reason` 字段的值。如果该值为 `length`，则表明当前模型生成内容所包含的 Tokens 数量超过请求中的 `max_completion_tokens` 参数，在这种情况下，Kimi API 仅会返回 `max_completion_tokens` 个 Tokens 内容，多余的内容将会被丢弃，即上文所说"内容不完整"或"内容被截断"。

在遇到 `finish_reason=length` 时，如果你想让 Kimi 大模型接着上一次返回的内容继续输出，可以使用 Kimi API 提供的 Partial Mode。详细的文档请参考：

[使用 Kimi API 的 Partial Mode](https://platform.kimi.com/docs/guide/use-partial-mode-feature-of-kimi-api)

如果你想避免出现 `finish_reason=length`，我们建议你适当增大 `max_completion_tokens` 的值。推荐的最佳实践是：通过 [estimate-token-count](https://platform.kimi.com/docs/api/estimate) 接口计算输入内容的 Tokens 数量，然后从所选模型支持的最大上下文窗口中扣除这部分输入 Tokens。例如，`kimi-k3` 模型最大支持 1M Tokens，`moonshot-v1-32k` 模型最大支持 32k Tokens，`kimi-k2.6`、`kimi-k2.5`、`kimi-k2-0905-preview` 和 `kimi-k2-turbo-preview` 模型最大支持 256k Tokens，扣除输入 Tokens 后的剩余值即可作为当前请求的 `max_completion_tokens` 上限。

## Kimi 大模型的输出长度是多少？

- 对于 `kimi-k3` 模型而言，`max_completion_tokens` 默认为 131072，最大输出长度是 `1024*1024 - prompt_tokens`。
- 对于 `moonshot-v1-8k` 模型而言，最大输出长度是 `8*1024 - prompt_tokens`。
- 对于 `moonshot-v1-32k` 模型而言，最大输出长度是 `32*1024 - prompt_tokens`。
- 对于 `moonshot-v1-128k` 模型而言，最大输出长度是 `128*1024 - prompt_tokens`。
- 对于 `kimi-k2.6`、`kimi-k2.5`、`kimi-k2-0905-preview` 和 `kimi-k2-turbo-preview` 模型而言，最大输出长度是 `256*1024 - prompt_tokens`。

## Kimi 大模型支持的汉字数量是多少？

- 对于 `kimi-k3` 模型而言，大约支持一百五十万个汉字。
- 对于 `moonshot-v1-8k` 模型而言，大约支持一万五千个汉字。
- 对于 `moonshot-v1-32k` 模型而言，大约支持六万个汉字。
- 对于 `moonshot-v1-128k` 模型而言，大约支持二十万个汉字。
- 对于 `kimi-k2.6`、`kimi-k2.5`、`kimi-k2-0905-preview` 和 `kimi-k2-turbo-preview` 模型而言，大约支持四十万个汉字。

*注：以上均为估算值，实际情况可能有所不同。*

## 我设置了 `max_completion_tokens=2000`，让 Kimi 输出 2000 字的内容，但 Kimi 输出的内容少于 2000 字

> 注：`max_tokens` 已弃用（deprecated），请使用 `max_completion_tokens`，两者含义相同。

`max_completion_tokens` 参数的含义是：**调用 `/v1/chat/completions` 时，允许模型生成的最大 Tokens 数量，当模型已经生成的 Tokens 数超过设置的 `max_completion_tokens` 时，模型会停止输出下一个 Token**。

`max_completion_tokens` 的作用在于：

1. 帮助调用方确定该使用哪个模型（例如，当 `prompt_tokens + max_completion_tokens <= 8 * 1024` 时，可以选择 `moonshot-v1-8k` 模型）。
2. 防止在某些意外的场合，Kimi 模型输出了过多不符合预期的内容，进而导致额外的费用消耗（例如，Kimi 模型重复输出空白字符）。

`max_completion_tokens` 并不能指示 Kimi 大模型输出多少 Tokens，换句话说，**`max_completion_tokens` 不会作为提示词 prompt 的一部分输入 Kimi 大模型**。如果你想让模型输出特定字数的内容，可以参考以下通用的解决办法：

- 对于要求输出内容字数在 1000 字以内的场合：
  1. 在提示词 prompt 中向 Kimi 大模型明确输出的字数。
  2. 通过人工或程序手段检测输出的字数是否符合预期，如果不符合预期，通过在第二轮对话中向 Kimi 大模型指示"字数多了"或"字数少了"，让 Kimi 大模型输出新一轮的内容。
- 对于要求输出内容字数在 1000 字以上甚至更多时：
  1. 尝试将预期输出的内容按结构或章节切割成若干部分，并制成模板，并使用占位符标记想要 Kimi 大模型输出内容的位置。
  2. 让 Kimi 大模型按照模板，逐个填充每个模板的占位符部分，最终拼装成完整的长文文本。

## 为何在提示词 prompt 相似的情况下，有的请求响应速度快，有的请求响应速度慢？

如果你遇到在相似提示词 prompt 的不同请求中，有的请求响应快（例如响应时间只有 3s），有的请求响应慢（例如响应时间长达 20s），这通常是由于 Kimi 大模型生成的 Tokens 数量不同导致的。通常而言，Kimi 大模型生成的 Tokens 数量与 Kimi API 的响应时间成正比，生成的 Tokens 数量越多，API 完整的响应时间越长。

需要注意的是，Kimi 大模型生成的 Tokens 数量只影响完整请求（指生成完最后一个 Token）的响应时间。你可以设置 `stream=True`，并观察首 Token 返回时间（首 Token 返回时间，我们简称为 TTFT -- Time To First Token）。通常情况下，提示词 prompt 的长度相似的场合，首 Token 响应时间不会有太大的波动。

## 我在一分钟内只请求了一次，但却触发了 `Your account reached max request` 错误

通常，OpenAI 提供的 SDK 包含了重试机制：

> Certain errors are automatically retried 2 times by default, with a short exponential backoff. Connection errors (for example, due to a network connectivity problem), 408 Request Timeout, 409 Conflict, 429 Rate Limit, and >=500 Internal errors are all retried by default.

这种重试机制在遇到错误时，会默认重试 2 次（总计 3 次请求）。通常来说，对于网络状况不稳定或者其他可能导致请求发生错误的场合，使用 OpenAI SDK 会将一个请求放大至 2 到 3 次请求，这些请求都会占用你的 RPM（每分钟请求数）次数。

*注：对于使用 OpenAI SDK 且账户等级为 `tier0` 的用户而言，由于存在默认的重试机制，一次错误的请求就会消耗完所有的 RPM 额度。*

## 出现 Connection 相关错误

如果在使用 Kimi API 的过程中，经常出现 `Connection Error`、`Connection Time Out` 等错误，请按照以下顺序检查：

1. 程序代码或使用的 SDK 是否有默认的超时设置。
2. 是否有使用任何类型的代理服务器，并检查代理服务器的网络和超时设置。

另一种可能导致 `Connection` 相关错误的场景是，未启用流式输出 `stream=True` 时，Kimi 大模型生成的 Tokens 数量过多，导致在等待 Kimi 大模型生成过程时，触发了某个中间环节网关的超时时间设置。通常，某些网关应用会通过检测是否接收到服务器端返回的 `status_code` 和 `header` 来判断当前请求是否有效。在不使用流式输出 `stream=True` 的场合，Kimi 服务端会等待 Kimi 大模型生成完毕后发送 `header`，在等待 `header` 返回时，某些网关应用会关闭等待时间过长的连接，进而产生 `Connection` 相关错误。

**我们推荐启用流式输出 `stream=True` 来尽可能减少 `Connection` 相关错误。**

## 文件抽取内容不准确、图像无法被识别

我们提供各种格式的文件上传和文件解析服务。**对于文本文件，我们会提取文件中的文字内容；对于图片文件，我们会使用 OCR 识别图片中的文字；对于 PDF 文档，如果 PDF 文档中只包含图片，我们会使用 OCR 提取图片中的文字，否则仅会提取文本内容。**

*注意，对于图片，我们只会使用 OCR 提取图片中的文字内容，因此如果你的图片中不包含任何文字内容，则会引起解析失败的错误。*

完整的文件格式支持列表，请参考 [上传文件接口](https://platform.kimi.com/docs/api/files-upload)。

## 文件上传是否计费？

文件上传本身不产生费用。但当你在对话中引用已上传的文件时，文件内容会被解析为 token 并计入输入 token 计费。文件越大，解析产生的 token 越多。

## 文件接口可以上传图片吗？

可以。文件上传接口支持图片文件上传，上传后可在对话中引用。若使用 Vision 模型，也可直接在消息中通过 URL 或 Base64 传入图片。

## 使用 `files` 接口时，希望使用 `file_id` 引用文件内容

我们目前不支持使用文件 `file_id` 的方式引用文件内容作为上下文。

## 使用接口报错 `content_filter: The request was rejected because it was considered high risk`

当前请求 Kimi API 的输入或 Kimi 大模型的输出内容包含不安全或敏感内容。**注意：Kimi 大模型生成的内容也可能包含不安全或敏感内容，进而导致 `content_filter` 错误。**

如果你通过第三方平台或工具调用，请先确认该错误确实由 Kimi API 返回：第三方平台可能使用自己的内容安全策略和错误话术，其提示不一定来自 Kimi API，此时请同时查看第三方平台的日志。

平台无法提供具体命中的安全策略规则。你可以尝试缩小请求范围、移除可能引起误判的内容后重试。

## Kimi 大模型出现数值计算错误

由于 Kimi 大模型生成过程的不确定性，在数值计算方面，Kimi 大模型可能会出现不同程度的计算错误。我们推荐使用工具调用 `tool_calls` 为 Kimi 大模型提供计算器功能，关于工具调用 `tool_calls`，可以参考我们撰写的工具调用指南：

[使用 Kimi API 完成工具调用（tool_calls）](https://platform.kimi.com/docs/guide/use-kimi-api-to-complete-tool-calls)

## Kimi 大模型无法回答今天的日期

Kimi 大模型无法获取像当前日期这样时效性非常强的信息，但你可以在系统提示词 system prompt 中为 Kimi 大模型提供这样的信息。例如：

```python
import os
from datetime import datetime
from openai import OpenAI

client = OpenAI(
    api_key=os.environ['MOONSHOT_API_KEY'],
    base_url="https://api.moonshot.cn/v1",
)

# 我们通过 datetime 库生成了当前日期，并将其添加到系统提示词 system prompt 中
system_prompt = f"""
你是 Kimi，今天的日期是 {datetime.now().strftime('%d.%m.%Y %H:%M:%S')}
"""

completion = client.chat.completions.create(
    model="kimi-k3",
    messages=[
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": "今天的日期？"},
    ],
)

print(completion.choices[0].message.content)  # 输出：今天的日期是 2024 年 7 月 31 日。
```

```js
const OpenAI = require('openai')

client = new OpenAI({
    apiKey: process.env.MOONSHOT_API_KEY,
    baseURL: "https://api.moonshot.cn/v1",
})

// 我们通过 datetime 库生成了当前日期，并将其添加到系统提示词 system prompt 中
system_prompt = `你是 Kimi，今天的日期是 ${new Date().toString()}`

async function main() {
    completion = await client.chat.completions.create({
        model: "kimi-k3",
        messages: [
            {role: "system", content: system_prompt},
            {role: "user", "content": "今天的日期？"},
        ],
    })

    console.log(completion.choices[0].message.content)  // 输出：今天的日期是 2024 年 7 月 31 日。
}

main()
```

<Callout type="info">
本页示例默认使用最新模型 `kimi-k3`。K3 使用请求顶层 `reasoning_effort` 配置思考力度（支持 `"low"` / `"high"` / `"max"`，默认 `"max"`）。换用 `kimi-k2.6`、`kimi-k2.5` 等其他模型时，只需替换 `model` 字段，但各模型的参数配置存在差异，详见 [模型参数参考](https://platform.kimi.com/docs/api/models-overview)。
</Callout>

## 在不使用 SDK 的场景下如何处理错误

在某些场合，你可能会需要自行对接 Kimi API（而不是使用 OpenAI SDK）。在自行对接 Kimi API 时，你需要根据 API 返回的状态来决定后续的处理逻辑。通常而言，我们会使用 HTTP 状态码 200 表示请求成功，而使用 4xx、5xx 的状态码表示请求失败，我们会提供一个 JSON 格式的错误信息。关于请求状态具体的处理逻辑，请参考以下的代码片段：

```python
import os
import httpx

header = {
    "Authorization": f"Bearer {os.environ['MOONSHOT_API_KEY']}",
}

messages = [
    {"role": "system", "content": "你是 Kimi"},
    {"role": "user", "content": "你好。"},
]

r = httpx.post("https://api.moonshot.cn/v1/chat/completions",
               headers=header,
               json={
                   "model": "kimi-k3",  # <-- 如果你使用一个正确的模型，下方会进入 if status_code==200 分支
                   # "model": "moonshot-v1-129k",  # <-- 如果你使用一个错误的模型名称，下方会进入 else 分支
                   "messages": messages,
               })

if r.status_code == 200:  # 当使用正确的模型进行请求时，会进入此分支，进行正常的处理逻辑
    completion = r.json()
    print(completion["choices"][0]["message"]["content"])
else:  # 当使用错误的模型名称进行请求时，会进入此分支，在这里进行错误处理
    # 在这里，为了演示，我们仅将错误打印出来。
    # 在实际的代码逻辑中，你可能需要更多的处理逻辑，例如记录日志、中断请求或进行重试等。
    error = r.json()
    print(f"error: status={r.status_code}, type='{error['error']['type']}', message='{error['error']['message']}'")
```

```js
const axios = require('axios');

header = {
    "Authorization": `Bearer ${process.env.MOONSHOT_API_KEY}`,
}

messages = [
    {"role": "system", "content": "你是 Kimi"},
    {"role": "user", "content": "你好。"},
]

async function main() {
    r = await axios.post("https://api.moonshot.cn/v1/chat/completions",
        {
            "model": "kimi-k3",  // <-- 如果你使用一个正确的模型，下方会进入 if status_code==200 分支
            //"model": "moonshot-v1-129k",  // <-- 如果你使用一个错误的模型名称，下方会进入 else 分支
            "messages": messages,
        },
        {
            headers: header,
            validateStatus: function (status) {
                return status == 200; // Resolve only if the status code is less than 500
            }
        },
     ).catch(function (error) {
        console.log(`error: ${error.message}`)
     })

    if (r) {  // 当使用正确的模型进行请求时，会进入此分支，进行正常的处理逻辑
        console.log(r.data.choices[0].message.content)
    }
}

main()
```

我们的错误信息会遵循如下的格式：

```json
{
    "error": {
        "type": "error_type",
        "message": "error_message"
    }
}
```

具体的错误信息对照表，请参考 [错误说明](https://platform.kimi.com/docs/api/errors)。

## 为了便于传输，我使用 `base64` 编码我的文本内容

请不要这样做，使用 `base64` 编码你的文件会导致产生巨量的 Tokens 消耗。如果你的文件类型是我们 `/v1/files` 文件接口支持的格式，使用文件接口上传并抽取文件内容即可。

对于二进制或其他格式编码的文件，Kimi 大模型暂时无法解析内容，请不要添加到上下文中。

## PPT 生成和深度研究有 API 吗？

目前 PPT 生成和深度研究功能**暂未开放 API 接口**。这些功能仅在 Kimi 产品端可用。请关注平台公告获取最新动态。

## 支持本地化部署吗？

Kimi API 目前仅提供云端 API 服务，**暂不支持本地化私有部署**。如有私有化部署需求，请通过 [platform.kimi.com/contact-sales](https://platform.kimi.com/contact-sales) 联系销售团队咨询。

## 国外可以调用 Kimi API 吗？

Kimi API 主要面向国内用户提供服务。海外地区的访问可能受到网络环境影响，稳定性无法完全保障。如有海外使用需求，建议联系销售团队了解可行方案。
