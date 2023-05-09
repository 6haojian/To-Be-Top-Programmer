# 简介
markdown是一种轻量标记语言。

# 标题语法
在单词前添加`#`号创建标题
```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

# 段落语法
使用空白行将一行或多行文本进行分隔

# 换行语法
在一行末尾添加两个或多个空格，然后按回车创建一个换行

# 强调语法
**粗体**：在单词或短语前后加两个星号
*斜体*：在单词或短语前后加一个星号
***粗体+斜体***：在单词或短语前后加三个星号

# 引用语法 {#引用语法}
在段落前加一个`>`符号创建引用
> 这是一个引用

# 列表引用
创建无序列表, 每个列表项前加破折号`-`
- item1
- item2

有序列表，每个列表项前添加数字并紧跟一个英文句号
1. 1st
2. 2nd
   
保留列表连续性的同时在列表中添加另一种元素，将该元素缩进四个空格或一个制表符
代码块缩进八个空格或两个制表符

# 代码语法
将单词或短语包裹在反引号``中

# 分隔语法
在单独一行上使用三个或多个`---`
在分割线的前后添加空白行

# 链接语法
链接文本放在`[]`内，链接地址放在后面的括号中
`[百度](https://www.baidu.com/ "百度")`
其中"百度"是标题（可选）

# 图片语法
使用感叹号`!`，然后在方括号增加替代文本，图片链接放在圆括号内，括号里的链接后可以增加一个可选的图片标题文本
`![这是图片](图片链接 "图片title")`
![图片](https://images.unsplash.com/photo-1558979158-65a1eaa08691?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80 "网络图片")

# 转义字符
反斜杠\

# 扩展语法

## 表格
使用三个或多个`-`字符创建每列的标题，使用`|`分隔每列。
|syntax|description|
|:---:|:---:|
|header|title|
|paragraph|text|

- 靠左对齐：`:---`
- 靠右对齐: `---:`
- 两端对齐: `:---:`

## 围栏代码
使用三个`````
```
echo "hello!"
```

## 脚注
使用脚注添加注释和参考，而不会是文档混乱。创建脚注时，带有脚注的上标数字会出现在添加脚注参考的位置，可以单击链接跳至页面底部的脚注内容。
在括号内使用另一个插入符号和数字添加脚注，并用冒号和文本（[^3]: my peace）

Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.

## 标题链接
在标题同行上用大括号扩起自定义ID

```
### 标题 {#标签ID}
```

```
[text](#标text
```

[跳转](#引用语法)

## 定义列表
要创建定义列表，请在第一行上键入术语。在下一行，键入一个冒号，后跟一个空格和定义。

First Term
: This is the definition of the first term.

Second Term
: This is one definition of the second term.
: This is another definition of the second term.

## 删除线
在单词前后使用两个波浪线
~~hello world!~~

## 任务列表
在任务列表之前添加破折号`-`和方括号`[]`,`[]`前加上空格，选择一个复选框，在方括号之间加x。
- [x] 看书
- [ ] 游戏

## emoji表情
以冒号开头和结尾包含表情符号名称
:joy:
:cry:
[表情符号简码列表](https://gist.github.com/rxaviers/7360908)