# js计算数组里的对象的某个值相同，其余值相加 #

```
 let arry=[
 {Code:'x',Quantity:1,ItemType:'normal'},
 {Code:'x',Quantity:2,ItemType:'normal'},
 {Code:'x',Quantity:5,ItemType:'normal'},
 {Code:'y',Quantity:1,ItemType:'spec'},
 {Code:'y',Quantity:2,ItemType:'spec'},
 {Code:'z',Quantity:1,ItemType:'normal'},
]
let newfood=[];
var temp = {};

for(var i in arry) {
 var key= arry[i].Code;
 if(temp[key]) {
   temp[key].Code = temp[key].Code ;
   temp[key].Quantity = temp[key].Quantity+ arry[i].Quantity;
 } else {
   temp[key] = {};
   temp[key].Code = arry[i].Code;
   temp[key].Quantity = arry[i].Quantity;
 }
 temp[key].ItemType= arry[i].ItemType;
}

for(var k in temp) {
 newfood.push(temp[k])
}
alert(JSON.stringify(newfood));
```

原文: https://blog.csdn.net/qq_34117170/article/details/81058709
