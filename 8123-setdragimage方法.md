# setDragImage()

- setDragImage方法用于在拖放操作过程中，修改鼠标指针所指向的图像

- 语法

      event.dataTransfer.setDrag(image,x,y);

      ---

      function mDragStart(e){

         elem=e.target;

         e.dataTransfer.setData('text',elem.getAttribute("id"));

         e.dataTransfer.setDragImage(e.target,120,130);

       }

