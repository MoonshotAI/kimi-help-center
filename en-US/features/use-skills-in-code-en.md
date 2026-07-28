---
title: "Using Skills in Kimi Code"
slug: "use-skills-in-code"
order: 11
extract_headings: false
preview: false
---

<SeoMeta
  title="Using Skills in Kimi Code - Kimi Help Center"
  description="Learn how to create and invoke Skills in Kimi Code CLI to standardize team coding conventions and automate development workflows."
  ogType="article"
/>

# Using Skills in Kimi Code

Kimi Code is an AI programming assistant designed specifically for developers, running directly in terminals or editors to help write code, fix bugs, and generate documentation. Kimi Code supports providing knowledge-based guidance through `SKILL.md` files. After reading them, the AI follows the standards defined within. Suitable for defining code styles, workflows, and best practices.

<Frames
  src="./images/skills/kimi-code-skill.png"
  alt="Invoke skills using slash command"
/>

## Invoking Skills

The Kimi Code CLI allows you to invoke Skills using slash commands:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "/skill:<name>",
    },
  ]}
/>

For example, entering `/skill:git-commits` will cause Kimi Code to read the corresponding `SKILL.md` content and send it as an instruction to the Agent.

You can also append additional descriptions after the slash command, which will be added to the end of the Skill instruction:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "/skill:git-commits fix user login issue",
    },
  ]}
/>

For regular conversations, manual invocation isn't necessary—the Agent will automatically determine based on context whether to read Skill content.

## Creating Your First Skill

Creating a Skill requires just two steps: Create a subdirectory in the Skills directory, then create a `SKILL.md` file inside it.

Recommended storage location (works for all projects):

<CodePreview
  files={[
    {
      name: "Directory Structure",
      language: "text",
      content: "~/.config/agents/skills/\n└── my-skill/\n    └── SKILL.md",
    },
  ]}
/>

`SKILL.md` uses YAML Frontmatter to define metadata, followed by Markdown for the core specifications:

<CodePreview
  files={[
    {
      name: "SKILL.md",
      language: "markdown",
      content: "---\nname: code-style\ndescription: My project code style standards\n---\n\n## Code Style\n\n- Use 4-space indentation\n- Use camelCase for variable names\n- Use snake_case for function names\n- Every function requires a docstring\n- Single lines not exceeding 100 characters",
    },
  ]}
/>

Both `name` and `description` in Frontmatter are optional fields. If omitted, the directory name is used as default.

### Example

Your team requires commit messages to follow Conventional Commits format, but having to explain it repeatedly is tedious. By writing it as a Skill, you only need a single command to invoke it in the future.

**Step 1: Create Skill File**

<CodePreview
  files={[
    {
      name: "~/.config/agents/skills/git-commits/SKILL.md",
      language: "markdown",
      content: "---\nname: git-commits\ndescription: Git commit message standards using Conventional Commits format\n---\n\n## Git Commit Standards\n\nUse Conventional Commits format: type(scope): description\n\nAllowed types: feat, fix, docs, style, refactor, test, chore\n\nExamples:\n- feat(auth): Add OAuth login support\n- fix(api): Fix user query returning empty value issue",
    },
  ]}
/>

**Step 2: After completing code changes, invoke the Skill**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "/skill:git-commits fixed login page layout shift in Safari",
    },
  ]}
/>

Kimi Code will read your standards, combine them with task descriptions, and directly output a properly formatted commit message without you needing to repeat any format requirements.

## Flow Skills: Defining Multi-Step Workflows

While regular Skills provide static standards, **Flow Skills** can define automated multi-step processes.

Set `type: flow` in Frontmatter and embed a flowchart in Mermaid or D2 format to create a Flow Skill.

<CodePreview
  files={[
    {
      name: "~/.config/agents/skills/code-review/SKILL.md",
      language: "markdown",
      content: "---\nname: code-review\ndescription: Code review workflow\ntype: flow\n---\n\n```mermaid\nflowchart TD\nA([BEGIN]) --> B[Analyze code changes, list all modified files and functionality]\nB --> C{Code quality meets standards?}\nC -->|Yes| D[Generate code review report]\nC -->|No| E[List issues and suggest improvements]\nE --> B\nD --> F([END])\n```",
    },
  ]}
/>

Execute using `/flow:<name>` command. The Agent will start from the `BEGIN` node and automatically complete each step in sequence until reaching `END`.

## Skill Loading Mechanism

Kimi Code CLI searches for and loads Skills based on the following priority (first matched takes precedence):

1. **Built-in Skills**: Installed with the software package, providing basic capabilities.
2. **User-level Skills**: Stored in home directory, applicable to all projects.
3. **Project-level Skills**: Stored in project directory, applicable only to that project.

You can also manually specify additional Skills directories using the `--skills-dir` parameter:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --skills-dir /path/to/my-skills",
    },
  ]}
/>

<Callout type="info">
Kimi Code CLI includes two built-in useful Skills: `kimi-cli-help` (answers CLI usage questions) and `skill-creator` (guides you through creating new Skills). Enter `/skill:skill-creator` to get started.
</Callout>

For complete configuration options and parameter explanations, please refer to the [Kimi Code CLI Skills Documentation](https://www.kimi.com/code/docs/en/kimi-code-cli/customization/skills.html).