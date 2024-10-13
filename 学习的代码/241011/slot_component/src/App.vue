<template>
<Slot3 >
<template #header="msgprops">
  <h3>{{msg}}--{{msgprops.msg}}</h3>

</template >

<template #main="msgprops">
  <h3>{{msg}}--{{msgprops.msg1}}</h3>

</template>
</Slot3>
</template>
<script>
// import Slot from './components/Slot.vue';
// import Slot1 from './components/Slot1.vue';
import Slot3 from './components/Slot3.vue';
export default{
  components:{
    Slot3
  },
  data(){
   return{
    msg:"APP内容"
   }
  }
}
</script>