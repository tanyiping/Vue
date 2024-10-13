<template>
    <h3>主组件:{{zhi}}</h3>
<Sreach @findHandle="find"/>

</template>
<script>
import Sreach from './Sreach.vue';
export default{
    data(){
        return{
            zhi:""
        }
    },
    components:{
Sreach
    },
    methods:{
        find(data){
            this.zhi=data
        }
    }
}
</script>