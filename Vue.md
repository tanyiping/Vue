



# Vue基础

### vue的风格  （选项式API）（组合式API）

## 开发前的准备

安装node.js >16版本

![image-20240926141229883](D:/Typora/image-20240926141229883.png)

## 创建Vue项目

```bash
npm init vue@latest
```

![image-20240926141727242](D:/Typora/image-20240926141727242.png)

![image-20240926141904435](D:/Typora/image-20240926141904435.png)

(执行上面的绿色按钮  即可)  可将 npm install  -》cnpm install  （用镜像的形式来加快下载速率）

```bash

C:\Users\Tan\Desktop\Vue\学习的代码\240926>cd vue-base

C:\Users\Tan\Desktop\Vue\学习的代码\240926\vue-base>cnpm install
```

![image-20240926142827370](D:/Typora/image-20240926142827370.png)

![image-20240926143029425](D:/Typora/image-20240926143029425.png)

### 开发环境

![image-20240926143114080](D:/Typora/image-20240926143114080.png)

![image-20240926143820539](D:/Typora/image-20240926143820539.png)

1.入门代码

### {{}}

![image-20240926144809738](D:/Typora/image-20240926144809738.png)



![image-20240926145050515](D:/Typora/image-20240926145050515.png)

![image-20240926154023174](D:/Typora/image-20240926154023174.png)

```js
 <p>{{message.split('').reverse().join('')}}</p>
message.split('')//字符串切割
reverse()//反转
join('')//合并
 <!-- {{}}里面  不要有逻辑的操作   -->
```



### v-html

![image-20240926155023929](D:/Typora/image-20240926155023929.png)

```vue

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

```



### v-bind（：）

![image-20240926160335562](D:/Typora/image-20240926160335562.png)

![image-20240926160607359](D:/Typora/image-20240926160607359.png)

### 绑定多个属性

![image-20240926161928713](D:/Typora/image-20240926161928713.png)

```vue

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
```



## 条件渲染

### v-if

![image-20240926163207084](D:/Typora/image-20240926163207084.png)

### if-else-if

![image-20240926163628495](D:/Typora/image-20240926163628495.png)

### v-show

![image-20240926163910551](D:/Typora/image-20240926163910551.png)

```vue
<template>
<h3>条件渲染</h3>
<div v-if="flag">你能看见我吗</div>
<div v-else>那你还是看看我吧</div>
<div v-if="type==='A'">A</div>
<div v-else-if="type==='B'">B</div>
<div v-else-if="type==='C'">C</div>
<div v-else>Not A/B/C/</div>
<div v-show="flag1">你能看见我么</div>
</template>
<script>
export default{
    data(){
        return{
            flag:false,
            type:"D",
            flag1:true,
        }
    }
}
</script>
```



### v-if与v-show的区别

![image-20240926163947926](D:/Typora/image-20240926163947926.png)

### v-for

![image-20240926170200233](D:/Typora/image-20240926170200233.png)





### 注意item的值  是可以改变的

<template>
<h3>列表渲染</h3>
<p v-for="item in names">{{ item }}</p>
<p v-for="name in names">{{ name }}</p>  
//只要  名字 对应到后面即可
</template>


<script>
export default{
    data(){
        return{
            names:["lala","baba","jiejie"],
        }
    }
}
</script>



![image-20240926171241465](D:/Typora/image-20240926171241465.png)

### item in items    可将in-》of

### item，key，index

![image-20240926171727152](D:/Typora/image-20240926171727152.png)

![image-20240926173136637](D:/Typora/image-20240926173136637.png)

推荐  将KEY  赋值为  唯一索引 （最好是‘id）

```vue
<template>
<h3>列表渲染</h3>
<p v-for="(item,index) in names">{{ item }}---{{index}}</p>
<p v-for="name in names">{{ name }}</p>
<p v-for="value,key,index of user">{{key}}:{{value}}[{{ index }}]</p>
</template>

<script>
export default{
    data(){
        return{
            names:["lala","baba","jiejie"],
            user:{
                name:"tan",
                age:22,
                sex:"女",
            },
        }
    }
}
</script>


```



## 事件处理

![image-20240926173529038](D:/Typora/image-20240926173529038.png)

