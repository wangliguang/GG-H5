# 什么是sessionStorage

 - sessionStorange这部分API就像是会话cookie的替代

   cookie以及sessionStorage都是在特定的时间段内保持数据可用，但Cookie使用浏览器作为引用，而sessionStorage使用单个窗口作为引用，这就意味着，窗口关闭之后，sessionStorage就不能再使用

# 创建数据

 - sessionStorage和lcoalStorage都将数据存储为项，项采用键值对的组合形式

 - 语法

   - setItem(key,value)：用键和值创建项，如果键已经存储则更新值，所以也可以用这个方法更新值

   - getItem(key):指定要获取的项的键，根据键得到对应的值

         //设置数据
         sessionStorage.setItem("uname","Naruto");

         //读取数据
         var name = sessionStorage.getItem("uname");

# 读取数据

- API提供了更多的方法和属性来操纵项，使得代码变得更有用

- 属性

  - length:返回应用程序在存储空间中积累的项的数量

- 方法

    - key(index)：获取指定索引对应的项的键

          var len = sessionStorage.length;

          for(var i=0;i<len;i++){

              var key = sessionStorage.key(i);
 
              alert(sessionStorage.getItem(key));
          }

# 删除数据

- API中提供了两个方法可以删除项

 - removeItem(key):根据键删除指定项

 - clear():清空整个存储空间，每个项都被删除

        sessionStorage.removeItem("uname");

        sessionStorage.clear();

        alert(sessionStorage.length);