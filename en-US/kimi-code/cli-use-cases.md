---
title: "Common use cases"
slug: "cli-use-cases"
order: 4
extract_headings: false
preview: false
---

<SeoMeta
  title="Common use cases - Kimi Help Center"
  description="Here are some typical scenarios for using Kimi Code CLI in everyday development, each with example prompts for reference."
  pageUrl="https://www.kimi.com/help/kimi-code/cli-use-cases"
/>

Here are some typical scenarios for using Kimi Code CLI in everyday development, each with example prompts for reference.

## Implement new features

Describe your requirements in natural language — the AI will automatically read relevant code, write new code, and verify the results.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Add a sort-by-registration-date feature to the user list page — both frontend and backend need changes",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Implement a rate limiter middleware using the token bucket algorithm, limiting each IP to 60 requests per minute",
    },
  ]}
/>

## Fix bugs

Paste the error message directly to the AI — it will automatically locate the root cause and provide a fix.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "After running npm test I got this error, please fix it:\nTypeError: Cannot read properties of undefined (reading 'map')\n  at UserList (src/components/UserList.tsx:23)",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "The CI pipeline failed at the lint stage. Here's the log: ... Please fix it",
    },
  ]}
/>

## Understand a project

When you're onboarding onto a new project or need to understand a specific piece of code, just ask.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "What's the overall architecture of this project? What are the main modules?",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "What does src/auth/middleware.ts do? How does the authentication flow work?",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Explain how database migrations are managed in this project",
    },
  ]}
/>

## Automate small tasks

Ideal for batch code modifications, adding documentation, generating tests, and other repetitive work.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Add JSDoc comments to all exported functions in the src/utils/ directory",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Generate unit tests for all public methods of the UserService class",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Replace all var declarations in the project with const or let",
    },
  ]}
/>

## General tasks

Kimi Code CLI is not limited to coding — it can also handle research, data analysis, bulk file operations, and more.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Research the current mainstream Node.js ORM libraries and compare their pros and cons",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Analyze access logs from the past 7 days in the logs/ directory and list the top 10 request paths",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Merge all CSV files in the data/ directory into one and remove duplicate rows",
    },
  ]}
/>
