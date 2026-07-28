---
title: "Kimi chat common issues"
slug: "chat-issues"
order: 3
extract_headings: true
preview: false
---

<SeoMeta
  title="Kimi chat common issues - Kimi Help Center"
  description="Having trouble with Kimi chats? This article summarizes troubleshooting steps for common chat issues, including interrupted replies, abnormal content, and loading failures, to help you resolve them quickly."
/>

# Kimi chat common issues

## Can't send messages / red circle appears?

This may be caused by:

- **Rate limit triggered**: Kimi has a conversation cap within certain time windows. Sending messages too frequently may prevent further interaction. Wait 2–3 hours before trying again, and manage your conversation frequency.
- **Poor network conditions**: Weak signal or an unstable connection may prevent messages from being sent. Switch to a different network and retry.

## Conversation exceeds 200,000 words?

K2.6's single-conversation context is approximately 128K tokens (~200,000 words). Once this limit is reached, the model can no longer read in new content. What to do depends on why you hit the limit:

- **A single file you sent is too large and hits the limit on the first turn**: split the file into smaller parts and send them in batches.
- **A multi-turn conversation gradually builds up to the limit**: first summarize the key conclusions so far (you can also ask Kimi to "summarize and generate a handoff document"), then paste that into a new conversation as the initial context to continue.

<Callout type="info">
**Tips**:
- More fundamentally, using [Memory](/features/memory-space) and [Projects](/features/project) helps you avoid hitting the limit — Memory automatically retains key information, and a Project keeps your reference files, instructions, and memory together so every new conversation carries the context.
- Deleting earlier messages in the same conversation does not free up the context window — just start a new conversation instead.
- Thinking consumes tokens; to save credits, set **Thinking strength** to **Standard**.
- For very long documents, K3 offers a 1M-token context (available with the top-tier membership); when composing, select **Conversation length: Extra long**.
</Callout>

## Seeing "let's talk about something else" ?

This prompt indicates that the current content has triggered a safety policy and the topic cannot continue. Simply type a new topic to resume the conversation — no waiting required.

<Callout type="info">
If you believe the content was not in violation, click "👎" to submit feedback and help us improve our safety policies.
</Callout>

## Seeing "Kimi is a bit tired"?

This means too many users are online and compute resources are under heavy load — a peak-hour rate limit. Wait 1–2 minutes and try again.

<Callout type="tip">
To reduce wait times, consider subscribing to a membership plan for priority access to dedicated compute resources.
</Callout>

## Can't download PPT/Word/Excel?

The Kimi chat window itself does not generate downloadable Office files:

| File Type | Where to Generate |
|-----------|-------------------|
| **Slides** | Go to [Kimi Slides](https://www.kimi.com/slides) — supports online generation and download |
| **Word/Excel** | Use **Agent** mode |

## How do I delete a single conversation?

In the Kimi app or on the web, find the conversation and tap delete. Once deleted, it will no longer appear on your device, and the related data will enter the processing workflow in accordance with Section 5 of the [Kimi Privacy Policy](https://www.kimi.com/user/agreement/userPrivacy?version=v2).

## After I delete a conversation, is the share link still accessible?

No. A share link's accessibility is tied directly to its conversation: once the conversation is deleted, any external share links generated from it become invalid at the same time, others can no longer access the content through them, and the platform retains no accessible copy of the link.

## What should I do if I uploaded sensitive information by mistake?

Delete the conversation in the app immediately. If it involves highly sensitive information such as an ID card, bank card, or legal document, contact customer support at [support@moonshot.ai](mailto:support@moonshot.ai) after deleting it, and note the type of sensitive information (e.g. “ID card”, “bank card”, “legal document”) in the email subject line so we can prioritize your request.

## Is any data retained after deletion?

As required by the Cybersecurity Law and other applicable laws and regulations, the platform must retain certain network logs (such as operation timestamps and account identifiers) for a specified period. These logs are used solely for security compliance and regulatory audits, and will not be used for any other purpose without your consent.

If you need to cancel your account and delete all associated data, see [Account deletion & data removal](/others/account-deletion).
