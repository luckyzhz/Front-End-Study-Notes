> 浮动（float）的元素会脱离正常文档流。

## 浮动（float）基本概念

可以用 `float` 属性把一个元素浮动到**所在容器**的左侧或右侧。此时，浮动的元素会脱离正常文档流。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="jOGNzyN" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/jOGNzyN">
  08-浮动（float）_1</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

我们可以看到浮动的特点：

1. 在浮动元素之前还是正常的文档流，例如这里的 `<h1>`。
2. 浮动元素会脱离正常的文档流，后面的元素会递补上来。
3. 后面递补上来的元素的 **border** 不会意识到有浮动元素；
4. 但是**行内元素**会尊重浮动元素的边界，所以这段文字会围绕浮动元素。
5. 通常得给浮动元素设置 `width`。
6. 行内元素也可以浮动，例如 `<img>`。

`float` 属性的取值：

1. `none`
   * 默认值，表明元素不进行浮动。
2. `left`
   * 表明元素浮动在其所在的块容器左侧。
3. `right`
   * 表明元素浮动在其所在的块容器右侧。
4. `inline-start`
   * 表明元素浮动在其所在块容器的开始一侧。
5. `inline-end`
   * 表明元素浮动在其所在块容器的结束一侧。

## 多个浮动元素

当一个元素浮动之后，它会被移出正常的文档流，然后向左或者向右平移，一直平移直到碰到了所处容器的**边框**，或者碰到**另外一个浮动的元素**。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="RwLbMEE" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/RwLbMEE">
  08-浮动（float）_2</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

当多个浮动元素一行放不下时，就会换行继续放置。

## 清除浮动

有时我们可能希望某个元素不要被浮动元素重叠到，此时可以使用 `clear` 属性。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="jOGNxEM" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/jOGNxEM">
  08-浮动（float）_3</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

`clear` 属性的取值有：

1. `none`
   * 默认值，不清除之前的浮动。
2. `left`
   * 元素被向下移动用于清除之前的左浮动。。
3. `right`
   * 元素被向下移动用于清除之前的右浮动。
4. `both`
   * 元素被向下移动用于清除之前的左右浮动。
5. `inline-start`
   * 元素被向下移动以清除其包含块的起始侧上的浮动。
6. `inline-end`
   * 元素被向下移动以清除其包含块的结束侧上的浮动。

## `clear` 技巧

如果一个元素里只有浮动元素，那它的高度会是 0，因为没有正常文档流撑起高度。为了使这个元素自适应包含其内部的所有浮动元素，我们可以利用其 `::after` 伪元素。

*（`::after` **创建**一个伪元素，作为已选中元素的**最后一个子元素**）*

<!-- tabs:start -->

#### **高度为 0**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="oNGvdpO" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/oNGvdpO">
  08-浮动（float）_4</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **高度为自适应**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="MWEgGXQ" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/MWEgGXQ">
  08-浮动（float）_5</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<!-- tabs:end -->



> 更新时间：{docsify-updated}