<template>
<h3>A组件</h3>
<p>{{msg}}</p>
<componentB :chuandi="tanFn"/>
</template>
<script>
import ComponentB from './ComponentB.vue';
export default{
    data(){
        return{
           msg:""
        }
    },
    methods:{
        tanFn(data){
        console.log(data) ;
this.msg=data
        }

    },
    components:{
        ComponentB
    }

}
</script>