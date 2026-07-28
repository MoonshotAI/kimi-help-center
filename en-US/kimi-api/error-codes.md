---
title: "Error codes"
slug: "api-error-codes"
order: 2
extract_headings: true
preview: false
---

<SeoMeta
  title="Error codes - Kimi Help Center"
  description="Kimi API error code reference, including typical messages and troubleshooting steps for 400, 401, 403, 404, 429, 499, 500, and 503 errors."
/>

# Error codes

When a request fails, the API returns a JSON response that contains error information:

```json
{
    "error": {
        "type": "content_filter",
        "message": "The request was rejected because it was considered high risk"
    }
}
```

## 400 — Bad Request

| error type | Typical message | Cause and fix |
| --- | --- | --- |
| `content_filter` | The request was rejected because it was considered high risk | The input or model output triggered content safety review. Modify the prompt and avoid sensitive or high-risk content. |
| `invalid_request_error` | Request format error, missing required parameter, or invalid parameter type | Check the request body against the API documentation. |
| `invalid_request_error` | Input token length too long | The input tokens exceed the model's maximum context limit. Shorten the input or use a model with a larger context window. |
| `invalid_request_error` | prompt tokens + max_tokens exceeds the model specification | Reduce `max_tokens` or switch to another model. |
| `invalid_request_error` | Invalid purpose: only 'file-extract' accepted | The `purpose` field for file upload is incorrect. Currently, only `file-extract` is supported. |
| `invalid_request_error` | File size is too large, max file size is 100MB, please confirm and re-upload the file | The uploaded file exceeds the 100MB limit. Compress or split the file and upload it again. |
| `invalid_request_error` | File size is zero, please confirm and re-upload the file | The uploaded file size is 0. Check whether the file is corrupted or empty. |
| `invalid_request_error` | Too many uploaded files | The total number of uploaded files exceeds the limit. Delete earlier files that are no longer used, then try again. |

## 401 — Authentication Error

| error type | Typical message | Cause and fix |
| --- | --- | --- |
| `invalid_authentication_error` | Invalid Authentication | The API key is invalid or malformed. Check `Authorization: Bearer <key>`. |
| `incorrect_api_key_error` | Incorrect API key provided | The API key was not provided, or the key is incorrect. |

**Platform key isolation**: Keys issued on `platform.kimi.ai` are independent from keys issued on other regional Kimi platforms. Mixing keys across platforms returns 401. Make sure the endpoint matches the platform where the key was created.

## 403 — Permission Error

| error type | Typical message | Cause and fix |
| --- | --- | --- |
| `permission_denied_error` | The API you are accessing is not open | This API is not currently available to your account. |
| `permission_denied_error` | You are not allowed to get other user info | You are not allowed to access other users' information. Check the permission scope for the API. |
| `permission_denied_error` | Your IP is not allowed to access this organization | The calling IP is not in the organization's allowlist. This is common on the international platform. Contact an administrator to add the IP. |

## 404 — Resource Not Found

| error type | Typical message | Cause and fix |
| --- | --- | --- |
| `resource_not_found_error` | Model not found, or this account does not have permission to access the model | Check the spelling of the `model` parameter and the account tier. |

## 429 — Rate Limit / Insufficient Quota

| error type | Typical message | Cause and fix |
| --- | --- | --- |
| `engine_overloaded_error` | The engine is currently overloaded, please try again later | The service node is under high load (for example, peak-hour capacity pressure). Wait as indicated by `Retry-After`, reduce concurrency, and retry with exponential backoff. This is caused by server-side capacity; topping up or upgrading your tier does not resolve it. |
| `exceeded_current_quota_error` | Account balance is insufficient or the account has been disabled | Check your balance and billing status. |
| `exceeded_current_quota_error` | Token quota is insufficient | Top up your account and try again. |
| `rate_limit_reached_error` | Organization-level concurrency limit reached | Reduce concurrency or retry after the time indicated in the response. |
| `rate_limit_reached_error` | Organization-level RPM limit reached | Retry after waiting for the time indicated in the response. RPM means requests per minute. |
| `rate_limit_reached_error` | Organization-level TPM limit reached | Reduce request frequency or upgrade your tier. TPM means tokens per minute. |
| `rate_limit_reached_error` | Organization-level TPD limit reached | The limit will reset the next day, or you can upgrade your plan. TPD means tokens per day. |

## 499 / 500 / 503 — Connection And Server Errors

| HTTP | error type | Cause and fix |
| --- | --- | --- |
| 499 | `client_closed_request` | The client disconnected before the server returned a response. This is common when a streaming response is cut off by an intermediate proxy or when the user cancels the request. Check KeepAlive and timeout settings. |
| 500 | `server_error` / `unexpected_output` | Internal server error. Try again later. If the issue persists, contact support with the `request_id`. |
| 503 | `server_unavailable` | The service is temporarily unavailable. Try again later. This is usually related to node scaling or maintenance. |

## Troubleshooting Tips

- **401 response**: First confirm that you are using an API key from the correct platform.
- **429 response**: First identify the cause by `error.type`: back off and retry for node overload, reduce concurrency or upgrade your account tier for organization-level rate limits, and top up for insufficient balance. See [Top-up and Rate Limits](https://platform.kimi.ai/docs/pricing/limits).
- **500 response**: Try again later. If the issue persists, contact the support team at [api-service@moonshot.ai](mailto:api-service@moonshot.ai).
