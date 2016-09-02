# $对象

 - $对象实际上是模仿jQuery中的$,用于根据指定的选择器获取页面上的元素

       window.$ = function(selecotr){

          var arr = new Array();

          ...

          return arr;
       }

# TQuery对象

 - TQuery对象是一个自定义的JS对象，其主要目的是为了保存通过各个选择器获取的一个或一组DOM对象

 - TQuery对象除了能够保存DOM对象外，还要具备一组方法，用来方便的操作这些对象

       function tQuery(){};

       tQuery.prototype = new Array();

 - 使用自定义的JS对象TQuery，替换$对象中的Array数组

 - 实现TQuery对象的链式操作

       window.$ = function(selecotr){

          var tQuery = new tQuery();

          ....

          _tQuery.push(elems[i]);
          ....

          return _tQuery;  
       }

# TQuery对象转换DOM对象

 - 利用自定义JS对象TQuery，封装了一些简化ODM操作的方法，但并不能将DOM的所有操作全部封装

 - 需要提供get()方法，允许将TQuery对象转换回DOM对象，以便使用DOM方式继续操作

       tQuery.prototype.get = function(index){
          return this[index];
       }

