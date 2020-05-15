---
title: 【一】HTML、CSS快速学习（简化路径）
date: 2020-05-14 10:39:10
tags:
  - html常用快速学习
  - css快速学习
categories:
  - 前端快速学习
description: 快速掌握常用的html和css，适合需要快速入门的小伙伴。
---

HTML：div、label、ol、ul、li、dl、dt、dd、h1、h2、h3、p、input、em、i
CSS：css语法、css盒模型、css定位、css优先级
---------------------------------------------
部分知识引用外部链接：https://www.runoob.com/css/css-tutorial.html

<!-- more -->

<center><h1>HTML、CSS</h1></center>

### HTML常用标签
div、label、span、b、p、ul、ol、li、dl、dt、dd、h1、h2、h3、input、i、em

### CSS语法
 .操作符，使用 class 引用
 #操作符，使用 id 引用


### 基本概念

> #### 层叠式是什么意思？
> - 意思就是再html上披上了华丽的外衣，也就是美化网页

> #### CSS 盒模型
> - margin（外边距）  清楚边框外的区域，外边距是透明的
> - border（边框）      围绕在padding（内边距）外和content（内容）外的边框
> - padding（内边距）清楚内容周围的区域，内边距是透明的
> - content（内容）盒子的内容，显示文字和图像

###### 1. 边框属性
* 边框宽度设置：
  border-width: 5px ;

* border-style 值:
none: 默认无边框
dotted: 定义一个点线边框
dashed: 定义一个虚线边框
solid: 定义实线边框
double: 定义两个边框。 两个边框的宽度和 border-width 的值相同
groove: 定义3D沟槽边框。效果取决于边框的颜色值
ridge: 定义3D脊边框。效果取决于边框的颜色值
inset:定义一个3D的嵌入边框。效果取决于边框的颜色值
outset: 定义一个3D突出边框。 效果取决于边框的颜色值
圆角边框：border-radius: 20px ;

* 边框颜色：
border-color: red ;

* 边框-单独设置各边------(指定不同侧面不同边框)style（样式）也可以换成color（边框颜色）和width（边框宽度）
border-top-style: dotted ;            上
border-right-style: solid ;              右
border-bottom-style: dotted ;       下
border-left-style: solid ;                左


###### 2. 轮廓（outline）属性  **和边框（border）类似
说明--->
轮廓（outline）是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用。
轮廓（outline）属性指定元素轮廓的样式、颜色和宽度。

* 轮廓宽度设置：
outline-width: 2px ;

* 轮廓样式（style）值：
outline-style 值 :
none: 默认无边框
dotted: 定义一个点线边框
dashed: 定义一个虚线边框
solid: 定义实线边框
double: 定义两个边框。 两个边框的宽度和 border-width 的值相同
groove: 定义3D沟槽边框。效果取决于边框的颜色值
ridge: 定义3D脊边框。效果取决于边框的颜色值
inset:定义一个3D的嵌入边框。效果取决于边框的颜色值
outset: 定义一个3D突出边框。 效果取决于边框的颜色值
inherit

* 轮廓的颜色：
  outline-color : blue


###### 3. margin（外边距）
说明--->
margin 清除周围的（外边框）元素区域。margin 没有背景颜色，是完全透明的。
margin 可以单独改变元素的上，下，左，右边距，也可以一次改变所有的属性。

margin - 单边外边距属性
margin-top: 100px ;              设置上边距的属性
margin-right : 20px ;             设置右边距的属性
margin-bottom : 90px ;         设置下边距的属性
margin-left : 50px ;                设置左边距的属性

margin - 简写属性
说明--->
为了缩短代码，有可能使用一个属性中margin指定的所有边距属性。这就是所谓的简写属性。
所有边距属性的简写属性是 margin :
margin属性可以有一到四个值。

下方为从左至右顺序排序--：

四个值时：
margin : 25px 8px 56px 87px ;
上边距为 25px
右边距为 8px
下边距为 56px
左边距为 87px

三个值时：
margin : 67px 43px 90px ; 
上边距为 67px
左右边距为 43px
下边距为 90px

两个值时：
margin : 90px 67px ; 
上下边距为90px
左右边距为 67px

一个值时：
margin : 100px ;
上下左右边距（四边）都为 100px 


###### 4. padding（内边距）

(填充------>>类似与margin（外边距）的操作差不多)

说明：
当元素的 padding（填充）内边距被清除时，^*所释放的区域将会受到元素背景颜色的填充*^。
单独使用 padding 属性可以改变上下左右的填充。

