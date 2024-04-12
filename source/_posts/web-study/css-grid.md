---
layout: _posts
title: css-网格布局（Grid）
date: 2024-04-03 10:13:24
category: web css
tags:
  - CSS
  - 学习记录
---

### 基础概念

#### 容器和项目
  采用网格布局的区域，称为"容器"（container）。容器内部采用网格定位的子元素，称为"项目"（item）。
  ``` html 
  <div>
    <div><p>1</p></div>
    <div><p>2</p></div>
    <div><p>3</p></div>
  </div>
  ```
  上面代码中，最外层的< div>元素就是容器，内层的三个< div>元素就是项目。

  
  <font color=Red>注意</font>：项目只能是容器的顶层子元素，不包含项目的子元素，比如上面代码的< p>元素就不是项目。Grid 布局只对项目生效。

  #### 行和列
  容器里面的水平区域称为"行"（row），垂直区域称为"列"（column）。

  #### 单元格
  行和列的交叉区域，称为"单元格"（cell）。

  正常情况下，<font color='#9932CC'>n</font>行和<font color='#9932CC'>m</font>列会产生<font color='#9932CC'>n x m</font>个单元格。比如，3行3列会产生9个单元格。

  #### 网格线
  划分网格的线，称为"网格线"（grid line）。水平网格线划分出行，垂直网格线划分出列。

  正常情况下，<font color='#9932CC'>n</font>行有<font color='#9932CC'>n + 1</font>根水平网格线，<font color='#9932CC'>m</font>列有<font color='#9932CC'>m + 1</font>根垂直网格线，比如三行就有四根水平网格线。

  ### 容器属性

  #### display：容器布局模式

  - display: grid  容器作为块状元素
 
  - display: inline-grid;  容器作为行内元素
  <font color=Red>注意</font>:设为网格布局以后，容器子元素（项目）的float、display: inline-block、display: table-cell、vertical-align、column-*、width和height等设置都将失效。
  #### grid-template-columns、grid-template-rows：列宽和行高设置

  - px,具体数值
  > grid-template-columns: 100px 100px 100px; 每列列宽为100px

  - %,百分比
  > grid-template-columns: 33.33% 33.33% 33.33%; 每列列宽为33.33%

  - fr,份数
  > grid-template-columns: 1fr 1fr 1fr; 每列列宽为1份

  - repeat(n, m), 重复函数(n为重复次数，m为重复内容)
  > grid-template-columns: repeat(3, 33.33%); 共3列，每列列宽为33.33%
  > grid-template-columns: repeat(3, 1fr); 共3列，每列列宽为1份
  > grid-template-columns: repeat(2, 100px 20px 80px); 共2列，每列列宽为100px、20px、80px（实际显示6列）
  > grid-template-columns: repeat(auto-fill, 100px); 自由列数，每列100px，具体多少列由容器宽度决定

  - minmax(min,max)，区间（min为最小值，max为最大值）
  > grid-template-columns: 1fr 1fr minmax(100px, 1fr); 第三列最小为100px，最大为1分宽度

  - auto，自由宽度
  > grid-template-columns: 100px auto 100px; 第二列由浏览器自己决定长度

  #### grid-row-gap，grid-column-gap，grid-gap： 间距设置

  - grid-gap: < grid-row-gap> < grid-column-gap>; 行间距和列间距

  #### grid-auto-flow：布局方向设置

  - grid-auto-flow: column; 先行后列
  - grid-auto-flow: row; 先列后行

  #### justify-items，align-items，place-items：项目元素对齐方式（垂直方向与水平方向）

  - place-items: < align-items> < justify-items>; 垂直方向与水平方向
  - justify-items: start; 对齐单元格的起始边缘
  - justify-items: end; 对齐单元格的结束边缘
  - justify-items: center; 单元格内部居中
  - justify-items: stretch; 拉伸，占满单元格的整个宽度（默认值）

  #### justify-content，align-content，place-content：内容区的对齐方式（垂直方向与水平方向）

  - place-content: < align-content> < justify-content> ; 垂直方向与水平方向
  - justify-content: start ; 对齐容器的起始边框。
  - justify-content: end; 对齐容器的结束边框。
  - justify-content: center; 容器内部居中。
  - justify-content: stretch; 项目大小没有指定时，拉伸占据整个网格容器。
  - justify-content: space-around; 每个项目两侧的间隔相等。所以，项目之间的间隔比项目与容器边框的间隔大一倍。
  - justify-content: space-between; 项目与项目的间隔相等，项目与容器边框之间没有间隔。
  - justify-content: space-evenly; 项目与项目的间隔相等，项目与容器边框之间也是同样长度的间隔。

  ### 项目属性

  #### grid-column-start，grid-column-end，grid-row-start，grid-row-end：设置项目定位在哪根网格线（垂直方向与水平方向）
  
  - grid-column: < grid-column-start> < grid-column-end>; 左边框所在的垂直网格线与右边框所在的垂直网格线
  - grid-row: < grid-row-start> < grid-row-end>; 上边框所在的水平网格线与下边框所在的水平网格线
  - grid-column-start: 1; 设置左边框在1号垂直网格线
  - grid-column-end: 3; 设置右边框在3号垂直网格线
  - grid-row-start: 2; 设置上边框在2号水平网格线
  - grid-row-end: 4; 设置下边框在4号水平网格线

  #### justify-self，align-self，place-self：项目内容位置设置（垂直方向与水平方向）

  - place-self: < align-self> < justify-self>; 垂直方向与水平方向
  - justify-self: start; 对齐单元格的起始边缘
  - justify-self: end; 对齐单元格的结束边缘
  - justify-self: center; 单元格内部居中
  - justify-self: stretch; 拉伸，占满单元格的整个宽度（默认值）

  ### 参考链接
  ```
  https://www.ruanyifeng.com/blog/2019/03/grid-layout-tutorial.html
  ```


