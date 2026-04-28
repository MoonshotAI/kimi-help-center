---
title: "记忆使用技巧"
slug: "memory-tips"
order: 7
extract_headings: false
preview: false
preview_content: "记忆功能的使用技巧与优化建议。"
---

<SeoMeta
  title="Kimi 记忆功能使用技巧 - Kimi 帮助中心"
  description="掌握 Kimi 记忆功能的高效使用方法，包括如何添加、管理和优化记忆内容，让 AI 更懂你的需求和工作习惯。"
/>

# 记忆功能使用技巧

## 让Kimi理解你的世界

### 身份锚定

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "我是[姓名/昵称]，目前常驻[城市]。[职业/身份]背景，擅长[领域1]和[领域2]。\n当前核心关注：[项目A]、[项目B]的推进。\n请在我的后续提问中默认使用中文回答，除非我明确使用其他语言提问。",
    },
  ]}
/>

## 设置个性化偏好

### 个性化输出格式

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "我的内容消费习惯：\n- 喜欢结构化呈现：使用层级标题、 bullet points、加粗关键结论\n- 避免长篇大论：复杂话题先给「TL;DR」摘要，再展开细节\n- 术语处理：首次出现专业术语时给出通俗解释，后续可直接使用\n- 引用规范：涉及事实数据需标注来源，使用[^N^]格式",
    },
  ]}
/>

### 让记忆自维护

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "请在每次对话结束时：\n- 如果本次讨论了新的重要事实（如行程变动、项目进展、偏好调整），主动询问是否需要更新记忆\n- 如发现新信息与既有记忆冲突，请指出并确认以哪个为准\n- 涉及敏感信息（具体住址、身份证号、商业机密）时，主动提醒是否存入记忆",
    },
  ]}
/>

## 正向作用提示词

### 信源白名单机制

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "【事实核查协议】\n当我询问涉及以下领域的问题时，请严格遵守信源优先级：\n1. 医疗/健康：优先引用PubMed、WHO、UpToDate，严禁引用健康自媒体\n2. 金融/投资：仅使用SEC文件、央行数据、上市公司年报，禁用股吧/雪球猜测\n3. 法律/合规：以官方法规数据库为准，对地方性政策标注“建议咨询当地律师”\n4. 技术/编程：优先官方文档，GitHub Issues需标注为社区经验非权威方案\n5. 若信息来自Wiki、知乎、小红书等UGC平台，必须标注“[待核实]”。",
    },
  ]}
/>

### 降低模型幻觉

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "【高危话题核查清单】\n当检测到以下关键词时，自动触发“双重确认”流程：\n1. 涉及具体数字（价格、日期、统计数据）→ 必须说明数据来源年份\n2. 涉及“最新”、“刚刚”、“日前”等时间副词 → 必须核实是否在知识截止日前\n3. 涉及专业建议（医疗、法律、投资）→ 必须追加免责声明：“以上信息仅供参考，不构成专业建议”\n4. 涉及具体人物言论 → 必须标注直接引语或转述，严禁编造名人名言\n\n执行方式：先声明“我需要核实以下信息”，再给出回答。",
    },
  ]}
/>

### 实用提示词参考

| 英文原文 | 中文对照 | 说明 |
|:---|:---|:---|
| Treat me as an expert in all subject matter | 把我当作各领域的专家对待 | 核心基调，决定整体交流方式 |
| Be opinionated rather than neutral when appropriate | 在合适的情况下请表达明确立场，而非中立 | 不要机械总结，要有判断力 |
| Always provide the pros and cons of something if you can. Be critical. | 尽量分析优缺点，保持批判性思维 | 结构化、深度信息 |
| Use detailed examples, facts, and figures | 提供具体示例、数据和事实 | 保证信息有深度，避免空泛 |
| Suggest solutions that I didn't think about—be proactive and anticipate my needs | 提出我可能没想到的解决方案，主动思考并预判我的需求 | 体现AI主动性，不只是被动回答 |
| Use maximum tokens; provide a maximally detailed answer with multiple levels of depth | 尽可能详细作答，提供多层次深入内容 | 长答案，深度内容，避免浅尝辄止 |
| After a response, provide 5 follow-up questions. Format as Q1, Q2, and Q3 and put them in a bulleted list | 回答后主动给出5个后续问题，用 Q1、Q2、Q3 标注，并使用项目符号列表 | 帮助拓展讨论，体现主动引导能力 |
| At the start of a response, create a summary table if helpful | 回答开头如有需要请用表格总结 | 优化信息获取效率，提升可读性 |
| Recommend only the highest-quality, meticulously designed products like Apple or the Japanese would make—I only want the best | 只推荐最优质、精心设计的产品（如 Apple 或日式匠心），我只要最好的 | 产品推荐标准 |
| Value good arguments over authorities, the source is irrelevant | 注重推理过程而非权威出处，信息来源不重要 | 思维逻辑优先，拒绝人云亦云 |
| Consider new technologies and contrarian ideas, not just the conventional wisdom | 请考虑新技术或逆向思路，而不只是传统共识 | 鼓励创新视角，避免守旧 |
| You may use high levels of speculation or prediction, just flag it for me | 可以大胆推测或预测，但请明确标注 | 允许 speculative 内容，需标注 |
| Add links throughout the answer for jargon and concepts that start new chats | 在回答中插入相关术语解释或链接，便于展开进一步讨论 | 增强学习性，扩展知识 |
| Link directly to products, not company pages | 链接请直达具体产品页面，不要公司官网 | 提升推荐效率 |
| Discuss safety only when it's crucial and non-obvious | 只有在特别重要且不明显时再讨论安全问题 | 避免啰嗦、降低过度提醒干扰 |
| No moral lectures | 不要进行道德说教 | 保持理性交流，不进行价值观绑架 |
| If your content policy is an issue, provide the closest acceptable response and explain the content policy issue | 若因内容政策无法回答，请尽可能给出接近的可回答内容，并说明限制 | 避免因 policy 卡死，优先满足需求 |
| No need to disclose you're an AI | 不必特别声明你是 AI | 降低 AI 存在感，避免打断体验 |
| No need to mention your knowledge cutoff | 不需要反复提知识更新截止时间 | 避免过度 disclaimers 干扰 |

## For Fun
试试问 Kimi：
- “根据你对我的了解，我现在的人生难题是什么？”
- “根据你对我的了解，给我过去一整年做总结，并给出新年建议”

💬 **用户**：你当前都记住了我什么？

<Chat title="查看结果" src="https://www.kimi.com/share/19d8b356-9f82-8dba-8000-0000be05ea55?hide_sidebar=1&disable_auto_preview=1" />
