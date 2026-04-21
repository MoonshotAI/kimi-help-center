---
title: "对话限制与 API 限频"
slug: "conversation-limits"
order: 10
extract_headings: true
preview: true
preview_content: "Kimi Claw 对话 Token 限制与 API 限频的处理方法。"
---
<SeoMeta
  title="Kimi Claw 对话限制说明 - Kimi 帮助中心"
  description="了解 Kimi Claw 的对话轮数限制、消息长度限制和会话超时规则，帮助你合理规划对话节奏，获得最佳使用体验。"
/>

# 对话限制与 API 限频

## Token 超过最大限制怎么办？

当对话上下文过长，超过模型的 token 限制时，Kimi Claw 可能无法正常回复。

<Frames
  src="./images/kimi-claw/conversation-limits-01.png"
  alt="发送 /new 新建对话"
/>

**解决办法**：

- 发送 `/new` 命令新建对话，清空当前上下文。
- 如果 `/new` 之后仍然提示超过 context 限制，可能是模型误加载了过多的 Skill 内容。此时可以尝试：
  - 使用 `/skills` 查看当前加载的技能，卸载不需要的技能。
  - 使用 `/compact` 压缩当前上下文。
  - 使用 `/reset` 重置 Kimi Claw。

## 提示 API rate limit reached

出现此提示说明你已触发 API 限流，请稍后重试。

**查看额度与频次**：

1. 前往 [kimi.com/code](https://kimi.com/code)。
2. 进入 **控制台**。
3. 点击 **查看额度与频次**，了解当前的使用情况和限制。

如果经常遇到限流，建议合理安排任务频率，或升级会员计划以获取更高的调用额度。
