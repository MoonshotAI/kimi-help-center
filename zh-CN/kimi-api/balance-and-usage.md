---
title: "余额消耗查询"
slug: "api-balance-and-usage"
order: 4
extract_headings: false
preview: true
preview_content: "如何查询 API 账户余额、消耗明细与用量估算。"
---
<SeoMeta
  title="如何查看 Kimi API 余额和用量？ - Kimi 帮助中心"
  description="了解如何在 Kimi 开放平台查看 API 账户余额、历史用量和消费明细，掌握额度使用情况，及时充值避免服务中断。"
/>

# 余额消耗查询

Kimi API 提供多种方式查看账户余额和消耗明细，帮助你掌握用量和成本。

## 控制台查看

登录 [platform.kimi.com/](https://platform.kimi.com/)，在控制台的 **fee-detail**（费用明细）页面可以查看：

- 账户当前余额
- 每日消耗明细
- 各模型分别的用量和费用
- 历史消费趋势

<Callout type="info">
**注意**：当日账单将于**次日 7:00** 更新。实时消耗数据可能存在一定延迟。
</Callout>

## Token 估算接口

在发送请求前，你可以使用 Token 估算接口预估本次调用将消耗的 token 数量，便于成本控制。

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "POST https://api.moonshot.cn/v1/tokenizers/estimate-token-count",
    },
  ]}
/>

请求体中传入与 Chat Completion 相同格式的 messages，接口将返回预估的 token 数量。

## 余额查询接口

通过 API 直接查询当前账户余额：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "GET https://api.moonshot.cn/v1/users/me/balance",
    },
  ]}
/>

在请求头中携带你的 API Key 即可获取当前可用余额信息。

## 用量监控建议

- 定期查看 fee-detail 页面，关注消耗趋势。
- 在代码中集成余额查询接口，设置余额预警阈值。
- 使用 Token 估算接口在关键调用前预估成本。
