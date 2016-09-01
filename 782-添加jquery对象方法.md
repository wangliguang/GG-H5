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


    