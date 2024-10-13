<template>
<h3 @click="AddList">变更数据</h3>
<li v-for="name,index in names" :key="index">{{name}}</li>
<h3 v-on:click="Addshuze">变更数组</h3>
<p v-for="num1,index in number1" :key="index">{{num1}}</p>
<p v-for="num2,index in number2" :key="index">{{num2}}</p>

</template>
<script>
export default{
    data(){
        return{
            names:["tan","cheng","li"],
            number1:[1,2,3,4],
            number2:[5,6,7,8],
        }
    },
    methods:{
        AddList(){
            //在数组中 添加一个王
            this.names.push("wang");
            //用concat直接添加数组  但是 页面上的数据  并没有改变
            this.names.concat(["fang"]);
            //但是直接使用显示  可以发现  数组其实 发生了变化
            console.log(this.names.concat(["fang"]));
            //我们可以这么来使用它  //这样网页  就可以变动了
            this.names=this.names.concat(["fang"]);
    
        },
        Addshuze(){
            this.number1=this.number1.concat(this.number2);
        }
    }
}

</script>