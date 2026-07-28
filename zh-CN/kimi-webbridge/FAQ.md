---
title: "常见问题（FAQ）"
slug: "kimi-webbridge-faq"
order: 4
extract_headings: true
preview: false
---

<SeoMeta
  title="Kimi WebBridge 产品介绍 - Kimi Help Center"
  description="Kimi WebBridge 是一款专为 AI Agent 设计的浏览器插件，支持 Chrome 和 Edge，让 Agent 像真人一样与网页交互。"
  ogType="article"
/>

# 常见问题（FAQ）

## 安装与配置

### 安装扩展时提示"无法从该网站添加应用"？

请确保从官方应用商店（Chrome Web Store 或 Edge Add-ons）安装。如无法访问应用商店，可使用官网提供的手动安装方式。

### 运行连接指令后没有反应？

请检查网络连接是否正常。如仍有问题，尝试重启 Kimi Claw Desktop 后再次运行指令。

### 可以在多台电脑上使用吗？

可以，每台电脑需要单独安装和配置 WebBridge。

### 找不到 Kimi Claw Desktop？

Kimi Claw Desktop 是部署在你本地电脑上的 Kimi Claw。打开 Kimi 桌面版，在左侧边栏找到 Kimi Claw，新建一个 Claw，选择部署到"我的电脑"。

## 连接与使用

### 插件状态显示未连接？

请确认已成功安装 Kimi WebBridge 浏览器插件，然后根据你的使用方式操作：

- **Kimi 桌面版**：重启 Kimi 桌面版后重试
- **其他 Local Agent**：在 Agent 中重新发送以下指令，运行后重启 Agent：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "curl -fsSL https://kimi-web-img.moonshot.cn/webbridge/install_skill.sh | bash -s -- -y",
    },
  ]}
/>

### 在Windows中安装WebBridge，报错：安装失败
Kimi WebBridge支持Windows操作系统，可以在Linux环境中运行安装命令：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "irm https://kimi-web-img.moonshot.cn/webbridge/install.ps1 | iex",
    },
  ]}
/>

### 已经完成安装步骤，但使用时提示和 Chrome 不兼容，这是怎么回事？

如果 WebBridge 能正常打开网页，但 `snapshot`、`evaluate`、`screenshot`、`click` 这类操作一直失败，更常见的原因是**浏览器里的其他插件发生了冲突**。

尤其是爬虫类、网站助手类、录屏类、AI 辅助类插件，更容易影响 WebBridge 的正常使用。

建议你这样排查：

1. 打开浏览器扩展管理页
2. 先临时关闭其他插件
3. 只保留 Kimi WebBridge
4. 重启浏览器后再试一次
5. 如果恢复正常，再把其他插件一个个打开，定位冲突插件

### WebBridge 会泄露我的登录信息吗？

不会。所有执行都在你本地完成，登录态和网页内容不会离开你的设备。Agent 只能获取你授权的操作结果。

### 为什么有时候操作会失败？

网页结构复杂或动态加载可能导致操作失败。可以尝试简化指令，或让 Agent 先截图确认页面状态后再执行操作。

### 支持哪些浏览器？

目前支持 Chrome 和 Edge 浏览器，建议使用最新版本以获得最佳体验。

## 与其他 Agent 配合

### 除了 Kimi，还支持哪些 Agent？

WebBridge 支持所有 Local Agent，包括 Claude Code、Codex、Cursor、Kimi Code、Hermes Claw 等。

### 不同 Agent 的配置方式一样吗？

配置指令相同，都是运行一条 curl 命令完成安装。具体可参考各 Agent 的 Skill 配置方式。

## 反馈与帮助

如果你在使用过程中遇到问题或有建议，欢迎提供反馈。

<Callout type="tip">
反馈时信息越完整，我们越能快速定位和解决问题。
</Callout>

<Frames
  src="./images/FAQ/用户群.png"
  alt="Kimi WebBridge用户群"
/>

反馈时请提供：

- **浏览器版本**：例如 Chrome 124.0.6367.82
- **WebBridge 插件版本**：可在浏览器扩展管理页面查看
- **你使用的 AI Agent**：例如 Kimi Desktop、Claude Code、Cursor 等
- **问题描述和截图**：请尽量描述复现步骤
- **相关日志（如有）**：可在插件界面或浏览器控制台获取