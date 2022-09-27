# css基础

## 样式

### 行内样式

-   直接定义在标签的`sytle`属性中

```html
<img src="/images/mountain.jpg" alt="" style="width: 300px;">
<div style="width: 300px;height: 300px;background-color: lightblue;"></div>
```

### 内部样式

-   定义在`<head>`里的`style`标签

```HTML
    <style type="text/css">
        img {
            width: 50%;
        }
    </style>
```

### 外部样式

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

## 选择器

### 选择`div`

```css
div {
    width: 100px;
    height: 100px;
    background-color:  lightblue;
    margin: 10px;
}
```

### `id`选择器

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

### 类选择器

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

### 伪类选择器

-   用于定义元素的特殊状态

#### 链接伪类选择器

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

#### 位置伪类选择器

-   `:nth-child(关于n的表达式)`选择是其父标签第n个子元素的所有元素。

```css
p:nth-child(2n + 1) {
    background-color: lightblue;
}
```

#### 目标伪类选择器

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

### 复合选择器

-   `element1, element2 {}`同时选择元素`element1, element2`
-   `element1.class {}`选择包含某类的`element`元素
-   `element1 + element2 {}`选择紧跟在`element1`后面的`element2`元素
-   `element1 element2 {}`选择`element1`内的所有`element2 {}`元素（找父/祖先）
-   `element1 > element2 {}`选择父标签为`element1`的所有`element2`元素

### 通配符选择器

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

### 伪元素选择器

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

### 样式渲染优先级

-   看权重，越具体权重越大
-   看先后

## 颜色

### 16进制

-   `#ADE8B3`

### RGB

-   `rgb(173, 216, 230)`

### RGBA

-   多了一个透明度`rgb(173, 216, 230, 0.5)`



