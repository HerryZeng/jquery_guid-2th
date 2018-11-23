## 选择器的优势

与传统的JavaScript获取页面元素和编写事务相比，jQuery选择器具有明显的优势，具体表现在以下两个方面：
    + 代码更简单
    + 完善的检测机制

### 代码更简单

由于在jQuery库中，封装了大量的可能通过选择器直接调用的方法或函数，使编写代码更加简单轻松，简单几行代码就可以实现较为复杂的功能。

下面通过一个实现表格隔行调变色功能的示例，分别使用传统的JavaScript语言与jQuery语言加以说明。

**功能说明**
在页面中，通过一个`<tbale>`标记展示数据列表信息，在元素标记中，奇数和偶数行的背景色不同，从面实现隔行变色的页面展示效果。

**代码实现**
1. 传统的JavaScript实现方法
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>使用JavaScript实现隔行变色</title>
		<style type="text/css">
			body {
				font-size: 12px);
				text-align: center;
			}
			#tbStu {
				width: 260px;
				border: 1px solid #666;
				background-color: #eee;
			}
			
			#tbStu tr {
				line-height: 23px;
			}
			
			#tbStu tr th {
				background-color: #ccc;
				color: #fff;
			}
			
			#tbStu .trOdd {
				background-color: #FFFFFF;
			}
		</style>
		
		<script type="text/javascript">
			window.onload=function() {
				var oTb = document.getElementById("tbStu");
					for(var i=0;i<oTb.rows.length-1;i++){
						if(i/2){
							oTb.rows[i].className = "trOdd";
						}
					}
			}
		</script>
	</head>
	<body>
		<table id="tbStu" cellspacing="" cellpadding="">
			<tbody>
				<tr>
					<th>学号</th>
					<th>姓名</th>
					<th>性别</th>
					<th>总分</th>
				</tr>
				
				<tr>
					<td>1001</td>
					<td>张小明</td>
					<td>男</td>
					<td>320</td>
				</tr>
				<tr>
					<td>1002</td>
					<td>李明琪</td>
					<td>女</td>
					<td>350</td>
				</tr>
			</tbody>
		</table>
	</body>
</html>
```
首先通过ID获取表格元素，然后遍历表格的各行，根据行号的奇偶性，动态设置行的背景色，从而实现隔行变色的效果。

页面中的JavaScript代码虽可以实现最终效果，但循环页面的元素会影响打开速度，并且代码较为复杂，如使用jQuery选择器实现上述页面效果，则需要在页面中加一些代码。