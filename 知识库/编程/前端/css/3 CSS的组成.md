---
tags:
  - 样式表
  - 设计
  - 浏览器
  - CSS
作者: Acid
---

Css在Web工程中有三种存在形式：外部样式表、内部样式表、内联样式；

### 外部样式表

外部样式表在HTML的link元素中链接(假设css文件名为styles.css)：
 
```html
<link rel="stylesheet" href="styles.css"/>
```

这是将样式表链接到HTML文档的最常用形式。

### 内部样式表

内部样式表包含在HTML中`head`元素内的`style`元素中；

```html
<!doctype html>
<html lang="zh-CN">
	<head>
		<meta charset="utf-8" />
		<title>test</title>
	<style>
		h1,p {
			color= red;
			font-size= bold;
		}
	</style>
	</head>
	<body>
		<h1>测试用html</h1>
		<p>这是一个用来测试内部样式表的html代码</p>
	</body>
</html>
```

### 内联样式

内联样式是影响单个HTML元素的CSS声明，包含在元素的 `style` 属性中;

```html
<!doctype html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8" />
    <title>我的 CSS 测试</title>
  </head>
  <body>
	<!--内联样式在元素中声明-->
    <h1 style="color: blue;background-color: yellow;border: 1px solid black;">
      Hello World!
    </h1>
    <p style="color:red;">这是我的第一个 CSS 示例</p>
  </body>
</html>
```

## 层叠和优先级
---
### 层叠

层叠规则就是在一个CSS文件中，后声明的CSS样式将会覆盖掉先声明的冲突CSS样式，冲突代表着两个选择器选中了同一个HTML元素的情况；

### 优先级

优先级就是当选择器是类名，因为类被认为是更具体的，所以它会覆盖元素名选择器指定的样式，就算位置在样式表较前面。

## CSS结构
---
### 属性与值

CSS语句由属性和值组成：
- **属性**：人类可读的标识符，指示想要更改的样式特征。如`font-size`、`width`、`background-color`；
- **值**：每个指定的属性都有一个值，这个值表示如何对属性施加样式；

一个`属性-值对`称为一个CSS声明，用半角冒号`:`连接二者，多个语句一并成为一个CSS声明块，声明块中的最后一个语句可以不加冒号，但是不推荐这么做。

CSS声明块放入选择器的大括号对中的整体就称为CSS规则集

```css
h1 {
	/*大括号中的所有语句称为CSS声明块*/
	color: blue;
	backgroun-color: yellow;
	/*最后一条语句的冒号是可省的*/
}
/*以上所有代码称为一个CSS规则集*/
```

CSS的属性和值不区分大小写。
## 函数
---
### calc()函数

`calc()`函数允许在 CSS 中进行简单的计算，计算的结果并不是可以事先计算并作为静态值输入的东西。

### Transform 函数

transform的不同取值，如 `rotate()`。

## @规则(at-rules)

@规则提供了CSS应该如何执行或表现的指令，一般形式是一个关键词和一个值：

```CSS
/*将一个样式表导入另一个样式表*/
@import "styles1.css"
```

@media 规则在`媒体查询`中用于为不同的媒体类型/设备应用不同的样式。

`媒体查询`可用于检查许多事情，诸如：

- 视口的宽度和高度
- 设备的宽度和高度
- 方向（手机或平板电脑处于横屏还是竖屏模式？）
- 分辨率

```CSS
body {
  background-color: pink;
}

@media (min-width: 30em) {
  body {
    background-color: blue;
  }
}
```

## 简写属性

font、background、padding、border、margin称为简写属性，它们允许在一行中设置多个属性值，从而节省时间并使代码更整洁。

```CSS
/* 在像 padding 和 margin 这样的 4 值简写语法中，
   数值的应用顺序是上、右、下、左（从顶部顺时针方向）。
   也有其他的简写类型，例如 2 值简写，
   它为顶部/底部设置 padding/margin，然后是左侧/右侧 */
padding: 10px 15px 15px 5px;

```

这一行代码：

```CSS
background: red url(bg-graphic.png) 10px 10px repeat-x fixed;
```

与这五行代码是等价的：

```CSS
background-color: red;
background-image: url(bg-graphic.png);
background-position: 10px 10px;
background-repeat: repeat-x;
background-attachment: fixed;
```

## CSS注释

```CSS
/*CSS注释是这么写的*/
```

## 空白

空白是指实际的空格、制表符和换行符。就像浏览器忽略了 HTML 中的空白一样，浏览器也忽略了 CSS 中的空白。空白的价值在于它可以提高可读性。