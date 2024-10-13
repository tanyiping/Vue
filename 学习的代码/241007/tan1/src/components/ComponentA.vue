<template>
<h1>A</h1>
<ComponentB :name="name"  :names="names"/>
</template>
<script>
import ComponentB from './ComponentB.vue';
export default{
    data(){
        return{
            name:"tan",
            age:20,
            names:["tan","yi","ping"]
        }
    },
    components:{
        ComponentB,
    }
}
</script>