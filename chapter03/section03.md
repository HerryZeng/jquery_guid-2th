## 获取和设置元素

### 获取和设置元素内容

在jQuery中，操作元素的内容方法包括`html()`和`text()`。前者与JavaScript中的innerHTML属性类似，即获取或设置元素的HTML内容，后者类似与JavaScript中的innerText属性。即获取或设置元素的文本内容。

`html()`和`text()`方法的区别

|语法格式|参数说明|功能描述|
|---|---|---|
|`html()`|无参数|用于获取元素的HTML内容|
|`html(val)`|val参数为元素的HTML内容|用于设置元素的HTML内容|
|`text()`|无参数|用于获取元素的文本内容|
|`text(val)`|val参数为元素的文本内容|设置元素的文本内容|

`html()`方法仅支持XHTML的文档，不能用于XML文档，而`text()`既支持HTML文档，也支持XML文档。


### 获取和设置元素值

在jQuery中，要获取元素的值通过`val()`方法实现。其语法格式如下：
```jquery
val(val)
```
其中，如果不带参数val，是获取某元素的值 ，反之，则是将参数val的值赋予某元素，即设置元素的值。该方法学用于表单中获取或设置对象的值。
另外，通过`val()`方法还可以获取`select`标记中的多个选项值，其语法格式如下：
```jquery
val().join(",")
```
示例如下：
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>获取或设置元素的值</title>
		<script src="js/jquery-3.3.1.min.js" type="text/javascript" charset="utf-8"></script>
		<style type="text/css">
			body {font-size: 12px; text-align: center;}
			div {padding: 3px; margin: 3px; width: 120px;float: left;}
			.txt {
				border: 1px solid #666666;
				padding: 3px;
			}
		</style>
		
		<script type="text/javascript">
			$(function  () {
				$("select").change(function() {
					var strSel = $("select").val().join(",");
					$("#p1").html(strSel);
				})
				
				$("input").change(function() {
					var strTxt = $(this).val();
					$("#p2").html(strTxt);
				})
				
				$("input").focus(function() {
					$("input").val("");
				})
			})
		</script>
		
	</head>
	<body>
		<div>
			<select multiple="multiple" style="height: 96px;width: 85px;">
				<option value="1">Item 1</option>
				<option value="2">Item 2</option>
				<option value="3">Item 3</option>
				<option value="4">Item 4</option>
				<option value="5">Item 5</option>
				<option value="6">Item 6</option>
				<option value="7">Item 7</option>
			</select>
			<p id="p1"></p>
		</div>
		
		<div >
			<input type="text" class="txt" />
			<p id="p2"></p>
		</div>
	</body>
</html>
```