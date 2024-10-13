<template>
<h3 ref="ceshi">生命周期钩子读取数据ref测试</h3>
</template>
<script>
export default{
    data(){
        return{
        
        }
    },
    beforeMount(){
        console.log("我是挂载前");
        
      console.log(this.$refs.ceshi);
        
    },
    mounted(){
        console.log("我是挂载后");

        console.log(this.$refs.ceshi);

    }
}

</script>