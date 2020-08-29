# js中的变量作为json的key #

具体解决描述如下.

假使 var key1 = "aaa"; 

var value1 = "bbbb";

json 对象 data={k:'aa',b:'aaa'};

这时如果想给data改为 {k:'aa',b:'aaa',aaa:'bbbb'};

用 data.key1 = value1;这样是不行的。会把变量名作为key来传输。

那么 我们的解决方案的写法为 data[key1] = value1;

这样 问题就解决了。

链接：https://blog.csdn.net/xiaomanonyo/article/details/78642148
