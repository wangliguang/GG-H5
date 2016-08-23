### 通过ID选取元素

document.getElementById\('id'\)可用于在当前DOM树中根据ID选择某一个子元素

```
<ul id = "menuList">
   <ul id="menuList"> 
   <li id="m1">首页</li>
   <li id="m2">企业介绍</li>
   <li id="m3">联系我们</li>
</ul>

--------

 var ul = document.getElementById('menulist');

 console.log(type ul);  
```

思考：页面中若是有两个相同ID的元素会怎么样？

### 通过标签名选取元素

node.getElementsByTagName\('标签名'\)可以根据标签名返回所有具有指定标签名的元素集合

```
 <ul>
    <ul id = "menuList">
    <ul id="menuList">
    <li id="m1">首页</li>
    <li id="m2">企业介绍   </li>
    <li id="m3">联系我们</li>
 </ul>

--------

 var ul = document.getElementById('menulist');

 var list = ul.getElementsByTagName('li');

 //数组对象
 console.log(type list);

 console.log(list.length);

```

### 通过name属性选取元素

document.getElementByName\('name属性值'\)可以返回DOM树中具有指定name属性值的所有子元素集合

```
<form id = 'registerForm'> 
   <input type = "checkbox" name = "bobboy"/>
   <input type = "checkBox" name = "bobboy">
   <input type = "checkBox" name = "bobboy">    
</form>

--------

 var list = document.getElementsByName('hobby');

 console.log(typeof list);
 console.log(list.length);

```

