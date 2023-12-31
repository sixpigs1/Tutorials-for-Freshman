本文涉及对Markdown的简单介绍和基本语法。

# 什么是Markdown

据 GitHub Flavored Markdown（GFM）官方文档介绍，Markdown 是由约翰·格鲁伯（John Gruber）在亚伦·斯沃茨（Aaron Swartz）的帮助下开发，并在2004年发布的标记语言。其设计灵感主要来源于纯文本电子邮件的格式，目标是让人们能够使用易读、易写的纯文本格式编写文档，而且这些文档可以转换为HTML（Hyper Text Markup Language，超文本标记语言）文档。

简而言之，Markdown 是一种轻量级标记语言，它允许人们使用易读、易写的纯文本格式编写文档。

# 如何编辑Markdown

## 记事本

Markdown 可以用 Windows 系统自带的记事本进行打开与编辑。这使得 Markdown 的编辑十分简单方便。但是这种编辑方式存在一个巨大的缺陷，即无法预览Markdown 文件的效果，因此并不推荐。

## VScode

作为一款在多个操作系统（Windows，Mac，Linux等）通用的代码编辑器，VScode 也可以在经过简单的配置以后编辑并预览Markdown文件。以下是一些配置 VScode 中Markdown的推荐插件。

- `Markdown All in One`   实现VScode中Markdown的基本功能
- `Markdown PDF`   实现将Markdown转化为PDF
- `markdownlint`   Markdown的语法检查器
- `Markdown Preview Enhanced` 提供一些更全面的预览

本文所有对于Markdown的介绍都将基于VScode平台进行。

# Markdown 基本语法

## 标题

Markdown 中标题有两种实现形式：

1. 用若干个 `#` + 空格 处理。如：`# `为一级标题；`## `为二级标题；`### `为三级标题。

Example:

```Markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

2. 用`=====`和`-----`(=和-的数量至少两个，但是为了编辑时方便看清楚通常建议打一排)

Example:

```Markdown
一级标题
================
二级标题
-----------------
```

**建议使用第一种表达方法，因为第一种方式更加简洁且可以实现的标题级数更多**

## 粗体与斜体

1. 粗体： 将需要粗体的内容用两个`**`或`__`包围起来

Example: 

```Markdown
**粗体 Bold**
__粗体 Bold__
```

2. 斜体： 将需要斜体的内容用两个`*`或`_`包围起来

Example:

```Markdown
*斜体 italic*
_斜体 italic_
```

**建议使用`*`来表示粗体和斜体，因为在编辑时*的可读性比_更强**

## 段落与换行

1. 如果行与行之间没有空行，则视为同一段落。
2. 如果行与行之间有空行，则视为不同的段落。
3. 如果想在段内换行，则需要在上一行的结尾插入两个以上的空格然后按回车键。

Example1:

```Markdown
我是第一行
我是第二行
```

Example2(加空格):

```Markdown
我是第一行  
我是第二行
```

Example3:

```Markdown
我是第一行

我是第二行
```

**建议用空一行的方式进行换段**

## 列表

1. 有序列表

有序列表用`数字+.+空格`的形式进行表示，如`1. `。

Example:

```Markdown
1. item1
2. item2
3. item3
```

*注意使用`.`而不是`。`*

2. 无序列表

无序列表用`*/+/- + 空格`的形式进行表示，如`* `或`+ `或`- `。

Example1(*):

```Markdown
* item1
* item2
* item3 
```

Example2(+):

```Markdown
+ item1
+ item2
+ item3
```

Example3(-):

```Markdown
- item1
- item2
- item3
```

*可见，三种表示方法是等价的*

**但是当三种表达方式混合使用的时候会被认为是三个独立的无序列表**

Example:

```Markdown
* item1
+ item2
- item3 
```

3. 嵌套列表

列表具有可以嵌套的特点，有序列表和无序列表之间都可以互相嵌套。

嵌套列表的使用方法是：第n层嵌套的列表即在前面加n个`Tab`。

Example:

```Markdown
* item1
* item2
     - subitem1
     - subitem2
          1. subsubitem1
          2. subsubitem2
          3. subsubitem3
* item3
     + subitem1
          * subsubitem
     + subitem2
