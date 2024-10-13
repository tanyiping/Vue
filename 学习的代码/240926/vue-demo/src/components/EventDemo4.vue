<template>
<h3>事件传参</h3>
<p @click="getName(name,$event)" v-for="name,index in names" :key="index">{{name}}</p>
</template>
<script>
export default{
    data(){
        return{
            names:["tan","yi","ping"],
        }
    },
    methods:{
        getName(name,e){
            console.log(name);
            console.log(e)
        }
    }
}

</script>