# HTML
HTML（HyperText Markup Language，超文本标记语言）是一种用来告知浏览器如何组织页面的标记语言。

**嵌套元素**
可以把元素放到其他元素之中

**块级元素和内联元素**
- 块级元素
  块级元素在页面以块的形式展现。一个块级元素出现在它前面的内容之后的新行上。任何跟在块级元素后面的内容也会出现在新的行上。
  块级元素通常是页面上的结构元素。
- 内联元素
  内联元素通常出现在块级元素中并环绕文档内容的一小部分，而不是一整个段落或者一组内容。内联元素不会导致文本换行。它通常与文本一起使用。

**空元素**
不是所有元素都拥有开始标签、内容和结束标签。一些元素只有一个标签，通常用来在此元素所在位置插入/嵌入一些东西。这些元素被称为空元素。如图片

    <img src="xxx", alt="xxx">

**属性**
属性包含元素的额外信息。

<a href="https://www.mozilla.org/" title="The Mozilla homepage" target="_blank"></a>

属性的值需使用双引号或单引号来包裹。

**HTML中的空白**
无论在HTML元素的内容中使用多少空格，当渲染这些代码时候，HTML解释器会将连续出现的空白符减少为一个单独的空格符。

**在HTML中包含特殊字符**
在HTML中，`<`,`>`,`、`和`&`是特殊字符，必须使用字符引用
|原义字符|等价字符引用|
|-|-|
|<|\&lt;|
|>|\&gt;|
|"|\&quot;|
|'|\&apos;|
|&|\&amp;|

**HTML注释**
使用`<!--`和`-->`包裹起来。

# HTML头信息

在页面加载完成的时候，HTML文档中的头部`<head>`元素是不会显示在web浏览器的，它的作用是保存页面的一些元数据。

title元素为文档添加标题
meta元素为文档添加元数据，如字符编码、作者和描述
许多meta元素包含了name和content属性
- name 指定了meta元素的类型
- content 指定了实际的元数据内容


```html
<head>
    <title>标题</title>
    <meta charset="utf-8" />
    <meta name="author" content="someone" />
    <meta name="description" content="some description" />

</head>
```

**自定义图标**
在元数据中添加对自定义图标的引用,
    <link rel="icon" href="favicon.ico" type="image/x-icon" />

**在HTML中应用CSS和JavaScript**

`<link>`元素经常位于文档的头部，有两个属性，rel="stylesheet"表明这是文档的样式表，而href包含了样式表文件的路径
    <link rel="stylesheet" href="style.css" />

<script>元素也应该放在文档的头部，并包含src属性来指向需要加载的JavaScript文件路径，同时最好加上`defer`以告诉浏览器在解析完HTML后再加载JavaScript。
    <script src="my.js" defer></script>

**为文档设定主语言**
```html
<html lang="zh-CN">
    ...
</html>
```

# HTML文本处理基础
大部分机构化文本由标题和段落组成。

**重点强调**
`<strong>`标记比周围文本更重要的文本
`<em>`斜体

# 超链接
超链接能够将文档链接到任何其他文档，也可以链接到文档的指定部分，点击超链接将使网络浏览器转到另一个网址。

> URL 可以指向 HTML 文件、文本文件、图像、文本文档、视频和音频文件以及可以在网络上保存的任何其他内容。

**链接的解析**

通过将文本或其他内容包裹在<a>元素内，并给它一个包含网址的href属性来创建一个基本链接。

使用title属性添加支持信息，包含关于链接的补充信息。

**电子邮件链接**
    <a href="mailto:nowhere@example.com">向xxx发邮件</a>