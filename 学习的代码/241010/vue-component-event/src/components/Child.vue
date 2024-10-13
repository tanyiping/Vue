<template>
    <h3>Child</h3>
    <button @click="EventHandle">按钮</button>
</template>
    <script>
    export default{
        data(){
            return{
                names:"tan"
            }
        },
        methods:{
            EventHandle(){
                this.$emit("zidyi",this.names)
            }
        }
    }
    </script>