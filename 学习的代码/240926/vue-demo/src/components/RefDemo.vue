<template>
<div class="container" ref="container">{{tan}} </div>
<button @click="tandd">改变</button>
<input type="text" ref="neirong">
</template>
<script>
export default{
    data(){
        return{
            tan:"typ",

        }
    },
    methods:{
        tandd(){
            console.log(this.$refs.container.innerHTML);
            this.$refs.container.innerHTML="tandd";
            console.log(this.$refs.neirong.value)
        }
    },
}

</script>