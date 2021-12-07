> 简单介绍响应式网页设计。

我们知道，电脑、平板、手机的屏幕尺寸各不相同，这就导致为某一种屏幕尺寸设计的网页，到了另一种屏幕尺寸，可能会显得很别扭，甚至无法阅读。于是就有人提出了响应式网页设计的概念，希望网页能根据屏幕尺寸自动调整布局或展示方式，从而实现跨设备的友好体验。

响应式网页设计（responsive web design，RWD），指的是**一组允许网页改变其布局和外观以适应不同屏幕宽度、分辨率等的做法**。

## 媒体查询（media queries）

要进行响应式设计，首先要能探知设备状况。CSS 媒体查询提供了一种仅当浏览器和设备环境 ***匹配指定的规则*** 时才应用 CSS 的方法。

最简单的媒体查询语法：

```css
@media 媒体类型 and (媒体特征规则) {
  /* 一系列 CSS 规则 */
}
```

**媒体类型** 有：

* `all`，指所有媒体类型。
* `print`，打印媒体。
* `screen`，屏幕。这是设计时使用最多的媒体类型。
* `speech`，朗读器。

例如在页面被打印时把字号设为 12pt：

```css
@media print {
  body {
    font-size: 12pt;
  }
}
```

媒体类型是可选的，如果没有在媒体查询中指示一个媒体类型的话，那么媒体查询默认会设为用于全部媒体类型。

最常用的 **媒体特征** 有：

* `min-width`，最小视口宽度。
  * 例如，`min-width: 600px`，意味着当视口宽度大于或等于 600px 时，对应的 CSS 规则会应用。
* `max-width`，最大视口宽度。
  * 例如，`max-width: 768px`，意味着当视口宽度小于或等于 768px 时，对应的 CSS 规则会应用。
* `orientation`，方向。
  * 例如，`orientation: portrait`，值视口处于纵向，即高度大于或等于宽度。
  * 例如，`orientation: landscape`，值视口处于横向，即宽度大于高度。

更多媒体特征可参考：<https://developer.mozilla.org/zh-CN/docs/Web/CSS/Media_Queries/Using_media_queries>

媒体查询中的 `与`，`或`，`非`：

```css
/* and 表示逻辑与。
在视口至少为 400px，且设备横放时，文本变为蓝色。 */
@media screen and (min-width: 400px) and (orientation: landscape) {
  body {
    color: blue;
  }
}
```

```css
/* 用逗号隔开查询条件，表示逻辑或。
在 （视口宽至少 400px） 或者 （设备处于横放状态） 时，文本变为蓝色 */
@media screen and (min-width: 400px), screen and (orientation: landscape) {
  body {
    color: blue;
  }
}
```

```css
/* not 表示逻辑非。
在设备非横向（即竖向）时，文本变为蓝色*/
@media not all and (orientation: landscape) {
  body {
    color: blue;
  }
}
```

## 如何选择断点

所谓断点，就是设备判断的临界值。例如 `min-width: 600px`，这里 600px 就是一个断点。如今各种设备层出不穷，我们如何确定断点呢？一个简单的原则是：

* 从你需要适配的 ***最小屏幕宽度*** 开始，慢慢拉伸，当你发现页面像坨屎的时候，一个新的断点就确定了。

## 移动优先

为什么要移动优先？

在最小的那个设备上的视图很多时候都是一个**简单的单列内容**，这意味着，很可能不需要为小设备做多少布局设计，默认情况下就能得到可读的布局。

从简单的切入点开始，然后慢慢添加功能，这符合开发规律。另外，如果我们把对应不同设备的 CSS 规则存储到不同文件，那小屏设备需要加载的 CSS 文件很可能小许多，这样有利于提高页面加载速度。

## 改造网页为响应式

上一节 [14-网页布局-float](02-CSS/14-网页布局-float) 的实例是非响应式的，我们可以进一步将其改造为响应式网页。

改造后的预览效果可以通过这个链接查看：[响应式网页设计](_media/响应式网页设计.html ':ignore')

试着改变浏览器窗口宽度，来感受响应式网页设计的魅力。

下面具体介绍如何改造。

### HTML 的改变

先考察 HTML 作了哪些改动。

