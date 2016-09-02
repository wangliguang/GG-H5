# DOM的使用问题

 - 在JS中使用DOM解析并操作HTML元素

 - W3C指定的DOM规范不仅适用于解析并操作HTML页面，还适用于解析并操作XML文件

 - 使用DOM解析并操作XML页面中的元素代码并不简洁
 
 - 如果实现逻辑过于复杂的话，还可能影响HTML页面的性能

       var myDiv = document.getElementById("mydiv");

       var mydiv = document.getElementByName("mydiv");

       var mydiv = document.getElementByTagName("mydiv");

# T-Query功能

  - 我们可以通过自定义的T-Query完成对一些基本操作的封装，将基本操作进行简化

  - 如果以后想使用某些功能的话只需要调用T-Query的方法即可

  - T-Query功能大体如下

    - 创建$全局对象，并提供工厂函数

    - 使用$(expr)方式简化DOM获取HTML页面元素

        expr使用css的选择器方法

    - 创建方法简化DOM的基本操作

    - 提供get()方法用于自定义对象与DOM对象之间的转换



