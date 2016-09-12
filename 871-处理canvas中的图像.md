# 绘制图像

* 在H5中，不仅可以使用Canvas API来绘制图形，还可以读取磁盘或网络中的图像文件，然后使用Canvas API将该图像绘制在画布中

* 绘制图像时，是要使用drawImage方法，定义如下

  * drawImage\(image,x,y\)

    ```
    image：可以是image元素，video元素，js中的image对象

     x:起始横坐标

     y:起始纵坐标
    ```

  * drawImage\(image,x,y,w,h\)

    ```
    W:宽度
    h:高度
    ```



* 示例

  ```
  function initial(){

     var elem=document.getElementById('canvas');

     var canvas=elem.getContext('2d');

     for(var i=0;i<3;i++){

       image=new Image();

       image.src="img/monster3.gif";

       img.onload=function(){

          canvas.drawImage(image,i*50,i*50,150,148);
       }
     }

  }
  ```

  ![](/assets/屏幕快照 2016-09-12 下午5.36.39.png)


# 绘制图像

* 所谓图像平铺就是用按一定比例缩小后的图像将画布填满，实现图像平铺的方式有两种，**一种是前面介绍的drawImage\(\)方法；另一种方法是使用上下文对象的createPattern\(\)方法**

* 语法：canvas.createPattern\(image,type\)

  * image:要平铺的图像
  * type:平铺方式

    * no-repeat:不平铺
    * repeat-x:水平方向平铺
    * repeat-y:垂直方向平铺
    * repeat:全方向平铺



* 示例

  ```
  function initial(){

     elem=document.getElementById('canvas');

     canvas=elem.getContext('2d');

     var img=new Image();

     img.src="img/monster3.gif";

     var ptrn=canvas.createPattern(img,'repeat');

     canvas.fillStyle=ptrn;

     canvas.fillRect(0,0,400,300);

  }
  ```

  ![](/assets/屏幕快照 2016-09-12 下午5.43.36.png)


# 切割元素

* 在Canvas中，不仅能以各种方式平铺绘制的图像，还可以通过上下文环境中的clip\(\)方法切割画布中的绘制图像。

* clip\(\)方法调用格式如下：

  ```
  canvas.clip()
  ```

- 该方法用于切割使用路径方式在画布中绘制的区域，因此，在使用该方法前，必须使用路径在画布中绘制一个区域

- 示例

      elem=document.getElementById('canvas');

      canvas=elem.getContext('2d');

      image=new Image();

      image.src="img/flower.jpg";

      image.onload=function(){

         canvas.drawImage(image,0,0,280,190);

      }

      canvas.beginPath();

      canvas.arc(140,95,60,0,Math.PI*2,true);

      canvas.closePath();

      canvas.clip();

 ![](/assets/屏幕快照 2016-09-12 下午5.49.35.png)
