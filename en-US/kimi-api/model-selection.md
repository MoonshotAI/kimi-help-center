---
title: "Model selection"
slug: "api-model-selection"
order: 6
extract_headings: true
preview: false
---

<SeoMeta
  title="Model selection - Kimi Help Center"
  description="How to choose the right Kimi API model. Compare kimi-k3, kimi-k2.6, and other models by capability, context length, speed, and price."
/>

# Model selection

Kimi API provides a variety of models for developers to choose from. Different models have different strengths in capability, speed, and price.

## Main models

### kimi-k3

`kimi-k3` is Kimi's flagship model, built for long-horizon coding and end-to-end knowledge work, with native visual understanding. K3 always runs in thinking mode. You can set the thinking effort via the top-level `reasoning_effort` parameter (supports `low`, `high`, `max`; defaults to `max`). It supports a context window of up to 1M tokens.

### kimi-k2.6

`kimi-k2.6` supports text, image, and video input, and supports switching between thinking and non-thinking modes. It is suitable for conversation, code generation, visual understanding, and agent tasks. It supports a context window of up to 256k tokens.

For the full list of available models and their parameters, visit [platform.kimi.ai/docs/introduction](https://platform.kimi.ai/docs/introduction).

## Selection dimensions

When choosing a model, evaluate the following dimensions:

- **Context length**: Different models support different maximum context windows. Choose a larger-context model for long-document processing.
- **Response speed**: Lighter models respond faster, making them suitable for latency-sensitive scenarios.
- **Generation quality**: Higher-tier models perform better on complex reasoning and creative tasks.
- **Price**: Choose the most cost-effective model based on your budget and call volume.
- **Thinking mode**: Choose `kimi-k3` for deep reasoning, or `kimi-k2.6` when you need flexibility to switch thinking mode on and off.

## Vision models (image understanding)

Vision models support image input and can be used for image description, OCR, chart interpretation, and similar tasks:

- Each image is billed at a fixed **1024 tokens**, regardless of image size or resolution.
- Common image formats are supported (JPEG, PNG, WebP, etc.).
- Images can be passed via URL or Base64 encoding.

## Currently unsupported capabilities

- **PPT generation API**: PPT generation is not currently available via API.
- **Deep research API**: Deep research is not currently available via API.

Watch the platform announcements for the latest updates.