#### HTML `<head>` 的改变

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>响应式网页设计</title>

    <!-- 移动端和桌面端共有的样式 -->
    <link rel="stylesheet" href="响应式网页设计-main.css">
    <!-- 视口宽度小于或等于 768px 时添加移动端样式 -->
    <link rel="stylesheet" href="响应式网页设计-mobile.css" media="screen and (max-width: 768px)">
    <!-- 视口宽度大于 768px 时添加桌面端样式 -->
    <link rel="stylesheet" href="响应式网页设计-desktop.css" media="not screen and (max-width: 768px)">
</head>
```

我们首先注意到这个元数据：

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

这个元标签告诉移动端浏览器，它们应该将视口宽度设定为设备的宽度，将文档放大到其预期大小的100%，在移动端以你所希望的为移动优化的大小展示文档。

为何需要这个？因为移动端浏览器倾向于在它们的视口宽度上说谎。

这个元标签的存在，是由于原来iPhone发布以后，人们开始在小的手机屏幕上阅览网页，而大多数站点未对移动端做优化的缘故。移动端浏览器因此会把视口宽度设为960像素，并以这个宽度渲染页面，结果展示的是桌面布局的缩放版本。其他的移动端浏览器（例如谷歌安卓上的）也是这么做的。用户可以在站点中放大、移动，查看他们感兴趣的那部分，但是这看起来很不舒服。如果你不幸遇到了一个没有响应式设计的网站，今天你还会看到这种情况。

麻烦的是，你的带断点和媒介查询的响应式设计不会在移动端浏览器上像预期那样工作。如果你有个窄屏布局，在480像素及以下的视口宽度下生效，但是视口是按960像素设定的，你将不会在移动端看到你的窄屏布局。通过设定width=device-width，你用设备的实际宽度覆写了苹果默认的width=960px，然后你的媒介查询就会像预期那样生效。

***所以你应该在你的文档头部总是包含上面那行 HTML。***

然后我们引入了三个 CSS，分别是：

* `响应式网页设计-main.css`，这是移动端和桌面端共有的样式。
* `响应式网页设计-mobile.css`，这是移动端特有的样式。
  * 注意这里使用了媒体查询 `media="screen and (max-width: 768px)"`。
* `响应式网页设计-desktop.css`，这是桌面端特有的样式。
  * 注意这里使用了媒体查询 `media="not screen and (max-width: 768px)"`。

这里可以得到的经验是：

1. 我们不一定要在 CSS 文件里使用媒体查询，可以在链入 CSS 文件时再使用媒体查询。
2. 如果移动端和桌面端样式差异较大，我们可以把 CSS 拆分成共有的部分，和各客户端各自对应的部分。这样可以避免样式混杂在一起，有利于代码维护。

#### HTML `<body>` 的改变

为了实现移动端导航栏的动态效果，我们在 `<header>` 和 `<nav>` 之间添加了以下代码：

```html
<!-- 利用 checkbox 的开关状态来对应导航栏开关状态。
这部分只在移动端显示。 -->
<input type="checkbox" id="nav-switch">
<label for="nav-switch">
    <img id="show-nav" src="../_logo/remixicon/menu-line.svg">
    <img id="hide-nav" src="../_logo/remixicon/close-line.svg">
    <div id="hide-nav-overlay"></div>
</label>
```

为了控制导航栏的显示与否，必须有一个量来记录导航栏的显示状态。比较常规的做法是利用 JavaScript，直接设置一个量来记录显示状态（例如 0 代表关闭，1 代表开启）。

但是在本例中，我们巧妙地利用了复选框 `<input type="checkbox">` 来记录导航栏的显示状态，因为复选框恰好有选中和不选中两种状态。

那为什么要把这部分代码放在 `<header>` 和 `<nav>` 之间呢？因为，**CSS 没有父选择器**，所以我们把 `<input type="checkbox">` 作为 `<nav>` 的兄弟，以便后面可以通过 `<input type="checkbox">` 的伪类（即状态）选择到 `<nav>`，从而设置复选框特定状态下 `<nav>` 的样式。所以，我们不能把这部分代码用 `<div>` 包起来。

另外，为了让移动端导航栏更美观，我们在 `<nav>` 里添加了 logo：

```html
<a href="#"><img alt="logo" src="../_logo/zhi-logo.svg"></a>
```

### CSS 的改变

移动端和桌面端的差异：

1. 导航栏。
   * 移动端的导航栏被抽离出文档流，形成了一个动态的侧面板。
2. 中间部分（文章和侧边栏）。
   * 移动端对于中间部分只需要简单流动下来即可，而桌面端需要文章和侧边栏浮动并列。

除此以外，其他部分的样式都是共享的。

#### 共享的样式（`响应式网页设计-main.css`）

共享样式主要是添加了 CSS 动画过渡时间的继承：

```css
/* 首先把盒模型设为 border-box，避免溢出。
另外也设置动画过渡时长，使动画速度统一 */
html {
    box-sizing: border-box;
    transition: all 0.5s;
}

