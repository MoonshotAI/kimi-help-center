---
title: "Using with third-party coding agents"
slug: "third-party-agents"
order: 11
extract_headings: false
preview: false
---

<SeoMeta
  title="Using with third-party coding agents - Kimi Help Center"
  description="Kimi Code benefits can be used with Claude Code and Roo Code, allowing you to enjoy Kimi's AI capabilities within your preferred coding tools."
/>

Kimi Code benefits can be used with Claude Code and Roo Code, allowing you to enjoy Kimi's AI capabilities within your preferred coding tools.

## Prerequisites

- An active Kimi membership with Kimi Code benefits enabled.
- An API Key (created in the [Kimi Console](https://kimi.com/code)).

## Using with Claude Code

[Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview) is a command-line coding assistant by Anthropic.

### Configuration steps

1. Set the environment variables:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "export ANTHROPIC_BASE_URL=https://api.kimi.com/coding/v1\nexport ANTHROPIC_API_KEY=your-api-key",
    },
  ]}
/>

2. Launch Claude Code with the `kimi-k2.5` model:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "claude --model kimi-k2.5",
    },
  ]}
/>

> In Claude Code, you can press **Tab** to switch to the Kimi K2 Thinking model.

> If you encounter a 400 error caused by `tool_search` calls, you can temporarily resolve it by setting the environment variable `ENABLE_TOOL_SEARCH=false`.

## Using with Roo Code

[Roo Code](https://github.com/RooCodeInc/Roo-Code) is an AI coding extension for VS Code.

### Install Roo Code

1. Search for **Roo Code** in the VS Code Extensions Marketplace and install it.
2. After installation, the Roo Code icon will appear in the activity bar; if it doesn't, restart VS Code.

### Configure the Kimi Code model

1. Open the Roo Code panel and navigate to the **Settings** page.
2. In the **Providers** section, select **OpenAI Compatible** and fill in the following:

   | Setting | Value |
   | --- | --- |
   | Entrypoint | `https://api.kimi.com/coding/v1` |
   | API Key | Your API Key |
   | Model | `kimi-k2.5` |

3. Save the configuration and you're ready to go.

## Important notes

- Kimi Code benefits are only supported in **Kimi Code CLI**, **Claude Code**, and **Roo Code**.
- Using your API Key with unauthorized platforms or tools may be considered a violation and could result in restricted access.
- For questions, refer to the [Benefits](/kimi-code/benefits) page or contact Kimi support.
