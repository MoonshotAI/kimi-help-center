---
title: "IDE integration"
slug: "cli-ides"
order: 7
extract_headings: false
preview: true
preview_content: "Integrate Kimi Code CLI into your IDE via ACP."
---

<SeoMeta
  title="IDE integration - Kimi Help Center"
  description="Integrate Kimi Code CLI into your IDE via the Agent Client Protocol (ACP). Setup guides for Zed, JetBrains IDEs, and Paseo, plus troubleshooting."
/>

# Using Kimi Code CLI in IDEs

<Callout type="info">
Kimi Code CLI supports integration into IDEs via the [Agent Client Protocol (ACP)](https://agentclientprotocol.com/get-started/introduction), letting you use AI-assisted coding directly inside your editor.
</Callout>

## Prerequisites

Before configuring your IDE, make sure Kimi Code CLI is installed and you have completed the login setup.

The ACP adapter is exposed as the `kimi acp` subcommand. The IDE launches it as a child process and communicates over stdin/stdout using JSON-RPC. Each time the IDE creates a session, the CLI reuses its existing authentication state — no need to log in again.

<Callout type="tip">
Child processes launched from an IDE GUI on macOS typically do **not** inherit the terminal shell's `PATH`. If `kimi` is not in a system directory like `/usr/local/bin`, use the absolute path in your IDE configuration. Run `which kimi` in a terminal to find the active path.
</Callout>

## Using Kimi Code CLI in Zed

[Zed](https://zed.dev/) is a modern editor with native ACP support.

Add the following to Zed's config file at `~/.config/zed/settings.json`:

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\n  \"agent_servers\": {\n    \"Kimi Code CLI\": {\n      \"type\": \"custom\",\n      \"command\": \"kimi\",\n      \"args\": [\"acp\"],\n      \"env\": {}\n    }\n  }\n}",
    },
  ]}
/>

Configuration fields:

- `type`: fixed value `"custom"`
- `command`: path to the Kimi Code CLI executable. If `kimi` is not on `PATH`, use the full path (e.g. `/Users/you/.local/bin/kimi`).
- `args`: startup arguments. The `acp` subcommand switches the CLI into ACP mode.
- `env`: additional environment variables; usually leave this empty. Zed injects a default environment automatically.

After saving, open a new conversation in Zed's Agent panel and it will launch a `Kimi Code CLI` ACP subprocess using the configuration above. MCP servers declared in Zed's `agent_servers` section are also forwarded to the kimi side via the ACP protocol.

## Using Kimi Code CLI in JetBrains IDEs

JetBrains IDEs (IntelliJ IDEA, PyCharm, WebStorm, etc.) support ACP through the AI chat plugin.

If you do not have a JetBrains AI subscription, you can enable `llm.enable.mock.response` in the Registry to access the AI chat panel in ACP-only scenarios. Press Shift twice and search for "Registry" to open it.

In the AI chat panel menu, click **Configure ACP agents** and add the following configuration:

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\n  \"agent_servers\": {\n    \"Kimi Code CLI\": {\n      \"command\": \"~/.local/bin/kimi\",\n      \"args\": [\"acp\"],\n      \"env\": {}\n    }\n  }\n}",
    },
  ]}
/>

JetBrains is strict about the `command` field — always use an **absolute path**, which you can get by running `which kimi` in a terminal. After saving, `Kimi Code CLI` will appear in the AI chat's agent selector.

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "which kimi",
    },
  ]}
/>

## Using Kimi Code CLI in Paseo

[Paseo](https://paseo.sh/) is a self-hosted orchestrator that runs and supervises agent CLIs from your desktop, web, and mobile. It connects to Kimi Code CLI over ACP, the same way an IDE does.

Pick **Kimi Code CLI** from Paseo's built-in ACP provider catalog, or add a custom provider in `~/.paseo/config.json`:

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\n  \"agents\": {\n    \"providers\": {\n      \"kimi\": {\n        \"extends\": \"acp\",\n        \"label\": \"Kimi Code CLI\",\n        \"command\": [\"kimi\", \"acp\"]\n      }\n    }\n  }\n}",
    },
  ]}
/>

Paseo's generic ACP adapter does not drive the login flow, so complete the terminal login first (see [Prerequisites](#prerequisites)) — otherwise session creation fails with `Authentication required`.

## Troubleshooting

- **Session disconnects immediately / IDE shows "agent exited"**: usually a wrong `command` path or a missing login. Run `kimi acp` in a terminal first to verify — if it blocks waiting for stdin, the CLI itself is fine and the problem is in the IDE configuration; if it exits immediately with an error, follow the error message (most commonly you need to run `/login`).
- **IDE shows "auth required"**: the CLI has no usable authentication token. Exit the IDE, run `kimi` in a terminal to complete login, then restart the IDE.
- **MCP tools not visible**: check the `kimi acp` capability table to confirm that the MCP transport type configured in your IDE is supported. The Kimi Code CLI ACP adapter currently supports `http` and `stdio` transports; `sse` and `acp` types are silently dropped and a warning is written to the log.

