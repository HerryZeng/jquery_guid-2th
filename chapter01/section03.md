## jQuery程序的代码风格


### '$'美元符的使用

在jQuery程序中，使用最多的是`$`美元符了，无论是页面元素的选择、功能函数的前缀都须使用该符号，可以说它是jQuery程序的标志。如下代码：
```jquery
$("#tip").html("Hello World!").show(1000);
```
上述代码表示1000毫秒后，在ID为`tip`的元素中显示`Hello World!`。

### 事件操作链接式书写

在编写页面的某元素事件时，jQuery程序可以使用链接式的方式编写该元素的所有事件。为了更好地说明该书写方法的使用，我们通过一示例加以阐述。
**示例说明**
在页面中增加两个`div`元素，一个为框架，另一who标题。框架元素包含标题和内容元素。当页面首次加载时，被包含的内容`div`标记是不可见的，当用户单击主题`div`标记时，改变自身的背景色，并将内容`div`标记显示出来。

```html<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>事件的链式写法</title>
		<style type="text/css">
			.iframe {
				border: 1px solid #888;
				font-size: 14px;
			}
			.title {
				padding: 6px;
				background-color: #eee;
			}
			.content {
				padding: 8px 0;
				font-size: 18px;
				text-align: center;
				display: none;
			}
			.curcol {
				background-color: #ccc;
			}
		</style>
		<script src="js/jquery-3.3.1.min.js"></script>
		<script type="text/javascript">
			$(function() {
				$(".content").html("你好!,欢迎来到jQuery的精彩世界");
				$(".title").click(function(){
					$(this).addClass("curcol").next(".content").css("display","block");
				});
			});
		</script>
	</head>
	<body>
		<div class="iframe">
			<div class="title">标题</div>
			<div class="content"></div>
		</div>
	</body>
</html>
```