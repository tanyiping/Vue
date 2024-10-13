
<template>
  <div :class="msg" :id="tid">测试</div>
  <div v-bind="tanobjeck">测试1</div>

  <button :disabled="buke">按钮</button>
</template>
<script >
export default{
  data(){
    return{
      msg:"active",
      tid:"tanid",
      kedian:true,
      buke:false,
      tanobjeck:{
        class:"active",
        id:"tanid",
      }
    }
  }
}
</script>