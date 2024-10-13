<template>
<h3>内联数据处理器</h3>
<button v-on:click="addcount">Add</button>
<!-- @dbcilk  双击 才能 用函数 -->
<!-- v-on->@   可以直接写为@-->
<p>{{count}}</p>
</template>
<script>
export default{
    data(){
        return{
            count:0,
        }
    },
    //官方  认定的  将所有的方法和函数  放在这个里面methods
    //与data同级
    methods:{
        addcount(){
            //读取到data里面的方案：this.
            // this.count++
            this.count+=1;
            console.log("点击了");
        }
    }
}

</script>