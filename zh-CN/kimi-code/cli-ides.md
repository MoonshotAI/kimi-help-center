---
title: "在 IDE 中使用"
slug: "cli-ides"
order: 7
extract_headings: false
preview: true
preview_content: "在 Zed、JetBrains 等 IDE 中使用 Kimi Code 的配置方法。"
---
<SeoMeta
  title="在 IDE 中使用 Kimi Code - Kimi 帮助中心"
  description="通过 ACP 协议将 Kimi Code 集成到 Zed 和 JetBrains IDE（IntelliJ/PyCharm/WebStorm 等）中的详细配置步骤。"
  pageUrl="https://www.kimi.com/help/kimi-code/cli-ides"
/>
# 在 IDE 中使用

Kimi Code CLI 支持通过 Agent Client Protocol（ACP）集成到 IDE 中，让你在编辑器内直接使用 AI 编程能力。

//
在配置 IDE 之前，请确保已安装 Kimi Code CLI 并完成 `/login` 配置。
Callout 注意
//

## 在 Zed 中使用

[Zed](https://zed.dev/) 是一个原生支持 ACP 的现代 IDE。

在 Zed 的配置文件 `~/.config/zed/settings.json` 中添加以下配置：

//
{
  "agent_servers": [
    {
      "id": "kimi-cli",
      "name": "Kimi Code",
      "command": "kimi",
      "args": ["acp"]
    }
  ]
}
CodePreview
//

保存配置后，在 Zed 的 Agent 面板中即可选择 Kimi Code 进行对话。

## 在 JetBrains IDE 中使用

JetBrains 全家桶（IntelliJ IDEA、PyCharm、WebStorm 等）通过 AI Assistant 插件支持 ACP。

### 前置条件

1. 确保 AI Assistant 插件已安装并启用。
2. 需要在注册表（Registry）中启用实验性功能：
   - 打开 **Help → Find Action**，搜索 `Registry...`
   - 找到并勾选 `llm.enable.mock.response`

### 配置步骤

1. 打开 **AI 聊天面板**。
2. 点击 **Configure ACP agents**。
3. 添加新的 ACP 配置：

//
   {
     "id": "kimi-cli",
     "name": "Kimi Code",
     "command": "/path/to/kimi",
     "args": ["acp"]
   }
CodePreview
//

//
`command` 字段需要使用 `kimi` 的完整路径。可以在终端中运行 `which kimi` 获取：

which kimi

Callout 警告
//

配置完成后，在 AI 聊天面板中选择 Kimi Code 即可开始使用。
