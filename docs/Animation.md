动画
====

CSS3，我们可以创建动画，它可以取代许多网页动画图像，Flash 动画，和 Javascripts。

## CSS3 @keyframes 规则
要创建CSS3动画，你将不得不了解`@keyframes`规则。

`@keyframes`规则是用来创建动画。 `@keyframes`规则内指定一个 CSS样式和动画将逐步从目前的样式更改为新的样式。

**注意：**Internet Explorer 10、Firefox 以及 Opera 支持 `@keyframes` 规则和 animation 属性。
Chrome 和 Safari 需要前缀 -webkit-。

## CSS3 动画
当在`@keyframe`创建动画，把它绑定到一个选择器，否则动画不会有任何效果。

指定至少这两个 CSS3 的动画属性绑定向一个选择器：

* 规定动画的名称
* 规定动画的时长

例子：

    #animated_div {
        animation: animated_div 5s infinite;
        -moz-animation: animated_div 5s infinite;
        -webkit-animation: animated_div 5s infinite;
    }

## CSS3动画是什么？

* 动画是使元素从一种样式逐渐变化为另一种样式的效果。
* 您可以改变任意多的样式任意多的次数。
* 请用百分比来规定变化发生的时间，或用关键词 "from" 和 "to"，等同于 0% 和 100%。
* 0% 是动画的开始，100% 是动画的完成。
* 为了得到最佳的浏览器支持，您应该始终定义 0% 和 100% 选择器。

例子：

	@keyframes animated_div {
		0% {
		    left: 0px;
		}
		20% {
		    left: 50px;
		    background-color: green;
		}
		40% {
		    left: 140px;
		    background-color: red;
		}
		60% {
		    left: 280px;
		    background-color: yellow;
		}
		80% {
		    left: 425px;
		    background-color: blue;
		}
		100% {
		    left: 0px;
		    background-color: pink;
		}
	}

## 常用属性

<table class="reference"> <tbody><tr> <th style="width:30%;">属性</th> <th>描述</th> <th style="width:5%;">CSS</th> </tr> <tr> <td><a href="#" title="CSS3 @keyframes 规则">@keyframes</a></td> <td>规定动画。</td> <td>3</td> </tr> <tr> <td><a href="#" title="CSS3 animation 属性">animation</a></td> <td>所有动画属性的简写属性，除了 animation-play-state 属性。</td> <td>3</td> </tr> <tr> <td><a href="#" title="CSS3 animation-name 属性">animation-name</a></td> <td>规定 @keyframes 动画的名称。</td> <td>3</td> </tr> <tr> <td><a href="#" title="CSS3 animation-duration 属性">animation-duration</a></td> <td>规定动画完成一个周期所花费的秒或毫秒。默认是 0。</td> <td>3</td> </tr> <tr> <td><a href="#" title="CSS3 animation-timing-function 属性">animation-timing-function</a></td> <td>规定动画的速度曲线。默认是 "ease"。</td> <td>3</td> </tr> <tr> <td><a href="#" title="CSS3 animation-delay 属性">animation-delay</a></td> <td>规定动画何时开始。默认是 0。</td> <td>3</td> </tr> <tr> <td><a href="#" title="CSS3 animation-iteration-count 属性">animation-iteration-count</a></td> <td>规定动画被播放的次数。默认是 1。`infinite`是播放无限次</td> <td>3</td> </tr> <tr> <td><a href="#" title="CSS3 animation-direction 属性">animation-direction</a></td> <td>规定动画是否在下一周期逆向地播放。默认是 "normal"。</td> <td>3</td> </tr> <tr> <td><a href="#" title="CSS3 animation-play-state 属性">animation-play-state</a></td> <td>规定动画是否正在运行或暂停。默认是 "running"。可以改为暂停 "paused", 动画可以暂停</td> <td>3</td> </tr> </tbody></table>

### animation的使用
`animation: name duration timing-function delay iteration-count direction fill-mode play-state;`
可以看到后面跟了许多属性

### animation-timing-function
| animation-timing-function参数 | 用法解释                                                                                                                                                                                                                                       |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| linear                        | 动画从头到尾的速度是相同的。                                                                                                                                                                                                                   |
| ease                          | 默认。动画以低速开始，然后加快，在结束前变慢。                                                                                                                                                                                                 |
| ease-in                       | 动画以低速开始。                                                                                                                                                                                                                               |
| ease-out                      | 动画以低速结束。                                                                                                                                                                                                                               |
| ease-in-out                   | 动画以低速开始和结束。                                                                                                                                                                                                                         |
| steps(int,start\|end)         | 指定了时间函数中的间隔数量（步长）。有两个参数，第一个参数指定函数的间隔数，该参数是一个正整数（大于 0）。 第二个参数是可选的，表示动画是从时间段的开头连续还是末尾连续。含义分别如下：1. start：表示直接开始。 2. end：默认值，表示戛然而止。 |
| cubic-bezier(n,n,n,n)         | 在 cubic-bezier 函数中自己的值。可能的值是从 0 到 1 的数值。                                                                                                                                                                                   |


### animation-direction
| animation-direction参数 | 用法解释                                                             |
| ----------------------- | -------------------------------------------------------------------- |
| normal                  | 默认值。动画按正常播放。                                             |
| reverse                 | 动画反向播放。                                                       |
| alternate               | 动画在奇数次（1、3、5...）正向播放，在偶数次（2、4、6...）反向播放。 |
| alternate-reverse       | 动画在奇数次（1、3、5...）反向播放，在偶数次（2、4、6...）正向播放。 |
| initial                 | 设置该属性为它的默认值。请参阅 initial。                             |
| inherit                 | 从父元素继承该属性。请参阅 inherit。                                 |

## 源码

本文中所用例子源码参见
<https://github.com/waylau/css3-tutorial> 中 `samples` 目录下的 animation.html、animation_2.html