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

[Claude Code](https://code.claude.com/docs) 是 Anthropic 推出的命令行编程助手。安装方式请参考 [Claude Code 官方文档](https://code.claude.com/docs/en/getting-started)。

<Callout type="info">
  安装完成后，需要跳过 Anthropic 默认的登录流程。在终端中执行以下命令：
</Callout>

<CodePreview
  files={[
    {
      name: "skip-onboarding.sh",
      content: "node --eval \"\n// enable third party model support and fast mode\nconst claudeJsonFilePath = path.join(os.homedir(), '.claude.json');\nif (fs.existsSync(claudeJsonFilePath)) {\n    const content = JSON.parse(fs.readFileSync(claudeJsonFilePath, 'utf-8'));\n    fs.writeFileSync(claudeJsonFilePath, JSON.stringify({ ...content, penguinModeOrgEnabled: true, hasCompletedOnboarding: true }, null, 2), 'utf-8');\n} else {\n    fs.writeFileSync(claudeJsonFilePath, JSON.stringify({ penguinModeOrgEnabled: true, hasCompletedOnboarding: true }), 'utf-8');\n}\n\n// delete old model id\nconst claudeSettingsJsonFilePath = path.join(os.homedir(), '.claude', 'settings.json');\nif (fs.existsSync(claudeSettingsJsonFilePath)) {\n    const content = JSON.parse(fs.readFileSync(claudeSettingsJsonFilePath, 'utf-8'));\n    if (typeof content === 'object' && typeof content.env === 'object') {\n        for (const element of [\n            'ANTHROPIC_MODEL',\n            'ANTHROPIC_SMALL_FAST_MODEL',\n            'CLAUDE_CODE_SUBAGENT_MODEL',\n            'ANTHROPIC_DEFAULT_FABLE_MODEL',\n            'ANTHROPIC_DEFAULT_FABLE_MODEL_NAME',\n            'ANTHROPIC_DEFAULT_OPUS_MODEL',\n            'ANTHROPIC_DEFAULT_OPUS_MODEL_NAME',\n            'ANTHROPIC_DEFAULT_SONNET_MODEL',\n            'ANTHROPIC_DEFAULT_SONNET_MODEL_NAME',\n            'ANTHROPIC_DEFAULT_HAIKU_MODEL',\n            'ANTHROPIC_DEFAULT_HAIKU_MODEL_NAME',\n        ]) {\n            delete content.env[element];\n        }\n        fs.writeFileSync(claudeSettingsJsonFilePath, JSON.stringify(content, null, 2), 'utf-8');\n    }\n}\n\"",
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
      content:
        "export ANTHROPIC_BASE_URL=https://api.kimi.com/coding/\nexport ANTHROPIC_API_KEY=你的API Key\n\nclaude",
    },
  ]}
/>

**Windows**

<CodePreview
  files={[
    {
      name: "windows.ps1",
      language: "powershell",
      content:
        '$env:ANTHROPIC_BASE_URL="https://api.kimi.com/coding/"\n$env:ANTHROPIC_API_KEY="你的API Key"\n\nclaude',
    },
  ]}
/>

<Callout type="tip">
  启动后输入 `/status` 确认模型已生效。使用快捷键可开启 Thinking 模式：macOS 为
  `Option+T`，Windows 和 Linux 为 `Alt+T`。
</Callout>

### 切换到高速版

高速版输出速度约为普通版的 5–6 倍、**额度消耗约为普通版的 3 倍**，需订阅 [Allegretto](https://www.kimi.com/membership/pricing) 及以上档位会员。在 Claude Code 中有两种开启方式：

- **方式一：`/fast on` 命令**——启动 Claude Code 后输入 `/fast on`，出现 `⚡ Fast mode ON` 提示即为开启成功。
- **方式二：`/config` 命令**——输入 `/config` 打开配置面板，在 **Config** 标签下开启 **Fast mode**（以及 **Thinking mode**）即可。

## 在 Roo Code 中使用

[Roo Code](https://github.com/RooCodeInc/Roo-Code) 是一款 VS Code 中的 AI 编程插件。

### 安装 Roo Code

1. 在 VS Code 扩展市场搜索 **Roo Code** 并安装。
2. 安装完成后，活动栏会出现 Roo Code 图标；如未出现，可重启 VS Code。

### 配置 Kimi Code 模型

1. 打开 Roo Code 面板，进入**设置页**。
2. 在 **Providers** 区域选择 **OpenAI Compatible**，按照提示填写：

   | 配置项     | 值                               |
   | ---------- | -------------------------------- |
   | Entrypoint | `https://api.kimi.com/coding/v1` |
   | API Key    | 你的 API Key                     |
   | Model      | `kimi-for-coding` / `kimi-for-coding-highspeed`（普通版 / 高速版） |

3. 保存配置后即可开始使用。

## 注意事项

- Kimi Code 权益仅支持在 **Kimi Code CLI**、**Claude Code** 和 **Roo Code** 中使用。
- 在其他未授权的平台或工具中使用 API Key 可能被视为违规行为，并可能导致权益受限。
- 如有疑问，请参阅 [权益说明](/kimi-code/benefits) 或联系 Kimi 客服。

## 详细教程

- [在第三方 Coding Agent（Claude Code、Roo Code）中使用](https://www.kimi.com/code/docs/third-party-tools/other-coding-agents.html)
