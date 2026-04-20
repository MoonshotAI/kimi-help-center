---
title: "如何卸载 Kimi 插件？"
slug: "uninstall-plugin"
order: 15
extract_headings: false
preview: true
preview_content: "如何安全卸载 Kimi Claw 中的插件。"
---
<SeoMeta
  title="如何卸载 Kimi Claw 插件？ - Kimi 帮助中心"
  description="了解在各平台上卸载 Kimi Claw 插件的具体步骤，包括飞书、浏览器等环境下的完整卸载方法和注意事项。"
  pageUrl="https://www.kimi.com/help/kimi-claw/uninstall-plugin"
/>
# 卸载 Kimi 插件

//
**此操作仅适用于关联 OpenClaw 的设备**。请确认你是在自己部署的 OpenClaw 设备上执行卸载操作。
Callout 警告
//

## 卸载命令

在关联 OpenClaw 的设备上运行以下命令即可卸载 Kimi 插件：

//
bash <(curl -fsSL https://cdn.kimi.com/kimi-claw/uninstall.sh) CodePreview
//

## 严重警告

**不要在一键部署的 Kimi Claw 上运行此命令！**

在一键部署的 Kimi Claw 设备上运行卸载命令会导致你与 Kimi Claw 的连接**永久断开且不可修复**。此命令仅用于从自行部署的 OpenClaw 设备上移除 Kimi 插件。
