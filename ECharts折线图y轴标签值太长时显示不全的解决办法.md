# ECharts折线图y轴标签值太长时显示不全的解决办法 #

解决办法

官网在此：http://echarts.baidu.com/

我们要看的是配置项的部分：http://echarts.baidu.com/option.html#title

可以改的地方有下面几个：

    yAxis.axisLabel.margin：刻度标签与轴线之间的距离。默认值是8，可以改小一点。不过本来的值已经很小了，这个没多大作用。
    yAxis.axisLabel.formatter：刻度标签的内容格式器，支持字符串模板和回调函数两种形式。比如可以设置太长了换行之类的。
    grid.left：grid 组件离容器左侧的距离。默认值是10%。

原文：https://blog.csdn.net/dandelion_drq/article/details/79270597
