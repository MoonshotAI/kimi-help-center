---
title: "Tool integrations"
slug: "cli-integrations"
order: 8
extract_headings: false
preview: false
---

<SeoMeta
  title="Tool integrations - Kimi Help Center"
  description="In addition to IDE integration, Kimi Code CLI can be integrated into other tools to enhance your terminal workflow."
/>

# Tool integrations

<Callout type="info">
In addition to IDE integration, Kimi Code CLI can be integrated into other tools to enhance your terminal workflow.
</Callout>

## Zsh plugin

[zsh-kimi-cli](https://github.com/MoonshotAI/zsh-kimi-cli) is a Zsh plugin that lets you quickly switch to Kimi Code CLI from your shell.

### Oh My Zsh installation

If you use Oh My Zsh, follow these steps to install:

1. Clone the repository into Oh My Zsh's custom plugins directory:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "git clone https://github.com/MoonshotAI/zsh-kimi-cli.git\n${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/kimi-cli",
    },
  ]}
/>

2. Add `kimi-cli` to the plugins list in `~/.zshrc`:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "plugins=(\n# ... other plugins\nkimi-cli\n)",
    },
  ]}
/>

3. Reload the configuration:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "source ~/.zshrc",
    },
  ]}
/>

### Usage

Once installed, press **Ctrl-X** in your terminal to quickly switch to Kimi Code CLI without manually typing the `kimi` command.
