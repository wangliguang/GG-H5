# 什么是选择器



- 选择器是支持开发者所熟悉的CSS语法，快速且轻松的对页面进行设置



- CSS中常用的选择器



 - ID选择器：#id{}



 - 类选择器：.class{}



 - 标签选择器：element{}



 - ....



# ID选择器



 - 通过页面元素的id属性值去定位页面上的一个元素



 - 封装ID选择器的目的是简化document.getElementById()方法



 - 语法：$("id")



 if(selector.substring(0,1) === "#"){



 //判断是否为$("#id")

 var elem = document.getElementById(selector.substring(1));



 arr.push(elem);



 }



# 类选择器



 - 通过页面元素的class属性值去定位页面上的元素



 - 封装类选择器的目的是简化document.getElementsByClassName()方法



 - 语法： $("className")



 if(selector.substring(0,1) === "."){



 var elems = document.getElementsByClassName(selector.substring(1));



 for(var i=0; i<elms.length;i++){

 arr.push(elems[i]);

 }



 }



 # 元素选择器



 - 通过页面元素的元素名称去定位页面上的元素



 - 封装元素选择器的目的是简化document.getElementsByTagName()方法



 - 语法： $("elementName")



 //是否为标签选择器

 var elems = document.getElementsByTagName(selector);

 var len = elems.length;

 for(var i=0; i<len; i++){



 arr.push(elems[i]);



 }
