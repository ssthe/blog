+++
title = "Markdown笔记"
date = 2018-03-21T16:50:30-05:00
tags = ["markdown"]
categories = [""]
draft = false
+++

这是笔者学习[这个文档](http://wowubuntu.com/markdown/#acknowledgement "Markdown 语法说明 \(简体中文版\)")时自己摘抄总结的笔记，去掉了一些详细描述机制的部分，作为方便以后自己查找作为工具使用，请注意所有内容并非原创，均来自<http://wowubuntu.com>

***
# 区块元素
## 换行
使用`<br />`

    第一行<br />
    第二行
使用空格

    第一行（此处后有两个空格）  
    第二行
<br />
## 标题
atx

    ### 我是标题
由一个或多个“#”符号组成  
根据“#”数量的不同分别等价于h1，h2和h3的HTML tag，依此类推  

Setext

    我是h1
    ====================
    我是h2
    --------------------
符号的数量随意。  
<br />
## 区块引用
普通引用

    > This is an expample for blockquotes
    > 这是一个区块引用的例子
    > これはブロック参照の例です
也可以只在每个段落前使用`>`  

    > This is an expample for blockquotes This is an expample for 
    blockquotes This is an expample for blockquotes This is an expample 
    for blockquotes This is an expample for blockquotes
    > 这是一个区块引用的例子 这是一个区块引用的例子 这是一个区块引用的例子 这是一个
    区块引用的例子 这是一个区块引用的例子 这是一个区块引用的例子
    > これはブロック参照の例です これはブロック参照の例です これはブロック参照の例
    です これはブロック参照の例です これはブロック参照の例です これはブロック参照の
    例です
嵌套

    > ### This is an expample for blockquotes
    > > 这是一个区块引用的例子
    > 1. これはブロック参照の例です
所有的markdown语法，包括引用自身，都可以在区块引用内嵌套使用  
<br />
## 列表
无序列表  
使用`+`、`-`或`*`

    + apple
    + banana
    + cactus

    - 苹果
    - 香蕉
    - 仙人掌

    * リンゴ
    * バナナ
    * サボテン
以上三种完全等价  

有序列表
使用罗马数字+英文句点

    1. 苹果
    2. 香蕉
    3. 仙人掌
目前罗马数字的值本身并不影响最后的HTML结果，也就是说这些罗马数字可以取任意值，而最后的结果仍然是顺序列表  

多段落列表

    1.  This is the first paragraph This is the first paragraph This is the
        first paragraph This is the first paragraph This is the first paragraph
        This is the first paragraph
        
        这是第二段 这是第二段 这是第二段 这是第二段 这是第二段 这是第二段 这是第
        二段 这是第二段 这是第二段 这是第二段 这是第二段
    
    2.  This is the second item This is the second item This is the second item
        This is the second item This is the second item This is the second item 
        This is the second item
每个项目下的段落需要缩进四个空格或一个制表符  
<br />
## 代码区块
使用四个空格或者一个制表符

    这是普通的文字
    
        //这是代码区块文字
        System.out.println("你好");
不管是HTML还是Markdown的语法基本上在代码区块里是无效的，也就是说可以使用各种符号而不用担心是否需要转义字符或者其他  
<br />
## 分隔线
使用多个`*`，`_`或`-`，可以选择在其中加入空格
    
    * * *

    ***

    *****

    - - -

    ---------------------------------------
***
# 区段元素
## 链接
行内式

    This is [an example](http://example.com/ "Title") inline link.

    [This link](http://example.net/) has no title attribute.
参考式

    This is [an example][id] reference-style link.
然后在文件任意处添加

    [id]: http://example.com/  "Optional Title Here"
更多用法详见参考  
<br />
## 强调
使用一个`*`或`_`

    *斜体*
    _italic_
使用两个`*`或`_`

    **粗体**
    __bold__
如果`*`或`_`两边都是空白，它们等同于普通符号  
想要literally把文字用这两个符号框起来请使用转义符号`\`
<br />
## 代码
小段行内代码用`` ` ``包起来

    Java uses `System.out.print()` to print on the teminal
而在行内代码包含了`` ` ``的情况下，则用多个`` ` ``来包裹代码内容

    ``This is an exaple for ` in the code section``
当`` ` ``出现在开头或结尾时，请使用空格

    `` `this is sample` ``
<br />
## 图片
行内式

    ![Alt text](/path/to/img.jpg)

    ![Alt text](/path/to/img.jpg "Optional title")
参考式

    ![Alt text][id]
图片参考定义

    [id]: url/to/image  "Optional title attribute"
Markdown暂时不支持定义图片宽高，如有需求请直接使用`<img>`tag
<br />
***
# 其他
## 自动链接
使用`<`和`>`包住链接

    //这是一个网络链接范例
    <https://google.com>

    //这是一个邮箱地址范例
    <example@gmail.com>
<br />
## 反斜杠
反斜杠`\`一如既往做转义符号使用，此处不再赘述  
<br />