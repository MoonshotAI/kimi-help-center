---
title: "常见使用案例"
slug: "cli-use-cases"
order: 4
extract_headings: false
preview: true
preview_content: "Kimi Code 常见使用场景与示例提示词。"
---
<SeoMeta
  title="Kimi Code CLI 常见使用案例 - Kimi 帮助中心"
  description="探索 Kimi Code CLI 的五类典型场景：实现新功能、修复 Bug、理解项目架构、自动化批量任务和通用调研分析，附实用提示词示例。"
/>
# 常见使用案例

以下是 Kimi Code CLI 在日常开发中的几个典型使用场景，每个场景附带了示例 prompt 供参考。

## 实现新功能

直接用自然语言描述你的需求，AI 会自动阅读相关代码、编写新代码并进行验证。

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "给用户列表页添加一个按注册时间排序的功能，需要前后端都改",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "实现一个 rate limiter 中间件，使用令牌桶算法，限制每个 IP 每分钟 60 次请求",
    },
  ]}
/>

## 修复 Bug

将错误信息直接粘贴给 AI，它会自动定位问题根源并提供修复方案。

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "运行 npm test 后报了这个错误，帮我修复：\nTypeError: Cannot read properties of undefined (reading 'map')\n  at UserList (src/components/UserList.tsx:23)",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "CI 流水线在 lint 阶段失败了，日志如下：... 帮我修复",
    },
  ]}
/>

## 理解项目

当你接手一个新项目或需要了解某段代码的逻辑时，直接询问即可。

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "这个项目的整体架构是什么？主要模块有哪些？",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "src/auth/middleware.ts 这个文件的作用是什么？认证流程是怎样的？",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "解释一下这个项目的数据库迁移是怎么管理的",
    },
  ]}
/>

## 自动化小任务

适合批量修改代码、添加文档、生成测试等重复性工作。

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "给 src/utils/ 目录下所有导出函数添加 JSDoc 注释",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "为 UserService 类的所有公开方法生成单元测试",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "把项目中所有 var 声明改成 const 或 let",
    },
  ]}
/>

## 通用任务

Kimi Code CLI 不仅限于编程，还可以处理调研、数据分析、批量文件操作等任务。

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "帮我调研一下目前主流的 Node.js ORM 库，对比它们的优缺点",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "分析 logs/ 目录下最近 7 天的访问日志，统计 Top 10 的请求路径",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "把 data/ 目录下所有 CSV 文件合并成一个，并去除重复行",
    },
  ]}
/>
