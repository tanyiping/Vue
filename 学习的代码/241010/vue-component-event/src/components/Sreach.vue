<template>
搜索：<input type="text" v-model="neirong">
</template>
<script>
export default{
    data(){
        return{
            neirong:""
        }
    },
    watch:{
        neirong(New,Old){
            this.$emit("findHandle",New);
        }
    }
}
</script>