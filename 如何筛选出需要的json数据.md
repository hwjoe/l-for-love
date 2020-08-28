# 如何筛选出需要的json数据 #
```
data
    0    {id="1", type="1",name="a"}
    1    {id="2", type="5",name="b"}
    2    {id="3", type="3",name="c"}
    3    {id="4", type="5",name="d"}
    4    {id="5", type="2",name="e"}
    5    {id="6", type="2",name="f"}
```
問，如何循环取出type=5的数据，不等于5的移除只显示等于5的？

解，使用过滤器：
```
var data = [
    {'id':"1", 'type':"1",'name':"a"},
    {'id':"1", 'type':"5",'name':"a"},
    {'id':"1", 'type':"1",'name':"a"},
    {'id':"1", 'type':"4",'name':"a"},
    {'id':"2", 'type':"5",'name':"c"},
    {'id':"1", 'type':"1",'name':"a"}
];
data = data.filter(function(a){
    return a.type==5;
})
console.log(data);
```

链接：https://bbs.csdn.net/topics/392085437?page=1
