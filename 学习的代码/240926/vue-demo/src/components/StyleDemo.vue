<template>
    <!-- 常规写法 -->
<p :style="{color:yanse,fontSize:zize+'px'}">style绑定1</p>
<!-- 一对象的形式  在绑定样式 -->
<p :style="yangshi">style绑定2</p>
<!-- 上面的方法  也可以 以数组的形式绑定 -->
<p :style="[yangshi]">style绑定3</p>

</template>
<script>
export default{
    data(){
        return{
            yanse:"green",
            zize:40,  

            yangshi:{
                color:"red",
                fontSize:"20px"
            },
        }
    }
}
</script>