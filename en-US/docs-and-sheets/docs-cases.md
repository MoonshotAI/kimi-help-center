---
title: "Kimi Docs use cases & prompt library"
slug: "docs-cases"
order: 2
extract_headings: false
preview: false
---

<SeoMeta
  title="Kimi Docs use cases \u0026 prompt library - Kimi Help Center"
  description="Example use cases and prompts for Kimi Docs — from manuscript review to professional translation and PDF design."
  pageUrl="https://www.kimi.com/help/docs-and-sheets/docs-cases"
/>

# Kimi Docs use cases & prompt library

<Callout type="info">
Example use cases and prompts for Kimi Docs — from manuscript review to professional translation and PDF design.
</Callout>

## Review expert

Like a meticulous manuscript reviewer, Kimi breaks down revision feedback, pinpoints the relevant passages in your document, and automatically inserts detailed comments and suggestions.

**Example prompt**:

<CodePreview
  files={[
    {
      name: "prompt.md",
      language: "markdown",
      content: "You are a senior manuscript reviewer specializing in smart cities and regional planning.\nBelow is a set of specific review comments. Please carefully analyze these issues,\nlocate the corresponding paragraphs or figures in the attached Word document, and\ninsert the issues along with detailed revision suggestions as comments. Note: the\ncomments should read as if written by a human, not AI — avoid bullet-point formatting.\n\nPlease output the original manuscript with detailed comments.",
    },
  ]}
/>

## Professional translation

Like a tireless translator, Kimi translates a 50-page English PDF page by page into Chinese, preserving all formulas and code in the output.

**Example prompt**:

<CodePreview
  files={[
    {
      name: "prompt.md",
      language: "markdown",
      content: "Find the first assignment PDF for Stanford's CS336 course in English, then convert\nit to a Chinese PDF. Preserve all code and mathematical formulas in the Chinese version.\nThe translation should be fluent — do not omit or add any content.",
    },
  ]}
/>

<Frames
  src="./images/docs-cases/translate.png"
  alt="Translate"
/>

## PDF design & publishing service

Like a layout designer, Kimi helps you plan visual features, automatically arranges text and images, and generates publication-quality PDF portfolios.

<CodePreview
  files={[
    {
      name: "prompt.md",
      language: "markdown",
      content: "You are a curatorial publishing AI specializing in modern art, particularly Picasso studies.\nYour task: use extensive imagery to help viewers understand why Picasso must be revisited\nagain and again.\n\nOutput directly as a PDF.\n\nI. Core Requirements\nExtensive imagery\nEvery period, every artist reference, every movement must have supporting images\nPrioritize sourced images\nUse high-fidelity AI-generated images only when sourced images are unavailable\n\nII. Visual System\nMAP Logo as full-page watermark\nAsymmetric layout\nClear grid with controlled local disruption\nHigh-contrast black \u0026 white + primary color accents\n\nIII. Content Structure (generate all sections)\n1. Cover\nPicasso\nExhibition subtitle (English \u0026 Chinese)\nMAP Logo watermark\n\n2. Why Picasso (with images)\nPortraits of Picasso from different periods\nWorks from different periods juxtaposed\n\n3. Periods \u0026 Movements (image-centric)\nEach period must include 8–12 images:\nBlue Period\nRose Period\nCubism (Analytic / Synthetic)\nWar \u0026 Politics\nLate Experiments\n\nImage types:\nFull artwork\nDetail crops\nStructural deconstruction diagrams (AI-generated when needed)\n\n4. Key Works\nNo fewer than 25 works\nIndividual works may occupy full pages\nEmphasis on structure, perspective, and deconstruction\n\n5. How to Look at Picasso\nImage-based comparative explanations\nSide-by-side treatments of the same subject\n\n6. Exhibition Hall \u0026 Rhythm\nHigh-density viewing zones\nReflective buffer zones\n\n7. MAP's Contemporary Position\nWhy Shanghai needs Picasso\nWhy this moment matters",
    },
  ]}
/>

## More scenarios & example prompts

| Scenario | Example prompt |
|------|-----------|
| **Professional report** | Write a "2026 China Low-Altitude Economy Industry White Paper" in Word, McKinsey style, covering market size, competitive landscape, policy context, and investment recommendations |
| **Contract review** | [Upload contract.docx] Review this contract from an attorney's perspective, identify risk clauses, insert comments |
| **Financial modeling** | Build a three-year SaaS financial forecast model in Word, including revenue projections, cost structure, and cash flow |
| **Long-form distillation** | Distill this 30,000-word academic paper into a 5,000-word executive summary in Word format |
| **Multi-version comparison** | [Upload Contract V1 and V2] Compare versions, list all changes with impact descriptions, output as Word |
