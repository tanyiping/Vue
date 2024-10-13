<template>
<h3>父级标签</h3>
<Child :biaoti="tan"  :age="age"  :names="names" :lala="lala"/>
</template>

<script>
import Child from './Child.vue';
export default{

    data(){
        return{
            tan:"lala",
            age:20,
            names:['t','y','p'],
            lala:{name:"tan",age:22,sex:"女"}
        }
    },
    components:{
        Child,
    },
}

</script>