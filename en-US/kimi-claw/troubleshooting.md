---
title: "General troubleshooting"
slug: "troubleshooting"
order: 12
extract_headings: false
preview: false
---

<SeoMeta
  title="General troubleshooting - Kimi Help Center"
  description="This page covers common error codes and self-repair options for Kimi Claw."
/>

This page covers common error codes and self-repair options for Kimi Claw.

## Common error codes

| Code | Meaning | What to Do |
|------|---------|------------|
| **400** | Bad Request — Malformed input or invalid parameters | Check your message for unsupported content, then retry. |
| **401** | Unauthorized — Authentication failed | Sign out of Kimi and sign back in. If the issue persists, check your API credentials in Kimi Claw settings. |
| **403** | Forbidden — Insufficient permissions | Verify your membership tier supports the feature you're using. Ensure your account isn't restricted. |
| **429** | Too Many Requests — Rate limit exceeded | Wait a few minutes and retry. See [Conversation Limits](/kimi-claw/conversation-limits) for details on checking your quota. |
| **500** | Internal Server Error — Something went wrong on the server | Retry after a short wait. If recurring, use the self-repair options below or contact support. |

## Self-repair options

Kimi Claw provides built-in repair tools accessible from **Settings** on the web:

| Option | What It Does |
|--------|--------------|
| **Restart Kimi Claw** | Restarts the gateway connection. Fixes most transient issues (bridge disconnects, temporary hangs). |
| **Repair Kimi Claw** | Runs an automated diagnostic that detects and fixes configuration problems. Try this when a simple restart doesn't help. |
| **Restore Initial Settings** | Resets Kimi Claw to its default state. Workspace files and Memory are preserved, but chat platform connections (Telegram, etc.) need to be reconfigured. Use as a last resort. |

## Escalation path

If the self-repair options don't resolve the issue:

1. Run `/logs` in the Terminal to capture recent error output.
2. Run `/debug` to enable verbose diagnostics.
3. Contact **support@moonshot.ai** with the error details and any relevant logs.
