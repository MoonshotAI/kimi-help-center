# 在 JetBrains IDE 中使用

Kimi Code CLI 支持通过 [Agent Client Protocol (ACP)](https://agentclientprotocol.com/) 集成到 IDE 中，让你在编辑器内直接使用 AI 辅助编程。

## 前提条件

- 已安装 [Kimi Code CLI](/kimi-code-cli/getting-started) 并完成 `kimi /login` 配置。
- JetBrains IDE 版本支持 AI 聊天功能（含 ACP）。

## 配置方法

JetBrains 系列 IDE（IntelliJ IDEA、PyCharm、WebStorm 等）通过 AI 聊天插件支持 ACP。

如果你没有 JetBrains AI 订阅，可以在注册表中启用 `llm.enable.mock.response` 来使用 AI 聊天功能。连按两次 Shift 搜索 "注册表" 即可打开。

在 AI 聊天面板的菜单中点击 "Configure ACP agents"，添加以下配置：

<CodePreview
  files={[
    {
      name: "config.json",
      language: "json",
      content: '{\n  "agent_servers": {\n    "Kimi Code CLI": {\n      "command": "~/.local/bin/kimi",\n      "args": ["acp"],\n      "env": {}\n    }\n  }\n}',
    },
  ]}
/>

`command` 需要使用完整路径，可以在终端中运行 `which kimi` 获取。保存后，在 AI 聊天的 Agent 选择器中就可以选择 Kimi Code CLI 了。


