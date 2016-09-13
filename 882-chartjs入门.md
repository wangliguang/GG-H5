# 如何使用Chart.js框架


 - 在HTML页面中引入chart.js文件

       <script="chart.js"></script>

 - 创建canvas元素

    - 用于显示Chart图表的容器

          <canvas id="myChart" width="400" height="400"></canvas>

 - 获取Canvas对象

       document.getElementById("myChart").getContext("2d");

 - 创建Chart图表

       new Chart(ctx).PolarArea(data);

# Chart.js全局配置

 - Chart.js 全局配置是在Chart.js第一个正式版本中引入

 - Chart.js全局配置用于改变所有图表的类型，避免了需要在每一个图表中单独进行设置

 - 当然，Chart.js全局配置也可以专门为某一个特定的图表进行配置

 - 语法
       Chart.deaults.global.参数名 = 参数值;


 - 举例

       Chart.defaults.global.responsive = true;
       //创建指定图表是，responsive选项值为true










