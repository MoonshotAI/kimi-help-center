---
title: "集成到工具"
slug: "cli-integrations"
order: 8
extract_headings: false
preview: true
preview_content: "将 Kimi Code 集成到 Zsh 等工具中的安装步骤。"
---
<SeoMeta
  title="Kimi Code CLI 工具集成 - Kimi 帮助中心"
  description="了解如何通过 zsh-kimi-cli 插件将 Kimi Code 集成到终端工作流中，使用 Oh My Zsh 一键安装，Ctrl-X 快速唤起 AI 助手。"
  pageUrl="https://www.kimi.com/help/kimi-code/cli-integrations"
/>
# 集成到工具

除了 IDE 集成外，Kimi Code CLI 还可以集成到其他工具中，提升你的终端工作流效率。

## Zsh 插件

[zsh-kimi-cli](https://github.com/MoonshotAI/zsh-kimi-cli) 是一个 Zsh 插件，让你可以在 Zsh 中快速切换到 Kimi Code CLI。

### Oh My Zsh 安装

如果你使用 Oh My Zsh，可以按以下步骤安装：

1. 将仓库克隆到 Oh My Zsh 的自定义插件目录：

   ```bash
   git clone https://github.com/MoonshotAI/zsh-kimi-cli.git \
     ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/kimi-cli
   ```

2. 在 `~/.zshrc` 中将 `kimi-cli` 添加到插件列表：

   ```bash
   plugins=(
     # ... 其他插件
     kimi-cli
   )
   ```

3. 重新加载配置：

   ```bash
   source ~/.zshrc
   ```

### 使用方式

安装完成后，在终端中按 **Ctrl-X** 即可快速切换到 Kimi Code CLI，无需手动输入 `kimi` 命令。