```

**建议使用`- `来表示无序列表，因为`* `容易与粗体斜体混淆并且`- `更常用**

## 分割线

在Markdown 中，分隔线由3 个以上的`*`/`-`/`_`来标记。

Example:

```Markdown
***
```

or

```Markdown
---
```

or

```Markdown
___
```

可以发现，三种用法产生的分割线效果是相同的。

## 图片

在Markdown中插入图片的方式是`![图片替代文字](图片地址)`

Example:

```Markdown
![一些文字](Markdown.png)

![一些文字]()
```

从这两个例子里我们可以看到，图片地址为相对路径，通常与Markdown文件放在同一个文件夹内时只要添加图片文件名即可。如果图片地址无法找到会显示一个图片表示失败的小符号。此外，图片替代文字只有在图片未正常显示时会起到作用。

## 网址链接

在Markdown文件中插入网址链接的格式是：`[链接文字](链接地址)`或`<链接地址>`

Example:

```Markdown
[github官网网址](https://github.com/)

<https://github.com/>
```

## 代码

- 行内代码

Markdown中行内代码用`   ``   `符号包裹。

Example:

```Markdown
`行内代码`
```

- 代码块

1. 在Markdown中可以在行前面增加`Tab`或四个空格来表示代码块。
2. 后面在进阶语法中会介绍另一种更好的方法。

Example:

```Markdown
     #include <stdio.h>
          int main(){
          printf("Hello World!");
     }
```

## 引用

在Markdown中，用 `>`+引用内容 表示引用。如果连续多行引用时，需要在每一行前面加上`>`符号

Example:

```Markdown
> 其实世上本没有路，走的人多了，也就成了路。 
> ——鲁迅
```

## 转义

一些符号在Markdown中被用作排版符号，在输入这些符号时需要用转义符。这些符号包括：

\\ 反斜线
\` 反引号
\* 星号
\_ 底线
\{} 花括号
\[] 方括号
\() 括弧
\# 井字号
\+ 加号
\- 减号
\. 英文句点
\! 惊叹号

# Markdown进阶语法

随后将讲述Markdown的一些进阶语法，不一定所以编辑器都支持，但是现在大多数Markdown编译器能支持这些语法。它为Markdown提供了更多的功能，是Markdown的排版能力更加强大。

## 删除线

删除线用两个`~~`包裹表示。

Example：

```Markdown
~~删除线示例~~
```

## 表情

表情可以用两个`:`包裹起一条对应单词吗(如:笑脸是`smile`)表示。

Example：

```Markdown
:smile:
```

更多表情请根据这个链接:[表情链接](http://www.webpagefx.com/tools/emoji-cheat-sheet/)

## 表格

1. 表格表示为单元格竖线用`|`表示，表头与表格内容之间需要`---|---`类似的格式隔开(只有添加了这样的分割线才会被识别为表格排版格式)。
2. 表格对齐格式如下
- 左对齐（默认）：`:----`
- 右对齐：`----:`
- 居中对齐：`:----:`
3. 块级元素（代码区块、引用区块）不能插入表格中,但是链接可以插入。

Example:

```Markdown
a|b|c
:---|:---:|---:
dddddd|eeeeee|fffffff
g|h|i
```

## 任务列表

任务列表的格式表示方法是这样的:
- 未勾选 `- [ ]`
- 已勾选 `- [x]`

Example：

```Markdown
- [ ] 任务一
- [x] 任务二
```

## 代码块++

在Markdown中可以用` ``` `或者`~~~`在前后包裹代码来表示代码块。其中可以在前面的` ``` `或者`~~~`后增加所用代码语言的类型来获取相应的代码高亮。

Example:

```Markdown

```C
#include <stdio.h>
int main(){
     printf("Hello World!");
}
```

```

**推荐这一种方式**

在这两种方式的对比中，我们可以看到这种方式相对于前面的方式既方便表示和编辑，又可以获得高亮视觉效果更好。

## $\LaTeX$ 公式编辑

与 $\LaTeX$ 相似，Markdown书写公式也是用两个`$`包裹起来并且与 $\LaTeX$ 用法完全相同。

Example:

```Markdown
$\int \cos x dx = \sin x $
```

关于 $\LaTeX$ 的更多介绍可以参看以下文章:[LaTeX 介绍与基本语法](https://zhuanlan.zhihu.com/p/665393031)

# 声明
- 本文参考《了不起的Markdown》（毕小朋著，电子工业出版社），摘取笔者认为适合初学者入门的部分，可有效降低上手成本。
- 转载请注明出处并放置相关链接
