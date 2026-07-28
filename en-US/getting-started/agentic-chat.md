---
title: "Getting started with Kimi"
slug: "agentic-chat"
order: 2
extract_headings: false
preview: false
---

<SeoMeta
  title="Getting started with Kimi - Kimi Help Center"
  description="Learn about Kimi's three models (K2.6, K3, K3 Swarm), built-in tools, and multimodal capabilities to quickly get started with chat and task execution."
/>

# Getting started with Kimi

You can type questions in the chat box, upload files, or switch between models depending on your needs.
Open [kimi.com](https://www.kimi.com) and try sending a message — say hello to Kimi:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Hi, Kimi!",
    },
  ]}
/>

## Choose a model

Kimi offers multiple models. Click the model switch button above the input box to switch.

| Model | Thinking strength | Best for |
|-------|-------------------|----------|
| **K2.6** | Standard / High | Fast conversation and Q&A with quicker responses |
| **K3** | Low / High / Max | Chat and Agent tasks; the most capable overall |
| **K3 Swarm** | Low / High / Max | Large-scale search and batch processing, completed in one go |

<Callout type="tip">
K2.6 does not consume credits in Chat (when used as a K2.6 Agent inside Kimi Work, it still consumes membership credits); K3 and K3 Swarm are billed by credits. See the [membership benefits](https://www.kimi.com/help/membership/membership-overview) for details.
</Callout>

### About Kimi K3

Kimi K3 is currently Kimi's most powerful model, with 2.8 trillion parameters, built on Kimi Delta Attention (KDA) and Attention Residuals, featuring **native vision** and a **1-million-token context window**. As the world's first open 3T-class model, K3 is designed for frontier intelligence across long-horizon coding, knowledge work, and reasoning, reaching leading performance in coding, long-horizon execution, and a wide range of general intelligence tasks.

### Built-in tools

Available out of the box, no configuration needed:

| Tool | Description |
|------|------------|
| **Web Search** | Real-time web search for the latest news and information |
| **Fetch Tool** | Direct access to specific URLs (web pages, documents, images, and other online resources) |
| **Image Search** | Text-to-image and image-to-image search for quick visual content discovery |
| **IPython** | Execute Python code for data analysis and visualization |
| **Memory** | Smart memory that records your personal preferences and habits |

## Visual & multimodal capabilities
Kimi K3 supports full-scenario understanding of images, videos, and office documents (PDF/Word/Excel), using a **native multimodal architecture** (not bolt-on OCR). It can directly parse document content and perform intermediate-to-advanced office tasks (such as writing Excel formulas or generating PPT outlines/VBA code). Combined with native vision and a 1-million-token context window, it can handle longer and more complex multimodal materials.
### Multimodal input support
- **Images**: PNG, JPEG, WebP, GIF, etc. (via URL, Base64, or local file upload)
- **Video**: MP4, etc. (via video_url or image frame sequences + fps parameter)
- **Documents**: PDF, Word, Excel, TXT, Markdown, etc.
- **Online resources**: URLs, article links
- **Image search**: Upload an image to search for related or similar images
- **Video understanding**: Supports video understanding — it can analyze screen recordings and replicate interaction logic
- **Visual coding**: Upload screenshots or screen recordings to generate frontend code (HTML/Vue/React, etc.); can automatically reproduce web pages from design mockups

### Output formats
- Plain text / mixed text-and-image: Standard conversational replies
- Markdown: Rich text with headings, lists, tables, and links
- Code blocks: HTML/Vue/React/Python/JSON/Mermaid, etc. (with language identifiers)
- JSON structured data: Forced JSON mode output
- Mermaid diagrams: Flowcharts, sequence diagrams, mind maps, etc.
- LaTeX math formulas: Inline and block-level mathematical expressions
- Dual-mode output (Thinking): Returns both `reasoning_content` (thinking process) and `content` (final answer)
- Tool call format: Function Calling standard format (for developers)

### Important notes

1. **File output**: K3 can produce editable documents end-to-end (such as `.pptx`, `.docx`, `.xlsx`, `.pdf`) and other complex deliverables; K2.6 focuses on fast Q&A and only outputs text (such as PPT outlines, Word body text, or code).

<Callout type="tip">
Tip: To generate images, audio, or video, click "+" → Plugin, select the corresponding feature, and use it with **K3**. To create complex editable documents or run multi-step tasks, we recommend choosing **K3** or **K3 Swarm** for the full experience.
</Callout>

## Sessions vs. conversation turns
When you click "New Chat", think of it as starting a long conversation with Kimi.
| Concept | Analogy | Technical Definition |
|---------|---------|---------------------|
| **Session** | An entire meeting (from start to finish) | A complete chat process with a clear beginning and end |
| **Turn** | One exchange (you speak, Kimi replies) | Your input and Kimi's response form one round-trip |

### Key differences
**Session**
- **Continuous memory**: Kimi remembers all context within the current chat
- **Cross-turn context**: Each reply references prior conversation content as context for the next turn
- **Defined boundaries**: Clicking "New Chat" = fresh start; previous context is cleared
**Turn**
- **Cumulative count**: Turn 1, Turn 2, … incrementally added
- **Limited memory**: Too many turns (e.g., 50+) may cause Kimi to "forget" earlier content, especially for long-form writing or tasks with strict requirements
- **Context length constraint**: Limited by token count; when turns accumulate, the earliest content may be compressed

<Callout type="tip">
**Edge case**: If a single question-and-answer concludes the conversation, then 1 turn = 1 session.
</Callout>

## Why this distinction matters
Within a single session, each new question or instruction you send is answered with reference to all prior turns. As turns accumulate and content grows longer, response quality may gradually decline.

### Common scenarios
**Scenario 1: Switching topics**
- Wrong: Asking "help me calculate my taxes" in a session where you've been writing a 30,000-word novel
- Right: Start a new session for the tax question — avoid Kimi confusing novel characters with tax concepts
**Scenario 2: Long document processing**
- After dozens of turns, Kimi may "forget" rules or file summaries established at the start
- Solution: Proactively summarize mid-task ("Summarize our plan so far"), or start a new session
**Scenario 3: Understanding product limits**
- Context length limits are measured in tokens, but in everyday terms, think of it as "turns"
- If you see a "Start a new chat" prompt, it means the current session has too many turns
## Best practices

<Callout type="tip">
**Start a new session for each task**: Independent tasks — essay writing, research, debugging — should each get their own session to avoid context interference.
</Callout>

<Callout type="tip">
**Summarize periodically in long sessions**: After 20+ turns, proactively ask Kimi to summarize key information to prevent data loss.
</Callout>

<Callout type="tip">
**Clean up sensitive information promptly**: Chat history is retained; delete the entire session after handling private content.
</Callout>