### 内联处理器

![image-20240926174759921](D:/Typora/image-20240926174759921.png)

### 外联处理器

![image-20240926175845898](D:/Typora/image-20240926175845898.png)

```vue
<template>
<h3>内联数据处理器</h3>
<button v-on:click="addcount">Add</button>
<!-- @dbcilk  双击 才能 用函数 -->
<!-- v-on->@   可以直接写为@-->
<p>{{count}}</p>
</template>
<script>
export default{
    data(){
        return{
            count:0,
        }
    },
    //官方  认定的  将所有的方法和函数  放在这个里面methods
    //与data同级
    methods:{
        addcount(){
            //读取到data里面的方案：this.
            // this.count++
            this.count+=1;
            console.log("点击了");
        }
    }
}

</script>
```



### event

![image-20240926181322196](D:/Typora/image-20240926181322196.png)

```vue
<template>
    <!-- <h3>内联数据处理器</h3> -->
    <button v-on:click="addcount">Add</button>
    <p>{{count}}</p>
    </template>
    <script>

    export default{
        data(){
            return{
                count:0,
            }
        },
       
        methods:{
            //获取event对象
            addcount(e){
                //Vue中的Event对象，就是原生JS的Event
                //可以获取按钮  可以  修改内容
                    e.target.innerHTML="tan"+this.count;
                this.count+=1;
           
            }
        }
    }
    
    </script>
```



![image-20240927090545353](D:/Typora/image-20240927090545353.png)

![image-20240927090947605](D:/Typora/image-20240927090947605.png)

```vue
<template>
<h3>事件传参</h3>
<p @click="getName(name,$event)" v-for="name,index in names" :key="index">{{name}}</p>
</template>
<script>
export default{
    data(){
        return{
            names:["tan","yi","ping"],
        }
    },
    methods:{
        getName(name,e){
            console.log(name);
            console.log(e)
        }
    }
}

</script>
```



注意  参数和$event的顺序不可以改变

### 事件传参

![image-20240927085305786](D:/Typora/image-20240927085305786.png)

```vue
<template>
    <h3></h3>
    <button v-on:click="addcount('hello')">Add</button>
    <p>{{count}}</p>
    </template>
    <script>

    export default{
        data(){
            return{
                count:0,
            }
        },
       
        methods:{
            //获取event对象
            addcount(msg){
                //Vue中的Event对象，就是原生JS的Event
                //可以获取按钮  可以  修改内容
                    // e.target.innerHTML="tan"+this.count;
                    console.log(msg);
                this.count+=1;
           
            }
        }
    }
    
    </script>
```



![image-20240927090053544](D:/Typora/image-20240927090053544.png)

## 事件修饰符

![image-20240927091331070](D:/Typora/image-20240927091331070.png)

### 阻止默认事件

![image-20240927140043043](D:/Typora/image-20240927140043043.png)

![image-20240927140939038](D:/Typora/image-20240927140939038.png)

![image-20240927141336278](D:/Typora/image-20240927141336278.png)





### 阻止冒泡

![image-20240927142231719](D:/Typora/image-20240927142231719.png)

```vue
<template>
<h3>事件修饰符</h3>
<a @click.prevent="dianji" href="http://www.tanyiping.top">谭依萍的网站</a>
<div @click="divfuntion">
    <p @click.stop="pfuntion">阻止冒泡事件</p>
</div>

</template>
<script>
export default{
    data(){
        return{

        } 
    },
    methods:{
        dianji(e){
            //阻止默认事件
            // e.preventDefault();
            console.log("你被点击了");
        },
        divfuntion(){
            console.log("DIV")
        },
        pfuntion(e){
            // e.stopPropagation();
            console.log("P")
        },
    }
}
</script>
```



## 修改数据

![image-20240927145956305](D:/Typora/image-20240927145956305.png)

![image-20240927150255100](D:/Typora/image-20240927150255100.png)

### 添加数据

![image-20240927151824773](D:/Typora/image-20240927151824773.png)

由此类推 我们 就可以合并数组了

![image-20240927154829532](D:/Typora/image-20240927154829532.png)

