---
title: "Rate limits"
slug: "api-rate-limits"
order: 5
extract_headings: false
preview: false
---

<SeoMeta
  title="Rate limits - Kimi Help Center"
  description="Kimi API enforces rate limits on request frequency and concurrency to ensure platform stability and fair usage. Rate limit tiers are based on your account's..."
  pageUrl="https://www.kimi.com/help/kimi-api/api-rate-limits"
/>

Kimi API enforces rate limits on request frequency and concurrency to ensure platform stability and fair usage. Rate limit tiers are based on your account's cumulative top-up amount.

## Rate limit tiers

API rate limits are tiered based on your account's **cumulative top-up amount** — the more you've topped up, the higher your available rate limits. For specific tier thresholds and corresponding RPM (requests per minute) and TPM (tokens per minute) limits, refer to the [platform.moonshot.ai](https://platform.moonshot.ai) console.

## How to check current limits？

- Log in to the API console to view your current rate limit tier.
- API response headers also include rate limit information:
  - `X-RateLimit-Limit`: Current rate limit cap
  - `X-RateLimit-Remaining`: Remaining available requests
  - `X-RateLimit-Reset`: Time when the limit resets

## Handle 429 errors

When your request frequency exceeds the limit, the API returns a 429 status code. Recommended actions:

1. **Implement exponential backoff**: Wait 1 second initially, then double the wait time with each retry (2s, 4s, 8s…).
2. **Control concurrency**: Use request queues or semaphores to limit the number of simultaneous requests.
3. **Batch requests**: Combine multiple small requests into fewer, larger ones.

## Request higher rate limits

If your business needs exceed the current rate limits:

- **Top up to upgrade**: Increase your cumulative top-up amount and the system will automatically upgrade your rate limit tier.
- **Contact sales**: For special requirements, reach out to the platform sales team via [platform.moonshot.ai/contact-sales](https://platform.moonshot.ai/contact-sales) to request a custom rate quota.
