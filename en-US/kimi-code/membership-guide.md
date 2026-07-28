---
title: "Kimi Code membership guide"
slug: "membership-guide"
order: 1
extract_headings: false
preview: false
---

<SeoMeta
  title="Kimi Code membership guide - Kimi Help Center"
  description="Kimi Code is a developer-focused benefit within the Kimi membership plan, providing high-performance AI coding capabilities. You can use this benefit through..."
/>

# Kimi Code membership guide

<Callout type="info">
Kimi Code is a developer-focused benefit within the Kimi membership plan, providing high-performance AI coding capabilities. You can use this benefit through Kimi Code CLI, Claude Code, Roo Code, and other supported tools.
</Callout>

## Key advantages

| Advantage | Description |
|-----------|-------------|
| **Broad Compatibility** | Works with Kimi Code CLI, Claude Code, Roo Code, and other mainstream coding agents |
| **Standard / HighSpeed Tiers** | The same model at two speeds — HighSpeed delivers roughly 5–6× the output speed of Standard and switches on demand |
| **Ultra-Fast Responses** | Generation speeds up to 100 tokens/s, significantly boosting coding efficiency |
| **High-Frequency Concurrency** | Approximately 300–1,200 requests per 5-hour window (depending on your plan), with up to 30 concurrent streams |

## Quick start

Choose the path that fits your situation:

- **New Users**: Go to [kimi.com/code](https://kimi.com/code), sign in, and subscribe to a Coding Plan.
- **Existing Subscribers**: Access the console to manage your API Keys and start using Kimi Code.

## Obtaining an API key

1. Sign in to the [Kimi Console](https://kimi.com/code).
2. Navigate to the **API Keys** page.
3. Click **Create New API Key**.
4. Copy and securely store your API Key (it is only displayed once upon creation).

<Callout type="warning">
Do not share your API Key with others or commit it to public code repositories.
</Callout>

## One-click login

In Kimi Code CLI, you can use the `/login` command for quick authorization without manually copying an API Key:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/login",
    },
  ]}
/>

The system will automatically complete device authorization and account binding — the entire process takes just a few seconds.

## Device management

- Each account can be used across multiple devices.
- Device authorizations that have been **inactive for 30 days** will automatically expire; you will need to run `/login` again to re-authorize.
- You can view and manage authorized devices in the console.

## How to switch models

**The HighSpeed model is now available.** Kimi Code offers two tiers — **Standard** and **HighSpeed** — built on the same model with identical coding ability, sharing the same Base URL, API Key, and membership benefits. HighSpeed delivers roughly **5–6× the output speed** of Standard, so when you want instant responses and fast iteration, a one-click switch gives you a smoother coding experience. The main differences:

| Item | Standard | HighSpeed |
| --- | --- | --- |
| Model ID | `kimi-for-coding` | `kimi-for-coding-highspeed` |
| Output speed | Baseline | ~5–6× faster than Standard |
| Credit usage | Baseline | ~3× that of Standard |
| Coding ability | Full | Same as Standard |
| Best for | Everyday coding tasks | Instant responses, fast iteration |
| Membership | Available to all Kimi Code members | Requires an [Allegretto](https://www.kimi.com/membership/pricing) plan or above |

Ways to switch to the target model:

- **Official Kimi Code CLI**: type `/model` in a session to switch directly between Standard and HighSpeed — no config changes needed.
- **Kimi Code for VS Code**: pick the target model from the dropdown menu in the input bar; if HighSpeed isn't listed yet, restart VS Code or reinstall the extension.
- **Third-party tools**: set the tool's Model ID to the target model; all other settings stay the same. For where to find it in each tool, see [Using in Third-Party Coding Agents](/kimi-code/third-party-agents).

<Callout type="info">
- **Stable model IDs**: Both IDs are stable identifiers; the backend updates the model they map to as models improve, with no client config changes needed.
- **Enter it exactly**: The high-speed ID must be `kimi-for-coding-highspeed`. If mistyped or set to another value, the request silently falls back to the standard `kimi-for-coding` — no error, but no acceleration either.
- **401 without access**: If your plan doesn't include HighSpeed access, calling it returns a `401`; upgrade to Allegretto or above.
</Callout>

<Callout type="tip">
**Why doesn't the whole task feel 5–6× faster?** "5–6×" refers to **model output speed** (how fast text/code is generated). A coding task's total time is made up of "model output + tool calls (reading/writing files, running commands, web lookups, etc.) + script execution" — how long tool calls and script execution take depends on your project and commands, and HighSpeed doesn't change that part. So if the overall task doesn't feel 5–6× faster, it's usually because tool calls / script execution took up most of that turn, not because model generation slowed down.
</Callout>
