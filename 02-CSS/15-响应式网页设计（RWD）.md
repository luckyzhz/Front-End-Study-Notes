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









> 更新时间：{docsify-updated}