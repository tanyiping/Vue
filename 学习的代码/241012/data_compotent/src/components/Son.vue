<template>
    <h3>我是儿子</h3>
    <p>{{message}}</p>
    <p>{{tan}}</p>
</template>
<script>
export default{
inject:["message","tan"]
}
</script>