```vue
<template>
<h3 @click="AddList">变更数据</h3>
<li v-for="name,index in names" :key="index">{{name}}</li>
<h3 v-on:click="Addshuze">变更数组</h3>
<p v-for="num1,index in number1" :key="index">{{num1}}</p>
<p v-for="num2,index in number2" :key="index">{{num2}}</p>

</template>
<script>
export default{
    data(){
        return{
            names:["tan","cheng","li"],
            number1:[1,2,3,4],
            number2:[5,6,7,8],
        }
    },
    methods:{
        AddList(){
            //在数组中 添加一个王
            this.names.push("wang");
            //用concat直接添加数组  但是 页面上的数据  并没有改变
            this.names.concat(["fang"]);
            //但是直接使用显示  可以发现  数组其实 发生了变化
            console.log(this.names.concat(["fang"]));
            //我们可以这么来使用它  //这样网页  就可以变动了
            this.names=this.names.concat(["fang"]);
    
        },
        Addshuze(){
            this.number1=this.number1.concat(this.number2);
        }
    }
}

</script>
```



## 计算属性

![image-20240927221605478](D:/Typora/image-20240927221605478.png)

![image-20240927222857860](D:/Typora/image-20240927222857860.png)

### computed

![image-20240927223210466](D:/Typora/image-20240927223210466.png)

{{jisuan}}-》注意  这里的计算  不用加（）系统用已经自动处理了

### methods

![image-20240927224132175](D:/Typora/image-20240927224132175.png)

```vue
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
```



### 区别

![image-20240927223459671](D:/Typora/image-20240927223459671.png)

## class样式绑定

### 对象形式

![image-20240928084327963](D:/Typora/image-20240928084327963.png)

### 数组形式

![image-20240928085511371](D:/Typora/image-20240928085511371.png)

![image-20240928085825171](D:/Typora/image-20240928085825171.png)

### 对象数组合并的绑定形式

**特别要注意   只能是数组里面嵌套对象   不能反其道行之**

![image-20240928090258419](D:/Typora/image-20240928090258419.png)

```vue
<template>
<p :class="{'class1':xianshi,'class2':xianshi1}">class属性</p>
<p :class="tan">class属性绑定</p>
<!-- 以数组的形式绑定 -->
<p :class="[tan1,tan2]">class属性绑定</p>
<!-- 以数组的形式绑定里面  可以用三元 运算符来判断  最后显示样式 -->
<p :class="[xianshi?'class1':' ']">class属性绑定</p>
<p :class="[xianshi?'class1 class2':' ']">class属性绑定</p>
<p :class="[xianshi?'class2':' ',{'class1':xianshi}]">class属性联合绑定</p>

</template>
<script>
export default{
    data(){
        return{
            xianshi: true,
            xianshi1:true,
            tan:{
                class1: true,
                class2: true
            },
            tan1:'class1',
            tan2:'class2'
        }
    }
}

</script>
<style>

.class1{
/* text-decoration-colrgb(81, 110, 25)een; */
color: rgb(24, 209, 24);
}
.class2{
    text-align: center;
}
</style>
```



## style绑定



![image-20240928145313489](D:/Typora/image-20240928145313489.png)

style的权重  太高了   正常情况下  class  使用的多一点

```vue
<template>
    <!-- 常规写法 -->
<p :style="{color:yanse,fontSize:zize+'px'}">style绑定1</p>
<!-- 一对象的形式  在绑定样式 -->
<p :style="yangshi">style绑定2</p>
<!-- 上面的方法  也可以 以数组的形式绑定 -->
<p :style="[yangshi]">style绑定3</p>

</template>
<script>
export default{
    data(){
        return{
            yanse:"green",
            zize:40,  

            yangshi:{
                color:"red",
                fontSize:"20px"
            },
        }
    }
}
</script>
```



## 侦听器（watch）

![image-20240928151247790](D:/Typora/image-20240928151247790.png)

```vue
<template>
<h3>侦听器</h3>  
<!-- 只能监听响应式的数据 上面的h3 是不能侦听的 -->
 <!-- 下面的响应p 标签  是可以的 -->
<p @click="bian">{{message}}</p>
</template>
<script>
export default{
    data(){
        return{
            message:'tantan',
        }
    },
    methods:{
       bian(){
        this.message="doudou"
       },
    },
    watch:{
        message(newV,oldV){
            console.log(newV,oldV)
        }
    },
}

</script>
```



