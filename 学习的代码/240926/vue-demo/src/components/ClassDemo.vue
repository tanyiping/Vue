<template>
<p :class="{'class1':xianshi,'class2':xianshi1}">class属性</p>
<p :class="tan">class属性绑定</p>
<!-- 以数组的形式绑定 -->
<p :class="[tan1,tan2]">class属性绑定</p>
<!-- 以数组的形式绑定里面  可以用三元 运算符来判断  最后显示样式 -->
<p :class="[xianshi?'class1':' ']">class属性绑定</p>
<p :class="[xianshi?'class1 class2':' ']">class属性绑定</p>
<p :class="[xianshi?'class2':' ',{'class1':xianshi}]">class属性联合绑定</p>

</template>
<script>
export default{
    data(){
        return{
            xianshi: true,
            xianshi1:true,
            tan:{
                class1: true,
                class2: true
            },
            tan1:'class1',
            tan2:'class2'
        }
    }
}

</script>
<style>

.class1{
/* text-decoration-colrgb(81, 110, 25)een; */
color: rgb(24, 209, 24);
}
.class2{
    text-align: center;
}
</style>