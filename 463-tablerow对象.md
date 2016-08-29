# Select对象

 - Select对象代表HTML表单中的一个下拉列表

   select标签即表示一个Select对象

 - 常用属性

  options/selectedIndex/size

 - 常用方法

  add(option)/remove(index);

 - 事件

   onchange

 - 示例

       <select id = "sell" onchange = "showInfo()">
          <option value = "11">aa</option>
          <option value = "22">bb</option>
       </select>


# Option对象

 - Option对象代表HTML表单中下拉列表中的一个选项

    option标签表示一个Option对象

 - 创建对象

    var o = new Option(text,value); 

 - 常用属性

    index/text/value/selected

 - 示例

       function showInfo(){

           var selObj = document.getElementById("sell");
           var i = selObj.selectedIndex;

           console.log(selObj.options[i].value);         
        }  

        ---

       <select id="s1" onchange="selFunc();"> 

            <option value="1">aa</option>

            <option value="2">bb</option>

       </select>


       function selFunc(){

         var selObj = document.getElementById("s1");
         var value = selObj.options[selObj.selectedIndex].value;

         console.log(value);

         var option = new Option("cc","33");

         selObj.add(option);

        }
 
 