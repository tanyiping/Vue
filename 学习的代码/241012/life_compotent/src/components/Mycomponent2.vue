<template>
<h3 ref="ceshi">生命周期钩子添加数据测试</h3>
<li v-for="(item,index) in tan" :key="index">
    <p>{{ item.num }}</p>   <p>{{ item.name }}</p>
</li>
</template>
<script>
export default{
    data(){
        return{
            tan:[]
        }
    },
    created(){
        this.tan=[
            {
                "num":1,"name":"typ"
            },
            {  "num":2,"name":"tanyp"},
            {  "num":3,"name":"tandd"},
            {  "num":4,"name":"tandoudou"},
            {  "num":5,"name":"tanyiping"},
        ]
    }
}

</script>