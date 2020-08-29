# 修改JS里数组或对象的键名 #

```
var key = 'abc';
var obj = {key : '值'};
 
// 复制原来的值
obj[key] = obj['key'];
// 删除原来的键
delete obj['key'];
// 检查效果
alert(obj.abc);
```

链接: https://blog.csdn.net/evilcry2012/article/details/52442690
