# html()/html(text)

 - **html(text)** 用于向指定的T-Query元素赋html值

 - **html** 用于获取指定的T-Query元素的html值

 - html()方法是对innerHTML属性进行了封装

 - 语法： $(selector).html([html])

       tQuery.prototype.html = function(html){

            if(html){
              ...
            }else{
              ...  
            }
 
            return this;
        }