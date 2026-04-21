---
title: "在第三方 Coding Agent 中使用"
slug: "third-party-agents"
order: 11
extract_headings: false
preview: true
preview_content: "在 Claude Code、Roo Code 等第三方 Agent 中使用 Kimi 模型。"
---
<SeoMeta
  title="第三方 Coding Agent 中使用 Kimi - Kimi 帮助中心"
  description="了解如何在 Claude Code 和 Roo Code 等第三方 Coding Agent 中配置和使用 Kimi 模型，包括环境变量设置和 API 兼容配置步骤。"
/>
# 在第三方 Coding Agent 中使用

Kimi Code 权益支持在 Claude Code 和 Roo Code 中使用，让你可以在自己习惯的编程工具中享受 Kimi 的 AI 能力。

## 前提条件

- 已订阅 Kimi 会员并开通 Kimi Code 权益。
- 已获取 API Key（在 [Kimi 控制台](https://kimi.com/code) 中创建）。

## 在 Claude Code 中使用

[Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview) 是 Anthropic 推出的命令行编程助手。

### 配置步骤

1. 设置环境变量：

   ```bash
   export ANTHROPIC_BASE_URL=https://api.kimi.com/coding/v1
   export ANTHROPIC_API_KEY=你的API Key
   ```

2. 启动 Claude Code，使用 `kimi-k2.5` 模型：

   ```bash
   claude --model kimi-k2.5
   ```

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
- 如有疑问，请参阅 [权益说明](benefits.md) 或联系 Kimi 客服。
