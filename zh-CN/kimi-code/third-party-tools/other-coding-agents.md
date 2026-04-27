# 在第三方 Coding Agent 中使用

Kimi Code 权益支持在主流 Coding Agent 中使用——例如 Claude Code、Roo Code、OpenCode 等；也可以配合 OpenClaw、Hermes 等通用 Agent 框架。让你在自己习惯的工具里自由调用 Kimi 的 AI 能力。

本文档将展示 Claude Code 与 Roo Code 的配置方法

## 前提条件

- 已订阅 Kimi 会员并开通 Kimi Code 权益。
- 已获取 API Key（在 [Kimi Code 控制台](https://www.kimi.com/code/console) 中创建）。

## Claude Code

[Claude Code](https://docs.anthropic.com/en/docs/claude-code) 是 Anthropic 推出的命令行编程助手。安装方式请参考 [Claude Code 官方文档](https://docs.anthropic.com/en/docs/claude-code/getting-started)。

> 安装完成后，需要跳过 Anthropic 默认的登录流程。在终端中执行以下脚本：
>
><CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "node --eval \"\n    const homeDir = os.homedir();\n    const filePath = path.join(homeDir, '.claude.json');\n    if (fs.existsSync(filePath)) {\n        const content = JSON.parse(fs.readFileSync(filePath, 'utf-8'));\n        fs.writeFileSync(filePath, JSON.stringify({ ...content, hasCompletedOnboarding: true }, null, 2), 'utf-8');\n    } else {\n        fs.writeFileSync(filePath, JSON.stringify({ hasCompletedOnboarding: true }), 'utf-8');\n    }\"",
    },
  ]}
/>

### 配置 Kimi Code 模型

设置环境变量后启动 Claude Code：

**macOS / Linux**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "export ENABLE_TOOL_SEARCH=false\nexport ANTHROPIC_BASE_URL=https://api.kimi.com/coding/\nexport ANTHROPIC_API_KEY=你的API Key\n\nclaude",
    },
  ]}
/>

**Windows**

<CodePreview
  files={[
    {
      name: "command.ps1",
      language: "powershell",
      content: '$env:ENABLE_TOOL_SEARCH="false"\n$env:ANTHROPIC_BASE_URL="https://api.kimi.com/coding/"\n$env:ANTHROPIC_API_KEY="你的API Key"\n\nclaude',
    },
  ]}
/>

启动后输入 `/status` 确认模型已生效。使用 Tab 键可切换到 Kimi K2 Thinking 模型。

---

## Roo Code

[Roo Code](https://docs.roocode.com/) 是一款 VS Code 中的 AI 编程插件。如尚未安装，请在 VS Code 扩展市场搜索 `Roo Code` 并安装。

### 配置 Kimi Code 模型

打开 Roo Code 面板 → 设置页 → Providers 区域选择 `OpenAI Compatible`，填写以下信息：

| 配置项 | 值 |
| --- | --- |
| Entrypoint | `https://api.kimi.com/coding/v1` |
| API Key | 你的 Kimi Code API Key |
| Model | `kimi-for-coding` |

其余选项按如下方式设置：

<CodePreview
  files={[
    {
      name: "settings.txt",
      language: "text",
      content: "Use legacy OpenAI API format  ✓\nEnable streaming              ✓\nInclude max output tokens     ✓\nEnable Reasoning Effort       Medium\nMax Output Tokens             32768\nContext Window Size           262144",
    },
  ]}
/>

其中 Max Output Tokens 和 Context Window Size 用于告知 Roo Code 模型的能力范围，不填可能导致输出截断或上下文不足。

保存配置后新建会话即可使用。


> **注意**：使用时请保持工具的真实身份标识，篡改客户端标识（User-Agent）将被视为违规，可能导致会员权益暂停。