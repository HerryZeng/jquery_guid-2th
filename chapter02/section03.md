## 综合案例分析--导航条在项目中的应用


### 需求分析

本案例中的需求主要有以下两点：
1. 在页面中创建一个导航条，单击标题时，可以伸缩导航条的内容，标题中的提示图片也随之改变。
2. 单击`简化`链接时，隐藏指定的内容，并将`简化`字样改为`更多`;单击`更多`链接时，返回初始状态，并改变指定显示元素的背景色。

### 代码实现

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>导航条在项目中的应用</title>
		<script src="js/jquery-3.3.1.min.js" type="text/javascript" charset="utf-8"></script>
		<style type="text/css">
			body{
				font-size: 13px;
			}
			a {
				text-decoration: none;
			}
			
			#divFrame {
				border: 1px solid #666666;
				width: 301px;
				overflow: hidden;
			}
			#divFrame .clsHead {
				background-color: #EEEEEE;
				padding: 8px;
				height: 18px;
				cursor: hand;
			}
			
			#divFrame .clsHead h3 {
				padding: 0;
				margin: 0;
				float: left;
			}
			
			#divFrame .clsHead span {
				float: right;
				margin-top: 3px;
			}
			
			#divFrame .clsContent {
				padding: 8px;
			}
			
			#divFrame .clsContent ul {
				list-style-type: none;
				margin: 0;
				padding: 0;
			}
			#divFrame .clsContent ul li{
				float: left;
				width: 95px;
				height: 23px;
				line-height: 23px;
			}
			#divFrame .clsBot {
				float: right;
				padding-top: 5px;
				padding-bottom: 5px;
			}
			.GetFocus {
				background-color: #EEEEEE;
			}
		</style>
		
		<script type="text/javascript">
			$(function  () {
				$(".clsHead").click(function  () {
					if($(".clsContent").is(":visible")){
						$(".clsHead span img").attr("src","img/a1.png");
					}else{
						$(".clsHead span img").add("src","img/a2.png");
						$(".clsContent").css("display","block");
					}
				});
				
				$(".clsBot > a").click(function  () {
					if($(".clsBot > a").text() === '简化'){
						$("ul li:gt(4):not(:last)").hide();
						$(".clsBot >a").text("更多");
					}else {
						$("ul li:gt(4):not(:last)").show().addClass("GetFocus");
						$(".clsBot > a").text("简化");
					}
				})
			})
		</script>
	</head>
	<body>
		<div id="divFrame">
			<div class="clsHead">
				<h3>图书分类</h3>
				<span><img src="img/a2.png" alt="" /></span>
			</div>
			<div class="clsContent">
				<ul>
					<li><a href="#">小说</a><i>(1110)</i></li>
					<li><a href="#">文艺</a><i>(230)</i></li>
					<li><a href="#">青春</a><i>(1430)</i></li>
					<li><a href="#">少儿</a><i>(1560)</i></li>
					<li><a href="#">生活</a><i>(870)</i></li>
					<li><a href="#">社科</a><i>(1460)</i></li>
					<li><a href="#">管理</a><i>(1450)</i></li>
					<li><a href="#">计算机</a><i>(1780)</i></li>
					<li><a href="#">工具书</a><i>(930)</i></li>
					<li><a href="#">引进版</a><i>(980)</i></li>
					<li><a href="#">其他类</a><i>(3230)</i></li>
				</ul>
				<div class="clsBot"><a href="">简化</a>
					<img src="img/a5.png" alt="" />
				</div>
			</div>
		</div>
	</body>
</html>
```
