> `position` 属性用于指定一个元素在文档中的定位方式。

CSS `position` 属性用于指定一个元素在文档中的**定位方式**。`top`，`right`，`bottom` 和 `left` 属性则决定了该元素的偏移量。

`position` 属性的默认值是 `static`，也就是正常的布局行为。下面介绍特殊的定位。

## 相对定位（relative）

`position: relative;` 表示相对定位。相对定位的元素依然会在正常文档流占有位置。

所谓“相对”，是指偏离于原来在正常文档流中应处的位置。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="VwMZgdP" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/VwMZgdP">
  09-定位（position）_relative</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

可以看到，第二个盒子依然占有原来的位置，偏移量是相对原来位置的。

另外注意，`top`，`right`，`bottom` 和 `left` 属性值可以是负数，意味着向相反方向偏移。

## 绝对定位（absolute）

`position: absolute;` 表示相对定位。绝对定位的元素会被完全移出正常文档流，并且不为元素预留空间。也就是说，对于正常文档流来说，绝对定位的元素相当于不存在。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="dyVbrZd" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/dyVbrZd">
  09-定位（position）_absolute</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

绝对定位元素相对于最近的**非 static 祖先元素**定位。当这样的祖先元素不存在时，则相对于 ICB（initial containing block，初始包含块）。

通常我们把被参照的元素设为 `position: relative;`。

当有多个绝对定位元素时，我们可以用 `z-index` 属性来调整他们哪个在上层，哪个在下层。

`z-index` 属性值可以是 `auto` 或整数，数值越大越在上层。

## 固定定位（fixed）

`position: fixed;` 表示固定定位。固定定位的元素会被完全移出正常文档流，并且不为元素预留空间。同样，对于正常文档流来说，固定定位的元素相当于不存在。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="XWerQQx" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/XWerQQx">
  09-定位（position）_fixed</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

固定定位是相对于视口（view port）的，当滚动屏幕时仍固定在相同位置。

## 粘性定位（sticky）

`position: sticky;` 表示粘性定位。粘性定位可以被认为是**相对定位**和**固定定位**的混合。

元素在超过**特定阈值**前为相对定位，之后为固定定位，直到它到达其父元素的边界（也就是说，父容器的边界可以把粘性定位的元素推出可视区域）。

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="JjrPgxz" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/JjrPgxz">
  09-定位（position）_sticky</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

上例中，在粘性定位元素和其父元素的上边界距离 1em 之前，元素为相对定位；之后，元素将固定在与父元素的上边界距离 1em 的位置。

须指定 `top`, `right`, `bottom` 或 `left` 四个阈值其中之一，才可使粘性定位生效。否则其行为与相对定位相同。

粘性定位的一种典型应用场景如下：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="vYeYBLG" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/vYeYBLG">
  09-定位（position）_sticky_2</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

需要特别注意的是，每个 `<dt>` 都归属于单独的 `<dl>`。

也就是说，上例中**每个粘性定位元素都有独属的父元素**。

这样做是为了，当描述列表离开可视区域时，其内部的粘性定位元素能被描述列表的下边界推出可视区域，从而避免多个粘性定位的 `<dt>` 重叠。*（为了展示这个特点，特地给每个描述列表加了边框）*



> 更新时间：{docsify-updated}