## 表单输入绑定

![image-20241002095230936](D:/Typora/image-20241002095230936.png)

输入什么  同时  得到什么

![image-20241002095414753](D:/Typora/image-20241002095414753.png)

大大简化了 js的麻烦

![image-20241002101124586](D:/Typora/image-20241002101124586.png)

### 修饰符

![image-20241002101244764](D:/Typora/image-20241002101244764.png)

![image-20241002102248491](D:/Typora/image-20241002102248491.png)

或者点搜索的时候  才会显示

```vue
<template>
<h3>表单输入绑定</h3>
<form>
    <input type="text" v-model.lazy="message">
    <input type="checkbox"  id="checkbox" v-model="checkbox">
    <label for="checkbox">{{ checkbox }}</label>

</form>
<p>{{message}}</p>
</template>
<script>
export default{
    data(){
        return{
            message:"",
            checkbox:false,
        }
    },
    methods:{
    
    }
}
</script>
```



## 模板引用（$ref）

![image-20241007214735663](D:/Typora/image-20241007214735663.png)

![image-20241007220025343](D:/Typora/image-20241007220025343.png)

![image-20241007220323581](D:/Typora/image-20241007220323581.png)

**注意  一般情况 下  是不直接  更改dom的   消耗性能过大  除非  没有办法**

```vue
<template>
<div class="container" ref="container">{{tan}} </div>
<button @click="tandd">改变</button>
<input type="text" ref="neirong">
</template>
<script>
export default{
    data(){
        return{
            tan:"typ",

        }
    },
    methods:{
        tandd(){
            console.log(this.$refs.container.innerHTML);
            this.$refs.container.innerHTML="tandd";
            console.log(this.$refs.neirong.value)
        }
    },
}

</script>
```



## 组件组成（重要）

![image-20241007220604554](D:/Typora/image-20241007220604554.png)

![image-20241007223841178](D:/Typora/image-20241007223841178.png)

**我这里忘记加export default{}了**

![image-20241007224846236](D:/Typora/image-20241007224846236.png)

![image-20241007225020352](D:/Typora/image-20241007225020352.png)

### 组件的嵌套关系

![image-20241007233303162](D:/Typora/image-20241007233303162.png)

![image-20241008003459680](D:/Typora/image-20241008003459680.png)

### 组件的注册方式（全局 | 局部）

#### 全局注册



![image-20241008004603476](D:/Typora/image-20241008004603476.png)

#### 局部注册

正常的引入方式

![image-20241008004727923](D:/Typora/image-20241008004727923.png)

## 组件传递数据(父传子)



![image-20241008213227052](D:/Typora/image-20241008213227052.png)

**props转递数据  只能  父级传递给子级  不能  反其道而行之**

### 传递字符串类型

![image-20241008215431191](D:/Typora/image-20241008215431191.png)

![image-20241008220232632](D:/Typora/image-20241008220232632.png)

### 传递 多种类型（number array objeck）

![image-20241010102648286](D:/Typora/image-20241010102648286.png)

### 组件传递数据props的校验

#### 校验数据类型 （type）

![image-20241010105418970](D:/Typora/image-20241010105418970.png)

![image-20241010105640454](D:/Typora/image-20241010105640454.png)

#### 数据的默认值（default）

![image-20241010110146038](D:/Typora/image-20241010110146038.png)

**注意  只有数字  还有  字符串  可以直接用default  直接返回  数组 和字符串 要使用  函数的形式  返回默认值**

![image-20241010110928041](D:/Typora/image-20241010110928041.png)

#### 必选项（required）

![image-20241010111437834](D:/Typora/image-20241010111437834.png)

#### （重要）props传递过来的数据 是只读的

![image-20241010112257997](D:/Typora/image-20241010112257997.png)

```vue

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
```

```vue
<template>
<h1>A</h1>
<ComponentB :name="name"  :names="names"/>
</template>
<script>
import ComponentB from './ComponentB.vue';
export default{
    data(){
        return{
            name:"tan",
            age:20,
            names:["tan","yi","ping"]
        }
    },
    components:{
        ComponentB,
    }
}
</script>
```



