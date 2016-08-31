# 什么是jQuery对象

* jQuery对象就是通过jQuery包装DOM对象后产生的对象

* jQuery对象是jQuery独有的，如果一个对象是jQuery对象，就可以使用jQuery的方法

* 在jQuery对象中无法使用DOM对象的任何方法，反之，DOM对象也无法使用任何jQuery的方法

* 如：$\("div"\)和$\("\#d1"\)都是jQuery对象

  **如果获取的是jQuery对象，那么要在变量前面加上$**


# DOM对象-&gt;jQuery对象

* 使用$\(\)将DOM对象包装起来，就可以转换成jQuery对象

* 语法

  $\(DOM对象\)

  ```
   function f(){

     var obj = document.getElementById("d1");

     //DOM->jQuery对象
     var $obj = $(obj);

     $obj.html("hello jQuery");

    }
  ```


* jQuery对象-&gt;DOM对象

  * jQuery对象通过jQuery提供的get\(index\)方法，得到对应的DOM对象

  * 语法：

    DOM对象 = jQuery对象.get\(index\);


* jQuery对象是一个数组对象，可以通过\[index\]方式，得到对应的DOM对象

  * 语法

    DOM对象 = jQuery对象\[index\];

        function f(){

          var $obj = $("#d1");

          //jQuery对象->DOM
          var obj = $obj.get(0);

          obj.innerHTML = "hello jQuery";

        }

