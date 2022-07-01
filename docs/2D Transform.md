2D 转换
====

CSS3 2D转换，我们可以斜拉(skew)，缩放(scale)，旋转(rotate)以及位移(translate)元素。



**注意：** Internet Explorer 10, Firefox, 和 Opera支持transform 属性。Chrome 和 Safari 要求前缀 -webkit- 版本。
Internet Explorer 9 要求前缀 -ms- 版本.

常用 2D 变换方法：

* translate()
* rotate()
* scale()
* skew()
* matrix()

## translate()

translate()方法，根据左(X轴)和顶部(Y轴)位置给定的参数，从当前元素位置移动

    .translate {
        transform: translate(50px, 100px);
        -ms-transform: translate(50px, 100px); /* IE 9 */
        -webkit-transform: translate(50px, 100px); /* Safari and Chrome */
    }
    
## rotate()

rotate()方法，在一个给定度数沿着元素中心顺时针旋转的元素。负值是允许的，这样是元素逆时针旋转。

    .rotate
    {
        transform:rotate(30deg);
        -ms-transform:rotate(30deg); /* IE 9 */
        -webkit-transform:rotate(30deg); /* Safari and Chrome */
    }
        
## scale()

scale()方法，该元素增加或减少的大小，取决于宽度（X轴）和高度（Y轴）的参数：

    .scale
    {
        transform: scale(2,4);
        -ms-transform: scale(2,4); /* IE 9 */
        -webkit-transform: scale(2,4); /* Safari and Chrome */
    }
    
## skew()

skew()方法，该元素会根据横向（X轴）和垂直（Y轴）线参数给定角度：

    .skew
    {
        transform:skew(30deg,20deg);
        -ms-transform:skew(30deg,20deg); /* IE 9 */
        -webkit-transform:skew(30deg,20deg); /* Safari and Chrome */
    }
    
skewX(30deg) 如下图：

![](../images/skewx.jpg)

skewY(10deg) 如下图：

![](../images/skewy.jpg)

skew(30deg, 10deg) 如下图：
        
![](../images/skew.jpg)
## matrix()

matrix()方法和2D变换方法合并成一个。

matrix 方法有六个参数，包含旋转，缩放，移动（平移）和倾斜功能。

    .matrix
    {
        transform:matrix(0.866,0.5,-0.5,0.866,0,0);
        -ms-transform:matrix(0.866,0.5,-0.5,0.866,0,0); /* IE 9 */
        -webkit-transform:matrix(0.866,0.5,-0.5,0.866,0,0); /* Safari and Chrome */
    }

**2D变换矩阵**
总共有6个可动的参数，这六个参数分别控制不同的变换
| a b 0 |
| c d 0 |
| tx ty 1 |

a 水平缩放
b 水平拉伸
c 垂直拉伸
d 垂直缩放
tx 水平位移
ty 垂直位移
当矩阵为1的单元矩阵的时候，表明该图形没有变换

**同等效果**
缩放：scale(sx, sy) 等同于 matrix(sx, 0, 0, sy, 0, 0);
平移：translate(tx, ty) 等同于 matrix(1, 0, 0, 1, tx, ty);
旋转：rotate(deg) 等同于 matrix(cos(deg), sin(deg), -sin(deg), cos(deg), 0, 0);
拉伸：skew(degx, degy) 等同于 matrix(1, tan(degy), tan(degx), 1, 0, 0);
> matrix参考文档地址：https://www.jianshu.com/p/5830fe9d18ed


## 源码

本文中所用例子源码参见
<https://github.com/waylau/css3-tutorial> 中 `samples` 目录下的 2d_transform.html

## 参考
* <http://www.zhangxinxu.com/wordpress/2012/06/css3-transform-matrix-%E7%9F%A9%E9%98%B5/>