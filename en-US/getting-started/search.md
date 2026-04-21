---
title: "Agentic search"
slug: "search"
order: 5
extract_headings: false
preview: false
---

<SeoMeta
  title="Agentic search - Kimi Help Center"
  description="Kimi's Agentic Search is built on an end-to-end agentic reinforcement learning architecture. Unlike traditional tool-orchestration approaches, it lets the AI..."
/>

# Agentic search

<Callout type="info">
Kimi's Agentic Search is built on an end-to-end agentic reinforcement learning architecture. Unlike traditional tool-orchestration approaches, it lets the AI autonomously decide when to search, which tools to invoke, and how to adjust strategy — enabling complex information gathering and processing tasks.
</Callout>

Compared to traditional keyword-matching search, Kimi's search capabilities have gone through two major evolutions:
- **Explorer Search** (October 2024) combined large language model semantic understanding with real-time information retrieval, automatically decomposing complex questions and tracing sources.
- **Agentic Search** goes further with autonomous planning and tool invocation, supporting financial data queries, academic literature retrieval, image search, and other multimodal tasks.

## Web search settings

<Frames
  src="./images/search/web-search.png"
  alt="Web search"
/>

Web search (Auto/Off) breaks through knowledge freshness boundaries to deliver real-time, trustworthy, and traceable information.

Click the "Web search" toggle below the chat input box. When enabled, Kimi autonomously determines whether the current question requires real-time data and intelligently invokes search engines and vertical databases to retrieve and synthesize information.

## Core capabilities

### 1. Freshness meets authority
Real-time web retrieval covering 100+ verified, trustworthy sources (major news outlets, government announcements, financial data platforms, academic journal databases) — ensuring information is both current and authoritative.

### 2. Source attribution
All search-based answers include reference source links. Click through to view the original page and fully verify accuracy and context.

### 3. Global information access
Supports natural-language conversations in multiple languages. Kimi can proactively search non-English sources (e.g., Japanese technical documentation, French news) and automatically synthesize multilingual information.

## Recommended use cases

- Real-time news and updates (breaking news, stock market data, policy changes)
- Fact verification (online rumors, historical data, statistical methodologies)
- Professional research (competitor intelligence, academic frontiers, industry standards)

## Authoritative source badges

Kimi's web search filters sources across three dimensions — relevance, authority, and freshness — automatically filtering out risky sites, duplicate syndication, low-quality web content, and hallucinated information to ensure reliable results.

High-quality sources that pass Kimi's strict screening are marked with authority badges in responses (e.g., official website certification, academic certification, media certification icons), helping you quickly identify highly trustworthy information.

**Source screening mechanism**:
- **Filtered out**: Low-quality aggregator sites, unverified self-media, expired cached pages
- **Prioritized**: Government agency websites, authoritative media, academic journals, official financial reporting channels

## Financial & academic data sources

<Frames
  src="./images/search/screenshot-5.png"
  alt="screenshot 5"
/>

In professional scenarios, Kimi supports querying vertical-domain databases for structured, traceable professional data.

<Frames
  src="./images/search/screenshot-6.png"
  alt="screenshot 6"
/>

Simply state your request in the conversation, and Kimi will automatically select the appropriate data source.

### Example queries

- "Look up Apple's revenue data for the past five years"
- "Search for the latest papers on large language model inference optimization"
- "Compare GDP, GDP per capita, and unemployment rates of the world's top three economies"

### Supported data sources

| Source | Description |
|--------|-------------|
| **Global Finance Data** | Global stock, futures, index and other financial data |
| **Academic Data** | Journals, papers, preprints, dissertations, patents, etc. |
| **Stock Finance Data** | Chinese and global stock, futures, index and other financial data |
| **World Bank Data** | GDP, population, employment, trade of countries, etc. |

## Smart search

### Image search

Kimi supports image-based search and understanding. After uploading an image, Kimi can automatically invoke image search tools to identify the content and retrieve related information.

**Example queries**:
- "Where is this location?"
- "What's happening in this meme / what is this person saying?"
- "Find the real McDonald's"

**How to use**:
- Upload an image directly (supports JPG, PNG, and other formats)
- Describe the image content or ask image-related questions in your prompt
- Kimi will combine image recognition with web search to provide image origins, similar images, and related information

**Typical scenarios**:
- Identifying unknown objects, landmarks, or product models
- Finding the source or origin of an image
- Analyzing data in charts or screenshots and retrieving relevant background information

### Direct URL access

Kimi Search supports direct URL access to fetch internet resources.

<Frames
  src="./images/search/screenshot-22.png"
  alt="screenshot 22"
/>

**Paste a URL directly into the conversation**, and Kimi will automatically fetch and analyze the page content.

**Example use cases**:
- Summarize the key points of this article
- Extract the key data from this earnings report PDF
- Search for image information from the URL

## Tips

<Callout type="warning">
- Prefer **publicly accessible** links (e.g., news pages, public PDF documents)
- Some **password-protected** or crawl-restricted pages may not be accessible
- For **dynamically loaded** pages, Kimi may only retrieve the initial HTML content
- Kimi **cannot re-read shared conversation links** (i.e., links to other Kimi chats)
</Callout>
