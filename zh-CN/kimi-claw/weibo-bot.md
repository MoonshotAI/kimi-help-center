---
title: "配置微博龙虾助手"
slug: "weibo-bot"
order: 7
extract_headings: false
preview: true
preview_content: "将 Kimi Claw 接入微博龙虾助手的安装与配置说明。"
---
<SeoMeta
  title="如何将 Kimi Claw 接入微博？配置教程 - Kimi 帮助中心"
  description="了解 Kimi Claw 微博机器人的配置方法，在微博平台中接入 Kimi AI 能力，实现智能互动与内容创作。"
  pageUrl="https://www.kimi.com/help/kimi-claw/weibo-bot"
/>
# 配置微博龙虾助手

微博支持通过微博龙虾助手与 Kimi Claw 对话。微博官方配置说明请参考：[微博龙虾助手配置指南](https://weibo.com/6808810981/QvjZpiZVn)。

## 第一步：安装微博龙虾助手插件

- **2025 年 3 月 9 日之后**新创建的 Kimi Claw 已内置插件，可跳过此步。
- 之前创建的 Kimi Claw 需要手动安装，在对话中发送以下内容：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "- 先下载微博龙虾插件（git clone https://gitee.com/wecode-ai/openclaw-weibo.git）\n- 后进入对应目录并安装插件（openclaw plugins install .）\n- 最后重启 openclaw gateway",
    },
  ]}
/>

## 第二步：配置微博龙虾

1. 打开微博，私信 **@微博龙虾助手**，发送 **"连接龙虾"**。
2. 龙虾助手会回复你一组 **appKey** 和 **appSecret**。
3. 将收到的 appKey 和 appSecret 发送给 Kimi Claw。
4. Kimi Claw 完成配置后，前往 **设置** 并点击 **重启 Kimi Claw**。
5. 重启后，微博龙虾助手内可以看到"你的龙虾已上线"提示，即可在微博内与龙虾对话。

<Frames
  src="./images/kimi-claw/weibo-bot-01.png"
  alt="连接龙虾"
/>

<Frames
  src="./images/kimi-claw/weibo-bot-02.png"
  alt="连接成功"
/>

## 限制说明

- 目前微博龙虾助手仅在国内版微博支持，海外版本暂无法正常连接。
