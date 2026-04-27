# 快速开始

Kimi Code for VS Code 是集成于 Visual Studio Code 的扩展插件。安装后，您可在编辑器内直接发起提问、审查代码 diff 并快速提交变更。插件能够读取您引用的文件内容，并通过可视化界面展示修改建议，经您确认后执行。整个流程由您掌控，同时显著提升开发效率。

![Kimi Code VS Code](/images/zh/vscode/kimi-code-showcase.jpeg)


本扩展在 VS Code 中提供了原生聊天面板，支持通过 `@` 符号引用文件或文件夹、`/` 命令执行项目扫描与上下文管理、diff 视图展示文件变更并支持回退操作，同时支持集成 MCP 服务器以调用外部工具。聊天面板可置于活动栏、侧边栏或独立标签页中。

## 安装之前

需拥有 Kimi 账号订阅或 Kimi API 密钥。

## 安装方式

通过 [VS Code Marketplace](vscode:extension/moonshot-ai.kimi-code) 安装。

若安装后未显示扩展，请重启 VS Code 或在命令面板中执行 "Developer: Reload Window" (Mac: Cmd+Shift+P, Windows/Linux: Ctrl+Shift+P)。

## 身份认证

Kimi Code 支持两种认证模式：

**Kimi 账号模式**：点击登录按钮，浏览器将打开授权页面，完成授权流程后返回 VS Code。

**API Key 模式**：若已配置 API Key，可点击跳过登录。插件将在此模式下运行。

![Kimi Code Gear Icon](/images/zh/vscode/kimi-code-gear-icon.png)

您可随时通过齿轮图标切换认证模式。登出后将返回登录界面。

## 典型工作流

**代码解读**：输入 `@` 选择文件或文件夹，请求解释代码流程，可继续追问细节。

**重构**：引用目标代码如 `@src/feature/`，请求重构方案，审查 diff 并选择性批准，必要时使用回退。

**调试**：粘贴错误信息或堆栈跟踪，引用相关文件，请求诊断与修复，然后批准提议的变更。

**项目概览**：引用文件夹如 `@src/services/`，请求模块地图或架构摘要，可继续询问依赖关系或薄弱环节。

## 命令与快捷键

| 快捷键                          | 功能                                  |
| ------------------------------ | ------------------------------------ |
| `Ctrl+Shift+K` / `Cmd+Shift+K` | 聚焦 Kimi 输入框                      |
| `Alt+K`                        | 插入当前文件引用                      |
| `Ctrl+N` / `Cmd+N`             | 新建对话（需启用 `kimi.enableNewConversationShortcut`，启用后将占用系统默认的"新建文件"快捷键）|
| `↑` / `↓`                      | 在输入框中浏览输入历史                |

在命令面板中输入 "Kimi Code" 可访问更多命令：在新标签页打开、在侧边栏打开、新建对话等。

## 下一步

- [核心操作](/kimi-code-for-vscode/core-operations) – 学习聊天面板用法、上下文管理与 diff 审查
- [定制化](/kimi-code-for-vscode/customization) – 探索 Skills、Hooks 与 MCP 扩展能力
- [配置](/kimi-code-for-vscode/configuration) – 自定义认证、模型与行为设置
