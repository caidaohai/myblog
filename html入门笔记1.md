# HTML入门笔记
作为一个后端*php*程序员，经常接触到*html*，也写过一些*html*，知道一些简单的诸如*div*可以布局，*span*里面写文字，*a*标签打开新链接；从未有系统性的去了解过html，这次在**饥人谷**跟着方方老师学习*html*，超出预期，入门的课程就学到了不少干货。

## 一、HTML是谁发明的
写了好久的前端和后端代码，竟然连这个问题都没思考过:sweat_smile:，html是由[Tim Berners-Lee](https://baike.baidu.com/item/HTML/97049?fr=aladdin)爵士在1990年发明的,它是标准通用化标记语言SGML的应用。用HTML编写的超文本文档称为HTML文档，它能独立于各种操作系统平台(如UNIX， Windows等)。使用HTML，将所需要表达的信息按某种规则写成HTML文件，通过专用的浏览器来识别，并将这些HTML文件“翻译”成可以识别的信息，即现在所见到的网页。

## 二、HTML起手式该怎么写
```
<!DOCTYPE html>
<html lang="zh-CN">
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<meta http-equiv="X-UA-COMPATIBLE" content="ie=edge">
<title>我的网页</title>
<head>
</head>
<body>

</body>
</html>
```

## 三、常用的表章节标签
1. h1~h6:标题
2. section：章节
3. article：文章
4. main：主要内容
5. aside：旁支内容
6. header：头部
7. footer：脚部

## 四、全局属性有哪些
1. class
2. contenteditable
3. hidden
4. id
5. style
6. tabindex
7. title

## 五、常用的内容标签
1. a: anchor的缩写，超链接
2. strong：强调，显示为加粗
3. em：emphasis的简写，重读，显示为斜体
4. code：此标签通常用来写代码，它能将代码里的字符变成等宽，方便查看ls
5. pre：preview的缩写，用于保留回车，空格和tab键