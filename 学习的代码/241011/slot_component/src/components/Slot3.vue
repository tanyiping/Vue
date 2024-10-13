<template>
<h3>Slot拓展2</h3>
<slot name="header"  :msg="childmsg"></slot>
<hr>
<slot name="main"  :msg1="childmsg1"></slot>

</template>
<script>
export default{
    data(){
        return{
            childmsg:"子组件数据",
            childmsg1:"子组件数据1",

        }
    }
}
</script>
