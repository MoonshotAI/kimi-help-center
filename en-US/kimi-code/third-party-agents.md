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

# Using with third-party coding agents

Kimi Code benefits can be used with Claude Code and Roo Code, allowing you to enjoy Kimi's AI capabilities within your preferred coding tools.

## Prerequisites

- An active Kimi membership with Kimi Code benefits enabled.
- An API Key (created in the [Kimi Console](https://www.kimi.com/code)).

## Using with Claude Code

[Claude Code](https://code.claude.com/docs/en/overview) is a command-line coding assistant by Anthropic.

### Configuration steps

After installation, do not start Claude directly. First run the following script in the terminal to skip Anthropic's default login flow:

<CodePreview
  files={[
    {
      name: "skip-onboarding.sh",
      content: "node --eval \"\n// enable third party model support and fast mode\nconst claudeJsonFilePath = path.join(os.homedir(), '.claude.json');\nif (fs.existsSync(claudeJsonFilePath)) {\n    const content = JSON.parse(fs.readFileSync(claudeJsonFilePath, 'utf-8'));\n    fs.writeFileSync(claudeJsonFilePath, JSON.stringify({ ...content, penguinModeOrgEnabled: true, hasCompletedOnboarding: true }, null, 2), 'utf-8');\n} else {\n    fs.writeFileSync(claudeJsonFilePath, JSON.stringify({ penguinModeOrgEnabled: true, hasCompletedOnboarding: true }), 'utf-8');\n}\n\n// delete old model id\nconst claudeSettingsJsonFilePath = path.join(os.homedir(), '.claude', 'settings.json');\nif (fs.existsSync(claudeSettingsJsonFilePath)) {\n    const content = JSON.parse(fs.readFileSync(claudeSettingsJsonFilePath, 'utf-8'));\n    if (typeof content === 'object' && typeof content.env === 'object') {\n        for (const element of [\n            'ANTHROPIC_MODEL',\n            'ANTHROPIC_SMALL_FAST_MODEL',\n            'CLAUDE_CODE_SUBAGENT_MODEL',\n            'ANTHROPIC_DEFAULT_FABLE_MODEL',\n            'ANTHROPIC_DEFAULT_FABLE_MODEL_NAME',\n            'ANTHROPIC_DEFAULT_OPUS_MODEL',\n            'ANTHROPIC_DEFAULT_OPUS_MODEL_NAME',\n            'ANTHROPIC_DEFAULT_SONNET_MODEL',\n            'ANTHROPIC_DEFAULT_SONNET_MODEL_NAME',\n            'ANTHROPIC_DEFAULT_HAIKU_MODEL',\n            'ANTHROPIC_DEFAULT_HAIKU_MODEL_NAME',\n        ]) {\n            delete content.env[element];\n        }\n        fs.writeFileSync(claudeSettingsJsonFilePath, JSON.stringify(content, null, 2), 'utf-8');\n    }\n}\n\"",
    },
  ]}
/>

Then set the environment variables and launch:

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

2. Launch Claude Code with the `kimi-for-coding` model:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "claude --model kimi-for-coding",
    },
  ]}
/>

> In Claude Code, you can press **Tab** to switch to the Kimi K2 Thinking model.

> If you encounter a 400 error caused by `tool_search` calls, you can temporarily resolve it by setting the environment variable `ENABLE_TOOL_SEARCH=false`.

### Switching to HighSpeed

HighSpeed delivers roughly 5–6× the output speed of Standard at about **3× the credit usage**, and requires an [Allegretto](https://www.kimi.com/membership/pricing) plan or above. There are two ways to enable it in Claude Code:

- **Option 1: the `/fast on` command** — after starting Claude Code, type `/fast on`; the `⚡ Fast mode ON` output confirms it's enabled.
- **Option 2: the `/config` command** — type `/config` to open the config panel, then enable **Fast mode** (and **Thinking mode**) under the **Config** tab.

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
   | Model | `kimi-for-coding` / `kimi-for-coding-highspeed` (Standard / HighSpeed) |

3. Save the configuration and you're ready to go.

## Important notes

- Kimi Code benefits are only supported in **Kimi Code CLI**, **Claude Code**, and **Roo Code**.
- Using your API Key with unauthorized platforms or tools may be considered a violation and could result in restricted access.
- For questions, refer to the [Benefits](/kimi-code/benefits) page or contact Kimi support.
