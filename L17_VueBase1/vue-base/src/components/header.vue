<template>
  <div class="headerclass">
    <div :style="{color: activeColor,fontSize: fontSize + 'px'}" >
      <p :class="{active: isactive, classLiudd1,'text-danger':hasError}">
        我是header组件哦
      </p>
      <p>本节内容 ： Class 与 Style 绑定</p>
    </div>
    <h4>
      <p :class="classObject">
        绑定的数据对象不必内联定义在模板里
      </p>
      <p :class="classComputed">
        我们也可以在这里绑定一个返回对象的计算属性。这是一个常用且强大的模式
      </p>
    </h4>
    
    <h5>active 这个 class 存在与否将取决于数据属性 isActive 的真假--> active: isactive</h5>
    
   
  </div>
</template>
<script>
  export default {
    name:'',
    props:['seller'],
    data () {
      return {
         activeColor : 'red',
         fontSize : 16,
         classLiudd1: 'classLiudd1',
         isactive: true,
         error: null,
         hasError: false,
         classObject:{
           class1:false,
           'text-class2': true
         }
      };
    },

    components: {},

    computed: {
      classComputed: function(){
            return {
              classComputed1: this.isactive && !this.error,
              'text-danger2': this.error === null,
              'text-danger3': this.error && this.error.type === 'fatal'
            }
         }
    },

    beforeMount() {},

    mounted() {},

    methods: {},

    watch: {}

  }

</script>
<style lang='' scoped>
.classLiudd1{font-weight: bold}
.headerclass{
  background: #cccccc
}
</style>