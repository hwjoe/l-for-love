# JS将String转换为Date对象 #

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<h2>将字符串转换为 Date 对象。</h2>

<p id="demo"></p>

<script>

var text = '{ "name":"Runoob", "initDate":"2013-12-14", "site":"www.runoob.com"}';
var obj = JSON.parse(text);
obj.initDate = new Date(obj.initDate);

document.getElementById("demo").innerHTML = obj.name + "创建日期: " + obj.initDate;

</script>

</body>
</html>
```

Runoob创建日期：Sat Dec 14 2013 08:00:00 GMT+0800 (中国标准时间)

链接：https://www.runoob.com/try/try.php?filename=tryjson_parse_date