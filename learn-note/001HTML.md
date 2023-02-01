# [HTML 介绍](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Introduction_to_HTML)

- 学习一些重要概念和语法
- 如何对文本应用 HTML，创造超链接，以及使用 HTML 构造一个网页

## HTML入门

- [HTML](https://developer.mozilla.org/zh-CN/docs/Glossary/HTML) (HyperText Markup Language) 不是一门编程语言，而是一种用来告知浏览器如何组织页面的**标记语言**。它由一系列的**元素（[elements](https://developer.mozilla.org/zh-CN/docs/Glossary/Element)）**组成，这些元素可以用来包围不同部分的内容，使其以某种方式呈现或者工作。
- 标签不区分大小写，推荐全部小写
- 元素
  - 开始标签
  - 结束标签
  - 内容
  - 属性
- **嵌套元素**：在一个元素中还嵌套着其他元素

```html
<p>My cat is <strong>very</strong> grumpy.</p>
```

- **块级元素**：在页面中以块的形式展现
  - 单独占行
  - 不会被嵌套进内联元素中，可以嵌套进其他块级元素
- **内联元素**：通常出现在块级元素中环绕文档内容的一小部分
  - 不会导致文本换行，通常出现在一堆文字之间
  - 例：a,strong,em
- **空元素**：只有一个标签
- **布尔属性**：没有值的属性
  - 只能有和它的属性名一致的属性值
- **实体引用**：使用特殊字符

| 原义字符 | 等价字符引用 |
| :------- | :----------- |
| <        | \&lt;        |
| >        | \&gt;        |
| "        | \&quot;      |
| '        | \&apos;      |
| &        | \&amp;       |

- **注释**：\<!-- -->

## head标签与HTML中的元数据

- head元素内容不会在浏览器中呈现，而是会保存页面中元数据

- **元数据**：\<meta>元素

  - 描述数据的数据
  - name属性：指定元素类型
  - content属性：指定了实际的元数据内容

- 添加图标（head）

  - ```html
    <link rel="icon" href="favicon.ico" type="image/x-icon">
    ```

- CSS（head）

  - ```html
    <link rel="stylesheet" href="my-css-file.css">
    ```

- JS（body）

  - ```html
    <script src="my-js-file.js" defer></script>
    ```

  - `defer`：在处理完HTML后处理JS

- 设置主语言

  - ```html
    <html lang="zh-CN">
    ```

- 设置分段语言

  - ```html
    <p>Japanese example: <span lang="ja">ご飯が熱い。</span>.</p>
    ```

## HTML文本处理基础

- `<p></p>`：段落
- `<h1></h1>`：标题
- 列表
  - `ul`：无序列表
  - `ol`：有序列表
  - `li`：列表元素
- 强调
  - `<em></em>`：重音斜体
  - `<strong></strong>`：非常重要
- 字体
  - `<i></i>`：斜体
  - `<b></b>`：粗体
  - `<u></u>`：下划线

## 创建超链接

- 超链接可以链接到任何其他文档（资源），或其中一部分
- 几乎任何网络内容都可以转换为链接
- `<a href="" title="" target="_blank"></a>`：创建语法
  - `href`：地址
    - 可以通过id链接到文档片段
    - 电子邮件：`mailto:`前缀
  - `title`：提示信息
  - `target`：点击后的标签页状态
  - `download`：为下载链接时默认文件名
- 统一资源定位符（英文：**U**niform **R**esource **L**ocator，简写：URL）：定义了在网络上的位置的一个文本字符串

## 高级文本排版

- 描述列表：对术语进行描述

  - `<dl></dl>`：描述列表
  - `<dt></dt>`：术语
  - `<dd></dd>`：描述

- 引用

  - `blockquote`：块引用
    - `cite`：应用链接
  - `<q></q>`：行内引用
    - `cite`：应用链接
  - `<cite></cite>`：引文
    - 不显示，可以通过配上`<a>`显示

- `<abbr></abbr>`：缩略语

  - `title`：表示全意

- `<address></address>`：标记联系方式

- 上下标

  - `<sup></sup>`：上标
  - `<sub></sub>`：下标

- 展示计算机代码

  - `<code></code>`：通用代码
  - `<pre></pre>`：代码块
  - `<var></var>`：标记具体变量名
  - `<kbd></kbd>`：标记输入电脑的输入
  - `<samp></samp>`：标记电脑程序的输出

- `<time></time>`：标记时间和日期

  - 附上清晰的可被机器识别的日期格式

  - 

  - ```HTML
    <!-- 标准简单日期 -->
    <time datetime="2016-01-20">20 January 2016</time>
    <!-- 只包含年份和月份-->
    <time datetime="2016-01">January 2016</time>
    <!-- 只包含月份和日期 -->
    <time datetime="01-20">20 January</time>
    <!-- 只包含时间，小时和分钟数 -->
    <time datetime="19:30">19:30</time>
    <!-- 还可包含秒和毫秒 -->
    <time datetime="19:30:01.856">19:30:01.856</time>
    <!-- 日期和时间 -->
    <time datetime="2016-01-20T19:30">7.30pm, 20 January 2016</time>
    <!-- 含有时区偏移值的日期时间 -->
    <time datetime="2016-01-20T19:30+01:00">7.30pm, 20 January 2016 is 8.30pm in France</time>
    <!-- 调用特定的周 -->
    <time datetime="2016-W04">The fourth week of 2016</time>
    ```

## 文档和网站结构

![一个简单站点首页截图](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure/sample-website.png)

- `<header>`：页眉
- `<nav>`：导航栏
- `<article>`：文章
- `<section>`：分块，主内容的一部分
- `<main>`：主内容，每个页面只能使用一次
- `<aside>`：侧边栏，与主内容有联系
- `<footer>`：页脚
- `<div>`和`<span>`：无语义元素，用来封装一组元素配合CSS、JS
  - `<div>`：块级
  - `<span>`：内联
- `<br>`：换行
- `<hr>`：水平分割线

## 调试HTML

- [Markup Validation Service](https://validator.w3.org/)

# [多媒体和嵌入](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Multimedia_and_embedding)

- 探索如何使用 HTML 在你的网页里如何包含多媒体信息

# [HTML 表格](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Tables)

- 基本的表格标记及更多复杂的特性，例如实现标题和总结

