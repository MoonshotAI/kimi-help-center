---
title: "Kimi API overview"
slug: "api-overview"
order: 1
extract_headings: true
preview: false
---

<SeoMeta
  title="Kimi API overview - Kimi Help Center"
  description="Introduction to Kimi API core concepts, model capabilities, how to send requests, and handle responses."
/>

# Kimi API overview

Kimi API Open Platform provides developers with powerful large language model capabilities, helping you quickly integrate AI into your own products and services.

## Platform overview

Kimi API is based on Moonshot's self-developed large language models, providing text generation, multi-turn conversation, file parsing, web search, and other core capabilities. The platform is compatible with the OpenAI API format, allowing developers to migrate and integrate at low cost.

**Platform URL**: [platform.kimi.ai](https://platform.kimi.ai/)

## Main concepts

### Text and multimodal models

`kimi-k3` is Kimi's flagship model, built for long-horizon coding and end-to-end knowledge work, with native visual understanding; `kimi-k2.6` supports text, image, and video input, as well as thinking and non-thinking modes, and is suitable for conversation, code generation, visual understanding, and agent tasks. The input to a model is commonly called a "prompt", and clear instructions plus representative examples are the most effective way to get stable outputs. Other models are also available — see the [Model List](https://platform.kimi.ai/docs/models) for details.

### Language model inference service

The language model inference service is an API service based on the pretrained models developed and trained by Moonshot AI. Today, the platform primarily exposes a Chat Completions interface for conversation, code generation, visual understanding, and agent tasks. Models do not directly access external resources such as the internet or databases by default, but you can extend them with official tools or custom tool calls when needed.

### Token

Text generation models process text in units called Tokens. A Token represents a common sequence of characters. For example, a single English word like "antidisestablishmentarianism" might be broken down into a combination of several Tokens, while a short and common phrase like "word" might be represented by a single Token. Generally speaking, for a typical English text, 1 Token is roughly equivalent to 3-4 English characters.

It is important to note that the total length of Input and Output cannot exceed the selected model's maximum context length. For example, `kimi-k3` supports a context window of up to 1M tokens. For other models' context lengths, see the [Model List](https://platform.kimi.ai/docs/models).

## Target audience

- **Independent developers**: Quickly build AI-driven personal projects or tools.
- **Enterprise technical teams**: Embed AI capabilities into enterprise products to improve user experience and operational efficiency.
- **Startups**: Access top-tier AI capabilities at low cost to accelerate product iteration.

## Main use cases

- **Intelligent customer service**: Context-aware automated Q&A to improve service efficiency and user satisfaction.
- **Content generation**: Article writing, marketing copy, code generation, and other creative scenarios.
- **Data analysis**: Document interpretation, report analysis, knowledge extraction, and summarization.
- **Knowledge Q&A**: Intelligent retrieval and Q&A systems based on private document libraries.

## Getting an API key

You need an API key to use our service. You can create an [API key](https://platform.kimi.ai/console/api-keys) in our [Console](https://platform.kimi.ai/console).

## Sending requests

You can use our Chat Completions API to send requests. You need to provide an API key and a model name. You can choose to use the default `max_completion_tokens` parameter or customize the `max_completion_tokens` parameter. You can refer to the [Chat API documentation](https://platform.kimi.ai/docs/api/chat) for the calling method.

## Handling responses

Generally, we set a 2-hour timeout. If a single request exceeds this time, we will return a 504 error. If your request exceeds the rate limit, we will return a 429 error. If your request is successful, we will return a response in JSON format.

If you need to quickly process some tasks, you can use the non-streaming mode of our Chat Completions API. In this mode, we will return all the generated text in one request. If you need more control, you can use the streaming mode. In this mode, we will return an SSE stream, where you can obtain the generated text. This can provide a better user experience, and you can also interrupt the request at any time without wasting resources.

## Model list

For all available models and their capabilities, see the [Model List](https://platform.kimi.ai/docs/models) page.

## Compare with other Kimi products

<Callout type="info">
The Kimi API Open Platform uses pay-as-you-go billing with no subscription plan. It is different from products such as Kimi Membership and Kimi Code — please distinguish between them.
</Callout>

| Product | Overview | Billing |
| --- | --- | --- |
| Kimi API Open Platform (platform.kimi.ai) | An easy-to-use, stable, and cost-effective LLM API service for developers and enterprises, helping AI applications move quickly from development to deployment and scale. | Option 1: pay-as-you-go (create an API key after signing up). See the [Pricing](https://platform.kimi.ai/docs/pricing/chat) page for billing details.<br>Option 2: enterprise plans (submit [this form](https://platform.kimi.ai/contact-sales) to contact sales). |
| Kimi Business | An intelligent office solution built for enterprise teams, suitable for small and medium-sized businesses with team collaboration needs. See [this page](https://www.kimi.ai/membership/pricing) for details. | Annual subscription. Seat requirements and pricing are subject to [this page](https://www.kimi.ai/membership/pricing). |
| Kimi Membership | Kimi offers four membership subscription tiers, covering personal daily use through heavy professional use. See [this page](https://www.kimi.ai/membership/pricing) for details. Note: Kimi Membership currently includes [Kimi Code](https://www.kimi.com/code/docs/en/) benefits; the Kimi Code API is independent from the API service on this platform. | Monthly or annual subscription. Pricing is subject to [this page](https://www.kimi.ai/membership/pricing). |

## Quick start

1. Visit [platform.kimi.ai](https://platform.kimi.ai/) to register a developer account.
2. Create an API key in the console.
3. Complete your first API call by referring to the API documentation.
4. Choose the right model and parameters based on your business needs.
