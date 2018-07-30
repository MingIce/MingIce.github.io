---
layout: post
title: "BFC和IFC个人理解"
date: 2018-07-30
description: "个人理解"
tag: css笔记 
---


## 正文
  谈谈你对BFC和IFC的理解(是什么？如何产生？有什么作用)
  
#### BFC和IFC是什么？
```
答： 
   BFC也就是块级格式上下文，而IFC则是行内格式上下文。是一个常规流最常见的一个布局形态。可以想像BFC就是一个大箱子，大箱子里面的元素和外面的元素不会产生任何影响和作用
```

#### 如何产生BFC？

```
当html满足一下任何一个条件都会产生BFC
1. float不为none时

2.overflow不为 visible时

3.display的值为table-caption、table-cell、inline-block中的任何一个的时

4.position的值不为relative和static的时（在css3的时候元素在定位为非relative和static的情况会触发，float也是一种定位方式）
```

#### BFC作用

```
不和浮动元素进行重叠，清除外部浮动，阻止浮动元素覆盖。

（如果浮动元素后面跟着一个非浮动元素，那么将会产生重叠现象，常规流（标准流、普通流）是一个文档在被显示时最常见的布局形态，而float不为none、position是fixed和absolute的时候元素将脱离标准流）
```
