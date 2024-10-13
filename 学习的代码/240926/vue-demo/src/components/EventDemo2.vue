<template>
    <!-- <h3>内联数据处理器</h3> -->
    <button v-on:click="addcount">Add</button>
    <p>{{count}}</p>
    </template>
    <script>

    export default{
        data(){
            return{
                count:0,
            }
        },
       
        methods:{
            //获取event对象
            addcount(e){
                //Vue中的Event对象，就是原生JS的Event
                //可以获取按钮  可以  修改内容
                    e.target.innerHTML="tan"+this.count;
                this.count+=1;
           
            }
        }
    }
    
    </script>