多列
====

CSS3 多列再需要设计多个布局时是非常有用的。比如，报纸布局。

主要属性如下：

* column-count ： 指定元素的列数
* column-rule ： 设置列之间的宽度，样式和颜色
* column-gap ： 指定的列之间的差距

例子：

```css
.newspaper {
    column-count: 3;
    -moz-column-count: 3; /* Firefox */
    -webkit-column-count: 3; /* Safari and Chrome */

    column-gap: 40px;
    -moz-column-gap: 40px; /* Firefox */
    -webkit-column-gap: 40px; /* Safari and Chrome */

    column-rule: 4px outset #ff00ff;
    -moz-column-rule: 4px outset #ff00ff; /* Firefox */
    -webkit-column-rule: 4px outset #ff00ff; /* Safari and Chrome */
}
```

## 属性

<table width="100%" class="reference"> <tbody><tr> <th width="28%" align="left">属性</th> <th width="67%" align="left">说明</th> <th width="5%" align="left">CSS</th> </tr> <tr> <td><a href="#">column-count</a></td> <td>指定元素应分为的列数</td> <td>3</td> </tr> <tr> <td><a href="#">column-fill</a></td> <td>指定如何填充列</td> <td>3</td> </tr> <tr> <td><a href="#">column-gap</a></td> <td>指定列之间差距</td> <td>3</td> </tr> <tr> <td><a href="#">column-rule</a></td> <td>一个用于设置所有列规则的简写属性</td> <td>3</td> </tr> <tr> <td><a href="#">column-rule-color</a></td> <td>指定的列之间颜色规则</td> <td>3</td> </tr> <tr> <td><a href="#">column-rule-style</a></td> <td>指定的列之间的样式规则</td> <td>3</td> </tr> <tr> <td><a href="#">column-rule-width</a></td> <td>指定的列之间的宽度规则</td> <td>3</td> </tr> <tr> <td><a href="#">column-span</a></td> <td>指定一个元素应该横跨多少列</td> <td>3</td> </tr> <tr> <td><a href="#">column-width</a></td> <td>指定列的宽度</td> <td>3</td> </tr> <tr> <td><a href="#">columns</a></td> <td>缩写属性设置列宽和列数</td> <td>3</td> </tr> </tbody></table>

指定列数 `column-count: 4;`

指定列之间的宽度：`column-gap:100px;`

效果图

![](https://wx3.sinaimg.cn/mw2000/007slE0nly1h3x0nstynej31hc05n0z0.jpg)

### column-rule

语法：

`column-rule: *column-rule-width column-rule-style column-rule-color*;`

| 值                                                                                  | 说明                   |
| ----------------------------------------------------------------------------------- | ---------------------- |
| *[column-rule-width](https://www.runoob.com/cssref/css3-pr-column-rule-width.html)* | 设置列中之间的宽度规则 |
| *[column-rule-style](https://www.runoob.com/cssref/css3-pr-column-rule-style.html)* | 设置列中之间的样式规则 |
| *[column-rule-color](https://www.runoob.com/cssref/css3-pr-column-rule-color.html)* | 设置列中之间的颜色规则 |

## 源码

本文中所用例子源码参见
<https://github.com/waylau/css3-tutorial> 中 `samples` 目录下的 multiple_columns.html
