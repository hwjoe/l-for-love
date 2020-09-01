# Win7执行git reset –hard HEAD^后显示more？的解决方案 #

在学习git的过程中，如果你是直接使用windows的cmd控制台来操作git的话，有可能会出现一些奇怪的问题。

比如当我执行git reset --hard HEAD^命令想要恢复到上一次提交的时候，输入后回车就一直显示more?，多按几次回车后就直接报错了，

如何解决呢？

这是因为cmd控制台中换行符默认是^，而不是\,more?的意思就是问你下一行是否需要再输入，而^就被当作换行符而把git命令忽略了。

解决方案有以下几种：

1. 加引号：git reset --hard "HEAD^"

2. 加一个^：git reset --hard HEAD^^

3. ^换成~：git reset --hard HEAD\~或者git reset --hard HEAD~1

4. ~后面的数字表示恢复几次提交，默认为1

当然，如果你是在git bash或者powershell下操作就不会有这种问题了。

链接：http://www.zhengzw.com/832.html
