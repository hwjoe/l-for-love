# vue中关于checkbox的问题 #

在vue中写checkbox时，发现出现问题：当点击一个选项时，输出的数组为空，当取消或者点击下一个选项时，才会出现该选项值且下一个选项值不会出现：

```
<template>
    <div class='mycheck' @click='check()'>
        <input type="checkbox" v-model="value" value="短信" id='message'>
        <label for="message" class='msg' ></label>
        <label >短信</label> 
        <input type="checkbox" v-model="value" value="QQ" >
        <label >QQ</label>
        <input type="checkbox" v-model="value" value="微信" >
        <label >微信</label> 
        <input type="checkbox" v-model="value" value="微博">
        <label >微博</label> 
        <p>{{value}}</p> 
    </div>
</template>
<script>
export default {
    data(){
        return {
            value:[]
        }
    },
    methods:{
        check(){
            console.log(this.value)
        }
    }
</script>
```

当点击微博 选项，控制台输出为一个空数组：

当再点击微信 控制台输出微博

这个问题形成的原因是当点击checkbox时，先触发click事件，打印数据，然后，才把checbox的value值传给model，也就是传入value中。

在我网上搜索解决的办法中，发现使用setTimeout有奇效。用伪异步的方式去执行这段代码。（搜索的方法中有复杂的等有时间再仔细看，笔记后面附上地址。）

```
check(){
    setTimeout(() => console.log(this.value))
}
```

参考：https://segmentfault.com/q/1010000005734206

链接：https://blog.csdn.net/sinat_39417731/article/details/78928548
