## 页面元素操作

在本章开始时，讲过整个页面是一个DOM模型，页面中的各元素通过模型的节点相互关联形成树状，因此，如果在页面中增加某个元素，只需要找到元素的上级节点，通过函数`$(html)`完成元素的创建后，增加到该节点中。


### 创建节点元素

函数`$()`用于动态创建页面元素，其语法格式如下：
```jquery
$(html)
```
其中，参数`html`表示用于动态创建DOM元素的HTML标记字符串，即如果要在页面中动态创建一个`div`标记，并设置其内容和属性，可以加入如下代码：
```jquery
var $div = $("<div title'jQuery理念'>Write Less Do More</div>");$("body").append($div);
```
执行上述代码后，将在页面文档body中创建一个div标记，其内容为"Write Less Do More"，属性title的值为"jQuery理念"。


### 内部插入节点

在页面中动态创建元素需要执行节点的插入或追加操作。而在jQuery中，有多种方法可以实现该功能，`append()`方法仅是其中之一。按照插入元素的顺序来分，可以分为内部和外部两种方法。下面将分别对这些方法进行详细介绍。

内部插入节点的方法如下表：

|语法格式|参数说明|功能描述|
|---|---|---|
|`append(content)`|`content`表示追加到目标中的内容|向所选择的元素内部插入内容|
|`append(function(index,html))`|通过`function`函数返回追加到目标中的内容|向所选择的元素内部插入`function`函数所返回的内容|
|`appendTo(content)`|`content`表示被追加的内容|把所选择的元素追加到另一个指定的元素集合中|
|`prepend(content)`|`content`表示插入到目标元素前面的内容|向所选择的元素前面插入内容|
|`prepend(function(index,html))`|通过`function`函数返回插入到目标前面的内容|向所选择的元素前面插入`function`函数所返回的内容|
|`prependTo(content)`|`content`表示被插入的内容|把所选择的元素插入到另一个指定的元素集合中|

### 外部插入节点

外部插入节点的方法如下表：

|语法格式|参数说明|功能描述|
|---|---|---|
|`after(content)`|`content`表示插入目标元素外部后面的内容|向所选择的元素外部后面插入内容|
|`after(function)`|通过`function`函数返回值插入目标外部后面的内容|向所选择的元素外部后面插入`function`函数所返回的内容|
|`before(content)`|`content`表示插入元素外部前面的内容|向所选择的元素外部前面插入内容|
|`before(function)`|通过`function`函数返回值插入目标外部前面的内容|向所选择的元素外部前面插入`function`函数所返回的内容|
|`insertAfter(content)`|`content`表示插入目标元素外部后面的内容|将所选择的元素插入另一个指定的元素外部后面|
|`insertBefore(content)`|`content`表示插入目标元素外部前面的内容|将所选择的元素插入另一个指定的元素外部前面|


### 复制元素节点

