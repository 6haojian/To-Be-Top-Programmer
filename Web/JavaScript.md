# JavaScript

avaScript 是一门编程语言，可为网站添加交互功能.

    <script src="scripts/main.js" defer></script>

通过script标签将js引入HTML

文档对象模型（DOM）API

# JavaScript 快速入门

**变量**
let声明变量
    let myVariable = 'abc';

**数据类型**
|变量|解释|
|-|-|
|String|字符串，用单引号或者双引号括起来|
|Number|数字|
|Boolean|true/false|
|Array|单一引号中存储多个值|
|Object|Js中一切皆对象|

**运算符**
`+ - * 、 = === !== !`

**条件语句**
```
if () {

} else {

}
```

if ( ... ) 中的表达式进行测试，如果返回 true，则运行第一个代码块；如果返回 false，则跳过第一块直接运行 else 之后的第二个代码块。

**函数**
```
function functionname(para1, para2) {
    ...
    return
}
```

return语句告诉浏览器当前函数返回 result 变量。这是一点很有必要，因为函数内定义的变量只能在函数内使用。这叫做变量的 作用域。

**事件**
事件能为网页添加真实的交互能力，它可以捕捉浏览器操作并运行一些代码作为响应。最简单的事件是点击事件，鼠标的点击操作会触发该事件。

```
document.querySelect('html').addEventListener("click", function() {alert("don't touch me!")})
```
