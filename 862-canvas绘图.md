# 绘制矩形

- 在准备好Canvas之后，就可以创建和绘制实际图形了。API提供的工具非常广泛，包括创建图像、颜色、文本等

- API中的一些方法支持在画布上直接绘图，但这些方法专门用于绘制矩形形状，并且是唯一能够生成基础形状的方法。要想绘制其他形状，就要组合使用其他的绘图方法以及复杂路径

- 绘制矩形方法(生成基础形状方法)

 - fileRect(x,y,width,height)绘制实心矩形

 - strokeRect(x,y,width,height)绘制空心矩形

 - clearRect(x,y,width,height)清除属性所指定的区域的像素，类似于矩形擦除器

        function initial(){

           var elem = document.getElementById("canvas"); 

           var canvas = elem.getContext("2d");

           canvas.strokeRect(100,100,120,120);

           canvas.fillRect(110,110,110,110);

           canvas.clearRect(120,120,80,80);

        }

 ![](/assets/屏幕快照 2016-09-12 下午3.53.15.png)

