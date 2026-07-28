---
title: "Rate limits"
slug: "api-rate-limits"
order: 5
extract_headings: true
preview: false
---

<SeoMeta
  title="Rate limits - Kimi Help Center"
  description="How Kimi API rate limits work: concurrency, RPM, TPM, TPD, calculation logic, and how to handle 429 errors."
/>

# Rate limits

Kimi API enforces rate limits on request frequency and concurrency to ensure platform stability and fair usage. Rate limit tiers are based on your account's cumulative top-up amount.

## How do these rate limits work?

Rate limits are measured in four ways:

- **Concurrency**: Number of requests processed at the same time.
- **RPM** (requests per minute): Number of requests per minute.
- **TPM** (tokens per minute): Number of tokens per minute.
- **TPD** (tokens per day): Number of tokens per day.

The rate limit can be reached in any of these categories, depending on which one is hit first. For example, you might send 20 requests to Chat Completions, each with only 100 Tokens, and you would hit the limit (if your RPM limit is 20), even if you haven't reached 200k Tokens in those 20 requests (assuming your TPM limit is 200k).

## Rate limit calculation

For the gateway, for convenience, we calculate rate limits based on the `max_completion_tokens` parameter in the request:

- If your request includes the `max_completion_tokens` parameter, we will use this parameter to calculate the rate limit.
- If your request does not include the `max_completion_tokens` parameter, we will use the default `max_completion_tokens` parameter to calculate the rate limit.

After you make a request, we will determine whether you have reached the rate limit based on the number of Tokens in your request plus the number of `max_completion_tokens` in your parameter, regardless of the actual number of Tokens generated.

In the billing process, we calculate the cost based on the number of Tokens in your request plus the actual number of Tokens generated.

<Callout type="info">
- Rate limits are enforced at the user level, not the key level.
- Currently, we share rate limits across all models.
</Callout>

## Rate limit tiers

API rate limits are tiered based on your account's **cumulative top-up amount** — the more you've topped up, the higher your available rate limits. For specific tier thresholds and corresponding RPM, TPM, and TPD limits, refer to the [platform.kimi.ai](https://platform.kimi.ai) console.

## How to check current limits?

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

For more details on 429 troubleshooting, see [API Troubleshooting](https://platform.kimi.ai/docs/troubleshooting/api-troubleshooting).

## Request higher rate limits

If your business needs exceed the current rate limits:

- **Top up to upgrade**: Increase your cumulative top-up amount and the system will automatically upgrade your rate limit tier.
- **Contact sales**: For special requirements, reach out to the platform sales team via [platform.kimi.ai/contact-sales](https://platform.kimi.ai/contact-sales) to request a custom rate quota.
