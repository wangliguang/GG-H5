# Web Socket示例概述

 - 在服务端指定使用的Socket应用程序，并在服务端指定该socket应用程序的主机与端口

 - 编写在客户端使用的Web Socket实现与服务端进行连接并收发信息

# Web Socket示例代码

 - Web Socket客户端页面关键代码

       <h1>WebSocket客户端示例</h1> 

       <div id="message"></div>

       <p>请输入一些文字：</p>

       <input id="text" type="text"></input>

       <button id="connect" onclick="connect();">建立连接</button>

       <button id="send" onclick="send();">发送数据</button>

       <button id="disconnect" onclick="disconnect();">断开连接</button>

- Web Socket客户端JS关键代码，connect()方法

      function connect(){ 

         webSocket = new WebSocket(host);

         webSocket.onopen = function(){

             …

          }

         webSocket.onmessage = function(event){

             …

          }

         webSocket.onclose = function(){

             …

          }
      }


- Web Socket客户端JS关键代码，send()方法

      function send(){ 

          var text = …

          var message = …

          if(text==""){

               …

             return;

           }

          webSocket.send(text);

             …

         }

- Web Socket客户端JS关键代码，disconnect()方法

      function disconnect(){

          webSocket.close();

      }



