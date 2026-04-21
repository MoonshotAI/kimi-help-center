---
title: "Agent features & limitations"
slug: "agent-features-and-limits"
order: 3
extract_headings: false
preview: false
---

# Agent features & limitations

<SeoMeta
  title="Agent Features \u0026 Limitations - Kimi Help Center"
  description="Learn about Kimi Agent's capabilities, usage tips, limitations, and best practices for optimal results."
/>

<Callout type="info">
**Kimi Agent** is an AI-powered assistant that autonomously executes complex tasks through multi-step reasoning and tool integration. This guide covers best practices, limitations, and FAQs to help you get the most out of Agent mode.
</Callout>

## Usage tips

**(1) Before submitting a task**

Clearly state background information and constraints — project context, use case, and special requirements — to help Kimi understand your intent more accurately.

**(2) During execution**

Kimi Agent runs asynchronously in the background. If the web page appears frozen or stalled, **do not click "Stop"** — this will interrupt task execution. You can leave the page; the task will continue running in the background and you'll receive a notification when it completes. For tasks expected to take a long time (e.g., K2.6 Agent Swarm [Beta]), please be patient.

**(3) Website scenarios**

Agent can generate full-stack content, including frontend interfaces, backend services, and persistent storage logic. If a project does not run as expected, the issue is usually related to sandbox startup, database initialization, auth configuration, or missing publish actions. Standard Agent runs in the cloud and cannot directly access local files or enterprise intranet systems. For local file or intranet access, use Kimi Claw.

<Callout type="tip">
**Need to access local files?** Use Kimi Claw for secure access to local files and enterprise intranet systems. Learn more in the [Kimi Claw documentation](/help/kimi-claw/overview).
</Callout>

**(4) Multi-turn conversations and task adjustments**
Over multiple rounds of dialogue and revisions, the Agent may "forget" some early details. It's best to establish the task framework and key points first, then make incremental adjustments.

**(5) Large task decomposition**
For large, complex tasks, break them into 2–3 phases and submit them to Kimi in batches, or use K2.6 Agent Swarm [Beta].

**(6) File output limitations**
In standard Agent mode, typically only one file can be output per task (e.g., a document or spreadsheet). For multiple files (e.g., both a Word doc and a PPT), use K2.6 Agent Swarm [Beta].

**(7) Context limits and output balance**
Due to the 256K character context limit of large language models (approximately 40,000–50,000 Chinese characters / ~100,000 English words), processing large volumes of files requires balancing input and output volume.

<Callout type="warning">
**Context Limit Note**: Agent uses a 256K character context window. For optimal results, provide concise context and avoid overloading with unnecessary files.
</Callout>

## Important notes

<Callout type="warning">
**Quota Usage**: Agent tasks consume unified quota based on actual token usage. Each Agent task typically consumes 1 quota unit. For detailed quota information by membership tier, see [Quota & Billing](/help/agent/quota-and-billing).
Free tier: 6 Agent tasks/month
Paid tiers: 60–720 Agent tasks/month depending on your plan
</Callout>

- **Execution time**: In Agent mode, a single task typically takes 5–20 minutes. K2.6 Agent Swarm [Beta] tasks may take longer. You can leave the page — just don't click Stop to interrupt the task.
- **Quota usage**: Agent tasks consume unified quota based on actual token usage. 
- **Simple tasks**: For simple Q&A, standard chat mode is recommended for faster responses.

<Callout type="warning">
**Content Compliance**: Agent features are subject to the [Kimi User Agreement](https://www.kimi.com/user/agreement/modelUse?version=v2). Generating prohibited content is not supported; submitting prohibited content may result in service suspension.
</Callout>

## FAQ

**Q: What can Agent do?**
Agent meets the following needs through multiple tool calls:
- **Text generation & editing**: Generate articles, reports, documents, etc. with support for various writing styles and formats.
- **Web development**: Build full-stack project interfaces and services, supporting app interface design, backend integration, data persistence, and data visualization.
- **Slide generation**: Dedicated web-based PPT tool for generating complete presentations.
- **Coding assistance**: Code writing and debugging across multiple programming languages.

**Q: Why isn't the Agent-built website working?**
A complete project typically consists of three parts: frontend interface, backend services, and data storage. Agent can generate full-stack project content across all three layers. If your project does not run as expected, the issue is usually related to sandbox startup, database initialization, auth configuration, or missing publish actions.

**Q: What are Agent's deliverables?**
- Complete task execution files
- Deployed project preview and published versions
- Downloadable Zip archive (located in `/mnt/okcomputer/output/`)

**Q: What is Agent's context length?**
Agent uses a context length of **256K characters** (approximately 40,000–50,000 Chinese characters / ~100,000 English words).
**Q: How is Agent quota calculated?**
Agent, PPT, and Kimi Code share a unified quota system based on actual token usage. Each Agent task typically counts as one quota unit. View your current quota and usage at [Membership Credits](https://www.kimi.com/membership-credits).
