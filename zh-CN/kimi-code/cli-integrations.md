---
title: "工具集成"
slug: "cli-integrations"
order: 10
extract_headings: false
preview: false
---

<SeoMeta
  title="工具集成 - Kimi 帮助中心"
  description="除了 IDE 集成，Kimi Code CLI 还可以集成到其他工具中，增强你的终端工作流。"
/>

# 工具集成

<Callout type="info">
除了 IDE 集成，Kimi Code CLI 还可以集成到其他工具中，增强你的终端工作流。
</Callout>

## Zsh 插件

[zsh-kimi-cli](https://github.com/MoonshotAI/zsh-kimi-cli) 是一个 Zsh 插件，让你可以在 shell 中快速切换到 Kimi Code CLI。

### 通过 Oh My Zsh 安装

如果你使用 Oh My Zsh，按以下步骤安装：

1. 将仓库克隆到 Oh My Zsh 的自定义插件目录：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "git clone https://github.com/MoonshotAI/zsh-kimi-cli.git\n${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/kimi-cli",
    },
  ]}
/>

2. 在 `~/.zshrc` 的 plugins 列表中加入 `kimi-cli`：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "plugins=(\n# ... other plugins\nkimi-cli\n)",
    },
  ]}
/>

3. 重新加载配置：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "source ~/.zshrc",
    },
  ]}
/>

### 使用

安装完成后，在终端中按 **Ctrl-X** 即可快速切换到 Kimi Code CLI，无需手动输入 `kimi` 命令。
