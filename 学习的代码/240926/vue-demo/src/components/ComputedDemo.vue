 <template>
    <h3>计算属性</h3>
    <p >{{jisuan}}</p>
    <p >{{jisuans()}}</p>

 </template>
 <script>
export default{
    data(){
        return{
            tandouodou:{
                name:"tanyp",
                neirong:["22","女","大学生"],
                // neirong:[],

            }
        }
    },
    computed:{
        jisuan(){
          return  this.tandouodou.neirong.length>0 ? 'yes':'no';
        }
    },
    methods:{
        jisuans(){
          return  this.tandouodou.neirong.length>0 ? 'yes':'no';

        }
    }
}
</script>