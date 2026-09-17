# cases/ — 案例格式约定

`cases/tastings/`（产品品鉴）和 `cases/anatomies/`（公司拆解）会被 [lucyli-lpl.github.io](https://lucyli-lpl.github.io) 自动渲染。一个案例一个目录，主文件叫 `case.md`，章节用 `NN-slug.md`。

```
cases/tastings/claude-tag/
├── case.md            ← 必须；frontmatter + 一段摘要
├── 01-why.md          ← 章节，NN- 前缀决定顺序
├── 02-how.md
└── …
```

## 品鉴 `case.md` frontmatter

```yaml
product: Claude Tag              # 必填
company: Anthropic               # 必填
product_launched: 2026-06-23     # 可选，YYYY-MM-DD
analyzed: 2026-09-01             # 可选，站点按它排序
framework: ai-product-tasting    # 可选
framework_version: "1.0"         # 可选，字符串
verdict: "一句真判断，不是摘要"    # 必填；含引号或冒号时整体用引号包住
patterns:                        # 可选；用 ai-design-patterns 里的文件名（小写连字符）
  - thread-as-workspace
tags:                            # 可选
  - agent
```

`patterns` 里的名字如果在 pattern 库里存在，品鉴页会链过去，pattern 页也会反链回来；不存在只显示文字。

## 拆解 `case.md` frontmatter

```yaml
company: Example Inc             # 必填
filing_date: 2026-03-01          # 可选
exchange: NASDAQ                 # 可选
verdict: "一句真判断"             # 必填
patterns: []
tags: []
```

## 章节文件

```yaml
---
title: 为什么做
---
```

正文是普通 markdown。

## 常见错误

- `patterns: [a, b, c]` 行内数组在含特殊字符时会解析失败，用多行 `- ` 写法最稳
- `verdict` 里有 `"` 或 `：` 时必须整体加引号
- 目录里没有 `case.md` 的会被跳过，不报错
