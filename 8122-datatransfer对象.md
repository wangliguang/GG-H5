# 什么是dataTransfer对象

 - dataTransfer对象提供了对于预定义的剪贴板格式的访问，以便在拖放中使用，他使得自定义处理拖放操作成为可能

 - 可以通过dataTransfer对象保存拖放过程中各组件所涉及到的数据

# 在HTML5中，可以通过实践参数Event对象获取DataTransfer对象

 - 代码如下

       var transfer=e.dataTransfer;

       function mDragStart(event){

           dStart=document.getElementById('start');

           dStart.innerHTML = "Drag Start。。。";

           event.dataTransfer.setData("Text","http://www.tarena.com.cn");

       }

# 方法

- dataTransfer对象提供了一些方法用于在源元素与目标元素中共享数据

- 方法

   - setData(type,data)：用于声明所发送的数据与类型

  - getData(type)：返回指定type的数据

  - clearData(type)：删除指定类型的数据

  - type取值

    保存普通文本

        function mDragStart(e){ source1=document.getElementById('image');

            e.dataTransfer.setData("text",source1.src);

        }

        function mDrop(e){

            e.preventDefault();

            msg=e.dataTransfer.getData('text');

            drop.innerHTML="<img src='"+msg+"'/>";

        }

 ![](/assets/屏幕快照 2016-09-14 下午1.15.43.png)

