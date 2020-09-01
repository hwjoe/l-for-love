# webpack+git开发环境将git中tag自动显示到web中 #

问题由来: 系统通常是要显示版本信息的,但是,这之前做的web都是手动打tag,并手动将web中的version版本更新,
如果能将git中的tag版本信息自动添加到web中那是不是很赞?
有了这个想法自然就要探索一下实现方法了,
翻看了一下.git的文件目录,发现里面有个.git\refs\tags目录,这里面正是要找的tag信息,

每个文件里面记录着commit 标识,也就是该tag是在哪个节点上的,这里我们暂时不用处理那么深入(也许这个功能在别的地方能用到).
那我们就可以获取这些文件名称,然后再进行遍历得到tag编码最大的那个就好了,(通常tag都是逐渐增大的).
因为用到了webpack,自然在开发和打包的就有node环境,获取这些文件就需要用node方法,读取文件列表的方法用到了fs模块,看代码

获取列表的代码已经给出来了,但是应该放到什么位置呢?
在本地开发的vue项目中结构(react类似),
 
src目录和static目录是代码路径,环境不不是node环境,所以就不能放到这里面,外面还有build文件夹,这里面就是node环境了,(如果你分析过webpack的配置,就不会对这里陌生),自然要将上面的代码放到这里面,观察了一下内容,发现应该放到config配置里面最好,当然你也可以放到别的地方,在config文件夹下新建tag.js,

获取到最大的tag后导出一个对象出去即可,注意这里面获取tag时我只取了小数,如果像 v1.2.3这样的会自动变成1.2,当然想实现其他方法自己实现一下就可以了.
导出去之后就需要使用了,导入到config下index.js中使用了

此时在src下的js中还不能获取到该变量,我们在开发中经常会用到process这个变量,例如获取rocess.env.NODE_ENV变量进行dev和prodution环境切换就需要判断rocess.env.NODE_ENV === 'production'这个, 看到这我们自然也想用该方法去获取tag就好了,此时尝试获取时并不能得到我们的tag值,因为我们没在webpack中定义该变量.
在build文件夹下有两个文件webpack.dev.conf.js和webpack.prod.conf.js,里面定义了该环境下的变量,将tag变量也进行定义就可以了,

ok,此时重新运行webpack后发现我们子src的config.js文件下已经可以像访问process.env一样访问process.tag了,至于显示到web页面中或用于其他逻辑就看自己实现了.
这样每次tag更新发布自动带上了我们的tag,好高兴啊.
 
链接：https://www.jianshu.com/p/aec8eeeb2693
