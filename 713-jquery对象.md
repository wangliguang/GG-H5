# 什么是jQuery对象

 - jQuery对象就是通过jQuery包装DOM对象后产生的对象

 - jQuery对象是jQuery独有的，如果一个对象是jQuery对象，就可以使用jQuery的方法

 - 在jQuery对象中无法使用DOM对象的任何方法，反之，DOM对象也无法使用任何jQuery的方法

 - 如：$("div")和$("#d1")都是jQuery对象

 **如果获取的是jQuery对象，那么要在变量前面加上$**

# DOM对象->jQuery对象

 - 使用$()将DOM对象包装起来，就可以转换成jQuery对象

 - 语法

   $(DOM对象)

        function f(){

          var obj = document.getElementById("d1");

          //DOM->jQuery对象
          var $obj = $(obj);

          $obj.html("hello jQuery");

         }