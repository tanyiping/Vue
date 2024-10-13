<template>
<h3>组件事件</h3>
<Child  @zidyi="getHandle"/>
<p>我的名字：{{name}}</p>
</template>
<script>
import Child from './Child.vue';
export default{
    data(){
        return{
    name:""
        }
    },
    components:{
        Child
    },
    methods:{
        getHandle(data){
            console.log("触发了");
            console.log(data);
            this.name=data
        }
    }
}
</script>