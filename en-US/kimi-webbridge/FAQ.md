---
title: "FAQ"
slug: "kimi-webbridge-faq"
order: 3
extract_headings: true
preview: false
---

<SeoMeta
  title="Kimi WebBridge FAQ - Kimi Help Center"
  description="Frequently asked questions about Kimi WebBridge installation, connection, and usage with multiple browsers and Local Agents."
  ogType="article"
/>

# FAQ

## Installation and configuration

### See "Cannot add apps from this website" when installing the extension?

Please make sure to install from the official web store (Chrome Web Store or Edge Add-ons). If you cannot access the web store, use the manual installation method provided on the official website.

### Nothing happens after running the connection command?

Please check your internet connection. If the issue persists, try restarting Kimi Claw Desktop and run the command again.

### Can I use it on multiple computers?

Yes, but each computer needs to be installed and configured separately.

### I cannot find Kimi Claw Desktop?

Kimi Claw Desktop is a Kimi Claw deployed on your local computer. Open Kimi Desktop, find Kimi Claw in the left sidebar, create a new Claw, and select "Deploy on my computer".

## Connection and usage

### The extension status shows "Disconnected"?

Please confirm that the Kimi WebBridge browser extension is successfully installed, then follow the steps for your setup method:

- **Kimi Desktop**: Restart Kimi Desktop and try again

- **Other Local Agents**: Resend the following command in your Agent, then restart the Agent after it runs:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "curl -fsSL https://kimi-web-img.moonshot.cn/webbridge/install_skill.sh | bash -s -- -y",
    },
  ]}
/>

### In Windows, installing WebBridge, error: Installation failed

Kimi WebBridge supports the Windows operating system, and the installation command can be run in a Linux environment:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "irm https://kimi-web-img.moonshot.cn/webbridge/install.ps1 | iex",
    },
  ]}
/>

### WebBridge shows a Chrome compatibility warning after installation. What does that mean?

If WebBridge can open pages normally, but actions such as `snapshot`, `evaluate`, `screenshot`, or `click` keep failing, the more common cause is **a conflict with other browser extensions**.

This is especially common with scraping tools, website helper extensions, screen recording extensions, and AI assistant extensions.

We recommend the following steps to troubleshoot:

1. Open your browser's extensions management page
2. Temporarily disable other extensions
3. Keep only Kimi WebBridge enabled
4. Restart the browser and try again
5. If WebBridge works normally, re-enable the other extensions one by one to identify the conflicting extension


### Will WebBridge leak my login information?

No. All execution happens locally on your device—login states and web page content never leave your machine. The Agent can only access the operation results you authorize.

### Why do operations fail?

Complex page structures or dynamic loading may cause operations to fail. Try simplifying your instructions, or ask the Agent to take a screenshot first to confirm the page state before executing.

### Which browsers are supported?

Currently supports Chrome and Edge. We recommend using the latest version for the best experience.

## Working with other agents

### Which other Agents are supported?

WebBridge supports all Local Agents, including Claude Code, Codex, Cursor, Kimi Code, Hermes Claw, and more.

### Is the configuration the same for different Agents?

The setup command is the same for all—run a single curl command to install. Refer to each Agent's Skill configuration for details.
