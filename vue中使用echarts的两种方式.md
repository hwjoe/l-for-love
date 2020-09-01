# 在Vue中使用echarts的两种方式 #

准备：使用vue-cli脚手架

如果你已经有自己的项目，可以跳过这一步。

npm下载vue-cli脚手架

（写这篇文章时用的还是vue-cli2）

`npm install -g @vue/cli`

初始化一个项目

`vue init webpack hello`

然后等待它安装完所有的依赖包就可以了。

下面我们开始引入echarts。
 
方式一、直接引入echarts

先npm安装echarts

`npm install echarts --save`

开发：

main.js

`import myCharts from './comm/js/myCharts.js'Vue.use(myCharts)`

方式二、使用vue-echarts

先npm安装vue-echarts

`npm install vue-echarts --save`

开发：

除了全量引用echarts，我们还可以采用按需引入的方式

main.js

`import ECharts from 'vue-echarts/components/ECharts'import 'echarts/lib/chart/line'Vue.component('chart', ECharts)`

ps：原本webpack配置需要改的，看了一下vue-echarts的官网说明是v2.3.4之后都不需要改了，所以到这里就结束了。试过打包了，没报错~

选择

两种方式都能实现大部分需求。

个人认为：

    如果你的需求是定制化比较少的，基本上绑定数据然后展示就行了，或者你对echarts还不是很熟悉的，那么vue-chart是一个不错的选择；
    如果你的需求是定制化多的，比如需要特殊处理鼠标事件什么的（当然vue-chart也可以，但我不喜欢同时看两份API，多累呀），又或者你已经对echarts比较熟悉了（那你就不会看这篇文章了哈哈），你会发现Echarts官方文档写得真是清晰明了，直接用着也很爽呀完全没问题呀，那么我会更倾向于直接使用echarts。

我刚开始一两个项目的时候用vue-chart很舒服，上手很快，但后面做得多了，我觉得还是直接写更能满足我，Anyway，看个人选择吧！

链接：https://segmentfault.com/a/1190000015453413
