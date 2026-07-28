---
title: "Projects"
slug: "project"
order: 4
extract_headings: false
preview: true
preview_content: "A Project is a persistent workspace that keeps a long-running task's reference files, chats, and project instructions together, so you don't have to re-explain the background in every new chat."
---

<SeoMeta
  title="What Is a Kimi Project? How to Create and Use It - Kimi Help Center"
  description="Learn about Kimi Projects: a persistent workspace that groups reference files, chats, and project instructions — ideal for writing a series of documents, ongoing research, or maintaining a codebase. Covers creating and managing projects, project instructions, project files, and plan quotas."
/>

# Projects

A Project is a persistent workspace. You can keep the reference files, chats, and project instructions for one long-running task together in a single project, and every chat you start inside the project automatically carries this context — so you don't have to re-upload the same files or re-explain the project background each time.

**When to use a project**: Create a project when the work will continue over time, produce more than one output, or depend on the same set of files — for example, writing a series of documents, conducting ongoing research, or maintaining a codebase. If the task is self-contained and doesn't need shared context, just use a regular chat.

<Callout type="info">
The Kimi Work desktop app also has "Projects," which are separate from the Kimi (Chat) projects described here — the two are not connected and don't share data.
</Callout>

## Creating and managing projects

**Entry points**:
- the "+" button to the right of the "Projects" section in the sidebar;
- the "+ New project" item at the top of the home Project selector.

**Create**: enter a project name (required, 1–50 characters) and optionally project instructions; click "Create" to open the project home page.

**Edit / Delete**:
- hover over or right-click a project name in the sidebar to "Edit title" or "Pin";
- deleting a project requires confirmation. **Once deleted, the project's chats, files, and project instructions are permanently removed and cannot be recovered** — please proceed with care.

**Sidebar**: the "Projects" section sits below the Kimi Claw entry and above the chat history, listing your projects by most recently created; expand a project to see its chats.

## Project home page

The project home page uses a three-column layout:
- **Left**: the standard sidebar;
- **Center**: a chat-starting area and the project's chat list. The input box reads "Start a chat in 'project name'…", and sending a message here creates a chat that automatically belongs to the current project;
- **Right Panel**: two blocks — Instructions and Files (collapsible).

## What you can do in a project chat

Chats in a project have the same capabilities as regular Kimi chats, while automatically carrying the project's context. You can:
- use **project files** (read on demand by the model) and **project instructions**;
- use **plugins, Skills, and Goal**;
- **choose the model**.

Start a separate chat for each distinct output so its messages and results stay focused; the project keeps these related chats together.

## Project instructions

- Project instructions are custom instructions specific to the project (plain text) that Kimi follows in every chat within it;
- For example: "You are a senior product manager. Reply in Chinese and output in Markdown.";
- They take effect from your next message or a new chat after saving.

## Project files

- Upload reference files to a project for all its chats to use;
- Supported formats match Kimi Agent uploads: PDF, DOCX, XLSX, CSV, TXT, MD, common code files, and common image formats;
- **Each file must be no larger than 100 MB, and you can upload up to 50 files**;
- Project files are **read on demand by the model** — instead of preloading every file's full text in each turn, the model decides which files it needs based on your question;
- The Files block shows a capacity bar at the bottom; when it is near or at the limit, you will be prompted to delete files or upgrade your plan.

## How context works in a project

When you start a chat in a project, the context injected into the model includes: **system prompt + global main memory + project instructions + project files read on demand**.

Regular (non-project) chats do not inject project instructions or files; a project's instructions and files only take effect within that project and do not affect other projects or regular chats.

## Quotas and plans

The number of projects and project storage scale with your membership plan:

| Plan | Free | Go | Pro | Max | Ultra |
|---|---|---|---|---|---|
| Projects | 2 | 20 | 20 | 100 | 100 |
| Project storage | 500MB | 20GB | 20GB | 50GB | 50GB |

Other limits (such as chats per project and the character limit for project instructions) also scale with your plan; for the latest figures, see the [membership plans page](/membership/membership-pricing).

## FAQ

### Are project files fully read in every turn of a chat?
No. Project files are read on demand — the model decides which files it needs based on your question and reads only those, rather than preloading all files every turn.

### How many files can a project hold?
Each file must be no larger than 100 MB, and you can upload up to 50 files. Total project storage scales with your plan; see the [membership plans page](/membership/membership-pricing).

### What happens when I delete a project?
Deleting a project **permanently removes** its chats, files, and project instructions, and this cannot be undone. Please confirm before deleting.

### What if I hit the project count or storage limit?
Delete projects or files you no longer need to free up space, or upgrade your plan for a higher quota. See the [membership plans page](/membership/membership-pricing) for details.
