# 如何使用Two.js框架

 - 在HTML页面中引入Two.js文件
       <script src="two.js"></script>

 - 在HTML页面定义用于显示矢量图的容器

       <div id="draw-shapes"></div>

 - js代码获取元素

       document.getElementById("draw-shapes");

 - 使用Two.js提供的API进行绘制

       new Two(params).appendTo(elem);

# 绘制矩形元素

 - Two.js框架使用makeRectangle(x,y,width,height)方法

       makeRectangle(x,y,width,height)

  - x:指定绘制的矩形左上角的坐标值x
  - y:指定绘制的矩形左上角的坐标值y
  - width:绘制指定的矩形宽度
  - height:指定绘制矩形的高度

# 绘制圆形元素

  - Two.js框架使用makeCircle(x,y,radius)方法绘制矩形

        makeCircle(x,y,radius);

   - x：指定绘制圆形的圆心坐标值x
   - y：指定绘制圆形的圆心的坐标值y
   - radius:指定绘制的圆形的半径

# 元素分组

- 元素分组

  - Two.js框架允许将绘制在页面的多个图形分为一组或多组

  - Two.js提供的API方法允许针对组进行操作或实现动画

- 创建分组

  - 通过Two.js框架提供的构造器Two.Group()实现
  - 通过Two.js提供的相关API方法或属性进行操作


- 将已绘制的图形分为一组或多组

 - 通过创建的two对象调用makeGroup()方法

 - makeGroup()方法允许传递多个绘制图形对象
 
 - 通过Two.js框架提供的相关API方法或属性进行操作

# 添加动画

 - two.play()方法

  - 该方法向requestAnimationFrame loop添加一个实例，使该实例实现动画效果

 - two.pause()方法

  - 该方法从requestAnimationFrame loop删除一个示例，使该实例的动画效果停止

 - two.update()方法

  - 该方法用于更新在HTML页面中绘制的图形的尺寸，增加动画效果

  

