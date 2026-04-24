# Kimi 帮助中心 — 工程对接文档

Kimi 帮助中心中文版文档项目，共 85 篇文档，覆盖 11 个业务模块。

## 目录结构

```
docs/zh-CN/
├── _config.json                    # 全局配置
├── {category}/                     # 业务模块目录
│   ├── _category.json              # 一级页面展示配置
│   ├── _category.png               # 模块缩略图
│   ├── images/{subdir}/*.png|gif   # 图片资源
│   └── *.md                        # 文档文件
```

## 模块一览

| 目录 | 模块名称 | order | 文档数 |
|------|---------|-------|--------|
| `new-user-guide/` | 新手指南 | 1 | 8 |
| `agent/` | Agent 模式 | 2 | 4 |
| `websites/` | 网站生成 | 3 | 2 |
| `ppt/` | PPT 制作 | 4 | 5 |
| `docs-and-sheets/` | 文档与表格 | 5 | 3 |
| `deep-research/` | 深度研究 | 6 | 8 |
| `kimi-claw/` | Kimi Claw | 7 | 17 |
| `membership/` | 会员 | 8 | 10 |
| `kimi-code/` | Kimi Code | 9 | 11 |
| `kimi-api/` | Kimi API | 10 | 13 |
| `others/` | 其他 | 11 | 4 |

## 配置文件

### `_config.json`（全局配置）

```json
{
  "title": "站点标题",
  "description": "站点描述",
  "hot_questions": ["热门问题1", "热门问题2"],
  "search_placeholder": "搜索框占位文本",
  "field_definitions": {
    "extract_headings": {
      "type": "boolean",
      "default": false,
      "description": "是否抽取文章中的 ## 标题到二级文章列表页作为可展开子项"
    }
  }
}
```

### `_category.json`（一级页面展示配置）

帮助中心一级页面中，每个业务板块的展示信息。

| 字段 | 说明 |
|------|------|
| `title` | 业务板块标题 |
| `icon` | 业务板块图标 |
| `description` | 图标下方的简介文字 |
| `order` | 板块在一级页面的排列次序 |
| `note` | 备注说明（仅供内部参考，不渲染） |

## Frontmatter 字段说明

每篇 `.md` 文件顶部必须包含以下 YAML frontmatter：

```yaml
---
title: "文章标题"
slug: "category-article-name"
order: 1
extract_headings: false
preview: true
preview_content: "文章摘要"
---
```

| 字段 | 必填 | 说明 |
|------|------|------|
| `title` | 是 | 面包屑位置显示的标题 |
| `slug` | 是 | URL 路径标识，命名规则为 `{类别前缀}-{文章名}`，如 `agent-overview` |
| `order` | 是 | 文章在所属业务板块下的排列位置 |
| `extract_headings` | 是 | 是否在文章列表页展开该文章 md 中的二级标题 |
| `preview` | 是 | 文档页面搜索框中是否展示该文章 |
| `preview_content` | 是 | 文章在文档页面展示时的摘要文本 |

## SeoMeta 组件

紧跟在 frontmatter 之后，用于搜索引擎投放：

```html
<SeoMeta
  title="SEO 标题"
  description="SEO 描述"
  pageUrl="https://www.kimi.com/help/{category}/{slug}"
/>
```

## 页面标题与目录渲染规则

- 文章详情页右侧目录仅解析 **二级（`##`）及其以下层级标题**
- 一级标题（`#`）不参与右侧目录生成

## 自定义组件语法

### 图片容器（Frames）

```markdown
//Frames
![图片描述](images/{subdir}/{filename}.png)
![图片描述](images/{subdir}/{filename}.gif)
//
```

支持在一个 Frames 块中放置多张图片。

### 提示框（Callout）

```markdown
//Callout 提示
这是一条提示信息。
//
```

可用类型：`提示`、`注意`、`警告`

### 代码预览（CodePreview）

```markdown
//
示例内容 CodePreview
//
```

## 图片引用规范

- 路径格式：`images/{子目录}/{文件名}`，相对于当前 `.md` 文件所在目录
- 图片存放在各模块自己的 `images/` 目录下，按功能分子目录
- **不跨目录引用**，如需复用图片请复制一份到当前模块的 `images/` 下

示例：
```
agent/
├── images/
│   └── agent/
│       ├── overview-01.png
│       └── overview-02.png
└── overview.md  →  ![描述](images/agent/overview-01.png)
```

## 内部链接规范

- 同目录内链接：`[链接文本](文件名.md)` 或 `[链接文本](slug)`
- 跨目录链接：`[链接文本](slug)`
- 外部链接：`[链接文本](https://example.com)`
