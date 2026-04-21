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
