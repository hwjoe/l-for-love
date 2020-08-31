# ECharts柱状图的x轴文字纵向显示 #

在xAxisLabel中使用formatter回调函数实现换行，就能实现文字纵向显示。

具体代码如下所示：

```
axisLabel:{
    formatter:function(value){
        return value.split("").join("\n);
    }
}
```

链接：https://blog.csdn.net/u013594477/article/details/80103467
