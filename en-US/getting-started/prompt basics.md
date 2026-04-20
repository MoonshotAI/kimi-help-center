---
title: "Prompt basics"
slug: "what-is-prompt"
order: 3
extract_headings: false
preview: false
---

<SeoMeta
  title="Prompt basics - Kimi Help Center"
  description="A prompt is the text instruction you send to Kimi — it can be a question, a description, a set of requirements, or even a complete task brief. Kimi uses your..."
  pageUrl="https://www.kimi.com/help/getting-started/what-is-prompt"
/>

# Prompt basics

<Callout type="info">
A prompt is the text instruction you send to Kimi — it can be a question, a description, a set of requirements, or even a complete task brief. Kimi uses your prompt to understand your intent, organize a response, and execute tasks.

In short: **how you ask determines how Kimi answers.** A clear, specific prompt almost always leads to a more accurate and valuable response.
</Callout>

## Four core elements of a good prompt

### 1. Define role and context

Telling Kimi who you are and what situation you're in helps it match the right depth and tone.

| Vague Prompt | Better Prompt |
|-------------|--------------|
| Write an article about AI | I'm a tech media editor. I need a 2,000-word AI explainer article for a general audience, written in an accessible, engaging style |
| Help me analyze data | I'm a market analyst. Please analyze the conversion rates by channel in this Excel file, focusing on month-over-month changes |

### 2. Describe the task specifically

The more specific your description is, the fewer revision cycles you'll need. A good task description typically includes:

- **What to do**: A clear action (analyze, summarize, translate, generate, compare…)
- **Output format**: Table, list, paragraph, code, Markdown…
- **Scope and constraints**: Word count, number of items, time range, geographic scope…
- **Quality requirements**: Academic tone, conversational, concise, detailed…

<ComparisonBlock
  wrong={"Summarize this article"}
  correct={"Summarize this article in 3 bullet points, each no more than 50 words, in English"}
/>

### 3. Provide examples or references

When you have specific formatting expectations, giving Kimi an example (few-shot) is highly effective:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Please organize the meeting notes in this format:\n\nMeeting Topic: xxx\nAttendees: xxx\nKey Decisions:\nxxx\nxxxAction Items:\n[ ] xxx (Owner: xxx, Deadline: xxx)",
    },
  ]}
/>

### 4. Break complex tasks into steps
For complex tasks, split the work into smaller steps and guide Kimi through them:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "I need a competitive analysis report. Please follow these steps:\nList the top 3 domestic competitors and their core features\nCompare their pricing strategies\nAnalyze each product's strengths and weaknesses\nProvide differentiation recommendations for our product",
    },
  ]}
/>

## Practical tips
### Use follow-ups and iteration
Not satisfied with the first response? Just follow up — no need to restate all the context:
- "Please elaborate on point 2"
- "Make the tone more formal"
- "Add data sources"
- "Re-analyze from a different angle"
### Leverage files and links
Kimi supports uploading PDFs, Word docs, Excel files, images, and more. You can also paste URLs directly. Combining files with your prompt dramatically boosts efficiency:
| Task | Prompt Example |
|------|---------------|
| Summarize PDF | "Summarize the key points of this PDF" |
| Analyze data | "Analyze sales trends based on this Excel data" |
| Extract from URL | "Read this article at the link and extract the key takeaways" |

### Specify the output format
Tell Kimi exactly what format you want:
| Need | Prompt Example |
|------|---------------|
| Comparison table | "Compare the pros and cons of A and B in a table" |
| Code output | "Implement this in Python with comments" |
| Structured list | "Organize as a numbered list, each item under 20 words" |
| Markdown | "Output in Markdown format with heading hierarchy" |

### Use memory for persistent preferences
If you have recurring preferences and requirements, use Kimi's **Memory** feature to remember them long-term:
- "Remember that I'm a frontend engineer who prefers the React stack"
- "Always reply in English using Markdown format"
- "Include code examples when answering technical questions"

<Callout type="tip">
This way you don't have to repeat yourself — Kimi will automatically apply these preferences in future conversations.
</Callout>

## Common mistakes
| Mistake | Better Approach |
|---------|----------------|
| Cramming multiple unrelated tasks into one message | Start a new session for each independent task to keep context clean |
| Overly vague prompts (e.g., "write something for me") | Specify what to write, for whom, in what style, and how long |
| Expecting perfect output on the first try | Generate a draft first, then iterate through follow-ups |
| Not fact-checking AI output | Always verify dates, data, and factual claims |

## Quick-start templates
Here are a few ready-to-use prompt templates — copy, customize, and go:
**Writing**

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Write a [article type] about [topic] for [target audience], approximately [xxx] words.\nRequirements: [style/format/focus areas]",
    },
  ]}
/>

**Analysis**

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Analyze [subject], focusing on [key dimensions].\nOutput format: [table/chart/report]\nInclude conclusions and recommendations.",
    },
  ]}
/>

**Translation**

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Translate the following into [target language], maintaining a [academic/conversational/business] tone.\nInclude the original term in parentheses for domain-specific terminology.",
    },
  ]}
/>

<Callout type="info">
Master these core concepts and techniques, and you'll collaborate with Kimi far more effectively — turning AI into a true productivity tool.
</Callout>
