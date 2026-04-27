# 在 Zed 中使用

Kimi Code CLI 支持通过 [Agent Client Protocol (ACP)](https://agentclientprotocol.com/) 集成到 IDE 中，让你在编辑器内直接使用 AI 辅助编程。

## 前提条件

- 已安装 [Kimi Code CLI](/kimi-code-cli/getting-started) 并完成 `kimi /login` 配置。
- 已安装 [Zed](https://zed.dev/) 编辑器。

## 配置方法

[Zed](https://zed.dev/) 是一个支持 ACP 的现代 IDE。

在 Zed 的配置文件 `~/.config/zed/settings.json` 中添加：

<CodePreview
  files={[
    {
      name: "config.json",
      language: "json",
      content: '{\n  "agent_servers": {\n    "Kimi Code CLI": {\n      "type": "custom",\n      "command": "kimi",\n      "args": ["acp"],\n      "env": {}\n    }\n  }\n}',
    },
  ]}
/>

配置说明：

- `type`：固定值 `"custom"`
- `command`：Kimi Code CLI 的命令路径，如果 `kimi` 不在 PATH 中，需要使用完整路径
- `args`：启动参数，`acp` 启用 ACP 模式
- `env`：环境变量，通常留空即可

保存配置后，在 Zed 的 Agent 面板中就可以创建 Kimi Code CLI 会话了。


