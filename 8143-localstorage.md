# 什么是localStorage

 - 在窗口会话期间有一个可靠的系统来存储数据，在某些情况下可能有用。但是，想在Web上模拟强大的桌面应用程序，则一个临时的数据存储系统就不够用

 - 为了解决这个问题，API提供了另外一个系统，为每个来源保留一个存储空间，并保持信息持久可用-localStorage

 - 利用localStorage，可以保持大量数据，并由用户决定信息是否有用，是否保留

 - localStorage与sessionStorage拥有相同的接口，所以sessionStorage的方法和属性对于localStorage都有效

# stroge事件

- 由于localStorage向加载同一个程序时打开的的每个窗口都提供信息，所以至少产生两个问题

 - 各个窗口间如何通信

 - 如何更新当前没有活动或没有得到焦点的窗口信息

- 为了解决以上两个问题，API中提供了storage事件

- storage事件：存储空间每次发生变化时，都会触发这个事件，所以可以通过这个事件通知统一程序的每个窗口

- 语法

       window.addEventListener("storage",updateNum,false);

# WEB Socket

