---
title: "How to choose: K2.6 / K3 / K3 Cluster, thinking intensity, and Agent"
slug: "model-mode-selection"
order: 5
extract_headings: true
preview: false
---

<SeoMeta
  title="How to choose Kimi models and modes: K2.6 / K3 / K3 Cluster, thinking intensity, and Agent - Kimi Help Center"
  description="Understand Kimi’s three model options (K2.6 / K3 / K3 Cluster), thinking intensity levels (Standard / Advanced / Extreme), and the difference between Agent and Agent Cluster, so you can choose the best mode for each scenario."
/>

# How to choose: K2.6 / K3 / K3 Cluster, thinking intensity, and Agent

Kimi decides on its own whether to use the internet based on your question, so you don’t need to switch it manually. What you do need to choose are the **model** and **thinking intensity**; for complex tasks, you may also use **Agent** and **Agent Cluster**.

## Three model options

Use the model switcher above the input box to choose:

| Model | Thinking intensity | Best for | Credit |
|---|---|---|---|
| **K2.6** | Standard / Advanced | Fast conversations and Q&A, with faster responses | **No membership credits used in Chat** |
| **K3** | Standard / Advanced / Extreme | Conversations and Agent tasks, with the strongest overall capability | Billed against credits |
| **K3 Cluster** | Standard / Advanced / Extreme | Large-scale search, batch processing, and completing high-volume tasks in one go | Billed against credits |

- **K3** can produce editable documents end to end, such as `.pptx`, `.docx`, `.xlsx`, and `.pdf`; **K2.6** is optimized for fast Q&A and outputs text only, such as PPT outlines, Word body text, code, and more.
- For **image / video / audio generation**, click “+” → Plugins, then choose the relevant feature and use it with **K3**.

<Callout type="info">
K2.6 being free and not consuming credits applies only in Chat (the model switcher above the input box). When used as a K2.6 Agent inside Kimi Work, it still consumes membership credits.
</Callout>

## Thinking intensity: Standard / Advanced / Extreme

The higher the thinking intensity, the more fully the model reasons and, in general, the smarter the result—but it also **uses more tokens**.

- If you want **speed and lower credit usage** → choose **Standard**;
- If you need **stronger reasoning** for complex analysis or difficult problems → choose **Advanced** or **Extreme** (Extreme is supported by K3 / K3 Cluster).

## Agent and Agent Cluster

- **General-purpose Agent**: Automatically plans and completes tasks, including website generation, PPT creation, Deep Research (深度研究), and document and spreadsheet processing.
- **Agent Cluster**: Supports over 4,000 parallel tool calls and can autonomously coordinate up to 300 sub-agents (Sub-agents) in parallel. It is ideal for large-scale tasks such as **large-scale search, long-form writing, and batch processing**.

## What to choose by scenario

- **Fast Q&A and everyday conversations** → K2.6 (no credits used in Chat).
- **Complex conversations, document writing / PPT and spreadsheet creation / multi-step tasks** → K3.
- **Large-scale search, batch processing, and very long-form writing** → K3 Cluster.
- **To save credits** → use K2.6, or set the thinking intensity to “Standard”.

## FAQ

### Is “Thinking Mode” no longer available?
Kimi has integrated “conversation” and “Agent” into one experience, so they are no longer separate modes. “Thinking” is now controlled by **choosing the model and thinking intensity**—for example, using K3 with a higher thinking intensity gives you more thorough reasoning.

### What is the difference between K2.6 and K3?
K2.6 is optimized for fast Q&A, responds faster, and does not use membership credits in Chat. K3 has the strongest overall capability, excels at complex conversations and Agent tasks, can produce editable documents end to end, and is billed against credits.

### What is the difference between K3 and K3 Cluster?
K3 is suitable for regular conversations and Agent tasks. K3 Cluster uses large-scale parallelism—thousands of tool calls and hundreds of sub-agents—to handle high-volume tasks such as **large-scale search, batch processing, and very long-form writing**.

### How much content can be processed in a single turn?
K2.6 supports about 128K tokens of single-turn context (roughly 50,000–60,000 Chinese characters); K3 provides a 1 million-token context window (requires the highest-tier membership benefit). See [What should I do if a conversation exceeds 200,000 Chinese characters?](/others/chat-issues) for details.
