# Kimi Help Center Docs

This repository stores the checked-in source content for the Kimi Help Center.
It contains locale-specific article trees and media assets, authored as
MDX-compatible Markdown.

## Repository Layout

```text
.
├── AGENTS.md
├── en-US/
└── zh-CN/
```

Content is organized by locale and category:

```text
<locale>/<category>/
├── _category.json
├── _category.png
├── article.md
└── images/<article>/...
```

Examples:

- `en-US/kimi-code/cli-getting-started.md`
- `en-US/kimi-code/images/cli-getting-started/screenshot-23.png`
- `zh-CN/deep-research/overview.md`

## What Belongs Here

- Public help center articles.
- Locale-specific category metadata and images.
- Article screenshots, illustrations, and other media assets.

## Authoring Rules

All authoring conventions for this repo live in [AGENTS.md](./AGENTS.md).

That includes:

- required front matter fields
- supported custom MDX components
- image placement conventions
- internal link conventions
- formatting constraints for MDX content

## Editing Guidance

- Keep articles MDX-compatible and simple.
- Do not add `import` statements in article files.
- Keep local assets under the matching category `images/` tree.
- Prefer updating existing slugs and routes carefully to avoid broken links.
- Follow the component and front matter rules in `AGENTS.md` before adding new
  content.

## Locales

- `en-US/` contains English help center content.
- `zh-CN/` contains Simplified Chinese help center content.
