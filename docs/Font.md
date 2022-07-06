# 6.font(字体)

以前 CSS3 的版本，网页设计师不得不使用用户计算机上已经安装的字体。

使用 CSS3，网页设计师可以使用他/她喜欢的任何字体。

当你发现您要使用的字体文件时，只需简单的将字体文件包含在网站中，它会自动下载给需要的用户。

您所选择的字体在新的 CSS3 版本有关于`@font-face`规则描述。

您"自己的"的字体是在 CSS3 `@font-face` 规则中定义的。

**注意**：Internet Explorer 9+, Firefox, Chrome, Safari, 和 Opera 支持 **WOFF** (Web Open Font Format) 字体。

Firefox, Chrome, Safari, 和 Opera 支持 **.ttf**(True Type字体)和.otf(OpenType)字体字体类型）。

Chrome, Safari 和 Opera 也支持 **SVG** 字体/折叠。

Internet Explorer 同样支持 **EOT** (Embedded OpenType) 字体。

在 `@font-face` 规则中，您必须首先定义字体的名称（比如 FontAwesome ），然后指向该字体文件 fontawesome-webfont.woff 。

```css
@font-face {
    font-family: 'FontAwesome';
    src: url('fonts/fontawesome-webfont.woff');
}

.font6 {
    font-family: 'FontAwesome', sans-serif;
    font-size: 14px;
    color: pink;
    line-height: 1.3em;
}
```

### @font-face

所有的字体描述和里面的@font-face规则定义：

| 描述符        | 值                                                                                                                                                             | 描述                                                         |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| font-family   | *name*                                                                                                                                                         | 必需。规定字体的名称。                                       |
| src           | *URL*                                                                                                                                                          | 必需。定义字体文件的 URL。                                   |
| font-stretch  | - normal<br>- condensed<br>- ultra-condensed<br>- extra-condensed<br>- semi-condensed<br>- expanded<br>- semi-expanded<br>- extra-expanded<br>- ultra-expanded | 可选。定义如何拉伸字体。默认是 "normal"。                    |
| font-style    | - normal<br>- italic<br>- oblique                                                                                                                              | 可选。定义字体的样式。默认是 "normal"。                      |
| font-weight   | - normal<br>- bold<br>- 100<br>- 200<br>- 300<br>- 400<br>- 500<br>- 600<br>- 700<br>- 800<br>- 900                                                            | 可选。定义字体的粗细。默认是 "normal"。                      |
| unicode-range | *unicode-range*                                                                                                                                                | 可选。定义字体支持的 UNICODE 字符范围。默认是 "U+0-10FFFF"。 |

### line-height

| 值       | 描述                                                 |
| -------- | ---------------------------------------------------- |
| normal   | 默认。设置合理的行间距。                             |
| *number* | 设置数字，此数字会与当前的字体尺寸相乘来设置行间距。 |
| *length* | 设置固定的行间距。                                   |
| *%*      | 基于当前字体尺寸的百分比行间距。                     |
| inherit  | 规定应该从父元素继承 line-height 属性的值。          |

## 源码

本文中所用例子源码参见
<https://github.com/waylau/css3-tutorial> 中 `samples` 目录下的 font.html