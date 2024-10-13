<template>
<h3>KEY属性添加到v-for中</h3>
<p v-for="(item,index) in name" :key="index">{{item}}</p>
</template>
<script>
export default{
    data(){
        return{
            name:["tan","yi","ping"]
        }
    }
}
</script>