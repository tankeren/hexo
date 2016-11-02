---
title: jquery选择器
photos: /assets/img/jquery.jpg
description: 汇总了jquery常用选择器，方便快速操作页面元素
date: 2016-11-01 14:27:11
tags: [jquery,web]
categories: web
---


#### 一，多选，使用“,”  ####
>$("div,span,p.myClass")

#### 二，class 选择，标签加class 组合 ####
>$(".myclass.otherclass") 必须同时满足两个条件
>$("p.myClass"),标签+class 选择

#### 三，子元素下选择,使用“ ”空格 ####
>$('#elementId .myClass')//指定ID元素下进行筛选== 
>$(#elementId).find('.myClass')//

#### 四，a[attr=''] 标签+属性 ####
>$('a[attr]') 

也可以 
>$('a[attr="1"]')

#### 五，$('parent > child ') ####
>$("ul.topnav > li") 

注意与三区别，(E > F)和(E F)都作为后代组合，但是他们有所不同，更具体的是(E > F)它只会选择第一级的后代。

#### 六，$( "prev + next" ) ####
>$("label + input") 

满足 lable 后元素为 input ，并且只能是同级元素（并行）
重要的一点既要考虑下一个相邻兄弟选择器（ prev + next ）和一般兄弟选择器（ prev ~ siblings ）所选择到的元素，必须在同一个父元素下。

#### 七，$('#pre~siblings') ####
 (prev + next) 和 (prev ~ siblings)之间最值得注意的不同点是他们各自的可及之范围。前者只达到紧随的同级元素，后者扩展了该达到跟随其的所有同级元素。

>$("#prev ~ div") 
表示ID 为prev 后所有的同级的DIV元素

