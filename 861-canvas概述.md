# 什么是Canvas

- Canvas是H5出现的新标签，像所有DOM一样，拥有自己的属性、方法和事件，其中就有绘图的方法，javaScript能够调用他在页面上完成绘图

- Canvas也是H5种最强大的特性之一，允许开发者使用动态和交互式可视化方法在web上实现桌面应用程程序的功能

- **Internet Explorer8及更早IE版本的浏览器不支持canvas元素**

# 创建Canvas

- canvas元素会在网页上创建一个空白矩形区域，然后通过API操作这个区域，与空白的div元素相似，但用途完全不同

- 默认情况下，创建的canvas元素没有边框和内容

- 语法

      <canvas id="canvas" width="300" height="200"></canvas>

# getContext()方法

- 在使用Canvas元素时，要调用getContext()方法，其目的是得到画布的绘图上下文，通过这个引用，就可以使用其他的API进行绘图操作

- 语法

      function initial(){

        var elem = document.getElementById("canvas");

        var canvas = elem.getContext("2d");

      }

- **该方法可以接受两个值：2d和3d，分别表示二维和三维**