## 组件事件（$emit）

![image-20241010112458469](D:/Typora/image-20241010112458469.png)

![image-20241010160004797](D:/Typora/image-20241010160004797.png)

![image-20241010160410690](D:/Typora/image-20241010160410690.png)

![image-20241010160601455](D:/Typora/image-20241010160601455.png)

## 组件事件配合v-model的使用

**效果： 在组件A中用户  输入数据  在组件B中 可以实时读取到  输入的数据**

![image-20241010162224216](D:/Typora/image-20241010162224216.png)

![image-20241010163329546](D:/Typora/image-20241010163329546.png)

## 组件数据传递2（props实现子传父）

![image-20241010163507347](D:/Typora/image-20241010163507347.png)

**props是可以传递任意数据  的  所以  就是基于  这种  特性   可以通过  传递函数的方式 来实现  子传父**

![image-20241010170312960](D:/Typora/image-20241010170312960.png)

**这个  我个人  认为  有点绕  不推荐   格式  数据 多了  容易 把自己 绕进去**

## 透传Attributes

![image-20241011145027636](D:/Typora/image-20241011145027636.png)

![image-20241011150952459](D:/Typora/image-20241011150952459.png)

## 插槽slots

![image-20241011151223838](D:/Typora/image-20241011151223838.png)

![image-20241011153246011](D:/Typora/image-20241011153246011.png)

#### 插槽的动态渲染

![image-20241012002206030](D:/Typora/image-20241012002206030.png)

![image-20241012002944017](D:/Typora/image-20241012002944017.png)

#### 插槽的默认值

![image-20241012003315669](D:/Typora/image-20241012003315669.png)

#### 具名插槽（v-slot -》#）

![image-20241012004509795](D:/Typora/image-20241012004509795.png)

**注意APP中的格式 v-slot：name** （推荐使用简写  不容易错）

![image-20241012004708596](D:/Typora/image-20241012004708596.png)

#### 插槽传递父和子数据

![image-20241012005221381](D:/Typora/image-20241012005221381.png)

![image-20241012010934770](D:/Typora/image-20241012010934770.png)

#### 具名插槽传递父和子数据

![image-20241012012347677](D:/Typora/image-20241012012347677.png)

```vue
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
```

```vue
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

```



## 组件的生命周期

![image-20241012012534991](D:/Typora/image-20241012012534991.png)

#### 生命周期图

![image-20241012013228940](D:/Typora/image-20241012013228940.png)

![image-20241012102357328](D:/Typora/image-20241012102357328.png)

这里的销毁生命周期  我写的有问题  好像要写成unmount

![image-20241012103003388](D:/Typora/image-20241012103003388.png)

```vue
<template>
<h3>生命周期钩子</h3>
<p>{{msg}}</p>
<button @click="bian">改变msg</button>
</template>
<script>
export default{
    data(){
        return{
            msg:"更新之前",
        }
    },
    methods:{
        bian(){
            this.msg="更新之后"
        }
    },
    beforeCreate(){
        console.log("组件创建前");
    },
    created(){
        console.log("组件创建后");
    },
    beforeMount(){
        console.log("组件渲染前");
    },
    mounted(){
        console.log("组件渲染后");
    },
    beforeUpdate(){
        console.log("组件更新前");
    },
    updated(){
        console.log("组件更新后");
    },
    beforeUnmount(){
        console.log("组件销毁前");
    },
    unmounted(){
        console.log("组件销毁后");
    }
}
</script>
```

#### 生命周期的应用

##### 首先  找到适合  读取数据的生命周期测试

##### 通过ref获取dom结构

![image-20241012104345229](D:/Typora/image-20241012104345229.png)

```vue
<template>
<h3 ref="ceshi">生命周期钩子读取数据ref测试</h3>
</template>
<script>
export default{
    data(){
        return{

        }
    },
    beforeMount(){
        console.log("我是挂载前");
        
      console.log(this.$refs.ceshi);
        
    },
    mounted(){
        console.log("我是挂载后");

        console.log(this.$refs.ceshi);

    }
}

</script>
```



##### 适合添加数据的生命周期

