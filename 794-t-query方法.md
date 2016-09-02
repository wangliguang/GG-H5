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

        ---

        tQuery.prototype.html = function(text){

            if(text){

               //设置所有元素的html值
               for(var i=0; i<this.length; i++){

                   this[i].innerHTML = text;
               }
            }else{

               //获取所有元素的html值
               for(var i=0;i<this.length;i++){

                 this[i] = this[i].innerHTML;
               } 

            }
        }

# text()/text(text)

 - **text(text)** 用于向指定的T-Query元素赋text值

 - **text()** 用于获取指定的T-Query元素的text值

 - **text()** 方法是对textContent属性进行了封装

 - 语法： $(selector).text([text])

       tQuery.prototype.text = funciton(text){

          if(text){
             ....
          }else{
             ....
          }

          return this;
       }

       ----

       tQuery.prototype.text = funciton(text){

          if(text){

             //设置所有元素的textContent值
             for(var i=0;i<this.length;i++){

                 this[i].textContent = text;
             }
          }else{
              //获取所有元素的textContent值
              for(var i=0;i<this.length;i++){
                this[i] = this[i].textContent;
              } 
           }

           return this;
       }

# val()/val(value)

 - **val(value)** 用于向指定的T-Query元素的value属性赋值

 - **val()** 用于获取指定的T-Query元素的value属性值

 - **val()** 方法是对value属性尽心了封装

 - 语法： $(selector).val([value])

        tQuery.protype.val = function(val){

             if(val){
                ...
             }else{
                ...
             }
    
             return this;
         }

         ---

         tQuery.prototype.val = funciton(value){

             if(value){
 
                  for(var i = 0;i<this.length;i++){

                     var elem = this[i];
                     elem.value = value;
                  }
              }else{

                  for(var i = 0;i<this.data.length;i++){

                     var elem = this[i];

                     this[i] = elem.value;
                   }

              }

              return this;

        }


# attr(name,[value])

 - 获取或设置T-Query元素的制定属性值

 - 相当于dom.setAttribute(name,vlue)/dom.getAttribute(name)

 - 语法： $(seletor).attr("name",[value])

       tQuery.prototype.attr = function(name,value){

           if(name && value){
               ...
           }else{

               ...
           }

           return this;

       }

       ----

       tQuery.prototype.attr = funciton(name,value){

           if(name && name){
              
               for(var i=0;i<this.length;i++){

                  var elem = this[i];
                  elem.setAttribute(name,value);
               }

           }else if(name){

                for(var i=0;i<this.length;i++){

                   var elem = this[i];

                   this[i] = elem.getAttribute(name);
                }
           }

       }
     