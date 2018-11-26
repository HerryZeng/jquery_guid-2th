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

