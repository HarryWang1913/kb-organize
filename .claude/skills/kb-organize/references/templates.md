# Knowledge Base Templates

## Common Frontmatter

```yaml
---
title: "Title"
date: YYYY-MM-DD
type: content | concept | collection-index | index | changelog | framework | profile | reference | project
status: active | draft | archived | reference
source_origin: self | web | book | course | meeting | project | unclear
review_cycle: weekly | monthly | quarterly | none
tags:
  - 内容/参考资料
  - 领域/AI
aliases:
  - Alias
---
```

## Concept Page

```yaml
---
title: "概念名称"
date: YYYY-MM-DD
type: concept
status: active
source_origin: self
review_cycle: monthly
tags:
  - 概念
aliases:
  - 概念别名
---
```

```markdown
# 概念名称

> 一句话核心定义

## 当前判断

写当前认知。资料不足处写 `待补充资料`。

## 为什么重要

说明它在知识体系、业务、创作或决策中的位置。

## 核心要点

- **要点一**：含来源或证据。
- **要点二**：资料不足写 `待补充资料`。

## 相关文档

### 原创内容

- [[文档路径|简短描述]]

### 参考资料

- [[文档路径|简短描述]]

## 跨领域关联

- [[概念/相关概念]] - 关联说明

## 时间线

- YYYY-MM-DD | 首次建立
```

## Collection Index

```yaml
---
title: "集合名"
date: YYYY-MM-DD
type: collection-index
status: active
tags:
  - 索引/总目录
aliases:
  - 集合简称
---
```

```markdown
# 集合名

导语：覆盖来源、数量、主题范围和边界。

## 目录

| 文件 | 说明 |
|------|------|
| [[文件路径]] | 一句话说明 |
```

## Log Entry

```markdown
## [YYYY-MM-DD] maintenance | Title

- Changed:
  - `path/to/file.md`
- Links:
  - `[[概念/XXX]]`
- Notes:
  - 待补充资料
```

