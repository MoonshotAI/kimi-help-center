---
title: "Memory tips"
slug: "memory-tips"
order: 7
extract_headings: false
preview: false
---

<SeoMeta
  title="Memory tips - Kimi Help Center"
  description="I'm name/nickname, currently based in city. Background in profession/role, with expertise in area 1 and area 2."
/>

## 1. Help Kimi understand your world

### Identity anchoring

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "I'm [name/nickname], currently based in [city]. Background in [profession/role], with expertise in [area 1] and [area 2].\nCurrently focused on: advancing [Project A] and [Project B].\nPlease default to English for all future responses unless I explicitly write in another language.",
    },
  ]}
/>

## 2. Set personalization preferences

### Standardize output format

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "My content consumption preferences:\n- Prefer structured presentation: use heading hierarchy, bullet points, and bold key conclusions\n- Avoid walls of text: for complex topics, lead with a \"TL;DR\" summary, then expand into details\n- Terminology handling: explain jargon in plain language on first use, then use it freely afterward\n- Citation format: cite sources for factual data using [^N^] notation",
    },
  ]}
/>

### Memory self-maintenance instructions (advanced)

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "At the end of each conversation:\n- If we discussed new important facts (e.g., schedule changes, project updates, preference adjustments), proactively ask whether to update memory\n- If new information conflicts with existing memory, flag the discrepancy and confirm which takes priority\n- For sensitive information (specific addresses, ID numbers, trade secrets), proactively ask whether to store it in memory",
    },
  ]}
/>

## 3. Positive-effect prompts

### Source whitelist protocol

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "[Fact-Check Protocol]\nWhen I ask questions in the following domains, strictly follow this source priority:\n1. Medical/Health: Prefer PubMed, WHO, UpToDate; never cite health blogs or self-media\n2. Finance/Investment: Use only SEC filings, central bank data, and public company annual reports; no forum speculation\n3. Legal/Compliance: Refer to official regulatory databases; for local policies, note \"consult a local attorney\"\n4. Tech/Programming: Prefer official documentation; label GitHub Issues as community experience, not authoritative\n5. For information from Wikipedia, Reddit, Quora, or other UGC platforms, always tag as \"[Unverified]\"",
    },
  ]}
/>

### Hallucination trigger checks (process-level)

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "[High-Risk Topic Checklist]\nWhen the following keywords are detected, automatically trigger a \"double-check\" process:\n1. Specific numbers (prices, dates, statistics) → must state the data source and year\n2. Time-sensitive language (\"latest,\" \"just,\" \"recently\") → must verify whether it's within the knowledge cutoff\n3. Professional advice (medical, legal, investment) → must append disclaimer: \"The above is for reference only and does not constitute professional advice\"\n4. Specific quotes from individuals → must label as direct quote or paraphrase; never fabricate quotes\n\nExecution: First state \"I need to verify the following information,\" then provide the answer.",
    },
  ]}
/>

## Memory limits
Memory Space currently has the following limits:
- Up to 50 memory entries can be stored.
- Each memory entry is limited to 500 characters.
- Memories created before April 2026 may exceed this limit; those existing memories are still retained.
- To edit a legacy memory that exceeds 500 characters, you must first trim it to 500 characters or fewer.
- If you try to save content longer than 500 characters, the model receives a "content too long" signal and the user-facing UI shows "Memory update failed."
- If the user is using a non-Chinese interface, you may suggest storing memory in Chinese to fit more information under the same character limit.
- Each memory entry has an internal ID, but users cannot view these IDs. Referencing memory IDs in conversation does not help users locate a specific memory.

### Useful prompt references

| Prompt | Purpose |
|:---|:---|
| Treat me as an expert in all subject matter | Sets the core communication tone |
| Be opinionated rather than neutral when appropriate | Encourages judgment, not just summaries |
| Always provide the pros and cons of something if you can. Be critical. | Ensures structured, in-depth analysis |
| Use detailed examples, facts, and figures | Keeps information substantive and specific |
| Suggest solutions that I didn't think about — be proactive and anticipate my needs | Promotes AI initiative beyond passive Q&A |
| Use maximum tokens; provide a maximally detailed answer with multiple levels of depth | Delivers thorough, multi-layered responses |
| After a response, provide 5 follow-up questions. Format as Q1, Q2, Q3 in a bulleted list | Extends the discussion with guided exploration |
| At the start of a response, create a summary table if helpful | Improves readability and quick information access |
| Recommend only the highest-quality, meticulously designed products — I only want the best | Sets the bar for product recommendations |
| Value good arguments over authorities, the source is irrelevant | Prioritizes reasoning over name-dropping |
| Consider new technologies and contrarian ideas, not just the conventional wisdom | Encourages innovative perspectives |
| You may use high levels of speculation or prediction, just flag it for me | Allows speculative content with clear labeling |
| Add links throughout the answer for jargon and concepts that start new chats | Enhances learning and knowledge expansion |
| Link directly to products, not company pages | Makes recommendations more actionable |
| Discuss safety only when it's crucial and non-obvious | Reduces unnecessary disclaimers |
| No moral lectures | Keeps exchanges rational and focused |
| If your content policy is an issue, provide the closest acceptable response and explain the content policy issue | Avoids hard blocks; prioritizes user needs |
| No need to disclose you're an AI | Reduces AI presence disruption |
| No need to mention your knowledge cutoff | Avoids excessive disclaimers |

## 4. For fun
Try asking Kimi:
- "Based on what you know about me, what's my biggest life challenge right now?"
- "Based on what you know about me, summarize my past year and give me advice for the new year"
