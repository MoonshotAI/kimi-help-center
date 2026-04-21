---
title: "API error codes"
slug: "api-error-codes"
order: 2
extract_headings: false
preview: false
---

<SeoMeta
  title="API error codes - Kimi Help Center"
  description="Common error codes when calling Kimi API and how to resolve them."
/>

# API error codes

<Callout type="info">
Common error codes when calling Kimi API and how to resolve them.
</Callout>

## Error code reference

| Error Code | Meaning | Resolution |
| --- | --- | --- |
| 400 | Bad Request | Check request body format, parameter names and types. Common causes: malformed JSON, missing required parameters, values out of range. |
| 401 | Unauthorized | Verify API Key is correct, not expired or disabled. Confirm header format: `Authorization: Bearer <your-api-key>`. |
| 403 | Forbidden (insufficient balance) | Account balance depleted — top up in console. Account may also be restricted; contact support if needed. |
| 404 | Not Found | Check request URL path and model name. Confirm endpoint is `https://api.moonshot.ai/v1/...`. |
| 429 | Too Many Requests | Exceeded rate limit. Reduce frequency, implement exponential backoff, or contact support for higher limits. |
| 500 | Internal Server Error | Temporary server issue — retry later. If persists, contact support@moonshot.ai with `request_id`. |

## General troubleshooting tips

<Callout type="tip">
1. **Check the full error message**: The response JSON includes `error.message` with detailed description.
2. **Note the request_id**: Helps support quickly locate the issue.
3. **Refer to official documentation**: Ensure calls match docs at [platform.moonshot.ai](https://platform.moonshot.ai).
4. **Implement retry logic**: For 429 and 500 errors, use exponential backoff.
</Callout>
