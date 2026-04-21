---
title: "IDE integration"
slug: "cli-ides"
order: 7
extract_headings: false
preview: false
---

<SeoMeta
  title="IDE integration - Kimi Help Center"
  description="Kimi Code CLI supports integration into IDEs via the Agent Client Protocol ACP, allowing you to use AI coding capabilities directly within your editor."
/>

# IDE integration

<Callout type="info">
Kimi Code CLI supports integration into IDEs via the Agent Client Protocol (ACP), allowing you to use AI coding capabilities directly within your editor.
</Callout>

<Callout type="warning">
Before configuring your IDE, make sure Kimi Code CLI is installed and you have completed the `/login` setup.
</Callout>

## Using with Zed

[Zed](https://zed.dev/) is a modern IDE with native ACP support.

Add the following configuration to Zed's settings file `~/.config/zed/settings.json`:

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\n  \"agent_servers\": [\n    {\n      \"id\": \"kimi-cli\",\n      \"name\": \"Kimi Code\",\n      \"command\": \"kimi\",\n      \"args\": [\"acp\"]\n    }\n  ]\n}",
    },
  ]}
/>

After saving the configuration, you can select Kimi Code in Zed's Agent panel to start a conversation.

## Using with JetBrains IDEs

The JetBrains family of IDEs (IntelliJ IDEA, PyCharm, WebStorm, etc.) supports ACP through the AI Assistant plugin.

### Prerequisites

1. Ensure the AI Assistant plugin is installed and enabled.
2. Enable the experimental feature in the Registry:
   - Open **Help → Find Action** and search for `Registry...`
   - Find and enable `llm.enable.mock.response`

### Configuration steps

1. Open the **AI Chat panel**.
2. Click **Configure ACP agents**.
3. Add a new ACP configuration:

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\n  \"id\": \"kimi-cli\",\n  \"name\": \"Kimi Code\",\n  \"command\": \"/path/to/kimi\",\n  \"args\": [\"acp\"]\n}",
    },
  ]}
/>

<Callout type="tip">
The `command` field requires the full path to `kimi`. Find it by running `which kimi` in your terminal.
</Callout>

>

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "which kimi",
    },
  ]}
/>

After configuration, select Kimi Code in the AI Chat panel to get started.
