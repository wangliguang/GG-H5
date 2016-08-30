# event 对象

* 任何事件触发后将会产生一个event对象

* event对象记录事件发生时的鼠标位置、键盘按键状态和触发对象等信息，事件对象的常用属性

  * srcElement\/target：事件源对象
  * eventPhase: 事件所处的传播阶段
  * clientX\/offsetX\/pageX\/screenX\/x: 事件发生的X坐标
  * clientY\/offsetY\/pageY\/screenY\/y: 事件发生的Y坐标
  * which\/keyCode\/charCode: 键盘事件中按下的按键
  * button: 鼠标哪个按键被按下了
  * cancelBubble: 是否取消事件冒泡
  * returnValue: 是否阻止事件默认行为


```
 Event对象的所有属性列表可以在浏览器控制台中输出查看
```

# 获取event对象

* 需要考虑浏览器兼容性

  1. IE浏览器JS或HTML代码中直接使用event关键字

    ```
    <p onclick = "alert(event.clientX);">p text</p>
    <div onclick = "func();">div text</div>
    ---
    //IE 浏览器
    function func(){
      alert(event.clientX+":" + event.clientY);
    }
    ```

  2. Firefox浏览器,HTLM代码中直接使用event关键字

    ```
    <p onclick = "alert(event.clientX);">p text</p>
    <div onclick="func">

    ---

    firefox浏览器

    function func(){

    alert(event.clientX + ":" + event.client);
    }//此时会报警告，JS代码中不能直接使用event对象
    ```



* 在HTML代码中，在事件处理函数定义时，使用event关键字将事件对象作为参数传入方法

      <div onclick = "func(event);">div text</div>

      //火狐浏览器
      function func(e){

          alert(e.clientX + ":" + e.clientY);

      }//可以解决浏览器兼容问题
             
- 在JS代码中，如果使用方法二和方法三方式动态绑定事件处理函数时，Firefox会将事件对象默认以第一个参数方式传入，所以：

      div.onclick = func; 

      --- 
 
      //firefox浏览器
      function func(){
        var e = window.event || arguments[0];
        alert(e.clientX + ":" + e.clientY);
      }//可以解决浏览器兼容问题

# 目标对象与this

  - 对于event对象，经常需要获得事件源--目标对象

  - 目标对象：始终保持最初触发事件的节点对象
 
  - this:指代触发事件的当前节点对象，随事件冒泡而改变

  - 示例

        <div onclick = "func(event);">div text</div>
         
        //IE浏览器

        function func(e){
          var src = e.srcElement;
        }

        //firefox浏览器
        function func(e){ 
          var src = e.target;
        }

      如何写出各浏览器兼容的代码

        //考虑浏览器兼容问题
        function func(e){
           var obj = e.srcElement || e.target;
           alert(obj.nodeName);//DIV
        }

# 取消冒泡与利用冒泡

   - 取消冒泡：

      当某一事件触发后，如果不想继续向上层冒泡，可在当前事件处理函数结尾取消冒泡

     1. DOM标准

            e.stopPropagation()

     2. IE

            e.cancelBubble = true; 

     3. 示例

            //考虑浏览器兼容问题     
            function func(e){
               
              var obj = e.srcElement || e.target;

              ...
 
              if(e.stopPropagation){

                e.stopPropagation();
              }else{
                 e.cancelBubble = true;
              }

            }//可以解决浏览器兼容问题

- 利用冒泡 

   如果多个子元素都绑定了相同的事件处理程序，则可以仅在父元素上绑定一次即可

       <div onclick = "func(event);">

          <button>1</button>
          <button>2</button>
       </div>

       function func(e){
         var src = e.srcElement || e.target;
       }//通过src获得具体点击的是哪个子元素


# 取消事件

  - 通常浏览器在事件传递并处理完后可能会执行与该事件关联的默认动作，例如：

     如果表单中input type 属性是“submit”,点击后会自动提交表单

  - 但事件处理函数过程中发生了错误，会不希望继续执行默认行为时，都可以取消事件或阻止默认行为继续执行

 - 可采用下述方法阻止事件的默认行为

          if(event.preventDefault){

            event.preventDefault(); //DOM
          }else{
           event.returnValue = false; //IE
          }

 - 如果使用HTML绑定事件处理函数，可使用两个return的方式取消事件
    
          <form onsubmit = "return valiAll()">

          //取消事件 2个return
          function valiAll(){

             return true/false;

          }
          

# 事件坐标

 - event对象记录事件发生时的 鼠标位置

   1. 相对于浏览器显示区域坐标位置

         clientlx/clientYlY

   2. 相对于网页左上角坐标位置

       pageX/pageY，IE8不支持

   3. 没滚动时，以上两组值相等

   4. 相对于屏幕坐标位置

        screenX/screenY

   5. 相对于目标元素左上角的坐标位置

       offsetX/offsetY