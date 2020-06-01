---
layout: post
title: First Create Git Page
date: 2020-06-01
tags: blog
---

Well. Finally got around to putting this old website together. Neat thing about it - powered by [Jekyll](http://jekyllrb.com) and I can use Markdown to author my posts. It actually is a lot easier than I thought it was going to be.

marldown語法
---
行內HTML
---
Markdown的語法有個主要的目的：用來作為一種網路內容的寫作用語言。

This is a regular paragraph.

<table>
    <tr>
        <td>Foo</td>
        <td>Add</td>
    </tr>
</table>

This is another regular paragraph.

區塊元素
---
段落和換行    
使用空白和空行來進行段落分行

標題Setext和atx形式  
Setext

`This is an H1`  
`========`  
`This is an H2`  
`-------------`  

atx
在行首插入1到6個`#`
# This is an H1
## This is an H2
###### This is an H6
清單
*   Red
*   Green
*   Blue


區段元素
---
連結

This is \[an example\]\(http://example.com/ "Title"\) inline link.

\[This link\]\(http://example.net/) has no title attribute.

This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.

強調

\*single asterisks* = *single asterisks*

\_single underscores_ = _single underscores_

\**double asterisks** = **double asterisks**

\__double underscores_ = __double underscores__

程式碼

如果要標記一小段行內程式碼，你可以用反引號把它包起來（`

Use the \`printf()\`  function.

Use the `printf()` function.

圖片

![Alt text](/img/smile.png)

![Alt text](/path/to/img.jpg "Optional title")
