<template>
  <div style="">
    <h2>购物车</h2>
    <table>
        <tr>
            <td>勾选</td>
            <td>课程名称</td>
            <td>课程价格</td>
            <td>数量</td>
            <td>价格</td>
        </tr>
    </table>
    {{ title.name }}
    <!-- <button @click="sendMsgsendMsg" type='button' name='button'>传递数据</button> -->
    <div class="example" :title="titleliudd"> 
        <p>{{ 20+2 }} {{ 30*2 }}</p>
        <p>{{}}</p>
        <p>original message: {{message}}</p>
        <p>computed reversed message: {{ reversedMessage}}</p>
    </div>
    <div><p :class="monday">今天是2019/11/11</p></div>
    <div><p :class="{today: liudd}">2019/11/11</p></div>
    <p :class="{'c1': c1,'c2':c2}">对象class</p>
    <p :class="['c1','c2']">哈哈，我是数组class</p>
    <p :class="obj">迪奥</p>
    <button @click="chageClass()">改变class</button>
    <p :class="[{'active': isactive}, {'erronactive': erronactive}]"> active 这个 class 存在与否将取决于数据属性 isActive 的真假（truthy） </p>
    <p :class="classObject">绑定的数据对象不必内联定义在模板里</p>
    <div :class="classObject2">也可以绑定一个返回对象的计算属性</div>
    <p v-bind:style="styleObject">style 属性</p>
    <hr>
    <p>
      <label for="">表单</label>
      <input type="text" v-model="message">
    </p>
    <div> watch:监听事件----> {{message}} </div>
    <div>
      <p>watch监听事件2</p> 
      <p>{{myname}}</p>
      <button @click="mynameClick()">mynameClick</button>
    </div>
    <p>
      单个复选框，绑定到布尔值<br>
      <input type="checkbox" id="checkbox" v-model="checked">
      <label for="checkbox">{{ checked }}</label>
    </p>
    
  </div>
</template>

<script>

  export default {
    name:'',
    props:['title'],
    data () {
      return {
         message: 'hello',
         titleliudd: 'titleliudd',
         monday: "monday",
         today: true,
         liudd: "today",
         c1: true,
         c2: true,
         obj: {
           s1: 's1',
           s2: 's2'
         },
         isactive: true,
         erronactive: true,
         classObject: {
           'text-active':true,
           err: true
         },
          styleObject: {
            color: 'red',
            fontSize: '18px'
          },
          checked:true,
          myname: "liudd"
      };
    },

    components: {},
    // 计算属性
    computed: {
       reversedMessage(){
         return this.message.split("").reverse().join("")
       },
       classObject2 () {
         return {
           obj: true,
           liudd: false
         }
       }
    },

    beforeMount() {},

    mounted() {},

    methods: {
      chageClass(c1){
          this.c1 = false
       },
       mynameClick(){
        return this.myname += 1
       }
    },

    watch: {
      message (data){ // 必须是v-model里的才行
        console.log(data)
      },
      myname(data){
         console.log(data)
      }
    }

  }

</script>
<style lang='' scoped>
.c1{color: red}
.s1{font-weight: bold}
.active{font-size: 22px}
</style>
