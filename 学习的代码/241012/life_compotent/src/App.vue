<template>
  <KeepAlive>
  <component :is="bianliang"></component>

  </KeepAlive>
  <button @click="bian">改变组件</button>
</template>
<script>
import ComponentA from './components/ComponentA.vue';

// import ComponentB from './components/ComponentB.vue';

import { defineAsyncComponent } from 'vue';
const ComponentB =defineAsyncComponent(()=>
import('./components/ComponentB.vue'
))
export default{
  components:{
    ComponentA,
    ComponentB
  },
  data(){
    return{
      bianliang:"ComponentA"
    }
  },
  methods:{
    bian(){
     this.bianliang= this.bianliang == "ComponentA"?"ComponentB":"ComponentA"
    }
  }
}
</script>