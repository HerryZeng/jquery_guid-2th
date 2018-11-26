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

