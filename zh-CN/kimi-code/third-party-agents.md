---
title: "在第三方 Coding Agent 中使用"
slug: "third-party-agents"
order: 13
extract_headings: false
preview: true
preview_content: "在 Claude Code、Roo Code 等第三方 Agent 中使用 Kimi 模型。"
---

<SeoMeta
  title="第三方 Coding Agent 中使用 Kimi - Kimi 帮助中心"
  description="了解如何在 Claude Code 和 Roo Code 等第三方 Coding Agent 中配置和使用 Kimi 模型，包括环境变量设置和 API 兼容配置步骤。"
/>
# 在第三方 Coding Agent 中使用

Kimi Code 权益支持在主流 Coding Agent 中使用——例如 Claude Code、Roo Code、OpenCode 等；也可以配合 OpenClaw、Hermes 等通用 Agent 框架。让你在自己习惯的工具里自由调用 Kimi 的 AI 能力。

本文档将展示 Claude Code 与 Roo Code 的配置方法。

## 前提条件

- 已订阅 Kimi 会员并开通 Kimi Code 权益。
- 已获取 API Key（在 [Kimi Code 控制台](https://www.kimi.com/code/console) 中创建）。

## 在 Claude Code 中使用

[Claude Code](https://docs.anthropic.com/en/docs/claude-code) 是 Anthropic 推出的命令行编程助手。安装方式请参考 [Claude Code 官方文档](https://docs.anthropic.com/en/docs/claude-code/getting-started)。

<Callout type="info">
安装完成后，需要跳过 Anthropic 默认的登录流程。在终端中执行以下命令：
</Callout>

<CodePreview
  files={[
    {
      name: "skip-onboarding.sh",
      language: "bash",
      content: "echo '{\"hasCompletedOnboarding\": true}' > ~/.claude.json",
    },
  ]}
/>

### 配置 Kimi Code 模型

设置环境变量后启动 Claude Code：

**macOS / Linux**

<CodePreview
  files={[
    {
      name: "mac-linux.sh",
      language: "bash",
      content: "export ANTHROPIC_BASE_URL=https://api.kimi.com/coding/\nexport ANTHROPIC_API_KEY=你的API Key\n\nclaude",
    },
  ]}
/>

**Windows**

<CodePreview
  files={[
    {
      name: "windows.ps1",
      language: "powershell",
      content: "$env:ANTHROPIC_BASE_URL=\"https://api.kimi.com/coding/\"\n$env:ANTHROPIC_API_KEY=\"你的API Key\"\n\nclaude",
    },
  ]}
/>

<Callout type="tip">
启动后输入 `/status` 确认模型已生效。使用快捷键可开启 Thinking 模式：macOS 为 `Option+T`，Windows 和 Linux 为 `Alt+T`。
</Callout>

<Callout type="tip">
在 Claude Code 中，你可以使用 **Tab** 键切换到 Kimi K2 Thinking 模型。
</Callout>

<Callout type="tip">
如果遇到 `tool_search` 调用导致的 400 错误，可以通过配置环境变量 `ENABLE_TOOL_SEARCH=false` 暂时解决。
</Callout>

## 在 Roo Code 中使用

[Roo Code](https://github.com/RooCodeInc/Roo-Code) 是一款 VS Code 中的 AI 编程插件。

### 安装 Roo Code

1. 在 VS Code 扩展市场搜索 **Roo Code** 并安装。
2. 安装完成后，活动栏会出现 Roo Code 图标；如未出现，可重启 VS Code。

### 配置 Kimi Code 模型

1. 打开 Roo Code 面板，进入**设置页**。
2. 在 **Providers** 区域选择 **OpenAI Compatible**，按照提示填写：

   | 配置项 | 值 |
   | --- | --- |
   | Entrypoint | `https://api.kimi.com/coding/v1` |
   | API Key | 你的 API Key |
   | Model | `kimi-k2.5` |

3. 保存配置后即可开始使用。

## 注意事项

- Kimi Code 权益仅支持在 **Kimi Code CLI**、**Claude Code** 和 **Roo Code** 中使用。
- 在其他未授权的平台或工具中使用 API Key 可能被视为违规行为，并可能导致权益受限。
- 如有疑问，请参阅 [权益说明](/kimi-code/benefits) 或联系 Kimi 客服。

## 详细教程

- [在 JetBrains IDE 中使用](https://www.kimi.com/code/docs/third-party-tools/jetbrains.html)
- [在 Zed 中使用](https://www.kimi.com/code/docs/third-party-tools/zed.html)
- [Zsh 插件集成](https://www.kimi.com/code/docs/third-party-tools/zsh.html)
- [在第三方 Coding Agent（Claude Code、Roo Code）中使用](https://www.kimi.com/code/docs/third-party-tools/other-coding-agents.html)