*, *::before, *::after {
    box-sizing: inherit;
    transition: inherit;
}
```

#### 移动端特有的样式（`响应式网页设计-mobile.css`）

移动端特有的样式主要是是实现导航栏侧面板的动态效果：

```css
/* ------------ 导航栏 ------------ */

nav {
    /* 导航栏通高固定定位 */
    position: fixed;
    width: 75%;
    height: 100%;
    top: 0;
    /* 一开始是隐藏的。隐藏的时候利用 left 属性定位，
    则后面出现的时候同样要用 left 属性定位，才能实现动画。
    可以理解为两个关键帧。 */
    left: -75%;
    background-color: rgba(255, 255, 255, 0.95);
    text-align: center;
}

/* 导航栏里的链接 */
nav>a:nth-child(n + 2) {
    display: block;
    width: 100%;
    margin-top: 0.2rem;
    padding: 1.2rem;
    background-color: #333;
    color: white;
    text-decoration: none;
}

/* 当鼠标悬浮在导航栏上的链接时，应该让链接变色 */
nav>a:nth-child(n + 2):hover {
    background-color: #ddd;
    color: black;
}

nav img[alt="logo"] {
    width: 3rem;
    margin: 1rem;
}

/* ------------ 导航栏开关图标 ------------ */

/* 复选框不需要显示，只是用来记录开关状态 */
input#nav-switch {
    display: none;
}

/* 开关图标的共同样式 */
label[for="nav-switch"]>img {
    display: inline-block;
    padding: 0.5rem;
    width: 2rem;
}

/* 当鼠标悬浮在开关图标时，应该让开关图标变色 */
label[for="nav-switch"]>img:hover {
    background-color: gray;
    /* 把图标颜色反转 */
    filter: invert(100%);
}

/* ≡ 图标，用于打开导航栏 */
#show-nav {
    /* 这里 position 设为 absolute 而非 fixed，
    则 ≡ 图标会随着滚动离开视口，避免挡住文章。 */
    position: absolute;
    top: 2rem;
    left: 2rem;
}

/* X 图标，用于关闭导航栏 */
#hide-nav {
    position: fixed;
    /* 设置 z-index，让 X 图标在导航栏上层 */
    z-index: 1;
    top: 1rem;
    /* 一开始是隐藏的 */
    right: calc(100% + 1rem);
}

/* 遮罩层，用于关闭导航栏 */
#hide-nav-overlay {
    position: fixed;
    width: 25%;
    height: 100%;
    top: 0;
    /* 一开始是隐藏的 */
    right: -25%;
    background-color: rgba(0, 0, 0, 0.5);
}

/* ------------ input#nav-switch:checked 时，导航栏开启 ------------ */

/* 导航栏出现 */
input#nav-switch:checked~nav {
    left: 0;
}

/* X 图标出现 */
input#nav-switch:checked~label[for="nav-switch"]>#hide-nav {
    right: calc(25% + 1rem);
}

/* 遮罩层出现 */
input#nav-switch:checked~label[for="nav-switch"]>#hide-nav-overlay {
    right: 0;
}
```

#### 桌面端特有的样式（`响应式网页设计-desktop.css`）

桌面端特有的样式主要是处理导航栏和中间部分的浮动：

```css
/* ------------ 不需要导航栏开关图标 ------------ */

input#nav-switch, label[for="nav-switch"] {
    display: none;
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

/* 不显示logo */
nav>a:first-child {
    display: none;
}

/* 导航栏里的链接 */
nav>a:nth-child(n+2) {
    display: block;
    float: left;
    padding: 0.8rem 1.2rem;
    color: white;
    text-align: center;
    text-decoration: none;
}

/* 导航栏从第 3 个 <a> 元素开始，每个都添加左边框，实现链接的隔离 */
nav>a:nth-child(n+3) {
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
```



> 更新时间：{docsify-updated}