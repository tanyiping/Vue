<template>
    <h1>插槽拓展</h1>
<slot name="header">我叫typ（默认值）</slot>
<hr>
<slot name="main">我叫tanyiping（默认值）</slot>

</template>
<script>
export default{
    data(){
        return{

        }
    }
}
</script>