---
title: CSS3选择器
description: 汇总了CSS3各类选择器
photos: /assets/img/css3.jpg
date: 2016-10-21 17:26:05
tags: [CSS3选择器,web]
categories: web
---

通配符选择器:
通配选择器的作用就是对页面上所有的元素都生效，
页面上的所有标签都会展示出通配符选择器设定的样式。
这样的弊端就是影响网页渲染的时间。所以不推荐直接使用通配符选择器
``` css
*{
    margin: 0;
    padding: 0;
}
```
 

*** 分组选择器(并集选择器) ***
``` css
html, body, ul, li, ol, dl, dd, dt, p, h1, h2, h3, h4, h5, h6, form, fieldset, legend, img {
    margin:0;
    padding:0;
}
```
--------------------

*** 标签选择器 ***
``` css
h1{
    color: blue;

}
p{
    font-family: 微软雅黑;
    color: cadetblue;
}
```

*** 类选择器: 最常用的选择器 ***
类选择器的单独使用
``` css
.desc{
    border: dashed;
}
```
类选择器和其他形式组合使用
``` css
.desc p{
    color: deeppink;
    font-size: 20px;
}

.desc *{  /**用到了通配符**/
    color: deeppink;
}
```


*** ID选择器 ***

需要注意的是，注意大小写.

不能使用词列表，参考区别2，错误代码如下：
``` csss
#title name{
    font-size: 30px;
}
```
可以和其他选择器结合使用
``` css
#title{
    font-size: 30px;
}
#title .name{
    color: #000;
}
```

*** 后代选择器（包含选择器）***
``` css
.desc p{
    color: deeppink;
    font-size: 20px;
}

.descendant em{
    font-weight: bold;
}
```

*** 子元素选择器 ***
``` css
.child > p > em{
    font-size: 30px;
}
```


*** 相邻选择器 ***
如果需要选择紧接在另一个元素后的元素，而且二者有相同的父元素，可以使用相邻兄弟选择器（Adjacent sibling selector）。
例如，如果要增加紧接在 h1 元素后出现的段落的上边距，可以这样写：
``` css
h1 + p {margin-top:50px;}
```

这个选择器读作：“选择紧接在 h1 元素后出现的段落，h1 和 p 元素拥有共同的父元素”。

*** 属性选择器 ***
页面上所有的超链接标签颜色都会变成红，也可以和其他选择器组合使用

根据一个属性去选择
``` css
.testA a[href] {
    color:red;
}

a[href] {
        color:red;
}
```

根据多个属性去选择
同样也可以和其他选择器组合使用
``` css
a[href][title] {
    font-size: 25px;
}
```

根据具体的属性值去选择，案例如上
``` css
a[href='#'][title='test'] {color: deeppink;}
```
属性与属性值必须匹配
``` css
a[class='aaa bbb']{
    color: chartreuse;
}
```

根据部分属性值选择,即只要该属性中存在指定值得元素都会被选择到

如果忽略了波浪号，则说明需要完成完全值匹配
``` css
p[class~='important']{
    color: red;
}
```

子串匹配属性选择器 : 
分三种
1.选择的属性中，属性值以指定的属性值开头
``` css
a[href ^= 'http://www.apple']{
    color: deeppink;
}
```
2.选择的属性中，属性值以指定的属性值结尾
``` css
a[href $= 'microsoft.com']{
    color: cadetblue;
}
```
3.选择的属性中，属性值存在指定的属性值
``` css
a[href*='www.w3school.com']{
    color: red;
}
```

特定属性选择类型

属性选择器最常见的用途还是匹配语言值
``` css
p[lang|='en']{
    color: red;
}
```

*** 伪类 ***
伪类名对大小写不敏感;
>:active 需要放在 :hover 后边才会生效;
>:hover 需要放在 :link :visited 后边才会生效;
另外伪类也可以和其他选择器结合使用

>a:link {color: #FF0000} 未访问的链接 
>a:visited {color: #00FF00} 已访问的链接 
>a:hover {color: #FF00FF} 鼠标移动到链接上 
>a:active {color: #0000FF} 选定的链接 

>:first-child 伪类来选择元素的第一个子元素

``` css
.wl p:first-child{
    color: red;
}  
```
容易被误解！读法：选用.wl这个类的元素下边第一个p标签，并不是p标签内的第一个元素，与下边样式对比
``` css
.wl p i:first-child{
    font-size: 30px;
}  
```
读法：.wl 类下所有p标签中的第一个 i 标签
``` css
.wl p:first-child i{
    color: #FF00FF;
}  
```

读法：.wl 下边的第一个 p 标签中所有 i 标签
``` css
.wl li:first-child{
    font-family: monospace;
}
```

*** 伪元素 ***
注：也可以和其他选择器结合使用
>:first-line 伪元素:用于向文本的首行设置特殊样式
>:first-line 只能用于块级元素,看页面样式

注：以下属性可以用于伪元素:first-line中

    font
    color
    background
    word-spacing
    letter-spacing
    text-decoration
    vertical-align
    text-transform
    line-height
    clear
``` css
.wl p:first-line {
    color:#ff0000;
    font-variant:small-caps;
}
```

>:first-letter: 处理首字母
>:first-letter 只能用于块级元素,看页面样式

注：以下属性可以用于伪元素:first-letter中

    font
    color
    background
    margin
    padding
    border
    text-decoration
    vertical-align (仅当 float 为 none 时)
    text-transform
    line-height
    float
    clear

``` css
.wl p:first-letter{
    color: chocolate;
}
```
以上两个就构成了多重伪元素

>:before 伪元素 :可以在元素的内容前面插入新内容

``` css
.wl p:before{
    content: url("");
}
.wl p:after{
    content: url("");
}
```

*** 优先级的问题 ***

id选择器优先级 > 类选择器优先级 > 标签选择器优先级