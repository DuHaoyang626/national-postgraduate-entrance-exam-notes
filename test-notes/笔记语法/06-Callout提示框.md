---
title: 06 - Callout 提示框
date: 2026-08-03
tags:
  - obsidian
  - callout
aliases:
  - Callout
  - 提示框
---

# 💬 Callout 提示框

> [!abstract] 说明
> **Callout** 是 Obsidian 的特色高亮块，语法为 `> [!类型]` 加缩进内容，阅读视图中渲染为带图标的彩色卡片。本页列出全部内置类型及进阶用法。

## 一、基础用法

```markdown
> [!note]
> 这是一个 note 提示框。
```

> [!note]
> 这是一个 note 提示框。

```markdown
> [!warning] 自定义标题
> 有标题的 warning 提示框。
```

> [!warning] 自定义标题
> 有标题的 warning 提示框。

```markdown
> [!tip] 只写标题，无内容
```

> [!tip] 只写标题，无内容

## 二、全部内置类型一览

| 类型 | 别名 | 视觉 |
|---|---|---|
| `note` | — | 蓝 · 铅笔 |
| `abstract` | `summary` `tldr` | 青 · 剪贴板 |
| `info` | — | 蓝 · 信息 |
| `todo` | — | 蓝 · 复选框 |
| `tip` | `hint` `important` | 青 · 火焰 |
| `success` | `check` `done` | 绿 · 对勾 |
| `question` | `help` `faq` | 黄 · 问号 |
| `warning` | `caution` `attention` | 橙 · 警告 |
| `failure` | `fail` `missing` | 红 · 叉 |
| `danger` | `error` | 红 · 闪电 |
| `bug` | — | 红 · 虫子 |
| `example` | — | 紫 · 列表 |
| `quote` | `cite` | 灰 · 引号 |

逐个渲染（实际效果）：

> [!note]
> note

> [!abstract]
> abstract / summary / tldr

> [!info]
> info

> [!todo]
> todo

> [!tip]
> tip / hint / important

> [!success]
> success / check / done

> [!question]
> question / help / faq

> [!warning]
> warning / caution / attention

> [!failure]
> failure / fail / missing

> [!danger]
> danger / error

> [!bug]
> bug

> [!example]
> example

> [!quote]
> quote / cite

## 三、可折叠 Callout

```markdown
> [!faq]- 默认折叠
> 点击展开后才显示的内容。

> [!faq]+ 默认展开
> 默认可见，也可手动折叠。
```

> [!faq]- 默认折叠
> 点击展开后才显示的内容。

> [!faq]+ 默认展开
> 默认可见，也可手动折叠。

## 四、嵌套 Callout

> [!question] 外层问题
> 这是一个外层提示框。
> > [!note] 内层注释
> > 这是嵌套的第一层。
> > > [!tip] 更深一层
> > > 可以无限嵌套下去。

## 五、Callout 内支持任意 Markdown

> [!note] 复杂内容
> - **加粗**、*斜体*、`行内代码`
> - 列表项 2
>
> ```python
> print("Callout 里的代码块")
> ```
>
> 1. 有序列表
> 2. 第二项

> [!success] 甚至可以放链接和嵌入
> 查看 [[项目Alpha]]，或嵌入 [[会议记录#关键决策]]。
> ![[会议记录#关键决策]]

## 六、自定义 Callout（CSS 片段）

新建 CSS 片段（如 `custom-callout.css`），加入：

```css
.callout[data-callout="custom"] {
  --callout-color: 255, 0, 255;
  --callout-icon: lucide-star;
}
```

启用片段后即可使用：

> [!custom] 自定义类型
> 这是一个自定义图标与颜色的 Callout。

> [!warning] 提示
> 自定义 Callout 需要先在「设置 → 外观 → CSS 片段」中启用对应文件。

---

*返回总览：[[Home]] · 上一篇：[[05-嵌入Embed]] · 下一篇：[[07-属性与标签]]*
