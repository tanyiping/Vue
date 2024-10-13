<template>
<h3>事件修饰符</h3>
<a @click.prevent="dianji" href="http://www.tanyiping.top">谭依萍的网站</a>
<div @click="divfuntion">
    <p @click.stop="pfuntion">阻止冒泡事件</p>
</div>

</template>
<script>
export default{
    data(){
        return{

        } 
    },
    methods:{
        dianji(e){
            //阻止默认事件
            // e.preventDefault();
            console.log("你被点击了");
        },
        divfuntion(){
            console.log("DIV")
        },
        pfuntion(e){
            // e.stopPropagation();
            console.log("P")
        },
    }
}
</script>