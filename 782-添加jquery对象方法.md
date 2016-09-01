# 对象方法

* jQuery中大多数内置功能都是通过其对象的方法提供的，而且这些方法也是插件之所以诱人的关键

* 当函数需要操作DOM元素时，就是讲创建为jQuery对象方法的好机会

* 添加全局函数需要以新方法来扩展jQuery对象，添加实例方法即对象方法也类似，但扩展的是jQuery.fn对象

  ```
   jQuery.fn.method =        function(){
      //操作代码
   }
  ```


# 对象方法的环境

* 在任何插件内部，关键字this引用的都是当前的jQuery对象，因此可以在this上面调用任何内置的jQuery方法，或者提取他们的DOM节点并操作该节点

  ```
  jQuery.fn.changeBgColor = function(color){
      this.css("background",color);
   }
  ```

  ![](/assets/屏幕快照 2016-09-01 下午4.46.11.png)


# 编写一个小插件

编写一个插件，用于完成对li的样式进行切换。该插件中方法接受两个参数，即两个类样式名称，如果元素已经具备第一个类样式，则切换到第二个，否则，切换到第三个

![](/assets/屏幕快照 2016-09-01 下午4.52.42.png)

1. 编写插件

  ```
  jQuery.fn.swapClass = funciton(class1,class2){

      if(this.hasClass(class1)){

         this.removeClass(class1).addClass(class2);
      }else if(this.hasClass(class2)){
         this.removeClass(class2).addClass(class1);

      }
   }
  ```

2. 添加html元素以及css样式

       <ul>
        <li class = "bold">钢铁是怎样炼成的</li>
        <li class = "italic">遇见未知的自己</li>
        <li class = "bold">Java企业级应用开发</li>
        <li class = "italic">Ajax & jQuery</li>
       </ul>

       ---

       .itealic{font-style:italic;}
       .bold{font-wight:bold;}
   
3. **问题：**

     点击按钮后，每一行都变成了bold样式

   **原因：**

      jQuery的选择器会匹配零、一或多个元素，我们在调用.hasClass()的时候，只会检查最先匹配的元素。

   **解决办法** 独立检查和操作每个元素，在方法的环境上调用each方法，这样就会隐式迭代

         this(function()

            var $element = jQuery(this);

            if($element.hasClass(class1)){

                 $element.removeClass(class1).addClass(class2);

             }else if（$element.hasClass(class2)）{

                 $element.removeClass(class2).addClass(class1);
             }

         });

# 方法连缀

  - 除了隐式迭代外，jQuery用户应该能正常使用连缀行为。因而，我们必须在所有的插件中返回一个jQuery对象。除非对应的方法明显用于取得不同的信息

  - 返回的jQuery对象就是this所引用的对象，即return this

  - 如果使用.each()迭代this，可以只返回迭代的结果

        return this.eache(...,...);     