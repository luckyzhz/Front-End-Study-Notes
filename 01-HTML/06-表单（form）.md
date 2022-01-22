> `<form>` 元素表示文档中的一个区域，此区域包含交互控件，用于向 Web 服务器提交信息。

## 基本的表单

`<form>` 元素表示表单。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="mdBJYKy" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/mdBJYKy">
  06-表单（form）</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

`<form>` 的常用属性：

1. `action` 指定表单数据提交到的 URL。
   * 如 `action="https://www.example.com/example.php"`，则服务器上的脚本 `example.php` 会处理提交上来的表单数据。
2. `method` 指定提交表单数据的方法。
   * `method="post"`，则表单数据会打包后提交给服务器。特点是数据不会在浏览器地址栏中显示。因此，无法添加书签，适合一次性提交的表单，例如订单。如果表单包含敏感数据，也必须使用 post 方法。可传输的数据量比 get 方法多。
   * `method="get"`，则表单数据会在浏览器地址栏中显示。因此，可以添加书签，不能用来传输敏感数据。可传输的数据量比 post 方法少。
3. `target` 指定提交表单之后，在哪里显示响应信息。
   * `target="_self"`，默认值，在当前标签页中加载。
   * `target="_blank"`，在新标签页中加载。

## 输入元素（`<input>`）

`<input>` 是一个异常强大的表单输入元素，用 `type` 属性来决定具体是哪种输入控件。例如：

<!-- tabs:start -->

#### **浏览器普遍支持的**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="RwLWNqe" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/RwLWNqe">
  06-表单（form）_input</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **浏览器不一定支持的**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="wvrKBRV" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/wvrKBRV">
  06-表单（form）_input_2</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<!-- tabs:end -->

上例只是 `<input>` 简单的介绍，详细可参考：<https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input>

## 按钮（`<button>`）

`<button>` 元素表示一个可点击的按钮，可以用在表单或文档其它需要使用简单标准按钮的地方。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="abLvWdq" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/abLvWdq">
  06-表单（form）_button</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

`<button>` 的常用属性：

1. `type`，指定 `<button>` 的类型。
   * `type="submit"`，默认值，此按钮将表单数据提交给服务器。
   * `type="reset"`，此按钮重置所有组件为初始值。
   * `type="button"`，此按钮没有默认行为，由 JavaScript 编写其行为。
2. `form`，指定 `<button>` 关联的表单，值是表单 `id`。如果此属性未指定，`<button>` 元素必须是 form 元素的后代。利用此属性，可以将 `<button>` 元素放置在文档内的任何位置，而不仅仅是作为他们 form 元素的后代。
   * 例如 `form="customer"`，把 `<button>` 关联到 id 为 customer 的表单。

`<button>` 相比 `<input type="button">` 的优点：

`<button>` 元素比 `<input>` 元素更容易使用样式。你可以在元素内添加 HTML 内容（像 `<em>`、`<strong>` 甚至 `<img>`），以及 `::after` 和 `::before` 伪元素来实现复杂的效果，而 `<input>` 是单标签，只支持文本内容。

## 标签（`<label>`）

`<label>` 表示用户界面中某个元素的说明。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="OJxymYR" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/OJxymYR">
  06-表单（form）_label</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

将一个 `<label>` 和一个 `<input>` 元素相关联的优点：

* 标签文本不仅与其相应的输入元素在视觉上相关联，程序中也是如此。这意味着，当用户聚焦到这个表单输入元素时，屏幕阅读器可以读出标签，让使用辅助技术的用户更容易理解应输入什么数据。
* 可以点击关联的标签来聚焦或者激活这个输入元素，就像直接点击输入元素一样。这扩大了元素的可点击区域，让包括使用触屏设备在内的用户更容易激活这个元素。
* 点击或者轻触（tap）与表单控件相关联的 `<label>` 也可以触发关联控件的 click 事件。

## 选项菜单（`<select>`）

`<select>` 元素表示一个提供选项菜单的控件。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="vYeNZpX" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/vYeNZpX">
  06-表单（form）_select</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

* `name` 属性放在 `<select>`，被选中的 `<option>` 的 `value` 值会赋给 `<select>` 的 `name`。
* 如果 `<option>` 不含 `value` 属性，则 `value` 值默认为 `<option>` 的文本。
* 可以在 `<option>` 元素中设置一个 `selected` 属性以将其设置为页面加载完成时默认选中的元素。
* 把第一个 `<option>` 的 `value` 设为空，并放置提示文字。

此外，还可以：

* 用 `multiple` 属性规定能不能同时选中多个选项。如果设置了，用户可以通过按住 <kbd>Ctrl</kbd> 键，选择多个选项。
* 用 `size` 属性规定一次性显示多少选项。
* 用 `<optgroup>` 元素为下拉菜单创建不同的选项分组。

例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="yLzYXRZ" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/yLzYXRZ">
  Untitled</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 数据列表（`<datalist>`）

`<datalist>` 元素包含了一组 `<option>` 元素，这些元素表示其它表单控件可选值。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="eYGpGKV" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/eYGpGKV">
  06-表单（form）_datalist</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

使用时，把 `<input>` 元素的 `list` 属性值设为 `<datalist>` 元素的 `id`，从而实现 `<input>` 和 `<datalist>` 的关联。

上例中，例如当我们输入字母 i 时，含有字母 i 的选项就会在输入框下方列出来供我们选择。输入其他字母也是一样的。

## 文本区域（`<textarea>`）

`<textarea>` 元素表示一个多行纯文本编辑控件，当你希望用户输入一段相当长的、不限格式的文本，例如评论或反馈表单中的一段意见时，这很有用。例如：

<!-- tabs:start -->

#### **无 CSS**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="rNGOYVq" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/rNGOYVq">
  06-表单（form）_textarea</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### **有 CSS**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="GRMpOWN" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/GRMpOWN">
  06-表单（form）_textarea_2</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<!-- tabs:end -->

`<textarea>` 的几个特点：

* `rows` 和 `cols` 属性，用于声明 `<textarea>` 的精确尺寸。
* 位于开始标签和闭合标签之间的是默认内容。`<textarea>` 不支持 `value` 属性。
* 也可以使用 `placeholder` 属性作为用户提示。
* 文本框默认是可调整大小的。可通过 CSS 的 `resize: none;` 设为不可调整大小。

## 分组（`<fieldset>`）

`<fieldset>` 元素用于对表单中的控件进行分组。例如：

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="zYEvPVx" data-editable="true" data-user="luckyzhz" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luckyzhz/pen/zYEvPVx">
  Untitled</a> by luckyzhz (<a href="https://codepen.io/luckyzhz">@luckyzhz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

用 `<legend>` 元素指定标题。




> 更新时间：{docsify-updated}