---
title: "API pricing"
slug: "api-pricing"
order: 3
extract_headings: true
preview: false
---

<SeoMeta
  title="API pricing - Kimi Help Center"
  description="Kimi API billing based on token consumption, Kimi K3 pricing, and cost optimization tips."
/>

# API pricing

Kimi API billing based on token consumption, with model-specific and feature-specific pricing.

## Billing basics

- **Per-token billing**: Each API call is billed separately for input tokens and output tokens.
- **Token unit**: 1M = 1,000,000 tokens.
- **Model-specific pricing**: Higher-capability models have higher per-token costs — choose the model that best fits your use case.

## Additional feature billing

| Feature | Additional Fee |
| --- | --- |
| **Web Search** | $0.004 per invocation (independent of token consumption) |

## Context caching

<Callout type="tip">
**Context Caching** allows you to cache frequently used context content (such as system prompts and reference documents). Tokens that hit the cache are billed at a discounted rate, effectively reducing costs for repetitive context.
</Callout>

Refer to the official documentation for detailed Context Caching pricing.

## How is Kimi K3 billed?

Kimi K3 offers a 1M-token context and uses flat pay-as-you-go pricing — there is no tiering by context length. Input (with separate rates for cache hits and misses) and output are billed at uniform per-token prices. See [Kimi K3 pricing](https://platform.kimi.ai/docs/pricing/chat-k3).

## Pricing details

For the complete model pricing table and billing rules:

You can go to [platform.kimi.ai/docs/pricing/chat](https://platform.kimi.ai/docs/pricing/chat)

## Cost optimization tips

<Callout type="tip">
- Set the `max_tokens` parameter appropriately to avoid unnecessarily long outputs.
- Use Context Caching for repetitive system prompts and context.
- Choose the right model for the task complexity — use lightweight models for simple tasks.
- Streamline your prompt design to minimize unnecessary input tokens.
- If cost is a concern, you can use the `kimi-k2.6` model.
</Callout>
