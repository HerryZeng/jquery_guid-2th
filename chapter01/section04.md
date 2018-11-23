## jQuery简单应用

在介绍使用jQuery开发简单应用之前，首先需要了解如何使用jQuery访问DOM元素，如何将DOM对象转化成jQuery对象，然后通过控制转成的jQuery对象，实现各类应用的功能。

### jQuery访问DOM对象

1. 什么是DOM对象
每一个页面都是一个DOM(Document Object Model，文本对象模型)对象，通过传统的JavaScript方法访问页面中的元素，就是访问DOM对象。
如，页面中有两个`div`元素标记如下
```html
<div id="Tmp">测试魔王</div>
<div id="Out"></div>
```
通过下面的JavaScript代码可以访问DOM对象，以及获取或设置其内容值 ：
```javascript
var tDiv = document.getElementById("Tmp");    //获取DOM对象
var oDiv = document.getElementById("Out");    //获取DOM对象
var cDiv = tDiv.innerHTML;                    //获取DOM对象中的内容
var oDiv.innerHTML = cDiv;                    //设置DOM对象中的内容
```

2. 什么是jQuery对象
在jQuery库中，通过本身自带的方法获取页面元素的对象，称为jQuery对象，为了同样实现在ID为"Out"的标记中显示ID为"Tmp"的标记内容，采用jQuery访问页面元素的方法如下：
```jquery
var tDiv = $("#Tmp");
var oDiv = $("#Out");
oDiv.html(tDiv.html());
```

### jQuery控制DOM对象

在介绍使用jQuery控制DOM对象前，先通过一个简单的示例，说明如何用传统的JavaScript方法访问DOM对象

