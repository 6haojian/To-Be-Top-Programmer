# CSS
层叠样式表（Cascading Style Sheet）是为网页添加样式的代码。

    <link href="styles/style.css" rel="stylesheet">

通过link标签将CSS文件连接至HTML文档，放在head标签之间。

# CSS规则集详解
![](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics/css-declaration-small.png)

- 选择器：选择一个或多个需要添加样式的元素
- 声明：一个单独的规则
- 属性：
- 属性值：
  
每个规则集都应该包含在成对的大括号里
每个声明里要用冒号将属性与属性值分隔开
在每个规则集里要用分号将各个声明分隔开

**多元素选择**
```css
p, li, h1 {
  color: red;
}
```

# 不同类型的选择器
|选择器名称|选择内容|
|-|-|
|元素选择器|所有指定类型的HTML元素|
|ID选择器|具体特定ID的元素|
|类选择器|具有特定类的元素|
|属性选择器|拥有特定属性的元素|
|伪类选择器|特定状态下的特定元素（比如鼠标指针悬停）|

# 字体和文本
> 中文字体文件较大，不适合直接用于web font

# 盒子模型

![](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics/box-model.png)
- padding：内边距
- border：边框
- margin：外边距
- width: 元素的宽度
- background-color：元素内容和内边距底下的颜色
- color：元素内容的颜色
- text-shadow：为元素内的文本设置阴影

margin，padding属性接收1-4个值
- 当只指定一个值时，该值会统一应用到全部四个边的外边距上。
- 指定两个值时，第一个值会应用于上边和下边的外边距，第二个值应用于左边和右边。
- 指定三个值时，第一个值应用于上边，第二个值应用于右边和左边，第三个则应用于下边的外边距。
- 指定四个值时，依次（顺时针方向）作为上边，右边，下边，和左边的外边距。

border属性接收三个值：birder-width, border-style, border-color

