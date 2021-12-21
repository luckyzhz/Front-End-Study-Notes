> 简单介绍 flex items 相关属性。

上一节介绍的是 flexbox 的属性，本节介绍 flex 项目（flex items）的属性。

## 顺序（order）

可以用 order 属性来改变 flex 项目的显示顺序。order 属性的值是整数，默认是 0，可以是负数，值越小则越显示在前面。

*注意，order 仅仅对元素的视觉顺序（visual order）产生作用，并不会影响元素的逻辑或 tab 顺序。*

例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="ExwvbPd" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/ExwvbPd">
  17-网页布局-flexbox-2_order</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## flexbox 剩余空间的分配（flex-grow）

`flex-grow` 属性决定了 flexbox 剩余空间的分配，默认值为 0。

例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="JjryOWV" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/JjryOWV">
  17-网页布局-flexbox-2_flex-grow</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## flex 项目的收缩规则（flex-shrink）

`flex-shrink` 属性指定了 flex 项目的收缩规则。flex 项目仅在默认宽度之和大于容器时才会发生收缩，其收缩的大小依据 `flex-shrink` 的值。

* `flex-shrink` 初始值为 1，取值可以是 0，也可以是小数，不可以是负数。
* flex 项目的 `flex-shrink` 值越大，则在需要收缩时，收缩的比例越大。

例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="vYeJpEx" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/vYeJpEx">
  17-网页布局-flexbox-2_flex-shrink</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## flex 项目的初始大小（flex-basis）

`flex-basis` 指定了 flex 项目在主轴方向上的初始大小。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="bGorLVP" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/bGorLVP">
  17-网页布局-flexbox-2_flex-basis</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 简写属性 flex

`flex-grow`，`flex-shrink`，`flex-basis` 三个属性可简写为 `flex` 属性。

具体可参考：<https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex>

## 单个项目的对齐（align-self）

`align-self` 指定单个项目的对齐，并覆盖 flexbox 的 align-items 的值。例如：

<p class="codepen" data-height="400" data-default-tab="html,result" data-slug-hash="qBPXojG" data-editable="true" data-user="luckyzhz" style="height: 400px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/qBPXojG">
  17-网页布局-flexbox-2_align-self</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>



> 更新时间：{docsify-updated}