padding - 单边外边距属性
padding-top: 100px ;              设置上边距的属性
padding-right : 20px ;             设置右边距的属性
padding-bottom : 90px ;         设置下边距的属性
padding-left : 50px ;                设置左边距的属性

padding - 简写属性
说明--->
为了缩短代码，有可能使用一个属性中padding指定的所有边距属性。这就是所谓的简写属性。
所有边距属性的简写属性是 padding :
padding属性可以有一到四个值。

----下方为从左至右顺序排序：

四个值时：
padding : 25px 8px 56px 87px ;
上边距为 25px
右边距为 8px
下边距为 56px
左边距为 87px

三个值时：
padding : 67px 43px 90px ; 
上边距为 67px
左右边距为 43px
下边距为 90px

两个值时：
padding : 90px 67px ; 
上下边距为90px
左右边距为 67px

一个值时：
padding : 100px ;
上下左右边距（四边）都为 100px 








> #### CSS定位
> 在默认情况下，相对定位是相对于元素本身所在的位置去定位；绝对定位是相对于左上角坐标原点去定位。
> position 属性指定了元素的定位类型。
> - position 属性的五个值：
> static
> relative
> fixed
> absolute
> sticky
元素可以使用的顶部，底部，左侧和右侧属性定位。然而，这些属性无法工作，除非是先设定position属性。他们也有不同的工作方式，这取决于定位方法。

1. static 定位（静态定位，还是跟随着正常的文本流）
HTML 元素的默认值，即没有定位，遵循正常的文档流对象。
静态定位的元素不会受到 top, bottom, left, right影响。


2. fixed 定位（固定定位）
元素的位置相对于浏览器窗口是固定位置。
即使窗口是滚动的它也不会移动：
```
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
p.pos_fixed
{
	position:fixed;
	top:30px;
	right:5px;
}
</style>
</head>
<body>

<p class="pos_fixed">Some more text</p>
<p><b>注意:</b> IE7 和 IE8 支持只有一个 !DOCTYPE 指定固定值.</p>
<p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p><p>Some text</p>
</body>
```

3. relative 定位（相对定位，在原有基础的位置上没有脱离文档流）
相对定位元素的定位是相对其正常位置。


4. absolute 定位（绝对定位，在原有的基础上脱离了文档流）
绝对定位的元素的位置相对于最近的已定位父元素，如果元素没有已定位的父元素，那么它的位置相对于<html>:


5. sticky 定位（粘性定位，滚动到一定位置的时候会变为固定定位）
position: sticky; 基于用户的滚动位置来定位。
粘性定位的元素是依赖于用户的滚动，在 position:relative 与 position:fixed 定位之间切换。


6. 重要：
重叠的元素
元素的定位与文档流无关，所以它们可以覆盖页面上的其它元素
z-index属性指定了一个元素的堆叠顺序（哪个元素应该放在前面，或后面）
一个元素可以有正数或负数的堆叠顺序：
```
<style>
img
{
      position:absolute;
      left:0px;
      top:0px;
      z-index:-1;
}
</style>
<body>
<h1>This is a heading</h1>
<img src="w3css.gif" width="100" height="140" />
<p>因为图像元素设置了 z-index 属性值为 -1, 所以它会显示在文字之后。</p>
</body>
```




> #### css的优先级

* css优先级规则（1）
接近最中间的祖先样式比其它祖先样式优先级高
示例代码：
```
<!-- 类名为 son 的 div 的 color 为 blue -->
<div style="color: red">
    <div style="color: blue">
        <div class="son"></div>
    </div>
</div>
```

* css优先级规则（2）
直接样式（最中间样式）比祖先样式优先级高
示例代码：
```
<!-- 类名为 son 的 div 的 color 为 blue -->
<div style="color: red">
    <div class="son" style="color: blue"></div>
</div>
```

* css优先级规则（3）
优先级的关系：内联样式（4）>ID选择器（3）>类选择器（2）=属性选择器（2）=伪类选择器（2）>标签选择器（1）=伪元素选择器（1）


* css优先选择器（4）
参照css优先级规则（3）----- 按各个选择器的之和（后面标的数值用来相加）决定它们的优先级，和越大优先级越高，相反，和越小优先级越小
示例代码：
// HTML
```
<div id="con-id">
    <span class="con-span"></span>
</div>

// CSS
#con-id span {
    color: red;
}
div .con-span {
    color: blue;
}
```

最后span的值为red


* css优先选择器（5）
属性后插有 !important 的属性拥有最高优先级，若同时插有 !important，则利用规则3、4判断优先级