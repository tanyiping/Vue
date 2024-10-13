<template>
<h3>列表渲染</h3>
<p v-for="(item,index) in names">{{ item }}---{{index}}</p>
<p v-for="name in names">{{ name }}</p>
<p v-for="value,key,index of user">{{key}}:{{value}}[{{ index }}]</p>
</template>

<script>
export default{
    data(){
        return{
            names:["lala","baba","jiejie"],
            user:{
                name:"tan",
                age:22,
                sex:"女",
            },
        }
    }
}
</script>

