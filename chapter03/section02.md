## 元素属性操作

在jQuery中，可以对元素的属性执行获取、设置、删除的操作，通过`attr()`方法可以对元素属性执行获取和设置操作，而`removeAttr()`方法是可以轻松删除某一指定的属性。

### 获取元素的属性

获取元素的属性的语法格式如下：

```juery
attr(name)
```
其中，参数`name`表示属性的名称。下面示例将介绍如何通过调用attr()方法，以及元素属性名称为参数的方式来获取元素的属性的过程

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>获取元素的属性</title>
		<script src="js/jquery-3.3.1.min.js" type="text/javascript" charset="utf-8"></script>
		<style type="text/css">
			body {
				font-size: 12px;
			}
			
			div {
				float: left;
				padding-left: 10px;
			}
			
			img {
				border: 1px solid #CCCCCC;
				padding: 2px;
				float: left;
				width: 500px;
				height: 500px;
			}
		</style>
		<script type="text/javascript">
			$(function  () {
				var strAlt = $("img").attr("src")
				strAlt += "<br/><br/>" + $("img").attr("title")
				$("#divAlt").html(strAlt)
			})
		</script>
	</head>
	<body>
		<img src="img/img01.jpg" title="这是一幅风景画"/>
		<div id="divAlt">
			
		</div>
	</body>
</html>
```

### 设置元素的属性

在页面中，`attr()`方法不仅可以获取元素的属性值，还可以设置元素的属性，其设置属性语法格式如下：
```jquery
attr(key,value)
```
其中，参数`key`表示属性的名称，`value`表示属性的值。如果要设置多个属性，也可以通过`attr()`方法实现，其语法格式如下：
```jquery
attr({key0:value0,key1:value1})
```

示例如下：
```html

```