## 元素样式的操作

在页面中，元素样式的操作包含：直接设置样式、增加CSS类别、类别切换、删除类别

### **直接设置元素样式值**

在jQuery中，可以通过`css()`方法为某个指定的元素设置样式值 ，其语法格式如下：
```jquery
css(name,value)
```
其中`name`为样式名称，`value`为样式的值 

### **增加元素CSS类别**

通过`addClass()`方法增加元素类别的名称，其语法格式如下:
```jquery
addClass(class)
```
其中，参数`class`为类别的名称，也可以增加多个类别的名称，只需要用空格将其隔开即可，其语法格式如下：
```jquery
addClass(class0 class1...)
```

### **切换元素CSS类别**
通过`toggleClass()`方法切换不同的元素类别，其语法如下：
```jquery
toggleClass(class)
```
其中，参数`class`为类型名称，其功能是当元素中含有名称为`class`的CSS类别时，删除该类型，否则增加一个该名称的CSS类别 。

示例如下：
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>类别切换</title>
		<script src="js/jquery-3.3.1.min.js" type="text/javascript" charset="utf-8"></script>
		<style type="text/css">
			.clsImg {border: 1px solid #666666; padding: 5px;}
		</style>
		<script type="text/javascript">
			$(function  () {
				$("img").click(function  () {
					$(this).toggleClass("clsImg");
				})
			})
		</script>
	</head>
	<body>
		<img src="img/img01.jpg"/>
	</body>
</html>
```

### **删除元素CSS类别**

与增加类别的`addClass()`方法相对应，`removeClass()`方法则用于删除类别，其语法如下：
```jquery
removeClass([class])
```
其中，参数`class`为类别名称，该名称是可选。当选该名称时，删除名称是`class`的类别，有多个类别时用空格隔开，如不选名称，则删除元素中所有类别。

