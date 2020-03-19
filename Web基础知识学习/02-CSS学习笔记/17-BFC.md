@[toc](BFC)

&emsp;&emsp;BFC(Block formatting context)直译为"块级格式化上下文"。它是一个独立的渲染区域，只有Block-level Box参与，它规定了内部的Block-level box如何布局，并且与这个区域外部毫不相干。

# 元素的显示模式
&emsp;&emsp;元素的显示模式（display）分为：块级元素、行内元素和行内块元素。其实它还有很多其他显示模式：

![显示模式](./images/显示模式.png)

# 哪些元素会有BFC的条件
&emsp;&emsp;不是所有的元素模式都能产生BFC，w3c规定：display属性为block、list-item和table的元素会产生BFC。这个BFC有着具体的布局特性：

![box](./images/box.gif)

> 有宽度和高度；有外边距margin；有内边距padding；有边框border。

&emsp;&emsp;要给这些元素添加如下属性就可以触发BFC：

+ float属性不为none
+ position为absolute或fixed
+ display为inline-block, table-cell, table-caption, flex, inline-flex
+ overflow不为visible。

# BFC元素的特性
&emsp;&emsp;BFC布局规则特性：

1. 在BFC中盒子从顶端开始垂直地一个接一个地排列
2. 盒子垂直方向的距离由margin决定，属于同一个BFC的两个相邻盒子的margin会发生重叠
3. 在BFC中，每一个盒子的左外边缘（margin-left）会触碰到容器的左边缘(border-left)（对于从右到左的格式来说，则触碰到右边缘）。
4. BFC的区域不会与浮动盒子产生交集，而是紧贴浮动边缘。
5. 计算BFC的高度时，自然也会检测浮动或者定位的盒子高度。
