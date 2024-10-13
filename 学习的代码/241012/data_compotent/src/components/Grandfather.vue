<template>
    <h1>我是爷爷</h1>
    <Father />
</template>
<script>
import Father from './Father.vue';
export default{
    components:{
        Father
    },
    data(){
        return{
            msg:"爷爷的财产"
        }
    },
    // provide:{
    //     msg:"爷爷的财产"
    // }
    provide(){
        return{
            message: this.msg
        }
    }
}
</script>