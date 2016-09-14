# Web Socket对象 

- 调用Web Socket对象的构造器是建立与服务器之间的通信连接

      var webSocket = new WebSocket("ws://localhost:8005/socket");

  - url字符串必须以“ws”或“wss”（加密通信时）文字作为开头

  - 客户端可以通过WebSocket这个URL字符串重新获取连接

# Web Socket方法

 - 使用WebSocket对象的send()方法对服务器发送数据

       webSocket.send("data");

  - send()方法只能发送文本数据

  - 使用JSON把任何JS对象转换称文本数据后进行发送

- 通过WebSocket对象的close()方法来关闭socket，切断通信连接

      webSocket.close()

- Web Socket事件

 - 通过获取onmessage事件来接受服务器传来的数据

        webSocket.onmessage = function(event){

            var data = event.data;

        }

- 通过获取onopen事件来监听socket的打开事件

        webSocket.onopen = function(event){
            //开始通信时的处理
         }

- 通过获取onclose事件来监听socket的关闭事件：

        webSocket.onclose = function(event){

          //通信结束时的处理
        }

# readyState属性

  - 通过读取readyState的属性值来获取WebSocket对象的状态

  - readyState属性存在以下几种属性值

   - CONNECTING(0),表示正在连接
   - OPEN(1)，表示已建立连接
   - CLOSING(2),表示正在关闭连接
   - CLOSED(2),表示已关闭连接
   

