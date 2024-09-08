+++
title = 'markdown 语法'
date = 2024-09-06T21:48:59+08:00
draft = false
tags = ["markdown", "语法"]
categories = ["学习笔记"]
+++

> markdown 语法网站 [markdown](https://markdown.com.cn/intro.html)

## 标题
<!--more-->
语法：`### 标题`
> 井号越多、标题越小，井号越少、标题越大
>
> 有 1-6 级标题

## 段落

用法：空白行分隔

## 换行

用法：在换行处添加`<br>`即可

## 强调

### 粗体

语法：`**文本**`

### 斜体

语法： `*文本*或_文本_`

### 高亮

语法：`==文本==`

## 引用

语法：`> 文本`

## 列表

### 有序列表

语法：`1. 文本`

### 无序列表

语法：`- 文本、 * 文本或+ 文本`

## 代码

语法：\``文本`\`

## 分隔线

语法：`*** 、--- 或___`

## 上标和下标

语法：

- 上标：`2^2^`  

- 下标：`2~2~`

实例：

- 下标：2~2~

- 上标：2^2^

## 链接

语法：`[超链接显示名](超链接地址 "超链接title")`
用法：链接文本放在中括号内，链接地址放在后面的括号中，链接 title(光标放上去的显示名) 可选。
实例： [百度](https://baidu.com "搜索")

## 图片

语法：`![图片alt](图片链接 "图片title")`

用法：要添加图像，请使用感叹号 (!), 然后在方括号增加替代文本，图片链接放在圆括号里，括号里的链接后可以增加一个可选的图片标题文本。

实例：

![](https://chenpw721.github.io/assets/img(1).webp "动漫图片")

## 转义字符

用法：要显示原本用于格式化 Markdown 文档的字符，请在字符前面添加反斜杠字符 \ 。

## 表格

语法：

```markdown
|Syntax|Description|
|-|-|
|Header|Title|
|Paragraph|Text|
```

用法：要添加表，请使用三个或多个连字符（---）创建每列的标题，并使用管道（|）分隔每列。您可以选择在表的任一端添加管道。[表格](https://www.tablesgenerator.com/markdown_tables)

## 围栏代码块

语法：

```css
{
"firstName": "John",
"lastName": "Smith",
"age": 25
}
```

## 脚注

语法：

```markdown
[^1]文本
[^1]: 脚注释义
```

实例：

[^1]文本
[^1]: 脚注释义

用法：要创建脚注参考，请在方括号（\[^1]）内添加插入符号和标识符。标识符可以是数字或单词，但不能包含空格或制表符。标识符仅将脚注参考与脚注本身相关联 - 在输出中，脚注按顺序编号。

## 删除线

语法： `~~文本~~`

实例： ~~文本~~

## 任务列表 (复选框)

语法：

```markdown
- [x] Write the press release
- [x] Update the website
- [ ] Contact the media
```

实例：

- [x] 吃饭
- [ ] 睡觉

## 使用 Emoji 表情

用法：在 [emoji](https://emojipedia.org/ "emoji图片复制网站")网站复制

## 目录

用法：在文章顶部添加`[toc]`,即可

## 彩色提示块

{{< admonition title="这是一个默认不展开的横幅" open=false >}}
一个 **注意** 横幅
{{< /admonition >}}

{{< admonition >}}
一个 **注意** 横幅
{{< /admonition >}}

{{< admonition abstract >}}
一个 **摘要** 横幅
{{< /admonition >}}

{{< admonition info >}}
一个 **信息** 横幅
{{< /admonition >}}

{{< admonition tip >}}
一个 **技巧** 横幅
{{< /admonition >}}

{{< admonition success >}}
一个 **成功** 横幅
{{< /admonition >}}

{{< admonition question >}}
一个 **问题** 横幅
{{< /admonition >}}

{{< admonition warning >}}
一个 **警告** 横幅
{{< /admonition >}}

{{< admonition failure >}}
一个 **失败** 横幅
{{< /admonition >}}

{{< admonition danger >}}
一个 **危险** 横幅
{{< /admonition >}}

{{< admonition bug >}}
一个 **Bug** 横幅
{{< /admonition >}}

{{< admonition example >}}
一个 **示例** 横幅
{{< /admonition >}}

{{< admonition quote >}}
一个 **引用** 横幅
{{< /admonition >}}

<div style="background-color: #ffcccc; color: #ff0000; padding: 10px; border-radius: 5px;">
这是一个红色的提示块。
</div>

<div style="background-color: #ccddff; color: #0000ff; padding: 10px; border-radius: 5px;">
这是一个蓝色的提示块。
</div>

<div style="background-color: #ccffcc; color: #00ff00; padding: 10px; border-radius: 5px;">
这是一个绿色的提示块。
</div>

<div style="background-color: #ffffcc; color: #ffcc00; padding: 10px; border-radius: 5px;">
这是一个黄色的提示块。
</div>

## 定义列表

First Term
: This is the definition of the first term.

Second Term
: This is one definition of the second term.
: This is another definition of the second term.
