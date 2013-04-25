---
layout: post
title: "用Markdown写博客"
description: ""
category: blog
tags: Markdown ,Jekyll ,简书 ,Scriptogr.am
---
{% include JB/setup %}

> Markdown 是一种轻量级标记语言，创始人为约翰·格鲁伯（John Gruber）和亚伦·斯沃茨（Aaron Swartz）。它允许人们“使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML(或者HTML)文档”。——[wikipedia](http://zh.wikipedia.org/wiki/Markdown)  

Markdown适合喜欢写出排版精美、清晰易读的文字，而又不愿多花时间修饰调整的人。它的语法简单到你只需要五分钟就可以学会并使用，写一篇文章，大概只需要一两分钟来修改版式和结构，这样使你更能专注于内容的写作。  

我是在选择博客的时候，考虑了那些可能会受影响的因素，同时又为了专注于内容的写作，而不考虑排版一类的事情，了解到了Markdown。博客之所以选择了Jekyll，因为它支持Textile和Markdown两种都比较简单的标记语言，Markdown非常简单简单，而Textile的表格和脚注比较方便，当然，更重要的是，我是个程序员，还是很想自己来通过代码的方式来完成一些自己喜欢的东西。

### Jekyll  
Jekyll是一个简单的免费的Blog生成工具，类似WordPress。但是和WordPress又有很大的不同，原因是Jekyll只是一个生成静态网页的工具，不需要数据库支持。但是可以配合第三方服务,例如Disqus和友言等。而且Jekyll可以免费部署在Github上，还可以绑定自己的顶级域名。

其作者在《[blogging like a hacker](http://tom.preston-werner.com/2008/11/17/blogging-like-a-hacker.html)》中说明过设计Jekyll这个框架的原因:
> My blog would need to be easily customizable; coming from a graphic design background means I’ll always be tweaking the site’s appearance and layout.  
  
>  I feel a lightness now when I’m writing a post. The system is simple enough that I can keep the entire conversion process in my head. The distance from my brain to my blog has shrunk, and, in the end, I think that will make me a better author.  

## 简书
虽然[简书](http://jianshu.io/)内置Rich Text和Markdown两种编辑方式，但Rich Text那堆繁琐的按钮，点来点去的也比较烦，所以简书本身也是推荐Markdown的方式。  

简书提供了一种编辑器的预览模式，左边编辑右边预览，像[muhua](http://mahua.jser.me/)之类的在线编辑器也有这样的功能，如果还是有些许在意你的格式，可以在这里看一下是否有写错的地方。

另外，简书还有两个比较人性化的功能，可以把全部笔记像博客一样发布，也可以全部导出为.md后缀的文件压缩包。

## Scriptogr.am
[Scriptogr.am](Scriptogr.am)可以和Dropbox很好的结合。将Dropbox账号和 Scriptogr.am关联之后Scriptogr.am会在dropbox下面生成Apps/scriptogram/posts文件夹，只要 把.md文件放在posts里面，在Scriptogr.am上点击同步，就会发布成功。

据说还有很多类似的例如[DropPages.com](http://droppages.com/)和[Pancake.io](http://pancake.io/)这样的应用，也可以使用Dropbox免费的发布简单的网站，并未看过，有兴趣的可以自己去尝试。
