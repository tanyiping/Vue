<template>
<div class="aside">
    <h3>Aside</h3>
    <Item/>
    <Item/>
    
</div>
</template>
<script>
import Item from './Item.vue';
export default{
    components:{
        Item
    }
}
</script>
<style scoped>
.aside{
    float: right;
    text-align: center;
    width: 30%;
    height: 250px;
    border: 5px solid #999;
   box-sizing: border-box; 
    line-height: 100px;
}
</style>