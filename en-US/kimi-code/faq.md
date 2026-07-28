---
title: "Kimi Code FAQ"
slug: "faq"
order: 4
extract_headings: true
preview: true
preview_content: "Kimi Code frequently asked questions."
---

<SeoMeta
  title="Kimi Code FAQ - Kimi Help Center"
  description="Frequently asked questions about Kimi Code CLI installation, authentication, migration, interaction, and more."
/>

# Frequently asked questions

## Migrating from the legacy version

<Callout type="info">
Kimi Code CLI has gone through a major version upgrade — moving from Python/uv to Node.js, bringing a simpler install experience, faster startup, and a redesigned terminal UI. The legacy version will gradually be phased out, so we recommend upgrading as soon as possible.
</Callout>

If you are migrating from the legacy version, follow the steps below — a single command migrates your config, MCP servers, and session history to the new version.

### What's new

- **No more Python / uv**: Rebuilt on Node.js — no Python environment needed, simpler to install
- **Native binary, works out of the box**: Faster startup, lighter footprint
- **Redesigned terminal UI**: Smoother, more responsive experience
- **Full data migration**: Config, MCP servers, and session history all carry over seamlessly

### How to migrate

There are two ways to migrate.

The **first time you run `kimi`** after installing kimi-code, it automatically checks whether kimi-cli data exists under `~/.kimi/`. If it finds any, a migration prompt appears, and you can choose to migrate now, do it later, or never be asked again.

You can also **run it manually at any time**:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi migrate",
    },
  ]}
/>

You can choose whether to migrate chat sessions as well. If you don't need the history yet, pick **Config only**; otherwise pick **Config + N sessions** to bring everything across in one go. A summary is printed at the end.

### What happens during migration

**What gets migrated**: configuration (`config.toml`), MCP server configuration, input history, and whichever chat sessions you chose to migrate.

**What does not get migrated**: OAuth login credentials and MCP service authorizations are not copied, so you will need to run `/login` again and re-authorize MCP servers after migrating. kimi-cli plugins are also out of scope.

<Callout type="tip">
Migration **never modifies or deletes** any of the old data under `~/.kimi/`. kimi-cli keeps working as before, and the two do not interfere with each other. Migration can also be run repeatedly — sessions that have already been migrated are not imported again.
</Callout>

After migration, sessions imported from kimi-cli are tagged with `[imported]` in the session picker so you can tell them apart from new ones.

## Installation & authentication

### No models available when running `/login`

If you see "No models available for the selected platform" when running `/login`, it may be due to:

- **Invalid or expired API key**: Check whether the API key you entered is correct and still valid.
- **Network connection issue**: Confirm that you can access the API service address (such as `api.kimi.com` or `api.moonshot.cn`).

**Note the platform distinction**

Kimi Code membership benefits and the [Kimi Open Platform](https://platform.kimi.com) have different Base URLs. Please make sure the Base URL matches the API Key when configuring.

| Platform | Base URL | Billing | Key creation |
|------|---------|---------|-------------|
| **Kimi Code** | Anthropic compatible: `https://api.kimi.com/coding/` | Kimi membership subscription (includes credits) | [Kimi Code Console](https://www.kimi.com/code/console) |
| **Kimi Open Platform** | `https://api.moonshot.cn/v1` | Pay-as-you-go | [Kimi Open Platform](https://platform.kimi.com) |

### API key is invalid

Possible reasons for an invalid API key:

- **Key entered incorrectly**: Check for extra spaces or missing characters.
- **Key expired or revoked**: Confirm the key status in the platform console.

### Membership expired or credits exhausted

If you are using the Kimi Code platform, you can check your current credits and membership status via the `/usage` command. If your Credits are exhausted or your membership has expired, you need to renew or upgrade at [Kimi Code](https://kimi.com/code).

## Subscription

### How do I request an invoice or upgrade my membership?

Visit the [Kimi Membership page](https://www.kimi.com/membership/pricing#pricing-faq) and follow the instructions to submit an invoice request or upgrade your plan.

## Interaction issues

### Paste image fails

When pasting an image with `Ctrl-V`, if you see "Current model does not support image input", the current model does not support image input.

Solutions:

- **Switch to a model that supports images**: Use a model with the `image_in` capability.
- **Check clipboard contents**: Make sure the clipboard actually contains image data, not a path to an image file.

## Updates & upgrades

### macOS first launch is slow

macOS Gatekeeper performs a security check the first time a new program runs, causing slower startup. Solutions:

- **Wait for the check to complete**: Be patient on the first run; subsequent launches will return to normal speed.
- **Add to Developer Tools**: Add your terminal app in **System Settings → Privacy & Security → Developer Tools**.

### How to upgrade Kimi Code CLI

Run `kimi upgrade` to check for the latest version and present update options. Choose `Install update now` to upgrade. You can also upgrade directly via the package manager:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "npm install -g @moonshot-ai/kimi-code@latest",
    },
  ]}
/>

## VS Code extension FAQ

Below are frequently asked questions about the Kimi Code VS Code Extension.

### VS Code says no workspace is open

Please open a folder in VS Code. The Kimi Code VS Code extension requires a workspace to function properly.

### VS Code says CLI cannot be found

Please install Kimi Code CLI manually and configure `kimi.executablePath` in VS Code settings, or make sure the built-in CLI is present.

### VS Code login fails

Try skipping login and using API key mode instead, check your network connection, or retry later via the Kimi Code extension action menu.

### VS Code sends messages with no response

Please confirm that Kimi Code CLI is available, the model is configured, and a workspace folder is open in VS Code. Check error logs via "Kimi Code: Show Logs".

### VS Code connection times out

If there is no response within 30 seconds, it will time out. Please check your network and retry.

### VS Code error before sending a message

Certain errors prevent sending messages in VS Code, such as Kimi Code CLI not found, version too low, not logged in, or session busy. The error will be shown as a toast notification, and your input will be preserved for retry.

## Feedback & contact

### Documentation did not solve my problem

If the above did not solve your problem, feel free to contact us via email: [code@moonshot.ai](mailto:code@moonshot.ai). Please describe the issue you encountered, the steps you took, and any relevant log information in the email, and we will respond as soon as possible.

If you have any issues or suggestions, you can also provide feedback on [GitHub Issues](https://github.com/MoonshotAI/kimi-cli/issues).
