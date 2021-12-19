> 简单介绍 flexbox 布局。

flexbox（Flexible Box 模型的简称）是一种一维的布局模型，一次只能处理一个维度上的元素布局，一行或者一列。

## flexbox 初体验

先直观看一下 flexbox 的效果：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="KKXqNoq" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/KKXqNoq">
  16-网页布局-flexbox_1</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

通常会使用一个 `<div>` 元素作为 flex 容器（flex container）。当把容器设为 `display: flex;` 或 `display: inline-flex;` （后面会解释这两种的区别），容器中的直系子元素（既儿子）就会变为 flex 项目（flex item）。

## flexbox 的轴

flexbox 有两根轴，主轴（main axis）和交叉轴（cross axis）。主轴由属性 `flex-direction` 定义，交叉轴垂直于主轴。

主轴由 `flex-direction` 定义，可以取 4 个值：

1. `flex-direction: row;`，默认值，主轴沿着行方向伸展。
2. `flex-direction: row-reverse;`，主轴沿着行的**反**方向伸展。
3. `flex-direction: column;`，主轴沿着列方向伸展。
4. `flex-direction: column-reverse;`，主轴沿着列的**反**方向伸展。

例如：

<!-- tabs:start -->

#### **row**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="gOGRgNv" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/gOGRgNv">
  16-网页布局-flexbox_2.1</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **row-reverse**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="ZEXyLdg" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/ZEXyLdg">
  16-网页布局-flexbox_2.1</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **column**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="BawZpXV" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/BawZpXV">
  16-网页布局-flexbox_2.2</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **column-reverse**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="jOGwygd" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/jOGwygd">
  16-网页布局-flexbox_2.3</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<!-- tabs:end -->

默认情况下，flex 项目会在交叉轴方向被拉伸，来填充交叉轴方向的空间。也就是说，如果一个 flex 项目比其他 flex 项目高，而我们又没有定义其他 flex 项目的高度，那么其他 flex 项目会沿交叉轴方向被拉伸来填满充交叉轴方向的空间。

## 多行 flex 容器

虽然 flexbox 是一维模型，但可以通过 `flex-wrap` 属性使 flex 项目应用到多行中（即换行）。在这样做的时候，**要把每一行看作一个新的 flex 容器**。任何空间分布都将在该行上发生，而不影响该空间分布的其他行。

`flex-wrap` 的取值：

1. `flex-wrap: nowrap;`
   * 默认值，flex 项目被摆放到到一行，这可能导致溢出 flex 容器。
2. `flex-wrap: wrap;`
   * 当一行放不下时，flex 项目会被打断到多个行中。
3. `flex-wrap: wrap-reverse;`
   * 和 `wrap` 的行为一样，但是 cross-start 和 cross-end 互换。

例如：

<!-- tabs:start -->

#### **nowrap**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="XWegMOM" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/XWegMOM">
  16-网页布局-flexbox_3.2</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **wrap**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="xxXrqJL" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/xxXrqJL">
  16-网页布局-flexbox_3</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **wrap-reverse**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="dyVRvae" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/dyVRvae">
  16-网页布局-flexbox_3.1</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<!-- tabs:end -->

可以看到，当 flex 容器设为 `flex-wrap: nowrap;`，如果一行中有太多 flex 项目，flex 容器会压缩这些 flex 项目，尽量在一行里放进这些 flex 项目。如果一行实在放不下，则会发生溢出。

## 简写属性 `flex-flow`

`flex-direction` 和 `flex-wrap` 可组合为简写属性 `flex-flow`。例如 `flex-flow: column wrap;`。

## 沿主轴方向的对齐（justify-content）

`justify-content` 属性用来设置项目沿主轴方向的分布。

`justify-content` 的属性很多，具体可参考：<https://developer.mozilla.org/zh-CN/docs/Web/CSS/justify-content>

这里示例比较常用的：

<!-- tabs:start -->

#### **start**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="QWqgvad" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/QWqgvad">
  16-网页布局-flexbox_4.1</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **end**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="ZEXyKov" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/ZEXyKov">
  16-网页布局-flexbox_4.1</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **center**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="OJxgmEM" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/OJxgmEM">
  16-网页布局-flexbox_4.2</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **space-between**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="MWEomBO" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/MWEomBO">
  16-网页布局-flexbox_4.3</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **space-around**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="QWqgvVv" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/QWqgvVv">
  16-网页布局-flexbox_4.4</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **space-evenly**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="qBPjmMg" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/qBPjmMg">
  16-网页布局-flexbox_4.5</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<!-- tabs:end -->






> 更新时间：{docsify-updated}