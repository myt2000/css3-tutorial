背景
====

[toc]

CSS3 Background 中包含几个新的背景属性，提供更大背景元素控制。

主要是2个背景属性：

* background-size
* background-origin

您还将学习如何使用多重背景图像。

## background-size 

该属性规定背景图片的尺寸。

在 CSS3 之前，背景图片的尺寸是由图片的实际尺寸决定的。在 CSS3 中，可以规定背景图片的尺寸，这就允许我们在不同的环境中重复使用背景图片。

您能够以像素或百分比规定尺寸。如果以百分比规定尺寸，那么尺寸相对于父元素的宽度和高度。

	.background-size {
	    background: url(images/wl_white.png);
	    background-size: 100px 40px;
	    -moz-background-size: 100px 40px; /* Firefox 3.6 */
	    -webkit-background-size: 100px 40px;
	    background-repeat: no-repeat;
	    padding-top: 40px;
	}


可以限定图片的大小

![](https://wx4.sinaimg.cn/mw2000/007slE0nly1h3w2chmlivj309x0aiwfd.jpg)

### 语法
`background-size: length|percentage|cover|contain;`

| background-size参数 | 使用解释                                                                                                                 |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| length              | 设置背景图片高度和宽度。第一个值设置宽度，第二个值设置的高度。如果只给出一个值，第二个是设置为 **auto**(自动)            |
| percentage          | 将计算相对于**背景定位区域的百分比**。第一个值设置宽度，第二个值设置的高度。如果只给出一个值，第二个是设置为"auto(自动)" |
| cover               | 此时会保持图像的纵横比并将图像缩放成将完全覆盖背景定位区域的最小大小。                                                   |
| contain             | 此时会保持图像的纵横比并将图像缩放成将适合背景定位区域的最大大小。                                                       |




## background-origin

该属性指定了背景图像的位置区域。

content-box, padding-box,和 border-box 区域内可以放置背景图像。

![](https://wx4.sinaimg.cn/mw2000/007slE0nly1h3w1b1fvihj309a05i0to.jpg)


    .background-origin-border {
        width: 250px;
        height: 250px;
        border: 1px dotted green;
        padding: 25px;
        background-image: url('images/border.png');
        background-repeat: no-repeat;
        background-position: left;
        background-origin: border-box;
    }
    
    .background-origin-content {
        width: 250px;
        height: 250px;
        border: 1px dotted green;
        padding: 25px;
        background-image: url('images/border.png');
        background-repeat: no-repeat;
        background-position: left;
        background-origin: content-box;
    }

### 语法

`background-origin: padding-box|border-box|content-box;`

| background-origin参数 | 使用解释                   |
| --------------------- | -------------------------- |
| padding-box           | 背景图像填充框的相对位置   |
| border-box            | 背景图像边界框的相对位置   |
| content-box           | 背景图像的相对位置的内容框 |

![img](https://wx1.sinaimg.cn/mw2000/007slE0nly1h3w2xmixcej309z09ht9v.jpg)

如果设置为`padding-box`就是这个效果

### background-position

| background-position参数                                                                                                                | 描述                                                                                                                                                                                                    |
| :------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1. left top 2. left center 3. left bottom 4. right top 5. right center 6. right bottom 7. center top 8. center center 9. center bottom | 如果仅指定一个关键字，其他值将会是"center"。比如可以设置为`background-position: left top;`                                                                                                              |
| *x% y%*                                                                                                                                | 第一个值是水平位置，第二个值是垂直。左上角是0％0％。右下角是100％100％。如果仅指定了一个值，其他值将是50％。 。默认值为：0％0％                                                                         |
| *xpos ypos*                                                                                                                            | 第一个值是水平位置，第二个值是垂直。左上角是0。单位可以是像素（0px0px）或任何其他 [CSS单位](https://www.runoob.com/try/css-units.html)。如果仅指定了一个值，其他值将是50％。你可以混合使用％和positions |
| inherit                                                                                                                                | 指定background-position属性设置应该从父元素继承                                                                                                                                                         |

## 源码

本文中所用例子源码参见
<https://github.com/waylau/css3-tutorial> 中 `samples` 目录下的 background_size.html、background_origin.html