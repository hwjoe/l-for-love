# JavaScript清空数组的三种方法 #

1、length

用length方法可以很轻松地清空数组：
```
var arr = [1,2,3];
console.log(arr);

arr.length = 0;
console.log(arr);
```

2、splice

splice() 方法向/从数组中添加/删除项目，然后返回被删除的项目：
```
var arr = [1,2,3];
console.log(arr);

arr.splice(0);
console.log(arr);
```

3、[]


```
var arr = [1 ,2 ,3];
console.log(arr);

arr = [];
console.log(arr);
```

链接：https://blog.csdn.net/eclipse9527/article/details/80384941
