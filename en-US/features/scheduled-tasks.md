---
title: "Scheduled Tasks"
slug: "scheduled-tasks"
order: 5
extract_headings: false
preview: true
preview_content: "Scheduled tasks let Kimi automatically run a fixed task at a time you set — ideal for daily briefings, weekly monitoring, and regular clean-ups. Available in Kimi and the Kimi Work desktop app."
---

<SeoMeta
  title="How to Use Kimi Scheduled Tasks - Kimi Help Center"
  description="Learn about Kimi scheduled tasks: have Kimi automatically run a task at a set time, with daily, weekly, monthly, or one-time schedules, an optional expiration date, and the ability to combine with Skills for more complex work. Ideal for daily briefings, weekly industry monitoring, and periodic data clean-ups. Available in Kimi and the Kimi Work desktop app."
/>

# Scheduled Tasks

Scheduled tasks let Kimi automatically run a fixed task at the time you set, so you don't have to start it manually each time. They're ideal for regular, repeated work — daily briefings, weekly industry monitoring, periodic data clean-ups, and so on.

Scheduled tasks are a general feature, available in **Kimi** and the **Kimi Work desktop app**.

## Creating a scheduled task

Two ways:

- **From the entry point**: click "Create scheduled task" in the sidebar and fill in the task in the dialog;
- **From a conversation**: describe your scheduling need in natural language, and Kimi will create a scheduled task for you, automatically drafting the title, schedule, and task content.

A scheduled task includes:

- **Title**: summarizes the task so it's easy to find in the task list;
- **Schedule**: daily, weekly, monthly, or doesn't repeat (one-time);
- **Expiration date**: you can set when the task expires (selected by default when creating);
- **Task content**: a prompt describing what the task should do. At the scheduled time, Kimi runs this fixed prompt.

## Writing a good task prompt

A good task prompt states three things at once:

- **When**: when to run it (a specific date / a time each day / a day each week);
- **Output format**: how you want the result (key points, a table, a template, word count, language);
- **Constraints**: what it must not do or must satisfy (e.g., within 200 words, Chinese only, include a risk note, output only 3 items).

**A universal template**: At [time], do [task], output as [format], and follow [constraints].

Here are some examples you can copy and adapt:

<CodePreview
  files={[
    {
      name: "market-news.txt",
      language: "text",
      content: "Every day at 9:00, summarize the latest market news as 3 key points plus 1 risk note, in Chinese, within 200 words.",
    },
    {
      name: "daily-report-reminder.txt",
      language: "text",
      content: "In 1 hour, remind me to finish today's work report, and attach the report template (four-part structure).",
    },
    {
      name: "bedtime-reminder.txt",
      language: "text",
      content: "At 22:30 tonight, remind me to: turn off the computer, wash up, and get ready for bed. Keep the tone gentle.",
    },
  ]}
/>

## Managing scheduled tasks

The **task list** shows all your scheduled tasks (ordered by time). Each task card lets you:

- turn the task on or off;
- more actions: locate the task, run it once now, edit, and delete.

In a conversation, a scheduled task appears as a **task card** showing its title, frequency, next run time, and content — you can likewise run it now, pause, edit, or delete.

## Running and notifications

- At the scheduled time, Kimi runs the fixed prompt set in the task;
- Each run creates a notification marked as unread; you can view each run's result and jump to the corresponding conversation;
- Read status syncs across web and mobile;
- After a task runs, you can **choose a model to keep asking follow-ups** in the result conversation, and type "/" to **invoke plugins and Skills**.

## Combining with Skills

Scheduled tasks can combine with **Skills** to handle more complex work — especially Kimi's **finance** Skills (market data, earnings analysis, and so on).

Before using one, **install and test the Skill first**, confirming it works as expected, then use it in a scheduled task.

## Expiration

An expiration date is selected by default when you create a task, to avoid stale tasks lingering. The default expirations are:

- Daily: +7 days;
- Weekly: +1 month;
- Monthly: +3 months.

<Callout type="info">
Scheduled tasks running locally in the Kimi Work desktop app are not subject to the expiration rules above; local tasks run on their cycle while the app is open, and triggers missed while the app is closed are not run afterward.
</Callout>

## Quotas and plans

Scheduled tasks limit the number of **tasks you can have active at once** (there is no limit on how many you create). The number of active tasks scales with your membership plan:

| Plan | Free | Go | Pro | Max | Ultra |
|---|---|---|---|---|---|
| Scheduled tasks | 2 | 6 | 15 | 20 | 25 |

- When you are at the active limit and create another task, the new task is **saved as inactive**, with a prompt to upgrade or turn off some tasks;
- If your active limit drops (plan downgrade or expired benefits), tasks over the limit are automatically paused.

For the latest quotas, see the [membership plans page](/membership/membership-pricing).

<Callout type="tip">
**Tip**: Before scheduling a task, try its content once in a regular conversation, or use "Run once now" to verify it — confirm the wording is clear and the result is what you expect before relying on the schedule. If the task depends on a Skill, install and test that Skill first.
</Callout>

## FAQ

### Is there a limit on how many scheduled tasks I can create?
There is no limit on how many you create, but the number you can have **active at once** scales with your plan. When you exceed the active limit, a new task is saved as inactive; you can upgrade or turn off some tasks to activate it.

### Do I need to keep my computer or app open for tasks to run?
Scheduled tasks created in Kimi run in the cloud — you don't need to keep a client open. Tasks running locally in the Kimi Work desktop app require the app to be open; triggers missed while it is closed are not run afterward.

### Can I choose a model when a scheduled task runs?
You can't choose a model when creating a task. After it runs, you can choose a model to keep asking follow-ups in the result conversation, and type "/" to invoke plugins and Skills.

### What if I hit the active task limit?
Turn off tasks you no longer need, or upgrade your plan for a higher active limit. See the [membership plans page](/membership/membership-pricing) for details.
