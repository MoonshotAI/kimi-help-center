---
title: "Kimi chat common issues"
slug: "chat-issues"
order: 4
extract_headings: true
preview: false
---

<SeoMeta
  title="Kimi chat common issues - Kimi Help Center"
  description="This may be caused by:"
/>

## Can't send messages / red circle appears?

This may be caused by:

- **Rate limit triggered**: Kimi has a conversation cap within certain time windows. Sending messages too frequently may prevent further interaction. Wait 2–3 hours before trying again, and manage your conversation frequency.
- **Poor network conditions**: Weak signal or an unstable connection may prevent messages from being sent. Switch to a different network and retry.

## Conversation exceeds 200,000 words?

The single-conversation context limit is approximately 128K tokens (~200,000 words). Once this limit is reached, the model can no longer accept new input.

<Callout type="tip">
**Recommended actions**:

1. **Start a new conversation**: Copy the key conclusions or outline from the original conversation into a new one to continue.
2. **Generate a handoff document**: Ask Kimi to "summarize and generate a handoff document," then paste it into a new conversation as the initial context — this saves tokens while preserving information.

**Note**: Deleting messages within the same conversation does **not** free up the context window. Start a new conversation instead.
</Callout>

<Callout type="info">
Thinking models consume more tokens for reasoning, resulting in a smaller effective context limit. When working with long documents, prefer K2 over K2-Thinking.
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
