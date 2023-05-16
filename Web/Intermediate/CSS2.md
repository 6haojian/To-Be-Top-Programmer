# CSS
CSS是一门基于规则的语言，定义用于你的网页中特定元素样式的一组规则。

**添加CSS**
在文档的开头链接CSS
    <link rel="stylesheet" href="style.css">

**类选择器**
```css
.special {
  color: orange;
  font-weight: bold;
}
```

# 构建CSS
**外部样式表**
外部样式表是指将 CSS 编写在扩展名为.css 的单独文件中，并从 HTML `<link>` 元素引用它的情况。
    <link rel="stylesheet" href="styles/style.css">

**内部样式表**
内部样式表是指不使用外部 CSS 文件，而是将 CSS 放在 HTML 文件`<head>`标签里的`<style>`标签之中。
    <style></style>

**内联样式**
内联样式表存在于 HTML 元素的 style 属性之中。(尽量不要使用，难以维护)
    <h1 style=""></h1>

优先级：为p选择器定义两个规则，后一个会覆盖前面一个。类选择器优先级高于元素选择器。

**@规则**
要将额外的样式表导入主CSS样式表，可以使用@import
    @import 'style2.css';

媒体查询：根据各种设备特征和参数的值或者是否存在来调整网站或应用。
@media允许使用媒体查询来应用CSS，仅当某些条件成立。

该查询将根据视口宽度更改样式。

```css
body {
    background-color: pink;
}

@media (min-width: 30em) {
    body {
        background-color: blue;
    }
}
```

**速记属性**
padding: 上 下 左 右
background：

**注释**
CSS 中的注释以 /* 开头，以 */ 结尾。

# CSS如何运行
![](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_works/rendering.svg)

1. 浏览器载入HTML文件
2. 将HTML文件转化成一个DOM（document object model）,DOM是文件在计算机内存中的表现形式。
3. 浏览器会拉取该HTML相关的大部分资源，比如图片、视频和CSS样式。
4. 浏览器拉取到CSS之后进行解析。根据选择器的不同类型把它们分到不同的桶中。浏览器基于它找到的不同的选择器，将不同的规则应用到对应的DOM的节点中，并添加节点依赖的样式。
5. 上述的规则应用于渲染树后，渲染树会依照应该出现的结构进行布局。
6. 网页展示在屏幕上。

一个DOM有一个树形结构，标记语言中的每一个元素、属性以及每一段文字都对应着结构树中的一个节点。

一个好的实践：
当浏览器遇到无法解析的CSS代码会直接跳过，当实验新特性时，考虑将新特性放在后面，如果浏览器支持，直接覆盖直接的参数，如果不支持，浏览器会忽略它。


