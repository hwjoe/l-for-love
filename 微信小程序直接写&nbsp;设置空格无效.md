# 微信小程序直接写&nbsp;设置空格无效 #

问题：

今天在做小程序页面的时候，发现直接把`&nbsp;`写在`<text>`组件里面无效

解决方法：

通过查看小程序文档发现，原来要给`<text>`设置decode属性才可以正常使用

最终写法为：

`<text decode="true">&nbsp;&nbsp;测试&nbsp;&nbsp; &nbsp;文本</text>`

链接: https://www.jianshu.com/p/88b04d9e60de
