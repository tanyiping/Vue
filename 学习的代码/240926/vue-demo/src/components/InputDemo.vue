<template>
<h3>表单输入绑定</h3>
<form>
    <input type="text" v-model.lazy="message">
    <input type="checkbox"  id="checkbox" v-model="checkbox">
    <label for="checkbox">{{ checkbox }}</label>

</form>
<p>{{message}}</p>
</template>
<script>
export default{
    data(){
        return{
            message:"",
            checkbox:false,
        }
    },
    methods:{
    
    }
}
</script>