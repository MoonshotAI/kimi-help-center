---
title: "API pricing"
slug: "api-pricing"
order: 3
extract_headings: false
preview: false
---

<SeoMeta
  title="API pricing - Kimi Help Center"
  description="Kimi API billing based on token consumption, with model-specific and feature-specific pricing."
/>

# API pricing

<Callout type="info">
Kimi API billing based on token consumption, with model-specific and feature-specific pricing.
</Callout>

## Billing basics

- **Per-token billing**: Each API call is billed separately for input tokens and output tokens
- **Token unit**: 1M = 1,000,000 tokens
- **Model-specific pricing**: Higher-capability models have higher per-token costs — choose the model that best fits your use case

## Additional feature billing

| Feature | Additional Fee |
| --- | --- |
| **Web Search** | $0.004 per invocation (independent of token consumption) |

## Context caching

<Callout type="tip">
**Context Caching** allows you to cache frequently used context content (such as system prompts and reference documents). Tokens that hit the cache are billed at a discounted rate, effectively reducing costs for repetitive context.
</Callout>

Refer to the official documentation for detailed Context Caching pricing.

## Pricing details

For the complete model pricing table and billing rules:

<Callout type="info">
[platform.moonshot.ai/docs/pricing/chat](https://platform.moonshot.ai/docs/pricing/chat)
</Callout>

## Cost optimization tips

<Callout type="tip">
- Set the `max_tokens` parameter appropriately to avoid unnecessarily long outputs
- Use Context Caching for repetitive system prompts and context
- Choose the right model for the task complexity — use lightweight models for simple tasks
- Streamline your prompt design to minimize unnecessary input tokens
</Callout>
