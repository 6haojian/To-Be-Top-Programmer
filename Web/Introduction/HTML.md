# HTML（超文本标记语言）

> [实例练习 W3school](https://www.w3school.com.cn/html/index.asp)  
> [参考手册 MDN HTML](https://developer.mozilla.org/zh-CN/docs/Web/HTML)
> [项目练习 Responsive Web Design](https://www.freecodecamp.org/chinese/learn/2022/responsive-web-design/)

# HTML 基础

HTML定义了网页内容的含义和结构，由一系列的元素组成。
HTML使用“标记”来注明文本、图片和其他内容，以便在Web浏览器中显示。

**HTML元素详解**
![](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-small.png)

元素主要组成部分：
- 开始标签：包含元素的名称（本例为 p），被大于号、小于号所包围。
- 结束标签：与开始标签相似，只是其在元素名之前包含了一个斜杠。
- 内容：元素的内容

元素也能包含属性。

![](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-attribute-small.png)

属性应该包含：
- 属性的名称，并接上一个等号。
- 由引号包围属性值。

# HTML文档详解

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="My test image">
  </body>
</html>
```

- `<!DOCTYPE html>`：描述文档类型，作用有限，仅做了解。
- `<html></html>`：html元素包含整个页面的内容，称作根元素。
- `<head></head>`：head元素的内容对用户不可见，其中包含例如面向搜索引擎的搜索关键字、页面描述、CSS样式表和字符编码等。
- `<title></title>`：title元素设置页面的标题，显示在浏览器标签页上。
- `<body></body>`：body元素包含让用户在访问页面时看到的内容，包括文本、图像、视频、游戏、音频等

# 图像
    <img src="images/firefox-icon.png" alt="My test image" />

- src属性：描述图片地址
- alt属性：描述图片内容（当图片无法显示时）

# 标题
一般最多用到 3-4 级标题.
不要使用标题元素来加大、加粗字体。

```html
<h1>主标题</h1>
<h2>顶层标题</h2>
<h3>子标题</h3>
<h4>次子标题</h4>
```

# 段落
    <p>这是一个段落</p>

# 列表
1. 无序列表：`<ul></ul>`
2. 有序列表：`<ol></ol>`

# 链接
    <a href="https://www.mozilla.org/zh-CN/about/manifesto/">Mozilla Manifesto</a>

- `<a></a>`: a是"anchor"（锚）的缩写
- `href`：hypertext reference（超文本引用）

