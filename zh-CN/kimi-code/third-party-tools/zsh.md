# Zsh 插件集成

[zsh-kimi-cli](https://github.com/MoonshotAI/zsh-kimi-cli) 是一个 Zsh 插件，让你可以在 Zsh 中快速切换到 Kimi Code CLI。

## 安装

如果你使用 Oh My Zsh，可以这样安装：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "git clone https://github.com/MoonshotAI/zsh-kimi-cli.git \\\n  ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/kimi-cli",
    },
  ]}
/>

然后在 `~/.zshrc` 中添加插件：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "plugins=(... kimi-cli)",
    },
  ]}
/>

重新加载 Zsh 配置：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "source ~/.zshrc",
    },
  ]}
/>

## 使用

安装后，在 Zsh 中按 `Ctrl-X` 可以快速切换到 Kimi Code CLI，无需手动输入 `kimi` 命令。

> 如果你使用其他 Zsh 插件管理器（如 zinit、zplug 等），请参考 [zsh-kimi-cli 仓库](https://github.com/MoonshotAI/zsh-kimi-cli) 的 README 了解安装方法。
