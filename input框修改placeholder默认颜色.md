# input框修改placeholder默认颜色 #

```
//修改input输入框的默认样式
    input{
      background:none;
      outline:none;
      border:0px;
    }

    //修改placeholder的默认颜色：
    input::-webkit-input-placeholder{
      color:#585c89;
    }
    input::-moz-placeholder{   /* Mozilla Firefox 19+ */
      color:#585c89;
    }
    input:-moz-placeholder{    /* Mozilla Firefox 4 to 18 */
      color:#585c89;
    }
    input:-ms-input-placeholder{  /* Internet Explorer 10-11 */
      color:#585c89;
    }
```

在vue里面不需要加这些前缀，vue有这个模块自动添加了，所以直接

```
input::placeholder{
color:#585c89;
}
```

即可

链接：https://blog.csdn.net/weixin_42554311/article/details/81901901
