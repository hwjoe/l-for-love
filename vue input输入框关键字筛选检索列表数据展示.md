# vue input输入框关键字筛选检索列表数据展示 #

想必大家在项目开发中难免会用到关键字筛选的功能，正好这次项目有需求要做这一块，就整理一下vue的input输入关键字检索数据列表。下面直接上代码：

```
html：
<!-- 筛选demo -->
<template>
    <div>
        <input type="text" v-model="search">
        <ul>
            <!-- 注意！注意！注意！这里循环遍历的是items，不再是data里的list数组 -->
            <li v-for="(item,index) in items">
                <span>{{item.name}}</span>
                <span>{{item.msg}}</span>
            </li>
        </ul>
    </div>
</template>

匹配（所有||单个）字段 > js：
export default {
    data () {
        return {
            search:'',
            list:[
                {name:'AAA',msg:'aaa文本介绍1'},
                {name:'BBB',msg:'bbb文本介绍2'},
                {name:'CCC',msg:'ccc文本介绍3'},
                {name:'DDD',msg:'ddd文本介绍4'},
                {name:'EEE',msg:'eee文本介绍5'},
            ]
        }
    },

    computed: {
        //过滤方法
        items: function() {
            var _search = this.search;
            if (_search) {
                //不区分大小写处理
                var reg = new RegExp(_search, 'ig')
                //es6 filter过滤匹配，有则返回当前，无则返回所有
                return this.list.filter(function(e) {
                    //匹配所有字段
                    return Object.keys(e).some(function(key) {
                        return e[key].match(reg);
                    })
                    //匹配某个字段
                    //  return e.name.match(reg);
                })
            };
            return this.list;
        }
    },
}
```

链接：https://blog.csdn.net/zuorishu/article/details/86630097
