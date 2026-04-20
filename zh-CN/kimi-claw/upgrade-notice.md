---
title: "升级注意事项"
slug: "upgrade-notice"
order: 17
extract_headings: true
preview: true
preview_content: "Kimi Claw 升级注意事项：不要手动升级 OpenClaw 和飞书插件。"
---
<SeoMeta
  title="Kimi Claw 升级注意事项 - Kimi 帮助中心"
  description="重要提醒：请勿手动升级 OpenClaw 版本或飞书插件，可能导致插件失效。了解正确的升级方式和误升级后的恢复方法。"
  pageUrl="https://www.kimi.com/help/kimi-claw/upgrade-notice"
/>

# 升级注意事项

## 不要手动升级 OpenClaw 版本

OpenClaw 目前不支持更新到 3.22 日期之后的版本。如果手动升级或开启了自动更新，会导致 Kimi 插件失效，其他已安装的插件（微信、飞书、企微、微博等）也可能不可用。

<Callout type="warning">
**请勿手动升级或开启自动更新**，等待官方升级推送即可。
</Callout>

**误升级后的恢复方法：**

如果已经误升级导致插件失效，可以在设置中选择「恢复初始设置」恢复到可用版本。

- 工作空间和记忆会保留
- 需要重新配置聊天机器人（微信、飞书、企微等）

官方会在适配完成后统一推送升级，届时会在 Kimi Claw 页面内提示。

## 不要手动升级飞书插件

飞书插件升级时会同时升级 OpenClaw 版本，这会导致与当前环境不兼容。

<Callout type="warning">
**不建议手动升级飞书插件。** 目前新安装的 Kimi Claw 已经安装了适配的最新版本插件。
</Callout>

升级飞书插件后，最新版本的插件可能与当前 OpenClaw 版本不兼容，导致飞书机器人无法正常使用。

## 常见飞书诊断命令与问题修复

### 方法一：通过对话命令诊断

在与 AI 的对话中发送以下命令：

| 命令 | 说明 |
|------|------|
| `/feishu start` | 确认飞书插件是否安装成功 |
| `/feishu doctor` | 检查配置是否正常 |
| `/feishu auth` | 批量完成用户授权 |

<Callout type="tip">
插件中内置了常见问题的解决方案，遇到问题可以先问问小龙虾。
</Callout>

### 方法二：通过 npx 命令诊断与修复

如果对话命令无法解决问题，可在终端中运行以下诊断命令：

**查看问题：**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "npx https://sf3-cn.feishucdn.com/obj/open-platform-opendoc/8ab6e7a04c17db1becfcbda8ca35f091_1rCCFRWlRV.tgz doctor",
    },
  ]}
/>

<Frames
  src="./images/kimi-claw/upgrade-notice-01.png"
  alt="飞书诊断结果"
/>

**尝试自动修复：**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "npx https://sf3-cn.feishucdn.com/obj/open-platform-opendoc/8ab6e7a04c17db1becfcbda8ca35f091_1rCCFRWlRV.tgz doctor --fix",
    },
  ]}
/>

<Frames
  src="./images/kimi-claw/upgrade-notice-02.png"
  alt="飞书自动修复"
/>

### 方法三：反馈问题

如果仍然无法修复，可在反馈群里反馈信息。运行以下命令查看版本信息，反馈问题时请带上以辅助排查：

**查看版本信息：**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "npx https://sf3-cn.feishucdn.com/obj/open-platform-opendoc/8ab6e7a04c17db1becfcbda8ca35f091_1rCCFRWlRV.tgz info",
    },
  ]}
/>

<Frames
  src="./images/kimi-claw/upgrade-notice-03.png"
  alt="版本信息"
/>

**查看详细配置信息：**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "npx https://sf3-cn.feishucdn.com/obj/open-platform-opendoc/8ab6e7a04c17db1becfcbda8ca35f091_1rCCFRWlRV.tgz info --all",
    },
  ]}
/>

反馈群可以飞书扫码加入

<Frames
  src="./images/kimi-claw/upgrade-notice-04.png"
  alt="KimiClaw飞书群"
/>
