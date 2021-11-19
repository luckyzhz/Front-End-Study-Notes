# 04-列表（list）

> 介绍 3 种列表。

## 有序列表（ordered list）

`<ol>` 标签表示有序列表（ordered list），渲染为一个带编号的列表。例如：

```html
<ol>
    <li>条目</li>
    <li>条目</li>
    <li>条目</li>
</ol>
```

浏览器渲染后的结果：

<ol>
    <li>条目</li>
    <li>条目</li>
    <li>条目</li>
</ol>

被嵌套的 `<li>` 标签表示列表条目（list item）。

可以通过 `start` 属性指定列表编号的起始值。用 `reversed` 属性让列表编号倒序。例如：

```html
<ol start="6" reversed>
    <li>条目</li>
    <li>条目</li>
    <li>条目</li>
</ol>
```

浏览器渲染后的结果：

<ol start="6" reversed>
    <li>条目</li>
    <li>条目</li>
    <li>条目</li>
</ol>

注意 `reversed` 属性不需要值，这个属性存在就表示要倒序。另外，可以使用 css 的 `list-style-type` 属性设置编号的类型，例如设为字母或罗马数字等，待到 css 章节再讲。

## 无序列表（unordered list）

`<ul>` 标签表示无序列表（unordered list）。例如：

```html
<ul>
    <li>条目</li>
    <li>条目</li>
    <li>条目</li>
</ul>
```

浏览器渲染后的结果：

<ul>
    <li>条目</li>
    <li>条目</li>
    <li>条目</li>
</ul>

可以看到，无序列表同样使用 `<li>` 标签作为条目。条目前的标记同样可以通过 css 的 `list-style-type` 属性设置，甚至可以用自定义图片作为条目标记。

## 描述列表（description list）

有时我们需要为列表条目附上说明，这时可以使用描述列表（description list）。标签是 `<dl>`。例如：

```html
<dl>
    <dt>（术语）华南理工大学</dt>
    <dd>（描述）
        华南理工大学（英语：South China University of Technology，
        缩写：SCUT），简称华工、华工大，是一所直属中华人民共和国教育
        部的公立综合性研究型大学，位于广东省广州市，拥有五山、大学城
        和广州国际三个校区。
    <dd>
</dl>
```

浏览器渲染后的结果：

<dl>
    <dt>（术语）华南理工大学</dt>
    <dd>（描述）
        华南理工大学（英语：South China University of Technology，
        缩写：SCUT），简称华工、华工大，是一所直属中华人民共和国教育
        部的公立综合性研究型大学，位于广东省广州市，拥有五山、大学城
        和广州国际三个校区。
    <dd>
</dl>

`<dt>` 表示描述列表术语（description list term）。`<dd>` 表示描述列表中的描述（description list description）。一条术语可以对应多个描述，也可以多条术语对应一个描述，当然也可以多对多。

```html
<dl>
    <dt>（一条术语）华南理工大学</dt>
    <dd>
        （描述 1）华南理工大学（英语：South China University of 
        Technology，缩写：SCUT），简称华工、华工大，是一所直属中
        华人民共和国教育部的公立综合性研究型大学，位于广东省广州市
        ，拥有五山、大学城和广州国际三个校区。
    </dd>
    <dd>
        （描述 2）华南理工大学是中华人民共和国顶尖高校之一，是“双
        一流A类”和原“985工程”、原“211工程”重点建设大学，是现时13
        所广东省高水平大学之一。
    </dd>

    <dt>（术语 1）中山大学</dt>
    <dt>（术语 2）Sun Yat-sen University</dt>
    <dd>
        （一条描述）中山大学（英语：Sun Yat-sen University，缩写：
        SYSU），简称中大，是一所中国大陆的综合性研究型大学，位于广
        东省广州市、珠海市和深圳市，直属于中华人民共和国教育部，由
        教育部与广东省人民政府共建。
    </dd>
</dl>

```

浏览器渲染后的结果：

<dl>
    <dt>（一条术语）华南理工大学</dt>
    <dd>
        （描述 1）华南理工大学（英语：South China University of 
        Technology，缩写：SCUT），简称华工、华工大，是一所直属中
        华人民共和国教育部的公立综合性研究型大学，位于广东省广州市
        ，拥有五山、大学城和广州国际三个校区。
    </dd>
    <dd>
        （描述 2）华南理工大学是中华人民共和国顶尖高校之一，是“双
        一流A类”和原“985工程”、原“211工程”重点建设大学，是现时13
        所广东省高水平大学之一。
    </dd>
    <dt>（术语 1）中山大学</dt>
    <dt>（术语 2）Sun Yat-sen University</dt>
    <dd>
        （一条描述）中山大学（英语：Sun Yat-sen University，缩写：
        SYSU），简称中大，是一所中国大陆的综合性研究型大学，位于广
        东省广州市、珠海市和深圳市，直属于中华人民共和国教育部，由
        教育部与广东省人民政府共建。
    </dd>
</dl>




> 更新时间：{docsify-updated}