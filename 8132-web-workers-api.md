# WEB Workers API 
 
 - 检测浏览器对Web Worker的支持性
 - 创建Web Worker文件
 - 创建Web Worker对象
 - 与Web Worker进行通信

  - onMessage事件：该事件用于监听Web Worker传递的消息

  - postMessage()方法：该方法用于Web Worker传递消息

- 终止Web Worker

# 检测WEB Workers

 - 在创建Web Worker之前，需要先检测用户的浏览器是否支持

       if(typeof(Worker) !== "undefined"){

           //表示当前用户浏览器支持Web Worker

       }else{

          //表示当前用户浏览器不支持Web Worker

       }

# 创建WEB Worker文件

 - 创建普通的JS文件，都可以用于Web Worker文件。

 - Web Worker文件可以调用通信的事件和方法

   - onMessage事件
   - postMessage()方法

 - **HTML页面只能通过Worker对象调用Web Worker的JS文件**

# 创建WEB Worker对象

 - 在HTML页面中，通过Worker的构造器创建Web Worker对象

       var w = new Worker("myworker.js");

       参数：表示指定调用的Web Worker文件的路径

# 与WEB Worker通信

 - onMessage事件

       w.onMessage = function(event){

       }

   - 用于监听Web Worker传递消息，通过回调函数接收传递的消息

   - 通过回调函数的参数data属性可以获取传递的消息

 - postMessage()方法

       w.postMessage("worker success");

     - 通过postMessage()方法传递消息内容

# 终止WEB Worker

在HTML页面中，通过调用Web worker对象的terminate()方法终止Web Worker

       w.terminate();
      
   
