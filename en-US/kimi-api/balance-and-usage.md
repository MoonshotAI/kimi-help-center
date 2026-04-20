---
title: "Balance & usage"
slug: "api-balance-and-usage"
order: 4
extract_headings: false
preview: false
---

<SeoMeta
  title="Balance \u0026 usage - Kimi Help Center"
  description="Kimi API provides multiple ways to view your account balance and usage details, helping you track consumption and costs."
  pageUrl="https://www.kimi.com/help/kimi-api/api-balance-and-usage"
/>

Kimi API provides multiple ways to view your account balance and usage details, helping you track consumption and costs.

## Console dashboard

Log in to [platform.moonshot.ai](https://platform.moonshot.ai) and navigate to the **fee-detail** (billing details) page in the console to view:

- Current account balance
- Daily usage breakdown
- Per-model usage and costs
- Historical spending trends

<Callout type="info">
Daily billing is updated by **7:00 AM the following day**. Real-time usage data may have a slight delay.
</Callout>

> **Note**: Daily billing is updated by **7:00 AM the following day**. Real-time usage data may have a slight delay.

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

Include your API Key in the request header to retrieve your available balance.

## Usage monitoring tips

<Callout type="tip">
**Best Practices**:
- Check the fee-detail page regularly to monitor spending trends
- Integrate the Balance Query API and set up balance alert thresholds
- Use the Token Estimation API before critical calls to estimate costs
</Callout>
