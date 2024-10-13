<template>
  <Grandfather />
  <!-- <Son /> -->
</template>
<script>
import Grandfather from './components/Grandfather.vue';
import Son from './components/Son.vue';
export default{
  components:{
    Grandfather,
    Son
  },
  provide:{
    tan:"lalal"
  }
}
</script>