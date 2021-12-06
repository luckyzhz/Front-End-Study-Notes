> 介绍如何用 float 实现经典网页布局。

下图所示是一种经典的网页布局，由 5 部分组成：`头部（header）`，`导航栏（nav）`，`主体（main）`，`侧边栏（aside）`，`脚部（footer）`。

![网页经典布局](../_images/网页经典布局.svg ':size=600')

下面介绍如何用 `float` 属性实现这个布局。

## 语义化的 HTML

传统上，是利用 `<div>` 元素和 `class` 属性实现网页分区，例如 `<div class="header"`>。这里，我们使用最新的语义化标签，这样既能更好地体现 HTML 文档结构，又有利于 SEO。

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>网页经典布局</title>
    <link rel="stylesheet" href="网页经典布局.css">
</head>

<body>
    <!-- 网页头部 -->
    <header>
        <h1>网页经典布局</h1>
    </header>

    <!-- 导航栏 -->
    <nav>
        <a href="#">链接 1</a>
        <a href="#">链接 2</a>
        <a href="#">链接 3</a>
        <a href="#">链接 4</a>
    </nav>

    <!-- float 属性把一个元素浮动到**所在容器**的左侧或右侧。
    所以用一个容器把网页中间部分（<main> 和 <aside>）包裹起来，
    避免中间部分浮动到别处和其他元素重叠 -->
    <div class="container">
        <main>
            <!-- 网页主体部分一般包含多篇文章 -->
            <article>
                <h2>文章标题</h2>
                <h5>文章描述，例如作者、日期</h5>
                <div class="imgbox">图片</div>
                <p>一些文本……</p>
                <p>
                    汉阳大学（韩语：한양대학교／漢陽大學校），简称汉大（韩语：한대／漢大），
                    位于大韩民国首都首尔市，是一所创建于1939年的私立综合型大学。主校区位于
                    首尔城东区杏堂洞（행당동），另有位于京畿道安山市的校舍。
                </p>
            </article>
            <!-- 第二篇文章 -->
            <article>
                <h2>文章标题</h2>
                <h5>文章描述，例如作者、日期</h5>
                <div class="imgbox">图片</div>
                <p>一些文本……</p>
                <p>
                    汉阳大学（韩语：한양대학교／漢陽大學校），简称汉大（韩语：한대／漢大），
                    位于大韩民国首都首尔市，是一所创建于1939年的私立综合型大学。主校区位于
                    首尔城东区杏堂洞（행당동），另有位于京畿道安山市的校舍。
                </p>
            </article>
            <!-- 第三篇文章 -->
            <article>
                <h2>文章标题</h2>
                <h5>文章描述，例如作者、日期</h5>
                <div class="imgbox">图片</div>
                <p>一些文本……</p>
                <p>
                    汉阳大学（韩语：한양대학교／漢陽大學校），简称汉大（韩语：한대／漢大），
                    位于大韩民国首都首尔市，是一所创建于1939年的私立综合型大学。主校区位于
                    首尔城东区杏堂洞（행당동），另有位于京畿道安山市的校舍。
                </p>
            </article>
        </main>

        <aside>
            <!-- 侧边栏往往有多个卡片 -->
            <section>
                <h3>关于我</h3>
                <div class="imgbox">图片</div>
                <p>一些关于我的文本……</p>
            </section>
            <!-- 第二个卡片 -->
            <section>
                <h3>热门帖子</h3>
                <div class="imgbox">图片</div>
                <div class="imgbox">图片</div>
                <div class="imgbox">图片</div>
            </section>
            <!-- 第三个卡片 -->
            <section>
                <h3>关注我</h3>
                <p>一些文本……</p>
            </section>
        </aside>
    </div>

    <!-- 网页脚部 -->
    <footer>
        <h2>脚部。可以放置版权声明、日期等信息。</h2>
    </footer>
</body>

</html>
```

## CSS 部分

```css
/* ------------ 网页整体设置 ------------ */

/* 首先把盒模型设为 border-box，避免溢出 */
html {
    box-sizing: border-box;
}

*, *::before, *::after {
    box-sizing: inherit;
}

body {
    /* margin 设为 0，从而可以让背景色铺满整个网页 */
    margin: 0;
    background: #f1f1f1;
    /* 让网页各区块和浏览器边界有空隙 */
    padding: 1rem;
    font-family: sans-serif;
}

/* ------------ 头部 ------------ */

header {
    padding: 2.4rem;
    text-align: center;
    background-color: white;
}

header>h1 {
    margin: 0;
    font-size: 3rem;
}

/* ------------ 导航栏 ------------ */

/* 导航栏 */
nav {
    background-color: #333;
    margin-top: 0.5rem;
}

/* 因为 <nav> 的子元素都 float 了，
因此必须利用 ::after 伪元素来撑起 <nav> 盒子，
不然盒子高度就坍缩为 0 了 */
nav::after {
    content: "";
    display: block;
    clear: both;
}

/* 导航栏里的链接 */
nav>a {
    display: block;
    float: left;
    padding: 0.8rem 1.2rem;
    color: white;
    text-align: center;
    text-decoration: none;
}

/* 导航栏从第二个 <a> 元素开始，每个都添加左边框，实现链接的隔离 */
nav>a:nth-child(n+2) {
    border-left: dashed 1px white;
}

/* 把最后一个链接放到右边，让导航栏更均衡 */
nav>a:last-child {
    float: right;
}

/* 当鼠标悬浮在导航栏上的链接时，应该让链接变色 */
nav>a:hover {
    background-color: #ddd;
    color: black;
}

/* ------------ 中间部分 ------------ */

/* 因为 .container 的子元素都 float 了，
因此必须利用 ::after 伪元素来撑起 .container 盒子，
不然盒子高度就坍缩为 0 了 */
.container::after {
    content: "";
    display: block;
    clear: both;
}

/* ------------ main 部分 ------------ */

.container>main {
    width: 75%;
    float: left;
}

/* ------------ aside 部分 ------------ */

.container>aside {
    width: 25%;
    float: left;
    /* 和 main 部分留有空隙 */
    padding-left: 1rem;
}

/* ------------ 卡片效果 ------------ */

/* 给文章和侧边栏的区块添加卡片效果 */
main>article, aside>section {
    background-color: white;
    padding: 1rem;
    margin-top: 1rem;
    box-shadow: 0.3rem 0.3rem 0.3rem gray;
}

/* 文章卡片里的图片盒，侧边栏卡片里的图片盒 */
div.imgbox {
    margin-top: 0.5rem;
    background-color: #aaa;
    width: 100%;
    height: 12rem;
}

/* ------------ 脚部 ------------ */

footer {
    margin-top: 1rem;
    padding: 1.2rem;
    text-align: center;
    background-color: #ddd;
}

footer>h2 {
    margin: 0;
    font-size: 1.5rem;
}
```

关于 float 的坍缩，可参考：<a href="#/02-CSS/08-浮动（float）?id=clear-技巧" target="_blank">clear 技巧</a>

## 最终效果

最终效果可以通过这个链接查看：[网页经典布局](_media/网页经典布局.html ':ignore')



> 更新时间：{docsify-updated}