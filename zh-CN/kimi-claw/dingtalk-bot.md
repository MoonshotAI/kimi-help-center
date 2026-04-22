---
title: "配置钉钉机器人"
slug: "dingtalk-bot"
order: 11
extract_headings: false
preview: true
preview_content: "将 Kimi Claw 接入钉钉机器人的完整配置流程。"
---
<SeoMeta
  title="如何将 Kimi Claw 接入钉钉？配置教程 - Kimi 帮助中心"
  description="了解 Kimi Claw 钉钉机器人的配置步骤与使用方法，在钉钉群组中直接使用 Kimi AI Agent 完成各类任务。"
/>

# 配置钉钉机器人

Kimi Claw 支持部署到钉钉。按照以下 5 个步骤完成配置。

## 创建钉钉应用

1. 前往 [钉钉开放平台](https://open-dev.dingtalk.com/)。
2. 点击创建 **企业内部应用**。
3. 设置应用名称和描述。
4. 创建完成后，在应用信息页获取 **ClientID** 和 **ClientSecret**，记录下来。

## 创建机器人

1. 在应用管理页面，点击 **添加能力**，选择 **机器人**。
2. 配置机器人的基本信息（名称、头像等）。
3. 消息接收模式选择 **Stream 模式**（长连接方式）。

## 发布应用

1. 在权限管理中添加以下权限：
   - `Card.Streaming.Write`
   - `Card.Instance.Write`
   - `qyapi_robot_sendmsg`
2. 点击 **创建版本** 并发布应用。
3. 等待管理员审批通过。

## 在 Kimi Claw 中配置

将钉钉应用的凭证发送给 Kimi Claw：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "ClientID: xxxxxxxxxx\nClientSecret: xxxxxxxxxx\n这是我的钉钉机器人凭证，帮我配置一下",
    },
  ]}
/>

Kimi Claw 会自动完成配置，配置完成后需要重启生效。

## 开始使用

在钉钉群聊中 **@机器人** 即可开始对话。也可以在单聊中直接与机器人交流。
