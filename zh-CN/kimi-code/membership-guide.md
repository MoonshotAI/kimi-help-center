---
title: "Kimi Code 会员权益指南"
slug: "membership-guide"
order: 1
extract_headings: false
preview: true
preview_content: "Kimi Code 会员权益、API Key 管理与设备登录指南。"
---
<SeoMeta
  title="Kimi Code 会员权益指南 - Kimi 帮助中心"
  description="了解 Kimi Code 的会员权益，包括兼容多种 Agent 工具、100 Tokens/s 高速推理、高频并发支持，以及 API Key 获取与设备管理方法。"
  pageUrl="https://www.kimi.com/help/kimi-code/membership-guide"
/>
# Kimi Code 会员权益指南

Kimi Code 是 Kimi 会员计划中专为代码开发打造的权益，为开发者提供高性能的 AI 编程能力。你可以通过 Kimi Code CLI、Claude Code、Roo Code 等多种工具使用该权益。

## 核心优势

- **广泛兼容**：支持 Kimi Code CLI、Claude Code、Roo Code 等主流 Coding Agent，灵活接入你习惯的开发工具。
- **极速响应**：最高可达 100 Tokens/s 的生成速度，显著提升编码效率。
- **高频并发**：每 5 小时约 300–1200 次请求（视套餐而定），最高支持 30 路并发，满足高强度开发场景。

## 快速开始

根据你的情况选择对应的方式：

- **新用户**：前往 [kimi.com/code](https://kimi.com/code) 登录，选择 Coding Plan 套餐完成订阅。
- **已订阅用户**：进入控制台管理你的 API Key，即可开始使用。

## 获取 API Key

1. 登录 [Kimi 控制台](https://kimi.com/code)。
2. 进入 **API Keys** 页面。
3. 点击 **创建新的 API Key**。
4. 复制并妥善保存你的 API Key（创建后仅显示一次）。

<Callout type="warning">
请勿将 API Key 分享给他人或提交到公开代码仓库中。
</Callout>

## 一键登录

在 Kimi Code CLI 中，你可以使用 `/login` 命令快速完成授权，无需手动复制 API Key：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/login",
    },
  ]}
/>

系统会自动完成设备授权与账号绑定，整个过程只需几秒。

## 设备管理

- 每个账号可在多台设备上使用。
- **30 天未活跃**的设备授权会自动失效，届时需要重新执行 `/login` 完成授权。
- 你可以在控制台查看和管理已授权的设备。
