## 认识jQuery

jQuery是由美国人John Resig于2006年创建的一个开源项目，随着被人们的熟知，越来越多的程序高手加入其中，完善和壮大其项目内容；如今已发展成为集JavaScript、CSS、DOM、AJAX于一体的强大框架体系，它的主旨是：**以更少的代码，实现更多的功能(Write less,do more)** 。

---

### jQuery基本功能

1. 访问和操作DOM元素
使用jQuery库，可以很方便地获取和修改页面中的某个元素，无论是删除、移动、复制某元素，jQuery都提供了一整套方便、快捷的方法，既减少了代码的编写，又大大提高了用户对页面的体验度。

2. 控制页面样式
通过引入jQuery，程序开发人员可以很便捷地控制页面的CSS文件。浏览器对页面文件的兼容性一直以来都是页面开发者最为头痛的事，而使用jQuery操作页面的样式，却可以很好地兼容各种浏览器。

3. 对页面事件的处理
引入jQuery库后，使页面的表现层与功能开发分离，开发者可以更多地专注于程序的逻辑与功效；页面设计者侧重于页面的优化与用户体验，通过事件绑定机制，可以很轻松地实现二者的结合。

4. 大量插件在页面中的运用
在引入jQuery库后，还可以使用大量的插件来完善页面的功能和效果，如表单插件、UI插件，这些插件的使用，极大丰富了页面的展示效果，原来使用JavaScript代码遥不可及的功能，通过插件的引入都可以轻松的实现

5. 与AJAX技术的完美结合
AJAX的异步读取服务器数据的方法，极大方便了程序的开发，加深了用户的页面体验度；而引入jQuery库后，不仅完善了原有的功能，而且减少了代码的书写，利用其内部对象或函数，加上几行代码就可以实现复杂的功能。

---

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

