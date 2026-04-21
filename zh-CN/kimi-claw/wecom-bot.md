---
title: "配置企业微信机器人"
slug: "wecom-bot"
order: 6
extract_headings: false
preview: true
preview_content: "将 Kimi Claw 接入企业微信机器人的配置步骤。"
---
<SeoMeta
  title="如何将 Kimi Claw 接入企业微信？配置教程 - Kimi 帮助中心"
  description="了解 Kimi Claw 企业微信机器人的配置方法，将 AI Agent 集成到企业微信工作流中，提升团队协作效率。"
/>
# 配置企业微信机器人

Kimi Claw 支持部署到企业微信。
目前，企业微信内企业管理员、成员均可以创建智能机器人，并支持单聊、内部群聊内主动向用户推送消息。你可以根据下面的步骤完成基于 Kimi Claw 的企业微信机器人配置，或参考官方文档[《以长连接方式接入 OpenClaw》](https://open.work.weixin.qq.com/help2/pc/cat?doc_id=21658)。

<Callout type="info">
请安装[企业微信](https://work.weixin.qq.com/)**最新版本电脑客户端**，手机版暂时无法创建智能机器人。
</Callout>

## 第一步：创建企业微信机器人

1. 在电脑客户端进入「工作台」，点击「智能机器人」→「创建机器人」→「手动创建」
2. 滑到页面底部，选择 **API 模式** 创建

<Frames
  src="./images/kimi-claw/wecom-bot-01.png"
  alt="工作台入口"
/>

<Frames
  src="./images/kimi-claw/wecom-bot-02.png"
  alt="创建机器人"
/>

<Frames
  src="./images/kimi-claw/wecom-bot-03.png"
  alt="API模式"
/>

3. 选择以「长连接」方式创建，并获取 **Bot ID** 和 **Secret**
4. 复制 Bot ID 和 Secret 后，保存智能机器人

<Frames
  src="./images/kimi-claw/wecom-bot-04.png"
  alt="长连接方式"
/>

## 第二步：安装企业微信插件

2025 年 3 月 9 日之后新创建的 Kimi Claw 已默认安装企业微信插件，可直接跳到第三步。之前创建的 Kimi Claw 需要先安装插件：

1. 在对话中向 Kimi Claw 发送：

> "帮我运行 `openclaw plugins install @wecom/wecom-openclaw-plugin` 安装企业微信插件"

2. 运行成功后，点击「设置」→「重启 Kimi Claw」，完成插件安装

## 第三步：在 Kimi Claw 内配置机器人

打开 Kimi Claw，将机器人的 Bot ID 和 Secret 告诉 Kimi Claw，让它帮你完成配置。命令行配置方式可参考官方文档[《以长连接方式接入 OpenClaw》](https://open.work.weixin.qq.com/help2/pc/cat?doc_id=21658)。

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "botId: xxxxxxxxxx\nsecret: xxxxxxxxxx\n我的企业微信机器人信息，帮我配置一下",
    },
  ]}
/>

<Frames
  src="./images/kimi-claw/wecom-bot-07.png"
  alt="配置机器人"
/>

## 第四步：完成配对

1. 前往企业微信，点开机器人，和机器人对话
2. 第一次它会发给你一个**配对信息**，将这段内容发给 Kimi Claw
3. Kimi Claw 会帮你完成配对，完成后就可以在企业微信私信/群组内正常对话了

<Frames
  src="./images/kimi-claw/wecom-bot-08.png"
  alt="配对信息"
/>

<Frames
  src="./images/kimi-claw/wecom-bot-09.png"
  alt="发送配对"
/>

<Frames
  src="./images/kimi-claw/wecom-bot-11.png"
  alt="群聊对话示例"
/>

## 限制说明

- 目前企业微信的「微信插件」暂不支持智能机器人，因此在微信内暂时无法查看智能机器人信息
- Kimi Claw 暂不支持以「自建小程序」形态完成智能回复设置，如果未来更新会在文档同步
