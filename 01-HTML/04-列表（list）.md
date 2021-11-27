> 介绍 3 种列表。

## 有序列表（ordered list）

`<ol>` 标签表示有序列表（ordered list），渲染为一个带编号的列表。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="xxLBoRe" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/xxLBoRe">
  ref_01-HTML_04-列表（list）_&lt;ol&gt;</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

被嵌套的 `<li>` 标签表示列表条目（list item）。

可以通过 `start` 属性指定列表编号的起始值。用 `reversed` 属性让列表编号倒序。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="qBXvzRz" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/qBXvzRz">
  ref_01-HTML_04-列表（list）_&lt;ol&gt;_2</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

注意 `reversed` 属性不需要值，这个属性存在就表示要倒序。另外，可以使用 CSS 的 `list-style-type` 属性设置编号的类型，例如设为字母或罗马数字等，待到 CSS 章节再讲。

## 无序列表（unordered list）

`<ul>` 标签表示无序列表（unordered list）。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="dyzrBzP" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/dyzrBzP">
  ref_01-HTML_04-列表（list）_&lt;ul&gt;</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

可以看到，无序列表同样使用 `<li>` 标签作为条目。条目前的标记同样可以通过 CSS 的 `list-style-type` 属性设置，甚至可以用自定义图片作为条目标记。

## 描述列表（description list）

有时我们需要为列表条目附上说明，这时可以使用描述列表（description list）。标签是 `<dl>`。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="bGrZPrr" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/bGrZPrr">
  ref_01-HTML_04-列表（list）_&lt;dl&gt;</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

`<dt>` 表示描述列表术语（description list term）。`<dd>` 表示描述列表中的描述（description list description）。一条术语可以对应多个描述，也可以多条术语对应一个描述，当然也可以多对多。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="JjyzQyQ" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/JjyzQyQ">
  ref_01-HTML_04-列表（list）_&lt;dl&gt;_2</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>



> 更新时间：{docsify-updated}