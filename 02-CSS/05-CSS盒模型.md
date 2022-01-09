> 在 CSS 中，所有元素都被一个个的“盒子”（box）包围着。

## 盒模型（box model）

CSS 标准盒模型由 4 部分组成：

* Content box: 这个区域用来显示内容，大小可通过 `width` 和 `height` 设置。
* Padding box: 包围在内容区域外部的空白区域，大小通过 `padding` 相关属性设置。
* Border box: 边框盒包裹内容和内边距。大小通过 `border` 相关属性设置。
* Margin box: 这是最外面的区域，是盒子和其他元素之间的空白区域。大小通过 `margin` 相关属性设置。

如图：

![CSS 盒模型](../_images/CSS_box.svg ':size=400')

注意，在标准模型中，`width` 和 `height` 设置的是 content box。整个盒子的大小还要加上 padding 和 border。

*（margin 不计入实际大小 —— 当然，它会影响盒子在页面所占空间，但是影响的是盒子外部空间。盒子的范围到边框为止 —— 不会延伸到margin。）*

例如：

```css
.box {
    width: 300px;
    height: 150;
    padding: 15px;
    border: 5px solid red;
    margin: 30px;
}
```

盒子实际宽 = 300 + 15 * 2 + 5 * 2 = 340px

盒子实际高 = 150 + 15 * 2 + 5 * 2 = 190px

有许多人认为要设置盒子的尺寸还要这样计算很麻烦，于是有了“替代盒模型”。这个模型，宽高都是可见宽高，包含到 border。

现代浏览器默认使用标准模型。如果需要使用替代模型，可以通过设置 `box-sizing: border-box;` 来实现。 这样就可以告诉浏览器使用 `border-box` 来定义区域。

如果希望所有元素都使用替代模型，可以设置 `<html>` 元素的 `box-sizing`，然后设置所有元素都继承该属性。代码如下：

```css
html {
  box-sizing: border-box;
}
*, *::before, *::after {
  box-sizing: inherit;
}
```

*注意，当两个元素靠在一起时，他们的 margin 会重叠。所以两个盒子的距离，由较大的 margin 决定。这称为 margin 坍缩。*

## 块级盒子（block box）

一个被定义成块级的（block）盒子会表现出以下行为:

* 盒子会在内联的方向上扩展并占据父容器在该方向上的所有可用空间，在绝大数情况下意味着盒子会和父容器一样宽。
* 每个盒子都会换行。
* `width` 和 `height` 属性可以发挥作用。
* 内边距（padding）、外边距（margin）、边框（border）会将其他元素从当前盒子周围“推开”。

常见的块级盒子：`<div>`，标题（`<h1>` ~ `<h6>`）,`<p>`

margin 可以是负值，如下例：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="gOxJMmp" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/gOxJMmp">
  05-CSS盒模型_block_box</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

另外我们还注意到，可以单独设置某一边的 margin，例如 `margin-top: -40px;`。

border、padding 同样可以只设置某一边，例如 `border-left: red solid 2px;`、`padding-right: 1em;`。

我们还可以使用最细粒度的属性，例如 `border-right-width`:

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="MWvdeqX" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/MWvdeqX">
  05-CSS盒模型_border</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

注意，*细粒度属性* 要放在 *粗粒度属性* 之后，不然就被 *粗粒度属性* 覆盖了。例如 `border-right` 就应放在 `border` 之后。

border 的属性：

* `border-width`：边框宽度
* `border-style`：边框样式
* `border-color`：边框颜色
* `border-radius`：边框圆角半径

## 内联盒子（inline box）

如果一个盒子对外显示为 inline，那么他的行为如下:

* 盒子不会产生换行。
* width 和 height 属性将*不起*作用。
* 垂直方向的 padding、margin、border 会被应用但是不会把其他处于 inline 状态的盒子推开。
* 水平方向的 padding、margin、border 会被应用且会把其他处于 inline 状态的盒子推开。

常见的内联盒子：`<a>`，`<span>`，`<em>`

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="ExvzyrM" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/ExvzyrM">
  05-CSS盒模型_inline_box</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

*块级和内联布局是 web 上默认的行为，有时候被称为正常文档流。*

## 行内块盒子（inline-block）

如果不希望一个元素切换到新行，但希望它可以设定宽度和高度，可以设置 `display: inline-block;`。

行内块盒子（inline-block）特点：

* `width` 和 `height` 属性会生效。
* padding，margin，border 会推开其他元素。
* 不会跳转到新行。

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="abyrZrr" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/abyrZrr">
  05-CSS盒模型_inline-block</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>



> 更新时间：{docsify-updated}