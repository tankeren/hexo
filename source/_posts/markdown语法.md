---
title: markdown语法
date: 2016-11-01 15:49:19
photos:
description: markdown语法笔记
categories: web
tags: [markdown,web]
---

# 浏览效果:  #

*这是斜体*

_这也是斜体_

**粗体**

~~删除线~~


# h1 标题 #
## h2 标题 ##
### h3 标题 ###

> 这里是引用

+ red
+ green



1. one
2. tow
3. three

    

```java
@Deprecated
public interface IUserRepository extends CommonRepository<User, Long> {  
   User findByRoleId(Long roleId);
}
```

*******

[an 链接](http://www.baidu.com)

![Alt 图片](https://avatars1.githubusercontent.com/u/21215160?v=3&u=de550c45aa5fb62c23d38751f6584705c8fd4e02&s=140)

表格

| a | b | c |
| :- | :- | :- |
| 1 | 2 | 3 |


分隔符

---

# 对应源码:  #

```

*这是斜体*

_这也是斜体_

**粗体**

~~删除线~~


#h1 标题#
##h2 标题##
###h3 标题###

> 这里是引用

+ red
+ green



1. one
2. tow
3. three

    

、、、java
@Deprecated
public interface IUserRepository extends CommonRepository<User, Long> {  
   User findByRoleId(Long roleId);
}
、、、

*******

[an 链接](http://www.baidu.com)

![Alt 图片](https://avatars1.githubusercontent.com/u/21215160?v=3&u=de550c45aa5fb62c23d38751f6584705c8fd4e02&s=140)

表格

| a | b | c |
| :- | :- | :- |
| 1 | 2 | 3 |

分隔符
---

```