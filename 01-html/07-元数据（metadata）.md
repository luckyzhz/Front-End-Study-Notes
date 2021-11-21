> 元数据（metadata）含有页面的相关信息，包括样式、脚本及数据。

此前，我们一直讨论的是 `<body>` 里的标签。本章介绍 html 文档头部放置的标签，
这些标签，应该放在 `<head>` 标签内。

## 基准链接（base URL）

`<base>` 标签指定用于一个文档中包含的所有*相对* URL 的根 URL。
如果没有设置 `<base>` 标签，则 baseURI 指向当前文件所在目录。
例如：

```html
<head>
    <base href="http://www.example.com/">   <!-- 指定基链 -->
    <base target="_blank">  <!-- 指定相对链接默认在新窗口打开 -->
</head>

<body>
    <!-- 这个链接会指向 http://www.example.com/#anchor -->
    <a href="#anchor">锚</a>
</body>
```

注意，`<base>` 是单标签。另外，也可以把属性写在一起。例如：

```html
<base target="_blank" href="http://www.example.com/">
```

如果指定了多个 `<base>` 元素，只会使用第一个 `href` 和 `target` 值, 其余都会被忽略。

`<base>` 元素应放在其他任何属性是 URL 的元素之前。
因为浏览器是从上往下读 html 文档的，获取到了 `<base>` 信息，才能正确处理之后的相对链接。

> 小技巧：
> 如果我们想要页面上的链接默认在新标签页打开，可以设置：
> ```html
> <base target="_blank">
> ```

## 外部资源链接（link）

`<link>` 规定了当前文档与外部资源的关系，最常用于链接样式表（css），或创建站点图标。例如：

```html
<head>
    <link rel="stylesheet" href="main.css">
    <link rel="icon" href="_logo/zhi-logo.svg">
</head>
```

注意，`<link>` 是单标签。`rel` 属性表示 relationship，指明外部链接资源与当前文档的关系。例如 `rel="stylesheet"` 表示外链资源是样式表；`rel="icon"` 表示外链资源是站点图标。而 `href` 则指明了外链资源的地址。

## 元数据（meta）

`<meta>` 元素表示那些不能由其它 html 元相关（meta-related）元素（`<base>`、`<link>`, `<script>`、`<style>` 或 `<title>`）之一表示的任何元数据信息。

`<meta>` 最重要的作用是指定文档的字符编码。此外，还能指定网页的作者（author），关键字（keywords），描述（description）等，这些数据有利于 seo（搜索引擎优化）。
例如：

```html
<head>
    <!-- 应该坚持指定字符编码，否则很可能导致乱码。
    最常用的字符编码是 "utf-8" -->
    <meta charset="utf-8">

    <!-- 写明文档的作者 -->
    <meta name="author" content="zhi">

    <!-- 写明文档的关键字，用英文逗号分隔 -->
    <meta name="keywords" content="前端, 教程, html, css, js">

    <!-- 写明文档描述，这是被搜索引擎展示时对网页的描述 -->
    <meta name="description" content="阿智-前端学习笔记">
</head>
```

注意，`<meta>` 是单标签。

还能用来定时刷新页面（慎重使用）。例如：

```html
<head>
    <!-- 每30秒钟刷新当前页面 -->
    <meta http-equiv="refresh" content="30">

    <!-- 90 秒后重定向到 https://www.mozilla.org -->
    <meta http-equiv="refresh" content="90;url=https://www.mozilla.org">
</head>
```

在响应式布局中，经常要设置这样“视口”（viewport）元数据：

```html
<head>
    <!-- 视口宽度设为设备宽度，初始缩放比例为 1.0 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

## 文档标题（title）

`<title>` 元素定义文档的标题，显示在浏览器的标题栏或标签页上。它应该只包含文本。

前面讲的元数据相关标签都是单标签，而 `<title>` 是双标签，因为需要包含文字。例如：

```html
<head>
    <!-- 设置页面标题是必须的，也有利于 seo -->
    <title>阿智-前端学习笔记</title>
</head>
```



> 更新时间：{docsify-updated}