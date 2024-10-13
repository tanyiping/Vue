<template>
<h3>侦听器</h3>  
<!-- 只能监听响应式的数据 上面的h3 是不能侦听的 -->
 <!-- 下面的响应p 标签  是可以的 -->
<p @click="bian">{{message}}</p>
</template>
<script>
export default{
    data(){
        return{
            message:'tantan',
        }
    },
    methods:{
       bian(){
        this.message="doudou"
       },
    },
    watch:{
        message(newV,oldV){
            console.log(newV,oldV)
        }
    },
}

</script>