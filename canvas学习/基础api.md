# 1.canvas 基础用法

```javascript 
	var canvas = document.getElementById(id);
	
	if(canvas.getContext){
		var context = canvas.getContext('2d');
	}else{
		console.log('您的浏览器不支持canvas')
	}
```

## (1). 绘制矩形

```javascript

	// 绘制一个矩形
	context.fillRect(x,y,width,height)
	
	// 绘制一个矩形轮廓
	context.strokeRect(x,y,width,height)
	
	// 将一个清空画布内一个矩形
	context.clearRect(x,y,width,height)
	
```

## (2). 绘制路径
```javascript
	// 新建一条路径，生成之后，图形绘制命令被指向到路径上生成路径。
	begainPath()
	// 绘制一条从当前点到开始点的直线来闭合图形。如果图形是已经闭合了的，即当前点为开始点，该函数什么也不做。
	closePath()
	// 通过线条来绘制图形轮廓。
	stroke()
	// 通过填充路径的内容区域生成实心的图形。
	fill()
	// 将笔触移动到指定的坐标x以及y上。
	moveTo()
	// 绘制一条从当前位置到指定x以及y位置的直线。
	lineTo()
```

## (3). 绘制圆弧
```javascript
	/**
	*  画一个以（x,y）为圆心的以radius为半径的圆弧（圆），
	*  从startAngle开始到endAngle结束，按照anticlockwise给定的方*（默认为顺时针）来生成。
	*/
	arc(x, y, radius, startAngle, endAngle, anticlockwise)
	
	// 根据给定的控制点和半径画一段圆弧，再以直线连接两个控制点。
	arcTo(x1, y1, x2, y2, radius)
	
```
## (5).Path2D 对象
 
 Path2D()

	Path2D()会返回一个新初始化的Path2D对象
	（可能将某一个路径作为变量——创建一个它的副本，或者将一个包含SVG path数据的字符串作为变量）
	
Path2D.addPath(path [, transform])​

	添加了一条路径到当前路径（可能添加了一个变换矩阵）。
	
# 	2. canvas色彩 Colors
```javascript	

	// 设置图形的填充颜色。
	fillStyle = color
	
	// 设置图形轮廓的颜色。
	strokeStyle = color
	
	// 设置全局透明度 (0.0-1.0)
	context.globalAlpha

```
## (1). 线型 Line styles
```javascript
	// 设置绘线的粗细 默认1.0 （需要注意线宽的渲染）
	lineWidth
	
	// 属性 lineCap 的值决定了线段端点显示的样子。
	// 它可以为下面的三种的其中之一：butt，round 和 square。默认是 butt。
	lineCap
	
	// lineJoin 的属性值决定了图形中两线段连接处所显示的样子。
	// 它可以是这三种之一：round, bevel 和 miter。默认是 miter。
	lineJoin 属性的例子
	
	// 接受一个数组，来指定线段与间隙的交替
	setLineDash(Array) 
	
	// 属性设置起始偏移量.
	lineDashOffset  
	
	
```
## (2). 阴影 Shadows
```javascript
	shadowOffsetX = float
	shadowOffsetX 和 shadowOffsetY 用来设定阴影在 X 和 Y 轴的延伸距离，它们是不受变换矩阵所影响的。负值表示阴影会往上或左延伸，正值则表示会往下或右延伸，它们默认都为 0。
	
	shadowOffsetY = float
	shadowOffsetX 和 shadowOffsetY 用来设定阴影在 X 和 Y 轴的延伸距离，它们是不受变换矩阵所影响的。负值表示阴影会往上或左延伸，正值则表示会往下或右延伸，它们默认都为 0。
	
	shadowBlur = float
	shadowBlur 用于设定阴影的模糊程度，其数值并不跟像素数量挂钩，也不受变换矩阵的影响，默认为 0。
	
	shadowColor = color
	shadowColor 是标准的 CSS 颜色值，用于设定阴影颜色效果，默认是全透明的黑色。
```

## (3). Canvas 填充规则

```javascript
	nonzero
	evenodd
```

# 3. canvas 绘制文本
```javascript
	// 绘制文本 maxWidth是可选参数
	fillText(text,x,y,[maxWidth])
	
	// 绘制文本边框
	strokeText(text,x,y,[maxWidth])
```
## (1). 文本样式控制
```
	// 控制文本字体  类似css 的font属性
	font = value
	// 文本的对齐方式
	textAlign = value
	// 基线对齐方式
	textBaseline = value
	// 文本的方向
	direction = value
	
```
## (2) 预测量文本属性
```
	measureText()   // 将返回一个 TextMetrics对象的宽度、所在像素，这些体现文本特性的属性。
```


