---
title: "Kimi Sheets use cases & prompt library"
slug: "sheets-cases"
order: 3
extract_headings: false
preview: false
---

<SeoMeta
  title="Kimi Sheets use cases \u0026 prompt library - Kimi Help Center"
  description="Example use cases and prompts for Kimi Sheets — from financial valuation to storyboard creation."
  pageUrl="https://www.kimi.com/help/docs-and-sheets/sheets-cases"
/>

# Kimi Sheets use cases

<Callout type="info">
Example use cases and prompts for Kimi Sheets — from financial valuation to storyboard creation.
</Callout>

## Financial valuation

Like a financial analyst, Kimi collects real financial data, builds a DCF valuation model, and performs a simulated company valuation.

<Frames
  src="./images/sheets-cases/dcf.png"
  alt="DCF"
/>

**Example prompt**:

<CodePreview
  files={[
    {
      name: "prompt.md",
      language: "markdown",
      content: "Perform a DCF valuation of XX Healthcare. Put the entire valuation process and data\ninto an Excel spreadsheet, cite data sources, provide the reasoning behind estimated\nfigures such as market size, growth rates, and market share, and incorporate macro\nenvironment analysis.",
    },
  ]}
/>

## Storyboard creation

Like a storyboard artist, Kimi creates Excel-format video storyboard scripts including duration, shot descriptions, narration, sound effects, and reference frames.

<Frames
  src="./images/sheets-cases/transcript.png"
  alt="Transcript"
/>

**Example prompt**:

<CodePreview
  files={[
    {
      name: "prompt.md",
      language: "markdown",
      content: "Create a storyboard script in Excel for a 3D promotional video about Kimi AI's new\nupgrade — OK Computer — which supports generating and editing Office documents\n(e.g., long-form thesis formatting in Word, data modeling and analysis in Excel,\nautomatic slide generation).\n\nThe Excel should include:\nColumn A: Sequence number (1-20)\nColumn B: Cumulative duration (seconds)\nColumn C: Shot duration (seconds)\nColumn D: Shot description (3D / camera movement)\nColumn E: Narration/text (use different background colors to distinguish narration\nfrom on-screen text)\nColumn F: Sound effects/BGM (use different font colors to distinguish)\nColumn G: Storyboard frames (generate an image for each shot — maintain visual\nconsistency using the classic black-and-white line sketch style)\n\nPlease design the creative outline, script, and storyboards independently, then\ngenerate frames to complete this script, presented in a polished Excel format.",
    },
  ]}
/>

## More scenarios & example prompts

| Scenario | Example prompt |
|------|-----------|
| Financial modeling | Perform a DCF valuation of XX Company — put the full process and data into Excel, cite sources, and explain the reasoning behind key assumptions like growth rates |
| Industry data comparison | Research the top 20 domestic NEV companies — list market cap, 2025 sales volume, flagship models, and recent news in a comparison table |
| Literature cataloging | Search for papers on LLM inference optimization from the past three months — organize into Excel with title, authors, core methodology, and key contributions |
| Multi-sheet merge | [Upload 12 monthly sales Excel files] Merge these 12 sheets into an annual summary, calculate month-over-month growth rates, and use formulas for cross-sheet linkage |
| Sales lead extraction | [Upload expo PDF/images] Extract all exhibitor information and organize into a 1,000-row sales leads Excel file with company name, contact info, and product category |
| Project management | Create a PMO project management Excel with task list, assignees, progress status, Gantt chart, and cross-sheet linkage |
| Data visualization | Turn this sales data Excel into a visual dashboard with trend line charts, regional distribution charts, and completion rate donut charts |
