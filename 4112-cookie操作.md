# 保存Cookie

* Cookie可以由服务器端程序\(Java\/php等\)创建并发送给客户端保存，也可以由客户端JS脚本创建并保存

* ```
  //保存一个简单Cookie
  document.cookie = "uname=tom";

  //保存一个内容复杂的Cookie
  document.cookie = "msg" + encodeURICommponent("Hi,JS你好");

  //保存一个具有指定超时时间的Cookie
  document.cookie = "uid=7788; expires=" + new Date().toGMTString();
  ```

  Cookie键值中不能包含分好、逗号、等号、空格，同时为了防止中文乱码问题，键值应该使用encodeURIComponent\(\)函数进行编码

  上述三行语句可以创建三个Cookie，而不是只有一个


# 读取Cookie

* 可以使用document.cookie获取当前站点可以读取的所有Cookie\(多个Cookie间用；分隔\)

  ```
  var cookies = document.cookie;

  console.log(cookies); //多个Cookie用；分割

  var arr = arrkies.split(";");

  for(var i = 0; i<arr.length; i++){

    var cookie = arr[i];//键值对用=分割
    var cookiePair = cookie.split("=");
    console.log(cookiePair[0] + "=" + cookiePair[1]);

  }
  ```

  注意Cookie键名中可能会被浏览器添加空白字符，需要trim\(\)操作


# cookie的生命周期

* 若没有指定exprise属性，创建的Cookie其实只是保存在内存中，浏览器一关闭也就被销毁了

* 可以在保存Cookie时使用expires指定其生命周期
        
      document.cookie = “UI的= 7788”； //单会话Cookie

      var time = new Date().getTime() + 1000*3600*24*30;

      var exp = new Date(time);

      document.cookie = "uname=tom;expires=" + exp.toGMTString(); //30天后失效的Cookie
同理可以吧expires设置为一个过去的时间，就可以实现删除Cookie的效果

