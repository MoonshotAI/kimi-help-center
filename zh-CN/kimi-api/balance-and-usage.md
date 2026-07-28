---
title: "余额消耗查询"
slug: "api-balance-and-usage"
order: 4
extract_headings: true
preview: true
preview_content: "如何查询 API 账户余额、消耗明细、用量估算与成本控制方法。"
---

<SeoMeta
  title="如何查看 Kimi API 余额和用量？ - Kimi 帮助中心"
  description="了解如何在 Kimi 开放平台查看 API 账户余额、历史用量、消费明细和成本控制方法，掌握额度使用情况，及时充值避免服务中断。"
/>

# 余额消耗查询

Kimi 开放平台提供多种方式查看账户余额和消耗明细，帮助你掌握用量和成本。

## 控制台查看

登录 [Kimi 开放平台](https://platform.kimi.com/)，在控制台的 **fee-detail**（费用明细）页面可以查看：

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

在请求头中携带你的 API Key 即可获取当前可用余额信息，包括 `voucher_balance`（代金券余额）等字段。

## 如何控制成本、设置消费上限？

在使用大模型进行代码生成时，由于模型的随机性和复杂性，可能需要多次尝试才能生成符合预期的代码。编程工具会自动进行多轮重试和调用，这可能导致 token 用量快速增长。为了更好地控制成本和使用体验，建议你注意以下几点：

### 预算控制

- **设置日消费上限**：在使用前，请前往 [Kimi 开放平台项目设置](https://platform.kimi.com/console/projects/settings) 配置「项目日消费预算」。一旦达到预算上限，系统将自动拒绝该项目下所有 API 请求（注：由于计费延迟，限制生效可能有约 10 分钟延迟）。设置方式请见 [组织管理最佳实践](https://platform.kimi.com/docs/guide/org-best-practice)。
- **余额预警提醒**：建议开启账户余额提醒功能。当账户余额低于预设金额（默认 ¥20）时，系统会通过短信通知您及时充值。

### 使用建议

- 建议先用较短上下文明确提示词测试，再逐步加入完整业务上下文。
- **持续监控**：建议在编程软件运行期间保持监控，及时处理异常情况，避免因无限循环或过度重试造成不必要的资源消耗。
- **模型选择**：如果对成本敏感，可以选择使用 `kimi-k2.6` 模型。

## 用量监控建议

- 定期查看 fee-detail 页面，关注消耗趋势。
- 在代码中集成余额查询接口，设置余额预警阈值。
- 使用 Token 估算接口在关键调用前预估成本。
