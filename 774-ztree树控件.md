# zTree介绍

* zTree是利用jQuery的核心代码，实现一套能完成大部分常用功能的Tree插件

* 兼容IE、Firefox、chrome等主流浏览器

* 支持JSON数据

* 支持一次性静态生成和Ajax异步加载两种方式

* 支持tree的节点移动、编辑、删除


# zTree使用步骤

1. [下载](http://www.ztree.me/)zTree相关文件\(js\/css\)

2. 引入相关文件

  * css:样式文件夹，包含样式文件以及图像文件夹，必要的

  * js:与zTree相关的脚本文件

    * jquery.1.4.4 min.js jquery文件 必要的

    * jquery.ztree.core-3.5.js zTree核心文件  必须要的

3. 开发zTree

# 核心函数

 - $.fn.zTree.init(obj.zSetting,zNodes)

 - 初始化函数，通过init函数能够将数据绑定到树控件上

 - obj:用于展现zTree的DOM容器

 - zSetting:zTree的配置数据，以setting配置为准

 - zNodes: zTree的节点数据，支持JSOn

# setting配置

 - setting配置，setting对象的属性、方法对树控件做核心的配置，树控件的行为，效果都将以setting配置为准

 - setting对象的属性

   - callBack:与树控件事件相关的定义

   - check:与复选框样式及操作相关的定义

   - data:与数据相关的定义

   - view: 与小时效果相关的定义

 - 查看zTreeAPI详细了解


