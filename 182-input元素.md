# input元素

 - input元素用于收集用户信息

 - 该元素是一个单标记，语法为input

 - 主要属性

   - type:根据不同的type属性值，可以创建各种类型的输入字段、比如文本框、复选框

   - value:控件的数据

   - name:控件的名称

   - disabled:禁用控件

# 文本框与密码框

  - 文本框

        <input type="text">

  - 密码框

        <input type="password"/>

  - 主要属性

    - name:名称

    - value:由访问者自由输入的任何文本

    - maxlength:限制输入的字符数

    - readonly:设置文本控件只读
 # ![](/assets/屏幕快照 2016-09-24 下午4.19.55.png)

# 单选框和复选框

 - 单选框

       <input type="radio"/>

 - 复选框

       <input type="checkbox"/>

 - 主要属性

   - name:设置名称，并用于分组，一组单选框或者复选框的名称必须相同

   - value:文本，当提交form时，如果选中了此单选按钮，那么value就被发送到服务器

   - checked:设置默认被选中
  ![](/assets/屏幕快照 2016-09-24 下午4.29.07.png)

# 按钮

  - 提交按钮

        <input type="submit"/>

    - 传送表单数据给服务器或其他程序处理

  - 重置按钮

        <input type="reset"/>

    - 清空表单的内容并把所有表单控件设置为最初的默认值

  - 普通按钮

        <input type="button"/>

       - 用于执行客户端脚本

  - 主要属性

    - name:名称
    - value:按钮的标题文字

# 隐藏域或文件选择框

  - 隐藏域：

        <input type="hidden"/>

    - 在表单中包含不希望用户看到的信息
    - name属性：名称
    - value属性:值

  - 文件选择框

        <input type="file"/>

     - name属性：名称




 