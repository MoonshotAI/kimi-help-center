---
title: "API troubleshooting"
slug: "api-troubleshooting"
order: 8
extract_headings: true
preview: false
---

<SeoMeta
  title="API troubleshooting - Kimi Help Center"
  description="Common issues and solutions for developers using Kimi API."
  pageUrl="https://www.kimi.com/help/kimi-api/api-troubleshooting"
/>

# API troubleshooting

<Callout type="info">
Common issues and solutions for developers using Kimi API.
</Callout>

## How to handle 429 rate limit error?

A 429 error means your request frequency has exceeded the current account's rate limit. To resolve:

- Implement an exponential backoff retry strategy (wait 1s, 2s, 4s… before retrying).
- Control the number of concurrent requests using a queue mechanism.
- Increase your cumulative top-up amount to upgrade your rate limit tier.
- Contact the sales team if you need a higher quota.

## How to handle 401 authentication error?

A 401 error means API Key authentication failed. Check the following:

- Ensure the API Key was copied correctly (watch for leading/trailing spaces).
- Verify the request header format is `Authorization: Bearer <your-api-key>`.
- Confirm the API Key has not been deleted or disabled — check in the console.
- Make sure you are not using a key from another platform (Kimi API Keys start with `sk-`).

<Callout type="warning">
**API Key Format**: Kimi API Keys start with `sk-`. Ensure you're using the correct key format.
</Callout>

## Does file upload incur charges?

File upload itself is free. However, when you reference an uploaded file in a conversation, its content is parsed into tokens and billed as input tokens. Larger files produce more tokens.

## How to handle 403 insufficient balance error?

A 403 error typically indicates insufficient account balance. Top up in the console — funds are available immediately. You can also use the balance query API to check your current balance.

## What if the response is truncated?

If the API response is incomplete or truncated:

- Check whether the `max_tokens` parameter is set too low and increase it as needed.
- Inspect the `finish_reason` field in the response: `length` means the output was truncated due to the token limit; `stop` means it completed normally.
- For long text generation, consider breaking the request into segments.

<Callout type="tip">
**Check `finish_reason`**: `length` = truncated, `stop` = completed normally.
</Callout>

## Can I upload images via the file API?

Yes. The file upload API supports image files. Once uploaded, images can be referenced in conversations. With Vision models, you can also pass images directly in messages via URL or Base64 encoding.

## Sources for web search?

Kimi API's web search feature retrieves publicly available information from the internet in real time. Results are sourced from web pages indexed by major search engines. Each web search invocation incurs an additional fee of $0.004.

## Is there a relationship between Kimi membership and API concurrency?

<Callout type="warning">
**Kimi membership plans** (such as Allegretto) and the **API** are separate billing systems. The agent parallelism included in membership plans applies only to Kimi's consumer products and is unrelated to API rate limits. API concurrency limits are determined by your account's cumulative top-up tier.
</Callout>

## Difference between API and Kimi web app

| Aspect | Kimi Web App | Kimi API |
| --- | --- | --- |
| **Target** | Consumer-facing conversational product | Developer-facing integration interface |
| **Access** | Browser-based | Programmatic API calls |
| **Billing** | Membership/quota system | Pay-as-you-go by tokens |
| **Account** | Shared login | Shared login |
| **Credits** | Not transferable between systems | Not transferable between systems |

## Are PPT generation and deep research available via API?

<Callout type="warning">
**PPT generation** and **deep research** are **not yet available via API**. These features are currently only accessible through the Kimi consumer product. Follow platform announcements for updates.
</Callout>

## Is on-premises deployment supported?

Kimi API currently offers cloud-based API services only and **does not support on-premises private deployment**. For private deployment requirements, contact the sales team via [platform.moonshot.ai/contact-sales](https://platform.moonshot.ai/contact-sales).

## Can I call the Kimi API from outside of China?

Kimi API is available internationally via `api.moonshot.ai`. If you experience connectivity issues, contact the sales team to discuss the best solution for your region.
