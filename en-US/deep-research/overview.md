---
title: "Deep Research"
slug: "deep-research-overview"
order: 1
extract_headings: false
preview: true
preview_content: "Discover how Deep Research autonomously plans, searches, and delivers 10,000+ word research reports."
---

# Deep Research

<SeoMeta
  title="Deep Research Overview - Kimi Help Center"
  description="Discover how Deep Research autonomously plans, searches, and delivers 10,000+ word research reports."
/>

<Callout type="info">
**Deep Research** is Kimi's first Agent product, powered by the Kimi-Researcher model. It doesn't just answer questions — it works like a real researcher, autonomously completing the entire workflow from task planning to report delivery.
</Callout>

## How Kimi-Researcher works?
For every question, Kimi-Researcher independently completes the full research pipeline:
| Step | Description |
| --- | --- |
| **Clarification** | Proactively asks follow-up questions to build a clearer problem space |
| **Deep reasoning** | Averages 23 reasoning steps per task, organizing and resolving requirements |
| **Active search** | Plans ~74 keywords, discovers 206 URLs, filters to top 3.2% highest-quality content |
| **Iterative reasoning** | Evaluates results to determine if additional searches are needed |
| **Tool invocation** | Calls browsers, code execution, and other tools to process data |
| **Report generation** | Synthesizes information into a structured long-form report with citations |

<Callout type="info">
Deep Research operates asynchronously, taking 10–25 minutes for step-by-step reasoning, retrieval, and writing.
</Callout>

## Deliverables
Each research task produces two deliverables:
### 1. Text research report
- Average length: 10,000+ words
- ~26 high-quality, traceable sources
- Citations embedded inline — click to jump to source

<Frames
  src="./images/overview/dr-gif.gif"
  alt="DR gif"
/>

### 2. Visual report
- Interactive, shareable dynamic HTML report
- Structured layout and mind maps
- Public sharing link available

<Frames
  src="./images/overview/drreport.png"
  alt="DRreport"
/>

## Use cases

<Callout type="tip">
**Best for**: Investment analysis, industry research, academic topics, strategic planning, regulatory review, knowledge synthesis
</Callout>

| Category | Examples |
| --- | --- |
| **Professional research** | Investment analysis, industry research, academic topics, strategic planning |
| **Information synthesis** | Regulatory review, complex document retrieval, multi-source consolidation |
| **Knowledge & education** | Teaching materials, systematic surveys, deep topic exploration |
| **Everyday exploration** | Learn about topics of interest |

<Callout type="warning">
**Not suitable for**: Creative writing (fiction, screenplays), fortune-telling, resume writing, fixed-format templates, editable slides
</Callout>

## How to use Deep Research？
**Entry points**:
- **Web**: [kimi.com/deep-research](https://www.kimi.com/deep-research)
- **Mobile**: Kimi app → Taskbar → Deep Research Agent mode
**Steps**:
1. Enter your research question and send
2. Respond to clarification questions to confirm direction (or click "Include everything" to skip)
3. Monitor search keywords, reasoning process, and visited URLs in real time
4. Receive two deliverables when complete:
   - **Deep Research report** (Markdown): 10,000+ words with table of contents and traceable sources
   - **Visual report** (HTML): Interactive, publicly shareable visual report
5. Preview, download (PDF/Word), or share as needed
## Tips for best results
### 1. Focus the scope
Before submitting, consider specifying:
- **Time range**: "from 2023 to present"
- **Geographic scope**: "US market only"
- **Source types**: "prioritize official reports and academic papers"
- **Question decomposition**: Break broad questions into sub-questions

### 2. Calibrate during clarification
- State directions you do *not* want covered
- Add specific dimensions or angles for focus
- Provide background context for complex questions

<Callout type="warning">
Keep clarification responses concise and specific — overly long or unclear input may cause research drift.
</Callout>

### 3. Be patient during execution
Deep Research typically takes 10–25 minutes. The system runs in the background — you don't need to stay on the page.

<Callout type="warning">
**Do not click "Stop output"** — this will terminate the research. If the page appears unresponsive, simply refresh.
</Callout>

## Important notes
1. **Execution time**: 10–25 minutes. Task runs asynchronously — you'll be notified upon completion
2. **Credit refunds**: Automatically refunded for tool invocation errors; submit feedback for off-direction research
3. **Input quality**: Concise, well-defined questions produce better results
4. **Scope boundaries**: For simple Q&A, use standard chat mode for faster responses
5. **Terms**: Subject to [Kimi User Service Agreement](https://www.kimi.com/user/agreement/modelUse?version=v2)

## Related resources
- Technical report: [Kimi-Researcher: End-to-End RL Training](https://moonshotai.github.io/Kimi-Researcher/)
- User gallery: [kimi.com/deep-research](https://www.kimi.com/deep-research?showGallery=true)

<Frames
  src="./images/overview/dr-gallery.png"
  alt="DR gallery"
/>
