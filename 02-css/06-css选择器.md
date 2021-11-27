# 06-CSS选择器

> CSS 选择器规定了 CSS 规则会被应用到哪些元素上。

# 1. 基本选择器

## 元素选择器（Type selector）

CSS 元素选择器（也称为类型选择器）通过标签名选择元素。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="vYJqqeP" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/vYJqqeP">
  06-CSS选择器_Type_selector</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

会匹配 HTML 文档中所有的 `<p>` 元素，将其前景色设为红色。

## 类选择器（Class selector）

CSS 类选择器根据 HTML 标签的 `class` 属性选择元素。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="porXXaR" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/porXXaR">
  Untitled</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

会选择所有 `class` 属性里有 `green` 值的标签。

## ID 选择器（ID selector）

按照 id 属性选择一个与之匹配的元素。需要注意的是，一个文档中，每个 id 属性都应当是唯一。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="mdMZZod" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/mdMZZod">
  06-CSS选择器_ID_selector</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 属性选择器（Attribute selector）

CSS 属性选择器通过已经存在的属性名或属性值匹配元素。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="bGrPXpq" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/bGrPXpq">
  06-CSS选择器_Attribute_selector</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="JjyQgqd" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/JjyQgqd">
  06-CSS选择器_Attribute_selector_2</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 通用选择器（Universal selector）

选择所有元素。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="wvqVwjR" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/wvqVwjR">
  06-CSS选择器_Universal_selector</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

不推荐使用通用选择器，因为他是性能最低的 CSS 选择器。

# 2. 分组选择器（Grouping selectors）

## 选择器列表（Selector list）

用 `,` 将不同选择器组合在一起，表示这些选择器具有相同的样式，是并列的关系，又称为并集选择器。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="gOxVYEQ" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/gOxVYEQ">
  06-CSS选择器_Selector_list</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 交集选择器

交集选择器就是把元素选择器（Type selector）和其他基本选择器连写。例如：

```CSS
a.green { /* 选择 class 属性里有 green 值的 <a> 元素 */
  color: green;
}

div#sidebar { /* 选择 id 是 sidebar 的 <div> 元素 */
  border: dashed gray 2px;
}

li[title] { /* 选择有 title 属性的 <li> 元素 */
  color: purple;
}
```

交集选择器同样可以用于组合选择器。

# 3. 组合器（Combinators）

## 后代组合器（Descendant combinator）

` `（空格）组合器选择前一个元素的后代节点。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="vYJoxWN" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/vYJoxWN">
  06-CSS选择器_Descendant_combinator</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

注意是后代节点，而不仅是儿子节点。

## 直接子代组合器（Child combinator）

`>` 组合器选择前一个元素的直接子代的节点。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="rNzXyJQ" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/rNzXyJQ">
  06-CSS选择器_Child_combinator</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 一般兄弟组合器（General sibling combinator）

`~` 组合器选择兄弟元素，也就是说，后一个节点在前一个节点 ***后面*** 的任意位置，并且共享同一个父节点。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="LYjwWJE" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/LYjwWJE">
  06-CSS选择器_General_sibling_combinator</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 紧邻兄弟组合器（Adjacent sibling combinator）

`+` 组合器选择相邻元素，即后一个元素紧跟在前一个之后，并且共享同一个父节点。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="vYJoxQK" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/vYJoxQK">
  06-CSS选择器_Adjacent_sibling_combinator</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

# 4. 伪选择器（Pseudo）

## 伪类（pseudo-class）

`:` 伪选择器支持按照未被包含在文档树中的 ***状态信息*** 来选择元素。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="rNzXgoO" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/rNzXgoO">
  06-CSS选择器_pseudo-class</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

排在前面的伪类样式有可能被后面的覆盖，所以要注意顺序。链接伪类先后顺序被称为 LVHA 顺序：`:link` -> `:visited` -> `:hover` -> `:active`。

*可用两个单词记忆：LoVe HAte。*

另一个常用的伪类是 `:nth-child(an+b)` （n = 0，1，2，3...）。例如：

```CSS
li:nth-child(0n+3) {  /* 匹配兄弟中排行第三的 <li>。括号里也可以直接写 3 */
  color: red;
}

tr:nth-child(1n) {    /* 匹配每个 <tr> */
  color: red;
}

td:nth-child(2n+1) {  /* 匹配排行 1, 3, 5... 的 <td> */
  color: red;
}

a:nth-child(3n+4) {   /* 匹配排行 4, 7, 10... 的 <a> */
  color: red;
}
```

更多伪类可参考：<https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-classes>

## 伪元素（pseudo-element）

`::` 伪选择器用于表示无法用 HTML 语义表达的 ***实体***。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="JjygQGy" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/JjygQGy">
  06-CSS选择器_pseudo-element</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

更多伪元素可参考：<https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-elements>



> 更新时间：{docsify-updated}