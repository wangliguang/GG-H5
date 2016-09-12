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

- 示例

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
![](/assets/屏幕快照 2016-09-12 下午5.36.39.png)
