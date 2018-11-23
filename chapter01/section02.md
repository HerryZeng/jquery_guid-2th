## 搭建jQuery开发环境

由于jQuery是一个完整的JavaScript文件库，因此，搭建jQuery开发环境十分简单，无须安装任何文件，只需要先在jQuery官方网站下载最新的文件库，然后将该文件库引入页面中的`<head>`元素间即可。

### 下载jQuery文件库

jQuery的官方网站为:http://jquery.com。

### 引入jQuery文件库

在页面的`<head></head>`中加入如下代码：
```html
<script language="javascript" type="text/javascript" src="js/jquery-3.3.1.min.js"></script>
```

### 编写一个简单的jQuery程序

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>第一个简单的jQuery程序</title>
		<style type="text/css">
			div {
				padding: 8px 0;
				font-size: 12px;
				text-align: center;
				border: 1px solid #888;
			}
		</style>
		<script src="js/jquery-3.3.1.min.js"></script>
		<script type="text/javascript">
			$(document).ready(function(){
				$("div").html("你好，欢迎来到jQuery的精彩世界");
			});
		</script>
		
	</head>
	<body>
		<div></div>
	</body>
</html>
```


