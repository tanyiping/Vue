<template>
<h2>B</h2>
<p>{{name}}</p>
<p>age={{age}}</p>
<p>{{names}}</p>
<button @click="xiugai">修改props的值</button>
</template>
<script>
export default{
    data(){
        return{
            
        }
    },
    props:{
        name:{
         type:[String,Number,Array,Object]
        },
        age:{
            // default:60
            required:true
        },
        names:{
            default(){
                return "没有值"
            }
        }
    },
    methods:{
        xiugai(){
            console.log(this.name);
            this.name="tanyiping";
        }
    }
}
</script>