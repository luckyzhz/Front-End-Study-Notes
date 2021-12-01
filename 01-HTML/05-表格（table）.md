> `<table>` 元素表示表格数据 — 即通过二维数据表表示的信息。

## 最基本的表格

<p class="codepen" data-height="450" data-default-tab="html,result" data-slug-hash="rNGaWVK" data-editable="true" data-user="luckyzhz" style="height: 450px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/rNGaWVK">
  05-表格（table）_1</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

可以看到：

1. 用 `<table>` 标签包裹整个表格。
2. 每一行（row）用 `<tr>` 标签定义。
3. 没有列（column）标签，列是隐含的。例如我们在一行里放了三个数据，那就隐含了有三列。
4. 放数据的单元格有两种，`<th>` 和 `<td>`：
    * `<th>` 表示 table header，即表头。一般浏览器会渲染为加粗字体。
    * `<td>` 表示 table data，即表格的一格数据。
5. 表格是二维数据表，浏览器不会默认加上边框。表格的样式，应通过 CSS 设置（在 CSS 章节会讲）。

表头（`<tr>`）不一定要放在一行里，也可以放在一列。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="abLzpbz" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/abLzpbz">
  05-表格（table）_2</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

我们把每一行的第一个数据设为 `<th>`，这样第一列就是表头了。

## 给表格添加标题（caption）

用 `<caption>` 标签设置表格标题。

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="LYzExpZ" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/LYzExpZ">
  05-表格（table）_3</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

注意 `<caption>` 应作为 `<table>` 的第一个子元素。

表格标题默认在表格上方，可以通过 CSS 的 `caption-side` 属性设置到下方。

## 数据跨越多格

通过 `<td>`，`<th>` 的 `rowspan`、`colspan` 属性来设置数据跨越多格，就像 excel 中的合并单元格。例如：

<!-- tabs:start -->

#### **跨越多列**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="OJxPWbv" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/OJxPWbv">
  05-表格（table）_4</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **跨越多行**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="xxXbgdV" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/xxXbgdV">
  05-表格（table）_5</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **跨越多列多行**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="MWEYJEN" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/MWEYJEN">
  05-表格（table）_6</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<!-- tabs:end -->

为了突出数据跨越多格的效果，上例中设置了基本的 CSS 样式。

> 不应该用 `<table>` 标签实现网页布局，`<table>` 标签表示的是数据结构。网页布局应通过 CSS 实现。



> 更新时间：{docsify-updated}