# 11.User interface(UI)

增加了一些新的用户界面特性来调整元素尺寸，框尺寸和外边框。

在本章中，您将了解以下的用户界面属性：

- resize
- box-sizing
- outline-offset

**注意**：Firefox、Chrome 以及 Safari 支持 resize 属性。
Internet Explorer、Chrome、Safari 以及 Opera 支持 box-sizing 属性。Firefox 需要前缀 -moz-。
所有主流浏览器都支持 outline-offset 属性，除了 Internet Explorer。

## resize

resize 属性指定一个元素是否应该由用户去调整大小。可以使用 `resize:both`， `resize:vertical` 或者 `resize:horizontal`，用来分别设置元素是可以水平、垂直调整，垂直调整，水平调整。

例子

```css
.div-both {
    border: 1px solid green;
    margin-top: 20px;
    padding: 15px 30px;
    width: 250px;
    resize: both;
    overflow: auto;
}

.div-horizontal {
    border: 1px solid green;
    margin-top: 20px;
    padding: 15px 30px;
    width: 250px;
    resize: horizontal;
    overflow: auto;
}

.div-vertical {
    border: 1px solid green;
    margin-top: 20px;
    padding: 15px 30px;
    width: 250px;
    resize: vertical;
    overflow: auto;
}
```

> 可以拖动文本边框的大小

## box-sizing

box-sizing 允许您以确切的方式定义适应某个区域的具体内容

例子

```css
.box-sizing {
    box-sizing: border-box;
    -moz-box-sizing: border-box; /* Firefox */
    width: 50%;
    border: 1em solid red;
    float: left;
}
```

### 语法

`box-sizing: content-box|border-box|inherit:`

| 值          | 说明                                                                                                                                                                                                                                                                                                     |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| content-box | 默认值。如果你设置一个元素的宽为 100px，那么这个元素的内容区会有 100px 宽，并且任何边框和内边距的宽度都会被增加到最后绘制出来的元素宽度中。                                                                                                                                                              |
| border-box  | 告诉浏览器：你想要设置的边框和内边距的值是包含在 width 内的。也就是说，如果你将一个元素的 width 设为 100px，那么这 100px 会包含它的 border 和 padding，内容区的实际宽度是 width 减 去(border + padding) 的值。大多数情况下，这使得我们更容易地设定一个元素的宽高。<br>**注：**border-box 不包含 margin。 |
| inherit     | 指定 box-sizing 属性的值，应该从父元素继承                                                                                                                                                                                                                                                               |

content-box：指定盒模型为 W3C 标准模型，设置 border、padding 会增加元素 width与 height 的尺寸，即 border 与 padding 相当于是元素的“殖民地”，元素的“土地”、尺寸会增加，为向外延伸。

border-box：指定盒模型为 IE模型（怪异模式），设置 border、padding 不会影响元素 width 与 height 的尺寸，即 border 与 padding 由元素已设空间转变。即空间还是这个空间，只是将部分空余的地方，转变成了其他空间用法而已，为内部转变。

```
设置border与padding与被影响属性值的关系公式：

W3C标准盒模型（conten-box值）【width/height被改变，扩展】
width = content + border + padding;

// 其中，width 为浏览器视窗呈现尺寸，content 为在CSS中设置的元素的 width;

IE怪异盒模型（border-box值）【content被改变，压缩】
content = width - border - padding;

// 其中，width 为在CSS中设置的元素的width;


具体可用浏览器调试看看，多观察观察就懂了。
```

总之：

1.W3C标准盒模型（content-box），border、padding 的设置会破坏元素宽高，必须得重新计算，非常麻烦（除了在IE浏览器，默认就是标准盒模型，所以可以用 box-sizing 来转换）；

2.IE（怪异）盒模型（border-box），border、padding 的设置不会影响元素的宽高，这非常实用（且因为IE盒模型不是标准，所以才有 box-sizing 这个标准属性来设置，将它标准化）【IE6/5 是怪异模型，IE7开始是标准盒模型】

另外的小技巧：【行高的计算】

```css
/* 默认, W3C标准盒模型、 box-sizing: content-box */
<style type="text/css">
    .box {
      width: 200px;
      height: 200px;
      text-align: center;
      border: 10px solid black;
      padding: 15px;
    }
</style>
/* 此时的行高：line-height = height = 200px;*/
/* 【因为行高即内容的高，而内容在这里即元素的高（边框和填充是扩展外部空间的）】 */

/* - - - - - - 分割线 - - - - - - */

/* IE怪异盒模型、box-sizing: border-box; */
<style type="text/css">
    .box {
      width: 200px;
      height: 200px;
      text-align: center;
      border: 10px solid black;
      padding: 15px;
      box-sizing: border-box;
    }
</style>
/* 此时的行高：line-height = height - border*2 - padding*2 = 200px - 10px*2 - 15px*2 = 150px; */
/* 【因为此时，内容的其余空间被边框和填充占用，所以是元素的高减去边框和填充的空间，剩余即为内容空间】 */
```

## outline-offset

outline-offset 属性对轮廓进行偏移，并在超出边框边缘的位置绘制轮廓。

轮廓与边框有两点不同：

- 轮廓不占用空间
- 轮廓可能是非矩形

例子

```css
.outline-offset {
    width: 180px;
    height: 80px;
    border: 1px solid red;
    outline: 1px solid green;
    outline-offset: 20px;
}
```

## 属性

<table class="reference"> <tbody><tr> <th width="28%" align="left">属性</th> <th width="67%" align="left">说明</th> <th width="5%" align="left">CSS</th> </tr> <tr> <td><a href="#">appearance</a></td> <td>允许您使一个元素的外观像一个标准的用户界面元素</td> <td>3</td> </tr> <tr> <td><a href="#">box-sizing</a></td> <td>允许你以适应区域而用某种方式定义某些元素</td> <td>3</td> </tr> <tr> <td><a href="#">icon</a></td> <td>Provides the author the ability to style an element with an iconic equivalent</td> <td>3</td> </tr> <tr> <td><a href="#">nav-down</a></td> <td>指定在何处使用箭头向下导航键时进行导航</td> <td>3</td> </tr> <tr> <td><a href="#">nav-index</a></td> <td>指定一个元素的Tab的顺序</td> <td>3</td> </tr> <tr> <td><a href="#">nav-left</a></td> <td>指定在何处使用左侧的箭头导航键进行导航</td> <td>3</td> </tr> <tr> <td><a href="#">nav-right</a></td> <td>指定在何处使用右侧的箭头导航键进行导航</td> <td>3</td> </tr> <tr> <td><a href="#">nav-up</a></td> <td>指定在何处使用箭头向上导航键时进行导航</td> <td>3</td> </tr> <tr> <td><a href="#">outline-offset</a></td> <td>外轮廓修饰并绘制超出边框的边缘</td> <td>3</td> </tr> <tr> <td><a href="#">resize</a></td> <td>指定一个元素是否是由用户调整大小</td> <td>3</td> </tr> </tbody></table>

## 源码

本文中所用例子源码参见
<https://github.com/waylau/css3-tutorial> 中 `samples` 目录下的 userinterface.html