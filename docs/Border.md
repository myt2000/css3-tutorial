# 5. border(边框)

[toc]

CSS3 Border（边框）主要有以下属性：

* border-radius
* box-shadow
* border-image

**注意**：Internet Explorer 9+ 支持 border-radius 和 box-shadow 属性。Firefox、Chrome 以及 Safari 支持所有新的边框属性。
对于 border-image，Safari 5 以及更老的版本需要前缀 -webkit-。
Opera 支持 border-radius 和 box-shadow 属性，但是对于 border-image 需要前缀 -o-

## border-radius （圆角边框）

在 CSS3 中，border-radius 属性用于创建圆角

border-radius 允许你设置元素的外边框圆角。当使用一个半径时确定一个圆形，当使用两个半径时确定一个椭圆。这个(椭)圆与边框的交集形成圆角效果。

border-radius 属性是一个最多可指定四个 **border-\*-radius** 属性的复合属性

	.border_radius {
	    border: 2px solid;
	    font-size: 14px;
	    color: #ffffff;
	    font-weight: bold;
	    padding: 10px;
	    background: #6AAFCF;
	    border-radius: 25px;
	    -moz-border-radius: 25px; /* For Firefox Browser */
	    -webkit-border-radius: 25px; /* For Safari and Google Chrome Browser */
	    -o-border-radius: 25px /* For Opera Browser */
	}

### 语法

`border-radius: *1-4 length*|*%* / *1-4 length*|*%*;`

> 注意：每个半径的四个值的顺序是：**左上角，右上角，右下角，左下角**。如果省略左下角，右上角是相同的。如果省略右下角，左上角是相同的。如果省略右上角，左上角是相同的。

| 值       | 描述                  |
| :------- | :-------------------- |
| *length* | 定义弯道的形状。      |
| *%*      | 使用%定义角落的形状。 |



```css
border-radius: 1em/5em;

/* 等价于： */

border-top-left-radius:     1em 5em;
border-top-right-radius:    1em 5em;
border-bottom-right-radius: 1em 5em;
border-bottom-left-radius:  1em 5em;
```



```css
border-radius: 4px 3px 6px / 2px 4px;

/* 等价于： */

border-top-left-radius:     4px 2px;
border-top-right-radius:    3px 4px;
border-bottom-right-radius: 6px 2px;
border-bottom-left-radius:  3px 4px;
```



通过实验得出

`border-radius: 20px 0 / 50px;`

这个切的角是左上和右下， 椭圆内部20px是x轴的半径长度，50px是y轴的半径长度



## box-shadow （边框阴影）

在 CSS3 中，box-shadow 用于向方框添加阴影：

box-shadow属性可以设置一个或多个下拉阴影的框。

    .box_shadow {
        font-size: 14px;
        color: #ffffff;
        font-weight: bold;
        padding: 10px;
        background: #6AAFCF;
        -moz-box-shadow: 15px 15px 5px #888245; /* For Firefox/Mozilla */
        -webkit-box-shadow: 15px 15px 5px #888245; /* For Google Chrome and Safari */
        -o-box-shadow: 15px 15px 5px #888245; /* For Opera */
        box-shadow: 15px 15px 5px #888245;
    }

### 语法

`box-shadow: *h-shadow v-shadow blur spread color* inset;`

> **注意：**boxShadow 属性把一个或多个下拉阴影添加到框上。该属性是一个用逗号分隔阴影的列表，每个阴影由 2-4 个长度值、一个可选的颜色值和一个可选的 inset 关键字来规定。省略长度的值是 0。

|            | 说明                                                                                                     |
| :--------- | :------------------------------------------------------------------------------------------------------- |
| *h-shadow* | 必需的。水平阴影的位置。允许负值                                                                         |
| *v-shadow* | 必需的。垂直阴影的位置。允许负值                                                                         |
| *blur*     | 可选。模糊距离                                                                                           |
| *spread*   | 可选。阴影的大小(在元素周围阴影的范围，10px就是周围有10px大小的阴影环绕)                                 |
| *color*    | 可选。阴影的颜色。在[CSS颜色值](https://www.runoob.com/cssref/css_colors_legal.aspx)寻找颜色值的完整列表 |
| inset      | 可选。从外层的阴影（开始时）改变阴影内侧阴影                                                             |



`box-shadow: 5px 5px 5px #85b8c7;`中

第一个参数：阴影水平移动的位置，正值向右

第二个参数：阴影垂直移动的位置，正值向左

第三个参数：阴影的模糊（blur）程度

第四个参数：阴影颜色



## border-image （边框图片）

通过 CSS3 的 border-image 属性，您可以使用图片来创建边框：

```css
.border_image {
    /* border-width: 30px;  chrome浏览器无意义 */
            border: 20px solid transparent;
    -moz-border-image: url(/images/border.png) 30 30 round; /* Firefox */
    -webkit-border-image: url(/images/border.png) 30 30 round; /* Safari and Chrome */
    -o-border-image: url(/images/border.png) 30 30 round; /* Opera */
    border-image: url(/images/border.png) 30 30 round;
}
```

### 语法

`border-image: source slice width outset repeat|initial|inherit;`

| border-image参数                                                                        | 用法解释                                                                                     |
| :-------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------- |
| *[border-image-source](https://www.runoob.com/cssref/css3-pr-border-image-source.html)* | 用于指定要用于绘制边框的图像的位置                                                           |
| *[border-image-slice](https://www.runoob.com/cssref/css3-pr-border-image-slice.html)*   | 图像边界向内偏移(试了下，实际是border的图片上下向内拉伸或压缩，元素左右的效果也会拉伸或压缩) |
| *[border-image-width](https://www.runoob.com/cssref/css3-pr-border-image-width.html)*   | 图像边界的宽度                                                                               |
| *[border-image-outset](https://www.runoob.com/cssref/css3-pr-border-image-outset.html)* | 用于指定在边框外部绘制 border-image-area 的量                                                |
| *[border-image-repeat](https://www.runoob.com/cssref/css3-pr-border-image-repeat.html)* | 用于设置图像边界是否应重复（repeat）、拉伸（stretch）或铺满（round）。                       |

`border-image: url(/images/border.png) 30 30 round;`

第一个参数：border图片的路径

第二个参数：边界向内的偏移量

第三个参数：图像的宽度，主要指横轴

第四个参数：图片是重复（repeat）、拉伸（stretch）或铺满（round）

## 源码

本文中所用例子源码参见
<https://github.com/waylau/css3-tutorial> 中 `samples` 目录下的 border.htm