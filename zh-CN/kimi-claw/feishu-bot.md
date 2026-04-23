---
title: "配置飞书机器人"
slug: "feishu-bot"
order: 8
extract_headings: false
preview: true
preview_content: "将 Kimi Claw 接入飞书机器人的配置方法与常见问题。"
---
<SeoMeta
  title="如何将 Kimi Claw 接入飞书？配置教程 - Kimi 帮助中心"
  description="一步步教你将 Kimi Claw 接入飞书机器人。通过扫码快捷配置，即可在飞书群聊或私聊中使用 Kimi AI Agent 的全部能力。"
/>

# 配置飞书机器人

## 快捷配置

1. 点击https://www.kimi.com/bot 
2. 打开 Kimi Claw 的 **设置**
3. 进入 **聊天频道**。
4. 按照页面指引完成飞书扫码连接。

<Frames
  src="./images/kimi-claw/feishu-bot-01.gif"
  alt="飞书配置流程"
/>

## 手动配置飞书机器人

Kimi Claw 内置 Skill 会帮助你配置飞书机器人。你可以直接对它说“我想配置飞书机器人”，它会给你一份逐步完成的方案。你也可以按照以下步骤手动完成配置。

## 详细步骤

1. 前往 [飞书开发者平台](https://open.feishu.cn/)，点击 **创建企业自建应用**，设置 App 名称和描述。
2. 在应用中点击 **添加机器人**，创建机器人服务。
3. 进入 **权限设置** 页面，通过 **批量导入/导出权限** 添加所需权限。
4. 进入 **凭证与基础信息** 页，复制 **App ID** 和 **App Secret** 发送给 Kimi Claw，并告知这是飞书机器人的应用凭证。
5. Kimi Claw 配置完成后，重启使配置生效（可让 Kimi Claw 自行重启，或手动在设置内点击 **重启 Kimi Claw**）。
6. 重启完成后，在飞书开发者平台切换到 **事件与回调** 页面，选择 **长连接** 接收事件，点击保存，然后添加事件 `im.message.receive_v1`。
7. 切换到 **版本管理与发布**，发布应用。在飞书里搜索机器人名字即可开始对话。

## 诊断命令

如果飞书机器人配置遇到问题，可使用以下命令诊断：

| 命令 | 说明 |
|------|------|
| `/feishu start` | 确认飞书插件是否已安装并启动 |
| `/feishu doctor` | 检查飞书机器人配置是否正确 |
| `/feishu auth` | 批量授权飞书机器人权限 |

## 修复命令

如果需要进一步排查和修复，可在终端中使用以下命令：

| 命令 | 说明 |
|------|------|
| `npx doctor` | 诊断飞书插件运行状态 |
| `npx fix` | 自动修复常见配置问题 |
| `npx info` | 查看飞书插件详细信息 |

## 相关文档

- [飞书机器人无响应怎么办？](/kimi-claw/feishu-no-response)
- [升级注意事项（含飞书插件诊断命令详解）](/kimi-claw/upgrade-notice)