在页面中，有时需要将某个元素节点复制到另外一个节点，在jQuery中，可以通过方法`clone()`轻松实现，该方法的语法格式为：
```jquery
clone()
```
其功能为复制匹配的DOM元素并且选中复制成功的元素。该方法仅是复制元素本身，被复制后的新元素不具有任何元素作为。如果需要在复制时将元素的全部行为也进行复制，可以通过方法`clone(true)`实现，其格式为：
```jquery
clone(true)
```
其中的参数设置为`true`，就可以复制元素的所有事件处理。
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>复制元素节点</title>
		<script src="js/jquery-3.3.1.min.js" type="text/javascript" charset="utf-8"></script>
		<style type="text/css">
			img{border: 1px solid #CCCCCC;padding: 4px;margin: 5px;width: 500px;height: 500px;}
		</style>
		<script type="text/javascript">
			$(function () {
				$("img").click(function () {
					$(this).clone().appendTo("span");
				})
				
			})
		</script>
	</head>
	<body>
		<span id="">
			<img src="img/img01.jpg" title="封面"/>
		</span>
	</body>
</html>
```

### 替换元素节点

在jQuery中，如果要替换元素中的节点，可以使用`replaceWith()`和`replaceAll()`这两种方法，其语法格式如下：
```jquery
replaceWith(content)
```
该方法的功能是将所有选择的元素替换成指定的HTML或DOM元素，其中参数`content`为被所选择元素替换的内容。
```jquery
replaceAll(selector)
```
该方法的功能是将所有选择的元素替换成指定`selector`的元素，其中参数`selector`为需要被替换的元素。
示例如下：
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>替换元素节点</title>
		<script src="js/jquery-3.3.1.min.js" type="text/javascript" charset="utf-8"></script>
		<style type="text/css">
			body {font-size: 14px;}
			span {font-weight: bold;}
			p {background-color: #EEEEEE;padding: 5px; width: 200px;}
		</style>
		<script type="text/javascript">
			$(function () {
				$("#span1").replaceWith("<span title='replaceWith'>隐国蓉</span>");
				$("<span title='replaceWith'>abc@163.com</span>").replaceAll("#span2");
			})
		</script>
	</head>
	<body>
		<p>姓名：<sapn id="span1"></sapn></p>
		<p>邮箱：<sapn id="span2"></sapn></p>
	</body>
</html>
```
`replaceWith()`和`replaceAll()`方法都可以实现元素节点的替换，二者最在的区别在于替换字符的顺序，前者是用括号中的字符替换所选择的元素；后者是用字符串替换括号中所选择的无比。一旦完成替换，被替换元素中的全部事件都将消失。


### 包裹元素节点

在jQuery中，不仅可以通过方法替换元素节点，还可以根据需注包裹某个指定的节点，对节点的包裹也是DOM对象操作中很重要的一项，其与包裹节点相关的全部方法如下表：


|语法格式|参数说明|功能描述|
|---|---|---|
|`wrap(html)`|`html`参数为字符串代码，用于生成元素并包裹所选元素|把所有选择的元素用其他字符串代码包裹起来|
|`wrap(elem)`|`elem`参数用于包装所选元素的DOM元素|把所有选择的元素用其他DOM元素包装起来|
|`wrap(fn)`|`fn`参数为包裹结构的一个函数|把所有选择的元素用`function`函数返回的代码包裹起来|
|`unwrap()`| 无参数|　移除所选元素的父元素或包裹标记|
|`wrapAll(html)`|`html`参数为字符串代码，用于生成元素并包裹所选元素|把所有选择的元素用单个元素包裹起来|
|`wrapAll(elem)`|`elem`参数用于包装所选元素的DOM 元素|把所有选择的元素用单个DOM 元素包裹起来|
|`wrapInner(html)`|`html`参数为字符串代码，用于生成元素并包裹所选元素|把所有选择的元素的子内容( 包括文本节点) 用字符串代码包裹起来|
|`wrapInner(elem)`|`elem`参数用于包装所选元素的DOM 元素|把所有选择的元素的子内容( 包括文本节点) 用DOM 元素包裹起来|
|`wrapInner(fn)`|`fn` 参数为包裹结构的一个函数|把所有选择的元素的子内容( 包括文本节点) 用function 函数返回的代码包裹起来|

上表中，`wrap(html)`和`wrapInner(html)`方法比较常用，前者包裹外部元素，后者包裹元素内部的文本字符 。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>包裹元素节点</title>
		<script src="js/jquery-3.3.1.min.js" type="text/javascript" charset="utf-8"></script>
		<style type="text/css">
			body {font-size: 14px;}
			p {background-color: #EEEEEE;padding: 5px; width: 200px;}
		</style>
		
		<script type="text/javascript">
			$(function () {
				$("p").wrap("<b></b>");
				$("span").wrapInner("<i></i>")
			})
		</script>
	</head>
	<body>
		<p>最喜爱的体育运行：<span>羽毛球</span></p>
		<p>最爱看哪类型图书：<span>网络、技术</span></p>
	</body>
</html>
```

