> 介绍基本的字面量（Literals）。

字面量（Literals），又称直接量，是直接给出的固定值。例如：`3.14`，`false`。

## 数组字面量（Array literals）

数组是零个或多个表达式的列表，每个表达式代表一个数组元素，用方括号（`[]`）括起来。使用数组字面量创建数组时，该数组使用指定的值作为其元素进行初始化，并且其长度为元素个数。例如：

```js
// 通常使用 const 来声明 object（数组也是object）。这涉及到一点指针的概念，可以不用深究
const coffees = ['French Roast', 'Colombian', 'Kona'];

coffees.length;     // 3
coffees[1]="coco";  // 修改第二个元素（数组从 0 开始计数）
```

不一定要依次赋值，可以跳过，被跳过的元素的值是 `undefined`。例如：

```js
const fish = ['Lion', , 'Angel'];
fish[0]     // 'Lion'
fish[1]     // undefined
fish[2]     // 'Angel'

const myList = [];
myList[1] = "bike";
myList[0];  // undefined
myList[1];  // "bike";
```

有些人喜欢给数组添加尾随逗号，认为这样方便添加新元素。但尾随逗号可能会在较旧版本的浏览器中产生错误，最好将其删除。没有尾随逗号，这样也与 JSON 格式保持一致。例如：

```js
// 这两个数组字面量是一样的
[1, 2, 3]     // 推荐没有尾随逗号
[1, 2, 3, ]
```

在编写自己的代码时，应该明确地将缺少的元素声明为 `undefined`。这样可以提高代码的清晰度和可维护性。








> 更新时间：{docsify-updated}