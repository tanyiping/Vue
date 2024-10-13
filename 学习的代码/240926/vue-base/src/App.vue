
<template>
 <h3>神奇的语法</h3>
 <p>{{msg}}</p>
 <p>{{hello}}</p>
 <p>{{number+1}}</p>
 <p>{{ok?'yes':'no'}}</p>
 <p>{{message.split('').reverse().join('')}}</p>
<p>{{thtml}}</p>
<p v-html="thtml"></p>

</template>

<script>
export default{
  data(){
    return{
      msg:"神奇的语法",
      hello:"hello Word",
      number:10,
      ok:true,
      message:"大家好",
      thtml:"<a href='http://www.tanyiping.top'>www.tanyiping.top</a>"
    }
  }
}
</script>