![image-20241012110730657](D:/Typora/image-20241012110730657.png)

```vue
<template>
<h3 ref="ceshi">生命周期钩子添加数据测试</h3>
<li v-for="(item,index) in tan" :key="index">
    <p>{{ item.num }}</p>   <p>{{ item.name }}</p>
</li>
</template>
<script>
export default{
    data(){
        return{
            tan:[]
        }
    },
    created(){
        this.tan=[
            {
                "num":1,"name":"typ"
            },
            {  "num":2,"name":"tanyp"},
            {  "num":3,"name":"tandd"},
            {  "num":4,"name":"tandoudou"},
            {  "num":5,"name":"tanyiping"},
        ]
    }
}

</script>
```



## 动态组件

实现组件的切换

使用<componnet :is="component_name" ></component>的形式来实现组件的切换

![image-20241012115226271](D:/Typora/image-20241012115226271.png)

```vue
<template>
  <component :is="bianliang"></component>
  <button @click="bian">改变组件</button>
</template>
<script>
import ComponentA from './components/ComponentA.vue';
import ComponentB from './components/ComponentB.vue';
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
```

**注意  这里组件的变量  都要用字符串  来定义**

## 组件保持存活

![image-20241012115431101](D:/Typora/image-20241012115431101.png)

#### 要知道  当组件切换的时候   组件会被自动卸载（要测试一下）

![image-20241012120859851](D:/Typora/image-20241012120859851.png)

#### 当组件切换时  它的数据  也会重新  初始化

![image-20241012121923611](D:/Typora/image-20241012121923611.png)

```vue
<template>
    <h3>compotentA组件</h3>
    <p>{{msg}}</p>
    <button @click="bianhua">改变数据</button>
</template>
<script>
export default{
    data(){
        return{
            msg:"老数据"
        }
    },
    beforeUnmount(){
    console.log("组件卸载前");
    
    },
    unmounted(){
        console.log("组件卸载后");

    },
    methods:{
        bianhua(){
            this.msg="新数据"
        }
    }
}
</script>
```

#### 实现组件保持存活<keepAlive>

![image-20241012122518489](D:/Typora/image-20241012122518489.png)

```vue
<template>
  <KeepAlive>
  <component :is="bianliang"></component>

  </KeepAlive>
  <button @click="bian">改变组件</button>
</template>
<script>
import ComponentA from './components/ComponentA.vue';
import ComponentB from './components/ComponentB.vue';
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
```



## 异步组件

![image-20241012122618510](D:/Typora/image-20241012122618510.png)

用户在使用页面的时候  可能不会到处点击  从而  页面中的组件  可能不会变化  

那些 预备变化的组件  就可以不用和默认组件一起加载  可以 用户点击之后 再加载 

大大提升性能优化（需要用的时候  再加载）

![image-20241012124459709](D:/Typora/image-20241012124459709.png)

```vue
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
```

## 依赖注入

用prop  想要实现爷-》子    过程：爷->父->子  

![image-20241012124601607](D:/Typora/image-20241012124601607.png)

要实现 爷-》子  的直接传递

![image-20241012125108443](D:/Typora/image-20241012125108443.png)

#### 死数据传递

![image-20241012131407426](D:/Typora/image-20241012131407426.png)

#### 动态数据传递

![image-20241012132110762](D:/Typora/image-20241012132110762.png)

注意：**provide和injeck只能由上往下  不能反之**

#### 根依赖

![image-20241012132919655](D:/Typora/image-20241012132919655.png)

也可以 在main.js中这样写

![image-20241012133030469](D:/Typora/image-20241012133030469.png)

## Vue应用

Vue从哪里开始执行的

![image-20241012133648857](D:/Typora/image-20241012133648857.png)

![image-20241012133740930](D:/Typora/image-20241012133740930.png)

![image-20241012134046442](D:/Typora/image-20241012134046442.png)

![image-20241012134228256](D:/Typora/image-20241012134228256.png)

**浏览器  可执行文件 HTML CSS JS Image**

其实Vue  是不能被直接被执行的  靠的构建工具  来实现编译的

![image-20241012134549272](D:/Typora/image-20241012134549272.png)

![image-20241012134632543](D:/Typora/image-20241012134632543.png)