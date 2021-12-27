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

## 布尔字面量（Boolean literals）

Boolean 类型有两种字面量：`true` 和 `false`。

## 数字字面量（Numeric literals）

JavaScript 整数有多种基，浮点数只有十进制。为了避免混乱，数字字面量涉及字母时，建议统一小写。

### 整数字面量（Integer literals）

整数字面量可以有十进制（基数 10）、十六进制（基数 16）、八进制（基数 8）和二进制（基数 2）。

* 十进制（decimal，基数 10）整数，例如：`0`，`145`。
* 十六进制（hexadecimal，基数 16）整数，以 `0x` 开头，可以使用 `0~9`，`a~f`，字母大小写都可以。例如：
  * `0xa` = `0XA` = `10`，`0xf` = `0XF` = `15`
* 八进制（octal，基数 8）整数，以 `0o` 开头，可以使用 `0~7`，字母大小写都可以。例如：
  * `0o5` = `0O5` = `5`，`0o11` = `0O11` = `9`
* 二进制（binary，基数 2）整数，以 `0b` 开头，可以使用 `0~1`，字母大小写都可以。例如：
  * `0b1` = `0B1` = `1`，`0b101` = `0B101` = `5`
* 大整数（BigInt），以 `n` 结尾，可以使用上面罗列的任意一种基。例如：
  * `123456789123456789n`，`0x123456789ABCDEFn`，`0o777777777777n`，`0b11101001010101010101n`

### 浮点数字面量（Floating-point literals）

浮点数里用 e（大写也可）表示指数，例如 `e3` 表示【乘以 10 的 3 次方】。浮点数的结构是：

```
[digits].[digits][(E|e)[(+|-)]digits]
```

例如：`3.14`，`.14`，`3.14e+12`，`.1e-23`

## 对象字面量（Object literals）

对象字面量是一个包含零对或多对 `属性名: 属性值` 的列表，用花括号（`{}`）括起来。例如：

```js
const myDog = {
  name: "CoCo",
  weight: 30,

  // 属性名也可以不符合标识符规则
  "hello world": 11,
  7: "seven"
};

// 访问属性值的两种方式
myDog["name"];          // "CoCo"，也可以是 myDog.name
myDog.weight;           // 30，也可以是 myDog["weight"]

// 属性名不符合标识符规则时，只能用 [] 访问
myDog["hello world"];   // 11
myDog["7"];             // "seven"

// 另外，属性值还可以是函数的调用，例如：
// const myObj = {hello: foo()};
// 属性值也可以是对象，从而形成对象的嵌套
```

注意：不要在语句的开头使用对象字面量！否则 `{` 将被解释为语句块的开头。

## 正则表达式字面量（RegExp literals）

正则表达式字面量是包含在斜杠 `/` 之间的模式。例如：

```js
let re = /ab+c/;
```

关于正则表达式，后面会有专门章节讲解。

## 字符串字面量（String literals）

字符串字面量是用双引号 `"` 或单引号 `'` 括起来的零个或多个字符。例如：

```js
'foo';
"bar";
'1234';
'one line \n another line';
"John's cat";
```

使用 `.length` 来获取字符串长度，例如：

```js
"John's cat".length;  // 10
```

JS 也支持字符串模板，使用反引号 <code>`</code> 括起来（注意反引号不是单引号）。例如：

```js
// 在字符串模板里，可以自由使用单引号、双引号
// 结果是 In JavaScript '\n' is a line-feed.
`In JavaScript '\\n' is a line-feed.`

// 多行字符串
`In JavaScript, template strings can run
 over multiple lines, but double and single
 quoted strings cannot.`

// 字符串插值。${变量} 会解释为变量值
let name = 'Bob', time = 'today';
`Hello ${name}, how are you ${time}?`     // 'Hello Bob, how are you today?'
```

转义字符。当我们想在字符串中表达特殊字符时，可使用反斜杠 `\` 转义。例如：

```js
// 当想在双引号里表达双引号时，需要用 \ 转义
// 结果是 He read "The Cremation of Sam McGee" by R.W. Service.
"He read \"The Cremation of Sam McGee\" by R.W. Service.";

// 结果是 c:\temp
'c:\\temp';

// 还可以通过在换行符前面加上反斜杠来转义换行符。反斜杠和换行符都从字符串的值中删除。可以看成“续行符”
// 结果是 this string is broken across multiple lines.
'this string \
is broken \
across multiple \
lines.'
```



> 更新时间：{docsify-updated}