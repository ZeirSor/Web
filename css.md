# css基础
<!-- TOC -->

- [1. 样式](#1-样式)
  - [1.1. 行内样式](#11-行内样式)
  - [1.2. 内部样式](#12-内部样式)
  - [1.3. 外部样式](#13-外部样式)
- [2. 选择器](#2-选择器)
  - [2.1. 选择`div`](#21-选择div)
  - [2.2. `id`选择器](#22-id选择器)
  - [2.3. 类选择器](#23-类选择器)
  - [2.4. 伪类选择器](#24-伪类选择器)
    - [2.4.1. 链接伪类选择器](#241-链接伪类选择器)
    - [2.4.2. 位置伪类选择器](#242-位置伪类选择器)
    - [2.4.3. 目标伪类选择器](#243-目标伪类选择器)
  - [2.5. 复合选择器](#25-复合选择器)
  - [2.6. 通配符选择器](#26-通配符选择器)
  - [2.7. 伪元素选择器](#27-伪元素选择器)
  - [2.8. 样式渲染优先级](#28-样式渲染优先级)
- [3. 颜色](#3-颜色)
  - [3.1. 进制](#31-进制)
  - [3.2. RGB](#32-rgb)
  - [3.3. RGBA](#33-rgba)
- [4. 文本](#4-文本)
- [5. 字体](#5-字体)
- [6. 背景](#6-背景)
- [7. 边框](#7-边框)
- [8. 元素展示格式](#8-元素展示格式)
- [9. 内边距和外边距](#9-内边距和外边距)
- [10. 盒子模型](#10-盒子模型)
- [11. 位置](#11-位置)
- [12. 浮动](#12-浮动)
- [13. flex 布局](#13-flex-布局)
- [14. 响应式布局](#14-响应式布局)

<!-- /TOC -->
## 1. 样式

### 1.1. 行内样式

-   直接定义在标签的`sytle`属性中

```html
<img src="/images/mountain.jpg" alt="" style="width: 300px;">
<div style="width: 300px;height: 300px;background-color: lightblue;"></div>
```

### 1.2. 内部样式

-   定义在`<head>`里的`style`标签

```HTML
    <style type="text/css">
        img {
            width: 50%;
        }
    </style>
```

### 1.3. 外部样式

-   外部定义`.css`文件

```css
div {
    width: 100px;
    height: 100px;
    background-color:  lightblue;
    margin: 10px;
}

p {
    width: 50px;
    height: 70px;
    background-color: lightgreen;
}
```

-   在`.html`的`<head>`中用`<link>`引入

```html
    <link rel="stylesheet" href="/css/style1.css" type="text/css">
```

-   注释: 只能用`/* 注释内容 */`

## 2. 选择器

### 2.1. 选择`div`

```css
div {
    width: 100px;
    height: 100px;
    background-color:  lightblue;
    margin: 10px;
}
```

### 2.2. `id`选择器

`css`中

-   用`#`

```css
#mydiv:hover {
    background-color: pink;
}
```

`html`中

-   对应`id`

```html
    <div id="mydiv">mydiv</div>
```

### 2.3. 类选择器

`css`中

-   用`.类`

```css
.red-tag {
    background: red;
}

.big-tag {
    width: 1000px;
    height: 300px;
}
```

`html`中

-   `class="类1 类2 ..."`

```html
    <div class="red-tag big-tag">div 1</div>
    <p class="red-tag">2</p>
    <p class="big-tag">3</p>
```

### 2.4. 伪类选择器

-   用于定义元素的特殊状态

#### 2.4.1. 链接伪类选择器

-   `:link`链接访问前的样式
-   `:visited`链接访问后的样式

```css
a:visited {
    color: green;
}

点击按钮变绿
button:visited {
    color: green;
}
```

-   `:hover`鼠标悬停时的样式

```css
.effect:hover {
    background: lightcoral;	背景色
    transform: scale(1.1);	放大1.1倍
    transition: 200ms;		用200ms来完成放大
}
```

-   `:active`鼠标点击长按时的样式

```css
button:active {
    color: white;
    background-color: chartreuse;
}
```

-   `:focus`聚焦后的样式

```css
input:focus {
    background-color: lightblue;
    width: 100px;	聚焦后长度变长
}
```

#### 2.4.2. 位置伪类选择器

-   `:nth-child(关于n的表达式)`选择是其父标签第n个子元素的所有元素。

```css
p:nth-child(2n + 1) {
    background-color: lightblue;
}
```

#### 2.4.3. 目标伪类选择器

-   `:target`当url指向该元素时生效。
    -   `#`页内标签(`id`)

`html`中

```html
    <a href="#myp">turn to my p</a>
    <p id="myp">my p</p>
```

`css`中

```css
#myp:target {
    transform: scale(1.5);
    color: orange;
    transition: 2s;
}
```

### 2.5. 复合选择器

-   `element1, element2 {}`同时选择元素`element1, element2`
-   `element1.class {}`选择包含某类的`element`元素
-   `element1 + element2 {}`选择紧跟在`element1`后面的`element2`元素
-   `element1 element2 {}`选择`element1`内的所有`element2 {}`元素（找父/祖先）
-   `element1 > element2 {}`选择父标签为`element1`的所有`element2`元素

### 2.6. 通配符选择器

-   `* {}`选择所有标签
-   `XXX[attribute]`选择具有某个属性的标签

```css
input[required] {
    background-color: lightblue;
}

input[id] {
    background-color: lightcoral;
}
```

-   `XXX[attribute=value]`选择属性为特定值的标签

```css
input[type=number] {
    background-color: lightgreen;
}
```

### 2.7. 伪元素选择器

-   `::first-letter`选择第一个字母

```css
p::first-letter {
    color: red;
}
```

-   `::first-line`选择第一行

```css
p::first-line {
    color: green;
}
```

-   `::selection`被选中的内容

```css
p::selection {
    color: yellow;
    background-color: blueviolet;
}
```

-   `::before`元素之前插入


```css
h1::before {
    content: "<<";
    color: red;
}
```

-   `::after`元素之后插入


```css
h1::after {
    content: ">>";
}
```

### 2.8. 样式渲染优先级

-   看权重，越具体权重越大
-   看先后

## 3. 颜色

### 3.1. 进制

-   `#ADE8B3`

### 3.2. RGB

-   `rgb(173, 216, 230)`

### 3.3. RGBA

-   多了一个透明度`rgb(173, 216, 230, 0.5)`

## 4. 文本

-   `text-align`控制行内内容对齐, `right/left/center/justify` 
-   `line-height`行间距

<p style="text-align:center">长度单位</p>

| 单位       | 描述                     |
| :--------- | :----------------------- |
| px         | 像素点                   |
| %          | 相对于父元素的百分比     |
| em         | 相对于当前元素的字体大小 |
| re(用的多) | 相对于根元素的字体大小   |
| vw         | 相对于视窗宽度的百分比   |
| vh         | 相对于视窗高度的百分比   |

-   `letter-spacing`字符间距
-   `text-indent`块元素收首行文本缩进量
-   `text-decoration`修饰线

```css
取消链接下划线
a {
    text-decoration: none;
}
```

-   `tesxt-shadow`文字阴影, `x偏移 y偏移 模糊半径 颜色`, 多个阴影用逗号隔开

```css
p {
    text-shadow: 5p 5px 2px grey,
    5px -5px 2px red;
}
```

## 5. 字体

-   `font-size`字体大小
-   `font-style`, `italic`斜体, `oblique`加粗
-   `font-weight`, 粗细`0-1000`, 一些字体只有`normal`和`bold`
-   `font-family` 给定一个有先后顺序的，由字体名或者字体族名组成的**列表**来为选定的元素设置字体

## 6. 背景

-   `background-color`
-   `background-image`
    -   `url`
    -   `linear-gradient`渐变色
-   `background-size`
-   `background-repeat`
    -   `no-repeat`
    -   `repeat-x`
    -   `repeat-y`
-   `background-position`设置初始位置
-   `background-attachment`固定或滚动

## 7. 边框

-   `boder-style`
    -   `solid`实线
    -   `dotted`虚线
-   `boder-width`边框粗细
-   `boder-color`边框颜色
-   `boder-radius`外边框圆角
    -   `50%`圆形
    -   两个半径为椭圆
-   `boder-collapse`
    -   `collapse`边框合并
    -   `separate`边框间距

## 8. 元素展示格式

-   `display`
    -   `block`
        -   独占一行
        -   `width/height/margin/padding(内边距)`
        -   `width`默认100%
    -   `inline`
        -   共占一行
        -   只有水平的`maigin`和`padding`有效
        -   `width`默认为本身内容宽度
    -   `inline-block`
        -   共占一行
        -   width/height/margin/padding(内边距)
        -   `width`默认为本身内容宽度
    -   可用于`div`和`space`互转
-   `white-space`
    -   处理空白
    -   `nowrap`不换行
    -   `pre`
-   `text-overflow`
    -   溢出内容处理
    -   `ellipsis`
-   `overflow/overflow-x/overflow-y`
    -   `hidden`超出用`...`代替
    -   `auto/scroll/scroll-x/scroll-y`滚轮

```css
overflow: hidden;
text-overflow: ellipsis;
```

## 9. 内边距和外边距

-   `margin`
-   -   上右下左
    -   `length`固定值
    -   `percentage`相对宽度
    -   `auto`
    -   上下外边距重叠取大值
-   `padding`
    -   上右下左
    -   `length`
    -   `percentage`

## 10. 盒子模型

-   `box-sizing`
    -   `content-box`默认值, 设置`border`和`padding`会增加元素的宽高
    -   `border-box`设置`border`和`padding`不会增加元素的宽高, 而是挤压内容区域

## 11. 位置

-   `position`

-   取值
    -   `static` 默认,
        -   从上往下
        -   此时`top`, `right`, `bottom`, `left`和 `z-index `属性无效。
    -   `relative` 相对定位
        -   相对于原来位置, 原来的位置还留着
    -   `absolute`绝对定位
        -   向上找第一个能定位的父元素(非`static`)
    -   `fixed`固定
        -   向上找第一个能定位的父元素(非`static`)
        -   相对于屏幕视窗, 滚动了不会消失
    -   `stiky`
        -   没滚出原始位置正常
        -   滚出原始位置会相对视窗定位

-   属性
    -   `top`向下平移
    -   `bottom`向上平移
    -   `right`向左平移
    -   `left`向右平移
    -   `z-index`值越大越靠上层

## 12. 浮动

-   `float` 常用于把不同的`div`放到同一行; 去掉左右边距
    -   `display`为`inline`或`inline-block`时, 使用`float`会统一变成`block`
    -   取值
        -   `left`
        -   `right`

-   `clear`
    -   强制元上都转移到浮动元素下方
    -   取值
        -   `left`
        -   `right`
        -   `both`


## 13. flex 布局

-   `display:flex`

-   `flex-direction`
    -   `row`按行从左到右
    -   `row-reverse`按行从右到左
    -   `column`按列从上到下
    -   `column-reverse`按列从下到上

-   `flex-warp` 控制单行or多行显示、行的堆叠方向
    
    -   `nowarp`默认值， 不换行
    -   `warp`换行，第一行在上方
    -   `warp-reverse`第一行在下方
    
-   `flex-flow`

    -   属性为`flex-direction`和`flex-wrap`
    -   默认值`row nowarp`

-   `justify-content`

    -   `flex-start`默认值 , 左对齐
    -   `flex-end`右对齐
    -   `space-between`左右两段对齐
    -   `space-around`首尾距离为相邻距离的一半
    -   `space-evenly`所有间隔距离均等

-   `align-items`

    -   `flex-start`主轴起点对齐
    -   `flex-end`主轴终点对齐
    -   `center`侧轴居中
    -   `stretch`铺满容器

-   `align-content`

    -   `flex-start`所有行从垂直轴起点开始填充

    -   `flex-end`所有行从垂直轴末尾开始填充

    -   `center`所有行朝向容器的中心填充

    -   `stretch`拉伸所有行来填满剩余空间

-   `order`

    -   定义`flex`项目的顺序, 值越小越靠前

-   `flex-grow`

    -   增长系数
    -   默认0. 负值无效

-   `flex-shrink`

    -   收缩规则
    -   默认1, 负值无效

-   `flex-basis`

    -   定义了`flex`元素在主轴方向上的初始大小

-   `flex`

    -   `flex-grow`、`flex-shrink`、`flex-basis`的缩写。
    -   `auto`: `flex: 1 1 auto`
    -   `none`: `flex 0 0 auto`

## 14. 响应式布局

 - `media`查询
    - 当屏幕宽度满足特定条件时应用`css`

```css
@media(min-width: 768px) {
    .container {
        width: 960px;
        background-color: lightblue;
    }
}
```

-   [Bootstrap官网]([Bootstrap v5 中文文档 · Bootstrap 是全球最受欢迎的 HTML、CSS 和 JS 前端工具库。 | Bootstrap 中文网 (bootcss.com)](https://v5.bootcss.com/))

