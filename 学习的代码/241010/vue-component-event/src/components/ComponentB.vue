<template>
    <h3>B组件</h3>
    <p>{{ chuandi("tanyiping") }}</p>
    </template>
    <script>
    export default{
        data(){
            return{
                
            }
        },
        props:{
            chuandi:{
                type:Function
            }
        }
    
    }
    </script>