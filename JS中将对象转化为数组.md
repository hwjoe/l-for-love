JS中将对象转化为数组

{ 'one': 'two', 'three': 'four' } 遍歷此對象並且將它轉換為數組 [ 'one', 'two', 'three', 'four' ]:
```
<script>
let obj = {'one':'two', 'three':'four'};
var arr = [];

for (let i in obj) {
    arr.push(i); // key
    arr.push(obj[i]); // value
}

console.log(arr);
</script>
```

链接: https://www.cnblogs.com/wancheng7/p/8735168.html
