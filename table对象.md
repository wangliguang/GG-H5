# Table 对象

  - Table对象代表一个HTML表格
 
     table标签表示一个Table对象

  - 常用属性
  
     rows

  - 常用方法
  
         insertRow(index);//返回TableRow对象
         deleteRow(index);

- 实例

  ![](/assets/屏幕快照 2016-08-29 下午2.17.00.png)

      <table id = "t1" border = "1" width = "100">
        <tr>
          <td rowspan = "2">a</td>
          <td>b</td>
        </tr>

        <tr>
          <td>c</td>
        </tr>
      </table>

      ---

      var table = document.getElementById("t1");

      console.log(table.rows.length); //2
    
# TableRow对象

 - TableRow对象代表一个HTML表格行

   tr标签表示一个TableRow对象

 - 常用属性

   cells/inner