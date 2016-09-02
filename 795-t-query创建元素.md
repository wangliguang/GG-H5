# $()创建元素

 - 在T-Query中，我们可以灵活的创建DOM元素以便提供给其他的元素去使用

 - 在DOM中，可以使用document.createElement方法，在T-Query中，可以封装成$()来进行创建

 - 语法： 

       $("<div>content</div>")

       即创建一个div元素，内容是content

---
    if(selector.charAt(0) === "<" && selector.charAt(selector.length - 1) === ">" && selector.length >= 3){

       //创建新的html元素
       var tag = selector.substring(1,selector.indexOf(">"));

       //获取元素中的文本内容(获取'>'与'<'之间的内容)
       var content = selector.substring(selector.indexOf('>')+1,selector.lastIndexOf('<'));

       var elem = document.createElement(tag);

       elem.innerHTML = content;

       _tQuery.push(elem);
    }
