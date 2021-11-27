> 介绍引入 CSS 的三种方式。

为 HTML 文档引入 CSS 有 3 种方式：

* 内联（`style` 属性）
* 嵌入（`<style>` 标签）
* 链接（`<link>` 标签）

## 内联（`style` 属性）

可以利用标签的 `style` 属性为该标签单独添加样式。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="MWvRjWx" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/MWvRjWx">
  02-如何引入CSS_style</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

可以注意到，`style` 属性值的写法和前面提到的 CSS 的基本语法结构：

![CSS基本语法结构](../_images/CSS基本语法结构.png ':size=600')

实际上是一致的。

因为已经确定作用于哪个标签了，所以不需要 CSS 选择器（selector）。
依然是以冒号分隔属性和属性值，每条样式以分号结束。样式和样式间隔一个空格。

实际就是把多行样式放到一行，然后用引号括起来，作为 `style` 属性值。

一般不推荐使用这种方式引入 CSS。一是因为这破坏了 HTML 专职表达内容的习惯，
提高了耦合度；二是因为这样不利于样式代码的复用。

## 嵌入（`<style>` 标签）

第二种引入方式是利用 `<style>` 标签把 CSS 嵌入到当前网页。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="JjyVbjr" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/JjyVbjr">
  02-如何引入CSS_&lt;style&gt;</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

注意，我们把 `<style>` 标签放到了头部（`<head>`）。原因有二：

1. `<style>` 标签里的是样式表，并不是内容，所以不应该放到 `<body>` 里。
2. 浏览器渲染 HTML 文档时是从上到下读取内容的。如果没有读取样式就先读取到内容，
   那内容就先按照默认样式显示，等后面读取到样式了，才又调整回来。这显然是降低
   效率的行为。

所以我们要保持把 `<style>` 标签放到头部（`<head>`），利于浏览器逐步渲染。

## 链接（`<link>` 标签）

使用 `<link>` 标签引入 CSS 样式是最普遍的做法，也有利于样式代码复用。多
份 HTML 文档可以索引到同一份 CSS 文件。

我们可以把上面 `<style>` 标签里的内容复制到一份独立的文件，然后另存为
扩展名为 `.css` 的文件，例如 *main.css*。文件内容如下：

```CSS
p {
    color: red;
    background-color: blue;
}
```

然后再用 `<link>` 标签引入：

```HTML
<head>
    <link rel="stylesheet" href="main.css">
</head>

<body>
    <p>
        FireFox 就是火狐。
    </p>
</body>
```

注意 `<link>` 标签跟 `<style>` 一样要放到头部（`<head>`）。

把样式存放到单独的 CSS 文件还有一个好处，就是假如两份 HTML 文档索引到
同一份 CSS 文件，那么切换页面时就不需要再去请求 CSS 文件了。



> 更新时间：{docsify-updated}