<template>
    <h3>子级标签</h3>
    <h3>{{biaoti}}</h3>
    <h2>{{age}}</h2>
    <li v-for="(item,index) in names" :key="index">{{item}}</li>
    <h4>{{lala.name}}--{{lala.age}}</h4>
    
    </template>
    
    <script>
    export default{
        data(){
            return{
               
            }
        },
        props:["biaoti","age","names","lala"]
  
    }
    
    </script>