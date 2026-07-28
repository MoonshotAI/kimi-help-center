---
title: "Balance & usage"
slug: "api-balance-and-usage"
order: 4
extract_headings: true
preview: false
---

<SeoMeta
  title="Balance & usage - Kimi Help Center"
  description="How to check your Kimi Open Platform account balance, usage details, and control costs."
/>

# Balance & usage

Kimi Open Platform provides multiple ways to view your account balance and usage details, helping you track consumption and costs.

## Console dashboard

Log in to [platform.kimi.ai](https://platform.kimi.ai) and navigate to the **fee-detail** (billing details) page in the console to view:

- Current account balance
- Daily usage breakdown
- Per-model usage and costs
- Historical spending trends

<Callout type="info">
Daily billing is updated by **7:00 AM the following day**. Real-time usage data may have a slight delay.
</Callout>

## Token estimation API

Before sending a request, you can use the Token Estimation API to estimate how many tokens the call will consume — useful for cost control.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "POST https://api.moonshot.ai/v1/tokenizers/estimate-token-count",
    },
  ]}
/>

Pass the same `messages` format as a Chat Completion request, and the API will return the estimated token count.

## Balance query API

Query your current account balance directly via the API:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "GET https://api.moonshot.ai/v1/users/me/balance",
    },
  ]}
/>

Include your API Key in the request header to retrieve your available balance, including `voucher_balance`.

## How do I control costs and set a spending limit?

When using large models for code generation, the model may need multiple attempts to produce the expected code because of the randomness and complexity of generation. Programming tools may automatically perform multiple rounds of retries and calls, which can cause token usage to grow quickly. To better control costs and improve the usage experience, we recommend the following:

### Budget control

- **Set a daily spending limit**: Before use, go to [Kimi Open Platform project settings](https://platform.kimi.ai/console/projects/settings) and configure a project daily spending budget. Once the budget limit is reached, the system will automatically reject all API requests under that project. Note that due to billing latency, the limit may take about 10 minutes to take effect. For setup instructions, see [Organization Management Best Practices](https://platform.kimi.ai/docs/guide/org-best-practice).
- **Balance alerts**: We recommend enabling account balance alerts. When your account balance falls below the preset amount, the system will notify you so you can top up in time.

### Usage recommendations

- Start with a short context and a clear prompt for testing, then gradually add the complete business context.
- **Continuous monitoring**: Keep monitoring your programming tool while it is running, handle abnormal situations promptly, and avoid unnecessary resource consumption caused by infinite loops or excessive retries.
- **Model selection**: If cost is a concern, you can use the `kimi-k2.6` model.

## Usage monitoring tips

<Callout type="tip">
**Best Practices**:
- Check the fee-detail page regularly to monitor spending trends.
- Integrate the Balance Query API and set up balance alert thresholds.
- Use the Token Estimation API before critical calls to estimate costs.
</Callout>
