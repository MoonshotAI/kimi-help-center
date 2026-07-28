---
title: "Creating skills FAQ"
slug: "create-custom-skills-faq"
order: 12
extract_headings: true
preview: false
---

<SeoMeta
  title="Creating skills FAQ - Kimi Help Center"
  description="Common questions about creating Kimi Skills, including document uploads, token usage, frequency limits, skill naming, and handling creation failures."
/>

# Frequently asked questions (FAQ) about skills

## Why is the "Create Skill" button disabled?

This may happen due to the following reasons:
1. The uploaded file or skill description is incomplete.
2. The file format or quantity does not meet requirements.
3. The system has detected that your account credits has been exhausted.

## How creating Skills consumes credits?

Creating a skill consumes your **tokens**, which can be from your gifted searches or your official membership credits.

**Deduction Order**:
1. Gifted searches are prioritized.
2. If gifted searches are unavailable, membership credits is used.

<Callout type="info">
If the creation process fails, no tokens will be deducted. Tokens are only consumed upon successful creation.
</Callout>

## Are there limits on the number or frequency of creations?

Yes, to ensure system stability and fair usage, there are the following limits:

1. **Concurrency Limit**: A maximum of **3 tasks** (Creating + Failed) can run in parallel. If you reach this limit, you will receive a prompt to retry after some time.
2. **Daily Limit**: Each user can perform a maximum of **10 "Office Document to Skill" conversions** per day (including retries). Exceeding this limit will show a toast notification.

## What should I do if a skill creation fails?

* You can choose to **Retry** or **Delete** the failed skill card.
* Failed attempts do not consume credits.
* The original skill description will be displayed on the failed card to help you distinguish between different tasks.

## What naming requirements apply to new skills?

New skill names must comply with the following rules:
1. **Cannot duplicate existing skills**: Including official skills and any skills you have already added.
   - For example, if you have skills A, B, and C, creating a new skill named A requires renaming to avoid conflicts.
2. **Character length**: Maximum of 25 characters.
3. **Allowed characters**: Only lowercase English letters, hyphens `-`, and underscores `_`.

<Callout type="info">
Following these rules ensures your skill is successfully added and avoids confusion with existing skills.
</Callout>

## What happens if a skill name is reported as "already in use"?

When creating a new skill, the system checks whether the entered name conflicts with existing skills, including official skills and those you have already added.
If a conflict is detected, a popup will appear saying:
> The skill name `/skill-name` is already in use. Please rename to avoid confusion.

At this point, you can either enter a new skill name and click **Rename and Add**, or click **Cancel** to abandon the creation.

## What if I don't resolve a naming conflict?

The system does not allow skills with duplicate names to be added. If you don't resolve the naming conflict, you cannot complete the skill creation.