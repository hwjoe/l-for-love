# v-for 排序 #

```
<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <script type="text/javascript" src="/assets/js/vue.js"></script>
  <title>v-for</title>
</head>

<body>
  <h1>v-for</h1>
  <hr>
  <div id="app">
    <ul>
      <li v-for="item in sortItems">{{item}}</li>
    </ul>
    <hr>
    <ul>
      <li v-for="(student,index) in sortStudents">
        {{index+1}}:{{student.name}}--{{student.age}}
      </li>
    </ul>
  </div>
</body>
 
<script type="text/javascript">
  var app = new Vue({
    el:"#app",
    data: {
      items:[123,443,223,443,12,32,23],
      students:[
        {name:'jspang',age:32},
        {name:'Panda',age:30},
        {name:'PanPaN',age:21},
        {name:'King',age:45}
      ]
    },
    computed:{
      sortItems:function() {
        return this.items.sort(sortNumber);
      },
      sortStudents:function() {
        return sortByKey(this.students,'age');
      }
    }
  });

 
  //数组排序方法
  function sortNumber(a,b) {
    return a-b;
  }

 
  //数组对象方法排序:
  function sortByKey(array,key) {
    return array.sort(function(a,b) {
      var x=a[key];
      var y=b[key];
      return ((x<y)?-1:((x>y)?1:0));
    });
  }
</script>
</html>
```

链接：https://blog.csdn.net/lovemyself196221/article/details/81483195
