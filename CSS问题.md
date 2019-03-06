### CSS问题

#### 父容器的高度大于子容器

问题描述

container1 高度大于child-1 加child-2

	<div class="container">
    	<div class="child-1"></div>
     	<div class="child-2"></div>
	</div>


[codepen 地址](https://codepen.io/shadowwalkerzero/pen/ywePBL)


<iframe height="265" width="265px" style="width: 100%;" scrolling="no" title="ywePBL" src="https://codepen.io/shadowwalkerzero/embed/ywePBL/?height=265&theme-id=0&default-tab=result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/shadowwalkerzero/pen/ywePBL/'>ywePBL</a> by shadowwalkerzero
  (<a href='https://codepen.io/shadowwalkerzero'>@shadowwalkerzero</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### 分析问题

块状元素内部的内联元素跟随着一个幽灵空白节点(感觉在后面)，相当于一个宽度为0的字符。child-2 为行内元素，对其方式默认为baseline, 下面的红色区域为文字baseline到文字底部的距离。

### 解决方案
1. 父元素 child-2 line-height: 0px;
2. child-2 font-size: 0px;
3. child-2 vertical-align: middle, top等

### 参考文献
[CSS深入理解vertical-align和line-height的基友关系](https://www.zhangxinxu.com/wordpress/2015/08/css-deep-understand-vertical-align-and-line-height/)


