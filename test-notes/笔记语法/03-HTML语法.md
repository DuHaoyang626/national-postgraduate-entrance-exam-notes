---
title: 03 - HTML 语法
date: 2026-08-03
tags:
  - obsidian
  - html
aliases:
  - HTML
  - 下划线
---

# 🌐 HTML 语法

> [!info] 说明
> Obsidian 在**阅读视图**中会渲染笔记内的 HTML 标签，因此可以用 HTML 实现标准 Markdown 做不到的排版，例如**下划线**、文字颜色、居中、折叠、表格、iframe 等。本页演示常用写法。

## 一、下划线（Underline）

标准 Markdown 没有下划线语法，用 HTML 的 `<u>` 标签实现：

`<u>这是一段下划线文字</u>` → <u>这是一段下划线文字</u>

> 区分三种类似效果：
> - <u>下划线</u> —— `<u>`（HTML）
> - ~~删除线~~ —— `~~删除线~~`（Markdown）
> - ==高亮== —— `==高亮==`（Obsidian）

## 二、文字颜色

`<span style="color:red">红色</span>` → <span style="color:red">红色</span>

- <span style="color:red">红色</span>
- <span style="color:blue">蓝色</span>
- <span style="color:green">绿色</span>
- <span style="color:orange">橙色</span>
- <span style="color:#7c3aed">紫色（十六进制 #7c3aed）</span>
- <span style="background-color:#fef08a">背景色高亮</span>

## 三、居中

```html
<center><b>居中的粗体文字</b></center>
```

<center><b>居中的粗体文字</b></center>

## 四、折叠块（details / summary）

```html
<details>
  <summary>点击展开</summary>
  这里是折叠后的内容。
</details>
```

<details>
  <summary>点击展开</summary>
  这里是折叠后的内容，支持任意 HTML，比如 <b>加粗</b>、<i>斜体</i>、<span style="color:red">颜色</span>。
</details>

## 五、HTML 表格

```html
<table>
  <tr><th>名称</th><th>数量</th><th>单价</th></tr>
  <tr><td>苹果</td><td>3</td><td>5 元</td></tr>
  <tr><td>香蕉</td><td>5</td><td>2.5 元</td></tr>
</table>
```

<table>
  <tr><th>名称</th><th>数量</th><th>单价</th></tr>
  <tr><td>苹果</td><td>3</td><td>5 元</td></tr>
  <tr><td>香蕉</td><td>5</td><td>2.5 元</td></tr>
</table>

## 六、上标与下标

- 化学式：`H<sub>2</sub>O` → H<sub>2</sub>O
- 平方：`x<sup>2</sup> + y<sup>2</sup>` → x<sup>2</sup> + y<sup>2</sup>

## 七、键盘按键样式（kbd）

`<kbd>Ctrl</kbd> + <kbd>S</kbd>` → <kbd>Ctrl</kbd> + <kbd>S</kbd>

## 八、iframe（嵌入网页）

```html
<iframe src="https://example.com" width="100%" height="300"></iframe>
```

> [!warning] 注意
> - iframe 需要联网，且部分网站通过 `X-Frame-Options` 禁止被嵌入。
> - Obsidian 也支持 `![[https://url]]` 语法直接嵌入网页，详见 [[05-嵌入Embed]]。

## 九、HTML 注释

`<!-- 这是注释 -->` —— 阅读视图中不可见，但编辑视图中可见：

<!-- 这是 HTML 注释，阅读视图中不可见 -->

## 十、视频 / 音频（HTML5）

```html
<video controls src="https://example.com/video.mp4"></video>
<audio controls src="https://example.com/audio.mp3"></audio>
```

> 本地音频/视频请优先使用嵌入语法，见 [[05-嵌入Embed]]。

## 注意事项

- **块级 HTML**（`<details>`、`<table>`、`<center>` 等）与 Markdown 混排时，HTML 块前后要留**空行**。
- 行内 HTML（`<span>`、`<u>`、`<sub>` 等）可直接写在段落中。
- 安全提醒：从网页复制的 HTML 可能携带脚本，Obsidian 会拦截，请勿粘贴不可信内容。

---

*返回总览：[[Home]] · 下一篇：[[04-链接与反链接]]*
