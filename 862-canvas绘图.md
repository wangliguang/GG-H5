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


# 颜色

- 在创建图形时如果不设定颜色，那么所有图形都会使用默认颜色-纯黑色

- 可以通过以下属性指定绘图颜色

   - strokeStyle:声明形状线条的颜色

   - fillStyle:声明形状内部区域的颜色

   - globalAlpha:透明度属性，可以设置画布上图形的透明度

- 示例

      function initial(){

          var elem = document.getElementById("canvas");

          var canvas = elem.getContext("2d");

          canvas.fillStyle="#000099";

          canvas.strokeStyle="990000";

          canvas.strokeRect(100,100,120,120); 

          canvas.fillRect(110,110,100,100);    

          canvas.clearRect(120,120,80,80);     

      }

![](/assets/屏幕快照 2016-09-12 下午4.01.42.png)


# 渐变

- Canvas支持的渐变效果包括包括线性渐变或射线渐变，并且支持设置颜色转折点

- 语法

  - createLinearGradient(x1,y1,x2,y2);在画布上创建一个线性渐变对象

  - createRadiaGradient(x1,y1,x2,y2,r2);在画布上创建一个射线渐变对象

 - addColorStop(position.color);指定渐变颜色值

- 示例

      function initial(){ 

          var elem=document.getElementById('canvas');

          var canvas=elem.getContext('2d');

          var grad=canvas.createLinearGradient(0,0,10,100);

          grad.addColorStop(0.5,'#0000FF');

          grad.addColorStop(1,'#FF0000');

          canvas.fillStyle=grad;

          canvas.fillRect(10,10,100,100);

          canvas.fillRect(150,10,200,100);


   ![](/assets/屏幕快照 2016-09-12 下午4.06.41.png)}


# 文字

- 在画布上写文字非常简单，只需要定义一些属性和方法即可

- 属性

  - font:与css的font属性类似，接受值也完全相同

  - textAlian:水平对齐方式，值可以是left/right/center

  - textBaseline: 文本基线，值可以是top/hanging(悬挂基线)/middle/alphabetic(默认值，字母基线)和bottom

- 方法

  - strokeText(text,x,y)：在位置（x,y）处绘制文字的轮廓

  - fillText(text,x,y);绘制实心文字

  - measureText()：返回指定文字的大小信息


- 示例

      function initial(){

         var elem=document.getElementById('canvas');

         canvas=elem.getContext('2d');

         canvas.font="bold 24px verdana,sans-serif";

         canvas.textAlign="start";

         canvas.textBaseline="bottom";

         canvas.fillText("Beijing Tarena",100,124);

         var size=canvas.measureText("Beijing Tarena");

         canvas.strokeRect(100,100,size.width,32);
      }  


![](/assets/屏幕快照 2016-09-12 下午4.13.20.png)

# 阴影

阴影也是Canvas API的重要组成部分，每一条路径和文字都可以创建阴影效果，API提供了4个实现阴影效果的属性

- shadowColor:使用CSS语法声明阴影颜色

- shadowOffsetX:接受一个数字，确定对象阴影的水平投射距离

- shadowOffsetY:接受一个数字，确定对象阴影的垂直投射距离

- shadowBlur:为阴影生成模糊效果

- 示例

      function initial(){

         var elem=document.getElementById("canvas");

         var  canvas=elem.getContext("2d");

         canvas.shadowColor="rgba(0,0,0,0.5)";

         canvas.shadowOffsetX=4;

         canvas.shadowOffsetY=4;

         canvas.shadowBlur=5;

         canvas.font="bold 50px verdana,sans-serif";

         canvas.fillText("Tarena",100,100);

      }

![](/assets/屏幕快照 2016-09-12 下午4.18.23.png)

# 创建路径

- 以上介绍的方法都是直接在画布上绘图，但是针对一些复杂图形的绘制，就需要自己通过路径进行描绘

- 路径就是画笔移动的地图，路径建立后，将其发送给上下文，就可以在画布上实际地绘制出图形

- 方法

  - beginPath():开始一个新的形状描述，创建路径之前，必须先调用这个方法

  - closePath():关闭路径，用直线将最后一个点与原点相连，如果想保留开放路径，则不需要调用这个方法

- 除此之外，还有三个方法可以再画布上录制路径

  - storke()：将路径绘制为轮廓形状

  - fill():将路径绘制为实心形状，使用该方法时可以不同closePath关闭路径，该方法会通过直线连接最后一个点与第一个点实现封闭

 - clip():在上下文中设置裁剪区域

- 以下方法可用于设置路径和创建真正的形状

  - moveTo(x,y):将笔触移到指定的位置

  - lineTo(x,y): 绘制一条直线，连接当前笔触位置到x和y属性声明的新位置

  - rect(x,y,width,height):生成一个矩形路径

  - arc(x,y,radius.startAngle,endAngle,direction)：这个方法可以在位置(x,y)上生成弧线或圆形，半径和弧度分别由属性指定，direction是布尔类型，表示顺时针或逆时针方向

- 示例

      function drawCircle(){

         elem=document.getElementById('canvas');

         canvas=elem.getContext('2d');

         canvas.beginPath();

         canvas.arc(100,100,40,0,Math.PI*2,false);

         canvas.closePath();

         canvas.fillStyle="yellow";

         canvas.fill();

      }

![](/assets/屏幕快照 2016-09-12 下午4.57.01.png)