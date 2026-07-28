---
title: "What are Skills?"
slug: "what-are-skills"
order: 8
extract_headings: true
preview: false
---

<SeoMeta
  title="What are Skills? - Kimi Help Center"
  description="Learn about the working principles, types, and usage of Kimi Skills. Skills are reusable knowledge packages for extending Agent capabilities in specific tasks, containing instructions, best practices, scripts, and resources."
  ogType="article"
/>

# What are Skills?

<Frames
  src="./images/skills/what_is_skill.png"
  alt="what_is_skill"
/>

Skills are reusable knowledge packages designed to extend the boundaries of an AI agent's capabilities. Each skill includes:

- **Working approaches & operational guidance** — Methodologies tailored for specific task types.
- **Best practices & standards** — Industry standards and internal protocols to be followed.
- **Scripts, tools & reference resources** — Optional tools and materials to assist in execution.

## How to use?

At the start of a conversation, the Agent will see a list of available skills with their names and brief descriptions. If a skill is relevant to the current task, the Agent will load the full instructions and execute accordingly.

## User Journey

From discovering skills to creating your own, the complete path is as follows:

1. **Discover skills** — Browse official and recommended skills in the Skills panel to find one that fits your scenario.
2. **Install skills** — Click the "+" button to add a skill instantly.
3. **Invoke skills** — Type `/` in the chat box to select a skill, or let Kimi trigger one automatically based on your query.
4. **Create your own** — If existing skills don't meet your needs, upload documents or describe your requirements to generate a custom skill, or use `/skill-creator` to build one through dialogue.

## How Skills Work?

When you send a request, Kimi Agent assesses whether the current task involves a specific skill. If so, it automatically loads the corresponding skill and follows its instructions to complete the task.

Skills are only loaded when relevant to the task, ensuring they do not interfere with the context of other conversations.

## Skills vs. direct prompting: What's the difference?

Using weekly report writing as an example:
- **Direct Prompting**: Ask Kimi Agent directly, and it writes based on its own understanding of the format.
- **Using Skills**: After installing a weekly report skill, every output follows your preset structure, tone, and length without needing to repeat instructions.

| | Direct prompting | Using skills |
|---|---|---|
| **Need to explain requirements every time?** | Yes | No, applied automatically |
| **Output format stability** | Variable | Consistent as defined |
| **Best use case** | One-off, temporary tasks | Repetitive, fixed workflows |
| **Setup required?** | No | Requires creation or installation |

## Skill Types

### (1) Official skills & recommended skills

**Official skills**: Created and maintained by Moonshot AI, available to all users. Kimi automatically triggers them in relevant scenarios.

Common official skills include:
- `docx` — Create and edit Word documents, suitable for any .docx task including document creation, editing, comments, revisions, footnotes, table of contents, and Markdown to Word conversion.
- `deep-research` — Conduct in-depth research and build long-form reports using a toolkit, requiring at least 10 iterative search cycles, recursive reflection, and mandatory IPython visualization.

**Recommended skills**: Curated scenario-based skills available for one-click addition, covering common use cases like investment research and document formatting.

Common recommended skills include:
- `sop-writer` — Transform business processes into complete Standard Operating Procedure (SOP) documents, including process flowcharts, RACI matrices, detailed operational steps, and exception handling.
- `event-etf-study` — Starting from a concept or event, identify related stocks, build a market-cap-weighted ETF index, analyze market value changes during the event window, and generate interactive HTML dashboards. Used when users inquire about concept stocks, concept ETFs, event-driven analysis, or event research.

**Office document to skill**: Upload documents to generate skills and easily replicate style themes.

### (2) Open-source skills

Download or install suitable Skills from open-source communities, combined with Local Agents (like Kimi Code) or Cloud Agents (like Kimi Claw).

**Common AI Skill Hub Platforms**

| Platform | URL | Description |
|----------|-----|-------------|
| SkillsMP | https://skillsmp.com | An AI agent skill marketplace sourcing SKILL.md packages from GitHub, compatible with Claude Code and OpenAI Codex CLI |
| SkillsLLM | https://skillsllm.com | An open-source AI agent skill marketplace with 1,600+ security-vetted skills for Claude Code, Codex CLI, and ChatGPT |
| LobeHub Skills | https://lobehub.com/skills | Browse and distribute SKILL.md packages compatible with Claude Code, Codex CLI, and ChatGPT |

### (3) Customize skills

Custom skills created by you for personal workflows and specific domain tasks, such as:
- Applying specific style guides to documents or presentations.
- Generating emails or communication content based on fixed templates.
- Organizing meeting minutes in a specific format.
- Executing specific data analysis workflows.