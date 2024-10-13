<template>
    <h3>compotentA组件</h3>
    <p>{{msg}}</p>
    <button @click="bianhua">改变数据</button>
</template>
<script>
export default{
    data(){
        return{
            msg:"老数据"
        }
    },
    beforeUnmount(){
    console.log("组件卸载前");
    
    },
    unmounted(){
        console.log("组件卸载后");

    },
    methods:{
        bianhua(){
            this.msg="新数据"
        }
    }
}
</script>