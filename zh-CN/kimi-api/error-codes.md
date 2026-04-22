---
title: "调用 API 报错（错误码说明）"
slug: "api-error-codes"
order: 2
extract_headings: false
preview: true
preview_content: "Kimi API 错误码一览表与排查建议。"
---
<SeoMeta
  title="Kimi API 错误码参考大全 - Kimi 帮助中心"
  description="查阅 Kimi API 常见错误码及其含义，包括 400、401、403、429、500 等错误的原因分析与解决方案，快速定位和修复问题。"
/>

# API 错误码说明

调用 Kimi API 时可能遇到以下错误码，请根据错误码和描述排查问题。

## 错误码一览

| 错误码 | 含义 | 处理方式 |
| --- | --- | --- |
| 400 | 请求参数错误（Bad Request） | 检查请求体格式是否正确，参数名称和类型是否符合文档要求。常见原因：JSON 格式错误、缺少必填参数、参数值超出范围。 |
| 401 | 认证失败（Unauthorized） | 检查 API Key 是否正确、是否已过期或被禁用。确认请求头中 `Authorization: Bearer <your-api-key>` 格式正确。 |
| 403 | 权限不足/余额不足（Forbidden） | 账户余额可能已耗尽，请前往控制台充值。也可能是账号被限制，请联系客服。 |
| 404 | 资源不存在（Not Found） | 检查请求的 URL 路径和模型名称是否正确。确认接口地址为 `https://api.moonshot.cn/v1/...`。 |
| 429 | 请求频率超限（Too Many Requests） | 已超出当前速率限制。请降低请求频率，实施指数退避重试策略，或联系客服申请提升速率限制。 |
| 500 | 服务器内部错误（Internal Server Error） | 服务端临时异常，请稍后重试。如果持续出现，请联系  api-service@moonshot.ai 并附上 request_id。 |

## 通用排查建议

1. **查看完整错误信息**：API 返回的 JSON 响应中通常包含 `error.message` 字段，提供更详细的错误描述。
2. **检查 request_id**：每次请求返回的 `request_id` 可用于联系客服时快速定位问题。
3. **参考官方文档**：确保调用方式与 [platform.kimi.com](https://platform.kimi.com/docs/overview) 文档一致。
4. **使用重试机制**：对于 429 和 500 错误，建议实现自动重试并配合指数退避策略。
