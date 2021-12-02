> 设置表格样式的常用属性。

## 表格边框

通过 `border`，`border-collapse`，`border-spacing` 属性设置表格边框。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="LYzVdxp" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/LYzVdxp">
  Untitled</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

对于单独一个表格单元（`<th>`，`<td>`），我们无法设置 `margin` 属性。如果想增加单元格间距，应对 `<table>` 使用 `border-spacing` 属性。

## 表格标题位置

通过 `caption-side` 属性设置表格标题位置。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="LYzVdXb" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/LYzVdXb">
  11-表格（table）样式_caption-side</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 表格示例

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="XWebEwm" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/XWebEwm">
  11-表格（table）样式_example</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

其中一个比较重要的技巧是利用伪元素间隔地添加背景色。



> 更新时间：{docsify-updated}